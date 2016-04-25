class SimplerExpandableListAdapter extends BaseExpandableListAdapter{
 private Context mContext;
 private String[][] mContents;
 private String[] mTitles;
 private LayoutInflater inflater;
 public SimplerExpandableListAdapter(Context context, String[] titles, String[][] contents, LayoutInflater inflater)
 {
  super();
  if(titles.length != contents.length){
   throw new IllegalArgumentException("Titles and Contents must be the same size.");
  }
  mContext = context;
  mContents = contents;
  mTitles = titles;
  this.inflater = inflater;
 }
 @Override
 public String getChild(int groupPosition, int childPosition){
  return mContents[groupPosition][childPosition];
 }
 @Override
 public long getChildId(int groupPosition, int childPosition){
  return 0;
 }
 @Override
 public View getChildView(int groupPosition, int childPosition, boolean isLastChild, View convertView,
         ViewGroup parent)
 {
  View v = inflater.inflate(R.layout.list_item_editprod, null);
  final EditText title = (EditText)v.findViewById(R.id.title);
  final EditText content = (EditText)v.findViewById(R.id.content);
  title.setText(mTitles[groupPosition]);
  content.setText(mContents[groupPosition][childPosition]);
  Button btnOk = (Button)v.findViewById(R.id.btnOk);
  btnOk.setOnClickListener(new OnClickListener(){
   @Override
   public void onClick(View v){
    Toast.makeText(v.getContext(), "OK: title:" + title.getText() + " content:" + content.getText(),
            Toast.LENGTH_SHORT).show();
   }
  });
  Button btnCancel = (Button)v.findViewById(R.id.btnCancel);
  btnCancel.setOnClickListener(new OnClickListener(){
   @Override
   public void onClick(View v){
    Toast.makeText(v.getContext(), "Cancel: title:" + title.getText() + " content:" + content.getText(),
            Toast.LENGTH_SHORT).show();
   }
  });
  return v;
 }
 @Override
 public int getChildrenCount(int groupPosition){
  return mContents[groupPosition].length;
 }
 @Override
 public String[] getGroup(int groupPosition){
  return mContents[groupPosition];
 }
 @Override
 public int getGroupCount(){
  return mContents.length;
 }
 @Override
 public long getGroupId(int groupPosition){
  return 0;
 }
 @Override
 public View getGroupView(int groupPosition, boolean isExpanded, View convertView, ViewGroup parent){
  //EditText row = (EditText)convertView;
  TextView row = (TextView)convertView;
  if(row == null){
   row = new TextView(mContext);
  }
  row.setTypeface(Typeface.DEFAULT_BOLD);
  row.setText(mTitles[groupPosition]);
  return row;
 }
 @Override
 public boolean hasStableIds(){
  return false;
 }
 @Override
 public boolean isChildSelectable(int groupPosition, int childPosition){
  return true;
 }
}

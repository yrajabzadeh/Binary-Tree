import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class BinaryTree 
{
	public BinaryTree( ) 
{
	root = null;
}
	public void insert( Comparable x ) 
{
	root = insert( x, root );
}
	public void remove( Comparable x ) 
{
	root = remove( x, root );
}
	public void removeMin( ) 
{
	root = removeMin( root );
}
	public Comparable findMin( ) 
{
	return elementAt( findMin( root ) );
}
	public Comparable findMax( ) 
{
	return elementAt( findMax( root ) );
}
	public Comparable find( Comparable x ) 
{
	return elementAt( find( x, root ) );
}
	public void makeEmpty( ) 
{
	root = null;
}
	public boolean isEmpty( ) 
{
	return root == null;
}
	private Comparable elementAt( BinaryNode t ) 
{
	return t == null ? null : t.element;
}
	protected BinaryNode insert( Comparable x, BinaryNode t ) 
{

if( t == null )
t = new BinaryNode( x );
else if( x.compareTo( t.element ) < 0 )
t.left = insert( x, t.left );
else if( x.compareTo( t.element ) > 0 )
t.right = insert( x, t.right );
else
;
return t;

	}
}

protected BinaryNode remove( Comparable x, BinaryNode t ) 

{

if( t == null )
throw new ItemNotFoundException( x.toString( ));
if( x.compareTo( t.element ) < 0 )
t.left = remove( x, t.left );
else if( x.compareTo( t.element ) > 0 )
t.right = remove( x, t.right );
else if( t.left != null && t.right != null )
{
	t.element = findMin( t.right ).element;
	t.right = removeMin( t.right );
}

else
t = ( t.left != null ) ? t.left : t.right;
return t;

}
protected BinaryNode removeMin( BinaryNode t ) 

{

if( t == null )
throw new ItemNotFoundException( );
else if( t.left != null ) {
t.left = removeMin( t.left );
return t;
} 

else
return t.right;

}

protected BinaryNode findMin( BinaryNode t ) 
{
if( t != null )
while( t.left != null )
t = t.left;
return t;
}

private BinaryNode findMax( BinaryNode t ) 

{

if( t != null )
while( t.right != null )
t = t.right;
return t;

}
private BinaryNode find( Comparable x, BinaryNode t ) 

{

while( t != null ) 

{

if( x.compareTo( t.element ) < 0 )
t = t.left;
else if( x.compareTo( t.element ) > 0 )
t = t.right;
else
return t;

}

return null;

}

protected BinaryNode root;
public static void main( String [ ] args ) 

{

BinaryTree t = new BinaryTree( );
final int NUMS = 4000;
final int GAP = 37;

System.out.println( "Checking output" );
for( int i = GAP; i != 0; i = ( i + GAP ) % NUMS )
t.insert( new Integer( i ) );
for( int i = 1; i < NUMS; i+= 2 )
t.remove( new Integer( i ) );
if( ((Integer)(t.findMin( ))).intValue( ) != 2 ||
((Integer)(t.findMax( ))).intValue( ) != NUMS - 2 )

System.out.println( "FindMin or FindMax error!" );
for( int i = 2; i < NUMS; i+=2 )
if( ((Integer)(t.find( new Integer( i ) ))).intValue( ) != i )
System.out.println( "Find error1!" );
for( int i = 1; i < NUMS; i+=2 ) {
if( t.find( new Integer( i ) ) != null )
System.out.println( "Find error2!" );

}

# ED
public class ListaNoDuplo<T> implements TADLista<T> {
		private No<T> inicio;
	@SuppressWarnings("unchecked")
	@Override
	public void add(T o) {
		No<T> novoNo = new No<T>();
		novoNo.setElemento((Comparable<T>)o);
		if(inicio == null ){
			inicio = novoNo;
		}
		else {
			No<T> noAUX = inicio;
			while (noAUX.getProximoNo()!=null){
				if(noAUX.getElemento().compareTo((T)o)<=-1 & noAUX.getProximoNo().getElemento().compareTo((T)o)>=1){
					novoNo.setProximoNo(noAUX.getProximoNo());
					novoNo.setAnterior(noAUX);
					noAUX.getProximoNo().setAnterior(novoNo);
					noAUX.setProximoNo(novoNo);
					break;
				}
				
			noAUX = noAUX.getProximoNo();
			}
			if (noAUX.getProximoNo()== null & noAUX.getElemento().compareTo((T)o)<=-1){
				novoNo.setAnterior(noAUX);
				noAUX.setProximoNo(novoNo);
			}
			else if(noAUX.getProximoNo()== null & noAUX.getElemento().compareTo((T)o)>=1){
				novoNo.setProximoNo(inicio);
				inicio.setAnterior(novoNo);
				inicio = novoNo;
			}
		}
		
	}

	@Override
	public boolean contains(T o) {
		// TODO Auto-generated method stub
		return false;
	}

	@Override
	public int indexOf(T o) {
		// TODO Auto-generated method stub
		return 0;
	}

	@Override
	public boolean remove(T o) {
		
		return false;
	}

	@Override
	public int size() {
		// TODO Auto-generated method stub
		return 0;
	}



}

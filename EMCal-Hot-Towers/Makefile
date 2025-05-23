##
# Hot Towers Analysis
#
# @file
# @version 0.1

ROOT_CPPFLAGS = `root-config --cflags`
ROOT_LIBFLAGS = `root-config --libs`
sPHENIX_CPPFLAGS = -I$(MYINSTALL)/include -I$(OFFLINE_MAIN)/include -I$(OFFLINE_MAIN)/rootmacros
sPHENIX_LIBFLAGS = -L$(OFFLINE_MAIN)/lib -lcalo_io -lcalo_reco -lcdbobjects -lffamodules -lphool
LIBFLAGS = -L$(MYINSTALL)/lib -lCaloHotTower

all: bin/hotAna bin/hotTypeAna bin/plots bin/genCDBTTree bin/genHotTowerList bin/convertHotList bin/Fun4All_CaloHotTower bin/Fun4All_CaloHotTowerSim bin/plots-hot

bin/hotAna: macro/HotTowerAnalysis.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS)

bin/hotTypeAna: macro/HotTowerTypeAnalysis.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS)

bin/plots: macro/display.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(ROOT_LIBFLAGS) -I$(OFFLINE_MAIN)/rootmacros

bin/genCDBTTree: macro/genCDBTTree.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_CPPFLAGS) $(sPHENIX_LIBFLAGS)

bin/genHotTowerList: macro/genHotTowerList.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS)

bin/convertHotList: macro/convertHotList.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS)

bin/plots-hot: macro/display-hot.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS)

bin/Fun4All_CaloHotTower: macro/Fun4All_CaloHotTower.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(LIBFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS) -lfun4all -lphparameter -lffarawobjects -lcalotrigger

bin/Fun4All_CaloHotTowerSim: macro/Fun4All_CaloHotTowerSim.C
	mkdir -p bin
	g++ -o $@ $< $(ROOT_CPPFLAGS) $(sPHENIX_CPPFLAGS) $(LIBFLAGS) $(ROOT_LIBFLAGS) $(sPHENIX_LIBFLAGS) -lfun4all -lphparameter

clean:
	rm bin/hotAna
	rm bin/hotTypeAna
	rm bin/plots
	rm bin/plots-hot
	rm bin/genHotTowerList
	rm bin/convertHotList
	rm bin/Fun4All_CaloHotTower
	rm bin/Fun4All_CaloHotTowerSim

# end

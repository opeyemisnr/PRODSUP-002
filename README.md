It is taking lot of time to run because of this code in circle.yml file

private void validate() throws IllegalArgumentException {
+ for (int i=0; i<20*60*60; i++) {
+ System.out.print('.');
+ try {
+ Thread.currentThread().sleep(1000);
+ } catch (InterruptedException e) {
+ break;
+ }
+ }

This method is called upon lot of time , which causing a loop .Change the loop with something like below and build will execute in 2 minutes

private void validate() throws IllegalArgumentException {
+ for (int i=0; i<100; i++) {
+ System.out.print('.');
+ try {
+ Thread.currentThread().sleep(1);
+ } catch (InterruptedException e) {
+ break;
+ }
+ }

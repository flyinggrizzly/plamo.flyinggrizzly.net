- Hey. I'm Sean. I really enjoy making plastic models, and this is where I keep track of and chat shit to myself about my work.
- query-table:: false
  #+BEGIN_QUERY
   {
      :title [:b "build-log entries"]
      :query [ :find (pull ?p [*])
                    :where
                    [?p :block/namespace ?namespace]
                    [?namespace :block/name "build-log"]]
      :result-transform (fn [result]
                                           (sort-by (comp - (fn [h] (get h :block/name))) result))
  }
  #+END_QUERY
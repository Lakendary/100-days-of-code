Model
	-Add validation
	-Add System.ComponentModel.DataAnnotations
	-Examples of validation on properties:
		[Required]
        [MaxLength(50, ErrorMessage = "Name cannot exceed 50 characters")]
        [RegularExpression(@"^[a-zA-Z0-9_.+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9-.]+$", ErrorMessage = "Invalid Email format")]
        [Display(Name = "Office Email")]
    -Add Repository with CRUD methods
    -Interface:
    	Employee GetEmployee(int id);
        IEnumerable<Employee> GetEmployees();
        Employee Add(Employee employee);
        Employee Update(Employee employeeChanges);
        Employee Delete(int id);
    -Implement Repository (Data)
    -Add AppDbContext and inherit DbContext (Microsoft.EntityFramework)
    	//	Add constructor and add options
    	public AppDbContext(DbContextOptions<AppDbContext> options)
            : base(options)
        {

        }
        //	Add DbSet with Model i.e. Database table
        public DbSet<Employee> Employees { get; set; }


View
Controller
# CWmiFinalizer::SetStatus(long,long,ushort *,IWbemClassObject *)

- ea: `0x1800051f0`
- end: `0x180005a56`
- name: `?SetStatus@CWmiFinalizer@@QEAAJJJPEAGPEAUIWbemClassObject@@@Z`
- size: `2150`
- prototype: `__int64 __usercall@<rax>(CWmiFinalizer *__hidden this@<rcx>, int@<edx>, int@<r8d>, unsigned __int16 *@<r9>, struct IWbemClassObject *)`
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800050f0`
- `0x18000816c`

## callees

- `0x180004bf8`
- `0x180004d20`
- `0x180004de8`
- `0x1800051f0`
- `0x1800061b0`
- `0x1800066a0`
- `0x180006b9c`
- `0x18000898c`
- `0x180008b70`
- `0x180009b90`
- `0x18000b104`
- `0x18000b140`
- `0x18000b46c`
- `0x18003cfe0`
- `0x1800da010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180005732`
- `msvcrt!_wcsnicmp` at `0x180005819`
- `msvcrt!_wcsnicmp` at `0x180005732`
- `msvcrt!_wcsnicmp` at `0x180005819`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000553e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800055a8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000553e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800055a8`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000531b`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18000531b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180005256`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800053d2`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000542b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000548a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800056ae`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x180005256`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800053d2`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000542b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18000548a`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x1800056ae`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005271`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005413`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000544d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800054b9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800054f2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800056dd`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005271`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x180005413`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18000544d`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800054b9`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800054f2`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x1800056dd`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800053e3`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000554d`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x1800053e3`
- `wbemcomn!?Size@CFlexArray@@QEBAHXZ` at `0x18000554d`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180005529`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x180005529`
- `wbemcomn!GetMemLogObject` at `0x180005865`
- `wbemcomn!GetMemLogObject` at `0x1800058ce`
- `wbemcomn!GetMemLogObject` at `0x18000596b`
- `wbemcomn!GetMemLogObject` at `0x1800059ca`
- `wbemcomn!GetMemLogObject` at `0x180005865`
- `wbemcomn!GetMemLogObject` at `0x1800058ce`
- `wbemcomn!GetMemLogObject` at `0x18000596b`
- `wbemcomn!GetMemLogObject` at `0x1800059ca`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005873`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005979`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800059d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005873`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058d9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005979`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800059d8`
- `OLEAUT32!__imp_SysAllocString` at `0x18000562f`
- `OLEAUT32!__imp_SysAllocString` at `0x180005852`
- `OLEAUT32!__imp_SysAllocString` at `0x18000562f`
- `OLEAUT32!__imp_SysAllocString` at `0x180005852`
- `OLEAUT32!__imp_SysFreeString` at `0x18000583c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000583c`

## pseudocode

```c

```

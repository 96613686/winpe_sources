# CQueryEngine::ExecQlQuery(CWbemNamespace *,ushort *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18003d3b0`
- end: `0x18003f044`
- name: `?ExecQlQuery@CQueryEngine@@CAJPEAVCWbemNamespace@@PEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `7316`
- prototype: `__int64 __fastcall(struct CWbemNamespace *this, unsigned __int16 *, int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `29`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003a030`

## callees

- `0x18000aed8`
- `0x18000b104`
- `0x18000b140`
- `0x18000b46c`
- `0x18000e950`
- `0x18001307c`
- `0x18002bf10`
- `0x18002ca8c`
- `0x180035390`
- `0x18003cd90`
- `0x18003cfe0`
- `0x18003d050`
- `0x18003d3b0`
- `0x18003f04c`
- `0x18003f2a0`
- `0x18003f74c`
- `0x180041324`
- `0x180053530`
- `0x18005e92c`
- `0x18005fd50`
- `0x180061fd8`
- `0x180071268`
- `0x18007258c`
- `0x18008837c`
- `0x18008ae80`
- `0x18008d608`
- `0x18009c6e4`
- `0x1800b1ef8`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dc73`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003dc73`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003df92`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003dfeb`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003df92`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18003dfeb`
- `wbemcomn!??1QL_LEVEL_1_TOKEN@@QEAA@XZ` at `0x18003da67`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x18003d46d`
- `wbemcomn!??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z` at `0x18003d46d`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18003d49e`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18003e51a`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18003d49e`
- `wbemcomn!??1QL1_Parser@@UEAA@XZ` at `0x18003e51a`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x18003d481`
- `wbemcomn!?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z` at `0x18003d481`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x18003dabe`
- `wbemcomn!??1QL_LEVEL_1_RPN_EXPRESSION@@QEAA@XZ` at `0x18003dabe`
- `wbemcomn!?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d4aa`
- `wbemcomn!?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d784`
- `wbemcomn!?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d4aa`
- `wbemcomn!?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d784`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d597`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003de06`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003df3a`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e0ce`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e213`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e386`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e3ed`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e444`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e48e`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e4a3`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003d597`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003de06`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003df3a`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e0ce`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e213`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e386`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e3ed`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e444`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e48e`
- `wbemcomn!?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ` at `0x18003e4a3`
- `wbemcomn!?GetText@QL_LEVEL_1_RPN_EXPRESSION@@QEAAPEAGXZ` at `0x18003dafe`
- `wbemcomn!?GetText@QL_LEVEL_1_RPN_EXPRESSION@@QEAAPEAGXZ` at `0x18003dafe`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003db70`
- `wbemcomn!??0WString@@QEAA@XZ` at `0x18003db70`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d66e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d7ae`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d88a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d9a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d9d4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003db36`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003de4e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d66e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d7ae`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d88a`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d9a0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003d9d4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003db36`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18003de4e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003da39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003da7e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003dac7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ddba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e1c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e29c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e336`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003da39`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003da7e`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003dac7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003ddba`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e1c7`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e29c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18003e336`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003d875`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003dbe6`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003d875`
- `wbemcomn!??0CCritSec@@QEAA@XZ` at `0x18003dbe6`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003d951`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003dba9`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003dbca`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003d951`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003dba9`
- `wbemcomn!??0CFlexArray@@QEAA@HH@Z` at `0x18003dbca`
- `wbemcomn!GetMemLogObject` at `0x18003deaa`
- `wbemcomn!GetMemLogObject` at `0x18003e052`
- `wbemcomn!GetMemLogObject` at `0x18003e4b9`
- `wbemcomn!GetMemLogObject` at `0x18003e546`
- `wbemcomn!GetMemLogObject` at `0x18003e59c`
- `wbemcomn!GetMemLogObject` at `0x18003e611`
- `wbemcomn!GetMemLogObject` at `0x18003e6b7`
- `wbemcomn!GetMemLogObject` at `0x18003e71d`
- `wbemcomn!GetMemLogObject` at `0x18003e7c0`
- `wbemcomn!GetMemLogObject` at `0x18003e840`
- `wbemcomn!GetMemLogObject` at `0x18003e95c`
- `wbemcomn!GetMemLogObject` at `0x18003ea55`
- `wbemcomn!GetMemLogObject` at `0x18003eaa8`
- `wbemcomn!GetMemLogObject` at `0x18003eb1c`
- `wbemcomn!GetMemLogObject` at `0x18003eba0`
- `wbemcomn!GetMemLogObject` at `0x18003ec2e`
- `wbemcomn!GetMemLogObject` at `0x18003ec6e`
- `wbemcomn!GetMemLogObject` at `0x18003ecf4`
- `wbemcomn!GetMemLogObject` at `0x18003ed7e`
- `wbemcomn!GetMemLogObject` at `0x18003edbd`
- `wbemcomn!GetMemLogObject` at `0x18003ee29`
- `wbemcomn!GetMemLogObject` at `0x18003ee75`
- `wbemcomn!GetMemLogObject` at `0x18003eeb9`
- `wbemcomn!GetMemLogObject` at `0x18003ef18`
- `wbemcomn!GetMemLogObject` at `0x18003ef7a`
- `wbemcomn!GetMemLogObject` at `0x18003efdc`
- `wbemcomn!GetMemLogObject` at `0x18003deaa`
- `wbemcomn!GetMemLogObject` at `0x18003e052`
- `wbemcomn!GetMemLogObject` at `0x18003e4b9`
- `wbemcomn!GetMemLogObject` at `0x18003e546`
- `wbemcomn!GetMemLogObject` at `0x18003e59c`
- `wbemcomn!GetMemLogObject` at `0x18003e611`
- `wbemcomn!GetMemLogObject` at `0x18003e6b7`
- `wbemcomn!GetMemLogObject` at `0x18003e71d`
- `wbemcomn!GetMemLogObject` at `0x18003e7c0`
- `wbemcomn!GetMemLogObject` at `0x18003e840`
- `wbemcomn!GetMemLogObject` at `0x18003e95c`
- `wbemcomn!GetMemLogObject` at `0x18003ea55`
- `wbemcomn!GetMemLogObject` at `0x18003eaa8`
- `wbemcomn!GetMemLogObject` at `0x18003eb1c`
- `wbemcomn!GetMemLogObject` at `0x18003eba0`
- `wbemcomn!GetMemLogObject` at `0x18003ec2e`
- `wbemcomn!GetMemLogObject` at `0x18003ec6e`
- `wbemcomn!GetMemLogObject` at `0x18003ecf4`
- `wbemcomn!GetMemLogObject` at `0x18003ed7e`
- `wbemcomn!GetMemLogObject` at `0x18003edbd`
- `wbemcomn!GetMemLogObject` at `0x18003ee29`
- `wbemcomn!GetMemLogObject` at `0x18003ee75`
- `wbemcomn!GetMemLogObject` at `0x18003eeb9`
- `wbemcomn!GetMemLogObject` at `0x18003ef18`
- `wbemcomn!GetMemLogObject` at `0x18003ef7a`
- `wbemcomn!GetMemLogObject` at `0x18003efdc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003deb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e060`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e4c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e554`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e5aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e61f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e6c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e72b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e7cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e84e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e967`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ea60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eb2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ebae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ec3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ec7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003edc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ee37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ee83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eec7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003efea`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003deb8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e060`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e4c7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e554`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e5aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e61f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e6c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e72b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e7cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e84e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003e967`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ea60`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eab6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eb2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ebae`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ec3c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ec7c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed02`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ed8c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003edc9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ee37`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ee83`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003eec7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef2c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003ef8e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003efea`
- `esscli!??0CContextMetaData@@QEAA@PEAVCMetaData@@PEAUIWbemContext@@@Z` at `0x18003d9f8`
- `esscli!??0CContextMetaData@@QEAA@PEAVCMetaData@@PEAUIWbemContext@@@Z` at `0x18003d9f8`
- `esscli!??0CStandardMetaData@@QEAA@PEAUIWbemServices@@@Z` at `0x18003d9bd`
- `esscli!??0CStandardMetaData@@QEAA@PEAUIWbemServices@@@Z` at `0x18003d9bd`
- `esscli!?SimplifyQueryForChild@CQueryAnalyser@@SAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemClassObject@@PEAVCContextMetaData@@AEAPEAU2@@Z` at `0x18003da25`
- `esscli!?SimplifyQueryForChild@CQueryAnalyser@@SAJPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEBGPEAUIWbemClassObject@@PEAVCContextMetaData@@AEAPEAU2@@Z` at `0x18003da25`
- `esscli!??1CContextMetaData@@QEAA@XZ` at `0x18003da30`
- `esscli!??1CContextMetaData@@QEAA@XZ` at `0x18003da30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e7b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003e7b4`
- `OLEAUT32!__imp_SysAllocString` at `0x18003e835`
- `OLEAUT32!__imp_SysAllocString` at `0x18003e835`
- `OLEAUT32!__imp_VariantInit` at `0x18003e8eb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CQueryEngine::ExecQlQuery(
        struct CWbemNamespace *this,
        unsigned __int16 *a2,
        int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  CBasicObjectSink *v9; // rbx
  __int64 result; // rax
  QL_LEVEL_1_RPN_EXPRESSION *v11; // rdi
  int v12; // eax
  __int64 v13; // rdx
  int *v14; // r8
  const unsigned __int16 *v15; // rsi
  unsigned __int16 *i; // r14
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // cx
  unsigned int v19; // ebx
  CProjectingSink *v20; // r14
  int v21; // eax
  CBasicObjectSink *v22; // rax
  CBasicObjectSink *v23; // rsi
  struct QL_LEVEL_1_RPN_EXPRESSION *v24; // rbx
  __int64 v25; // rcx
  CBasicObjectSink *v26; // rax
  CBasicObjectSink *v27; // rbx
  __int64 v28; // rcx
  struct CContextMetaData *v29; // rsi
  CBasicObjectSink *v30; // rax
  CBasicObjectSink *v31; // r15
  __int64 v32; // rcx
  struct IWbemServices *v33; // rbx
  CBasicObjectSink *v34; // rax
  struct CMetaData *v35; // rbx
  CBasicObjectSink *v36; // rax
  struct IWbemContext *v37; // r14
  int v38; // ebx
  struct QL_LEVEL_1_RPN_EXPRESSION *v39; // rax
  struct QL_LEVEL_1_RPN_EXPRESSION *v40; // rdx
  char *v41; // rcx
  char *v42; // rbx
  struct QL_LEVEL_1_RPN_EXPRESSION *v43; // rbx
  unsigned int v44; // r13d
  unsigned __int16 *Text; // rax
  unsigned __int16 *v46; // r12
  char *v47; // rax
  char *v48; // rsi
  __int64 v49; // rax
  struct _IWmiArbitrator *v50; // r14
  struct _IWmiCoreHandle *v51; // rbx
  _QWORD *Value; // rax
  __int64 v53; // rax
  int v54; // eax
  CBasicObjectSink *v55; // rbx
  CBasicObjectSink *v56; // rax
  CBasicObjectSink *v57; // rsi
  CMemoryLog *v58; // rax
  int v59; // edx
  unsigned int v60; // ebx
  struct IWbemClassObject *v61; // rbx
  CMemoryLog *v62; // rax
  unsigned int v63; // esi
  unsigned int v64; // r13d
  unsigned int v65; // r13d
  unsigned int v66; // ebx
  CMemoryLog *MemLogObject; // rax
  unsigned int v68; // ebx
  CMemoryLog *v69; // rax
  CClientCnt *v70; // rcx
  __int64 v71; // rdx
  CMemoryLog *v72; // rax
  CMemoryLog *v73; // rax
  CMemoryLog *v74; // rax
  CMemoryLog *v75; // rax
  HRESULT v76; // ebx
  CMemoryLog *v77; // rax
  BSTR v78; // rax
  CMemoryLog *v79; // rax
  int v80; // ebx
  CMemoryLog *v81; // rax
  CClientCnt *v82; // rcx
  __int64 v83; // rdx
  CMemoryLog *v84; // rax
  CMemoryLog *v85; // rax
  CMemoryLog *v86; // rax
  CMemoryLog *v87; // rax
  CClientCnt *v88; // rcx
  __int64 v89; // rdx
  CMemoryLog *v90; // rax
  CMemoryLog *v91; // rax
  CClientCnt *v92; // rcx
  __int64 v93; // rdx
  CMemoryLog *v94; // rax
  int v95; // edx
  CMemoryLog *v96; // rax
  CMemoryLog *v97; // rax
  CMemoryLog *v98; // rax
  CMemoryLog *v99; // rax
  CMemoryLog *v100; // rax
  CMemoryLog *v101; // rax
  CMemoryLog *v102; // rax
  unsigned int v103; // r13d
  CMemoryLog *v104; // rax
  struct CDynasty *v105; // [rsp+50h] [rbp-1B8h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-1B0h] BYREF
  WCHAR DestStr; // [rsp+60h] [rbp-1A8h] BYREF
  struct QL_LEVEL_1_RPN_EXPRESSION *v108; // [rsp+68h] [rbp-1A0h]
  struct QL_LEVEL_1_RPN_EXPRESSION *v109; // [rsp+70h] [rbp-198h] BYREF
  struct QL_LEVEL_1_RPN_EXPRESSION *v110; // [rsp+78h] [rbp-190h] BYREF
  LPVOID *p_ppv; // [rsp+80h] [rbp-188h] BYREF
  CBasicObjectSink *v112; // [rsp+88h] [rbp-180h] BYREF
  CBasicObjectSink *v113; // [rsp+90h] [rbp-178h] BYREF
  struct IWbemClassObject *v114; // [rsp+98h] [rbp-170h] BYREF
  unsigned int v115; // [rsp+A0h] [rbp-168h]
  struct IWbemClassObject *v116; // [rsp+A8h] [rbp-160h] BYREF
  CBasicObjectSink *v117; // [rsp+B0h] [rbp-158h]
  VARIANTARG v118; // [rsp+B8h] [rbp-150h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-138h] BYREF
  _QWORD v121[4]; // [rsp+F0h] [rbp-118h] BYREF
  _BYTE v122[248]; // [rsp+110h] [rbp-F8h] BYREF
  int SrcStr; // [rsp+220h] [rbp+18h] BYREF
  struct IWbemContext *v126; // [rsp+228h] [rbp+20h]

  v126 = a4;
  v115 = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      49,
      (unsigned int)WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  }
  LODWORD(v112) = a3 & 1;
  v9 = a5;
  if ( (a3 & 1) == 0 )
  {
    result = CQueryEngine::ExecComplexQuery(this, a2, a3, a4, a5);
    if ( (int)result >= 0 )
      return result;
  }
  v121[0] = &CTextLexSource::`vftable';
  v121[2] = a2;
  v121[1] = a2;
  v109 = 0;
  QL1_Parser::QL1_Parser((QL1_Parser *)v122, (struct CGenLexSource *)v121);
  if ( QL1_Parser::Parse((QL1_Parser *)v122, &v109) )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217385);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749911LL);
    }
    v68 = CBasicObjectSink::Return(v9, -2147217385, 0);
    QL1_Parser::~QL1_Parser((QL1_Parser *)v122);
    return v68;
  }
  QL1_Parser::~QL1_Parser((QL1_Parser *)v122);
  QL_LEVEL_1_RPN_EXPRESSION::AddRef(v109);
  v11 = v109;
  v108 = v109;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 88LL))(*((_QWORD *)this + 5), 0);
  v14 = (int *)v109;
  if ( !v12 )
  {
    if ( v109 )
    {
      if ( *((_QWORD *)v109 + 3) )
      {
        LODWORD(v110) = 1;
        if ( !*((_DWORD *)v109 + 18) )
          goto LABEL_9;
      }
    }
    v69 = GetMemLogObject();
    CMemoryLog::Write(v69, -2147217385);
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v71 = 53;
LABEL_301:
      WPP_SF_d(*((_QWORD *)v70 + 2), v71, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749911LL);
    }
LABEL_302:
    v60 = CBasicObjectSink::Return(v9, -2147217385, 0);
LABEL_102:
    if ( v11 )
      QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
    v108 = 0;
    return v60;
  }
  if ( *((_DWORD *)v109 + 18) || (LODWORD(v110) = 0, !*((_QWORD *)v109 + 3)) )
  {
    v104 = GetMemLogObject();
    CMemoryLog::Write(v104, -2147217385);
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v71 = 52;
      goto LABEL_301;
    }
    goto LABEL_302;
  }
LABEL_9:
  v15 = L"meta_class";
  for ( i = (unsigned __int16 *)*((_QWORD *)v109 + 3); ; ++i )
  {
    v17 = *i;
    if ( *i )
    {
      if ( v17 > 0x7Fu )
      {
        LOWORD(SrcStr) = *i;
        DestStr = 0;
        v17 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, &DestStr, 1) ? DestStr : SrcStr;
        v14 = (int *)v109;
      }
      else if ( (unsigned __int16)(v17 - 65) <= 0x19u )
      {
        v17 += 32;
      }
    }
    else if ( !*v15 )
    {
      if ( v14[12] > 0 || !v14[14] )
      {
        v72 = GetMemLogObject();
        CMemoryLog::Write(v72, -2147217385);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
            2147749911LL);
        }
        v19 = CBasicObjectSink::Return(a5, -2147217385, 0);
        goto LABEL_163;
      }
      v19 = CQueryEngine::ExecSchemaQuery(this, a2, (struct QL_LEVEL_1_RPN_EXPRESSION *)v14, a4, a5);
      if ( v11 )
      {
        QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
        v108 = 0;
        return v19;
      }
LABEL_165:
      v108 = 0;
      return v19;
    }
    v18 = *v15;
    if ( *v15 > 0x7Fu )
    {
      LOWORD(SrcStr) = *v15;
      DestStr = 0;
      v18 = LCMapStringW(0x7Fu, 0x100u, (LPCWSTR)&SrcStr, 1, &DestStr, 1) ? DestStr : SrcStr;
      v14 = (int *)v109;
    }
    else if ( (unsigned __int16)(v18 - 65) <= 0x19u )
    {
      v18 += 32;
    }
    if ( v17 != v18 )
      break;
    ++v15;
  }
  std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(&v105, v13, v14);
  v20 = 0;
  v116 = 0;
  v21 = CWbemNamespace::DynAux_BuildClassHierarchy(this, *((unsigned __int16 **)v109 + 3), a3, (__int64)&v105, &v116);
  if ( v21 >= 0 )
  {
    ppv = 0;
    p_ppv = &ppv;
    if ( !*((_DWORD *)v109 + 19) )
    {
      if ( (int)CWbemNamespace::Exec_GetObjectByPath(
                  this,
                  *((const unsigned __int16 **)v109 + 3),
                  a3,
                  a4,
                  (struct IWbemClassObject **)&ppv,
                  0) >= 0 )
        goto LABEL_27;
      v74 = GetMemLogObject();
      CMemoryLog::Write(v74, -2147217392);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749904LL);
      }
      v66 = CBasicObjectSink::Return(a5, -2147217392, 0);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      ppv = 0;
LABEL_157:
      std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
      if ( v11 )
        QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
      v108 = 0;
      return v66;
    }
    if ( !(_DWORD)v110 )
    {
      v75 = GetMemLogObject();
      CMemoryLog::Write(v75, -2147217396);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749900LL);
      }
      v66 = CBasicObjectSink::Return(a5, -2147217396, 0);
      CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
      goto LABEL_157;
    }
    v76 = CoCreateInstance(&CLSID_WbemClassObject, 0, 1u, &IID_IWbemClassObject, &ppv);
    if ( v76 < 0 )
    {
      v77 = GetMemLogObject();
      CMemoryLog::Write(v77, v76);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
          (unsigned int)v76);
      }
      v66 = CBasicObjectSink::Return(a5, v76, 0);
      CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
      goto LABEL_157;
    }
    v78 = SysAllocString(L"__Generic");
    if ( !v78 )
    {
      v79 = GetMemLogObject();
      CMemoryLog::Write(v79, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
      }
      v66 = CBasicObjectSink::Return(a5, -2147217402, 0);
      CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
      goto LABEL_157;
    }
    *(_QWORD *)&v118.vt = 8;
    *(_OWORD *)&v118.decVal.Lo32 = (unsigned __int64)v78;
    VariantInit(&pvarg);
    _variant_t::Clear((_variant_t *)&pvarg);
    pvarg = v118;
    v118.vt = 0;
    v80 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, VARIANTARG *, int))(*(_QWORD *)ppv + 40LL))(
            ppv,
            L"__Class",
            0,
            &v118,
            8);
    if ( v80 < 0 )
    {
      v81 = GetMemLogObject();
      CMemoryLog::Write(v81, v80);
      v82 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v83 = 61;
        goto LABEL_220;
      }
      goto LABEL_221;
    }
    v80 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, _QWORD, int))(*(_QWORD *)ppv + 40LL))(
            ppv,
            L"Count",
            0,
            0,
            19);
    if ( v80 < 0 )
    {
      v84 = GetMemLogObject();
      CMemoryLog::Write(v84, v80);
      v82 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v83 = 62;
LABEL_220:
        WPP_SF_d(*((_QWORD *)v82 + 2), v83, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, (unsigned int)v80);
      }
LABEL_221:
      v66 = CBasicObjectSink::Return(a5, v80, 0);
      _variant_t::~_variant_t((_variant_t *)&pvarg);
LABEL_223:
      CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
      goto LABEL_157;
    }
    _variant_t::~_variant_t((_variant_t *)&pvarg);
LABEL_27:
    if ( (a3 & 0x100000) != 0 )
    {
      v115 = a3 & 0xFFEFFFFF;
      v20 = a5;
      goto LABEL_29;
    }
    v56 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0xF8u);
    v113 = v56;
    v57 = a5;
    if ( v56 )
      v20 = CProjectingSink::CProjectingSink(v56, a5, (struct CWbemClass *)ppv, v109, a3);
    if ( !v20 )
    {
      v85 = GetMemLogObject();
      CMemoryLog::Write(v85, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
      }
      v59 = -2147217402;
LABEL_98:
      v60 = CBasicObjectSink::Return(v57, v59, 0);
      if ( ppv )
        goto LABEL_99;
      goto LABEL_100;
    }
    if ( !*((_DWORD *)v20 + 48) )
    {
      CProjectingSink::`scalar deleting destructor'(v20, 1u);
      v58 = GetMemLogObject();
      CMemoryLog::Write(v58, -2147217385);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749911LL);
      }
      v59 = -2147217385;
      goto LABEL_98;
    }
LABEL_29:
    v22 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x48u);
    v23 = v22;
    v113 = v22;
    if ( v22 )
    {
      v24 = v109;
      CBasicObjectSink::CBasicObjectSink(v22);
      *(_QWORD *)v25 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
      *(_QWORD *)(v25 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *(_DWORD *)(v25 + 16) = 0;
      *(_QWORD *)v25 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
      *(_QWORD *)(v25 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *((_QWORD *)v23 + 3) = (*(__int64 (__fastcall **)(CProjectingSink *))(*(_QWORD *)v20 + 88LL))(v20);
      *((_QWORD *)v23 + 4) = (*(__int64 (__fastcall **)(CProjectingSink *))(*(_QWORD *)v20 + 96LL))(v20);
      *((_QWORD *)v23 + 5) = v20;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 3) + 8LL))(*((_QWORD *)v23 + 3));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 4) + 8LL))(*((_QWORD *)v23 + 4));
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v23 + 5) + 8LL))(*((_QWORD *)v23 + 5));
      *(_QWORD *)v23 = &CFilteringSink::`vftable'{for `IWbemObjectSinkEx'};
      *((_QWORD *)v23 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *(_QWORD *)v23 = &CQlFilteringSink::`vftable'{for `IWbemObjectSinkEx'};
      *((_QWORD *)v23 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
      *((_QWORD *)v23 + 6) = v24;
      *((_DWORD *)v23 + 14) = 1;
      *((_QWORD *)v23 + 8) = this;
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids);
      }
      QL_LEVEL_1_RPN_EXPRESSION::AddRef(*((QL_LEVEL_1_RPN_EXPRESSION **)v23 + 6));
    }
    else
    {
      v23 = 0;
    }
    if ( v23 )
    {
      if ( (_DWORD)v112 )
      {
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids);
        }
        *((_DWORD *)v23 + 14) = 1;
      }
      v26 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x70u);
      v27 = v26;
      v113 = v26;
      if ( v26 )
      {
        CBasicObjectSink::CBasicObjectSink(v26);
        *(_QWORD *)v28 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
        *(_QWORD *)(v28 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
        *(_DWORD *)(v28 + 16) = 0;
        *(_QWORD *)v28 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
        *(_QWORD *)(v28 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
        *((_QWORD *)v27 + 3) = (*(__int64 (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v23 + 88LL))(v23);
        *((_QWORD *)v27 + 4) = (*(__int64 (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v23 + 96LL))(v23);
        *((_QWORD *)v27 + 5) = v23;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 + 3) + 8LL))(*((_QWORD *)v27 + 3));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 + 4) + 8LL))(*((_QWORD *)v27 + 4));
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 + 5) + 8LL))(*((_QWORD *)v27 + 5));
        *(_QWORD *)v27 = &CCombiningSink::`vftable'{for `IWbemObjectSinkEx'};
        *((_QWORD *)v27 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
        *((_DWORD *)v27 + 12) = -2147217406;
        v29 = 0;
        *((_DWORD *)v27 + 13) = 0;
        *((_QWORD *)v27 + 7) = 0;
        *((_QWORD *)v27 + 8) = 0;
        CCritSec::CCritSec((CBasicObjectSink *)((char *)v27 + 72));
      }
      else
      {
        v29 = 0;
        v27 = 0;
      }
      if ( v27 )
      {
        v30 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x98u);
        v31 = v30;
        v113 = v30;
        if ( v30 )
        {
          CBasicObjectSink::CBasicObjectSink(v30);
          *(_QWORD *)v32 = &CObjectSink::`vftable'{for `IWbemObjectSinkEx'};
          *(_QWORD *)(v32 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          *(_DWORD *)(v32 + 16) = 0;
          *(_QWORD *)v32 = &CForwardingSink::`vftable'{for `IWbemObjectSinkEx'};
          *(_QWORD *)(v32 + 8) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          *((_QWORD *)v31 + 3) = (*(__int64 (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v27 + 88LL))(v27);
          *((_QWORD *)v31 + 4) = (*(__int64 (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v27 + 96LL))(v27);
          *((_QWORD *)v31 + 5) = v27;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 3) + 8LL))(*((_QWORD *)v31 + 3));
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 4) + 8LL))(*((_QWORD *)v31 + 4));
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v31 + 5) + 8LL))(*((_QWORD *)v31 + 5));
          *(_QWORD *)v31 = &CDynPropsSink::`vftable'{for `IWbemObjectSinkEx'};
          *((_QWORD *)v31 + 1) = &CInternalMerger::COwnSink::`vftable'{for `CDestination'};
          v114 = (struct IWbemClassObject *)((char *)v31 + 48);
          CFlexArray::CFlexArray((CBasicObjectSink *)((char *)v31 + 48), 8, 100);
          v33 = (struct IWbemServices *)this;
          *((_QWORD *)v31 + 18) = this;
          _InterlockedIncrement((volatile signed __int32 *)this + 6);
        }
        else
        {
          v31 = 0;
          v33 = (struct IWbemServices *)this;
        }
        if ( v31 )
        {
          (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 8LL))(v31);
          v112 = v31;
          if ( (_DWORD)v110 )
          {
            v37 = v126;
            goto LABEL_55;
          }
          v110 = 0;
          v34 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x18u);
          v113 = v34;
          if ( v34 )
            v35 = CStandardMetaData::CStandardMetaData(v34, v33);
          else
            v35 = 0;
          if ( !v35 )
          {
            v91 = GetMemLogObject();
            CMemoryLog::Write(v91, -2147217402);
            v92 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v93 = 68;
              goto LABEL_258;
            }
LABEL_259:
            CBasicObjectSink::Return(v31, -2147217402, 0);
            CReleaseMe::release((CReleaseMe *)&v112);
            CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
            goto LABEL_151;
          }
          v36 = (CBasicObjectSink *)CWin32DefaultArena::WbemMemAlloc(0x10u);
          v113 = v36;
          v37 = v126;
          if ( v36 )
            v29 = CContextMetaData::CContextMetaData(v36, v35, v126);
          if ( v29 )
          {
            v38 = CQueryAnalyser::SimplifyQueryForChild(
                    v109,
                    *((const unsigned __int16 **)v109 + 3),
                    (struct IWbemClassObject *)ppv,
                    v29,
                    &v110);
            CContextMetaData::~CContextMetaData(v29);
            CWin32DefaultArena::WbemMemFree(v29);
            if ( v38 < 0 )
            {
              v96 = GetMemLogObject();
              CMemoryLog::Write(v96, -2147217385);
              if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  70,
                  WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                  2147749911LL);
              }
              v95 = -2147217385;
            }
            else
            {
              v39 = v110;
              if ( v110 )
              {
                v40 = v109;
                v41 = (char *)*((_QWORD *)v109 + 2);
                if ( v41 )
                {
                  v42 = v41 - 8;
                  `eh vector destructor iterator'(v41, 0x80u, *((_QWORD *)v41 - 1), QL_LEVEL_1_TOKEN::~QL_LEVEL_1_TOKEN);
                  CWin32DefaultArena::WbemMemFree(v42);
                  v40 = v109;
                  v39 = v110;
                }
                *((_QWORD *)v40 + 2) = *((_QWORD *)v39 + 2);
                *((_DWORD *)v109 + 2) = *((_DWORD *)v110 + 2);
                *((_QWORD *)v110 + 2) = 0;
                v43 = v110;
                if ( v110 )
                {
                  QL_LEVEL_1_RPN_EXPRESSION::~QL_LEVEL_1_RPN_EXPRESSION(v110);
                  CWin32DefaultArena::WbemMemFree(v43);
                }
                v33 = (struct IWbemServices *)this;
LABEL_55:
                v44 = CQueryEngine::ValidateQuery(v109, (struct CWbemClass *)ppv);
                if ( (v44 & 0x80000000) == 0 )
                {
                  if ( *((_DWORD *)v109 + 19) )
                    Text = Macro_CloneLPWSTR(a2);
                  else
                    Text = QL_LEVEL_1_RPN_EXPRESSION::GetText(v109);
                  v46 = Text;
                  if ( Text )
                  {
                    *(_OWORD *)&v118.vt = (unsigned __int64)Text;
                    if ( (v115 & 0x200) != 0 )
                    {
                      CQueryEngine::DirectRead(
                        (struct CWbemNamespace *)v33,
                        v105,
                        Text,
                        v109,
                        v37,
                        (struct IWbemObjectSink *)v31,
                        v115 & 0xFFFFFEFF);
LABEL_78:
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          77,
                          WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                          v44);
                      }
                      CWin32DefaultArena::WbemMemFree(v46);
                      (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
                      v112 = 0;
                      if ( ppv )
                        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                      ppv = 0;
                      std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
                      if ( v11 )
                        QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
                      v108 = 0;
                      return v44;
                    }
                    v47 = (char *)CWin32DefaultArena::WbemMemAlloc(0x158u);
                    v48 = v47;
                    v113 = (CBasicObjectSink *)v47;
                    if ( v47 )
                    {
                      *(_QWORD *)v47 = &CWmiMerger::`vftable'{for `_IWmiArbitratee'};
                      *((_QWORD *)v47 + 1) = &CWmiMerger::`vftable'{for `_IWmiArbitratedQuery'};
                      *((_DWORD *)v47 + 4) = 0;
                      WString::WString((WString *)(v47 + 24));
                      *((_QWORD *)v48 + 4) = 0;
                      *((_QWORD *)v48 + 5) = 0;
                      *((_QWORD *)v48 + 6) = 0;
                      *((_QWORD *)v48 + 7) = v33;
                      *((_QWORD *)v48 + 8) = 0;
                      *((_DWORD *)v48 + 18) = -1;
                      v114 = (struct IWbemClassObject *)(v48 + 80);
                      CFlexArray::CFlexArray((CFlexArray *)(v48 + 80), 8, 100);
                      v117 = (CBasicObjectSink *)(v48 + 176);
                      CFlexArray::CFlexArray((CFlexArray *)(v48 + 176), 8, 100);
                      *((_QWORD *)v48 + 34) = 0;
                      v48[280] = 1;
                      CCritSec::CCritSec((CCritSec *)(v48 + 288));
                      *((_DWORD *)v48 + 82) = 0;
                      *((_QWORD *)v48 + 42) = 0;
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                      {
                        WPP_SF_q(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          10,
                          WPP_fe01880289a43dbd8863a298ad6cadc3_Traceguids,
                          v33);
                      }
                      v49 = *((_QWORD *)v48 + 7);
                      if ( v49 )
                        _InterlockedIncrement((volatile signed __int32 *)(v49 + 24));
                      _InterlockedIncrement(&dword_1801ADE74);
                    }
                    else
                    {
                      v48 = 0;
                    }
                    if ( !v48 )
                    {
                      v99 = GetMemLogObject();
                      CMemoryLog::Write(v99, -2147217402);
                      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          73,
                          WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                          2147749894LL);
                      }
                      v66 = CBasicObjectSink::Return(v31, -2147217402, 0);
                      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(&v118);
                      CReleaseMe::release((CReleaseMe *)&v112);
                      goto LABEL_223;
                    }
                    _InterlockedIncrement((volatile signed __int32 *)v48 + 4);
                    v110 = (struct QL_LEVEL_1_RPN_EXPRESSION *)v48;
                    if ( CWmiArbitrator::m_pArb )
                    {
                      _InterlockedIncrement((volatile signed __int32 *)CWmiArbitrator::m_pArb + 2);
                      v50 = CWmiArbitrator::m_pArb;
                      if ( CWmiArbitrator::m_pArb )
                      {
                        v114 = (struct IWbemClassObject *)CWmiArbitrator::m_pArb;
                        v51 = 0;
                        Value = TlsGetValue(g_QueueTlsIndex);
                        if ( Value )
                        {
                          v53 = Value[1];
                          if ( v53 )
                            v51 = *(struct _IWmiCoreHandle **)(v53 + 32);
                        }
                        v113 = 0;
                        v54 = CWmiMerger::Initialize(
                                (CWmiMerger *)v48,
                                v50,
                                v51,
                                *((const unsigned __int16 **)v109 + 3),
                                (struct IWbemObjectSink *)v31,
                                &v113);
                        SrcStr = v54;
                        v55 = v113;
                        v117 = v113;
                        if ( v54 < 0 )
                        {
                          if ( v54 == -2147217358 )
                          {
                            v64 = SrcStr;
                          }
                          else
                          {
                            v101 = GetMemLogObject();
                            v64 = SrcStr;
                            CMemoryLog::Write(v101, SrcStr);
                            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                75,
                                WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                                v64);
                            }
                          }
                          v65 = CBasicObjectSink::Return(v31, v64, 0);
                          if ( v55 )
                            (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v55 + 16LL))(v55);
                          v117 = 0;
                          (*(void (__fastcall **)(struct _IWmiArbitrator *))(*(_QWORD *)v50 + 16LL))(v50);
                          v114 = 0;
                          (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 16LL))(v48);
                          v110 = 0;
                          CWin32DefaultArena::WbemMemFree(v46);
                          (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
                          v112 = 0;
                          if ( ppv )
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                          ppv = 0;
                          std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
                          if ( v11 )
                            QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
                        }
                        else
                        {
                          if ( (int)CQueryEngine::EvaluateSubQuery(
                                      this,
                                      v105,
                                      v46,
                                      v109,
                                      v126,
                                      0,
                                      (struct CWmiMerger *)v48,
                                      v113,
                                      v115 & 0xFFFFFEFF,
                                      0) < 0
                            || (SrcStr = CWmiMerger::ScheduleMergerParentRequest((CWmiMerger *)v48, v126), SrcStr >= 0) )
                          {
                            if ( v55 )
                              (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v55 + 16LL))(v55);
                            v117 = 0;
                            (*(void (__fastcall **)(struct _IWmiArbitrator *))(*(_QWORD *)v50 + 16LL))(v50);
                            v114 = 0;
                            (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 16LL))(v48);
                            v110 = 0;
                            goto LABEL_78;
                          }
                          v102 = GetMemLogObject();
                          v103 = SrcStr;
                          CMemoryLog::Write(v102, SrcStr);
                          if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            WPP_SF_d(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              76,
                              WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                              v103);
                          }
                          v65 = CBasicObjectSink::Return(v55, v103, 0);
                          if ( v55 )
                            (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v55 + 16LL))(v55);
                          v117 = 0;
                          (*(void (__fastcall **)(struct _IWmiArbitrator *))(*(_QWORD *)v50 + 16LL))(v50);
                          v114 = 0;
                          (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 16LL))(v48);
                          v110 = 0;
                          CWin32DefaultArena::WbemMemFree(v46);
                          (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
                          v112 = 0;
                          if ( ppv )
                            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                          ppv = 0;
                          std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
                          if ( v11 )
                          {
                            QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
                            v108 = 0;
                            return v65;
                          }
                        }
                        v108 = 0;
                        return v65;
                      }
                    }
                    v100 = GetMemLogObject();
                    CMemoryLog::Write(v100, -2147217398);
                    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        74,
                        WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                        2147749898LL);
                    }
                    v60 = CBasicObjectSink::Return(v31, -2147217398, 0);
                    (*(void (__fastcall **)(char *))(*(_QWORD *)v48 + 16LL))(v48);
                    v110 = 0;
                    CWin32DefaultArena::WbemMemFree(v46);
                    (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
                    v112 = 0;
                    if ( ppv )
LABEL_99:
                      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_100:
                    ppv = 0;
LABEL_101:
                    std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
                    goto LABEL_102;
                  }
                  v98 = GetMemLogObject();
                  CMemoryLog::Write(v98, -2147217402);
                  v92 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v93 = 72;
LABEL_258:
                    WPP_SF_d(*((_QWORD *)v92 + 2), v93, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
                  }
                  goto LABEL_259;
                }
                v97 = GetMemLogObject();
                CMemoryLog::Write(v97, v44);
                if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    71,
                    WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                    v44);
                }
                CBasicObjectSink::Return(v31, v44, 0);
                (*(void (__fastcall **)(CBasicObjectSink *))(*(_QWORD *)v31 + 16LL))(v31);
                v112 = 0;
                if ( ppv )
                  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
                ppv = 0;
LABEL_151:
                std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
                if ( v11 )
                  QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
LABEL_153:
                v108 = 0;
                return 0;
              }
              v95 = 0;
            }
          }
          else
          {
            v94 = GetMemLogObject();
            CMemoryLog::Write(v94, -2147217402);
            if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                69,
                WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids,
                2147749894LL);
            }
            CStandardMetaData::`scalar deleting destructor'(v35, 1u);
            v95 = -2147217402;
          }
          CBasicObjectSink::Return(v31, v95, 0);
          CReleaseMe::release((CReleaseMe *)&v112);
          CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
          std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
          if ( v11 )
            QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
          goto LABEL_153;
        }
        v90 = GetMemLogObject();
        CMemoryLog::Write(v90, -2147217402);
        v88 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v89 = 67;
LABEL_246:
          WPP_SF_d(*((_QWORD *)v88 + 2), v89, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
        }
      }
      else
      {
        v87 = GetMemLogObject();
        CMemoryLog::Write(v87, -2147217402);
        v88 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v89 = 66;
          goto LABEL_246;
        }
      }
      v60 = CBasicObjectSink::Return(a5, -2147217402, 0);
      CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
      goto LABEL_101;
    }
    v86 = GetMemLogObject();
    CMemoryLog::Write(v86, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749894LL);
    }
    v19 = CBasicObjectSink::Return(a5, -2147217402, 0);
    CReleaseMeRef<IWbemClassObject *>::release(&p_ppv);
    std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
LABEL_163:
    if ( v11 )
      QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
    goto LABEL_165;
  }
  v61 = v116;
  v114 = v116;
  if ( v21 != -2147217406 && v21 != -2147217392 )
  {
    v73 = GetMemLogObject();
    CMemoryLog::Write(v73, -2147217385);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749911LL);
    }
    v66 = CBasicObjectSink::Return(a5, -2147217385, v116);
    CReleaseMe::release((CReleaseMe *)&v114);
    goto LABEL_157;
  }
  v62 = GetMemLogObject();
  CMemoryLog::Write(v62, -2147217392);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_6bfb4fd727a43c8e297a0be172c39878_Traceguids, 2147749904LL);
  }
  v63 = CBasicObjectSink::Return(a5, -2147217392, v116);
  if ( v61 )
    ((void (__fastcall *)(struct IWbemClassObject *))v61->lpVtbl->Release)(v61);
  v114 = 0;
  std::unique_ptr<CDynasty>::~unique_ptr<CDynasty>(&v105);
  if ( v11 )
    QL_LEVEL_1_RPN_EXPRESSION::Release(v11);
  v108 = 0;
  return v63;
}

```

## disassembly

```asm
0x18003d3b0  mov     [rsp+arg_18], r9
0x18003d3b5  mov     [rsp+Src], rdx
0x18003d3ba  mov     [rsp+arg_0], rcx
0x18003d3bf  push    rbx
0x18003d3c0  push    rsi
0x18003d3c1  push    rdi
0x18003d3c2  push    r12
0x18003d3c4  push    r13
0x18003d3c6  push    r14
0x18003d3c8  push    r15
0x18003d3ca  sub     rsp, 1D0h
0x18003d3d1  mov     r12, r9
0x18003d3d4  mov     r15d, r8d
0x18003d3d7  mov     [rsp+208h+var_168], r8d
0x18003d3df  mov     rdi, rdx
0x18003d3e2  mov     r13, rcx
0x18003d3e5  lea     r14, WPP_GLOBAL_Control
0x18003d3ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d3f3  cmp     rcx, r14
0x18003d3f6  jz      short loc_18003D402
0x18003d3f8  test    byte ptr [rcx+1Ch], 1
0x18003d3fc  jnz     loc_18003E104
0x18003d402  mov     eax, r15d
0x18003d405  and     eax, 1
0x18003d408  mov     dword ptr [rsp+208h+var_180], eax
0x18003d40f  mov     rbx, [rsp+208h+arg_20]
0x18003d417  jnz     short loc_18003D437
0x18003d419  mov     [rsp+208h+lpDestStr], rbx; struct CBasicObjectSink *
0x18003d41e  mov     r9, r12; struct IWbemContext *
0x18003d421  mov     r8d, r15d; int
0x18003d424  mov     rdx, rdi; unsigned __int16 *
0x18003d427  mov     rcx, r13; this
0x18003d42a  call    ?ExecComplexQuery@CQueryEngine@@CAJPEAVCWbemNamespace@@PEAGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CQueryEngine::ExecComplexQuery(CWbemNamespace *,ushort *,long,IWbemContext *,CBasicObjectSink *)
0x18003d42f  test    eax, eax
0x18003d431  jns     loc_18003DE14
0x18003d437  lea     rax, ??_7CTextLexSource@@6B@; const CTextLexSource::`vftable'
0x18003d43e  mov     [rsp+208h+var_118], rax
0x18003d446  mov     [rsp+208h+var_108], rdi
0x18003d44e  mov     [rsp+208h+var_110], rdi
0x18003d456  xor     esi, esi
0x18003d458  mov     [rsp+208h+var_198], rsi
0x18003d45d  lea     rdx, [rsp+208h+var_118]
0x18003d465  lea     rcx, [rsp+208h+var_F8]
0x18003d46d  call    cs:__imp_??0QL1_Parser@@QEAA@PEAVCGenLexSource@@@Z; QL1_Parser::QL1_Parser(CGenLexSource *)
0x18003d473  nop
0x18003d474  lea     rdx, [rsp+208h+var_198]
0x18003d479  lea     rcx, [rsp+208h+var_F8]
0x18003d481  call    cs:__imp_?Parse@QL1_Parser@@QEAAHPEAPEAUQL_LEVEL_1_RPN_EXPRESSION@@@Z; QL1_Parser::Parse(QL_LEVEL_1_RPN_EXPRESSION * *)
0x18003d487  mov     [rsp+208h+var_120], eax
0x18003d48e  test    eax, eax
0x18003d490  jnz     loc_18003E4B9
0x18003d496  lea     rcx, [rsp+208h+var_F8]
0x18003d49e  call    cs:__imp_??1QL1_Parser@@UEAA@XZ; QL1_Parser::~QL1_Parser(void)
0x18003d4a4  nop
0x18003d4a5  mov     rcx, [rsp+208h+var_198]
0x18003d4aa  call    cs:__imp_?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ; QL_LEVEL_1_RPN_EXPRESSION::AddRef(void)
0x18003d4b0  mov     rdi, [rsp+208h+var_198]
0x18003d4b5  mov     [rsp+208h+var_1A0], rdi
0x18003d4ba  mov     rcx, [r13+28h]
0x18003d4be  mov     rax, [rcx]
0x18003d4c1  xor     edx, edx
0x18003d4c3  mov     rax, [rax+58h]
0x18003d4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4cc  mov     r8, [rsp+208h+var_198]; struct QL_LEVEL_1_RPN_EXPRESSION *
0x18003d4d1  test    eax, eax
0x18003d4d3  jz      loc_18003E527
0x18003d4d9  cmp     dword ptr [r8+48h], 0
0x18003d4de  jnz     loc_18003EFDC
0x18003d4e4  mov     dword ptr [rsp+208h+var_190], esi
0x18003d4e8  cmp     qword ptr [r8+18h], 0
0x18003d4ed  jz      loc_18003EFDC
0x18003d4f3  lea     rsi, aMetaClass; "meta_class"
0x18003d4fa  mov     r14, [r8+18h]
0x18003d4fe  xchg    ax, ax
0x18003d500  movzx   ebx, word ptr [r14]
0x18003d504  test    bx, bx
0x18003d507  jz      short loc_18003D54D
0x18003d509  cmp     bx, 7Fh
0x18003d50d  ja      loc_18003DF59
0x18003d513  lea     eax, [rbx-41h]
0x18003d516  cmp     ax, 19h
0x18003d51a  jbe     short loc_18003D541
0x18003d51c  movzx   ecx, word ptr [rsi]
0x18003d51f  cmp     cx, 7Fh
0x18003d523  ja      loc_18003DFB2
0x18003d529  lea     eax, [rcx-41h]
0x18003d52c  cmp     ax, 19h
0x18003d530  jbe     short loc_18003D547
0x18003d532  cmp     bx, cx
0x18003d535  jnz     short loc_18003D5AD
0x18003d537  add     r14, 2
0x18003d53b  add     rsi, 2
0x18003d53f  jmp     short loc_18003D500
0x18003d541  add     bx, 20h ; ' '
0x18003d545  jmp     short loc_18003D51C
0x18003d547  add     cx, 20h ; ' '
0x18003d54b  jmp     short loc_18003D532
0x18003d54d  cmp     word ptr [rsi], 0
0x18003d551  jnz     short loc_18003D51C
0x18003d553  cmp     dword ptr [r8+30h], 0
0x18003d558  jg      loc_18003E59C
0x18003d55e  cmp     dword ptr [r8+38h], 0
0x18003d563  jz      loc_18003E59C
0x18003d569  mov     rsi, [rsp+208h+arg_20]
0x18003d571  mov     [rsp+208h+lpDestStr], rsi; struct CBasicObjectSink *
0x18003d576  mov     r9, r12; struct IWbemContext *
0x18003d579  mov     rdx, [rsp+208h+Src]; unsigned __int16 *
0x18003d581  mov     rcx, r13; this
0x18003d584  call    ?ExecSchemaQuery@CQueryEngine@@CAJPEAVCWbemNamespace@@PEAGPEAUQL_LEVEL_1_RPN_EXPRESSION@@PEAUIWbemContext@@PEAVCBasicObjectSink@@@Z; CQueryEngine::ExecSchemaQuery(CWbemNamespace *,ushort *,QL_LEVEL_1_RPN_EXPRESSION *,IWbemContext *,CBasicObjectSink *)
0x18003d589  mov     ebx, eax
0x18003d58b  test    rdi, rdi
0x18003d58e  jz      loc_18003E4A9
0x18003d594  mov     rcx, rdi
0x18003d597  call    cs:__imp_?Release@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ; QL_LEVEL_1_RPN_EXPRESSION::Release(void)
0x18003d59d  mov     [rsp+208h+var_1A0], 0
0x18003d5a6  mov     eax, ebx
0x18003d5a8  jmp     loc_18003DE14
0x18003d5ad  lea     rcx, [rsp+208h+var_1B8]
0x18003d5b2  call    ??0?$unique_ptr@$$BY0A@PEAUIUnknown@@U?$default_delete@$$BY0A@PEAUIUnknown@@@std@@@std@@QEAA@XZ; std::unique_ptr<IUnknown * [0]>::unique_ptr<IUnknown * [0]>(void)
0x18003d5b7  nop
0x18003d5b8  xor     r14d, r14d
0x18003d5bb  mov     [rsp+208h+var_160], r14
0x18003d5c3  lea     rax, [rsp+208h+var_160]
0x18003d5cb  mov     qword ptr [rsp+208h+cchDest], rax; struct IWbemClassObject **
0x18003d5d0  lea     rax, [rsp+208h+var_1B8]
0x18003d5d5  mov     [rsp+208h+lpDestStr], rax; __int64
0x18003d5da  mov     r9, r12
0x18003d5dd  mov     r8d, r15d; int
0x18003d5e0  mov     rdx, [rsp+208h+var_198]
0x18003d5e5  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18003d5e9  mov     rcx, r13; this
0x18003d5ec  call    ?DynAux_BuildClassHierarchy@CWbemNamespace@@QEAAJPEAGJPEAUIWbemContext@@AEAV?$unique_ptr@VCDynasty@@U?$default_delete@VCDynasty@@@std@@@std@@PEAPEAUIWbemClassObject@@@Z; CWbemNamespace::DynAux_BuildClassHierarchy(ushort *,long,IWbemContext *,std::unique_ptr<CDynasty> &,IWbemClassObject * *)
0x18003d5f1  test    eax, eax
0x18003d5f3  js      loc_18003E037
0x18003d5f9  mov     [rsp+208h+ppv], r14
0x18003d5fe  lea     rax, [rsp+208h+ppv]
0x18003d603  mov     [rsp+208h+var_188], rax
0x18003d60b  mov     rdx, [rsp+208h+var_198]
0x18003d610  cmp     [rdx+4Ch], r14d
0x18003d614  jnz     loc_18003E716
0x18003d61a  mov     qword ptr [rsp+208h+cchDest], r14; struct IWbemClassObject **
0x18003d61f  lea     rax, [rsp+208h+ppv]
0x18003d624  mov     [rsp+208h+lpDestStr], rax; struct IWbemClassObject **
0x18003d629  mov     r9, r12; struct IWbemContext *
0x18003d62c  mov     r8d, r15d; int
0x18003d62f  mov     rdx, [rdx+18h]; unsigned __int16 *
0x18003d633  mov     rcx, r13; this
0x18003d636  call    ?Exec_GetObjectByPath@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAPEAUIWbemClassObject@@2@Z; CWbemNamespace::Exec_GetObjectByPath(ushort const *,long,IWbemContext *,IWbemClassObject * *,IWbemClassObject * *)
0x18003d63b  test    eax, eax
0x18003d63d  js      loc_18003E6B7
0x18003d643  mov     r12d, 8
0x18003d649  bt      r15d, 14h
0x18003d64e  jnb     loc_18003DE49
0x18003d654  btr     r15d, 14h
0x18003d659  mov     [rsp+208h+var_168], r15d
0x18003d661  mov     r14, [rsp+208h+arg_20]
0x18003d669  mov     ecx, 48h ; 'H'
0x18003d66e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003d674  mov     rsi, rax
0x18003d677  mov     [rsp+208h+var_178], rax
0x18003d67f  test    rax, rax
0x18003d682  jz      loc_18003EB00
0x18003d688  mov     rbx, [rsp+208h+var_198]
0x18003d68d  mov     rcx, rax; this
0x18003d690  call    ??0CBasicObjectSink@@QEAA@XZ; CBasicObjectSink::CBasicObjectSink(void)
0x18003d695  nop
0x18003d696  lea     r13, ??_7CObjectSink@@6BIWbemObjectSinkEx@@@; const CObjectSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d69d  mov     [rcx], r13
0x18003d6a0  lea     r15, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d6a7  mov     [rcx+8], r15
0x18003d6ab  mov     dword ptr [rcx+10h], 0
0x18003d6b2  lea     rax, ??_7CForwardingSink@@6BIWbemObjectSinkEx@@@; const CForwardingSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d6b9  mov     [rcx], rax
0x18003d6bc  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d6c3  mov     [rcx+8], rax
0x18003d6c7  mov     rax, [r14]
0x18003d6ca  mov     rcx, r14
0x18003d6cd  mov     rax, [rax+58h]
0x18003d6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6d6  mov     [rsi+18h], rax
0x18003d6da  mov     rax, [r14]
0x18003d6dd  mov     rcx, r14
0x18003d6e0  mov     rax, [rax+60h]
0x18003d6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6e9  mov     [rsi+20h], rax
0x18003d6ed  mov     [rsi+28h], r14
0x18003d6f1  mov     rcx, [rsi+18h]
0x18003d6f5  mov     rax, [rcx]
0x18003d6f8  mov     rax, [rax+8]
0x18003d6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d701  mov     rcx, [rsi+20h]
0x18003d705  mov     rax, [rcx]
0x18003d708  mov     rax, [rax+8]
0x18003d70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d711  mov     rcx, [rsi+28h]
0x18003d715  mov     rax, [rcx]
0x18003d718  mov     rax, [rax+8]
0x18003d71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d721  nop
0x18003d722  lea     rax, ??_7CFilteringSink@@6BIWbemObjectSinkEx@@@; const CFilteringSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d729  mov     [rsi], rax
0x18003d72c  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d733  mov     [rsi+8], rax
0x18003d737  lea     rax, ??_7CQlFilteringSink@@6BIWbemObjectSinkEx@@@; const CQlFilteringSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d73e  mov     [rsi], rax
0x18003d741  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d748  mov     [rsi+8], rax
0x18003d74c  mov     [rsi+30h], rbx
0x18003d750  mov     dword ptr [rsi+38h], 1
0x18003d757  mov     rcx, [rsp+208h+arg_0]
0x18003d75f  mov     [rsi+40h], rcx
0x18003d763  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d76a  lea     rbx, WPP_GLOBAL_Control
0x18003d771  cmp     rcx, rbx
0x18003d774  jz      short loc_18003D780
0x18003d776  test    byte ptr [rcx+1Ch], 1
0x18003d77a  jnz     loc_18003E0E0
0x18003d780  mov     rcx, [rsi+30h]
0x18003d784  call    cs:__imp_?AddRef@QL_LEVEL_1_RPN_EXPRESSION@@QEAAXXZ; QL_LEVEL_1_RPN_EXPRESSION::AddRef(void)
0x18003d78a  nop
0x18003d78b  lea     r14, ??_7CForwardingSink@@6BIWbemObjectSinkEx@@@; const CForwardingSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d792  test    rsi, rsi
0x18003d795  jz      loc_18003EB1C
0x18003d79b  cmp     dword ptr [rsp+208h+var_180], 0
0x18003d7a3  jnz     loc_18003DE27
0x18003d7a9  mov     ecx, 70h ; 'p'
0x18003d7ae  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003d7b4  mov     rbx, rax
0x18003d7b7  mov     [rsp+208h+var_178], rax
0x18003d7bf  test    rax, rax
0x18003d7c2  jz      loc_18003EB97
0x18003d7c8  mov     rcx, rax; this
0x18003d7cb  call    ??0CBasicObjectSink@@QEAA@XZ; CBasicObjectSink::CBasicObjectSink(void)
0x18003d7d0  nop
0x18003d7d1  mov     [rcx], r13
0x18003d7d4  mov     [rcx+8], r15
0x18003d7d8  mov     dword ptr [rcx+10h], 0
0x18003d7df  mov     [rcx], r14
0x18003d7e2  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d7e9  mov     [rcx+8], rax
0x18003d7ed  mov     rax, [rsi]
0x18003d7f0  mov     rcx, rsi
0x18003d7f3  mov     rax, [rax+58h]
0x18003d7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7fc  mov     [rbx+18h], rax
0x18003d800  mov     rax, [rsi]
0x18003d803  mov     rcx, rsi
0x18003d806  mov     rax, [rax+60h]
0x18003d80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d80f  mov     [rbx+20h], rax
0x18003d813  mov     [rbx+28h], rsi
0x18003d817  mov     rcx, [rbx+18h]
0x18003d81b  mov     rax, [rcx]
0x18003d81e  mov     rax, [rax+8]
0x18003d822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d827  mov     rcx, [rbx+20h]
0x18003d82b  mov     rax, [rcx]
0x18003d82e  mov     rax, [rax+8]
0x18003d832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d837  mov     rcx, [rbx+28h]
0x18003d83b  mov     rax, [rcx]
0x18003d83e  mov     rax, [rax+8]
0x18003d842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d847  nop
0x18003d848  lea     rax, ??_7CCombiningSink@@6BIWbemObjectSinkEx@@@; const CCombiningSink::`vftable'{for `IWbemObjectSinkEx'}
0x18003d84f  mov     [rbx], rax
0x18003d852  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d859  mov     [rbx+8], rax
0x18003d85d  mov     dword ptr [rbx+30h], 80041002h
0x18003d864  xor     esi, esi
0x18003d866  mov     [rbx+34h], esi
0x18003d869  mov     [rbx+38h], rsi
0x18003d86d  mov     [rbx+40h], rsi
0x18003d871  lea     rcx, [rbx+48h]
0x18003d875  call    cs:__imp_??0CCritSec@@QEAA@XZ; CCritSec::CCritSec(void)
0x18003d87b  nop
0x18003d87c  test    rbx, rbx
0x18003d87f  jz      loc_18003EBA0
0x18003d885  mov     ecx, 98h
0x18003d88a  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18003d890  mov     r15, rax
0x18003d893  mov     [rsp+208h+var_178], rax
0x18003d89b  test    rax, rax
0x18003d89e  jz      loc_18003EC1E
0x18003d8a4  mov     rcx, rax; this
0x18003d8a7  call    ??0CBasicObjectSink@@QEAA@XZ; CBasicObjectSink::CBasicObjectSink(void)
0x18003d8ac  nop
0x18003d8ad  mov     [rcx], r13
0x18003d8b0  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d8b7  mov     [rcx+8], rax
0x18003d8bb  mov     [rcx+10h], esi
0x18003d8be  mov     [rcx], r14
0x18003d8c1  lea     rax, ??_7COwnSink@CInternalMerger@@6BCDestination@@@; const CInternalMerger::COwnSink::`vftable'{for `CDestination'}
0x18003d8c8  mov     [rcx+8], rax
0x18003d8cc  mov     rax, [rbx]
0x18003d8cf  mov     rcx, rbx
0x18003d8d2  mov     rax, [rax+58h]
0x18003d8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8db  mov     [r15+18h], rax
0x18003d8df  mov     rax, [rbx]
  ... truncated ...
```

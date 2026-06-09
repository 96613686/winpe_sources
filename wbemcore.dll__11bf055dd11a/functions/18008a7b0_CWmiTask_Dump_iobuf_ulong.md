# CWmiTask::Dump(_iobuf *,ulong)

- ea: `0x18008a7b0`
- end: `0x18008ac88`
- name: `?Dump@CWmiTask@@QEAAJPEAU_iobuf@@K@Z`
- size: `1240`
- prototype: `__int64 __fastcall(CWmiTask *__hidden this, struct _iobuf *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003c80`

## callees

- `0x18000e950`
- `0x18003cfe0`
- `0x180044994`
- `0x18005edf4`
- `0x18008a7b0`
- `0x18008ed48`
- `0x18009c198`
- `0x1800c0e1c`
- `0x1800da010`

## import_xrefs

- `msvcrt!fprintf` at `0x18008a7d9`
- `msvcrt!fprintf` at `0x18008a7ed`
- `msvcrt!fprintf` at `0x18008a801`
- `msvcrt!fprintf` at `0x18008a815`
- `msvcrt!fprintf` at `0x18008a878`
- `msvcrt!fprintf` at `0x18008a896`
- `msvcrt!fprintf` at `0x18008a8ad`
- `msvcrt!fprintf` at `0x18008a8e5`
- `msvcrt!fprintf` at `0x18008a92e`
- `msvcrt!fprintf` at `0x18008aa44`
- `msvcrt!fprintf` at `0x18008aa5d`
- `msvcrt!fprintf` at `0x18008aa76`
- `msvcrt!fprintf` at `0x18008aa8f`
- `msvcrt!fprintf` at `0x18008aaa8`
- `msvcrt!fprintf` at `0x18008aac1`
- `msvcrt!fprintf` at `0x18008aad1`
- `msvcrt!fprintf` at `0x18008ab06`
- `msvcrt!fprintf` at `0x18008ab25`
- `msvcrt!fprintf` at `0x18008ab3c`
- `msvcrt!fprintf` at `0x18008ab53`
- `msvcrt!fprintf` at `0x18008aba8`
- `msvcrt!fprintf` at `0x18008ac0a`
- `msvcrt!fprintf` at `0x18008ac26`
- `msvcrt!fprintf` at `0x18008ac57`
- `msvcrt!fprintf` at `0x18008a7d9`
- `msvcrt!fprintf` at `0x18008a7ed`
- `msvcrt!fprintf` at `0x18008a801`
- `msvcrt!fprintf` at `0x18008a815`
- `msvcrt!fprintf` at `0x18008a878`
- `msvcrt!fprintf` at `0x18008a896`
- `msvcrt!fprintf` at `0x18008a8ad`
- `msvcrt!fprintf` at `0x18008a8e5`
- `msvcrt!fprintf` at `0x18008a92e`
- `msvcrt!fprintf` at `0x18008aa44`
- `msvcrt!fprintf` at `0x18008aa5d`
- `msvcrt!fprintf` at `0x18008aa76`
- `msvcrt!fprintf` at `0x18008aa8f`
- `msvcrt!fprintf` at `0x18008aaa8`
- `msvcrt!fprintf` at `0x18008aac1`
- `msvcrt!fprintf` at `0x18008aad1`
- `msvcrt!fprintf` at `0x18008ab06`
- `msvcrt!fprintf` at `0x18008ab25`
- `msvcrt!fprintf` at `0x18008ab3c`
- `msvcrt!fprintf` at `0x18008ab53`
- `msvcrt!fprintf` at `0x18008aba8`
- `msvcrt!fprintf` at `0x18008ac0a`
- `msvcrt!fprintf` at `0x18008ac26`
- `msvcrt!fprintf` at `0x18008ac57`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x18008a826`
- `wbemcomn!??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z` at `0x18008a826`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x18008ac6c`
- `wbemcomn!??1CCheckedInCritSec@@QEAA@XZ` at `0x18008ac6c`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x18008a8f6`
- `wbemcomn!?Leave@CCheckedInCritSec@@QEAAXXZ` at `0x18008a8f6`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008a8c3`
- `wbemcomn!??ACFlexArray@@QEAAAEAPEAXH@Z` at `0x18008a8c3`
- `OLEAUT32!__imp_VariantInit` at `0x18008a83b`
- `OLEAUT32!__imp_VariantInit` at `0x18008a83b`

## string_xrefs

- `0x18008a7cf`: `---Task = 0x%p ---------------------------\n`
- `0x18008a7f7`: `    TaskStatus       = %u\n`
- `0x18008a80b`: `    Task ID          = %u\n`
- `0x18008a8db`: `    Task Provider [0x%p] Prov=0x%p Sink=0x%p\n`
- `0x18008a91d`: `WMICORE_TASK_STATUS_NEW`
- `0x18008a914`: `WMICORE_TASK_STATUS_CANCELLED`
- `0x18008a9c5`: `WMICORE_TASK_NULL`
- `0x18008a9bc`: `WMICORE_TASK_GET_OBJECT`
- `0x18008a9b3`: `WMICORE_TASK_GET_INSTANCE`
- `0x18008a9a7`: `WMICORE_TASK_PUT_INSTANCE`
- `0x18008a99b`: `WMICORE_TASK_DELETE_INSTANCE`
- `0x18008a98f`: `WMICORE_TASK_ENUM_INSTANCES`
- `0x18008a983`: `WMICORE_TASK_GET_CLASS`
- `0x18008a977`: `WMICORE_TASK_PUT_CLASS`
- `0x18008a9ce`: `WMICORE_TASK_DELETE_CLASS`
- `0x18008aa30`: `WMICORE_TASK_ENUM_CLASSES`
- `0x18008aa27`: `WMICORE_TASK_EXEC_QUERY`
- `0x18008aa1e`: `WMICORE_TASK_EXEC_METHOD`
- `0x18008aa15`: `WMICORE_TASK_OPEN`
- `0x18008aa0c`: `WMICORE_TASK_OPEN_SCOPE`
- `0x18008aa03`: `WMICORE_TASK_OPEN_NAMESPACE`
- `0x18008a9fa`: `WMICORE_TASK_EXEC_NOTIFICATION_QUERY`
- `0x18008aa3a`: `    Task Type = [0x%X] %s `
- `0x18008aa53`: ` WMICORE_TASK_TYPE_SYNC`
- `0x18008aa6c`: ` WMICORE_TASK_TYPE_SEMISYNC`
- `0x18008aa85`: ` WMICORE_TASK_TYPE_ASYNC`
- `0x18008aa9e`: ` WMICORE_TASK_TYPE_PRIMARY`
- `0x18008aab7`: ` WMICORE_TASK_TYPE_DEPENDENT`
- `0x18008aafc`: `    Task semisync option = REWINDABLE\n`
- `0x18008ab1b`: `    Task memory usage = %u bytes\n`
- `0x18008ab32`: `    Task total sleep time = %d ms\n`
- `0x18008ab49`: `    Task last sleep time = %d ms\n`
- `0x18008ab9e`: `    Task Start time = %ls\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWmiTask::Dump(CWmiTask *this, struct _iobuf *a2, char a3)
{
  int v6; // eax
  LONG lVal; // r8d
  unsigned int i; // ebx
  const void ***v9; // rax
  int v10; // ecx
  const char *v11; // rbx
  const char *v12; // r8
  int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // r15d
  __int64 v16; // rax
  int v17; // r8d
  CWmiFinalizer *v19; // [rsp+30h] [rbp-40h] BYREF
  CWmiFinalizer *v20; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v21[16]; // [rsp+40h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  ULONGLONG v23; // [rsp+A0h] [rbp+30h] BYREF
  OLECHAR *DatetimeStr; // [rsp+B8h] [rbp+48h] BYREF

  fprintf(a2, "---Task = 0x%p ---------------------------\n", this);
  fprintf(a2, "    Refcount         = %d\n", *((_DWORD *)this + 2));
  fprintf(a2, "    TaskStatus       = %u\n", *((_DWORD *)this + 4));
  fprintf(a2, "    Task ID          = %u\n", *((_DWORD *)this + 5));
  CCheckedInCritSec::CCheckedInCritSec((CCheckedInCritSec *)v21, (CWmiTask *)((char *)this + 272));
  if ( *((_QWORD *)this + 22) )
  {
    VariantInit(&pvarg);
    v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, _QWORD, VARIANTARG *))(**((_QWORD **)this + 22) + 72LL))(
           *((_QWORD *)this + 22),
           L"__GroupOperationId",
           0,
           &pvarg);
    lVal = -1;
    if ( v6 >= 0 )
      lVal = pvarg.lVal;
    fprintf(a2, "    GroupOperationID = %d\n", lVal);
    _variant_t::~_variant_t(&pvarg);
  }
  fprintf(a2, "    Throttled state  = %d\n", *((_DWORD *)this + 7));
  fprintf(a2, "    AsyncClientSink  = 0x%p\n", *((const void **)this + 16));
  for ( i = 0; (signed int)i < *((_DWORD *)this + 10); ++i )
  {
    v9 = (const void ***)CFlexArray::operator[]((char *)this + 40, i);
    fprintf(a2, "    Task Provider [0x%p] Prov=0x%p Sink=0x%p\n", this, **v9, (*v9)[1]);
  }
  CCheckedInCritSec::Leave((CCheckedInCritSec *)v21);
  v10 = *((_DWORD *)this + 4);
  v11 = "<none>";
  if ( v10 )
  {
    if ( v10 == 1 )
      v12 = "WMICORE_TASK_STATUS_CANCELLED";
    else
      v12 = "<none>";
  }
  else
  {
    v12 = "WMICORE_TASK_STATUS_NEW";
  }
  fprintf(a2, " %s\n", v12);
  v13 = *((_DWORD *)this + 3);
  if ( (unsigned __int8)v13 > 8u )
  {
    switch ( (unsigned __int8)v13 )
    {
      case 9u:
        v11 = "WMICORE_TASK_ENUM_CLASSES";
        break;
      case 0xAu:
        v11 = "WMICORE_TASK_EXEC_QUERY";
        break;
      case 0xBu:
        v11 = "WMICORE_TASK_EXEC_METHOD";
        break;
      case 0xCu:
        v11 = "WMICORE_TASK_OPEN";
        break;
      case 0xDu:
        v11 = "WMICORE_TASK_OPEN_SCOPE";
        break;
      case 0xEu:
        v11 = "WMICORE_TASK_OPEN_NAMESPACE";
        break;
      case 0x19u:
        v11 = "WMICORE_TASK_EXEC_NOTIFICATION_QUERY";
        break;
    }
  }
  else if ( (unsigned __int8)v13 == 8 )
  {
    v11 = "WMICORE_TASK_DELETE_CLASS";
  }
  else if ( (_BYTE)v13 )
  {
    switch ( (unsigned __int8)v13 )
    {
      case 1u:
        v11 = "WMICORE_TASK_GET_OBJECT";
        break;
      case 2u:
        v11 = "WMICORE_TASK_GET_INSTANCE";
        break;
      case 3u:
        v11 = "WMICORE_TASK_PUT_INSTANCE";
        break;
      case 4u:
        v11 = "WMICORE_TASK_DELETE_INSTANCE";
        break;
      case 5u:
        v11 = "WMICORE_TASK_ENUM_INSTANCES";
        break;
      case 6u:
        v11 = "WMICORE_TASK_GET_CLASS";
        break;
      case 7u:
        v11 = "WMICORE_TASK_PUT_CLASS";
        break;
    }
  }
  else
  {
    v11 = "WMICORE_TASK_NULL";
  }
  fprintf(a2, "    Task Type = [0x%X] %s ", v13, v11);
  if ( (*((_DWORD *)this + 3) & 0x1000000) != 0 )
    fprintf(a2, " WMICORE_TASK_TYPE_SYNC");
  if ( (*((_DWORD *)this + 3) & 0x2000000) != 0 )
    fprintf(a2, " WMICORE_TASK_TYPE_SEMISYNC");
  if ( (*((_DWORD *)this + 3) & 0x4000000) != 0 )
    fprintf(a2, " WMICORE_TASK_TYPE_ASYNC");
  if ( (*((_DWORD *)this + 3) & 0x10000000) != 0 )
    fprintf(a2, " WMICORE_TASK_TYPE_PRIMARY");
  if ( (*((_DWORD *)this + 3) & 0x40000000) != 0 )
    fprintf(a2, " WMICORE_TASK_TYPE_DEPENDENT");
  fprintf(a2, "\n");
  v19 = 0;
  if ( (int)CWmiTask::GetFinalizer(this, &v19) >= 0 && *((_BYTE *)v19 + 608) )
    fprintf(a2, "    Task semisync option = REWINDABLE\n");
  v20 = v19;
  fprintf(a2, "    Task memory usage = %u bytes\n", *((_DWORD *)this + 36));
  fprintf(a2, "    Task total sleep time = %d ms\n", *((_DWORD *)this + 37));
  fprintf(a2, "    Task last sleep time = %d ms\n", *((_DWORD *)this + 39));
  v14 = 10000 * *((_DWORD *)this + 80) + g_uliOsBootupTime.LowPart;
  v23 = v14;
  v15 = a3 & 0xF;
  DatetimeStr = WBEMTime::GetDatetimeStr((WBEMTime *)&v23, v14, v15);
  fprintf(a2, "    Task Start time = %ls\n", DatetimeStr);
  CSysFreeMe::~CSysFreeMe(&DatetimeStr);
  if ( v19 )
  {
    v16 = *((_QWORD *)v19 + 29);
    if ( v16 )
    {
      v23 = 10000 * v16 + g_uliOsBootupTime.QuadPart;
      DatetimeStr = WBEMTime::GetDatetimeStr((WBEMTime *)&v23, v23, v15);
      fprintf(a2, "    LastHeartbeat   = %ls\n", DatetimeStr);
      CSysFreeMe::~CSysFreeMe(&DatetimeStr);
    }
    else
    {
      fprintf(a2, "    LastHeartbeat   = 0\n");
    }
    CWmiFinalizer::DumpEx(v19, a2, v17);
  }
  CWbemNamespace::Dump(*((CWbemNamespace **)this + 39), a2, 1);
  fprintf(a2, "\n");
  CReleaseMe::release((CReleaseMe *)&v20);
  CCheckedInCritSec::~CCheckedInCritSec((CCheckedInCritSec *)v21);
  return 0;
}

```

## disassembly

```asm
0x18008a7b0  mov     [rsp-28h+arg_8], rbx
0x18008a7b5  push    rbp
0x18008a7b6  push    rsi
0x18008a7b7  push    rdi
0x18008a7b8  push    r14
0x18008a7ba  push    r15
0x18008a7bc  mov     rbp, rsp
0x18008a7bf  sub     rsp, 70h
0x18008a7c3  mov     r15d, r8d
0x18008a7c6  mov     rdi, rdx
0x18008a7c9  mov     rsi, rcx
0x18008a7cc  mov     r8, rcx
0x18008a7cf  lea     rdx, aTask0xP; "---Task = 0x%p ------------------------"...
0x18008a7d6  mov     rcx, rdi; Stream
0x18008a7d9  call    cs:__imp_fprintf
0x18008a7df  mov     r8d, [rsi+8]
0x18008a7e3  lea     rdx, aRefcountD; "    Refcount         = %d\n"
0x18008a7ea  mov     rcx, rdi; Stream
0x18008a7ed  call    cs:__imp_fprintf
0x18008a7f3  mov     r8d, [rsi+10h]
0x18008a7f7  lea     rdx, aTaskstatusU; "    TaskStatus       = %u\n"
0x18008a7fe  mov     rcx, rdi; Stream
0x18008a801  call    cs:__imp_fprintf
0x18008a807  mov     r8d, [rsi+14h]
0x18008a80b  lea     rdx, aTaskIdU; "    Task ID          = %u\n"
0x18008a812  mov     rcx, rdi; Stream
0x18008a815  call    cs:__imp_fprintf
0x18008a81b  lea     rdx, [rsi+110h]
0x18008a822  lea     rcx, [rbp+var_30]
0x18008a826  call    cs:__imp_??0CCheckedInCritSec@@QEAA@PEAVCCritSec@@@Z; CCheckedInCritSec::CCheckedInCritSec(CCritSec *)
0x18008a82c  nop
0x18008a82d  cmp     qword ptr [rsi+0B0h], 0
0x18008a835  jz      short loc_18008A888
0x18008a837  lea     rcx, [rbp+pvarg]; pvarg
0x18008a83b  call    cs:__imp_VariantInit
0x18008a841  nop
0x18008a842  mov     rcx, [rsi+0B0h]
0x18008a849  mov     rax, [rcx]
0x18008a84c  lea     r9, [rbp+pvarg]
0x18008a850  xor     r8d, r8d
0x18008a853  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18008a85a  mov     rax, [rax+48h]
0x18008a85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a863  or      r8d, 0FFFFFFFFh
0x18008a867  test    eax, eax
0x18008a869  cmovns  r8d, dword ptr [rbp+pvarg+8]
0x18008a86e  lea     rdx, aGroupoperation_0; "    GroupOperationID = %d\n"
0x18008a875  mov     rcx, rdi; Stream
0x18008a878  call    cs:__imp_fprintf
0x18008a87e  nop
0x18008a87f  lea     rcx, [rbp+pvarg]; this
0x18008a883  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x18008a888  mov     r8d, [rsi+1Ch]
0x18008a88c  lea     rdx, aThrottledState; "    Throttled state  = %d\n"
0x18008a893  mov     rcx, rdi; Stream
0x18008a896  call    cs:__imp_fprintf
0x18008a89c  mov     r8, [rsi+80h]
0x18008a8a3  lea     rdx, aAsyncclientsin; "    AsyncClientSink  = 0x%p\n"
0x18008a8aa  mov     rcx, rdi; Stream
0x18008a8ad  call    cs:__imp_fprintf
0x18008a8b3  xor     ebx, ebx
0x18008a8b5  lea     r14, [rsi+28h]
0x18008a8b9  cmp     [r14], ebx
0x18008a8bc  jle     short loc_18008A8F2
0x18008a8be  mov     edx, ebx
0x18008a8c0  mov     rcx, r14
0x18008a8c3  call    cs:__imp_??ACFlexArray@@QEAAAEAPEAXH@Z; CFlexArray::operator[](int)
0x18008a8c9  mov     r9, [rax]
0x18008a8cc  mov     rax, [r9+8]
0x18008a8d0  mov     [rsp+70h+var_50], rax
0x18008a8d5  mov     r9, [r9]
0x18008a8d8  mov     r8, rsi
0x18008a8db  lea     rdx, aTaskProvider0x; "    Task Provider [0x%p] Prov=0x%p Sink"...
0x18008a8e2  mov     rcx, rdi; Stream
0x18008a8e5  call    cs:__imp_fprintf
0x18008a8eb  inc     ebx
0x18008a8ed  cmp     ebx, [r14]
0x18008a8f0  jl      short loc_18008A8BE
0x18008a8f2  lea     rcx, [rbp+var_30]
0x18008a8f6  call    cs:__imp_?Leave@CCheckedInCritSec@@QEAAXXZ; CCheckedInCritSec::Leave(void)
0x18008a8fc  mov     ecx, [rsi+10h]
0x18008a8ff  lea     rbx, aNone_0; "<none>"
0x18008a906  test    ecx, ecx
0x18008a908  jz      short loc_18008A91D
0x18008a90a  cmp     ecx, 1
0x18008a90d  jz      short loc_18008A914
0x18008a90f  mov     r8, rbx
0x18008a912  jmp     short loc_18008A924
0x18008a914  lea     r8, aWmicoreTaskSta; "WMICORE_TASK_STATUS_CANCELLED"
0x18008a91b  jmp     short loc_18008A924
0x18008a91d  lea     r8, aWmicoreTaskSta_0; "WMICORE_TASK_STATUS_NEW"
0x18008a924  lea     rdx, aS_0; " %s\n"
0x18008a92b  mov     rcx, rdi; Stream
0x18008a92e  call    cs:__imp_fprintf
0x18008a934  mov     r8d, [rsi+0Ch]
0x18008a938  movzx   eax, r8b
0x18008a93c  cmp     eax, 8
0x18008a93f  ja      loc_18008A9D7
0x18008a945  jz      loc_18008A9CE
0x18008a94b  test    r8b, r8b
0x18008a94e  jz      short loc_18008A9C5
0x18008a950  sub     eax, 1
0x18008a953  jz      short loc_18008A9BC
0x18008a955  sub     eax, 1
0x18008a958  jz      short loc_18008A9B3
0x18008a95a  sub     eax, 1
0x18008a95d  jz      short loc_18008A9A7
0x18008a95f  sub     eax, 1
0x18008a962  jz      short loc_18008A99B
0x18008a964  sub     eax, 1
0x18008a967  jz      short loc_18008A98F
0x18008a969  sub     eax, 1
0x18008a96c  jz      short loc_18008A983
0x18008a96e  cmp     eax, 1
0x18008a971  jnz     loc_18008AA37
0x18008a977  lea     rbx, aWmicoreTaskPut_0; "WMICORE_TASK_PUT_CLASS"
0x18008a97e  jmp     loc_18008AA37
0x18008a983  lea     rbx, aWmicoreTaskGet_1; "WMICORE_TASK_GET_CLASS"
0x18008a98a  jmp     loc_18008AA37
0x18008a98f  lea     rbx, aWmicoreTaskEnu_0; "WMICORE_TASK_ENUM_INSTANCES"
0x18008a996  jmp     loc_18008AA37
0x18008a99b  lea     rbx, aWmicoreTaskDel; "WMICORE_TASK_DELETE_INSTANCE"
0x18008a9a2  jmp     loc_18008AA37
0x18008a9a7  lea     rbx, aWmicoreTaskPut; "WMICORE_TASK_PUT_INSTANCE"
0x18008a9ae  jmp     loc_18008AA37
0x18008a9b3  lea     rbx, aWmicoreTaskGet; "WMICORE_TASK_GET_INSTANCE"
0x18008a9ba  jmp     short loc_18008AA37
0x18008a9bc  lea     rbx, aWmicoreTaskGet_0; "WMICORE_TASK_GET_OBJECT"
0x18008a9c3  jmp     short loc_18008AA37
0x18008a9c5  lea     rbx, aWmicoreTaskNul; "WMICORE_TASK_NULL"
0x18008a9cc  jmp     short loc_18008AA37
0x18008a9ce  lea     rbx, aWmicoreTaskDel_0; "WMICORE_TASK_DELETE_CLASS"
0x18008a9d5  jmp     short loc_18008AA37
0x18008a9d7  sub     eax, 9
0x18008a9da  jz      short loc_18008AA30
0x18008a9dc  sub     eax, 1
0x18008a9df  jz      short loc_18008AA27
0x18008a9e1  sub     eax, 1
0x18008a9e4  jz      short loc_18008AA1E
0x18008a9e6  sub     eax, 1
0x18008a9e9  jz      short loc_18008AA15
0x18008a9eb  sub     eax, 1
0x18008a9ee  jz      short loc_18008AA0C
0x18008a9f0  sub     eax, 1
0x18008a9f3  jz      short loc_18008AA03
0x18008a9f5  cmp     eax, 0Bh
0x18008a9f8  jnz     short loc_18008AA37
0x18008a9fa  lea     rbx, aWmicoreTaskExe_0; "WMICORE_TASK_EXEC_NOTIFICATION_QUERY"
0x18008aa01  jmp     short loc_18008AA37
0x18008aa03  lea     rbx, aWmicoreTaskOpe_1; "WMICORE_TASK_OPEN_NAMESPACE"
0x18008aa0a  jmp     short loc_18008AA37
0x18008aa0c  lea     rbx, aWmicoreTaskOpe_0; "WMICORE_TASK_OPEN_SCOPE"
0x18008aa13  jmp     short loc_18008AA37
0x18008aa15  lea     rbx, aWmicoreTaskOpe; "WMICORE_TASK_OPEN"
0x18008aa1c  jmp     short loc_18008AA37
0x18008aa1e  lea     rbx, aWmicoreTaskExe_1; "WMICORE_TASK_EXEC_METHOD"
0x18008aa25  jmp     short loc_18008AA37
0x18008aa27  lea     rbx, aWmicoreTaskExe; "WMICORE_TASK_EXEC_QUERY"
0x18008aa2e  jmp     short loc_18008AA37
0x18008aa30  lea     rbx, aWmicoreTaskEnu; "WMICORE_TASK_ENUM_CLASSES"
0x18008aa37  mov     r9, rbx
0x18008aa3a  lea     rdx, aTaskType0xXS; "    Task Type = [0x%X] %s "
0x18008aa41  mov     rcx, rdi; Stream
0x18008aa44  call    cs:__imp_fprintf
0x18008aa4a  test    dword ptr [rsi+0Ch], 1000000h
0x18008aa51  jz      short loc_18008AA63
0x18008aa53  lea     rdx, aWmicoreTaskTyp_0; " WMICORE_TASK_TYPE_SYNC"
0x18008aa5a  mov     rcx, rdi; Stream
0x18008aa5d  call    cs:__imp_fprintf
0x18008aa63  test    dword ptr [rsi+0Ch], 2000000h
0x18008aa6a  jz      short loc_18008AA7C
0x18008aa6c  lea     rdx, aWmicoreTaskTyp; " WMICORE_TASK_TYPE_SEMISYNC"
0x18008aa73  mov     rcx, rdi; Stream
0x18008aa76  call    cs:__imp_fprintf
0x18008aa7c  test    dword ptr [rsi+0Ch], 4000000h
0x18008aa83  jz      short loc_18008AA95
0x18008aa85  lea     rdx, aWmicoreTaskTyp_1; " WMICORE_TASK_TYPE_ASYNC"
0x18008aa8c  mov     rcx, rdi; Stream
0x18008aa8f  call    cs:__imp_fprintf
0x18008aa95  test    dword ptr [rsi+0Ch], 10000000h
0x18008aa9c  jz      short loc_18008AAAE
0x18008aa9e  lea     rdx, aWmicoreTaskTyp_2; " WMICORE_TASK_TYPE_PRIMARY"
0x18008aaa5  mov     rcx, rdi; Stream
0x18008aaa8  call    cs:__imp_fprintf
0x18008aaae  test    dword ptr [rsi+0Ch], 40000000h
0x18008aab5  jz      short loc_18008AAC7
0x18008aab7  lea     rdx, aWmicoreTaskTyp_3; " WMICORE_TASK_TYPE_DEPENDENT"
0x18008aabe  mov     rcx, rdi; Stream
0x18008aac1  call    cs:__imp_fprintf
0x18008aac7  lea     rdx, asc_1800EF250; "\n"
0x18008aace  mov     rcx, rdi; Stream
0x18008aad1  call    cs:__imp_fprintf
0x18008aad7  mov     [rbp+var_40], 0
0x18008aadf  lea     rdx, [rbp+var_40]; struct _IWmiFinalizer **
0x18008aae3  mov     rcx, rsi; this
0x18008aae6  call    ?GetFinalizer@CWmiTask@@QEAAJPEAPEAU_IWmiFinalizer@@@Z; CWmiTask::GetFinalizer(_IWmiFinalizer * *)
0x18008aaeb  test    eax, eax
0x18008aaed  js      short loc_18008AB0C
0x18008aaef  mov     rax, [rbp+var_40]
0x18008aaf3  cmp     byte ptr [rax+260h], 0
0x18008aafa  jz      short loc_18008AB0C
0x18008aafc  lea     rdx, aTaskSemisyncOp; "    Task semisync option = REWINDABLE\n"
0x18008ab03  mov     rcx, rdi; Stream
0x18008ab06  call    cs:__imp_fprintf
0x18008ab0c  mov     rax, [rbp+var_40]
0x18008ab10  mov     [rbp+var_38], rax
0x18008ab14  mov     r8d, [rsi+90h]
0x18008ab1b  lea     rdx, aTaskMemoryUsag; "    Task memory usage = %u bytes\n"
0x18008ab22  mov     rcx, rdi; Stream
0x18008ab25  call    cs:__imp_fprintf
0x18008ab2b  mov     r8d, [rsi+94h]
0x18008ab32  lea     rdx, aTaskTotalSleep; "    Task total sleep time = %d ms\n"
0x18008ab39  mov     rcx, rdi; Stream
0x18008ab3c  call    cs:__imp_fprintf
0x18008ab42  mov     r8d, [rsi+9Ch]
0x18008ab49  lea     rdx, aTaskLastSleepT; "    Task last sleep time = %d ms\n"
0x18008ab50  mov     rcx, rdi; Stream
0x18008ab53  call    cs:__imp_fprintf
0x18008ab59  imul    rcx, [rsi+140h], 2710h
0x18008ab64  mov     rax, cs:?g_uliOsBootupTime@@3T_ULARGE_INTEGER@@A; _ULARGE_INTEGER g_uliOsBootupTime
0x18008ab6b  add     rax, rcx
0x18008ab6e  mov     rdx, rax
0x18008ab71  mov     rbx, 0FFFFFFFF00000000h
0x18008ab7b  and     rdx, rbx
0x18008ab7e  mov     ecx, eax
0x18008ab80  or      rdx, rcx; int
0x18008ab83  mov     [rbp+arg_0], rdx
0x18008ab87  and     r15d, 0Fh
0x18008ab8b  mov     r8d, r15d; unsigned int
0x18008ab8e  lea     rcx, [rbp+arg_0]; this
0x18008ab92  call    ?GetDatetimeStr@WBEMTime@@QEBAPEAGHK@Z; WBEMTime::GetDatetimeStr(int,ulong)
0x18008ab97  mov     [rbp+arg_18], rax
0x18008ab9b  mov     r8, rax
0x18008ab9e  lea     rdx, aTaskStartTimeL; "    Task Start time = %ls\n"
0x18008aba5  mov     rcx, rdi; Stream
0x18008aba8  call    cs:__imp_fprintf
0x18008abae  nop
0x18008abaf  lea     rcx, [rbp+arg_18]; this
0x18008abb3  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18008abb8  mov     rax, [rbp+var_40]
0x18008abbc  test    rax, rax
0x18008abbf  jz      short loc_18008AC38
0x18008abc1  mov     rax, [rax+0E8h]
0x18008abc8  test    rax, rax
0x18008abcb  jz      short loc_18008AC1C
0x18008abcd  imul    rcx, rax, 2710h
0x18008abd4  mov     rax, cs:?g_uliOsBootupTime@@3T_ULARGE_INTEGER@@A; _ULARGE_INTEGER g_uliOsBootupTime
0x18008abdb  add     rax, rcx
0x18008abde  mov     rdx, rax
0x18008abe1  and     rdx, rbx
0x18008abe4  mov     ecx, eax
0x18008abe6  or      rdx, rcx; int
0x18008abe9  mov     [rbp+arg_0], rdx
0x18008abed  mov     r8d, r15d; unsigned int
0x18008abf0  lea     rcx, [rbp+arg_0]; this
0x18008abf4  call    ?GetDatetimeStr@WBEMTime@@QEBAPEAGHK@Z; WBEMTime::GetDatetimeStr(int,ulong)
0x18008abf9  mov     [rbp+arg_18], rax
0x18008abfd  mov     r8, rax
0x18008ac00  lea     rdx, aLastheartbeatL; "    LastHeartbeat   = %ls\n"
0x18008ac07  mov     rcx, rdi; Stream
0x18008ac0a  call    cs:__imp_fprintf
0x18008ac10  nop
0x18008ac11  lea     rcx, [rbp+arg_18]; this
0x18008ac15  call    ??1CSysFreeMe@@QEAA@XZ; CSysFreeMe::~CSysFreeMe(void)
0x18008ac1a  jmp     short loc_18008AC2C
0x18008ac1c  lea     rdx, aLastheartbeat0; "    LastHeartbeat   = 0\n"
0x18008ac23  mov     rcx, rdi; Stream
0x18008ac26  call    cs:__imp_fprintf
0x18008ac2c  mov     rdx, rdi; struct _iobuf *
0x18008ac2f  mov     rcx, [rbp+var_40]; this
0x18008ac33  call    ?DumpEx@CWmiFinalizer@@QEAAXPEAU_iobuf@@H@Z; CWmiFinalizer::DumpEx(_iobuf *,int)
0x18008ac38  mov     r8d, 1; int
0x18008ac3e  mov     rdx, rdi; struct _iobuf *
0x18008ac41  mov     rcx, [rsi+138h]; this
0x18008ac48  call    ?Dump@CWbemNamespace@@QEAAJPEAU_iobuf@@H@Z; CWbemNamespace::Dump(_iobuf *,int)
0x18008ac4d  lea     rdx, asc_1800EF250; "\n"
0x18008ac54  mov     rcx, rdi; Stream
0x18008ac57  call    cs:__imp_fprintf
0x18008ac5d  nop
0x18008ac5e  lea     rcx, [rbp+var_38]; this
0x18008ac62  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18008ac67  nop
0x18008ac68  lea     rcx, [rbp+var_30]
0x18008ac6c  call    cs:__imp_??1CCheckedInCritSec@@QEAA@XZ; CCheckedInCritSec::~CCheckedInCritSec(void)
0x18008ac72  xor     eax, eax
0x18008ac74  mov     rbx, [rsp+70h+arg_8]
0x18008ac7c  add     rsp, 70h
0x18008ac80  pop     r15
0x18008ac82  pop     r14
0x18008ac84  pop     rdi
0x18008ac85  pop     rsi
0x18008ac86  pop     rbp
0x18008ac87  retn
```

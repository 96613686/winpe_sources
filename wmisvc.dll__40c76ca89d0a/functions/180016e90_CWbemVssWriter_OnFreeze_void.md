# CWbemVssWriter::OnFreeze(void)

- ea: `0x180016e90`
- end: `0x180016fae`
- name: `?OnFreeze@CWbemVssWriter@@UEAA_NXZ`
- size: `286`
- prototype: `char __fastcall(CWbemVssWriter *this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004fd0`
- `0x18000ca50`
- `0x180016e90`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f88`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f88`
- `wbemcomn!EnableAllPrivileges` at `0x180016f2e`
- `wbemcomn!EnableAllPrivileges` at `0x180016f2e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f11`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016f11`

## pseudocode

```c
char __fastcall CWbemVssWriter::OnFreeze(CWbemVssWriter *this)
{
  _QWORD *v2; // rsi
  HRESULT Instance; // eax
  char v5; // di
  int v6; // eax
  int v7; // r14d
  CWbemVssWriter *v8; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+38h] [rbp-8h]
  char v10; // [rsp+3Ch] [rbp-4h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp+20h] BYREF

  v8 = this;
  v9 = -2147212301;
  v10 = 0;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v2 = (_QWORD *)((char *)this + 16);
  if ( *((_QWORD *)this + 2) )
  {
    *((_DWORD *)this + 16) = -2147418113;
    *((_DWORD *)this + 17) = 147;
LABEL_3:
    LeaveCriticalSection(lpCriticalSection);
    OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>((__int64)&v8);
    return 0;
  }
  Instance = CoCreateInstance(&CLSID_WbemBackupRestore, 0, 4u, &IID_IWbemBackupRestoreEx, (LPVOID *)this + 2);
  if ( Instance < 0 )
  {
    *((_DWORD *)this + 16) = Instance;
    *((_DWORD *)this + 17) = 154;
    goto LABEL_3;
  }
  v5 = 1;
  v6 = EnableAllPrivileges(1u);
  if ( v6 < 0 )
  {
    *((_DWORD *)this + 16) = v6;
    *((_DWORD *)this + 17) = 158;
    goto LABEL_3;
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 40LL))(*v2);
  if ( v7 >= 0 )
  {
    v10 = 1;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    *v2 = 0;
    *((_DWORD *)this + 16) = v7;
    *((_DWORD *)this + 17) = 166;
    v5 = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>((__int64)&v8);
  return v5;
}

```

## disassembly

```asm
0x180016e90  mov     [rsp-18h+arg_8], rbx
0x180016e95  mov     [rsp-18h+arg_10], rsi
0x180016e9a  push    rbp
0x180016e9b  push    rdi
0x180016e9c  push    r14
0x180016e9e  mov     rbp, rsp
0x180016ea1  sub     rsp, 40h
0x180016ea5  mov     rbx, rcx
0x180016ea8  mov     [rbp+var_10], rcx
0x180016eac  mov     [rbp+var_8], 800423F3h
0x180016eb3  mov     [rbp+var_4], 0
0x180016eb7  lea     rdx, [rcx+18h]; struct _RTL_CRITICAL_SECTION *
0x180016ebb  lea     rcx, [rbp+lpCriticalSection]; this
0x180016ebf  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180016ec4  nop
0x180016ec5  lea     rsi, [rbx+10h]
0x180016ec9  cmp     qword ptr [rsi], 0
0x180016ecd  jz      short loc_180016EF8
0x180016ecf  mov     dword ptr [rbx+40h], 8000FFFFh
0x180016ed6  mov     dword ptr [rbx+44h], 93h
0x180016edd  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180016ee1  call    cs:__imp_LeaveCriticalSection
0x180016ee7  nop
0x180016ee8  lea     rcx, [rbp+var_10]
0x180016eec  call    ??1?$OnDeleteObjIf@JVCWbemVssWriter@@P81@EAAJJ@Z$1?LogFailure@1@AEAAJJ@Z@@QEAA@XZ; OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>(void)
0x180016ef1  xor     al, al
0x180016ef3  jmp     loc_180016F9B
0x180016ef8  mov     [rsp+40h+ppv], rsi; ppv
0x180016efd  lea     r9, IID_IWbemBackupRestoreEx; riid
0x180016f04  xor     edx, edx; pUnkOuter
0x180016f06  lea     r8d, [rdx+4]; dwClsContext
0x180016f0a  lea     rcx, CLSID_WbemBackupRestore; rclsid
0x180016f11  call    cs:__imp_CoCreateInstance
0x180016f17  test    eax, eax
0x180016f19  jns     short loc_180016F27
0x180016f1b  mov     [rbx+40h], eax
0x180016f1e  mov     dword ptr [rbx+44h], 9Ah
0x180016f25  jmp     short loc_180016EDD
0x180016f27  mov     edi, 1
0x180016f2c  mov     ecx, edi
0x180016f2e  call    cs:__imp_?EnableAllPrivileges@@YAJK@Z; EnableAllPrivileges(ulong)
0x180016f34  test    eax, eax
0x180016f36  jns     short loc_180016F44
0x180016f38  mov     [rbx+40h], eax
0x180016f3b  mov     dword ptr [rbx+44h], 9Eh
0x180016f42  jmp     short loc_180016EDD
0x180016f44  mov     rcx, [rsi]
0x180016f47  mov     rax, [rcx]
0x180016f4a  mov     rax, [rax+28h]
0x180016f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f53  mov     r14d, eax
0x180016f56  test    eax, eax
0x180016f58  jns     short loc_180016F80
0x180016f5a  mov     rcx, [rsi]
0x180016f5d  mov     rdx, [rcx]
0x180016f60  mov     rax, [rdx+10h]
0x180016f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f69  mov     qword ptr [rsi], 0
0x180016f70  mov     [rbx+40h], r14d
0x180016f74  mov     dword ptr [rbx+44h], 0A6h
0x180016f7b  xor     dil, dil
0x180016f7e  jmp     short loc_180016F84
0x180016f80  mov     [rbp+var_4], dil
0x180016f84  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180016f88  call    cs:__imp_LeaveCriticalSection
0x180016f8e  nop
0x180016f8f  lea     rcx, [rbp+var_10]
0x180016f93  call    ??1?$OnDeleteObjIf@JVCWbemVssWriter@@P81@EAAJJ@Z$1?LogFailure@1@AEAAJJ@Z@@QEAA@XZ; OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>(void)
0x180016f98  mov     al, dil
0x180016f9b  mov     rbx, [rsp+40h+arg_8]
0x180016fa0  mov     rsi, [rsp+40h+arg_10]
0x180016fa5  add     rsp, 40h
0x180016fa9  pop     r14
0x180016fab  pop     rdi
0x180016fac  pop     rbp
0x180016fad  retn
```

# CWbemVssWriter::OnAbort(void)

- ea: `0x180016df0`
- end: `0x180016e88`
- name: `?OnAbort@CWbemVssWriter@@UEAA_NXZ`
- size: `152`
- prototype: `bool __fastcall(CWbemVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004fd0`
- `0x18000ca50`
- `0x180016df0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e6a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e6a`

## pseudocode

```c
bool __fastcall CWbemVssWriter::OnAbort(CWbemVssWriter *this)
{
  int v2; // ebx
  __int64 v3; // rcx
  int v4; // eax
  bool v5; // bl
  CWbemVssWriter *v7; // [rsp+20h] [rbp-18h] BYREF
  int v8; // [rsp+28h] [rbp-10h]
  bool v9; // [rsp+2Ch] [rbp-Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+8h] BYREF

  v7 = this;
  v8 = -2147212301;
  v9 = 0;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v2 = 0;
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
    v2 = v4;
    if ( v4 < 0 )
    {
      *((_DWORD *)this + 16) = v4;
      *((_DWORD *)this + 17) = 223;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  v5 = v2 >= 0;
  v9 = v5;
  LeaveCriticalSection(lpCriticalSection);
  OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>((__int64)&v7);
  return v5;
}

```

## disassembly

```asm
0x180016df0  mov     rax, rsp
0x180016df3  mov     [rax+10h], rbx
0x180016df7  push    rdi
0x180016df8  sub     rsp, 30h
0x180016dfc  mov     rdi, rcx
0x180016dff  mov     [rax-18h], rcx
0x180016e03  mov     dword ptr [rax-10h], 800423F3h
0x180016e0a  mov     byte ptr [rax-0Ch], 0
0x180016e0e  lea     rdx, [rcx+18h]; struct _RTL_CRITICAL_SECTION *
0x180016e12  lea     rcx, [rax+8]; this
0x180016e16  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180016e1b  nop
0x180016e1c  xor     ebx, ebx
0x180016e1e  mov     rcx, [rdi+10h]
0x180016e22  test    rcx, rcx
0x180016e25  jz      short loc_180016E5B
0x180016e27  mov     rax, [rcx]
0x180016e2a  mov     rax, [rax+30h]
0x180016e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e33  mov     ebx, eax
0x180016e35  test    eax, eax
0x180016e37  jns     short loc_180016E43
0x180016e39  mov     [rdi+40h], eax
0x180016e3c  mov     dword ptr [rdi+44h], 0DFh
0x180016e43  mov     rcx, [rdi+10h]
0x180016e47  mov     rdx, [rcx]
0x180016e4a  mov     rax, [rdx+10h]
0x180016e4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e53  mov     qword ptr [rdi+10h], 0
0x180016e5b  shr     ebx, 1Fh
0x180016e5e  xor     bl, 1
0x180016e61  mov     [rsp+38h+var_C], bl
0x180016e65  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180016e6a  call    cs:__imp_LeaveCriticalSection
0x180016e70  nop
0x180016e71  lea     rcx, [rsp+38h+var_18]
0x180016e76  call    ??1?$OnDeleteObjIf@JVCWbemVssWriter@@P81@EAAJJ@Z$1?LogFailure@1@AEAAJJ@Z@@QEAA@XZ; OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>(void)
0x180016e7b  mov     al, bl
0x180016e7d  mov     rbx, [rsp+38h+arg_8]
0x180016e82  add     rsp, 30h
0x180016e86  pop     rdi
0x180016e87  retn
```

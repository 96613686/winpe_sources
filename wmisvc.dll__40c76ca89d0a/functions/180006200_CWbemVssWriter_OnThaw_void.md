# CWbemVssWriter::OnThaw(void)

- ea: `0x180006200`
- end: `0x1800062c2`
- name: `?OnThaw@CWbemVssWriter@@UEAA_NXZ`
- size: `194`
- prototype: `bool __fastcall(CWbemVssWriter *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004fd0`
- `0x180006200`
- `0x18000ca50`
- `0x180016d78`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006249`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006249`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800062a3`

## pseudocode

```c
bool __fastcall CWbemVssWriter::OnThaw(CWbemVssWriter *this)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v5; // eax
  int v6; // edi
  bool v7; // di
  CWbemVssWriter *v8; // [rsp+20h] [rbp-18h] BYREF
  int v9; // [rsp+28h] [rbp-10h]
  bool v10; // [rsp+2Ch] [rbp-Ch]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp+8h] BYREF

  v8 = this;
  v9 = -2147212301;
  v10 = 0;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 24));
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
    v6 = v5;
    if ( v5 < 0 )
    {
      *((_DWORD *)this + 16) = v5;
      *((_DWORD *)this + 17) = 196;
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    v7 = v6 >= 0;
    v10 = v7;
    LeaveCriticalSection(lpCriticalSection);
    OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&private: long CWbemVssWriter::LogFailure(long)>((__int64)&v8);
    return v7;
  }
  else
  {
    *((_DWORD *)this + 16) = -2147418113;
    *((_DWORD *)this + 17) = 186;
    LeaveCriticalSection(lpCriticalSection);
    CWbemVssWriter::LogFailure(this, 2147754995LL, v3);
    return 0;
  }
}

```

## disassembly

```asm
0x180006200  mov     rax, rsp
0x180006203  mov     [rax+10h], rbx
0x180006207  push    rdi
0x180006208  sub     rsp, 30h
0x18000620c  mov     rbx, rcx
0x18000620f  mov     [rax-18h], rcx
0x180006213  mov     edi, 800423F3h
0x180006218  mov     [rax-10h], edi
0x18000621b  mov     byte ptr [rax-0Ch], 0
0x18000621f  lea     rdx, [rcx+18h]; struct _RTL_CRITICAL_SECTION *
0x180006223  lea     rcx, [rax+8]; this
0x180006227  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18000622c  nop
0x18000622d  mov     rcx, [rbx+10h]
0x180006231  test    rcx, rcx
0x180006234  jnz     short loc_18000625E
0x180006236  mov     dword ptr [rbx+40h], 8000FFFFh
0x18000623d  mov     dword ptr [rbx+44h], 0BAh
0x180006244  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180006249  call    cs:__imp_LeaveCriticalSection
0x18000624f  nop
0x180006250  mov     edx, edi; int
0x180006252  mov     rcx, rbx; this
0x180006255  call    ?LogFailure@CWbemVssWriter@@AEAAJJ@Z; CWbemVssWriter::LogFailure(long)
0x18000625a  xor     al, al
0x18000625c  jmp     short loc_1800062B7
0x18000625e  mov     rax, [rcx]
0x180006261  mov     rax, [rax+30h]
0x180006265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000626a  mov     edi, eax
0x18000626c  test    eax, eax
0x18000626e  jns     short loc_18000627A
0x180006270  mov     [rbx+40h], eax
0x180006273  mov     dword ptr [rbx+44h], 0C4h
0x18000627a  mov     rcx, [rbx+10h]
0x18000627e  mov     rdx, [rcx]
0x180006281  mov     rax, [rdx+10h]
0x180006285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000628a  mov     qword ptr [rbx+10h], 0
0x180006292  shr     edi, 1Fh
0x180006295  xor     dil, 1
0x180006299  mov     [rsp+38h+var_C], dil
0x18000629e  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x1800062a3  call    cs:__imp_LeaveCriticalSection
0x1800062a9  nop
0x1800062aa  lea     rcx, [rsp+38h+var_18]
0x1800062af  call    ??1?$OnDeleteObjIf@JVCWbemVssWriter@@P81@EAAJJ@Z$1?LogFailure@1@AEAAJJ@Z@@QEAA@XZ; OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>::~OnDeleteObjIf<long,CWbemVssWriter,long (CWbemVssWriter::*)(long),&CWbemVssWriter::LogFailure(long)>(void)
0x1800062b4  mov     al, dil
0x1800062b7  mov     rbx, [rsp+38h+arg_8]
0x1800062bc  add     rsp, 30h
0x1800062c0  pop     rdi
0x1800062c1  retn
```

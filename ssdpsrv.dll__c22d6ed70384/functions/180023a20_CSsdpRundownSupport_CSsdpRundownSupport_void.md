# CSsdpRundownSupport::~CSsdpRundownSupport(void)

- ea: `0x180023a20`
- end: `0x180023ab6`
- name: `??1CSsdpRundownSupport@@QEAA@XZ`
- size: `150`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180035590`

## callees

- `0x1800186a0`
- `0x180022a80`
- `0x180023a20`
- `0x180023abc`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180023a94`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023a2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023aaf`

## pseudocode

```c
void __fastcall CSsdpRundownSupport::~CSsdpRundownSupport(LPCRITICAL_SECTION lpCriticalSection)
{
  bool v2; // zf
  _QWORD *v3; // [rsp+30h] [rbp+8h] BYREF
  LPCRITICAL_SECTION v4; // [rsp+38h] [rbp+10h] BYREF

  EnterCriticalSection(lpCriticalSection);
  v2 = lpCriticalSection[1].DebugInfo == 0;
  v4 = lpCriticalSection + 1;
  if ( !v2 )
  {
    v3 = 0;
    do
    {
      if ( (unsigned int)CUList<CRundownHelperBase *>::Iterator::HrGetItem(&v4, &v3) )
        break;
      if ( *v3 )
        (**(void (__fastcall ***)(_QWORD, __int64))*v3)(*v3, 1);
    }
    while ( !(unsigned int)CUList<__int64>::Iterator::HrNext(&v4) );
  }
  CUList<CRundownHelperBase *>::Clear(&lpCriticalSection[1]);
  LeaveCriticalSection(lpCriticalSection);
  CUList<CRundownHelperBase *>::Clear(&lpCriticalSection[1]);
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x180023a20  mov     [rsp+arg_10], rbx
0x180023a25  push    rdi
0x180023a26  sub     rsp, 20h
0x180023a2a  mov     rbx, rcx
0x180023a2d  call    cs:__imp_EnterCriticalSection
0x180023a33  lea     rdi, [rbx+28h]
0x180023a37  cmp     qword ptr [rdi], 0
0x180023a3b  mov     [rsp+28h+arg_8], rdi
0x180023a40  jz      short loc_180023A89
0x180023a42  mov     [rsp+28h+arg_0], 0
0x180023a4b  lea     rdx, [rsp+28h+arg_0]
0x180023a50  lea     rcx, [rsp+28h+arg_8]
0x180023a55  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180023a5a  test    eax, eax
0x180023a5c  jnz     short loc_180023A89
0x180023a5e  mov     rax, [rsp+28h+arg_0]
0x180023a63  mov     rcx, [rax]
0x180023a66  test    rcx, rcx
0x180023a69  jz      short loc_180023A7B
0x180023a6b  mov     rax, [rcx]
0x180023a6e  mov     edx, 1
0x180023a73  mov     rax, [rax]
0x180023a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a7b  lea     rcx, [rsp+28h+arg_8]
0x180023a80  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x180023a85  test    eax, eax
0x180023a87  jz      short loc_180023A4B
0x180023a89  mov     rcx, rdi
0x180023a8c  call    ?Clear@?$CUList@PEAVCRundownHelperBase@@@@QEAAXXZ; CUList<CRundownHelperBase *>::Clear(void)
0x180023a91  mov     rcx, rbx; lpCriticalSection
0x180023a94  call    cs:__imp_LeaveCriticalSection
0x180023a9a  mov     rcx, rdi
0x180023a9d  call    ?Clear@?$CUList@PEAVCRundownHelperBase@@@@QEAAXXZ; CUList<CRundownHelperBase *>::Clear(void)
0x180023aa2  mov     rcx, rbx
0x180023aa5  mov     rbx, [rsp+28h+arg_10]
0x180023aaa  add     rsp, 20h
0x180023aae  pop     rdi
0x180023aaf  jmp     cs:__imp_DeleteCriticalSection
```

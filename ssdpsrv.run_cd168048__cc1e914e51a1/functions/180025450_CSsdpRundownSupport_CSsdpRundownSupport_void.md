# CSsdpRundownSupport::~CSsdpRundownSupport(void)

- ea: `0x180025450`
- end: `0x1800254f7`
- name: `??1CSsdpRundownSupport@@QEAA@XZ`
- size: `167`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800380e0`

## callees

- `0x180019920`
- `0x180024490`
- `0x180025450`
- `0x180025500`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800254ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800254ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002545d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002545d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800254eb`

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
0x180025450  mov     [rsp+arg_10], rbx
0x180025455  push    rdi
0x180025456  sub     rsp, 20h
0x18002545a  mov     rbx, rcx
0x18002545d  call    cs:__imp_EnterCriticalSection
0x180025464  nop     dword ptr [rax+rax+00h]
0x180025469  lea     rdi, [rbx+28h]
0x18002546d  cmp     qword ptr [rdi], 0
0x180025471  mov     [rsp+28h+arg_8], rdi
0x180025476  jz      short loc_1800254BF
0x180025478  mov     [rsp+28h+arg_0], 0
0x180025481  lea     rdx, [rsp+28h+arg_0]
0x180025486  lea     rcx, [rsp+28h+arg_8]
0x18002548b  call    ?HrGetItem@Iterator@?$CUList@PEAVCRundownHelperBase@@@@QEAAJPEAPEAPEAVCRundownHelperBase@@@Z; CUList<CRundownHelperBase *>::Iterator::HrGetItem(CRundownHelperBase * * *)
0x180025490  test    eax, eax
0x180025492  jnz     short loc_1800254BF
0x180025494  mov     rax, [rsp+28h+arg_0]
0x180025499  mov     rcx, [rax]
0x18002549c  test    rcx, rcx
0x18002549f  jz      short loc_1800254B1
0x1800254a1  mov     rax, [rcx]
0x1800254a4  mov     edx, 1
0x1800254a9  mov     rax, [rax]
0x1800254ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254b1  lea     rcx, [rsp+28h+arg_8]
0x1800254b6  call    ?HrNext@Iterator@?$CUList@_J@@QEAAJXZ; CUList<__int64>::Iterator::HrNext(void)
0x1800254bb  test    eax, eax
0x1800254bd  jz      short loc_180025481
0x1800254bf  mov     rcx, rdi
0x1800254c2  call    ?Clear@?$CUList@PEAVCRundownHelperBase@@@@QEAAXXZ; CUList<CRundownHelperBase *>::Clear(void)
0x1800254c7  mov     rcx, rbx; lpCriticalSection
0x1800254ca  call    cs:__imp_LeaveCriticalSection
0x1800254d1  nop     dword ptr [rax+rax+00h]
0x1800254d6  mov     rcx, rdi
0x1800254d9  call    ?Clear@?$CUList@PEAVCRundownHelperBase@@@@QEAAXXZ; CUList<CRundownHelperBase *>::Clear(void)
0x1800254de  mov     rcx, rbx
0x1800254e1  mov     rbx, [rsp+28h+arg_10]
0x1800254e6  add     rsp, 20h
0x1800254ea  pop     rdi
0x1800254eb  jmp     cs:__imp_DeleteCriticalSection
```

# TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(void * const &)

- ea: `0x140011268`
- end: `0x1400112c0`
- name: `?ElementInList@?$TLstMgr@VTPrinterHandleInfo@TLPCMgr@@PEAX@@QEBAPEAV?$TLstNd@VTPrinterHandleInfo@TLPCMgr@@PEAX@@AEBQEAX@Z`
- size: `88`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010d98`
- `0x140011624`
- `0x140011814`
- `0x140011bb0`

## callees

- `0x140011268`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14001127e`
- `KERNEL32!EnterCriticalSection` at `0x14001127e`
- `KERNEL32!LeaveCriticalSection` at `0x1400112ad`
- `KERNEL32!LeaveCriticalSection` at `0x1400112ad`

## pseudocode

```c
_QWORD *__fastcall TLstMgr<TLPCMgr::TPrinterHandleInfo,void *>::ElementInList(__int64 a1, _QWORD *a2)
{
  _QWORD *i; // rbx

  i = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  if ( *(_DWORD *)(a1 + 48) )
  {
    for ( i = *(_QWORD **)(a1 + 32); i && *i && *(_QWORD *)(*i + 24LL) != *a2; i = (_QWORD *)i[1] )
      ;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  return i;
}

```

## disassembly

```asm
0x140011268  push    rbx
0x14001126a  push    rsi
0x14001126b  push    rdi
0x14001126c  push    r14
0x14001126e  sub     rsp, 28h
0x140011272  mov     rdi, rcx
0x140011275  mov     r14, rdx
0x140011278  add     rcx, 38h ; '8'; lpCriticalSection
0x14001127c  xor     ebx, ebx
0x14001127e  call    cs:__imp_EnterCriticalSection
0x140011284  cmp     [rdi+30h], ebx
0x140011287  jz      short loc_1400112A9
0x140011289  mov     rbx, [rdi+20h]
0x14001128d  jmp     short loc_1400112A4
0x14001128f  mov     rax, [rbx]
0x140011292  test    rax, rax
0x140011295  jz      short loc_1400112A9
0x140011297  mov     rdx, [r14]
0x14001129a  cmp     [rax+18h], rdx
0x14001129e  jz      short loc_1400112A9
0x1400112a0  mov     rbx, [rbx+8]
0x1400112a4  test    rbx, rbx
0x1400112a7  jnz     short loc_14001128F
0x1400112a9  lea     rcx, [rdi+38h]; lpCriticalSection
0x1400112ad  call    cs:__imp_LeaveCriticalSection
0x1400112b3  mov     rax, rbx
0x1400112b6  add     rsp, 28h
0x1400112ba  pop     r14
0x1400112bc  pop     rdi
0x1400112bd  pop     rsi
0x1400112be  pop     rbx
0x1400112bf  retn
```

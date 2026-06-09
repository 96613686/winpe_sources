# SetGlobalEventMasks

- ea: `0x180034540`
- end: `0x1800345fd`
- name: `SetGlobalEventMasks`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180035280`

## callees

- `0x18001c7c0`
- `0x180034540`
- `0x180034694`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003456b`
- `KERNEL32!GetCurrentThreadId` at `0x1800345bf`
- `KERNEL32!GetCurrentThreadId` at `0x18003456b`
- `KERNEL32!GetCurrentThreadId` at `0x1800345bf`
- `KERNEL32!LeaveCriticalSection` at `0x1800345e5`
- `KERNEL32!LeaveCriticalSection` at `0x1800345e5`
- `KERNEL32!EnterCriticalSection` at `0x18003455b`
- `KERNEL32!EnterCriticalSection` at `0x18003455b`

## pseudocode

```c
__int64 __fastcall SetGlobalEventMasks(__int64 a1, __int64 a2)
{
  unsigned int v3; // edi
  size_t v4; // rdx
  __int64 i; // rbx
  size_t v6; // rdx

  v3 = 0;
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 708;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(pszDest, v4, "\\server\\event.c");
  for ( i = qword_180051908; i; i = *(_QWORD *)(i + 208) )
  {
    v3 = SettClientEventMasks(i, 0, a2, 0);
    if ( v3 )
      break;
  }
  dword_1800519F8 = 727;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v6, "\\server\\event.c");
  LeaveCriticalSection(&CriticalSection);
  return v3;
}

```

## disassembly

```asm
0x180034540  mov     [rsp+arg_0], rbx
0x180034545  mov     [rsp+arg_8], rsi
0x18003454a  push    rdi
0x18003454b  sub     rsp, 20h
0x18003454f  lea     rcx, CriticalSection; lpCriticalSection
0x180034556  mov     rsi, rdx
0x180034559  xor     edi, edi
0x18003455b  call    cs:__imp_EnterCriticalSection
0x180034561  mov     cs:dword_1800519E0, 2C4h
0x18003456b  call    cs:__imp_GetCurrentThreadId
0x180034571  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x180034578  mov     cs:dword_1800519E4, eax
0x18003457e  lea     rcx, pszDest; pszDest
0x180034585  call    StringCbCopyA
0x18003458a  mov     rbx, cs:qword_180051908
0x180034591  jmp     short loc_1800345B0
0x180034593  xor     r9d, r9d
0x180034596  mov     r8, rsi
0x180034599  xor     edx, edx
0x18003459b  mov     rcx, rbx
0x18003459e  call    SettClientEventMasks
0x1800345a3  mov     edi, eax
0x1800345a5  test    eax, eax
0x1800345a7  jnz     short loc_1800345B5
0x1800345a9  mov     rbx, [rbx+0D0h]
0x1800345b0  test    rbx, rbx
0x1800345b3  jnz     short loc_180034593
0x1800345b5  mov     cs:dword_1800519F8, 2D7h
0x1800345bf  call    cs:__imp_GetCurrentThreadId
0x1800345c5  lea     r8, aPrintscanTapiS+0Eh; pszSrc
0x1800345cc  mov     cs:dword_1800519FC, eax
0x1800345d2  lea     rcx, byte_1800519E8; pszDest
0x1800345d9  call    StringCbCopyA
0x1800345de  lea     rcx, CriticalSection; lpCriticalSection
0x1800345e5  call    cs:__imp_LeaveCriticalSection
0x1800345eb  mov     rbx, [rsp+28h+arg_0]
0x1800345f0  mov     eax, edi
0x1800345f2  mov     rsi, [rsp+28h+arg_8]
0x1800345f7  add     rsp, 20h
0x1800345fb  pop     rdi
0x1800345fc  retn
```

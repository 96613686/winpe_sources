# CachedOpenAlgorithmProvider

- ea: `0x18002c108`
- end: `0x18002c17f`
- name: `CachedOpenAlgorithmProvider`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002b838`

## callees

- `0x18002c108`
- `0x18002c1fc`
- `0x18002c2f4`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c148`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002c148`

## pseudocode

```c
__int64 __fastcall CachedOpenAlgorithmProvider(_QWORD *a1, wchar_t *a2)
{
  NTSTATUS v3; // ebx
  BCRYPT_ALG_HANDLE EntryInCache; // rax
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  phAlgorithm = 0;
  EntryInCache = (BCRYPT_ALG_HANDLE)findEntryInCache(a2);
  phAlgorithm = EntryInCache;
  if ( !EntryInCache )
  {
    v3 = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, 0, 0);
    if ( v3 >= 0 )
    {
      addEntryToCache(phAlgorithm, a2);
      EntryInCache = phAlgorithm;
    }
    else
    {
      EntryInCache = 0;
    }
  }
  *a1 = EntryInCache;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002c108  mov     rax, rsp
0x18002c10b  mov     [rax+8], rbx
0x18002c10f  mov     [rax+10h], rsi
0x18002c113  mov     [rax+18h], r8
0x18002c117  push    rdi
0x18002c118  sub     rsp, 20h
0x18002c11c  mov     rsi, rcx
0x18002c11f  xor     ebx, ebx
0x18002c121  mov     rcx, rdx; String1
0x18002c124  mov     [rax+18h], rbx
0x18002c128  mov     rdi, rdx
0x18002c12b  call    findEntryInCache
0x18002c130  mov     [rsp+28h+phAlgorithm], rax
0x18002c135  test    rax, rax
0x18002c138  jnz     short loc_18002C16A
0x18002c13a  xor     r9d, r9d; dwFlags
0x18002c13d  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18002c142  xor     r8d, r8d; pszImplementation
0x18002c145  mov     rdx, rdi; pszAlgId
0x18002c148  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18002c14e  mov     ebx, eax
0x18002c150  test    eax, eax
0x18002c152  jns     short loc_18002C158
0x18002c154  xor     eax, eax
0x18002c156  jmp     short loc_18002C16A
0x18002c158  mov     rcx, [rsp+28h+phAlgorithm]
0x18002c15d  mov     rdx, rdi
0x18002c160  call    addEntryToCache
0x18002c165  mov     rax, [rsp+28h+phAlgorithm]
0x18002c16a  mov     [rsi], rax
0x18002c16d  mov     eax, ebx
0x18002c16f  mov     rbx, [rsp+28h+arg_0]
0x18002c174  mov     rsi, [rsp+28h+arg_8]
0x18002c179  add     rsp, 20h
0x18002c17d  pop     rdi
0x18002c17e  retn
```

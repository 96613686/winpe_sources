# p_GetAlgHandle

- ea: `0x18001f8c8`
- end: `0x18001f93b`
- name: `p_GetAlgHandle`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001da04`
- `0x1800226e4`

## callees

- `0x18001f8c8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001f923`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001f923`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001f8f3`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001f8f3`

## pseudocode

```c
__int64 p_GetAlgHandle()
{
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp+10h] BYREF

  phAlgorithm = 0;
  if ( !g_hSha1Provider )
  {
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0) < 0 )
      __fastfail(7u);
    if ( _InterlockedCompareExchange64(&g_hSha1Provider, (signed __int64)phAlgorithm, 0) )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  return g_hSha1Provider;
}

```

## disassembly

```asm
0x18001f8c8  mov     [rsp+phAlgorithm], rdx
0x18001f8cd  sub     rsp, 28h
0x18001f8d1  and     [rsp+28h+phAlgorithm], 0
0x18001f8d7  cmp     cs:g_hSha1Provider, 0
0x18001f8df  jnz     short loc_18001F92F
0x18001f8e1  xor     r9d, r9d; dwFlags
0x18001f8e4  lea     rdx, pszAlgId; "SHA1"
0x18001f8eb  xor     r8d, r8d; pszImplementation
0x18001f8ee  lea     rcx, [rsp+28h+phAlgorithm]; phAlgorithm
0x18001f8f3  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001f8fa  nop     dword ptr [rax+rax+00h]
0x18001f8ff  test    eax, eax
0x18001f901  jns     short loc_18001F90A
0x18001f903  mov     ecx, 7
0x18001f908  int     29h; Win8: RtlFailFast(ecx)
0x18001f90a  mov     rcx, [rsp+28h+phAlgorithm]
0x18001f90f  xor     eax, eax
0x18001f911  lock cmpxchg cs:g_hSha1Provider, rcx
0x18001f91a  jz      short loc_18001F92F
0x18001f91c  mov     rcx, [rsp+28h+phAlgorithm]; hAlgorithm
0x18001f921  xor     edx, edx; dwFlags
0x18001f923  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001f92a  nop     dword ptr [rax+rax+00h]
0x18001f92f  mov     rax, cs:g_hSha1Provider
0x18001f936  add     rsp, 28h
0x18001f93a  retn
```

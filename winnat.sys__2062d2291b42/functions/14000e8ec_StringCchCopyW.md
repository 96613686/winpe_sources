# StringCchCopyW

- ea: `0x14000e8ec`
- end: `0x14000e93b`
- name: `StringCchCopyW`
- size: `79`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bdf0`
- `0x14000f188`
- `0x14000f480`
- `0x14000fb40`
- `0x140010290`
- `0x1400103e0`

## callees

- `0x14000e8ec`

## pseudocode

```c
HRESULT __stdcall StringCchCopyW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // rax
  __int64 v4; // r9
  STRSAFE_LPWSTR v5; // rdx
  HRESULT result; // eax

  v3 = 2147483646;
  v4 = 261;
  do
  {
    if ( !v3 )
      break;
    if ( !*pszSrc )
      break;
    *pszDest++ = *pszSrc++;
    --v3;
    --v4;
  }
  while ( v4 );
  v5 = pszDest - 1;
  result = v4 == 0 ? 0x8007007A : 0;
  if ( v4 )
    v5 = pszDest;
  *v5 = 0;
  return result;
}

```

## disassembly

```asm
0x14000e8ec  mov     eax, 7FFFFFFEh
0x14000e8f1  mov     r9d, 105h
0x14000e8f7  xor     r10d, r10d
0x14000e8fa  test    rax, rax
0x14000e8fd  jz      short loc_14000E91C
0x14000e8ff  movzx   edx, word ptr [r8]
0x14000e903  test    dx, dx
0x14000e906  jz      short loc_14000E91C
0x14000e908  mov     [rcx], dx
0x14000e90b  add     r8, 2
0x14000e90f  add     rcx, 2
0x14000e913  dec     rax
0x14000e916  sub     r9, 1
0x14000e91a  jnz     short loc_14000E8FA
0x14000e91c  mov     rax, r9
0x14000e91f  lea     rdx, [rcx-2]
0x14000e923  neg     rax
0x14000e926  sbb     eax, eax
0x14000e928  not     eax
0x14000e92a  and     eax, 8007007Ah
0x14000e92f  test    r9, r9
0x14000e932  cmovnz  rdx, rcx
0x14000e936  mov     [rdx], r10w
0x14000e93a  retn
```

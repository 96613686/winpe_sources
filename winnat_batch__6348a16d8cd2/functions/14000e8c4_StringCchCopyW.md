# StringCchCopyW

- ea: `0x14000e8c4`
- end: `0x14000e913`
- name: `StringCchCopyW`
- size: `79`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bdf0`
- `0x14000f130`
- `0x14000f428`
- `0x14000fae0`
- `0x140010230`
- `0x140010380`

## callees

- `0x14000e8c4`

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
0x14000e8c4  mov     eax, 7FFFFFFEh
0x14000e8c9  mov     r9d, 105h
0x14000e8cf  xor     r10d, r10d
0x14000e8d2  test    rax, rax
0x14000e8d5  jz      short loc_14000E8F4
0x14000e8d7  movzx   edx, word ptr [r8]
0x14000e8db  test    dx, dx
0x14000e8de  jz      short loc_14000E8F4
0x14000e8e0  mov     [rcx], dx
0x14000e8e3  add     r8, 2
0x14000e8e7  add     rcx, 2
0x14000e8eb  dec     rax
0x14000e8ee  sub     r9, 1
0x14000e8f2  jnz     short loc_14000E8D2
0x14000e8f4  mov     rax, r9
0x14000e8f7  lea     rdx, [rcx-2]
0x14000e8fb  neg     rax
0x14000e8fe  sbb     eax, eax
0x14000e900  not     eax
0x14000e902  and     eax, 8007007Ah
0x14000e907  test    r9, r9
0x14000e90a  cmovnz  rdx, rcx
0x14000e90e  mov     [rdx], r10w
0x14000e912  retn
```

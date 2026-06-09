# StringCbCopyW

- ea: `0x18000e46c`
- end: `0x18000e4c4`
- name: `StringCbCopyW`
- size: `88`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007a00`
- `0x18000e9e0`

## callees

- `0x18000e46c`

## string_xrefs

- `0x18000e471`: `DINPUT.DLL`

## pseudocode

```c
HRESULT __stdcall StringCbCopyW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  __int64 v3; // rax
  wchar_t *v4; // rdx
  __int64 v5; // r8
  STRSAFE_LPWSTR v6; // rdx
  HRESULT result; // eax

  v3 = 2147483646;
  v4 = aDinputDll_0;
  v5 = 32;
  do
  {
    if ( !v3 )
      break;
    if ( !*v4 )
      break;
    *pszDest++ = *v4++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = pszDest - 1;
  result = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v6 = pszDest;
  *v6 = 0;
  return result;
}

```

## disassembly

```asm
0x18000e46c  mov     eax, 7FFFFFFEh
0x18000e471  lea     rdx, aDinputDll_0; "DINPUT.DLL"
0x18000e478  mov     r8d, 20h ; ' '
0x18000e47e  xor     r10d, r10d
0x18000e481  test    rax, rax
0x18000e484  jz      short loc_18000E4A5
0x18000e486  movzx   r9d, word ptr [rdx]
0x18000e48a  test    r9w, r9w
0x18000e48e  jz      short loc_18000E4A5
0x18000e490  mov     [rcx], r9w
0x18000e494  add     rdx, 2
0x18000e498  add     rcx, 2
0x18000e49c  dec     rax
0x18000e49f  sub     r8, 1
0x18000e4a3  jnz     short loc_18000E481
0x18000e4a5  mov     rax, r8
0x18000e4a8  lea     rdx, [rcx-2]
0x18000e4ac  neg     rax
0x18000e4af  sbb     eax, eax
0x18000e4b1  not     eax
0x18000e4b3  and     eax, 8007007Ah
0x18000e4b8  test    r8, r8
0x18000e4bb  cmovnz  rdx, rcx
0x18000e4bf  mov     [rdx], r10w
0x18000e4c3  retn
```

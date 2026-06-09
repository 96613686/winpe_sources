# StringCbCatW

- ea: `0x18000b43c`
- end: `0x18000b4e7`
- name: `StringCbCatW`
- size: `171`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000370c`
- `0x18000c350`
- `0x18000c628`
- `0x180010ffc`
- `0x180021008`
- `0x18002b1e0`

## callees

- `0x18000b43c`

## pseudocode

```c
HRESULT __stdcall StringCbCatW(STRSAFE_LPWSTR pszDest, size_t cbDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v3; // rdx
  __int64 v4; // r10
  size_t v6; // r9
  STRSAFE_LPWSTR v7; // rax
  HRESULT result; // eax
  size_t v9; // rcx
  wchar_t *v10; // rax
  size_t i; // rdx
  wchar_t *v12; // rcx

  v3 = cbDest >> 1;
  v4 = 2147483646;
  if ( v3 - 1 > 0x7FFFFFFE )
    return -2147024809;
  v6 = v3;
  v7 = pszDest;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  result = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
    v9 = v3 - v6;
  else
    v9 = 0;
  if ( v6 )
  {
    v10 = &pszDest[v9];
    for ( i = v3 - v9; i; --i )
    {
      if ( !v4 )
        break;
      if ( !*pszSrc )
        break;
      *v10++ = *pszSrc++;
      --v4;
    }
    v12 = v10 - 1;
    if ( i )
      v12 = v10;
    result = i == 0 ? 0x8007007A : 0;
    *v12 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b43c  mov     [rsp+arg_0], rbx
0x18000b441  shr     rdx, 1
0x18000b444  mov     r10d, 7FFFFFFEh
0x18000b44a  mov     r11, rcx
0x18000b44d  lea     rax, [rdx-1]
0x18000b451  cmp     rax, r10
0x18000b454  ja      loc_18000B4DC
0x18000b45a  mov     r9, rdx
0x18000b45d  mov     rax, rcx
0x18000b460  xor     ebx, ebx
0x18000b462  cmp     [rax], bx
0x18000b465  jz      short loc_18000B471
0x18000b467  add     rax, 2
0x18000b46b  sub     r9, 1
0x18000b46f  jnz     short loc_18000B462
0x18000b471  mov     rax, r9
0x18000b474  neg     rax
0x18000b477  sbb     eax, eax
0x18000b479  not     eax
0x18000b47b  and     eax, 80070057h
0x18000b480  test    r9, r9
0x18000b483  jz      short loc_18000B48D
0x18000b485  mov     rcx, rdx
0x18000b488  sub     rcx, r9
0x18000b48b  jmp     short loc_18000B490
0x18000b48d  mov     rcx, rbx
0x18000b490  test    r9, r9
0x18000b493  jz      short loc_18000B4E1
0x18000b495  lea     rax, [r11+rcx*2]
0x18000b499  sub     rdx, rcx
0x18000b49c  jz      short loc_18000B4C0
0x18000b49e  test    r10, r10
0x18000b4a1  jz      short loc_18000B4C0
0x18000b4a3  movzx   ecx, word ptr [r8]
0x18000b4a7  test    cx, cx
0x18000b4aa  jz      short loc_18000B4C0
0x18000b4ac  mov     [rax], cx
0x18000b4af  add     r8, 2
0x18000b4b3  add     rax, 2
0x18000b4b7  dec     r10
0x18000b4ba  sub     rdx, 1
0x18000b4be  jnz     short loc_18000B49E
0x18000b4c0  lea     rcx, [rax-2]
0x18000b4c4  test    rdx, rdx
0x18000b4c7  cmovnz  rcx, rax
0x18000b4cb  neg     rdx
0x18000b4ce  sbb     eax, eax
0x18000b4d0  not     eax
0x18000b4d2  and     eax, 8007007Ah
0x18000b4d7  mov     [rcx], bx
0x18000b4da  jmp     short loc_18000B4E1
0x18000b4dc  mov     eax, 80070057h
0x18000b4e1  mov     rbx, [rsp+arg_0]
0x18000b4e6  retn
```

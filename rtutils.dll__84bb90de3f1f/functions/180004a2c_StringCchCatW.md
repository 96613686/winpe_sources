# StringCchCatW

- ea: `0x180004a2c`
- end: `0x180004ab1`
- name: `StringCchCatW`
- size: `133`
- prototype: `HRESULT __stdcall(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cc0`
- `0x180006c6c`
- `0x1800070c4`
- `0x1800074e8`
- `0x180007664`
- `0x180007e34`

## callees

- `0x180004a2c`
- `0x180004b60`

## pseudocode

```c
HRESULT __stdcall StringCchCatW(STRSAFE_LPWSTR pszDest, size_t cchDest, STRSAFE_LPCWSTR pszSrc)
{
  size_t v5; // r9
  STRSAFE_LPWSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // r8
  size_t v10; // [rsp+20h] [rbp-18h]

  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v5 = cchDest;
  v6 = pszDest;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0x80070057 : 0;
  if ( v5 )
  {
    v8 = (cchDest - v5) & -(__int64)(v5 != 0);
    return StringCopyWorkerW(&pszDest[v8], cchDest - v8, (size_t *)v8, pszSrc, v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180004a2c  mov     [rsp+arg_0], rbx
0x180004a31  push    rdi
0x180004a32  sub     rsp, 30h
0x180004a36  lea     rax, [rdx-1]
0x180004a3a  mov     rbx, r8
0x180004a3d  mov     r10, rdx
0x180004a40  mov     r11, rcx
0x180004a43  cmp     rax, 7FFFFFFEh
0x180004a49  ja      short loc_180004A9F
0x180004a4b  mov     r9, rdx
0x180004a4e  mov     rax, rcx
0x180004a51  xor     edi, edi
0x180004a53  cmp     [rax], di
0x180004a56  jz      short loc_180004A62
0x180004a58  add     rax, 2
0x180004a5c  sub     r9, 1
0x180004a60  jnz     short loc_180004A53
0x180004a62  mov     rax, r9
0x180004a65  mov     rcx, r10
0x180004a68  neg     rax
0x180004a6b  mov     rax, r9
0x180004a6e  sbb     edx, edx
0x180004a70  sub     rcx, r9
0x180004a73  not     edx
0x180004a75  and     edx, 80070057h
0x180004a7b  neg     rax
0x180004a7e  sbb     r8, r8
0x180004a81  and     r8, rcx; pcchNewDestLength
0x180004a84  test    r9, r9
0x180004a87  jz      short loc_180004AA4
0x180004a89  sub     r10, r8
0x180004a8c  lea     rcx, [r11+r8*2]; pszDest
0x180004a90  mov     rdx, r10; cchDest
0x180004a93  mov     r9, rbx; pszSrc
0x180004a96  call    StringCopyWorkerW
0x180004a9b  mov     edx, eax
0x180004a9d  jmp     short loc_180004AA4
0x180004a9f  mov     edx, 80070057h
0x180004aa4  mov     rbx, [rsp+38h+arg_0]
0x180004aa9  mov     eax, edx
0x180004aab  add     rsp, 30h
0x180004aaf  pop     rdi
0x180004ab0  retn
```

# Iwcstombs

- ea: `0x18000f764`
- end: `0x18000f7fd`
- name: `Iwcstombs`
- size: `153`
- prototype: `__int64 __fastcall(LPSTR lpMultiByteStr, LPCWCH lpWideCharStr, int cbMultiByte)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ed70`
- `0x18000eff0`
- `0x180017100`
- `0x18001a530`
- `0x18001a690`
- `0x18001a8e0`
- `0x18001aa80`

## callees

- `0x18000f764`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f7b5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f7e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f7b5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000f7e5`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000f78e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000f7bf`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000f78e`
- `api-ms-win-core-localization-l1-2-0!GetACP` at `0x18000f7bf`

## pseudocode

```c
int __fastcall Iwcstombs(LPSTR lpMultiByteStr, LPCWCH lpWideCharStr, int cbMultiByte)
{
  __int64 v3; // rax
  int v7; // ebx
  UINT ACP; // eax
  UINT v9; // eax
  int result; // eax

  v3 = -1;
  do
    ++v3;
  while ( lpWideCharStr[v3] );
  v7 = v3 + 1;
  do
  {
    --v7;
    ACP = GetACP();
  }
  while ( WideCharToMultiByte(ACP, 0x400u, lpWideCharStr, v7, 0, 0, 0, 0) >= cbMultiByte );
  v9 = GetACP();
  result = WideCharToMultiByte(v9, 0x400u, lpWideCharStr, v7, lpMultiByteStr, cbMultiByte, 0, 0);
  lpMultiByteStr[result] = 0;
  return result;
}

```

## disassembly

```asm
0x18000f764  push    rbx
0x18000f766  push    rbp
0x18000f767  push    rsi
0x18000f768  push    rdi
0x18000f769  push    r14
0x18000f76b  sub     rsp, 40h
0x18000f76f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f773  mov     esi, r8d
0x18000f776  xor     r14d, r14d
0x18000f779  mov     rdi, rdx
0x18000f77c  mov     rbp, rcx
0x18000f77f  inc     rax
0x18000f782  cmp     [rdx+rax*2], r14w
0x18000f787  jnz     short loc_18000F77F
0x18000f789  lea     ebx, [rax+1]
0x18000f78c  dec     ebx
0x18000f78e  call    cs:__imp_GetACP
0x18000f794  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000f799  mov     r9d, ebx; cchWideChar
0x18000f79c  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x18000f7a1  mov     ecx, eax; CodePage
0x18000f7a3  mov     [rsp+68h+cbMultiByte], r14d; cbMultiByte
0x18000f7a8  mov     r8, rdi; lpWideCharStr
0x18000f7ab  mov     edx, 400h; dwFlags
0x18000f7b0  mov     [rsp+68h+lpMultiByteStr], r14; lpMultiByteStr
0x18000f7b5  call    cs:__imp_WideCharToMultiByte
0x18000f7bb  cmp     eax, esi
0x18000f7bd  jge     short loc_18000F78C
0x18000f7bf  call    cs:__imp_GetACP
0x18000f7c5  mov     [rsp+68h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000f7ca  mov     r9d, ebx; cchWideChar
0x18000f7cd  mov     [rsp+68h+lpDefaultChar], r14; lpDefaultChar
0x18000f7d2  mov     ecx, eax; CodePage
0x18000f7d4  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x18000f7d8  mov     r8, rdi; lpWideCharStr
0x18000f7db  mov     edx, 400h; dwFlags
0x18000f7e0  mov     [rsp+68h+lpMultiByteStr], rbp; lpMultiByteStr
0x18000f7e5  call    cs:__imp_WideCharToMultiByte
0x18000f7eb  movsxd  rcx, eax
0x18000f7ee  mov     [rcx+rbp], r14b
0x18000f7f2  add     rsp, 40h
0x18000f7f6  pop     r14
0x18000f7f8  pop     rdi
0x18000f7f9  pop     rsi
0x18000f7fa  pop     rbp
0x18000f7fb  pop     rbx
0x18000f7fc  retn
```

# UnicodeToAnsi(ushort * const,char * * const)

- ea: `0x18000e770`
- end: `0x18000e81a`
- name: `?UnicodeToAnsi@@YAHQEAGQEAPEAD@Z`
- size: `170`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **const)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012a64`

## callees

- `0x18000e770`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e7a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7e8`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e7d1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000e7d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e809`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e7f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e809`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e7dd`

## pseudocode

```c
__int64 __fastcall UnicodeToAnsi(LPCWCH lpWideCharStr, LPVOID *a2)
{
  __int64 v4; // rax
  int cbMultiByte; // esi
  char *lpMultiByteStr; // rax
  unsigned int v7; // esi
  DWORD LastError; // ebx
  DWORD v10; // ecx

  if ( !lpWideCharStr || !*lpWideCharStr || !a2 )
  {
    v10 = 87;
    goto LABEL_12;
  }
  v4 = -1;
  do
    ++v4;
  while ( lpWideCharStr[v4] );
  cbMultiByte = v4 + 1;
  lpMultiByteStr = (char *)CoTaskMemAlloc((unsigned int)(v4 + 1));
  *a2 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    v10 = 14;
LABEL_12:
    SetLastError(v10);
    return 0;
  }
  v7 = WideCharToMultiByte(0, 0x400u, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0);
  if ( !v7 )
  {
    LastError = GetLastError();
    CoTaskMemFree(*a2);
    *a2 = 0;
    SetLastError(LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x18000e770  push    rbx
0x18000e772  push    rbp
0x18000e773  push    rsi
0x18000e774  push    rdi
0x18000e775  sub     rsp, 48h
0x18000e779  xor     ebp, ebp
0x18000e77b  mov     rdi, rdx
0x18000e77e  mov     rbx, rcx
0x18000e781  test    rcx, rcx
0x18000e784  jz      short loc_18000E804
0x18000e786  cmp     [rcx], bp
0x18000e789  jz      short loc_18000E804
0x18000e78b  test    rdx, rdx
0x18000e78e  jz      short loc_18000E804
0x18000e790  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e794  inc     rax
0x18000e797  cmp     [rcx+rax*2], bp
0x18000e79b  jnz     short loc_18000E794
0x18000e79d  lea     esi, [rax+1]
0x18000e7a0  mov     ecx, esi; cb
0x18000e7a2  call    cs:__imp_CoTaskMemAlloc
0x18000e7a8  mov     [rdi], rax
0x18000e7ab  test    rax, rax
0x18000e7ae  jz      short loc_18000E7FD
0x18000e7b0  mov     [rsp+68h+lpUsedDefaultChar], rbp; lpUsedDefaultChar
0x18000e7b5  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000e7b9  mov     [rsp+68h+lpDefaultChar], rbp; lpDefaultChar
0x18000e7be  mov     r8, rbx; lpWideCharStr
0x18000e7c1  mov     [rsp+68h+cbMultiByte], esi; cbMultiByte
0x18000e7c5  mov     edx, 400h; dwFlags
0x18000e7ca  xor     ecx, ecx; CodePage
0x18000e7cc  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18000e7d1  call    cs:__imp_WideCharToMultiByte
0x18000e7d7  mov     esi, eax
0x18000e7d9  test    eax, eax
0x18000e7db  jnz     short loc_18000E7F9
0x18000e7dd  call    cs:__imp_GetLastError
0x18000e7e3  mov     rcx, [rdi]; pv
0x18000e7e6  mov     ebx, eax
0x18000e7e8  call    cs:__imp_CoTaskMemFree
0x18000e7ee  mov     ecx, ebx; dwErrCode
0x18000e7f0  mov     [rdi], rbp
0x18000e7f3  call    cs:__imp_SetLastError
0x18000e7f9  mov     eax, esi
0x18000e7fb  jmp     short loc_18000E811
0x18000e7fd  mov     ecx, 0Eh
0x18000e802  jmp     short loc_18000E809
0x18000e804  mov     ecx, 57h ; 'W'; dwErrCode
0x18000e809  call    cs:__imp_SetLastError
0x18000e80f  xor     eax, eax
0x18000e811  add     rsp, 48h
0x18000e815  pop     rdi
0x18000e816  pop     rsi
0x18000e817  pop     rbp
0x18000e818  pop     rbx
0x18000e819  retn
```

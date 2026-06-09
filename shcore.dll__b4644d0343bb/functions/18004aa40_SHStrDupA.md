# SHStrDupA

- ea: `0x18004aa40`
- end: `0x18004ab0e`
- name: `SHStrDupA`
- size: `206`
- prototype: `HRESULT __stdcall(LPCSTR psz, LPWSTR *ppwsz)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800356b0`

## callees

- `0x18001abfc`
- `0x18004aa40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aa7c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aad2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aa7c`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18004aad2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aae6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004aab0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004aab0`

## pseudocode

```c
HRESULT __stdcall SHStrDupA(LPCSTR psz, LPWSTR *ppwsz)
{
  int v4; // eax
  unsigned int cchWideChar; // ebx
  unsigned int v6; // eax
  HRESULT Error; // ebx
  unsigned __int64 v9; // rcx
  WCHAR *lpWideCharStr; // rax
  WCHAR *v11; // rdi

  *ppwsz = 0;
  if ( !psz )
    return -2147024809;
  v4 = MultiByteToWideChar(0, 0, psz, -1, 0, 0);
  cchWideChar = v4;
  if ( !v4 )
    return ResultFromLastError();
  v6 = v4 + 1;
  if ( v6 < cchWideChar )
    return -2147024362;
  v9 = 2LL * v6;
  if ( v9 > 0xFFFFFFFF )
    return -2147024362;
  lpWideCharStr = (WCHAR *)CoTaskMemAlloc((unsigned int)v9);
  v11 = lpWideCharStr;
  if ( !lpWideCharStr )
    return -2147024882;
  if ( MultiByteToWideChar(0, 0, psz, -1, lpWideCharStr, cchWideChar) )
  {
    Error = 0;
    *ppwsz = v11;
    v11 = 0;
  }
  else
  {
    Error = ResultFromLastError();
  }
  CoTaskMemFree(v11);
  return Error;
}

```

## disassembly

```asm
0x18004aa40  push    rbx
0x18004aa42  push    rsi
0x18004aa43  push    rdi
0x18004aa44  push    r14
0x18004aa46  sub     rsp, 38h
0x18004aa4a  mov     qword ptr [rdx], 0
0x18004aa51  mov     r14, rdx
0x18004aa54  mov     rsi, rcx
0x18004aa57  test    rcx, rcx
0x18004aa5a  jz      loc_18004AAF7
0x18004aa60  mov     r8, rcx; lpMultiByteStr
0x18004aa63  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x18004aa6b  xor     ecx, ecx; CodePage
0x18004aa6d  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x18004aa76  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18004aa7a  xor     edx, edx; dwFlags
0x18004aa7c  call    cs:__imp_MultiByteToWideChar
0x18004aa82  mov     ebx, eax
0x18004aa84  test    eax, eax
0x18004aa86  jz      short loc_18004AAFE
0x18004aa88  inc     eax
0x18004aa8a  cmp     eax, ebx
0x18004aa8c  jnb     short loc_18004AA9F
0x18004aa8e  mov     ebx, 80070216h
0x18004aa93  mov     eax, ebx
0x18004aa95  add     rsp, 38h
0x18004aa99  pop     r14
0x18004aa9b  pop     rdi
0x18004aa9c  pop     rsi
0x18004aa9d  pop     rbx
0x18004aa9e  retn
0x18004aa9f  mov     ecx, eax
0x18004aaa1  mov     eax, 0FFFFFFFFh
0x18004aaa6  add     rcx, rcx
0x18004aaa9  cmp     rcx, rax
0x18004aaac  ja      short loc_18004AA8E
0x18004aaae  mov     ecx, ecx; cb
0x18004aab0  call    cs:__imp_CoTaskMemAlloc
0x18004aab6  mov     rdi, rax
0x18004aab9  test    rax, rax
0x18004aabc  jz      short loc_18004AB07
0x18004aabe  mov     [rsp+58h+cchWideChar], ebx; cchWideChar
0x18004aac2  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18004aac6  mov     r8, rsi; lpMultiByteStr
0x18004aac9  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18004aace  xor     edx, edx; dwFlags
0x18004aad0  xor     ecx, ecx; CodePage
0x18004aad2  call    cs:__imp_MultiByteToWideChar
0x18004aad8  test    eax, eax
0x18004aada  jz      short loc_18004AAEE
0x18004aadc  xor     ebx, ebx
0x18004aade  mov     [r14], rdi
0x18004aae1  xor     edi, edi
0x18004aae3  mov     rcx, rdi; pv
0x18004aae6  call    cs:__imp_CoTaskMemFree
0x18004aaec  jmp     short loc_18004AA93
0x18004aaee  call    ResultFromLastError
0x18004aaf3  mov     ebx, eax
0x18004aaf5  jmp     short loc_18004AAE3
0x18004aaf7  mov     eax, 80070057h
0x18004aafc  jmp     short loc_18004AA95
0x18004aafe  call    ResultFromLastError
0x18004ab03  mov     ebx, eax
0x18004ab05  jmp     short loc_18004AA93
0x18004ab07  mov     ebx, 8007000Eh
0x18004ab0c  jmp     short loc_18004AA93
```

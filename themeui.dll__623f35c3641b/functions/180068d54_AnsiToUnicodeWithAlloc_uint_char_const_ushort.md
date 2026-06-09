# AnsiToUnicodeWithAlloc(uint,char const *,ushort * *)

- ea: `0x180068d54`
- end: `0x180068df0`
- name: `?AnsiToUnicodeWithAlloc@@YAJIPEBDPEAPEAG@Z`
- size: `156`
- prototype: `__int64 __fastcall(UINT CodePage, LPCCH lpMultiByteStr, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180067e40`
- `0x180067fb0`
- `0x1800693c4`
- `0x180069940`
- `0x180069d70`
- `0x180069ec0`

## callees

- `0x180068d54`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068d7f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068dbb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068d7f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180068dbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180068d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068dd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068dd1`

## pseudocode

```c
__int64 __fastcall AnsiToUnicodeWithAlloc(UINT CodePage, LPCCH lpMultiByteStr, LPVOID *a3)
{
  int v6; // eax
  int cchWideChar; // ebx
  unsigned __int16 *lpWideCharStr; // rax
  unsigned int v9; // ebx

  v6 = MultiByteToWideChar(CodePage, 0, lpMultiByteStr, -1, 0, 0);
  cchWideChar = v6;
  if ( !v6 )
  {
    v9 = -2147467259;
    goto LABEL_8;
  }
  lpWideCharStr = (unsigned __int16 *)CoTaskMemAlloc(2LL * v6);
  *a3 = lpWideCharStr;
  if ( lpWideCharStr )
  {
    if ( MultiByteToWideChar(CodePage, 0, lpMultiByteStr, -1, lpWideCharStr, cchWideChar) )
      return 0;
    v9 = -2147467259;
    CoTaskMemFree(*a3);
LABEL_8:
    *a3 = 0;
    return v9;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180068d54  push    rbx
0x180068d56  push    rbp
0x180068d57  push    rsi
0x180068d58  push    rdi
0x180068d59  sub     rsp, 38h
0x180068d5d  mov     rdi, r8
0x180068d60  mov     [rsp+58h+cchWideChar], 0; cchWideChar
0x180068d68  mov     r8, rdx; lpMultiByteStr
0x180068d6b  mov     [rsp+58h+lpWideCharStr], 0; lpWideCharStr
0x180068d74  mov     rsi, rdx
0x180068d77  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180068d7b  xor     edx, edx; dwFlags
0x180068d7d  mov     ebp, ecx
0x180068d7f  call    cs:__imp_MultiByteToWideChar
0x180068d85  movsxd  rbx, eax
0x180068d88  test    eax, eax
0x180068d8a  jz      short loc_180068DD9
0x180068d8c  mov     rcx, rbx
0x180068d8f  add     rcx, rcx; cb
0x180068d92  call    cs:__imp_CoTaskMemAlloc
0x180068d98  mov     [rdi], rax
0x180068d9b  test    rax, rax
0x180068d9e  jnz     short loc_180068DA7
0x180068da0  mov     ebx, 8007000Eh
0x180068da5  jmp     short loc_180068DE5
0x180068da7  mov     [rsp+58h+cchWideChar], ebx; cchWideChar
0x180068dab  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180068daf  mov     r8, rsi; lpMultiByteStr
0x180068db2  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x180068db7  xor     edx, edx; dwFlags
0x180068db9  mov     ecx, ebp; CodePage
0x180068dbb  call    cs:__imp_MultiByteToWideChar
0x180068dc1  test    eax, eax
0x180068dc3  jz      short loc_180068DC9
0x180068dc5  xor     ebx, ebx
0x180068dc7  jmp     short loc_180068DE5
0x180068dc9  mov     rcx, [rdi]; pv
0x180068dcc  mov     ebx, 80004005h
0x180068dd1  call    cs:__imp_CoTaskMemFree
0x180068dd7  jmp     short loc_180068DDE
0x180068dd9  mov     ebx, 80004005h
0x180068dde  mov     qword ptr [rdi], 0
0x180068de5  mov     eax, ebx
0x180068de7  add     rsp, 38h
0x180068deb  pop     rdi
0x180068dec  pop     rsi
0x180068ded  pop     rbp
0x180068dee  pop     rbx
0x180068def  retn
```

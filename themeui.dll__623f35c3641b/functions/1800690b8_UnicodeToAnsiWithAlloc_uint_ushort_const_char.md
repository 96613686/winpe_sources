# UnicodeToAnsiWithAlloc(uint,ushort const *,char * *)

- ea: `0x1800690b8`
- end: `0x180069173`
- name: `?UnicodeToAnsiWithAlloc@@YAJIPEBGPEAPEAD@Z`
- size: `187`
- prototype: `__int64 __fastcall(UINT CodePage, LPCWCH lpWideCharStr, char **)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800693c4`

## callees

- `0x1800690b8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800690f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006913e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800690f3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006913e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069103`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069103`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069154`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069154`

## pseudocode

```c
__int64 __fastcall UnicodeToAnsiWithAlloc(UINT CodePage, LPCWCH lpWideCharStr, LPVOID *a3)
{
  int v6; // eax
  int cbMultiByte; // ebx
  char *lpMultiByteStr; // rax
  unsigned int v9; // ebx

  v6 = WideCharToMultiByte(CodePage, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( !v6 )
  {
    v9 = -2147467259;
    goto LABEL_8;
  }
  lpMultiByteStr = (char *)CoTaskMemAlloc(v6);
  *a3 = lpMultiByteStr;
  if ( lpMultiByteStr )
  {
    if ( WideCharToMultiByte(CodePage, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
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
0x1800690b8  mov     rax, rsp
0x1800690bb  push    rbx
0x1800690bc  push    rbp
0x1800690bd  push    rsi
0x1800690be  push    rdi
0x1800690bf  sub     rsp, 48h
0x1800690c3  mov     qword ptr [rax-30h], 0
0x1800690cb  mov     rdi, r8
0x1800690ce  mov     qword ptr [rax-38h], 0
0x1800690d6  mov     r8, rdx; lpWideCharStr
0x1800690d9  mov     rsi, rdx
0x1800690dc  mov     dword ptr [rax-40h], 0
0x1800690e3  xor     edx, edx; dwFlags
0x1800690e5  mov     qword ptr [rax-48h], 0
0x1800690ed  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800690f1  mov     ebp, ecx
0x1800690f3  call    cs:__imp_WideCharToMultiByte
0x1800690f9  movsxd  rbx, eax
0x1800690fc  test    eax, eax
0x1800690fe  jz      short loc_18006915C
0x180069100  mov     rcx, rbx; cb
0x180069103  call    cs:__imp_CoTaskMemAlloc
0x180069109  mov     [rdi], rax
0x18006910c  test    rax, rax
0x18006910f  jnz     short loc_180069118
0x180069111  mov     ebx, 8007000Eh
0x180069116  jmp     short loc_180069168
0x180069118  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180069121  or      r9d, 0FFFFFFFFh; cchWideChar
0x180069125  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18006912e  mov     r8, rsi; lpWideCharStr
0x180069131  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x180069135  xor     edx, edx; dwFlags
0x180069137  mov     ecx, ebp; CodePage
0x180069139  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18006913e  call    cs:__imp_WideCharToMultiByte
0x180069144  test    eax, eax
0x180069146  jz      short loc_18006914C
0x180069148  xor     ebx, ebx
0x18006914a  jmp     short loc_180069168
0x18006914c  mov     rcx, [rdi]; pv
0x18006914f  mov     ebx, 80004005h
0x180069154  call    cs:__imp_CoTaskMemFree
0x18006915a  jmp     short loc_180069161
0x18006915c  mov     ebx, 80004005h
0x180069161  mov     qword ptr [rdi], 0
0x180069168  mov     eax, ebx
0x18006916a  add     rsp, 48h
0x18006916e  pop     rdi
0x18006916f  pop     rsi
0x180069170  pop     rbp
0x180069171  pop     rbx
0x180069172  retn
```

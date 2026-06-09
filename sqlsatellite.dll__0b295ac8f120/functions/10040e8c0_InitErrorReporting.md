# InitErrorReporting

- ea: `0x10040e8c0`
- end: `0x10040ea89`
- name: `InitErrorReporting`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x100404a00`

## callees

- `0x10040e8c0`
- `0x100486af0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x10040e9fe`
- `KERNEL32!LoadLibraryW` at `0x10040e9fe`
- `KERNEL32!GetModuleFileNameW` at `0x10040e8f2`
- `KERNEL32!GetModuleFileNameW` at `0x10040e8f2`
- `KERNEL32!GetLastError` at `0x10040e8fc`
- `KERNEL32!GetLastError` at `0x10040e937`
- `KERNEL32!GetLastError` at `0x10040ea0d`
- `KERNEL32!GetLastError` at `0x10040e8fc`
- `KERNEL32!GetLastError` at `0x10040e937`
- `KERNEL32!GetLastError` at `0x10040ea0d`
- `sqldk!?SetErrorReportingManager@@YAXPEAVIErrorReportingManager@@@Z` at `0x10040ea2b`
- `sqldk!?SetErrorReportingManager@@YAXPEAVIErrorReportingManager@@@Z` at `0x10040ea2b`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x10040ea31`
- `VCRUNTIME140!wcsrchr` at `0x10040e929`
- `VCRUNTIME140!wcsrchr` at `0x10040e929`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
signed int __fastcall InitErrorReporting(struct IErrorReportingManager *a1, HMODULE a2)
{
  signed int result; // eax
  wchar_t *v4; // rax
  wchar_t *v5; // rsi
  __int64 v6; // rcx
  WCHAR *v7; // rax
  int v8; // edi
  __int64 v9; // rax
  WCHAR *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  char *v13; // r8
  WCHAR v14; // dx
  WCHAR *v15; // rax
  HMODULE LibraryW; // rax
  wchar_t Filename[264]; // [rsp+20h] [rbp-238h] BYREF

  if ( !GetModuleFileNameW(a2, Filename, 0x104u) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v4 = wcsrchr(Filename, 0x5Cu);
  v5 = v4;
  if ( !v4 )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v6 = 260;
  *v4 = 0;
  v7 = Filename;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v6;
  }
  while ( v6 );
  v8 = -2147024809;
  v9 = 260 - v6;
  if ( !v6 )
    goto LABEL_23;
  v10 = &Filename[v9];
  v11 = 260 - v9;
  if ( 260 != v9 )
  {
    v12 = 2147483646;
    v13 = (char *)((char *)L"\\resources\\1033\\sqlevn70.rll" - (char *)v10);
    do
    {
      if ( !v12 )
        break;
      v14 = *(WCHAR *)((char *)v10 + (_QWORD)v13);
      if ( !v14 )
        break;
      *v10 = v14;
      --v12;
      ++v10;
      --v11;
    }
    while ( v11 );
  }
  v15 = v10 - 1;
  v8 = -2147024774;
  if ( v11 )
  {
    v15 = v10;
    v8 = 0;
  }
  *v15 = 0;
  if ( !v11 )
  {
LABEL_23:
    _mm_lfence();
    return v8;
  }
  LibraryW = LoadLibraryW(Filename);
  *((_QWORD *)a1 + 1) = LibraryW;
  if ( LibraryW )
  {
    _mm_lfence();
    *v5 = 0;
    SetErrorReportingManager(a1);
    s_pServerConf = (struct IServerConfiguration *)&off_1004EDE70;
    qword_1004EE0B0 = (__int64)qword_100556EA0;
    return v8;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x10040e8c0  push    rbx
0x10040e8c2  push    rbp
0x10040e8c3  sub     rsp, 248h
0x10040e8ca  mov     rax, cs:__security_cookie
0x10040e8d1  xor     rax, rsp
0x10040e8d4  mov     [rsp+258h+var_28], rax
0x10040e8dc  mov     rax, rdx
0x10040e8df  mov     rbp, rcx
0x10040e8e2  mov     ebx, 104h
0x10040e8e7  lea     rdx, [rsp+258h+Filename]; lpFilename
0x10040e8ec  mov     r8d, ebx; nSize
0x10040e8ef  mov     rcx, rax; hModule
0x10040e8f2  call    cs:__imp_GetModuleFileNameW
0x10040e8f8  test    eax, eax
0x10040e8fa  jnz     short loc_10040E917
0x10040e8fc  call    cs:__imp_GetLastError
0x10040e902  test    eax, eax
0x10040e904  jle     loc_10040EA6F
0x10040e90a  movzx   eax, ax
0x10040e90d  or      eax, 80070000h
0x10040e912  jmp     loc_10040EA6F
0x10040e917  mov     edx, 5Ch ; '\'; Ch
0x10040e91c  mov     [rsp+258h+arg_10], rsi
0x10040e924  lea     rcx, [rsp+258h+Filename]; Str
0x10040e929  call    cs:__imp_wcsrchr
0x10040e92f  mov     rsi, rax
0x10040e932  test    rax, rax
0x10040e935  jnz     short loc_10040E952
0x10040e937  call    cs:__imp_GetLastError
0x10040e93d  test    eax, eax
0x10040e93f  jle     loc_10040EA67
0x10040e945  movzx   eax, ax
0x10040e948  or      eax, 80070000h
0x10040e94d  jmp     loc_10040EA67
0x10040e952  mov     [rsp+258h+arg_18], rdi
0x10040e95a  mov     rcx, rbx
0x10040e95d  mov     [rsp+258h+var_18], r14
0x10040e965  xor     r14d, r14d
0x10040e968  mov     [rax], r14w
0x10040e96c  lea     rax, [rsp+258h+Filename]
0x10040e971  cmp     [rax], r14w
0x10040e975  jz      short loc_10040E981
0x10040e977  add     rax, 2
0x10040e97b  sub     rcx, 1
0x10040e97f  jnz     short loc_10040E971
0x10040e981  mov     rax, rbx
0x10040e984  mov     edi, 80070057h
0x10040e989  sub     rax, rcx
0x10040e98c  test    rcx, rcx
0x10040e98f  cmovz   rax, r14
0x10040e993  cmovnz  edi, r14d
0x10040e997  jz      loc_10040EA52
0x10040e99d  lea     rcx, [rsp+258h+Filename]
0x10040e9a2  lea     rcx, [rcx+rax*2]
0x10040e9a6  sub     rbx, rax
0x10040e9a9  jz      short loc_10040E9DF
0x10040e9ab  lea     r8, aResources1033S; "\\resources\\1033\\sqlevn70.rll"
0x10040e9b2  mov     eax, 7FFFFFFEh
0x10040e9b7  sub     r8, rcx
0x10040e9ba  nop     word ptr [rax+rax+00h]
0x10040e9c0  test    rax, rax
0x10040e9c3  jz      short loc_10040E9DF
0x10040e9c5  movzx   edx, word ptr [r8+rcx]
0x10040e9ca  test    dx, dx
0x10040e9cd  jz      short loc_10040E9DF
0x10040e9cf  mov     [rcx], dx
0x10040e9d2  dec     rax
0x10040e9d5  add     rcx, 2
0x10040e9d9  sub     rbx, 1
0x10040e9dd  jnz     short loc_10040E9C0
0x10040e9df  test    rbx, rbx
0x10040e9e2  lea     rax, [rcx-2]
0x10040e9e6  mov     edi, 8007007Ah
0x10040e9eb  cmovnz  rax, rcx
0x10040e9ef  cmovnz  edi, r14d
0x10040e9f3  mov     [rax], r14w
0x10040e9f7  jz      short loc_10040EA52
0x10040e9f9  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x10040e9fe  call    cs:__imp_LoadLibraryW
0x10040ea04  mov     [rbp+8], rax
0x10040ea08  test    rax, rax
0x10040ea0b  jnz     short loc_10040EA21
0x10040ea0d  call    cs:__imp_GetLastError
0x10040ea13  test    eax, eax
0x10040ea15  jle     short loc_10040EA57
0x10040ea17  movzx   eax, ax
0x10040ea1a  or      eax, 80070000h
0x10040ea1f  jmp     short loc_10040EA57
0x10040ea21  lfence
0x10040ea24  mov     rcx, rbp
0x10040ea27  mov     [rsi], r14w
0x10040ea2b  call    cs:__imp_?SetErrorReportingManager@@YAXPEAVIErrorReportingManager@@@Z; SetErrorReportingManager(IErrorReportingManager *)
0x10040ea31  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x10040ea38  lea     rax, off_1004EDE70
0x10040ea3f  mov     [rcx], rax
0x10040ea42  lea     rax, qword_100556EA0
0x10040ea49  mov     cs:qword_1004EE0B0, rax
0x10040ea50  jmp     short loc_10040EA55
0x10040ea52  lfence
0x10040ea55  mov     eax, edi
0x10040ea57  mov     rdi, [rsp+258h+arg_18]
0x10040ea5f  mov     r14, [rsp+258h+var_18]
0x10040ea67  mov     rsi, [rsp+258h+arg_10]
0x10040ea6f  mov     rcx, [rsp+258h+var_28]
0x10040ea77  xor     rcx, rsp; StackCookie
0x10040ea7a  call    __security_check_cookie
0x10040ea7f  add     rsp, 248h
0x10040ea86  pop     rbp
0x10040ea87  pop     rbx
0x10040ea88  retn
```

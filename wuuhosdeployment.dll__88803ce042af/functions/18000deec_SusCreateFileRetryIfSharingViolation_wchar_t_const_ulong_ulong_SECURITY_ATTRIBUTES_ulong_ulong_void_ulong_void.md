# SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)

- ea: `0x18000deec`
- end: `0x18000e054`
- name: `?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z`
- size: `360`
- prototype: `void *__usercall@<rax>(LPCWSTR lpFileName@<rcx>, DWORD dwDesiredAccess@<edx>, DWORD dwShareMode@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, DWORD, DWORD, void *, unsigned int, void *, int, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000cea8`
- `0x180011034`
- `0x180015670`
- `0x18002f194`

## callees

- `0x18000956c`
- `0x18000deec`
- `0x18000eba0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000df65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfaf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e028`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000e028`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000df94`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000df94`

## string_xrefs

- `0x18000dfe1`: `CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)`
- `0x18000dfec`: `SusCreateFileRetryIfSharingViolation`

## pseudocode

```c
void *__fastcall SusCreateFileRetryIfSharingViolation(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        struct _SECURITY_ATTRIBUTES *a4,
        DWORD a5,
        DWORD a6,
        void *a7,
        unsigned int a8,
        void *a9,
        int a10,
        unsigned int a11)
{
  unsigned int v11; // r12d
  DWORD dwCreationDisposition; // r13d
  int v16; // esi
  signed int v17; // ebx
  void *v18; // rdi
  signed int LastError; // eax
  int v20; // eax
  struct _SECURITY_ATTRIBUTES *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  void *FileW; // [rsp+98h] [rbp+20h] BYREF

  v11 = a6;
  dwCreationDisposition = a5;
  FileW = (void *)-1LL;
  v16 = 0;
  while ( 1 )
  {
    if ( a10 )
    {
      v17 = SafeCreateFile(
              &FileW,
              a11,
              lpFileName,
              dwDesiredAccess,
              dwShareMode,
              dwFlagsAndAttributes,
              dwCreationDisposition,
              v11);
      SetLastError(v17);
      v18 = FileW;
    }
    else
    {
      FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, dwCreationDisposition, v11, 0);
      v18 = FileW;
      if ( FileW != (void *)-1LL )
        return v18;
      LastError = GetLastError();
      v17 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v17 = LastError;
      if ( v17 >= 0 )
        v17 = -2147418113;
    }
    if ( v17 != -2147024891 && v17 != -2147024864 )
      break;
    dwFlagsAndAttributes = (struct _SECURITY_ATTRIBUTES *)L"CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)";
    WUTrace("SusCreateFileRetryIfSharingViolation", 1921, 32, 3);
    v20 = v16++;
    if ( v20 == 10 )
      break;
    Sleep(0x1F4u);
  }
  return v18;
}

```

## disassembly

```asm
0x18000deec  mov     rax, rsp
0x18000deef  mov     [rax+8], rbx
0x18000def3  mov     [rax+10h], rbp
0x18000def7  mov     [rax+18h], rsi
0x18000defb  mov     [rax+20h], r9
0x18000deff  push    rdi
0x18000df00  push    r12
0x18000df02  push    r13
0x18000df04  push    r14
0x18000df06  push    r15
0x18000df08  sub     rsp, 50h
0x18000df0c  mov     r12d, [rsp+78h+arg_28]
0x18000df14  mov     ebp, r8d
0x18000df17  mov     r13d, [rsp+78h+arg_20]
0x18000df1f  mov     r14d, edx
0x18000df22  mov     r15, rcx
0x18000df25  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x18000df2d  xor     esi, esi
0x18000df2f  cmp     [rsp+78h+arg_48], 0
0x18000df37  jz      short loc_18000DF75
0x18000df39  mov     edx, [rsp+78h+arg_50]; unsigned int
0x18000df40  lea     rcx, [rsp+78h+arg_18]; void **
0x18000df48  mov     [rsp+78h+var_40], r12d; unsigned int
0x18000df4d  mov     r9d, r14d; unsigned int
0x18000df50  mov     dword ptr [rsp+78h+hTemplateFile], r13d; unsigned int
0x18000df55  mov     r8, r15; wchar_t *
0x18000df58  mov     [rsp+78h+dwCreationDisposition], ebp; unsigned int
0x18000df5c  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x18000df61  mov     ecx, eax; dwErrCode
0x18000df63  mov     ebx, eax
0x18000df65  call    cs:__imp_SetLastError
0x18000df6b  mov     rdi, [rsp+78h+arg_18]
0x18000df73  jmp     short loc_18000DFCD
0x18000df75  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18000df7e  xor     r9d, r9d; lpSecurityAttributes
0x18000df81  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18000df86  mov     r8d, ebp; dwShareMode
0x18000df89  mov     edx, r14d; dwDesiredAccess
0x18000df8c  mov     [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x18000df91  mov     rcx, r15; lpFileName
0x18000df94  call    cs:__imp_CreateFileW
0x18000df9a  mov     [rsp+78h+arg_18], rax
0x18000dfa2  mov     rdi, rax
0x18000dfa5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000dfa9  jnz     loc_18000E033
0x18000dfaf  call    cs:__imp_GetLastError
0x18000dfb5  movzx   ebx, ax
0x18000dfb8  or      ebx, 80070000h
0x18000dfbe  test    eax, eax
0x18000dfc0  cmovle  ebx, eax
0x18000dfc3  mov     eax, 8000FFFFh
0x18000dfc8  test    ebx, ebx
0x18000dfca  cmovns  ebx, eax
0x18000dfcd  cmp     ebx, 80070005h
0x18000dfd3  jz      short loc_18000DFDD
0x18000dfd5  cmp     ebx, 80070020h
0x18000dfdb  jnz     short loc_18000E033
0x18000dfdd  mov     [rsp+78h+var_30], esi
0x18000dfe1  lea     rax, aCreatefileWsAc; "CreateFile %ws (Access = %lu, Share = %"...
0x18000dfe8  mov     [rsp+78h+var_38], ebp
0x18000dfec  lea     rcx, aSuscreatefiler; "SusCreateFileRetryIfSharingViolation"
0x18000dff3  mov     [rsp+78h+var_40], r14d
0x18000dff8  mov     r9d, 3
0x18000dffe  mov     [rsp+78h+hTemplateFile], r15
0x18000e003  mov     edx, 781h
0x18000e008  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x18000e00d  mov     [rsp+78h+dwCreationDisposition], ebx
0x18000e011  lea     r8d, [r9+1Dh]
0x18000e015  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18000e01a  mov     eax, esi
0x18000e01c  inc     esi
0x18000e01e  cmp     eax, 0Ah
0x18000e021  jz      short loc_18000E033
0x18000e023  mov     ecx, 1F4h; dwMilliseconds
0x18000e028  call    cs:__imp_Sleep
0x18000e02e  jmp     loc_18000DF2F
0x18000e033  lea     r11, [rsp+78h+var_28]
0x18000e038  mov     rax, rdi
0x18000e03b  mov     rbx, [r11+30h]
0x18000e03f  mov     rbp, [r11+38h]
0x18000e043  mov     rsi, [r11+40h]
0x18000e047  mov     rsp, r11
0x18000e04a  pop     r15
0x18000e04c  pop     r14
0x18000e04e  pop     r13
0x18000e050  pop     r12
0x18000e052  pop     rdi
0x18000e053  retn
```

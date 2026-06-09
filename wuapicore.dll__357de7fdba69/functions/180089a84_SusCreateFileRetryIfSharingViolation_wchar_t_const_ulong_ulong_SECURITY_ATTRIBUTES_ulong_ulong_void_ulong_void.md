# SusCreateFileRetryIfSharingViolation(wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *,ulong,void *,int,ulong)

- ea: `0x180089a84`
- end: `0x180089bec`
- name: `?SusCreateFileRetryIfSharingViolation@@YAPEAXPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAXK2HK@Z`
- size: `360`
- prototype: `void *__usercall@<rax>(LPCWSTR lpFileName@<rcx>, DWORD dwDesiredAccess@<edx>, DWORD dwShareMode@<r8d>, struct _SECURITY_ATTRIBUTES *@<r9>, DWORD, DWORD, void *, unsigned int, void *, int, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008985c`
- `0x180089f44`
- `0x180098470`

## callees

- `0x180089a84`
- `0x180090bc8`
- `0x1800951dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089afd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089afd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089b47`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180089bc0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180089bc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180089b2c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180089b2c`

## string_xrefs

- `0x180089b79`: `CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)`
- `0x180089b84`: `SusCreateFileRetryIfSharingViolation`

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
  DWORD v13; // r13d
  int v16; // esi
  signed int v17; // ebx
  void *v18; // rdi
  signed int LastError; // eax
  int v20; // eax
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-58h]
  struct _SECURITY_ATTRIBUTES *dwFlagsAndAttributes; // [rsp+28h] [rbp-50h]
  void *FileW; // [rsp+98h] [rbp+20h] BYREF

  v11 = a6;
  v13 = a5;
  FileW = (void *)-1LL;
  v16 = 0;
  while ( 1 )
  {
    if ( a10 )
    {
      v17 = SafeCreateFile(&FileW, a11, lpFileName, dwDesiredAccess, dwShareMode, dwFlagsAndAttributes, v13, v11);
      SetLastError(v17);
      v18 = FileW;
    }
    else
    {
      FileW = CreateFileW(lpFileName, dwDesiredAccess, dwShareMode, 0, v13, v11, 0);
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
    LODWORD(dwCreationDisposition) = v17;
    WUTrace(
      "SusCreateFileRetryIfSharingViolation",
      1921,
      32,
      3,
      dwCreationDisposition,
      L"CreateFile %ws (Access = %lu, Share = %lu)(retry %u ...)");
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
0x180089a84  mov     rax, rsp
0x180089a87  mov     [rax+8], rbx
0x180089a8b  mov     [rax+10h], rbp
0x180089a8f  mov     [rax+18h], rsi
0x180089a93  mov     [rax+20h], r9
0x180089a97  push    rdi
0x180089a98  push    r12
0x180089a9a  push    r13
0x180089a9c  push    r14
0x180089a9e  push    r15
0x180089aa0  sub     rsp, 50h
0x180089aa4  mov     r12d, [rsp+78h+arg_28]
0x180089aac  mov     ebp, r8d
0x180089aaf  mov     r13d, [rsp+78h+arg_20]
0x180089ab7  mov     r14d, edx
0x180089aba  mov     r15, rcx
0x180089abd  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180089ac5  xor     esi, esi
0x180089ac7  cmp     [rsp+78h+arg_48], 0
0x180089acf  jz      short loc_180089B0D
0x180089ad1  mov     edx, [rsp+78h+arg_50]; unsigned int
0x180089ad8  lea     rcx, [rsp+78h+arg_18]; void **
0x180089ae0  mov     [rsp+78h+var_40], r12d; unsigned int
0x180089ae5  mov     r9d, r14d; unsigned int
0x180089ae8  mov     dword ptr [rsp+78h+hTemplateFile], r13d; unsigned int
0x180089aed  mov     r8, r15; wchar_t *
0x180089af0  mov     dword ptr [rsp+78h+dwCreationDisposition], ebp; unsigned int
0x180089af4  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x180089af9  mov     ecx, eax; dwErrCode
0x180089afb  mov     ebx, eax
0x180089afd  call    cs:__imp_SetLastError
0x180089b03  mov     rdi, [rsp+78h+arg_18]
0x180089b0b  jmp     short loc_180089B65
0x180089b0d  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180089b16  xor     r9d, r9d; lpSecurityAttributes
0x180089b19  mov     [rsp+78h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180089b1e  mov     r8d, ebp; dwShareMode
0x180089b21  mov     edx, r14d; dwDesiredAccess
0x180089b24  mov     dword ptr [rsp+78h+dwCreationDisposition], r13d; dwCreationDisposition
0x180089b29  mov     rcx, r15; lpFileName
0x180089b2c  call    cs:__imp_CreateFileW
0x180089b32  mov     [rsp+78h+arg_18], rax
0x180089b3a  mov     rdi, rax
0x180089b3d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180089b41  jnz     loc_180089BCB
0x180089b47  call    cs:__imp_GetLastError
0x180089b4d  movzx   ebx, ax
0x180089b50  or      ebx, 80070000h
0x180089b56  test    eax, eax
0x180089b58  cmovle  ebx, eax
0x180089b5b  mov     eax, 8000FFFFh
0x180089b60  test    ebx, ebx
0x180089b62  cmovns  ebx, eax
0x180089b65  cmp     ebx, 80070005h
0x180089b6b  jz      short loc_180089B75
0x180089b6d  cmp     ebx, 80070020h
0x180089b73  jnz     short loc_180089BCB
0x180089b75  mov     [rsp+78h+var_30], esi
0x180089b79  lea     rax, aCreatefileWsAc; "CreateFile %ws (Access = %lu, Share = %"...
0x180089b80  mov     [rsp+78h+var_38], ebp
0x180089b84  lea     rcx, aSuscreatefiler; "SusCreateFileRetryIfSharingViolation"
0x180089b8b  mov     [rsp+78h+var_40], r14d
0x180089b90  mov     r9d, 3
0x180089b96  mov     [rsp+78h+hTemplateFile], r15
0x180089b9b  mov     edx, 781h
0x180089ba0  mov     qword ptr [rsp+78h+dwFlagsAndAttributes], rax
0x180089ba5  mov     dword ptr [rsp+78h+dwCreationDisposition], ebx
0x180089ba9  lea     r8d, [r9+1Dh]
0x180089bad  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180089bb2  mov     eax, esi
0x180089bb4  inc     esi
0x180089bb6  cmp     eax, 0Ah
0x180089bb9  jz      short loc_180089BCB
0x180089bbb  mov     ecx, 1F4h; dwMilliseconds
0x180089bc0  call    cs:__imp_Sleep
0x180089bc6  jmp     loc_180089AC7
0x180089bcb  lea     r11, [rsp+78h+var_28]
0x180089bd0  mov     rax, rdi
0x180089bd3  mov     rbx, [r11+30h]
0x180089bd7  mov     rbp, [r11+38h]
0x180089bdb  mov     rsi, [r11+40h]
0x180089bdf  mov     rsp, r11
0x180089be2  pop     r15
0x180089be4  pop     r14
0x180089be6  pop     r13
0x180089be8  pop     r12
0x180089bea  pop     rdi
0x180089beb  retn
```

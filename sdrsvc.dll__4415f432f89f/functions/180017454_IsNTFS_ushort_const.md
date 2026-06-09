# IsNTFS(ushort const *)

- ea: `0x180017454`
- end: `0x1800175fc`
- name: `?IsNTFS@@YAJPEBG@Z`
- size: `424`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1800148dc`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180017454`
- `0x18001c58c`
- `0x18001c61c`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017590`
- `msvcrt!_wcsicmp` at `0x180017590`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800175c6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017510`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180017510`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001755d`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001755d`

## pseudocode

```c
__int64 __fastcall IsNTFS(LPCWSTR lpFileName)
{
  __int16 v2; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v4; // rcx
  HANDLE FileW; // rdi
  unsigned int v6; // eax
  __int16 v7; // ax
  int v9; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v10; // [rsp+44h] [rbp-BCh]
  __int16 v11; // [rsp+46h] [rbp-BAh]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  int FsInformation; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v14[8]; // [rsp+94h] [rbp-6Ch] BYREF
  wchar_t String1[266]; // [rsp+9Ch] [rbp-64h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "IsNTFS", 134, 1);
  FsInformation = 0;
  IoStatusBlock = 0;
  memset_0(v14, 0, 0x214u);
  v2 = 139;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v9 = -2147024809;
LABEL_3:
    v11 = v2;
    goto LABEL_14;
  }
  v9 = 0;
  v10 = 139;
  FileW = CreateFileW(lpFileName, 0x1000A0u, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
    v9 = LastFailureAsHRESULT;
    v2 = 142;
    goto LABEL_3;
  }
  v9 = 0;
  v10 = 142;
  v6 = NtQueryVolumeInformationFile(FileW, &IoStatusBlock, &FsInformation, 0x218u, FileFsAttributeInformation);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v6);
  v9 = LastFailureAsHRESULT;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v10 = 144;
    if ( _wcsicmp(String1, L"NTFS") )
    {
      v9 = 1;
      v7 = 150;
      LastFailureAsHRESULT = 1;
    }
    else
    {
      v9 = 0;
      LastFailureAsHRESULT = 0;
      v7 = 147;
    }
    v10 = v7;
  }
  else
  {
    v11 = 144;
  }
  if ( FileW )
    CloseHandle(FileW);
LABEL_14:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180017454  mov     [rsp-8+arg_8], rbx
0x180017459  mov     [rsp-8+arg_10], rdi
0x18001745e  push    rbp
0x18001745f  lea     rbp, [rsp-1C0h]
0x180017467  sub     rsp, 2C0h
0x18001746e  mov     rax, cs:__security_cookie
0x180017475  xor     rax, rsp
0x180017478  mov     [rbp+1C0h+var_10], rax
0x18001747f  mov     rbx, rcx
0x180017482  lea     rdx, aIsntfs; "IsNTFS"
0x180017489  lea     rcx, [rsp+2C0h+var_280]; this
0x18001748e  mov     r9d, 1; unsigned __int16
0x180017494  mov     r8d, 86h; unsigned __int16
0x18001749a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001749f  xorps   xmm0, xmm0
0x1800174a2  mov     [rbp+1C0h+FsInformation], 0
0x1800174a9  xor     edx, edx; Val
0x1800174ab  lea     rcx, [rbp+1C0h+var_22C]; void *
0x1800174af  mov     r8d, 214h; Size
0x1800174b5  movups  xmmword ptr [rsp+2C0h+IoStatusBlock], xmm0
0x1800174ba  call    memset_0
0x1800174bf  mov     eax, 8Bh
0x1800174c4  test    rbx, rbx
0x1800174c7  jnz     short loc_1800174DC
0x1800174c9  mov     ebx, 80070057h
0x1800174ce  mov     [rsp+2C0h+var_280], ebx
0x1800174d2  mov     [rsp+2C0h+var_27A], ax
0x1800174d7  jmp     loc_1800175CC
0x1800174dc  mov     [rsp+2C0h+hTemplateFile], 0; hTemplateFile
0x1800174e5  mov     r8d, 3; dwShareMode
0x1800174eb  mov     [rsp+2C0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800174f3  xor     r9d, r9d; lpSecurityAttributes
0x1800174f6  mov     edx, 1000A0h; dwDesiredAccess
0x1800174fb  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180017500  mov     rcx, rbx; lpFileName
0x180017503  mov     [rsp+2C0h+var_280], 0
0x18001750b  mov     [rsp+2C0h+var_27C], ax
0x180017510  call    cs:__imp_CreateFileW
0x180017516  mov     rdi, rax
0x180017519  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001751d  jnz     short loc_180017531
0x18001751f  call    GetLastFailureAsHRESULT
0x180017524  mov     ebx, eax
0x180017526  mov     [rsp+2C0h+var_280], eax
0x18001752a  mov     eax, 8Eh
0x18001752f  jmp     short loc_1800174D2
0x180017531  mov     eax, 8Eh
0x180017536  mov     [rsp+2C0h+var_280], 0
0x18001753e  mov     r9d, 218h; Length
0x180017544  mov     [rsp+2C0h+var_27C], ax
0x180017549  lea     r8, [rbp+1C0h+FsInformation]; FsInformation
0x18001754d  mov     [rsp+2C0h+dwCreationDisposition], 5; FsInformationClass
0x180017555  lea     rdx, [rsp+2C0h+IoStatusBlock]; IoStatusBlock
0x18001755a  mov     rcx, rdi; FileHandle
0x18001755d  call    cs:__imp_NtQueryVolumeInformationFile
0x180017563  mov     ecx, eax
0x180017565  call    HRESULTFromNTSTATUS
0x18001756a  mov     ebx, eax
0x18001756c  mov     [rsp+2C0h+var_280], eax
0x180017570  test    eax, eax
0x180017572  mov     eax, 90h
0x180017577  jns     short loc_180017580
0x180017579  mov     [rsp+2C0h+var_27A], ax
0x18001757e  jmp     short loc_1800175BE
0x180017580  lea     rdx, aNtfs; "NTFS"
0x180017587  mov     [rsp+2C0h+var_27C], ax
0x18001758c  lea     rcx, [rbp+1C0h+String1]; String1
0x180017590  call    cs:__imp__wcsicmp
0x180017596  test    eax, eax
0x180017598  jnz     short loc_1800175A7
0x18001759a  mov     [rsp+2C0h+var_280], eax
0x18001759e  xor     ebx, ebx
0x1800175a0  mov     eax, 93h
0x1800175a5  jmp     short loc_1800175B9
0x1800175a7  mov     [rsp+2C0h+var_280], 1
0x1800175af  mov     eax, 96h
0x1800175b4  mov     ebx, 1
0x1800175b9  mov     [rsp+2C0h+var_27C], ax
0x1800175be  test    rdi, rdi
0x1800175c1  jz      short loc_1800175CC
0x1800175c3  mov     rcx, rdi; hObject
0x1800175c6  call    cs:__imp_CloseHandle
0x1800175cc  lea     rcx, [rsp+2C0h+var_280]; this
0x1800175d1  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800175d6  mov     eax, ebx
0x1800175d8  mov     rcx, [rbp+1C0h+var_10]
0x1800175df  xor     rcx, rsp; StackCookie
0x1800175e2  call    __security_check_cookie
0x1800175e7  lea     r11, [rsp+2C0h+var_s0]
0x1800175ef  mov     rbx, [r11+18h]
0x1800175f3  mov     rdi, [r11+20h]
0x1800175f7  mov     rsp, r11
0x1800175fa  pop     rbp
0x1800175fb  retn
```

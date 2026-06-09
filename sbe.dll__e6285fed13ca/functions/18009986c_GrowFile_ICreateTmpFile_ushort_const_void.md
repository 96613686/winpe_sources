# GrowFile::ICreateTmpFile(ushort const *,void * *)

- ea: `0x18009986c`
- end: `0x180099990`
- name: `?ICreateTmpFile@GrowFile@@AEAAJPEBGPEAPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(GrowFile *__hidden this, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180099b08`

## callees

- `0x180001c00`
- `0x180002ed4`
- `0x1800627f0`
- `0x18009986c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800998b8`
- `KERNEL32!GetCurrentThreadId` at `0x1800998b8`
- `KERNEL32!GetLastError` at `0x18009993a`
- `KERNEL32!GetLastError` at `0x18009993a`
- `KERNEL32!GetCurrentProcessId` at `0x1800998c0`
- `KERNEL32!GetCurrentProcessId` at `0x1800998c0`
- `KERNEL32!CreateFileW` at `0x18009992b`
- `KERNEL32!CreateFileW` at `0x18009992b`

## pseudocode

```c
__int64 __fastcall GrowFile::ICreateTmpFile(GrowFile *this, const unsigned __int16 *a2, void **a3)
{
  unsigned int v6; // ebx
  struct CEhEventTracer *v7; // rcx
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  int v10; // eax
  HANDLE FileW; // rax
  signed int LastError; // eax
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-250h]
  DWORD hTemplateFile; // [rsp+30h] [rbp-248h]
  WCHAR FileName[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a3 )
  {
    v6 = -2147024809;
    v7 = (GrowFile *)((char *)this + 168);
    v8 = -2147024809;
    v9 = 775;
LABEL_10:
    SBEBasicTracers::EtwTraceError(v7, "multimedia\\dshow\\filters\\sbe\\sal\\growfile.cpp", v9, v8);
    return v6;
  }
  hTemplateFile = GetCurrentThreadId();
  dwFlagsAndAttributes = GetCurrentProcessId();
  v10 = StringCchPrintfW(
          FileName,
          0x104u,
          L"%s%s_%x_%x.tmp.sbf",
          (char *)this + 792,
          a2,
          dwFlagsAndAttributes,
          hTemplateFile);
  v6 = v10;
  if ( v10 < 0 )
  {
    v8 = v10;
    v9 = 777;
LABEL_9:
    v7 = (GrowFile *)((char *)this + 168);
    goto LABEL_10;
  }
  FileW = CreateFileW(FileName, 0xC0000000, 7u, 0, 2u, 0x24000180u, 0);
  *a3 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v8 = v6;
    v9 = 792;
    goto LABEL_9;
  }
  return v6;
}

```

## disassembly

```asm
0x18009986c  mov     [rsp+arg_18], rbx
0x180099871  push    rbp
0x180099872  push    rsi
0x180099873  push    rdi
0x180099874  sub     rsp, 260h
0x18009987b  mov     rax, cs:__security_cookie
0x180099882  xor     rax, rsp
0x180099885  mov     [rsp+278h+var_28], rax
0x18009988d  mov     rsi, r8
0x180099890  mov     rbp, rdx
0x180099893  mov     rdi, rcx
0x180099896  test    r8, r8
0x180099899  jnz     short loc_1800998B8
0x18009989b  mov     ebx, 80070057h
0x1800998a0  add     rcx, 0A8h
0x1800998a7  mov     r9d, 80070057h
0x1800998ad  mov     r8d, 307h
0x1800998b3  jmp     loc_18009995F
0x1800998b8  call    cs:__imp_GetCurrentThreadId
0x1800998be  mov     ebx, eax
0x1800998c0  call    cs:__imp_GetCurrentProcessId
0x1800998c6  mov     [rsp+278h+hTemplateFile], ebx
0x1800998ca  lea     r9, [rdi+318h]
0x1800998d1  mov     [rsp+278h+dwFlagsAndAttributes], eax
0x1800998d5  lea     r8, aSSXXTmpSbf; "%s%s_%x_%x.tmp.sbf"
0x1800998dc  mov     edx, 104h; unsigned __int64
0x1800998e1  mov     qword ptr [rsp+278h+dwCreationDisposition], rbp
0x1800998e6  lea     rcx, [rsp+278h+FileName]; Buffer
0x1800998eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800998f0  mov     ebx, eax
0x1800998f2  test    eax, eax
0x1800998f4  jns     short loc_180099901
0x1800998f6  mov     r9d, eax
0x1800998f9  mov     r8d, 309h
0x1800998ff  jmp     short loc_180099958
0x180099901  xor     r9d, r9d; lpSecurityAttributes
0x180099904  mov     qword ptr [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18009990d  mov     [rsp+278h+dwFlagsAndAttributes], 24000180h; dwFlagsAndAttributes
0x180099915  lea     rcx, [rsp+278h+FileName]; lpFileName
0x18009991a  mov     edx, 0C0000000h; dwDesiredAccess
0x18009991f  mov     [rsp+278h+dwCreationDisposition], 2; dwCreationDisposition
0x180099927  lea     r8d, [r9+7]; dwShareMode
0x18009992b  call    cs:__imp_CreateFileW
0x180099931  mov     [rsi], rax
0x180099934  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180099938  jnz     short loc_18009996B
0x18009993a  call    cs:__imp_GetLastError
0x180099940  mov     ebx, eax
0x180099942  test    eax, eax
0x180099944  jle     short loc_18009994F
0x180099946  movzx   ebx, ax
0x180099949  or      ebx, 80070000h
0x18009994f  mov     r9d, ebx; unsigned int
0x180099952  mov     r8d, 318h; unsigned int
0x180099958  lea     rcx, [rdi+0A8h]; struct CEhEventTracer *
0x18009995f  lea     rdx, aMultimediaDsho_1; "multimedia\\dshow\\filters\\sbe\\sal\\g"...
0x180099966  call    ?EtwTraceError@SBEBasicTracers@@SAXAEAVCEhEventTracer@@PEBDKK@Z; SBEBasicTracers::EtwTraceError(CEhEventTracer &,char const *,ulong,ulong)
0x18009996b  mov     eax, ebx
0x18009996d  mov     rcx, [rsp+278h+var_28]
0x180099975  xor     rcx, rsp; StackCookie
0x180099978  call    __security_check_cookie
0x18009997d  mov     rbx, [rsp+278h+arg_18]
0x180099985  add     rsp, 260h
0x18009998c  pop     rdi
0x18009998d  pop     rsi
0x18009998e  pop     rbp
0x18009998f  retn
```

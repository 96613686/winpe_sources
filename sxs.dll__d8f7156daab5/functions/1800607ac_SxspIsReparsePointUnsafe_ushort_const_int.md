# SxspIsReparsePointUnsafe(ushort const *,int *)

- ea: `0x1800607ac`
- end: `0x1800609bd`
- name: `?SxspIsReparsePointUnsafe@@YAHPEBGPEAH@Z`
- size: `529`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002aa40`
- `0x180053760`

## callees

- `0x18000a804`
- `0x18000c000`
- `0x18000df40`
- `0x18000dffc`
- `0x18001c270`
- `0x180046ed4`
- `0x18005d2b0`
- `0x1800607ac`
- `0x180060bc0`
- `0x18006a110`

## import_xrefs

- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x180060959`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x180060959`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060865`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800608c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060837`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060865`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800608c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060892`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180060892`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060976`
- `KERNEL32!DeviceIoControl` at `0x1800608fc`
- `KERNEL32!DeviceIoControl` at `0x1800608fc`

## string_xrefs

- `0x18006092a`: `SxspIsReparsePointUnsafe`
- `0x180060931`: `SXS.DLL: %s(): DevoiceIoControl on file %S returned 0-sized buffer; bad filter driver? Letting through, but beware deadlocks!\n`

## pseudocode

```c
__int64 __fastcall SxspIsReparsePointUnsafe(LPCWSTR lpFileName, int *a2)
{
  const char *v4; // rcx
  HANDLE FileW; // rdi
  _DWORD *v6; // r14
  unsigned int v7; // ebx
  LPVOID lpOutBuffer; // [rsp+40h] [rbp-19h] BYREF
  char v10; // [rsp+48h] [rbp-11h]
  int v11; // [rsp+50h] [rbp-9h] BYREF
  DWORD BytesReturned; // [rsp+54h] [rbp-5h] BYREF
  int v13; // [rsp+58h] [rbp-1h] BYREF
  __int64 v14; // [rsp+60h] [rbp+7h]
  __int64 *v15; // [rsp+68h] [rbp+Fh]
  __int64 v16; // [rsp+70h] [rbp+17h]
  int v17; // [rsp+78h] [rbp+1Fh]
  int *v18; // [rsp+80h] [rbp+27h]

  v13 = 1;
  v15 = &qword_180075390;
  v16 = 544438355;
  v18 = &v11;
  v11 = 0;
  v14 = 0;
  v17 = 3073;
  CFrame::BaseEnter((CFrame *)&v13);
  lpOutBuffer = 0;
  v10 = 0;
  BytesReturned = 0;
  if ( lpFileName )
  {
    if ( !a2 )
    {
      v17 = 3081;
      goto LABEL_3;
    }
    *a2 = 1;
    SetLastError(0);
    FileW = CreateFileW(lpFileName, 0, 7u, 0, 3u, 0x2200000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      FusionpTraceWin32LastErrorFailureOrigination((const struct _CALL_SITE_INFO *)off_180075370);
      goto LABEL_18;
    }
    CSmartPtrBase<unsigned char,CSmartArrayPtr<unsigned char>,CSmartPtrBaseTypeHelper<unsigned char>>::Win32AllocateArrayBase(&lpOutBuffer);
    v6 = lpOutBuffer;
    SetLastError(0);
    if ( !DeviceIoControl(FileW, 0x900A8u, 0, 0, v6, 0x4000u, &BytesReturned, 0) )
    {
      *v18 = 0;
      FusionpTraceWin32LastErrorFailure((const struct _CALL_SITE_INFO *)off_180075350);
LABEL_17:
      CloseHandle(FileW);
      goto LABEL_18;
    }
    if ( BytesReturned )
    {
      if ( *v6 != -2147483641
        && *v6 != -2147483629
        && !(unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed((unsigned int)*v6) )
      {
        goto LABEL_16;
      }
    }
    else
    {
      FusionpDbgPrintEx(
        0xC0000000,
        "SXS.DLL: %s(): DevoiceIoControl on file %S returned 0-sized buffer; bad filter driver? Letting through, but beware deadlocks!\n",
        "SxspIsReparsePointUnsafe",
        lpFileName);
    }
    *a2 = 0;
LABEL_16:
    v11 = 1;
    goto LABEL_17;
  }
  v17 = 3080;
LABEL_3:
  FusionpTraceParameterCheck(v4);
  SetLastError(0x57u);
  *v18 = 0;
LABEL_18:
  v7 = v11;
  CSmartArrayPtr<unsigned char>::~CSmartArrayPtr<unsigned char>(&lpOutBuffer);
  CFnTracerWin32::~CFnTracerWin32((CFnTracerWin32 *)&v13);
  return v7;
}

```

## disassembly

```asm
0x1800607ac  mov     [rsp-8+arg_10], rbx
0x1800607b1  push    rbp
0x1800607b2  push    rsi
0x1800607b3  push    rdi
0x1800607b4  push    r14
0x1800607b6  push    r15
0x1800607b8  lea     rbp, [rsp-37h]
0x1800607bd  sub     rsp, 90h
0x1800607c4  mov     rax, cs:__security_cookie
0x1800607cb  xor     rax, rsp
0x1800607ce  mov     [rbp+57h+var_28], rax
0x1800607d2  lea     rax, qword_180075390
0x1800607d9  mov     [rbp+57h+var_58], 1
0x1800607e0  mov     [rbp+57h+var_48], rax
0x1800607e4  mov     rsi, rcx
0x1800607e7  lea     rax, [rbp+57h+var_60]
0x1800607eb  mov     [rbp+57h+var_40], 20737853h
0x1800607f3  xor     r15d, r15d
0x1800607f6  mov     [rbp+57h+var_30], rax
0x1800607fa  lea     rcx, [rbp+57h+var_58]; this
0x1800607fe  mov     [rbp+57h+var_60], r15d
0x180060802  mov     rbx, rdx
0x180060805  mov     [rbp+57h+var_50], r15
0x180060809  mov     [rbp+57h+var_38], 0C01h
0x180060810  call    ?BaseEnter@CFrame@@QEAAXXZ; CFrame::BaseEnter(void)
0x180060815  mov     [rbp+57h+lpOutBuffer], r15
0x180060819  mov     [rbp+57h+var_68], r15b
0x18006081d  mov     [rbp+57h+BytesReturned], r15d
0x180060821  test    rsi, rsi
0x180060824  jnz     short loc_18006084F
0x180060826  mov     [rbp+57h+var_38], 0C08h
0x18006082d  call    ?FusionpTraceParameterCheck@@YAXPEBD@Z; FusionpTraceParameterCheck(char const *)
0x180060832  mov     ecx, 57h ; 'W'; dwErrCode
0x180060837  call    cs:__imp_SetLastError
0x18006083e  nop     dword ptr [rax+rax+00h]
0x180060843  mov     rax, [rbp+57h+var_30]
0x180060847  mov     [rax], r15d
0x18006084a  jmp     loc_180060982
0x18006084f  test    rbx, rbx
0x180060852  jnz     short loc_18006085D
0x180060854  mov     [rbp+57h+var_38], 0C09h
0x18006085b  jmp     short loc_18006082D
0x18006085d  xor     ecx, ecx; dwErrCode
0x18006085f  mov     dword ptr [rbx], 1
0x180060865  call    cs:__imp_SetLastError
0x18006086c  nop     dword ptr [rax+rax+00h]
0x180060871  xor     r9d, r9d; lpSecurityAttributes
0x180060874  mov     [rsp+0B0h+hTemplateFile], r15; hTemplateFile
0x180060879  mov     [rsp+0B0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180060881  xor     edx, edx; dwDesiredAccess
0x180060883  mov     rcx, rsi; lpFileName
0x180060886  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18006088e  lea     r8d, [r9+7]; dwShareMode
0x180060892  call    cs:__imp_CreateFileW
0x180060899  nop     dword ptr [rax+rax+00h]
0x18006089e  mov     rdi, rax
0x1800608a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800608a5  jnz     short loc_1800608B8
0x1800608a7  lea     rcx, off_180075370; struct _CALL_SITE_INFO *
0x1800608ae  call    ?FusionpTraceWin32LastErrorFailureOrigination@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailureOrigination(_CALL_SITE_INFO const &)
0x1800608b3  jmp     loc_180060982
0x1800608b8  lea     rcx, [rbp+57h+lpOutBuffer]
0x1800608bc  call    ?Win32AllocateArrayBase@?$CSmartPtrBase@EV?$CSmartArrayPtr@E@@V?$CSmartPtrBaseTypeHelper@E@@@@IEAAH_KPEBDH@Z; CSmartPtrBase<uchar,CSmartArrayPtr<uchar>,CSmartPtrBaseTypeHelper<uchar>>::Win32AllocateArrayBase(unsigned __int64,char const *,int)
0x1800608c1  mov     r14, [rbp+57h+lpOutBuffer]
0x1800608c5  xor     ecx, ecx; dwErrCode
0x1800608c7  call    cs:__imp_SetLastError
0x1800608ce  nop     dword ptr [rax+rax+00h]
0x1800608d3  mov     [rsp+0B0h+lpOverlapped], r15; lpOverlapped
0x1800608d8  lea     rax, [rbp+57h+BytesReturned]
0x1800608dc  mov     [rsp+0B0h+hTemplateFile], rax; lpBytesReturned
0x1800608e1  xor     r9d, r9d; nInBufferSize
0x1800608e4  mov     [rsp+0B0h+dwFlagsAndAttributes], 4000h; nOutBufferSize
0x1800608ec  xor     r8d, r8d; lpInBuffer
0x1800608ef  mov     edx, 900A8h; dwIoControlCode
0x1800608f4  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r14; lpOutBuffer
0x1800608f9  mov     rcx, rdi; hDevice
0x1800608fc  call    cs:__imp_DeviceIoControl
0x180060903  nop     dword ptr [rax+rax+00h]
0x180060908  test    eax, eax
0x18006090a  jnz     short loc_180060921
0x18006090c  mov     rax, [rbp+57h+var_30]
0x180060910  lea     rcx, off_180075350; struct _CALL_SITE_INFO *
0x180060917  mov     [rax], r15d
0x18006091a  call    ?FusionpTraceWin32LastErrorFailure@@YAXAEBU_CALL_SITE_INFO@@@Z; FusionpTraceWin32LastErrorFailure(_CALL_SITE_INFO const &)
0x18006091f  jmp     short loc_180060973
0x180060921  cmp     [rbp+57h+BytesReturned], r15d
0x180060925  jnz     short loc_180060944
0x180060927  mov     r9, rsi
0x18006092a  lea     r8, aSxspisreparsep; "SxspIsReparsePointUnsafe"
0x180060931  lea     rdx, aSxsDllSDevoice; "SXS.DLL: %s(): DevoiceIoControl on file"...
0x180060938  mov     ecx, 0C0000000h; unsigned int
0x18006093d  call    ?FusionpDbgPrintEx@@YAKKPEBDZZ; FusionpDbgPrintEx(ulong,char const *,...)
0x180060942  jmp     short loc_180060969
0x180060944  cmp     dword ptr [r14], 80000007h
0x18006094b  jz      short loc_180060969
0x18006094d  cmp     dword ptr [r14], 80000013h
0x180060954  jz      short loc_180060969
0x180060956  mov     ecx, [r14]
0x180060959  call    cs:__imp_RtlIsNonEmptyDirectoryReparsePointAllowed
0x180060960  nop     dword ptr [rax+rax+00h]
0x180060965  test    al, al
0x180060967  jz      short loc_18006096C
0x180060969  mov     [rbx], r15d
0x18006096c  mov     [rbp+57h+var_60], 1
0x180060973  mov     rcx, rdi; hObject
0x180060976  call    cs:__imp_CloseHandle
0x18006097d  nop     dword ptr [rax+rax+00h]
0x180060982  mov     ebx, [rbp+57h+var_60]
0x180060985  lea     rcx, [rbp+57h+lpOutBuffer]
0x180060989  call    ??1?$CSmartArrayPtr@E@@QEAA@XZ; CSmartArrayPtr<uchar>::~CSmartArrayPtr<uchar>(void)
0x18006098e  lea     rcx, [rbp+57h+var_58]; this
0x180060992  call    ??1CFnTracerWin32@@QEAA@XZ; CFnTracerWin32::~CFnTracerWin32(void)
0x180060997  mov     eax, ebx
0x180060999  mov     rcx, [rbp+57h+var_28]
0x18006099d  xor     rcx, rsp; StackCookie
0x1800609a0  call    __security_check_cookie
0x1800609a5  mov     rbx, [rsp+0B0h+arg_10]
0x1800609ad  add     rsp, 90h
0x1800609b4  pop     r15
0x1800609b6  pop     r14
0x1800609b8  pop     rdi
0x1800609b9  pop     rsi
0x1800609ba  pop     rbp
0x1800609bb  retn
```

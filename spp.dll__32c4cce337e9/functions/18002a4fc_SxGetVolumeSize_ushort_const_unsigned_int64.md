# SxGetVolumeSize(ushort const *,unsigned __int64 *)

- ea: `0x18002a4fc`
- end: `0x18002a770`
- name: `?SxGetVolumeSize@@YAJPEBGPEA_K@Z`
- size: `628`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180028ee8`

## callees

- `0x180001b98`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180026cf4`
- `0x18002a4fc`
- `0x18002d6e8`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18002a66e`
- `KERNEL32!CreateFileW` at `0x18002a66e`
- `KERNEL32!DeviceIoControl` at `0x18002a6d6`
- `KERNEL32!DeviceIoControl` at `0x18002a6d6`
- `KERNEL32!CloseHandle` at `0x18002a733`
- `KERNEL32!CloseHandle` at `0x18002a733`

## pseudocode

```c
__int64 __fastcall SxGetVolumeSize(const unsigned __int16 *a1, unsigned __int64 *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int16 v6; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  HANDLE FileW; // rdi
  __int64 v11; // rcx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  __int64 OutBuffer; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v16; // [rsp+54h] [rbp-ACh]
  __int16 v17; // [rsp+56h] [rbp-AAh]
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "SxGetVolumeSize", 1260, 1);
  memset_0(FileName, 0, 0x20Au);
  OutBuffer = 0;
  BytesReturned = 0;
  if ( a2 )
    *a2 = 0;
  v6 = 1271;
  if ( !a1 || (v16 = 1271, v6 = 1272, !a2) )
  {
    LastFailureAsHRESULT = -2147024809;
    v15 = -2147024809;
LABEL_8:
    v17 = v6;
    goto LABEL_29;
  }
  v16 = 1272;
  LastFailureAsHRESULT = StringCchCopyW(FileName, 0x105u, a1);
  v15 = LastFailureAsHRESULT;
  v6 = 1277;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_8;
  v16 = 1277;
  v8 = -1;
  do
    ++v8;
  while ( FileName[v8] );
  if ( !(_DWORD)v8 )
  {
    LastFailureAsHRESULT = -2147024809;
    v17 = 1280;
    v15 = -2147024809;
    goto LABEL_29;
  }
  v16 = 1280;
  v15 = 0;
  if ( FileName[(unsigned int)(v8 - 1)] == 92 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)(v8 - 1) >= 0x20A )
      _report_rangecheckfailure();
    FileName[(unsigned int)(v8 - 1)] = 0;
  }
  FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
    v15 = LastFailureAsHRESULT;
    v6 = 1297;
    goto LABEL_8;
  }
  v16 = 1297;
  v15 = 0;
  if ( DeviceIoControl(FileW, 0x7405Cu, 0, 0, &OutBuffer, 8u, &BytesReturned, 0) )
  {
    v16 = 1303;
    if ( OutBuffer >= 0 )
    {
      LastFailureAsHRESULT = 0;
      v16 = 1309;
      *a2 = OutBuffer;
    }
    else
    {
      LastFailureAsHRESULT = -2147418113;
      v17 = 1309;
    }
    v15 = LastFailureAsHRESULT;
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11);
    v15 = LastFailureAsHRESULT;
    v17 = 1303;
  }
  if ( FileW )
  {
    CloseHandle(FileW);
    LastFailureAsHRESULT = v15;
  }
LABEL_29:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15, v4, v5);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18002a4fc  mov     [rsp-8+arg_10], rbx
0x18002a501  mov     [rsp-8+arg_18], rsi
0x18002a506  push    rbp
0x18002a507  push    rdi
0x18002a508  push    r14
0x18002a50a  lea     rbp, [rsp-1B0h]
0x18002a512  sub     rsp, 2B0h
0x18002a519  mov     rax, cs:__security_cookie
0x18002a520  xor     rax, rsp
0x18002a523  mov     [rbp+1C0h+var_20], rax
0x18002a52a  mov     rsi, rdx
0x18002a52d  mov     rbx, rcx
0x18002a530  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a537  lea     rax, WPP_GLOBAL_Control
0x18002a53e  cmp     rcx, rax
0x18002a541  jz      short loc_18002A561
0x18002a543  test    dword ptr [rcx+1Ch], 20000000h
0x18002a54a  jz      short loc_18002A561
0x18002a54c  mov     rcx, [rcx+10h]
0x18002a550  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002a557  mov     edx, 22h ; '"'
0x18002a55c  call    WPP_SF_
0x18002a561  mov     r9d, 1; unsigned __int16
0x18002a567  lea     rdx, aSxgetvolumesiz; "SxGetVolumeSize"
0x18002a56e  mov     r8d, 4ECh; unsigned __int16
0x18002a574  lea     rcx, [rsp+2C0h+var_270]; this
0x18002a579  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002a57e  mov     edi, 20Ah
0x18002a583  lea     rcx, [rbp+1C0h+FileName]; void *
0x18002a587  mov     r8d, edi; Size
0x18002a58a  xor     edx, edx; Val
0x18002a58c  call    memset_0
0x18002a591  xor     r14d, r14d
0x18002a594  mov     [rsp+2C0h+OutBuffer], r14
0x18002a599  mov     [rsp+2C0h+BytesReturned], r14d
0x18002a59e  test    rsi, rsi
0x18002a5a1  jz      short loc_18002A5A6
0x18002a5a3  mov     [rsi], r14
0x18002a5a6  mov     eax, 4F7h
0x18002a5ab  test    rbx, rbx
0x18002a5ae  jnz     short loc_18002A5C3
0x18002a5b0  mov     ebx, 80070057h
0x18002a5b5  mov     [rsp+2C0h+var_270], ebx
0x18002a5b9  mov     [rsp+2C0h+var_26A], ax
0x18002a5be  jmp     loc_18002A73D
0x18002a5c3  mov     [rsp+2C0h+var_26C], ax
0x18002a5c8  mov     eax, 4F8h
0x18002a5cd  test    rsi, rsi
0x18002a5d0  jz      short loc_18002A5B0
0x18002a5d2  mov     r8, rbx; unsigned __int16 *
0x18002a5d5  mov     [rsp+2C0h+var_26C], ax
0x18002a5da  mov     edx, 105h; unsigned __int64
0x18002a5df  lea     rcx, [rbp+1C0h+FileName]; unsigned __int16 *
0x18002a5e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a5e8  mov     ebx, eax
0x18002a5ea  mov     [rsp+2C0h+var_270], eax
0x18002a5ee  test    eax, eax
0x18002a5f0  mov     eax, 4FDh
0x18002a5f5  js      short loc_18002A5B9
0x18002a5f7  mov     [rsp+2C0h+var_26C], ax
0x18002a5fc  lea     rcx, [rbp+1C0h+FileName]
0x18002a600  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a604  inc     rax
0x18002a607  cmp     [rcx+rax*2], r14w
0x18002a60c  jnz     short loc_18002A604
0x18002a60e  mov     ecx, 500h
0x18002a613  test    eax, eax
0x18002a615  jnz     short loc_18002A62A
0x18002a617  mov     ebx, 80070057h
0x18002a61c  mov     [rsp+2C0h+var_26A], cx
0x18002a621  mov     [rsp+2C0h+var_270], ebx
0x18002a625  jmp     loc_18002A73D
0x18002a62a  mov     [rsp+2C0h+var_26C], cx
0x18002a62f  lea     ecx, [rax-1]
0x18002a632  add     rcx, rcx
0x18002a635  mov     [rsp+2C0h+var_270], r14d
0x18002a63a  cmp     [rbp+rcx+1C0h+FileName], 5Ch ; '\'
0x18002a640  jnz     short loc_18002A64D
0x18002a642  cmp     rcx, rdi
0x18002a645  jnb     short loc_18002A692
0x18002a647  mov     [rbp+rcx+1C0h+FileName], r14w
0x18002a64d  mov     [rsp+2C0h+hTemplateFile], r14; hTemplateFile
0x18002a652  lea     rcx, [rbp+1C0h+FileName]; lpFileName
0x18002a656  mov     r8d, 3; dwShareMode
0x18002a65c  mov     [rsp+2C0h+dwFlagsAndAttributes], r14d; dwFlagsAndAttributes
0x18002a661  xor     r9d, r9d; lpSecurityAttributes
0x18002a664  mov     [rsp+2C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002a669  mov     edx, 80000000h; dwDesiredAccess
0x18002a66e  call    cs:__imp_CreateFileW
0x18002a674  mov     rdi, rax
0x18002a677  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a67b  jnz     short loc_18002A698
0x18002a67d  call    GetLastFailureAsHRESULT
0x18002a682  mov     ebx, eax
0x18002a684  mov     [rsp+2C0h+var_270], eax
0x18002a688  mov     eax, 511h
0x18002a68d  jmp     loc_18002A5B9
0x18002a692  call    __report_rangecheckfailure
0x18002a698  mov     [rsp+2C0h+lpOverlapped], r14; lpOverlapped
0x18002a69d  mov     eax, 511h
0x18002a6a2  mov     [rsp+2C0h+var_26C], ax
0x18002a6a7  xor     r9d, r9d; nInBufferSize
0x18002a6aa  lea     rax, [rsp+2C0h+BytesReturned]
0x18002a6af  mov     [rsp+2C0h+var_270], r14d
0x18002a6b4  mov     [rsp+2C0h+hTemplateFile], rax; lpBytesReturned
0x18002a6b9  xor     r8d, r8d; lpInBuffer
0x18002a6bc  lea     rax, [rsp+2C0h+OutBuffer]
0x18002a6c1  mov     [rsp+2C0h+dwFlagsAndAttributes], 8; nOutBufferSize
0x18002a6c9  mov     edx, 7405Ch; dwIoControlCode
0x18002a6ce  mov     qword ptr [rsp+2C0h+dwCreationDisposition], rax; lpOutBuffer
0x18002a6d3  mov     rcx, rdi; hDevice
0x18002a6d6  call    cs:__imp_DeviceIoControl
0x18002a6dc  test    eax, eax
0x18002a6de  jnz     short loc_18002A6F7
0x18002a6e0  call    GetLastFailureAsHRESULT
0x18002a6e5  mov     ebx, eax
0x18002a6e7  mov     [rsp+2C0h+var_270], eax
0x18002a6eb  mov     eax, 517h
0x18002a6f0  mov     [rsp+2C0h+var_26A], ax
0x18002a6f5  jmp     short loc_18002A72B
0x18002a6f7  mov     eax, 517h
0x18002a6fc  mov     ecx, 51Dh
0x18002a701  mov     [rsp+2C0h+var_26C], ax
0x18002a706  mov     rax, [rsp+2C0h+OutBuffer]
0x18002a70b  test    rax, rax
0x18002a70e  jns     short loc_18002A71C
0x18002a710  mov     ebx, 8000FFFFh
0x18002a715  mov     [rsp+2C0h+var_26A], cx
0x18002a71a  jmp     short loc_18002A727
0x18002a71c  mov     ebx, r14d
0x18002a71f  mov     [rsp+2C0h+var_26C], cx
0x18002a724  mov     [rsi], rax
0x18002a727  mov     [rsp+2C0h+var_270], ebx
0x18002a72b  test    rdi, rdi
0x18002a72e  jz      short loc_18002A73D
0x18002a730  mov     rcx, rdi; hObject
0x18002a733  call    cs:__imp_CloseHandle
0x18002a739  mov     ebx, [rsp+2C0h+var_270]
0x18002a73d  lea     rcx, [rsp+2C0h+var_270]; this
0x18002a742  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a747  mov     eax, ebx
0x18002a749  mov     rcx, [rbp+1C0h+var_20]
0x18002a750  xor     rcx, rsp; StackCookie
0x18002a753  call    __security_check_cookie
0x18002a758  lea     r11, [rsp+2C0h+var_10]
0x18002a760  mov     rbx, [r11+30h]
0x18002a764  mov     rsi, [r11+38h]
0x18002a768  mov     rsp, r11
0x18002a76b  pop     r14
0x18002a76d  pop     rdi
0x18002a76e  pop     rbp
0x18002a76f  retn
```

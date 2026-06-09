# QueryFixedDiskMediaType

- ea: `0x180010800`
- end: `0x180010b2f`
- name: `QueryFixedDiskMediaType`
- size: `815`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task`

## callees

- `0x18000e4a0`
- `0x180010800`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180010914`
- `KERNEL32!CreateFileW` at `0x180010914`
- `KERNEL32!GetLastError` at `0x18001097b`
- `KERNEL32!GetLastError` at `0x18001097b`
- `KERNEL32!CloseHandle` at `0x180010acd`
- `KERNEL32!CloseHandle` at `0x180010acd`
- `KERNEL32!DeviceIoControl` at `0x18001096b`
- `KERNEL32!DeviceIoControl` at `0x180010a06`
- `KERNEL32!DeviceIoControl` at `0x18001096b`
- `KERNEL32!DeviceIoControl` at `0x180010a06`
- `ole32!CoTaskMemFree` at `0x180010aa8`
- `ole32!CoTaskMemFree` at `0x180010aa8`
- `ole32!CoTaskMemAlloc` at `0x1800109be`
- `ole32!CoTaskMemAlloc` at `0x1800109be`

## pseudocode

```c
__int64 __fastcall QueryFixedDiskMediaType(LPCWSTR lpFileName, int *a2, _DWORD *a3, __int64 a4)
{
  int v8; // r15d
  __int64 v9; // rcx
  int *v10; // rax
  __int16 v11; // ax
  unsigned __int64 v12; // rax
  bool v13; // cc
  __int64 v14; // rcx
  HANDLE FileW; // rsi
  __int64 v16; // rcx
  unsigned int LastFailureAsHRESULT; // ebx
  __int16 v18; // ax
  DWORD v19; // edi
  _DWORD *v20; // rbx
  __int64 v21; // rcx
  __int16 v22; // ax
  int v23; // edi
  int v24; // eax
  int v26; // [rsp+40h] [rbp-49h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-45h] BYREF
  int v28; // [rsp+48h] [rbp-41h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-3Dh]
  __int16 v30; // [rsp+4Eh] [rbp-3Bh]
  _OWORD OutBuffer[2]; // [rsp+80h] [rbp-9h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v28, "QueryFixedDiskMediaType", 0x36Cu, 1u);
  v8 = 0;
  v26 = 0;
  memset(OutBuffer, 0, sizeof(OutBuffer));
  BytesReturned = 0;
  if ( a2 )
  {
    v9 = 4;
    v10 = a2;
    do
    {
      *(_BYTE *)v10 = 0;
      v10 = (int *)((char *)v10 + 1);
      --v9;
    }
    while ( v9 );
  }
  v11 = 889;
  if ( !lpFileName )
    goto LABEL_37;
  v29 = 889;
  v12 = -1;
  do
    ++v12;
  while ( lpFileName[v12] );
  v13 = v12 <= 2;
  v11 = 890;
  if ( v13 || (v29 = 890, v11 = 891, !a2) || (v29 = 891, v11 = 892, !a3) || (v29 = 892, v11 = 893, !a4) )
  {
LABEL_37:
    LastFailureAsHRESULT = -2147024809;
    v28 = -2147024809;
    v30 = v11;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 893;
  *a3 = 1;
  FileW = CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v28 = LastFailureAsHRESULT;
    v30 = 904;
    goto LABEL_38;
  }
  v28 = 0;
  v29 = 904;
  if ( DeviceIoControl(FileW, 0x560000u, 0, 0, OutBuffer, 0x20u, &BytesReturned, 0) || GetLastError() == 234 )
  {
    v28 = 0;
    v29 = 915;
    v19 = 24 * LODWORD(OutBuffer[0]) + 8;
    v20 = CoTaskMemAlloc(v19);
    v18 = 920;
    if ( !v20 )
    {
      LastFailureAsHRESULT = -2147024882;
      v28 = -2147024882;
      goto LABEL_33;
    }
    v28 = 0;
    v29 = 920;
    if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v20, v19, &BytesReturned, 0) )
    {
      v28 = 0;
      v29 = 929;
      v22 = 930;
      if ( *v20 )
      {
        v29 = 930;
        v23 = 0;
        if ( *v20 )
        {
          while ( 1 )
          {
            if ( v8 )
              goto LABEL_25;
            v28 = IsDiskHotPluggable(v20[6 * v23 + 2], &v26);
            if ( v28 < 0 )
              break;
            v29 = 934;
            if ( (unsigned int)++v23 >= *v20 )
            {
              if ( !v26 )
                goto LABEL_27;
LABEL_25:
              v24 = 11;
              goto LABEL_28;
            }
            v8 = v26;
          }
          v30 = 934;
        }
        else
        {
LABEL_27:
          v24 = 6;
LABEL_28:
          *a2 = v24;
        }
        goto LABEL_31;
      }
      v28 = -2147418113;
    }
    else
    {
      v28 = GetLastFailureAsHRESULT(v21);
      v22 = 929;
    }
    v30 = v22;
LABEL_31:
    CoTaskMemFree(v20);
    LastFailureAsHRESULT = v28;
    goto LABEL_34;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(v16);
  v28 = LastFailureAsHRESULT;
  v18 = 915;
LABEL_33:
  v30 = v18;
LABEL_34:
  if ( FileW )
    CloseHandle(FileW);
LABEL_38:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180010800  mov     [rsp-8+arg_18], rbx
0x180010805  push    rbp
0x180010806  push    rsi
0x180010807  push    rdi
0x180010808  push    r12
0x18001080a  push    r13
0x18001080c  push    r14
0x18001080e  push    r15
0x180010810  lea     rbp, [rsp-27h]
0x180010815  sub     rsp, 0B0h
0x18001081c  mov     rax, cs:__security_cookie
0x180010823  xor     rax, rsp
0x180010826  mov     [rbp+57h+var_40], rax
0x18001082a  mov     rsi, r9
0x18001082d  mov     rdi, r8
0x180010830  mov     r14, rdx
0x180010833  mov     rbx, rcx
0x180010836  mov     r9d, 1; unsigned __int16
0x18001083c  mov     r8d, 36Ch; unsigned __int16
0x180010842  lea     rdx, aQueryfixeddisk; "QueryFixedDiskMediaType"
0x180010849  lea     rcx, [rbp+57h+var_98]; this
0x18001084d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010852  xor     r12d, r12d
0x180010855  mov     r15d, r12d
0x180010858  mov     [rbp+57h+var_A0], r12d
0x18001085c  xorps   xmm0, xmm0
0x18001085f  movups  [rbp+57h+OutBuffer], xmm0
0x180010863  movups  [rbp+57h+var_50], xmm0
0x180010867  mov     [rbp+57h+BytesReturned], r12d
0x18001086b  test    r14, r14
0x18001086e  jz      short loc_180010884
0x180010870  lea     ecx, [r12+4]
0x180010875  mov     rax, r14
0x180010878  mov     [rax], r12b
0x18001087b  inc     rax
0x18001087e  sub     rcx, 1
0x180010882  jnz     short loc_180010878
0x180010884  mov     eax, 379h
0x180010889  test    rbx, rbx
0x18001088c  jz      loc_180010AF0
0x180010892  mov     [rbp+57h+var_94], ax
0x180010896  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001089a  inc     rax
0x18001089d  cmp     [rbx+rax*2], r12w
0x1800108a2  jnz     short loc_18001089A
0x1800108a4  cmp     rax, 2
0x1800108a8  mov     eax, 37Ah
0x1800108ad  jbe     loc_180010AF0
0x1800108b3  mov     [rbp+57h+var_94], ax
0x1800108b7  mov     eax, 37Bh
0x1800108bc  test    r14, r14
0x1800108bf  jz      loc_180010AF0
0x1800108c5  mov     [rbp+57h+var_94], ax
0x1800108c9  mov     eax, 37Ch
0x1800108ce  test    rdi, rdi
0x1800108d1  jz      loc_180010AF0
0x1800108d7  mov     [rbp+57h+var_94], ax
0x1800108db  mov     eax, 37Dh
0x1800108e0  test    rsi, rsi
0x1800108e3  jz      loc_180010AF0
0x1800108e9  mov     [rbp+57h+var_98], r12d
0x1800108ed  mov     [rbp+57h+var_94], ax
0x1800108f1  mov     dword ptr [rdi], 1
0x1800108f7  mov     [rsp+0E0h+hTemplateFile], r12; hTemplateFile
0x1800108fc  mov     [rsp+0E0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180010901  mov     r8d, 3; dwShareMode
0x180010907  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001090c  xor     r9d, r9d; lpSecurityAttributes
0x18001090f  xor     edx, edx; dwDesiredAccess
0x180010911  mov     rcx, rbx; lpFileName
0x180010914  call    cs:__imp_CreateFileW
0x18001091b  nop     dword ptr [rax+rax+00h]
0x180010920  mov     rsi, rax
0x180010923  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180010927  jz      loc_180010ADB
0x18001092d  mov     [rbp+57h+var_98], r12d
0x180010931  mov     ecx, 388h
0x180010936  mov     [rbp+57h+var_94], cx
0x18001093a  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x18001093f  lea     rax, [rbp+57h+BytesReturned]
0x180010943  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x180010948  mov     [rsp+0E0h+dwFlagsAndAttributes], 20h ; ' '; nOutBufferSize
0x180010950  lea     rax, [rbp+57h+OutBuffer]
0x180010954  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rax; lpOutBuffer
0x180010959  xor     r9d, r9d; nInBufferSize
0x18001095c  xor     r8d, r8d; lpInBuffer
0x18001095f  mov     r13d, 560000h
0x180010965  mov     edx, r13d; dwIoControlCode
0x180010968  mov     rcx, rsi; hDevice
0x18001096b  call    cs:__imp_DeviceIoControl
0x180010972  nop     dword ptr [rax+rax+00h]
0x180010977  test    eax, eax
0x180010979  jnz     short loc_1800109A2
0x18001097b  call    cs:__imp_GetLastError
0x180010982  nop     dword ptr [rax+rax+00h]
0x180010987  cmp     eax, 0EAh
0x18001098c  jz      short loc_1800109A2
0x18001098e  call    GetLastFailureAsHRESULT
0x180010993  mov     ebx, eax
0x180010995  mov     [rbp+57h+var_98], eax
0x180010998  mov     eax, 393h
0x18001099d  jmp     loc_180010AC1
0x1800109a2  mov     [rbp+57h+var_98], r12d
0x1800109a6  mov     eax, 393h
0x1800109ab  mov     [rbp+57h+var_94], ax
0x1800109af  mov     eax, dword ptr [rbp+57h+OutBuffer]
0x1800109b2  lea     ecx, [rax+rax*2]
0x1800109b5  lea     edi, ds:8[rcx*8]
0x1800109bc  mov     ecx, edi; cb
0x1800109be  call    cs:__imp_CoTaskMemAlloc
0x1800109c5  nop     dword ptr [rax+rax+00h]
0x1800109ca  mov     rbx, rax
0x1800109cd  test    rax, rax
0x1800109d0  mov     eax, 398h
0x1800109d5  jz      loc_180010AB9
0x1800109db  mov     [rbp+57h+var_98], r12d
0x1800109df  mov     [rbp+57h+var_94], ax
0x1800109e3  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800109e8  lea     rax, [rbp+57h+BytesReturned]
0x1800109ec  mov     [rsp+0E0h+hTemplateFile], rax; lpBytesReturned
0x1800109f1  mov     [rsp+0E0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1800109f5  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rbx; lpOutBuffer
0x1800109fa  xor     r9d, r9d; nInBufferSize
0x1800109fd  xor     r8d, r8d; lpInBuffer
0x180010a00  mov     edx, r13d; dwIoControlCode
0x180010a03  mov     rcx, rsi; hDevice
0x180010a06  call    cs:__imp_DeviceIoControl
0x180010a0d  nop     dword ptr [rax+rax+00h]
0x180010a12  test    eax, eax
0x180010a14  jnz     short loc_180010A25
0x180010a16  call    GetLastFailureAsHRESULT
0x180010a1b  mov     [rbp+57h+var_98], eax
0x180010a1e  mov     eax, 3A1h
0x180010a23  jmp     short loc_180010AA1
0x180010a25  mov     [rbp+57h+var_98], r12d
0x180010a29  mov     eax, 3A1h
0x180010a2e  mov     [rbp+57h+var_94], ax
0x180010a32  mov     eax, 3A2h
0x180010a37  cmp     [rbx], r12d
0x180010a3a  jz      short loc_180010A9A
0x180010a3c  mov     [rbp+57h+var_94], ax
0x180010a40  mov     edi, r12d
0x180010a43  cmp     [rbx], r12d
0x180010a46  jbe     short loc_180010A90
0x180010a48  lea     r13d, [rax+4]
0x180010a4c  test    r15d, r15d
0x180010a4f  jnz     short loc_180010A82
0x180010a51  mov     eax, edi
0x180010a53  lea     rcx, [rax+rax*2]
0x180010a57  lea     rdx, [rbp+57h+var_A0]
0x180010a5b  mov     ecx, [rbx+rcx*8+8]
0x180010a5f  call    IsDiskHotPluggable
0x180010a64  mov     [rbp+57h+var_98], eax
0x180010a67  test    eax, eax
0x180010a69  js      short loc_180010A89
0x180010a6b  mov     [rbp+57h+var_94], r13w
0x180010a70  inc     edi
0x180010a72  cmp     edi, [rbx]
0x180010a74  jnb     short loc_180010A7C
0x180010a76  mov     r15d, [rbp+57h+var_A0]
0x180010a7a  jmp     short loc_180010A4C
0x180010a7c  cmp     [rbp+57h+var_A0], r12d
0x180010a80  jz      short loc_180010A90
0x180010a82  mov     eax, 0Bh
0x180010a87  jmp     short loc_180010A95
0x180010a89  mov     [rbp+57h+var_92], r13w
0x180010a8e  jmp     short loc_180010AA5
0x180010a90  mov     eax, 6
0x180010a95  mov     [r14], eax
0x180010a98  jmp     short loc_180010AA5
0x180010a9a  mov     [rbp+57h+var_98], 8000FFFFh
0x180010aa1  mov     [rbp+57h+var_92], ax
0x180010aa5  mov     rcx, rbx; pv
0x180010aa8  call    cs:__imp_CoTaskMemFree
0x180010aaf  nop     dword ptr [rax+rax+00h]
0x180010ab4  mov     ebx, [rbp+57h+var_98]
0x180010ab7  jmp     short loc_180010AC5
0x180010ab9  mov     ebx, 8007000Eh
0x180010abe  mov     [rbp+57h+var_98], ebx
0x180010ac1  mov     [rbp+57h+var_92], ax
0x180010ac5  test    rsi, rsi
0x180010ac8  jz      short loc_180010AFC
0x180010aca  mov     rcx, rsi; hObject
0x180010acd  call    cs:__imp_CloseHandle
0x180010ad4  nop     dword ptr [rax+rax+00h]
0x180010ad9  jmp     short loc_180010AFC
0x180010adb  call    GetLastFailureAsHRESULT
0x180010ae0  mov     ebx, eax
0x180010ae2  mov     [rbp+57h+var_98], eax
0x180010ae5  mov     ecx, 388h
0x180010aea  mov     [rbp+57h+var_92], cx
0x180010aee  jmp     short loc_180010AFC
0x180010af0  mov     ebx, 80070057h
0x180010af5  mov     [rbp+57h+var_98], ebx
0x180010af8  mov     [rbp+57h+var_92], ax
0x180010afc  lea     rcx, [rbp+57h+var_98]; this
0x180010b00  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010b05  mov     eax, ebx
0x180010b07  mov     rcx, [rbp+57h+var_40]
0x180010b0b  xor     rcx, rsp; StackCookie
0x180010b0e  call    __security_check_cookie
0x180010b13  mov     rbx, [rsp+0E0h+arg_18]
0x180010b1b  add     rsp, 0B0h
0x180010b22  pop     r15
0x180010b24  pop     r14
0x180010b26  pop     r13
0x180010b28  pop     r12
0x180010b2a  pop     rdi
0x180010b2b  pop     rsi
0x180010b2c  pop     rbp
0x180010b2d  retn
```

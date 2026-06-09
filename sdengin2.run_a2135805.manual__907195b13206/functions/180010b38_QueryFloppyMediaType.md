# QueryFloppyMediaType

- ea: `0x180010b38`
- end: `0x180010e75`
- name: `QueryFloppyMediaType`
- size: `829`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x1800113d0`

## callees

- `0x18000c1f8`
- `0x180010b38`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180010c57`
- `KERNEL32!CreateFileW` at `0x180010c57`
- `KERNEL32!GetLastError` at `0x180010ccb`
- `KERNEL32!GetLastError` at `0x180010ccb`
- `KERNEL32!CloseHandle` at `0x180010e27`
- `KERNEL32!CloseHandle` at `0x180010e27`
- `KERNEL32!DeviceIoControl` at `0x180010cb7`
- `KERNEL32!DeviceIoControl` at `0x180010d6f`
- `KERNEL32!DeviceIoControl` at `0x180010cb7`
- `KERNEL32!DeviceIoControl` at `0x180010d6f`
- `ole32!CoTaskMemFree` at `0x180010d10`
- `ole32!CoTaskMemFree` at `0x180010df2`
- `ole32!CoTaskMemFree` at `0x180010d10`
- `ole32!CoTaskMemFree` at `0x180010df2`
- `ole32!CoTaskMemAlloc` at `0x180010d22`
- `ole32!CoTaskMemAlloc` at `0x180010d22`

## pseudocode

```c
__int64 __fastcall QueryFloppyMediaType(LPCWSTR lpFileName, _BYTE *a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int16 v10; // ax
  char *FileW; // rsi
  void *v12; // rdi
  DWORD v13; // r15d
  signed int LastError; // eax
  signed int LastFailureAsHRESULT; // ebx
  __int16 v16; // ax
  int *p_OutBuffer; // rbx
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  int v21; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v22; // [rsp+4Ch] [rbp-B4h]
  __int16 v23; // [rsp+4Eh] [rbp-B2h]
  int OutBuffer; // [rsp+80h] [rbp-80h] BYREF
  char v25[236]; // [rsp+84h] [rbp-7Ch] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "QueryFloppyMediaType", 0x522u, 1u);
  OutBuffer = 0;
  memset_0(v25, 0, sizeof(v25));
  BytesReturned = 0;
  v20 = 0;
  if ( a2 )
  {
    v8 = 4;
    v9 = a2;
    do
    {
      *v9++ = 0;
      --v8;
    }
    while ( v8 );
  }
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !lpFileName || !*lpFileName )
  {
    v10 = 1330;
LABEL_38:
    LastFailureAsHRESULT = -2147024809;
    v23 = v10;
    v21 = -2147024809;
    goto LABEL_39;
  }
  v22 = 1330;
  v10 = 1331;
  if ( !a2 )
    goto LABEL_38;
  v22 = 1331;
  v10 = 1332;
  if ( !a3 )
    goto LABEL_38;
  v22 = 1332;
  v10 = 1333;
  if ( !a4 )
    goto LABEL_38;
  v21 = 0;
  v22 = 1333;
  *a3 = 0;
  *a4 = 1;
  FileW = (char *)CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(FileW - 1);
    v21 = LastFailureAsHRESULT;
    v23 = 1345;
  }
  else
  {
    v12 = 0;
    v13 = 240;
    v21 = 0;
    v22 = 1345;
    if ( !DeviceIoControl(FileW, 0x2D0C00u, 0, 0, &OutBuffer, 0xF0u, &BytesReturned, 0) )
    {
      while ( 1 )
      {
        LastError = GetLastError();
        LastFailureAsHRESULT = LastError;
        if ( LastError != 122 && LastError != 234 )
        {
          if ( LastError > 0 )
            LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
          v21 = LastFailureAsHRESULT;
          v16 = 1366;
          if ( LastFailureAsHRESULT < 0 )
            goto LABEL_26;
          v22 = 1366;
        }
        if ( v12 )
          CoTaskMemFree(v12);
        v13 *= 2;
        v12 = CoTaskMemAlloc(v13);
        if ( !v12 )
          break;
        v21 = 0;
        v22 = 1381;
        p_OutBuffer = (int *)v12;
        if ( DeviceIoControl(FileW, 0x2D0C00u, 0, 0, v12, v13, &BytesReturned, 0) )
          goto LABEL_29;
      }
      LastFailureAsHRESULT = -2147024882;
      v21 = -2147024882;
      v23 = 1381;
      goto LABEL_36;
    }
    p_OutBuffer = &OutBuffer;
LABEL_29:
    LastFailureAsHRESULT = FindLargestFloppyMediaType(p_OutBuffer, BytesReturned / 0x18uLL, a2, &v20);
    v21 = LastFailureAsHRESULT;
    v16 = 1399;
    if ( LastFailureAsHRESULT < 0 )
    {
LABEL_26:
      v23 = v16;
    }
    else
    {
      v22 = 1399;
      *a4 = v20 == 0;
    }
    if ( v12 )
    {
      CoTaskMemFree(v12);
      LastFailureAsHRESULT = v21;
LABEL_36:
      CloseHandle(FileW);
      goto LABEL_39;
    }
  }
  if ( FileW != (char *)-1LL && FileW )
    goto LABEL_36;
LABEL_39:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180010b38  push    rbp
0x180010b3a  push    rbx
0x180010b3b  push    rsi
0x180010b3c  push    rdi
0x180010b3d  push    r12
0x180010b3f  push    r13
0x180010b41  push    r14
0x180010b43  push    r15
0x180010b45  lea     rbp, [rsp-88h]
0x180010b4d  sub     rsp, 188h
0x180010b54  mov     rax, cs:__security_cookie
0x180010b5b  xor     rax, rsp
0x180010b5e  mov     [rbp+0C0h+var_50], rax
0x180010b62  mov     r14, r9
0x180010b65  mov     rbx, r8
0x180010b68  mov     r12, rdx
0x180010b6b  mov     rdi, rcx
0x180010b6e  mov     r9d, 1; unsigned __int16
0x180010b74  mov     r8d, 522h; unsigned __int16
0x180010b7a  lea     rdx, aQueryfloppymed; "QueryFloppyMediaType"
0x180010b81  lea     rcx, [rsp+1C0h+var_178]; this
0x180010b86  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010b8b  xor     r13d, r13d
0x180010b8e  mov     [rbp+0C0h+OutBuffer], r13d
0x180010b92  xor     edx, edx; Val
0x180010b94  mov     r8d, 0ECh; Size
0x180010b9a  lea     rcx, [rbp+0C0h+var_13C]; void *
0x180010b9e  call    memset_0
0x180010ba3  mov     [rsp+1C0h+BytesReturned], r13d
0x180010ba8  mov     [rsp+1C0h+var_17C], r13d
0x180010bad  test    r12, r12
0x180010bb0  jz      short loc_180010BC5
0x180010bb2  lea     ecx, [r13+4]
0x180010bb6  mov     rax, r12
0x180010bb9  mov     [rax], r13b
0x180010bbc  inc     rax
0x180010bbf  sub     rcx, 1
0x180010bc3  jnz     short loc_180010BB9
0x180010bc5  test    rbx, rbx
0x180010bc8  jz      short loc_180010BCD
0x180010bca  mov     [rbx], r13d
0x180010bcd  test    r14, r14
0x180010bd0  jz      short loc_180010BD5
0x180010bd2  mov     [r14], r13d
0x180010bd5  test    rdi, rdi
0x180010bd8  jz      loc_180010E35
0x180010bde  cmp     [rdi], r13w
0x180010be2  jz      loc_180010E35
0x180010be8  mov     eax, 532h
0x180010bed  mov     [rsp+1C0h+var_174], ax
0x180010bf2  mov     eax, 533h
0x180010bf7  test    r12, r12
0x180010bfa  jz      loc_180010E3A
0x180010c00  mov     [rsp+1C0h+var_174], ax
0x180010c05  mov     eax, 534h
0x180010c0a  test    rbx, rbx
0x180010c0d  jz      loc_180010E3A
0x180010c13  mov     [rsp+1C0h+var_174], ax
0x180010c18  mov     eax, 535h
0x180010c1d  test    r14, r14
0x180010c20  jz      loc_180010E3A
0x180010c26  mov     [rsp+1C0h+var_178], r13d
0x180010c2b  mov     [rsp+1C0h+var_174], ax
0x180010c30  mov     [rbx], r13d
0x180010c33  mov     dword ptr [r14], 1
0x180010c3a  mov     [rsp+1C0h+hTemplateFile], r13; hTemplateFile
0x180010c3f  mov     [rsp+1C0h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180010c44  mov     r8d, 3; dwShareMode
0x180010c4a  mov     [rsp+1C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x180010c4f  xor     r9d, r9d; lpSecurityAttributes
0x180010c52  xor     edx, edx; dwDesiredAccess
0x180010c54  mov     rcx, rdi; lpFileName
0x180010c57  call    cs:__imp_CreateFileW
0x180010c5e  nop     dword ptr [rax+rax+00h]
0x180010c63  mov     rsi, rax
0x180010c66  lea     rcx, [rax-1]
0x180010c6a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180010c6e  ja      loc_180010E04
0x180010c74  mov     rdi, r13
0x180010c77  mov     r15d, 0F0h
0x180010c7d  mov     [rsp+1C0h+var_178], r13d
0x180010c82  mov     eax, 541h
0x180010c87  mov     [rsp+1C0h+var_174], ax
0x180010c8c  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x180010c91  lea     rax, [rsp+1C0h+BytesReturned]
0x180010c96  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180010c9b  mov     [rsp+1C0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180010ca0  lea     rax, [rbp+0C0h+OutBuffer]
0x180010ca4  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rax; lpOutBuffer
0x180010ca9  xor     r9d, r9d; nInBufferSize
0x180010cac  xor     r8d, r8d; lpInBuffer
0x180010caf  mov     edx, 2D0C00h; dwIoControlCode
0x180010cb4  mov     rcx, rsi; hDevice
0x180010cb7  call    cs:__imp_DeviceIoControl
0x180010cbe  nop     dword ptr [rax+rax+00h]
0x180010cc3  test    eax, eax
0x180010cc5  jnz     loc_180010D9F
0x180010ccb  call    cs:__imp_GetLastError
0x180010cd2  nop     dword ptr [rax+rax+00h]
0x180010cd7  mov     ebx, eax
0x180010cd9  cmp     eax, 7Ah ; 'z'
0x180010cdc  jz      short loc_180010D08
0x180010cde  cmp     eax, 0EAh
0x180010ce3  jz      short loc_180010D08
0x180010ce5  test    eax, eax
0x180010ce7  jle     short loc_180010CF2
0x180010ce9  movzx   ebx, ax
0x180010cec  or      ebx, 80070000h
0x180010cf2  mov     [rsp+1C0h+var_178], ebx
0x180010cf6  mov     eax, 556h
0x180010cfb  test    ebx, ebx
0x180010cfd  js      loc_180010D85
0x180010d03  mov     [rsp+1C0h+var_174], ax
0x180010d08  test    rdi, rdi
0x180010d0b  jz      short loc_180010D1C
0x180010d0d  mov     rcx, rdi; pv
0x180010d10  call    cs:__imp_CoTaskMemFree
0x180010d17  nop     dword ptr [rax+rax+00h]
0x180010d1c  add     r15d, r15d
0x180010d1f  mov     ecx, r15d; cb
0x180010d22  call    cs:__imp_CoTaskMemAlloc
0x180010d29  nop     dword ptr [rax+rax+00h]
0x180010d2e  mov     rdi, rax
0x180010d31  test    rax, rax
0x180010d34  mov     eax, 565h
0x180010d39  jz      short loc_180010D8C
0x180010d3b  mov     [rsp+1C0h+var_178], r13d
0x180010d40  mov     [rsp+1C0h+var_174], ax
0x180010d45  mov     rbx, rdi
0x180010d48  mov     [rsp+1C0h+lpOverlapped], r13; lpOverlapped
0x180010d4d  lea     rax, [rsp+1C0h+BytesReturned]
0x180010d52  mov     [rsp+1C0h+hTemplateFile], rax; lpBytesReturned
0x180010d57  mov     [rsp+1C0h+dwFlagsAndAttributes], r15d; nOutBufferSize
0x180010d5c  mov     qword ptr [rsp+1C0h+dwCreationDisposition], rdi; lpOutBuffer
0x180010d61  xor     r9d, r9d; nInBufferSize
0x180010d64  xor     r8d, r8d; lpInBuffer
0x180010d67  mov     edx, 2D0C00h; dwIoControlCode
0x180010d6c  mov     rcx, rsi; hDevice
0x180010d6f  call    cs:__imp_DeviceIoControl
0x180010d76  nop     dword ptr [rax+rax+00h]
0x180010d7b  test    eax, eax
0x180010d7d  jz      loc_180010CCB
0x180010d83  jmp     short loc_180010DA3
0x180010d85  mov     [rsp+1C0h+var_172], ax
0x180010d8a  jmp     short loc_180010DEA
0x180010d8c  mov     ebx, 8007000Eh
0x180010d91  mov     [rsp+1C0h+var_178], ebx
0x180010d95  mov     [rsp+1C0h+var_172], ax
0x180010d9a  jmp     loc_180010E24
0x180010d9f  lea     rbx, [rbp+0C0h+OutBuffer]
0x180010da3  mov     edx, [rsp+1C0h+BytesReturned]
0x180010da7  mov     rax, 0AAAAAAAAAAAAAAABh
0x180010db1  mul     rdx
0x180010db4  shr     rdx, 4
0x180010db8  lea     r9, [rsp+1C0h+var_17C]
0x180010dbd  mov     r8, r12
0x180010dc0  mov     rcx, rbx
0x180010dc3  call    FindLargestFloppyMediaType
0x180010dc8  mov     ebx, eax
0x180010dca  mov     [rsp+1C0h+var_178], eax
0x180010dce  test    eax, eax
0x180010dd0  mov     eax, 577h
0x180010dd5  js      short loc_180010D85
0x180010dd7  mov     [rsp+1C0h+var_174], ax
0x180010ddc  mov     eax, r13d
0x180010ddf  cmp     [rsp+1C0h+var_17C], r13d
0x180010de4  setz    al
0x180010de7  mov     [r14], eax
0x180010dea  test    rdi, rdi
0x180010ded  jz      short loc_180010E19
0x180010def  mov     rcx, rdi; pv
0x180010df2  call    cs:__imp_CoTaskMemFree
0x180010df9  nop     dword ptr [rax+rax+00h]
0x180010dfe  mov     ebx, [rsp+1C0h+var_178]
0x180010e02  jmp     short loc_180010E24
0x180010e04  call    GetLastFailureAsHRESULT
0x180010e09  mov     ebx, eax
0x180010e0b  mov     [rsp+1C0h+var_178], eax
0x180010e0f  mov     eax, 541h
0x180010e14  mov     [rsp+1C0h+var_172], ax
0x180010e19  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180010e1d  jz      short loc_180010E48
0x180010e1f  test    rsi, rsi
0x180010e22  jz      short loc_180010E48
0x180010e24  mov     rcx, rsi; hObject
0x180010e27  call    cs:__imp_CloseHandle
0x180010e2e  nop     dword ptr [rax+rax+00h]
0x180010e33  jmp     short loc_180010E48
0x180010e35  mov     eax, 532h
0x180010e3a  mov     ebx, 80070057h
0x180010e3f  mov     [rsp+1C0h+var_172], ax
0x180010e44  mov     [rsp+1C0h+var_178], ebx
0x180010e48  lea     rcx, [rsp+1C0h+var_178]; this
0x180010e4d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180010e52  mov     eax, ebx
0x180010e54  mov     rcx, [rbp+0C0h+var_50]
0x180010e58  xor     rcx, rsp; StackCookie
0x180010e5b  call    __security_check_cookie
0x180010e60  add     rsp, 188h
0x180010e67  pop     r15
0x180010e69  pop     r14
0x180010e6b  pop     r13
0x180010e6d  pop     r12
0x180010e6f  pop     rdi
0x180010e70  pop     rsi
0x180010e71  pop     rbx
0x180010e72  pop     rbp
0x180010e73  retn
```

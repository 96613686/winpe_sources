# QueryRemovableMediaType

- ea: `0x180010cc0`
- end: `0x1800110d4`
- name: `QueryRemovableMediaType`
- size: `1044`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task`

## callees

- `0x18000c008`
- `0x18000dbc0`
- `0x18000dd30`
- `0x18001048c`
- `0x180010cc0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180010e48`
- `KERNEL32!CreateFileW` at `0x180010e48`
- `KERNEL32!GetLastError` at `0x180010eb0`
- `KERNEL32!GetLastError` at `0x180010eb0`
- `KERNEL32!CloseHandle` at `0x18001108d`
- `KERNEL32!CloseHandle` at `0x18001108d`
- `KERNEL32!DeviceIoControl` at `0x180010ea2`
- `KERNEL32!DeviceIoControl` at `0x180010f62`
- `KERNEL32!DeviceIoControl` at `0x180010ea2`
- `KERNEL32!DeviceIoControl` at `0x180010f62`
- `ole32!CoTaskMemFree` at `0x180010f00`
- `ole32!CoTaskMemFree` at `0x18001105e`
- `ole32!CoTaskMemFree` at `0x180010f00`
- `ole32!CoTaskMemFree` at `0x18001105e`
- `ole32!CoTaskMemAlloc` at `0x180010f12`
- `ole32!CoTaskMemAlloc` at `0x180010f12`

## pseudocode

```c
__int64 __fastcall QueryRemovableMediaType(LPCWSTR lpFileName, _DWORD *a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v8; // rcx
  _BYTE *v9; // rax
  __int16 v10; // ax
  signed int LastFailureAsHRESULT; // ebx
  __int64 v12; // rcx
  char *FileW; // r13
  void *v14; // r12
  signed int LastError; // eax
  __int16 v16; // ax
  int *p_OutBuffer; // rbx
  DWORD nOutBufferSize; // [rsp+40h] [rbp-C0h]
  int v20; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v21; // [rsp+4Ch] [rbp-B4h]
  __int16 v22; // [rsp+4Eh] [rbp-B2h]
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  int v24; // [rsp+84h] [rbp-7Ch] BYREF
  _DWORD *v25; // [rsp+88h] [rbp-78h]
  int OutBuffer; // [rsp+90h] [rbp-70h] BYREF
  char v27[156]; // [rsp+94h] [rbp-6Ch] BYREF

  v25 = a2;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "QueryRemovableMediaType", 1427, 1);
  BytesReturned = 0;
  OutBuffer = 0;
  memset_0(v27, 0, sizeof(v27));
  v24 = 0;
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
    v10 = 1444;
LABEL_47:
    LastFailureAsHRESULT = -2147024809;
    v20 = -2147024809;
    goto LABEL_48;
  }
  v21 = 1444;
  v10 = 1445;
  if ( !a2 )
    goto LABEL_47;
  v21 = 1445;
  v10 = 1446;
  if ( !a3 )
    goto LABEL_47;
  v21 = 1446;
  v10 = 1447;
  if ( !a4 )
    goto LABEL_47;
  v20 = 0;
  v21 = 1447;
  *a3 = 0;
  *a4 = 1;
  LastFailureAsHRESULT = IsDeviceFloppy(lpFileName);
  v20 = LastFailureAsHRESULT;
  v10 = 1458;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_48:
    v22 = v10;
    goto LABEL_49;
  }
  v21 = 1458;
  FileW = (char *)CreateFileW(lpFileName, 0, 3u, 0, 3u, 0, 0);
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v12);
    v20 = LastFailureAsHRESULT;
    v22 = 1481;
    goto LABEL_43;
  }
  v14 = 0;
  nOutBufferSize = 160;
  v20 = 0;
  v21 = 1481;
  if ( DeviceIoControl(FileW, 0x2D0C04u, 0, 0, &OutBuffer, 0xA0u, &BytesReturned, 0) )
  {
    p_OutBuffer = &OutBuffer;
LABEL_35:
    LastFailureAsHRESULT = FindLargestRemovableMediaType(p_OutBuffer, v25, &v24);
    v20 = LastFailureAsHRESULT;
    v16 = 1550;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_32;
    v21 = 1550;
    if ( v24 )
    {
      *a4 = 0;
    }
    else
    {
      *a4 = 1;
      LastFailureAsHRESULT = IsDeviceLockable(lpFileName);
      v20 = LastFailureAsHRESULT;
      v16 = 1562;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_32;
      v21 = 1562;
      *a3 = 1;
      *v25 = 11;
    }
  }
  else
  {
    while ( 1 )
    {
      LastError = GetLastError();
      LastFailureAsHRESULT = LastError;
      if ( LastError == 50 || LastError == 1 )
        break;
      if ( LastError != 122 && LastError != 234 )
      {
        if ( LastError > 0 )
          LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
        v20 = LastFailureAsHRESULT;
        v16 = 1521;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_32;
        v21 = 1521;
      }
      if ( v14 )
        CoTaskMemFree(v14);
      nOutBufferSize *= 2;
      v14 = CoTaskMemAlloc(nOutBufferSize);
      if ( !v14 )
      {
        LastFailureAsHRESULT = -2147024882;
        v20 = -2147024882;
        v22 = 1535;
        goto LABEL_45;
      }
      v20 = 0;
      v21 = 1535;
      p_OutBuffer = (int *)v14;
      if ( DeviceIoControl(FileW, 0x2D0C04u, 0, 0, v14, nOutBufferSize, &BytesReturned, 0) )
        goto LABEL_35;
    }
    LastFailureAsHRESULT = IsDeviceLockable(lpFileName);
    v20 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT < 0 )
    {
      v16 = 1503;
LABEL_32:
      v22 = v16;
      goto LABEL_40;
    }
    *a3 = 1;
    *v25 = 11;
    LastFailureAsHRESULT = 0;
    v20 = 0;
    v21 = 1516;
  }
LABEL_40:
  if ( v14 )
  {
    CoTaskMemFree(v14);
    LastFailureAsHRESULT = v20;
LABEL_45:
    CloseHandle(FileW);
    goto LABEL_49;
  }
LABEL_43:
  if ( FileW != (char *)-1LL && FileW )
    goto LABEL_45;
LABEL_49:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v20);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180010cc0  push    rbp
0x180010cc2  push    rbx
0x180010cc3  push    rsi
0x180010cc4  push    rdi
0x180010cc5  push    r12
0x180010cc7  push    r13
0x180010cc9  push    r14
0x180010ccb  push    r15
0x180010ccd  lea     rbp, [rsp-48h]
0x180010cd2  sub     rsp, 148h
0x180010cd9  mov     rax, cs:__security_cookie
0x180010ce0  xor     rax, rsp
0x180010ce3  mov     [rbp+80h+var_50], rax
0x180010ce7  mov     rsi, r9
0x180010cea  mov     r14, r8
0x180010ced  mov     r12, rdx
0x180010cf0  mov     [rbp+80h+var_F8], rdx
0x180010cf4  mov     r15, rcx
0x180010cf7  mov     edi, 1
0x180010cfc  mov     r9d, edi; unsigned __int16
0x180010cff  mov     r8d, 593h; unsigned __int16
0x180010d05  lea     rdx, aQueryremovable; "QueryRemovableMediaType"
0x180010d0c  lea     rcx, [rsp+180h+var_138]; this
0x180010d11  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010d16  xor     r13d, r13d
0x180010d19  mov     [rbp+80h+BytesReturned], r13d
0x180010d1d  mov     [rsp+180h+var_13C], r13d
0x180010d22  mov     [rbp+80h+OutBuffer], r13d
0x180010d26  xor     edx, edx; Val
0x180010d28  mov     r8d, 9Ch; Size
0x180010d2e  lea     rcx, [rbp+80h+var_EC]; void *
0x180010d32  call    memset_0
0x180010d37  mov     [rsp+180h+nOutBufferSize], r13d
0x180010d3c  mov     [rbp+80h+var_FC], r13d
0x180010d40  test    r12, r12
0x180010d43  jz      short loc_180010D56
0x180010d45  lea     ecx, [rdi+3]
0x180010d48  mov     rax, r12
0x180010d4b  mov     [rax], r13b
0x180010d4e  add     rax, rdi
0x180010d51  sub     rcx, rdi
0x180010d54  jnz     short loc_180010D4B
0x180010d56  test    r14, r14
0x180010d59  jz      short loc_180010D5E
0x180010d5b  mov     [r14], r13d
0x180010d5e  test    rsi, rsi
0x180010d61  jz      short loc_180010D66
0x180010d63  mov     [rsi], r13d
0x180010d66  test    r15, r15
0x180010d69  jz      loc_180011095
0x180010d6f  cmp     [r15], r13w
0x180010d73  jz      loc_180011095
0x180010d79  mov     eax, 5A4h
0x180010d7e  mov     [rsp+180h+var_134], ax
0x180010d83  mov     eax, 5A5h
0x180010d88  test    r12, r12
0x180010d8b  jz      loc_18001109A
0x180010d91  mov     [rsp+180h+var_134], ax
0x180010d96  mov     eax, 5A6h
0x180010d9b  test    r14, r14
0x180010d9e  jz      loc_18001109A
0x180010da4  mov     [rsp+180h+var_134], ax
0x180010da9  mov     eax, 5A7h
0x180010dae  test    rsi, rsi
0x180010db1  jz      loc_18001109A
0x180010db7  mov     [rsp+180h+var_138], r13d
0x180010dbc  mov     [rsp+180h+var_134], ax
0x180010dc1  mov     [r14], r13d
0x180010dc4  mov     [rsi], edi
0x180010dc6  lea     rdx, [rsp+180h+nOutBufferSize]
0x180010dcb  mov     rcx, r15; lpFileName
0x180010dce  call    IsDeviceFloppy
0x180010dd3  mov     ebx, eax
0x180010dd5  mov     [rsp+180h+var_138], eax
0x180010dd9  test    eax, eax
0x180010ddb  mov     eax, 5B2h
0x180010de0  js      loc_1800110A3
0x180010de6  mov     [rsp+180h+var_134], ax
0x180010deb  mov     rcx, r15; lpFileName
0x180010dee  cmp     [rsp+180h+nOutBufferSize], r13d
0x180010df3  jz      short loc_180010E2E
0x180010df5  mov     r9, rsi
0x180010df8  mov     r8, r14
0x180010dfb  mov     rdx, r12
0x180010dfe  call    QueryFloppyMediaType
0x180010e03  mov     ebx, eax
0x180010e05  mov     [rsp+180h+var_138], eax
0x180010e09  test    eax, eax
0x180010e0b  jns     short loc_180010E17
0x180010e0d  mov     eax, 5BDh
0x180010e12  jmp     loc_1800110A3
0x180010e17  mov     [rsp+180h+var_138], r13d
0x180010e1c  mov     eax, 5BFh
0x180010e21  mov     [rsp+180h+var_134], ax
0x180010e26  mov     ebx, r13d
0x180010e29  jmp     loc_1800110A8
0x180010e2e  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x180010e33  mov     [rsp+180h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180010e38  mov     r8d, 3; dwShareMode
0x180010e3e  mov     [rsp+180h+dwCreationDisposition], r8d; dwCreationDisposition
0x180010e43  xor     r9d, r9d; lpSecurityAttributes
0x180010e46  xor     edx, edx; dwDesiredAccess
0x180010e48  call    cs:__imp_CreateFileW
0x180010e4e  mov     r13, rax
0x180010e51  dec     rax
0x180010e54  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010e58  ja      loc_18001106A
0x180010e5e  xor     r12d, r12d
0x180010e61  mov     ecx, 0A0h
0x180010e66  mov     [rsp+180h+nOutBufferSize], ecx
0x180010e6a  mov     [rsp+180h+var_138], r12d
0x180010e6f  mov     eax, 5C9h
0x180010e74  mov     [rsp+180h+var_134], ax
0x180010e79  mov     [rsp+180h+lpOverlapped], r12; lpOverlapped
0x180010e7e  lea     rax, [rbp+80h+BytesReturned]
0x180010e82  mov     [rsp+180h+hTemplateFile], rax; lpBytesReturned
0x180010e87  mov     [rsp+180h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x180010e8b  lea     rax, [rbp+80h+OutBuffer]
0x180010e8f  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; lpOutBuffer
0x180010e94  xor     r9d, r9d; nInBufferSize
0x180010e97  xor     r8d, r8d; lpInBuffer
0x180010e9a  mov     edx, 2D0C04h; dwIoControlCode
0x180010e9f  mov     rcx, r13; hDevice
0x180010ea2  call    cs:__imp_DeviceIoControl
0x180010ea8  test    eax, eax
0x180010eaa  jnz     loc_180010FDB
0x180010eb0  call    cs:__imp_GetLastError
0x180010eb6  mov     ebx, eax
0x180010eb8  cmp     eax, 32h ; '2'
0x180010ebb  jz      loc_180010F85
0x180010ec1  cmp     eax, edi
0x180010ec3  jz      loc_180010F85
0x180010ec9  cmp     eax, 7Ah ; 'z'
0x180010ecc  jz      short loc_180010EF8
0x180010ece  cmp     eax, 0EAh
0x180010ed3  jz      short loc_180010EF8
0x180010ed5  test    eax, eax
0x180010ed7  jle     short loc_180010EE2
0x180010ed9  movzx   ebx, ax
0x180010edc  or      ebx, 80070000h
0x180010ee2  mov     [rsp+180h+var_138], ebx
0x180010ee6  mov     eax, 5F1h
0x180010eeb  test    ebx, ebx
0x180010eed  js      loc_180010FA1
0x180010ef3  mov     [rsp+180h+var_134], ax
0x180010ef8  test    r12, r12
0x180010efb  jz      short loc_180010F06
0x180010efd  mov     rcx, r12; pv
0x180010f00  call    cs:__imp_CoTaskMemFree
0x180010f06  mov     eax, [rsp+180h+nOutBufferSize]
0x180010f0a  add     eax, eax
0x180010f0c  mov     [rsp+180h+nOutBufferSize], eax
0x180010f10  mov     ecx, eax; cb
0x180010f12  call    cs:__imp_CoTaskMemAlloc
0x180010f18  mov     r12, rax
0x180010f1b  test    rax, rax
0x180010f1e  mov     eax, 5FFh
0x180010f23  jz      short loc_180010F72
0x180010f25  mov     [rsp+180h+var_138], 0
0x180010f2d  mov     [rsp+180h+var_134], ax
0x180010f32  mov     rbx, r12
0x180010f35  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x180010f3e  lea     rax, [rbp+80h+BytesReturned]
0x180010f42  mov     [rsp+180h+hTemplateFile], rax; lpBytesReturned
0x180010f47  mov     ecx, [rsp+180h+nOutBufferSize]
0x180010f4b  mov     [rsp+180h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x180010f4f  mov     qword ptr [rsp+180h+dwCreationDisposition], r12; lpOutBuffer
0x180010f54  xor     r9d, r9d; nInBufferSize
0x180010f57  xor     r8d, r8d; lpInBuffer
0x180010f5a  mov     edx, 2D0C04h; dwIoControlCode
0x180010f5f  mov     rcx, r13; hDevice
0x180010f62  call    cs:__imp_DeviceIoControl
0x180010f68  test    eax, eax
0x180010f6a  jz      loc_180010EB0
0x180010f70  jmp     short loc_180010FDF
0x180010f72  mov     ebx, 8007000Eh
0x180010f77  mov     [rsp+180h+var_138], ebx
0x180010f7b  mov     [rsp+180h+var_132], ax
0x180010f80  jmp     loc_18001108A
0x180010f85  lea     rdx, [rsp+180h+var_13C]
0x180010f8a  mov     rcx, r15; lpFileName
0x180010f8d  call    IsDeviceLockable
0x180010f92  mov     ebx, eax
0x180010f94  mov     [rsp+180h+var_138], eax
0x180010f98  test    eax, eax
0x180010f9a  jns     short loc_180010FAB
0x180010f9c  mov     eax, 5DFh
0x180010fa1  mov     [rsp+180h+var_132], ax
0x180010fa6  jmp     loc_180011056
0x180010fab  cmp     [rsp+180h+var_13C], 0
0x180010fb0  jz      short loc_180010FBB
0x180010fb2  mov     eax, 0Ah
0x180010fb7  xor     edi, edi
0x180010fb9  jmp     short loc_180010FC0
0x180010fbb  mov     eax, 0Bh
0x180010fc0  mov     [r14], edi
0x180010fc3  mov     rcx, [rbp+80h+var_F8]
0x180010fc7  mov     [rcx], eax
0x180010fc9  xor     ebx, ebx
0x180010fcb  mov     [rsp+180h+var_138], ebx
0x180010fcf  mov     eax, 5ECh
0x180010fd4  mov     [rsp+180h+var_134], ax
0x180010fd9  jmp     short loc_180011056
0x180010fdb  lea     rbx, [rbp+80h+OutBuffer]
0x180010fdf  lea     r8, [rbp+80h+var_FC]
0x180010fe3  mov     rdx, [rbp+80h+var_F8]
0x180010fe7  mov     rcx, rbx
0x180010fea  call    FindLargestRemovableMediaType
0x180010fef  mov     ebx, eax
0x180010ff1  mov     [rsp+180h+var_138], eax
0x180010ff5  test    eax, eax
0x180010ff7  mov     eax, 60Eh
0x180010ffc  js      short loc_180010FA1
0x180010ffe  mov     [rsp+180h+var_134], ax
0x180011003  cmp     [rbp+80h+var_FC], 0
0x180011007  jnz     short loc_180011050
0x180011009  mov     [rsi], edi
0x18001100b  lea     rdx, [rsp+180h+var_13C]
0x180011010  mov     rcx, r15; lpFileName
0x180011013  call    IsDeviceLockable
0x180011018  mov     ebx, eax
0x18001101a  mov     [rsp+180h+var_138], eax
0x18001101e  test    eax, eax
0x180011020  mov     eax, 61Ah
0x180011025  js      loc_180010FA1
0x18001102b  mov     [rsp+180h+var_134], ax
0x180011030  cmp     [rsp+180h+var_13C], 0
0x180011035  jz      short loc_180011040
0x180011037  mov     eax, 0Ah
0x18001103c  xor     edi, edi
0x18001103e  jmp     short loc_180011045
0x180011040  mov     eax, 0Bh
0x180011045  mov     [r14], edi
0x180011048  mov     rcx, [rbp+80h+var_F8]
0x18001104c  mov     [rcx], eax
0x18001104e  jmp     short loc_180011056
0x180011050  mov     dword ptr [rsi], 0
0x180011056  test    r12, r12
0x180011059  jz      short loc_18001107F
0x18001105b  mov     rcx, r12; pv
0x18001105e  call    cs:__imp_CoTaskMemFree
0x180011064  mov     ebx, [rsp+180h+var_138]
0x180011068  jmp     short loc_18001108A
0x18001106a  call    GetLastFailureAsHRESULT
0x18001106f  mov     ebx, eax
0x180011071  mov     [rsp+180h+var_138], eax
0x180011075  mov     eax, 5C9h
0x18001107a  mov     [rsp+180h+var_132], ax
0x18001107f  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180011083  jz      short loc_1800110A8
0x180011085  test    r13, r13
0x180011088  jz      short loc_1800110A8
0x18001108a  mov     rcx, r13; hObject
0x18001108d  call    cs:__imp_CloseHandle
0x180011093  jmp     short loc_1800110A8
0x180011095  mov     eax, 5A4h
0x18001109a  mov     ebx, 80070057h
0x18001109f  mov     [rsp+180h+var_138], ebx
0x1800110a3  mov     [rsp+180h+var_132], ax
0x1800110a8  lea     rcx, [rsp+180h+var_138]; this
0x1800110ad  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800110b2  mov     eax, ebx
0x1800110b4  mov     rcx, [rbp+80h+var_50]
0x1800110b8  xor     rcx, rsp; StackCookie
0x1800110bb  call    __security_check_cookie
0x1800110c0  add     rsp, 148h
0x1800110c7  pop     r15
0x1800110c9  pop     r14
0x1800110cb  pop     r13
0x1800110cd  pop     r12
0x1800110cf  pop     rdi
0x1800110d0  pop     rsi
0x1800110d1  pop     rbx
0x1800110d2  pop     rbp
0x1800110d3  retn
```

# QueryRemovableMediaType

- ea: `0x1800113d0`
- end: `0x180011815`
- name: `QueryRemovableMediaType`
- size: `1093`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, service_task`

## callees

- `0x18000c388`
- `0x18000e060`
- `0x18000e1e8`
- `0x180010b38`
- `0x1800113d0`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180011558`
- `KERNEL32!CreateFileW` at `0x180011558`
- `KERNEL32!GetLastError` at `0x1800115cc`
- `KERNEL32!GetLastError` at `0x1800115cc`
- `KERNEL32!CloseHandle` at `0x1800117c7`
- `KERNEL32!CloseHandle` at `0x1800117c7`
- `KERNEL32!DeviceIoControl` at `0x1800115b8`
- `KERNEL32!DeviceIoControl` at `0x180011690`
- `KERNEL32!DeviceIoControl` at `0x1800115b8`
- `KERNEL32!DeviceIoControl` at `0x180011690`
- `ole32!CoTaskMemFree` at `0x180011622`
- `ole32!CoTaskMemFree` at `0x180011792`
- `ole32!CoTaskMemFree` at `0x180011622`
- `ole32!CoTaskMemFree` at `0x180011792`
- `ole32!CoTaskMemAlloc` at `0x18001163a`
- `ole32!CoTaskMemAlloc` at `0x18001163a`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v20, "QueryRemovableMediaType", 0x593u, 1u);
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
0x1800113d0  push    rbp
0x1800113d2  push    rbx
0x1800113d3  push    rsi
0x1800113d4  push    rdi
0x1800113d5  push    r12
0x1800113d7  push    r13
0x1800113d9  push    r14
0x1800113db  push    r15
0x1800113dd  lea     rbp, [rsp-48h]
0x1800113e2  sub     rsp, 148h
0x1800113e9  mov     rax, cs:__security_cookie
0x1800113f0  xor     rax, rsp
0x1800113f3  mov     [rbp+80h+var_50], rax
0x1800113f7  mov     rsi, r9
0x1800113fa  mov     r14, r8
0x1800113fd  mov     r12, rdx
0x180011400  mov     [rbp+80h+var_F8], rdx
0x180011404  mov     r15, rcx
0x180011407  mov     edi, 1
0x18001140c  mov     r9d, edi; unsigned __int16
0x18001140f  mov     r8d, 593h; unsigned __int16
0x180011415  lea     rdx, aQueryremovable; "QueryRemovableMediaType"
0x18001141c  lea     rcx, [rsp+180h+var_138]; this
0x180011421  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180011426  xor     r13d, r13d
0x180011429  mov     [rbp+80h+BytesReturned], r13d
0x18001142d  mov     [rsp+180h+var_13C], r13d
0x180011432  mov     [rbp+80h+OutBuffer], r13d
0x180011436  xor     edx, edx; Val
0x180011438  mov     r8d, 9Ch; Size
0x18001143e  lea     rcx, [rbp+80h+var_EC]; void *
0x180011442  call    memset_0
0x180011447  mov     [rsp+180h+nOutBufferSize], r13d
0x18001144c  mov     [rbp+80h+var_FC], r13d
0x180011450  test    r12, r12
0x180011453  jz      short loc_180011466
0x180011455  lea     ecx, [rdi+3]
0x180011458  mov     rax, r12
0x18001145b  mov     [rax], r13b
0x18001145e  add     rax, rdi
0x180011461  sub     rcx, rdi
0x180011464  jnz     short loc_18001145B
0x180011466  test    r14, r14
0x180011469  jz      short loc_18001146E
0x18001146b  mov     [r14], r13d
0x18001146e  test    rsi, rsi
0x180011471  jz      short loc_180011476
0x180011473  mov     [rsi], r13d
0x180011476  test    r15, r15
0x180011479  jz      loc_1800117D5
0x18001147f  cmp     [r15], r13w
0x180011483  jz      loc_1800117D5
0x180011489  mov     eax, 5A4h
0x18001148e  mov     [rsp+180h+var_134], ax
0x180011493  mov     eax, 5A5h
0x180011498  test    r12, r12
0x18001149b  jz      loc_1800117DA
0x1800114a1  mov     [rsp+180h+var_134], ax
0x1800114a6  mov     eax, 5A6h
0x1800114ab  test    r14, r14
0x1800114ae  jz      loc_1800117DA
0x1800114b4  mov     [rsp+180h+var_134], ax
0x1800114b9  mov     eax, 5A7h
0x1800114be  test    rsi, rsi
0x1800114c1  jz      loc_1800117DA
0x1800114c7  mov     [rsp+180h+var_138], r13d
0x1800114cc  mov     [rsp+180h+var_134], ax
0x1800114d1  mov     [r14], r13d
0x1800114d4  mov     [rsi], edi
0x1800114d6  lea     rdx, [rsp+180h+nOutBufferSize]
0x1800114db  mov     rcx, r15; lpFileName
0x1800114de  call    IsDeviceFloppy
0x1800114e3  mov     ebx, eax
0x1800114e5  mov     [rsp+180h+var_138], eax
0x1800114e9  test    eax, eax
0x1800114eb  mov     eax, 5B2h
0x1800114f0  js      loc_1800117E3
0x1800114f6  mov     [rsp+180h+var_134], ax
0x1800114fb  mov     rcx, r15; lpFileName
0x1800114fe  cmp     [rsp+180h+nOutBufferSize], r13d
0x180011503  jz      short loc_18001153E
0x180011505  mov     r9, rsi
0x180011508  mov     r8, r14
0x18001150b  mov     rdx, r12
0x18001150e  call    QueryFloppyMediaType
0x180011513  mov     ebx, eax
0x180011515  mov     [rsp+180h+var_138], eax
0x180011519  test    eax, eax
0x18001151b  jns     short loc_180011527
0x18001151d  mov     eax, 5BDh
0x180011522  jmp     loc_1800117E3
0x180011527  mov     [rsp+180h+var_138], r13d
0x18001152c  mov     eax, 5BFh
0x180011531  mov     [rsp+180h+var_134], ax
0x180011536  mov     ebx, r13d
0x180011539  jmp     loc_1800117E8
0x18001153e  mov     [rsp+180h+hTemplateFile], r13; hTemplateFile
0x180011543  mov     [rsp+180h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x180011548  mov     r8d, 3; dwShareMode
0x18001154e  mov     [rsp+180h+dwCreationDisposition], r8d; dwCreationDisposition
0x180011553  xor     r9d, r9d; lpSecurityAttributes
0x180011556  xor     edx, edx; dwDesiredAccess
0x180011558  call    cs:__imp_CreateFileW
0x18001155f  nop     dword ptr [rax+rax+00h]
0x180011564  mov     r13, rax
0x180011567  dec     rax
0x18001156a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001156e  ja      loc_1800117A4
0x180011574  xor     r12d, r12d
0x180011577  mov     ecx, 0A0h
0x18001157c  mov     [rsp+180h+nOutBufferSize], ecx
0x180011580  mov     [rsp+180h+var_138], r12d
0x180011585  mov     eax, 5C9h
0x18001158a  mov     [rsp+180h+var_134], ax
0x18001158f  mov     [rsp+180h+lpOverlapped], r12; lpOverlapped
0x180011594  lea     rax, [rbp+80h+BytesReturned]
0x180011598  mov     [rsp+180h+hTemplateFile], rax; lpBytesReturned
0x18001159d  mov     [rsp+180h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x1800115a1  lea     rax, [rbp+80h+OutBuffer]
0x1800115a5  mov     qword ptr [rsp+180h+dwCreationDisposition], rax; lpOutBuffer
0x1800115aa  xor     r9d, r9d; nInBufferSize
0x1800115ad  xor     r8d, r8d; lpInBuffer
0x1800115b0  mov     edx, 2D0C04h; dwIoControlCode
0x1800115b5  mov     rcx, r13; hDevice
0x1800115b8  call    cs:__imp_DeviceIoControl
0x1800115bf  nop     dword ptr [rax+rax+00h]
0x1800115c4  test    eax, eax
0x1800115c6  jnz     loc_18001170F
0x1800115cc  call    cs:__imp_GetLastError
0x1800115d3  nop     dword ptr [rax+rax+00h]
0x1800115d8  mov     ebx, eax
0x1800115da  cmp     eax, 32h ; '2'
0x1800115dd  jz      loc_1800116B9
0x1800115e3  cmp     eax, edi
0x1800115e5  jz      loc_1800116B9
0x1800115eb  cmp     eax, 7Ah ; 'z'
0x1800115ee  jz      short loc_18001161A
0x1800115f0  cmp     eax, 0EAh
0x1800115f5  jz      short loc_18001161A
0x1800115f7  test    eax, eax
0x1800115f9  jle     short loc_180011604
0x1800115fb  movzx   ebx, ax
0x1800115fe  or      ebx, 80070000h
0x180011604  mov     [rsp+180h+var_138], ebx
0x180011608  mov     eax, 5F1h
0x18001160d  test    ebx, ebx
0x18001160f  js      loc_1800116D5
0x180011615  mov     [rsp+180h+var_134], ax
0x18001161a  test    r12, r12
0x18001161d  jz      short loc_18001162E
0x18001161f  mov     rcx, r12; pv
0x180011622  call    cs:__imp_CoTaskMemFree
0x180011629  nop     dword ptr [rax+rax+00h]
0x18001162e  mov     eax, [rsp+180h+nOutBufferSize]
0x180011632  add     eax, eax
0x180011634  mov     [rsp+180h+nOutBufferSize], eax
0x180011638  mov     ecx, eax; cb
0x18001163a  call    cs:__imp_CoTaskMemAlloc
0x180011641  nop     dword ptr [rax+rax+00h]
0x180011646  mov     r12, rax
0x180011649  test    rax, rax
0x18001164c  mov     eax, 5FFh
0x180011651  jz      short loc_1800116A6
0x180011653  mov     [rsp+180h+var_138], 0
0x18001165b  mov     [rsp+180h+var_134], ax
0x180011660  mov     rbx, r12
0x180011663  mov     [rsp+180h+lpOverlapped], 0; lpOverlapped
0x18001166c  lea     rax, [rbp+80h+BytesReturned]
0x180011670  mov     [rsp+180h+hTemplateFile], rax; lpBytesReturned
0x180011675  mov     ecx, [rsp+180h+nOutBufferSize]
0x180011679  mov     [rsp+180h+dwFlagsAndAttributes], ecx; nOutBufferSize
0x18001167d  mov     qword ptr [rsp+180h+dwCreationDisposition], r12; lpOutBuffer
0x180011682  xor     r9d, r9d; nInBufferSize
0x180011685  xor     r8d, r8d; lpInBuffer
0x180011688  mov     edx, 2D0C04h; dwIoControlCode
0x18001168d  mov     rcx, r13; hDevice
0x180011690  call    cs:__imp_DeviceIoControl
0x180011697  nop     dword ptr [rax+rax+00h]
0x18001169c  test    eax, eax
0x18001169e  jz      loc_1800115CC
0x1800116a4  jmp     short loc_180011713
0x1800116a6  mov     ebx, 8007000Eh
0x1800116ab  mov     [rsp+180h+var_138], ebx
0x1800116af  mov     [rsp+180h+var_132], ax
0x1800116b4  jmp     loc_1800117C4
0x1800116b9  lea     rdx, [rsp+180h+var_13C]
0x1800116be  mov     rcx, r15; lpFileName
0x1800116c1  call    IsDeviceLockable
0x1800116c6  mov     ebx, eax
0x1800116c8  mov     [rsp+180h+var_138], eax
0x1800116cc  test    eax, eax
0x1800116ce  jns     short loc_1800116DF
0x1800116d0  mov     eax, 5DFh
0x1800116d5  mov     [rsp+180h+var_132], ax
0x1800116da  jmp     loc_18001178A
0x1800116df  cmp     [rsp+180h+var_13C], 0
0x1800116e4  jz      short loc_1800116EF
0x1800116e6  mov     eax, 0Ah
0x1800116eb  xor     edi, edi
0x1800116ed  jmp     short loc_1800116F4
0x1800116ef  mov     eax, 0Bh
0x1800116f4  mov     [r14], edi
0x1800116f7  mov     rcx, [rbp+80h+var_F8]
0x1800116fb  mov     [rcx], eax
0x1800116fd  xor     ebx, ebx
0x1800116ff  mov     [rsp+180h+var_138], ebx
0x180011703  mov     eax, 5ECh
0x180011708  mov     [rsp+180h+var_134], ax
0x18001170d  jmp     short loc_18001178A
0x18001170f  lea     rbx, [rbp+80h+OutBuffer]
0x180011713  lea     r8, [rbp+80h+var_FC]
0x180011717  mov     rdx, [rbp+80h+var_F8]
0x18001171b  mov     rcx, rbx
0x18001171e  call    FindLargestRemovableMediaType
0x180011723  mov     ebx, eax
0x180011725  mov     [rsp+180h+var_138], eax
0x180011729  test    eax, eax
0x18001172b  mov     eax, 60Eh
0x180011730  js      short loc_1800116D5
0x180011732  mov     [rsp+180h+var_134], ax
0x180011737  cmp     [rbp+80h+var_FC], 0
0x18001173b  jnz     short loc_180011784
0x18001173d  mov     [rsi], edi
0x18001173f  lea     rdx, [rsp+180h+var_13C]
0x180011744  mov     rcx, r15; lpFileName
0x180011747  call    IsDeviceLockable
0x18001174c  mov     ebx, eax
0x18001174e  mov     [rsp+180h+var_138], eax
0x180011752  test    eax, eax
0x180011754  mov     eax, 61Ah
0x180011759  js      loc_1800116D5
0x18001175f  mov     [rsp+180h+var_134], ax
0x180011764  cmp     [rsp+180h+var_13C], 0
0x180011769  jz      short loc_180011774
0x18001176b  mov     eax, 0Ah
0x180011770  xor     edi, edi
0x180011772  jmp     short loc_180011779
0x180011774  mov     eax, 0Bh
0x180011779  mov     [r14], edi
0x18001177c  mov     rcx, [rbp+80h+var_F8]
0x180011780  mov     [rcx], eax
0x180011782  jmp     short loc_18001178A
0x180011784  mov     dword ptr [rsi], 0
0x18001178a  test    r12, r12
0x18001178d  jz      short loc_1800117B9
0x18001178f  mov     rcx, r12; pv
0x180011792  call    cs:__imp_CoTaskMemFree
0x180011799  nop     dword ptr [rax+rax+00h]
0x18001179e  mov     ebx, [rsp+180h+var_138]
0x1800117a2  jmp     short loc_1800117C4
0x1800117a4  call    GetLastFailureAsHRESULT
0x1800117a9  mov     ebx, eax
0x1800117ab  mov     [rsp+180h+var_138], eax
0x1800117af  mov     eax, 5C9h
0x1800117b4  mov     [rsp+180h+var_132], ax
0x1800117b9  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800117bd  jz      short loc_1800117E8
0x1800117bf  test    r13, r13
0x1800117c2  jz      short loc_1800117E8
0x1800117c4  mov     rcx, r13; hObject
0x1800117c7  call    cs:__imp_CloseHandle
0x1800117ce  nop     dword ptr [rax+rax+00h]
0x1800117d3  jmp     short loc_1800117E8
0x1800117d5  mov     eax, 5A4h
0x1800117da  mov     ebx, 80070057h
0x1800117df  mov     [rsp+180h+var_138], ebx
0x1800117e3  mov     [rsp+180h+var_132], ax
0x1800117e8  lea     rcx, [rsp+180h+var_138]; this
0x1800117ed  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800117f2  mov     eax, ebx
0x1800117f4  mov     rcx, [rbp+80h+var_50]
0x1800117f8  xor     rcx, rsp; StackCookie
0x1800117fb  call    __security_check_cookie
0x180011800  add     rsp, 148h
0x180011807  pop     r15
0x180011809  pop     r14
0x18001180b  pop     r13
0x18001180d  pop     r12
0x18001180f  pop     rdi
0x180011810  pop     rsi
0x180011811  pop     rbx
0x180011812  pop     rbp
0x180011813  retn
```

# SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)

- ea: `0x18002a08c`
- end: `0x18002a4f3`
- name: `?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z`
- size: `1127`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180011fb0`
- `0x180028ee8`
- `0x18002aeb8`

## callees

- `0x180001b98`
- `0x18002182c`
- `0x1800268b4`
- `0x1800269ac`
- `0x180026cf4`
- `0x18002a08c`
- `0x18002b4a0`
- `0x18002b630`
- `0x18002d6e8`
- `0x180035b82`
- `0x180035b9a`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002a2e7`
- `KERNEL32!GetLastError` at `0x18002a2e7`
- `KERNEL32!CreateFileW` at `0x18002a24d`
- `KERNEL32!CreateFileW` at `0x18002a24d`
- `KERNEL32!DeviceIoControl` at `0x18002a2d9`
- `KERNEL32!DeviceIoControl` at `0x18002a2d9`
- `KERNEL32!CloseHandle` at `0x18002a4b3`
- `KERNEL32!CloseHandle` at `0x18002a4b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a4a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002a27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002a27c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a3c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002a3c9`

## pseudocode

```c
__int64 __fastcall SxGetVolumeIdentifier(const unsigned __int16 *a1, unsigned __int8 **a2, unsigned int *a3)
{
  __int64 FileW; // r15
  void *v7; // r13
  __int16 v8; // ax
  int v9; // eax
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rax
  __int64 v14; // rcx
  DWORD v15; // edi
  unsigned __int16 *v16; // rbx
  signed int LastFailureAsHRESULT; // eax
  __int64 v18; // rcx
  _QWORD *v19; // rcx
  int v20; // edx
  const char *v21; // r9
  unsigned __int8 *v22; // rax
  unsigned __int8 *v23; // rdi
  __int64 v24; // rdx
  __int64 v25; // r8
  unsigned int v26; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v30; // [rsp+44h] [rbp-BCh]
  __int16 v31; // [rsp+46h] [rbp-BAh]
  DWORD BytesReturned; // [rsp+78h] [rbp-88h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, (_DWORD)a3, (_DWORD)a1, (char)a2, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v29, "SxGetVolumeIdentifier", 1068, 1);
  memset_0(FileName, 0, 0x20Au);
  FileW = -1;
  BytesReturned = 0;
  v7 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 1084;
  if ( !a1 )
    goto LABEL_50;
  v30 = 1084;
  if ( !a2 )
  {
    v31 = 1085;
    goto LABEL_49;
  }
  v30 = 1085;
  v8 = 1086;
  if ( !a3 )
  {
LABEL_50:
    v29 = -2147024809;
LABEL_51:
    v31 = v8;
    goto LABEL_52;
  }
  v30 = 1086;
  v9 = StringCchCopyW(FileName, 0x105u, a1);
  v29 = v9;
  if ( v9 < 0 )
  {
    v31 = 1092;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sdSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v12, dwCreationDisposition, (__int64)a1, v9);
    goto LABEL_52;
  }
  v30 = 1092;
  v13 = -1;
  do
    ++v13;
  while ( FileName[v13] );
  if ( !(_DWORD)v13 )
  {
    v31 = 1095;
LABEL_49:
    v29 = -2147024809;
    goto LABEL_52;
  }
  v30 = 1095;
  v29 = 0;
  if ( FileName[(unsigned int)(v13 - 1)] == 92 )
  {
    if ( 2 * (unsigned __int64)(unsigned int)(v13 - 1) >= 0x20A )
      _report_rangecheckfailure();
    FileName[(unsigned int)(v13 - 1)] = 0;
  }
  FileW = (__int64)CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == -1 )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
    v29 = LastFailureAsHRESULT;
    v31 = 1113;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v20 = 30;
      v21 = "hVolume != INVALID_HANDLE_VALUE";
LABEL_46:
      WPP_SF_sSd(
        v19[2],
        v20,
        (unsigned int)&WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (_DWORD)v21,
        (__int64)FileName,
        LastFailureAsHRESULT);
    }
  }
  else
  {
    v29 = 0;
    v30 = 1113;
    v15 = 256;
    while ( 1 )
    {
      v16 = (unsigned __int16 *)CoTaskMemRealloc(v7, v15);
      v8 = 1121;
      if ( !v16 )
      {
        v29 = -2147024882;
        goto LABEL_51;
      }
      v29 = 0;
      v30 = 1121;
      v7 = v16;
      memset_0(v16, 0, v15);
      if ( DeviceIoControl((HANDLE)FileW, 0x4D0000u, 0, 0, v16, v15, &BytesReturned, 0) )
      {
        v29 = 0;
        v30 = 1140;
        v22 = (unsigned __int8 *)CoTaskMemAlloc(*v16);
        v23 = v22;
        if ( v22 )
        {
          v30 = 1148;
          v29 = 0;
          memcpy_0(v22, v16 + 1, *v16);
          *a3 = *v16;
          *a2 = v23;
        }
        else
        {
          v29 = -2147024882;
          v31 = 1148;
        }
        goto LABEL_52;
      }
      LastFailureAsHRESULT = GetLastError();
      if ( LastFailureAsHRESULT == 122 || LastFailureAsHRESULT == 234 )
      {
        LastFailureAsHRESULT = 0;
      }
      else if ( LastFailureAsHRESULT > 0 )
      {
        LastFailureAsHRESULT = (unsigned __int16)LastFailureAsHRESULT | 0x80070000;
      }
      v29 = LastFailureAsHRESULT;
      if ( LastFailureAsHRESULT < 0 )
        break;
      v15 *= 2;
      v30 = 1134;
      if ( v15 >= 0x10000 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
        v29 = LastFailureAsHRESULT;
        v31 = 1140;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
        {
          v20 = 32;
          v21 = "bRet";
          goto LABEL_46;
        }
        goto LABEL_52;
      }
    }
    v31 = 1134;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v20 = 31;
      v21 = "dwErr";
      goto LABEL_46;
    }
  }
LABEL_52:
  CoTaskMemFree(v7);
  CoTaskMemFree(0);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  v26 = v29;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v29, v24, v25);
  return v26;
}

```

## disassembly

```asm
0x18002a08c  mov     [rsp-8+arg_18], rbx
0x18002a091  push    rbp
0x18002a092  push    rsi
0x18002a093  push    rdi
0x18002a094  push    r12
0x18002a096  push    r13
0x18002a098  push    r14
0x18002a09a  push    r15
0x18002a09c  lea     rbp, [rsp-1A0h]
0x18002a0a4  sub     rsp, 2A0h
0x18002a0ab  mov     rax, cs:__security_cookie
0x18002a0b2  xor     rax, rsp
0x18002a0b5  mov     [rbp+1D0h+var_40], rax
0x18002a0bc  mov     rsi, r8
0x18002a0bf  mov     r14, rdx
0x18002a0c2  mov     rbx, rcx
0x18002a0c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0cc  lea     rdi, WPP_GLOBAL_Control
0x18002a0d3  cmp     rcx, rdi
0x18002a0d6  jz      short loc_18002A0FC
0x18002a0d8  test    dword ptr [rcx+1Ch], 20000000h
0x18002a0df  jz      short loc_18002A0FC
0x18002a0e1  mov     rcx, [rcx+10h]
0x18002a0e5  mov     edx, 1Ch
0x18002a0ea  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], r8
0x18002a0ef  mov     r9, rbx
0x18002a0f2  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r14
0x18002a0f7  call    WPP_SF_Sqq
0x18002a0fc  mov     r9d, 1; unsigned __int16
0x18002a102  lea     rdx, aSxgetvolumeide; "SxGetVolumeIdentifier"
0x18002a109  mov     r8d, 42Ch; unsigned __int16
0x18002a10f  lea     rcx, [rsp+2D0h+var_290]; this
0x18002a114  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18002a119  xor     edx, edx; Val
0x18002a11b  lea     rcx, [rbp+1D0h+FileName]; void *
0x18002a11f  mov     r8d, 20Ah; Size
0x18002a125  call    memset_0
0x18002a12a  xor     r12d, r12d
0x18002a12d  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002a131  mov     [rsp+2D0h+BytesReturned], r12d
0x18002a136  mov     r13d, r12d
0x18002a139  test    r14, r14
0x18002a13c  jz      short loc_18002A141
0x18002a13e  mov     [r14], r12
0x18002a141  test    rsi, rsi
0x18002a144  jz      short loc_18002A149
0x18002a146  mov     [rsi], r12d
0x18002a149  mov     eax, 43Ch
0x18002a14e  test    rbx, rbx
0x18002a151  jz      loc_18002A488
0x18002a157  mov     [rsp+2D0h+var_28C], ax
0x18002a15c  mov     eax, 43Dh
0x18002a161  test    r14, r14
0x18002a164  jz      loc_18002A479
0x18002a16a  mov     [rsp+2D0h+var_28C], ax
0x18002a16f  mov     eax, 43Eh
0x18002a174  test    rsi, rsi
0x18002a177  jz      loc_18002A488
0x18002a17d  mov     r8, rbx; unsigned __int16 *
0x18002a180  mov     [rsp+2D0h+var_28C], ax
0x18002a185  mov     edx, 105h; unsigned __int64
0x18002a18a  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x18002a18e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a193  mov     r11d, eax
0x18002a196  mov     [rsp+2D0h+var_290], eax
0x18002a19a  test    eax, eax
0x18002a19c  mov     eax, 444h
0x18002a1a1  jns     short loc_18002A1DD
0x18002a1a3  mov     [rsp+2D0h+var_28A], ax
0x18002a1a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1af  cmp     rcx, rdi
0x18002a1b2  jz      loc_18002A495
0x18002a1b8  test    dword ptr [rcx+1Ch], 2000000h
0x18002a1bf  jz      loc_18002A495
0x18002a1c5  mov     rcx, [rcx+10h]
0x18002a1c9  mov     dword ptr [rsp+2D0h+hTemplateFile], r11d
0x18002a1ce  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], rbx
0x18002a1d3  call    WPP_SF_sdSd
0x18002a1d8  jmp     loc_18002A495
0x18002a1dd  mov     [rsp+2D0h+var_28C], ax
0x18002a1e2  lea     rcx, [rbp+1D0h+FileName]
0x18002a1e6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a1ea  inc     rax
0x18002a1ed  cmp     [rcx+rax*2], r12w
0x18002a1f2  jnz     short loc_18002A1EA
0x18002a1f4  mov     ecx, 447h
0x18002a1f9  test    eax, eax
0x18002a1fb  jz      loc_18002A472
0x18002a201  mov     [rsp+2D0h+var_28C], cx
0x18002a206  lea     ecx, [rax-1]
0x18002a209  add     rcx, rcx
0x18002a20c  mov     [rsp+2D0h+var_290], r12d
0x18002a211  cmp     [rbp+rcx+1D0h+FileName], 5Ch ; '\'
0x18002a217  jnz     short loc_18002A22C
0x18002a219  cmp     rcx, 20Ah
0x18002a220  jnb     loc_18002A307
0x18002a226  mov     [rbp+rcx+1D0h+FileName], r12w
0x18002a22c  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x18002a231  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x18002a235  mov     r8d, 3; dwShareMode
0x18002a23b  mov     [rsp+2D0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x18002a240  xor     r9d, r9d; lpSecurityAttributes
0x18002a243  mov     [rsp+2D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x18002a248  mov     edx, 80000000h; dwDesiredAccess
0x18002a24d  call    cs:__imp_CreateFileW
0x18002a253  mov     r15, rax
0x18002a256  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a25a  jz      loc_18002A41F
0x18002a260  mov     ecx, 459h
0x18002a265  mov     [rsp+2D0h+var_290], r12d
0x18002a26a  mov     [rsp+2D0h+var_28C], cx
0x18002a26f  mov     edi, 100h
0x18002a274  mov     edx, edi; cb
0x18002a276  mov     rcx, r13; pv
0x18002a279  mov     r12d, edi
0x18002a27c  call    cs:__imp_CoTaskMemRealloc
0x18002a282  mov     rbx, rax
0x18002a285  test    rax, rax
0x18002a288  mov     eax, 461h
0x18002a28d  jz      loc_18002A415
0x18002a293  mov     r8d, r12d; Size
0x18002a296  mov     [rsp+2D0h+var_290], 0
0x18002a29e  xor     edx, edx; Val
0x18002a2a0  mov     [rsp+2D0h+var_28C], ax
0x18002a2a5  mov     rcx, rbx; void *
0x18002a2a8  mov     r13, rbx
0x18002a2ab  call    memset_0
0x18002a2b0  lea     rax, [rsp+2D0h+BytesReturned]
0x18002a2b5  xor     r12d, r12d
0x18002a2b8  mov     [rsp+2D0h+lpOverlapped], r12; lpOverlapped
0x18002a2bd  xor     r9d, r9d; nInBufferSize
0x18002a2c0  mov     [rsp+2D0h+hTemplateFile], rax; lpBytesReturned
0x18002a2c5  xor     r8d, r8d; lpInBuffer
0x18002a2c8  mov     [rsp+2D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18002a2cc  mov     edx, 4D0000h; dwIoControlCode
0x18002a2d1  mov     rcx, r15; hDevice
0x18002a2d4  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rbx; lpOutBuffer
0x18002a2d9  call    cs:__imp_DeviceIoControl
0x18002a2df  test    eax, eax
0x18002a2e1  jnz     loc_18002A3B7
0x18002a2e7  call    cs:__imp_GetLastError
0x18002a2ed  cmp     eax, 7Ah ; 'z'
0x18002a2f0  jz      short loc_18002A30D
0x18002a2f2  cmp     eax, 0EAh
0x18002a2f7  jz      short loc_18002A30D
0x18002a2f9  test    eax, eax
0x18002a2fb  jle     short loc_18002A310
0x18002a2fd  movzx   eax, ax
0x18002a300  or      eax, 80070000h
0x18002a305  jmp     short loc_18002A310
0x18002a307  call    __report_rangecheckfailure
0x18002a30d  mov     eax, r12d
0x18002a310  mov     [rsp+2D0h+var_290], eax
0x18002a314  test    eax, eax
0x18002a316  js      short loc_18002A378
0x18002a318  add     edi, edi
0x18002a31a  mov     eax, 46Eh
0x18002a31f  mov     [rsp+2D0h+var_28C], ax
0x18002a324  cmp     edi, 10000h
0x18002a32a  jb      loc_18002A274
0x18002a330  call    GetLastFailureAsHRESULT
0x18002a335  mov     ecx, 474h
0x18002a33a  mov     [rsp+2D0h+var_290], eax
0x18002a33e  mov     [rsp+2D0h+var_28A], cx
0x18002a343  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a34a  lea     rdx, WPP_GLOBAL_Control
0x18002a351  cmp     rcx, rdx
0x18002a354  jz      loc_18002A495
0x18002a35a  test    dword ptr [rcx+1Ch], 2000000h
0x18002a361  jz      loc_18002A495
0x18002a367  mov     edx, 20h ; ' '
0x18002a36c  lea     r9, aBret; "bRet"
0x18002a373  jmp     loc_18002A453
0x18002a378  mov     ecx, 46Eh
0x18002a37d  mov     [rsp+2D0h+var_28A], cx
0x18002a382  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a389  lea     rdx, WPP_GLOBAL_Control
0x18002a390  cmp     rcx, rdx
0x18002a393  jz      loc_18002A495
0x18002a399  test    dword ptr [rcx+1Ch], 2000000h
0x18002a3a0  jz      loc_18002A495
0x18002a3a6  mov     edx, 1Fh
0x18002a3ab  lea     r9, aDwerr; "dwErr"
0x18002a3b2  jmp     loc_18002A453
0x18002a3b7  mov     ecx, 474h
0x18002a3bc  mov     [rsp+2D0h+var_290], r12d
0x18002a3c1  mov     [rsp+2D0h+var_28C], cx
0x18002a3c6  movzx   ecx, word ptr [rbx]; cb
0x18002a3c9  call    cs:__imp_CoTaskMemAlloc
0x18002a3cf  mov     rdi, rax
0x18002a3d2  mov     ecx, 47Ch
0x18002a3d7  test    rax, rax
0x18002a3da  jz      short loc_18002A403
0x18002a3dc  mov     [rsp+2D0h+var_28C], cx
0x18002a3e1  lea     rdx, [rbx+2]; Src
0x18002a3e5  mov     [rsp+2D0h+var_290], r12d
0x18002a3ea  mov     rcx, rax; void *
0x18002a3ed  movzx   r8d, word ptr [rbx]; Size
0x18002a3f1  call    memcpy_0
0x18002a3f6  movzx   ecx, word ptr [rbx]
0x18002a3f9  mov     [rsi], ecx
0x18002a3fb  mov     [r14], rdi
0x18002a3fe  jmp     loc_18002A495
0x18002a403  mov     [rsp+2D0h+var_290], 8007000Eh
0x18002a40b  mov     [rsp+2D0h+var_28A], cx
0x18002a410  jmp     loc_18002A495
0x18002a415  mov     [rsp+2D0h+var_290], 8007000Eh
0x18002a41d  jmp     short loc_18002A490
0x18002a41f  call    GetLastFailureAsHRESULT
0x18002a424  mov     ecx, 459h
0x18002a429  mov     [rsp+2D0h+var_290], eax
0x18002a42d  mov     [rsp+2D0h+var_28A], cx
0x18002a432  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a439  cmp     rcx, rdi
0x18002a43c  jz      short loc_18002A495
0x18002a43e  test    dword ptr [rcx+1Ch], 2000000h
0x18002a445  jz      short loc_18002A495
0x18002a447  mov     edx, 1Eh
0x18002a44c  lea     r9, aHvolumeInvalid; "hVolume != INVALID_HANDLE_VALUE"
0x18002a453  mov     rcx, [rcx+10h]
0x18002a457  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x18002a45e  mov     [rsp+2D0h+dwFlagsAndAttributes], eax
0x18002a462  lea     rax, [rbp+1D0h+FileName]
0x18002a466  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax
0x18002a46b  call    WPP_SF_sSd
0x18002a470  jmp     short loc_18002A495
0x18002a472  mov     [rsp+2D0h+var_28A], cx
0x18002a477  jmp     short loc_18002A47E
0x18002a479  mov     [rsp+2D0h+var_28A], ax
0x18002a47e  mov     [rsp+2D0h+var_290], 80070057h
0x18002a486  jmp     short loc_18002A495
0x18002a488  mov     [rsp+2D0h+var_290], 80070057h
0x18002a490  mov     [rsp+2D0h+var_28A], ax
0x18002a495  mov     rcx, r13; pv
0x18002a498  call    cs:__imp_CoTaskMemFree
0x18002a49e  xor     ecx, ecx; pv
0x18002a4a0  call    cs:__imp_CoTaskMemFree
0x18002a4a6  lea     rax, [r15-1]
0x18002a4aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002a4ae  ja      short loc_18002A4B9
0x18002a4b0  mov     rcx, r15; hObject
0x18002a4b3  call    cs:__imp_CloseHandle
0x18002a4b9  mov     ebx, [rsp+2D0h+var_290]
0x18002a4bd  lea     rcx, [rsp+2D0h+var_290]; this
0x18002a4c2  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a4c7  mov     eax, ebx
0x18002a4c9  mov     rcx, [rbp+1D0h+var_40]
0x18002a4d0  xor     rcx, rsp; StackCookie
0x18002a4d3  call    __security_check_cookie
0x18002a4d8  mov     rbx, [rsp+2D0h+arg_18]
0x18002a4e0  add     rsp, 2A0h
0x18002a4e7  pop     r15
0x18002a4e9  pop     r14
0x18002a4eb  pop     r13
0x18002a4ed  pop     r12
0x18002a4ef  pop     rdi
0x18002a4f0  pop     rsi
0x18002a4f1  pop     rbp
0x18002a4f2  retn
```

# SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)

- ea: `0x180096308`
- end: `0x1800967a5`
- name: `?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z`
- size: `1181`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180097688`
- `0x1800b448c`

## callees

- `0x180001f88`
- `0x180009d44`
- `0x180014eac`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x180096308`
- `0x180097b08`
- `0x180097c9c`
- `0x1800cf552`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800964ce`
- `KERNEL32!CreateFileW` at `0x1800964ce`
- `KERNEL32!GetLastError` at `0x18009657a`
- `KERNEL32!GetLastError` at `0x18009657a`
- `KERNEL32!CloseHandle` at `0x18009675e`
- `KERNEL32!CloseHandle` at `0x18009675e`
- `KERNEL32!DeviceIoControl` at `0x180096566`
- `KERNEL32!DeviceIoControl` at `0x180096566`
- `ole32!CoTaskMemFree` at `0x180096737`
- `ole32!CoTaskMemFree` at `0x180096745`
- `ole32!CoTaskMemFree` at `0x180096737`
- `ole32!CoTaskMemFree` at `0x180096745`
- `ole32!CoTaskMemRealloc` at `0x180096503`
- `ole32!CoTaskMemRealloc` at `0x180096503`
- `ole32!CoTaskMemAlloc` at `0x180096662`
- `ole32!CoTaskMemAlloc` at `0x180096662`

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
  unsigned int v24; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v28; // [rsp+44h] [rbp-BCh]
  __int16 v29; // [rsp+46h] [rbp-BAh]
  DWORD BytesReturned; // [rsp+78h] [rbp-88h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_Sqq(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, (_DWORD)a3, (_DWORD)a1, (char)a2, (char)a3);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxGetVolumeIdentifier", 0x42Cu, 1u);
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
  v28 = 1084;
  if ( !a2 )
  {
    v29 = 1085;
    goto LABEL_49;
  }
  v28 = 1085;
  v8 = 1086;
  if ( !a3 )
  {
LABEL_50:
    v27 = -2147024809;
LABEL_51:
    v29 = v8;
    goto LABEL_52;
  }
  v27 = 0;
  v28 = 1086;
  v9 = StringCchCopyW(FileName, 0x105u, a1);
  v27 = v9;
  if ( v9 < 0 )
  {
    v29 = 1092;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      WPP_SF_sdSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, v12, dwCreationDisposition, (__int64)a1, v9);
    goto LABEL_52;
  }
  v28 = 1092;
  v13 = -1;
  do
    ++v13;
  while ( FileName[v13] );
  if ( !(_DWORD)v13 )
  {
    v29 = 1095;
LABEL_49:
    v27 = -2147024809;
    goto LABEL_52;
  }
  v28 = 1095;
  v27 = 0;
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
    v27 = LastFailureAsHRESULT;
    v29 = 1113;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v20 = 30;
      v21 = "hVolume != INVALID_HANDLE_VALUE";
LABEL_46:
      WPP_SF_sSd(
        v19[2],
        v20,
        (unsigned int)WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids,
        (_DWORD)v21,
        (__int64)FileName,
        LastFailureAsHRESULT);
    }
  }
  else
  {
    v27 = 0;
    v28 = 1113;
    v15 = 256;
    while ( 1 )
    {
      v16 = (unsigned __int16 *)CoTaskMemRealloc(v7, v15);
      v8 = 1121;
      if ( !v16 )
      {
        v27 = -2147024882;
        goto LABEL_51;
      }
      v27 = 0;
      v28 = 1121;
      v7 = v16;
      memset_0(v16, 0, v15);
      if ( DeviceIoControl((HANDLE)FileW, 0x4D0000u, 0, 0, v16, v15, &BytesReturned, 0) )
      {
        v27 = 0;
        v28 = 1140;
        v22 = (unsigned __int8 *)CoTaskMemAlloc(*v16);
        v23 = v22;
        if ( v22 )
        {
          v28 = 1148;
          v27 = 0;
          memcpy_0(v22, v16 + 1, *v16);
          *a3 = *v16;
          *a2 = v23;
        }
        else
        {
          v27 = -2147024882;
          v29 = 1148;
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
      v27 = LastFailureAsHRESULT;
      if ( LastFailureAsHRESULT < 0 )
        break;
      v15 *= 2;
      v28 = 1134;
      if ( v15 >= 0x10000 )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v18);
        v27 = LastFailureAsHRESULT;
        v29 = 1140;
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
    v29 = 1134;
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
  v24 = v27;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v24;
}

```

## disassembly

```asm
0x180096308  mov     [rsp-8+arg_18], rbx
0x18009630d  push    rbp
0x18009630e  push    rsi
0x18009630f  push    rdi
0x180096310  push    r12
0x180096312  push    r13
0x180096314  push    r14
0x180096316  push    r15
0x180096318  lea     rbp, [rsp-1A0h]
0x180096320  sub     rsp, 2A0h
0x180096327  mov     rax, cs:__security_cookie
0x18009632e  xor     rax, rsp
0x180096331  mov     [rbp+1D0h+var_40], rax
0x180096338  mov     rsi, r8
0x18009633b  mov     r14, rdx
0x18009633e  mov     rbx, rcx
0x180096341  mov     rcx, cs:WPP_GLOBAL_Control
0x180096348  lea     rdi, WPP_GLOBAL_Control
0x18009634f  cmp     rcx, rdi
0x180096352  jz      short loc_180096378
0x180096354  test    dword ptr [rcx+1Ch], 20000000h
0x18009635b  jz      short loc_180096378
0x18009635d  mov     rcx, [rcx+10h]
0x180096361  mov     edx, 1Ch
0x180096366  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], r8
0x18009636b  mov     r9, rbx
0x18009636e  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r14
0x180096373  call    WPP_SF_Sqq
0x180096378  mov     r9d, 1; unsigned __int16
0x18009637e  lea     rdx, aSxgetvolumeide; "SxGetVolumeIdentifier"
0x180096385  mov     r8d, 42Ch; unsigned __int16
0x18009638b  lea     rcx, [rsp+2D0h+var_290]; this
0x180096390  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180096395  xor     edx, edx; Val
0x180096397  lea     rcx, [rbp+1D0h+FileName]; void *
0x18009639b  mov     r8d, 20Ah; Size
0x1800963a1  call    memset_0
0x1800963a6  xor     r12d, r12d
0x1800963a9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800963ad  mov     [rsp+2D0h+BytesReturned], r12d
0x1800963b2  mov     r13d, r12d
0x1800963b5  test    r14, r14
0x1800963b8  jz      short loc_1800963BD
0x1800963ba  mov     [r14], r12
0x1800963bd  test    rsi, rsi
0x1800963c0  jz      short loc_1800963C5
0x1800963c2  mov     [rsi], r12d
0x1800963c5  mov     eax, 43Ch
0x1800963ca  test    rbx, rbx
0x1800963cd  jz      loc_180096727
0x1800963d3  mov     [rsp+2D0h+var_28C], ax
0x1800963d8  mov     eax, 43Dh
0x1800963dd  test    r14, r14
0x1800963e0  jz      loc_180096718
0x1800963e6  mov     [rsp+2D0h+var_28C], ax
0x1800963eb  mov     eax, 43Eh
0x1800963f0  test    rsi, rsi
0x1800963f3  jz      loc_180096727
0x1800963f9  mov     r8, rbx; unsigned __int16 *
0x1800963fc  mov     [rsp+2D0h+var_290], r12d
0x180096401  mov     edx, 105h; unsigned __int64
0x180096406  mov     [rsp+2D0h+var_28C], ax
0x18009640b  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x18009640f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180096414  mov     r11d, eax
0x180096417  mov     [rsp+2D0h+var_290], eax
0x18009641b  test    eax, eax
0x18009641d  mov     eax, 444h
0x180096422  jns     short loc_18009645E
0x180096424  mov     [rsp+2D0h+var_28A], ax
0x180096429  mov     rcx, cs:WPP_GLOBAL_Control
0x180096430  cmp     rcx, rdi
0x180096433  jz      loc_180096734
0x180096439  test    dword ptr [rcx+1Ch], 2000000h
0x180096440  jz      loc_180096734
0x180096446  mov     rcx, [rcx+10h]
0x18009644a  mov     dword ptr [rsp+2D0h+hTemplateFile], r11d
0x18009644f  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], rbx
0x180096454  call    WPP_SF_sdSd
0x180096459  jmp     loc_180096734
0x18009645e  mov     [rsp+2D0h+var_28C], ax
0x180096463  lea     rcx, [rbp+1D0h+FileName]
0x180096467  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009646b  inc     rax
0x18009646e  cmp     [rcx+rax*2], r12w
0x180096473  jnz     short loc_18009646B
0x180096475  mov     ecx, 447h
0x18009647a  test    eax, eax
0x18009647c  jz      loc_180096711
0x180096482  mov     [rsp+2D0h+var_28C], cx
0x180096487  lea     ecx, [rax-1]
0x18009648a  add     rcx, rcx
0x18009648d  mov     [rsp+2D0h+var_290], r12d
0x180096492  cmp     [rbp+rcx+1D0h+FileName], 5Ch ; '\'
0x180096498  jnz     short loc_1800964AD
0x18009649a  cmp     rcx, 20Ah
0x1800964a1  jnb     loc_1800965A0
0x1800964a7  mov     [rbp+rcx+1D0h+FileName], r12w
0x1800964ad  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x1800964b2  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x1800964b6  mov     r8d, 3; dwShareMode
0x1800964bc  mov     [rsp+2D0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800964c1  xor     r9d, r9d; lpSecurityAttributes
0x1800964c4  mov     [rsp+2D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800964c9  mov     edx, 80000000h; dwDesiredAccess
0x1800964ce  call    cs:__imp_CreateFileW
0x1800964d5  nop     dword ptr [rax+rax+00h]
0x1800964da  mov     r15, rax
0x1800964dd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800964e1  jz      loc_1800966BE
0x1800964e7  mov     ecx, 459h
0x1800964ec  mov     [rsp+2D0h+var_290], r12d
0x1800964f1  mov     [rsp+2D0h+var_28C], cx
0x1800964f6  mov     edi, 100h
0x1800964fb  mov     edx, edi; cb
0x1800964fd  mov     rcx, r13; pv
0x180096500  mov     r12d, edi
0x180096503  call    cs:__imp_CoTaskMemRealloc
0x18009650a  nop     dword ptr [rax+rax+00h]
0x18009650f  mov     rbx, rax
0x180096512  test    rax, rax
0x180096515  mov     eax, 461h
0x18009651a  jz      loc_1800966B4
0x180096520  mov     r8d, r12d; Size
0x180096523  mov     [rsp+2D0h+var_290], 0
0x18009652b  xor     edx, edx; Val
0x18009652d  mov     [rsp+2D0h+var_28C], ax
0x180096532  mov     rcx, rbx; void *
0x180096535  mov     r13, rbx
0x180096538  call    memset_0
0x18009653d  lea     rax, [rsp+2D0h+BytesReturned]
0x180096542  xor     r12d, r12d
0x180096545  mov     [rsp+2D0h+lpOverlapped], r12; lpOverlapped
0x18009654a  xor     r9d, r9d; nInBufferSize
0x18009654d  mov     [rsp+2D0h+hTemplateFile], rax; lpBytesReturned
0x180096552  xor     r8d, r8d; lpInBuffer
0x180096555  mov     [rsp+2D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180096559  mov     edx, 4D0000h; dwIoControlCode
0x18009655e  mov     rcx, r15; hDevice
0x180096561  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rbx; lpOutBuffer
0x180096566  call    cs:__imp_DeviceIoControl
0x18009656d  nop     dword ptr [rax+rax+00h]
0x180096572  test    eax, eax
0x180096574  jnz     loc_180096650
0x18009657a  call    cs:__imp_GetLastError
0x180096581  nop     dword ptr [rax+rax+00h]
0x180096586  cmp     eax, 7Ah ; 'z'
0x180096589  jz      short loc_1800965A6
0x18009658b  cmp     eax, 0EAh
0x180096590  jz      short loc_1800965A6
0x180096592  test    eax, eax
0x180096594  jle     short loc_1800965A9
0x180096596  movzx   eax, ax
0x180096599  or      eax, 80070000h
0x18009659e  jmp     short loc_1800965A9
0x1800965a0  call    __report_rangecheckfailure
0x1800965a6  mov     eax, r12d
0x1800965a9  mov     [rsp+2D0h+var_290], eax
0x1800965ad  test    eax, eax
0x1800965af  js      short loc_180096611
0x1800965b1  add     edi, edi
0x1800965b3  mov     eax, 46Eh
0x1800965b8  mov     [rsp+2D0h+var_28C], ax
0x1800965bd  cmp     edi, 10000h
0x1800965c3  jb      loc_1800964FB
0x1800965c9  call    GetLastFailureAsHRESULT
0x1800965ce  mov     ecx, 474h
0x1800965d3  mov     [rsp+2D0h+var_290], eax
0x1800965d7  mov     [rsp+2D0h+var_28A], cx
0x1800965dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800965e3  lea     rdx, WPP_GLOBAL_Control
0x1800965ea  cmp     rcx, rdx
0x1800965ed  jz      loc_180096734
0x1800965f3  test    dword ptr [rcx+1Ch], 2000000h
0x1800965fa  jz      loc_180096734
0x180096600  mov     edx, 20h ; ' '
0x180096605  lea     r9, aBret; "bRet"
0x18009660c  jmp     loc_1800966F2
0x180096611  mov     ecx, 46Eh
0x180096616  mov     [rsp+2D0h+var_28A], cx
0x18009661b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096622  lea     rdx, WPP_GLOBAL_Control
0x180096629  cmp     rcx, rdx
0x18009662c  jz      loc_180096734
0x180096632  test    dword ptr [rcx+1Ch], 2000000h
0x180096639  jz      loc_180096734
0x18009663f  mov     edx, 1Fh
0x180096644  lea     r9, aDwerr; "dwErr"
0x18009664b  jmp     loc_1800966F2
0x180096650  mov     ecx, 474h
0x180096655  mov     [rsp+2D0h+var_290], r12d
0x18009665a  mov     [rsp+2D0h+var_28C], cx
0x18009665f  movzx   ecx, word ptr [rbx]; cb
0x180096662  call    cs:__imp_CoTaskMemAlloc
0x180096669  nop     dword ptr [rax+rax+00h]
0x18009666e  mov     rdi, rax
0x180096671  mov     ecx, 47Ch
0x180096676  test    rax, rax
0x180096679  jz      short loc_1800966A2
0x18009667b  mov     [rsp+2D0h+var_28C], cx
0x180096680  lea     rdx, [rbx+2]; Src
0x180096684  mov     [rsp+2D0h+var_290], r12d
0x180096689  mov     rcx, rax; void *
0x18009668c  movzx   r8d, word ptr [rbx]; Size
0x180096690  call    memcpy_0
0x180096695  movzx   ecx, word ptr [rbx]
0x180096698  mov     [rsi], ecx
0x18009669a  mov     [r14], rdi
0x18009669d  jmp     loc_180096734
0x1800966a2  mov     [rsp+2D0h+var_290], 8007000Eh
0x1800966aa  mov     [rsp+2D0h+var_28A], cx
0x1800966af  jmp     loc_180096734
0x1800966b4  mov     [rsp+2D0h+var_290], 8007000Eh
0x1800966bc  jmp     short loc_18009672F
0x1800966be  call    GetLastFailureAsHRESULT
0x1800966c3  mov     ecx, 459h
0x1800966c8  mov     [rsp+2D0h+var_290], eax
0x1800966cc  mov     [rsp+2D0h+var_28A], cx
0x1800966d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800966d8  cmp     rcx, rdi
0x1800966db  jz      short loc_180096734
0x1800966dd  test    dword ptr [rcx+1Ch], 2000000h
0x1800966e4  jz      short loc_180096734
0x1800966e6  mov     edx, 1Eh
0x1800966eb  lea     r9, aHvolumeInvalid; "hVolume != INVALID_HANDLE_VALUE"
0x1800966f2  mov     rcx, [rcx+10h]
0x1800966f6  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800966fd  mov     [rsp+2D0h+dwFlagsAndAttributes], eax
0x180096701  lea     rax, [rbp+1D0h+FileName]
0x180096705  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax
0x18009670a  call    WPP_SF_sSd
0x18009670f  jmp     short loc_180096734
0x180096711  mov     [rsp+2D0h+var_28A], cx
0x180096716  jmp     short loc_18009671D
0x180096718  mov     [rsp+2D0h+var_28A], ax
0x18009671d  mov     [rsp+2D0h+var_290], 80070057h
0x180096725  jmp     short loc_180096734
0x180096727  mov     [rsp+2D0h+var_290], 80070057h
0x18009672f  mov     [rsp+2D0h+var_28A], ax
0x180096734  mov     rcx, r13; pv
0x180096737  call    cs:__imp_CoTaskMemFree
0x18009673e  nop     dword ptr [rax+rax+00h]
0x180096743  xor     ecx, ecx; pv
0x180096745  call    cs:__imp_CoTaskMemFree
0x18009674c  nop     dword ptr [rax+rax+00h]
0x180096751  lea     rax, [r15-1]
0x180096755  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180096759  ja      short loc_18009676A
0x18009675b  mov     rcx, r15; hObject
0x18009675e  call    cs:__imp_CloseHandle
0x180096765  nop     dword ptr [rax+rax+00h]
0x18009676a  mov     ebx, [rsp+2D0h+var_290]
0x18009676e  lea     rcx, [rsp+2D0h+var_290]; this
0x180096773  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180096778  mov     eax, ebx
0x18009677a  mov     rcx, [rbp+1D0h+var_40]
0x180096781  xor     rcx, rsp; StackCookie
0x180096784  call    __security_check_cookie
0x180096789  mov     rbx, [rsp+2D0h+arg_18]
0x180096791  add     rsp, 2A0h
0x180096798  pop     r15
0x18009679a  pop     r14
0x18009679c  pop     r13
0x18009679e  pop     r12
0x1800967a0  pop     rdi
0x1800967a1  pop     rsi
0x1800967a2  pop     rbp
0x1800967a3  retn
```

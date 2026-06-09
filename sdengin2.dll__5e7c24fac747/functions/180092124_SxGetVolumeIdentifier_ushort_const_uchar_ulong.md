# SxGetVolumeIdentifier(ushort const *,uchar * *,ulong *)

- ea: `0x180092124`
- end: `0x180092590`
- name: `?SxGetVolumeIdentifier@@YAJPEBGPEAPEAEPEAK@Z`
- size: `1132`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x18009341c`
- `0x1800aec54`

## callees

- `0x180001f18`
- `0x180009ac8`
- `0x1800145f4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x180092124`
- `0x18009386c`
- `0x1800939f0`
- `0x1800c97c2`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800922ea`
- `KERNEL32!CreateFileW` at `0x1800922ea`
- `KERNEL32!GetLastError` at `0x180092384`
- `KERNEL32!GetLastError` at `0x180092384`
- `KERNEL32!CloseHandle` at `0x180092550`
- `KERNEL32!CloseHandle` at `0x180092550`
- `KERNEL32!DeviceIoControl` at `0x180092376`
- `KERNEL32!DeviceIoControl` at `0x180092376`
- `ole32!CoTaskMemFree` at `0x180092535`
- `ole32!CoTaskMemFree` at `0x18009253d`
- `ole32!CoTaskMemFree` at `0x180092535`
- `ole32!CoTaskMemFree` at `0x18009253d`
- `ole32!CoTaskMemRealloc` at `0x180092319`
- `ole32!CoTaskMemRealloc` at `0x180092319`
- `ole32!CoTaskMemAlloc` at `0x180092466`
- `ole32!CoTaskMemAlloc` at `0x180092466`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "SxGetVolumeIdentifier", 1068, 1);
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
0x180092124  mov     [rsp-8+arg_18], rbx
0x180092129  push    rbp
0x18009212a  push    rsi
0x18009212b  push    rdi
0x18009212c  push    r12
0x18009212e  push    r13
0x180092130  push    r14
0x180092132  push    r15
0x180092134  lea     rbp, [rsp-1A0h]
0x18009213c  sub     rsp, 2A0h
0x180092143  mov     rax, cs:__security_cookie
0x18009214a  xor     rax, rsp
0x18009214d  mov     [rbp+1D0h+var_40], rax
0x180092154  mov     rsi, r8
0x180092157  mov     r14, rdx
0x18009215a  mov     rbx, rcx
0x18009215d  mov     rcx, cs:WPP_GLOBAL_Control
0x180092164  lea     rdi, WPP_GLOBAL_Control
0x18009216b  cmp     rcx, rdi
0x18009216e  jz      short loc_180092194
0x180092170  test    dword ptr [rcx+1Ch], 20000000h
0x180092177  jz      short loc_180092194
0x180092179  mov     rcx, [rcx+10h]
0x18009217d  mov     edx, 1Ch
0x180092182  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], r8
0x180092187  mov     r9, rbx
0x18009218a  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r14
0x18009218f  call    WPP_SF_Sqq
0x180092194  mov     r9d, 1; unsigned __int16
0x18009219a  lea     rdx, aSxgetvolumeide; "SxGetVolumeIdentifier"
0x1800921a1  mov     r8d, 42Ch; unsigned __int16
0x1800921a7  lea     rcx, [rsp+2D0h+var_290]; this
0x1800921ac  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800921b1  xor     edx, edx; Val
0x1800921b3  lea     rcx, [rbp+1D0h+FileName]; void *
0x1800921b7  mov     r8d, 20Ah; Size
0x1800921bd  call    memset_0
0x1800921c2  xor     r12d, r12d
0x1800921c5  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800921c9  mov     [rsp+2D0h+BytesReturned], r12d
0x1800921ce  mov     r13d, r12d
0x1800921d1  test    r14, r14
0x1800921d4  jz      short loc_1800921D9
0x1800921d6  mov     [r14], r12
0x1800921d9  test    rsi, rsi
0x1800921dc  jz      short loc_1800921E1
0x1800921de  mov     [rsi], r12d
0x1800921e1  mov     eax, 43Ch
0x1800921e6  test    rbx, rbx
0x1800921e9  jz      loc_180092525
0x1800921ef  mov     [rsp+2D0h+var_28C], ax
0x1800921f4  mov     eax, 43Dh
0x1800921f9  test    r14, r14
0x1800921fc  jz      loc_180092516
0x180092202  mov     [rsp+2D0h+var_28C], ax
0x180092207  mov     eax, 43Eh
0x18009220c  test    rsi, rsi
0x18009220f  jz      loc_180092525
0x180092215  mov     r8, rbx; unsigned __int16 *
0x180092218  mov     [rsp+2D0h+var_290], r12d
0x18009221d  mov     edx, 105h; unsigned __int64
0x180092222  mov     [rsp+2D0h+var_28C], ax
0x180092227  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x18009222b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180092230  mov     r11d, eax
0x180092233  mov     [rsp+2D0h+var_290], eax
0x180092237  test    eax, eax
0x180092239  mov     eax, 444h
0x18009223e  jns     short loc_18009227A
0x180092240  mov     [rsp+2D0h+var_28A], ax
0x180092245  mov     rcx, cs:WPP_GLOBAL_Control
0x18009224c  cmp     rcx, rdi
0x18009224f  jz      loc_180092532
0x180092255  test    dword ptr [rcx+1Ch], 2000000h
0x18009225c  jz      loc_180092532
0x180092262  mov     rcx, [rcx+10h]
0x180092266  mov     dword ptr [rsp+2D0h+hTemplateFile], r11d
0x18009226b  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], rbx
0x180092270  call    WPP_SF_sdSd
0x180092275  jmp     loc_180092532
0x18009227a  mov     [rsp+2D0h+var_28C], ax
0x18009227f  lea     rcx, [rbp+1D0h+FileName]
0x180092283  or      rax, 0FFFFFFFFFFFFFFFFh
0x180092287  inc     rax
0x18009228a  cmp     [rcx+rax*2], r12w
0x18009228f  jnz     short loc_180092287
0x180092291  mov     ecx, 447h
0x180092296  test    eax, eax
0x180092298  jz      loc_18009250F
0x18009229e  mov     [rsp+2D0h+var_28C], cx
0x1800922a3  lea     ecx, [rax-1]
0x1800922a6  add     rcx, rcx
0x1800922a9  mov     [rsp+2D0h+var_290], r12d
0x1800922ae  cmp     [rbp+rcx+1D0h+FileName], 5Ch ; '\'
0x1800922b4  jnz     short loc_1800922C9
0x1800922b6  cmp     rcx, 20Ah
0x1800922bd  jnb     loc_1800923A4
0x1800922c3  mov     [rbp+rcx+1D0h+FileName], r12w
0x1800922c9  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x1800922ce  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x1800922d2  mov     r8d, 3; dwShareMode
0x1800922d8  mov     [rsp+2D0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1800922dd  xor     r9d, r9d; lpSecurityAttributes
0x1800922e0  mov     [rsp+2D0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800922e5  mov     edx, 80000000h; dwDesiredAccess
0x1800922ea  call    cs:__imp_CreateFileW
0x1800922f0  mov     r15, rax
0x1800922f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800922f7  jz      loc_1800924BC
0x1800922fd  mov     ecx, 459h
0x180092302  mov     [rsp+2D0h+var_290], r12d
0x180092307  mov     [rsp+2D0h+var_28C], cx
0x18009230c  mov     edi, 100h
0x180092311  mov     edx, edi; cb
0x180092313  mov     rcx, r13; pv
0x180092316  mov     r12d, edi
0x180092319  call    cs:__imp_CoTaskMemRealloc
0x18009231f  mov     rbx, rax
0x180092322  test    rax, rax
0x180092325  mov     eax, 461h
0x18009232a  jz      loc_1800924B2
0x180092330  mov     r8d, r12d; Size
0x180092333  mov     [rsp+2D0h+var_290], 0
0x18009233b  xor     edx, edx; Val
0x18009233d  mov     [rsp+2D0h+var_28C], ax
0x180092342  mov     rcx, rbx; void *
0x180092345  mov     r13, rbx
0x180092348  call    memset_0
0x18009234d  lea     rax, [rsp+2D0h+BytesReturned]
0x180092352  xor     r12d, r12d
0x180092355  mov     [rsp+2D0h+lpOverlapped], r12; lpOverlapped
0x18009235a  xor     r9d, r9d; nInBufferSize
0x18009235d  mov     [rsp+2D0h+hTemplateFile], rax; lpBytesReturned
0x180092362  xor     r8d, r8d; lpInBuffer
0x180092365  mov     [rsp+2D0h+dwFlagsAndAttributes], edi; nOutBufferSize
0x180092369  mov     edx, 4D0000h; dwIoControlCode
0x18009236e  mov     rcx, r15; hDevice
0x180092371  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rbx; lpOutBuffer
0x180092376  call    cs:__imp_DeviceIoControl
0x18009237c  test    eax, eax
0x18009237e  jnz     loc_180092454
0x180092384  call    cs:__imp_GetLastError
0x18009238a  cmp     eax, 7Ah ; 'z'
0x18009238d  jz      short loc_1800923AA
0x18009238f  cmp     eax, 0EAh
0x180092394  jz      short loc_1800923AA
0x180092396  test    eax, eax
0x180092398  jle     short loc_1800923AD
0x18009239a  movzx   eax, ax
0x18009239d  or      eax, 80070000h
0x1800923a2  jmp     short loc_1800923AD
0x1800923a4  call    __report_rangecheckfailure
0x1800923aa  mov     eax, r12d
0x1800923ad  mov     [rsp+2D0h+var_290], eax
0x1800923b1  test    eax, eax
0x1800923b3  js      short loc_180092415
0x1800923b5  add     edi, edi
0x1800923b7  mov     eax, 46Eh
0x1800923bc  mov     [rsp+2D0h+var_28C], ax
0x1800923c1  cmp     edi, 10000h
0x1800923c7  jb      loc_180092311
0x1800923cd  call    GetLastFailureAsHRESULT
0x1800923d2  mov     ecx, 474h
0x1800923d7  mov     [rsp+2D0h+var_290], eax
0x1800923db  mov     [rsp+2D0h+var_28A], cx
0x1800923e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800923e7  lea     rdx, WPP_GLOBAL_Control
0x1800923ee  cmp     rcx, rdx
0x1800923f1  jz      loc_180092532
0x1800923f7  test    dword ptr [rcx+1Ch], 2000000h
0x1800923fe  jz      loc_180092532
0x180092404  mov     edx, 20h ; ' '
0x180092409  lea     r9, aBret; "bRet"
0x180092410  jmp     loc_1800924F0
0x180092415  mov     ecx, 46Eh
0x18009241a  mov     [rsp+2D0h+var_28A], cx
0x18009241f  mov     rcx, cs:WPP_GLOBAL_Control
0x180092426  lea     rdx, WPP_GLOBAL_Control
0x18009242d  cmp     rcx, rdx
0x180092430  jz      loc_180092532
0x180092436  test    dword ptr [rcx+1Ch], 2000000h
0x18009243d  jz      loc_180092532
0x180092443  mov     edx, 1Fh
0x180092448  lea     r9, aDwerr; "dwErr"
0x18009244f  jmp     loc_1800924F0
0x180092454  mov     ecx, 474h
0x180092459  mov     [rsp+2D0h+var_290], r12d
0x18009245e  mov     [rsp+2D0h+var_28C], cx
0x180092463  movzx   ecx, word ptr [rbx]; cb
0x180092466  call    cs:__imp_CoTaskMemAlloc
0x18009246c  mov     rdi, rax
0x18009246f  mov     ecx, 47Ch
0x180092474  test    rax, rax
0x180092477  jz      short loc_1800924A0
0x180092479  mov     [rsp+2D0h+var_28C], cx
0x18009247e  lea     rdx, [rbx+2]; Src
0x180092482  mov     [rsp+2D0h+var_290], r12d
0x180092487  mov     rcx, rax; void *
0x18009248a  movzx   r8d, word ptr [rbx]; Size
0x18009248e  call    memcpy_0
0x180092493  movzx   ecx, word ptr [rbx]
0x180092496  mov     [rsi], ecx
0x180092498  mov     [r14], rdi
0x18009249b  jmp     loc_180092532
0x1800924a0  mov     [rsp+2D0h+var_290], 8007000Eh
0x1800924a8  mov     [rsp+2D0h+var_28A], cx
0x1800924ad  jmp     loc_180092532
0x1800924b2  mov     [rsp+2D0h+var_290], 8007000Eh
0x1800924ba  jmp     short loc_18009252D
0x1800924bc  call    GetLastFailureAsHRESULT
0x1800924c1  mov     ecx, 459h
0x1800924c6  mov     [rsp+2D0h+var_290], eax
0x1800924ca  mov     [rsp+2D0h+var_28A], cx
0x1800924cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800924d6  cmp     rcx, rdi
0x1800924d9  jz      short loc_180092532
0x1800924db  test    dword ptr [rcx+1Ch], 2000000h
0x1800924e2  jz      short loc_180092532
0x1800924e4  mov     edx, 1Eh
0x1800924e9  lea     r9, aHvolumeInvalid; "hVolume != INVALID_HANDLE_VALUE"
0x1800924f0  mov     rcx, [rcx+10h]
0x1800924f4  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x1800924fb  mov     [rsp+2D0h+dwFlagsAndAttributes], eax
0x1800924ff  lea     rax, [rbp+1D0h+FileName]
0x180092503  mov     qword ptr [rsp+2D0h+dwCreationDisposition], rax
0x180092508  call    WPP_SF_sSd
0x18009250d  jmp     short loc_180092532
0x18009250f  mov     [rsp+2D0h+var_28A], cx
0x180092514  jmp     short loc_18009251B
0x180092516  mov     [rsp+2D0h+var_28A], ax
0x18009251b  mov     [rsp+2D0h+var_290], 80070057h
0x180092523  jmp     short loc_180092532
0x180092525  mov     [rsp+2D0h+var_290], 80070057h
0x18009252d  mov     [rsp+2D0h+var_28A], ax
0x180092532  mov     rcx, r13; pv
0x180092535  call    cs:__imp_CoTaskMemFree
0x18009253b  xor     ecx, ecx; pv
0x18009253d  call    cs:__imp_CoTaskMemFree
0x180092543  lea     rax, [r15-1]
0x180092547  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009254b  ja      short loc_180092556
0x18009254d  mov     rcx, r15; hObject
0x180092550  call    cs:__imp_CloseHandle
0x180092556  mov     ebx, [rsp+2D0h+var_290]
0x18009255a  lea     rcx, [rsp+2D0h+var_290]; this
0x18009255f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180092564  mov     eax, ebx
0x180092566  mov     rcx, [rbp+1D0h+var_40]
0x18009256d  xor     rcx, rsp; StackCookie
0x180092570  call    __security_check_cookie
0x180092575  mov     rbx, [rsp+2D0h+arg_18]
0x18009257d  add     rsp, 2A0h
0x180092584  pop     r15
0x180092586  pop     r14
0x180092588  pop     r13
0x18009258a  pop     r12
0x18009258c  pop     rdi
0x18009258d  pop     rsi
0x18009258e  pop     rbp
0x18009258f  retn
```

# CDlpWimCapture::WimSplitCaptureFile(ushort const *)

- ea: `0x1800309dc`
- end: `0x180030d9b`
- name: `?WimSplitCaptureFile@CDlpWimCapture@@AEAAJPEBG@Z`
- size: `959`
- prototype: `__int64 __fastcall(CDlpWimCapture *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a088`

## callees

- `0x18000aba4`
- `0x18000b9a8`
- `0x18000efb8`
- `0x180012f5c`
- `0x18001ad34`
- `0x18001fcc8`
- `0x18001fd60`
- `0x180026f28`
- `0x1800309dc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030c53`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180030c53`
- `WIMGAPI!WIMAddImagePath` at `0x180030c08`
- `WIMGAPI!WIMAddImagePath` at `0x180030c08`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030a5f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180030a5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030d2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030afe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180030d2d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030b0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180030d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d5d`

## string_xrefs

- `0x180030ae7`: `Wim Capture: Skipping [%s] because access was denied`
- `0x180030a4b`: `Wim Capture: Capturing [%s] to [%s]`
- `0x180030c86`: `Wim Capture: Reopened WIM handles successfully`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpWimCapture::WimSplitCaptureFile(CDlpWimCapture *this, const unsigned __int16 *a2)
{
  int v4; // eax
  signed int v5; // edi
  __int64 v6; // rcx
  const WCHAR *v7; // rsi
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  __int64 v10; // rcx
  unsigned int v11; // r12d
  __int64 v12; // rcx
  HANDLE ProcessHeap; // rax
  int FileSize; // eax
  bool v16; // r15
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  int NextSplitCaptureWim; // eax
  int v21; // edi
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int refreshed; // eax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  HANDLE v29; // rax
  signed int v30; // eax
  __int64 v31; // [rsp+20h] [rbp-38h]
  __int64 v32; // [rsp+28h] [rbp-30h]
  __int64 v33; // [rsp+60h] [rbp+8h] BYREF
  LPCWSTR lpFileName; // [rsp+70h] [rbp+18h] BYREF
  __int64 v35; // [rsp+78h] [rbp+20h] BYREF

  lpFileName = 0;
  v33 = 0;
  v4 = CMiscHelpersT<CEmptyType>::CombinePath(*((_QWORD *)this + 7), a2, 0, &lpFileName);
  v5 = v4;
  v6 = *((_QWORD *)this + 15);
  v7 = lpFileName;
  if ( v4 < 0 )
  {
    if ( v6 )
    {
      LODWORD(v32) = v4;
      LODWORD(v31) = 512;
      goto LABEL_54;
    }
    goto LABEL_57;
  }
  if ( v6 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v6, 2, L"Wim Capture: Capturing [%s] to [%s]", lpFileName, a2);
  FileAttributesW = GetFileAttributesW(v7);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = -2147467259;
    }
    if ( *((_QWORD *)this + 15) )
    {
      v10 = 0;
      if ( v5 < 0 )
      {
        LODWORD(v32) = v5;
        LODWORD(v31) = 517;
        goto LABEL_14;
      }
      goto LABEL_56;
    }
    goto LABEL_57;
  }
  if ( (FileAttributesW & 0x10) != 0 )
  {
    v33 = 0;
    v11 = 0x8000000;
  }
  else
  {
    if ( (unsigned int)CDlpHelpersT<CEmptyType>::GetFileSize(v7, &v33) == -2147024891 )
    {
      v12 = *((_QWORD *)this + 15);
      if ( v12 )
        CDlpLogT<CEmptyType>::DlpLogFormat(v12, 3, L"Wim Capture: Skipping [%s] because access was denied", v7);
      if ( v7 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      }
      return 0;
    }
    v11 = 270532608;
  }
  v35 = 0;
  FileSize = CDlpHelpersT<CEmptyType>::GetFileSize(*((_QWORD *)this + 6), &v35);
  v5 = FileSize;
  if ( FileSize >= 0 )
  {
    v16 = v35 + v33 >= *((_QWORD *)this + 18);
  }
  else
  {
    v16 = 0;
    v17 = *((_QWORD *)this + 15);
    if ( v17 )
    {
      LODWORD(v31) = 605;
      v18 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v17,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpWimCapture::WimSplitThresholdReached",
              v31,
              FileSize);
      v19 = (unsigned int)v18;
      if ( v18 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v19);
    }
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v5 < 0 )
  {
    v6 = *((_QWORD *)this + 15);
    if ( v6 )
    {
      LODWORD(v32) = v5;
      LODWORD(v31) = 538;
      goto LABEL_54;
    }
    goto LABEL_57;
  }
  if ( v16 )
  {
    NextSplitCaptureWim = CDlpWimCapture::CreateNextSplitCaptureWim(this);
    v5 = NextSplitCaptureWim;
    if ( NextSplitCaptureWim < 0 )
    {
      v6 = *((_QWORD *)this + 15);
      if ( v6 )
      {
        LODWORD(v32) = NextSplitCaptureWim;
        LODWORD(v31) = 541;
        goto LABEL_54;
      }
      goto LABEL_57;
    }
  }
  v21 = 0;
  while ( 1 )
  {
    v22 = WIMAddImagePath(*((_QWORD *)this + 11), v7, a2, v11);
    if ( v22 == 1 )
    {
LABEL_51:
      *((_QWORD *)this + 19) += v33;
      v27 = CDlpWimCapture::InvokeCallback(this, *((_QWORD *)this + 19), *((_QWORD *)this + 20));
      v5 = v27;
      if ( v27 < 0 )
      {
        v6 = *((_QWORD *)this + 15);
        if ( v6 )
        {
          LODWORD(v32) = v27;
          LODWORD(v31) = 583;
          goto LABEL_54;
        }
      }
      goto LABEL_57;
    }
    if ( !v22 )
      break;
LABEL_50:
    if ( (unsigned int)++v21 >= 3 )
      goto LABEL_51;
  }
  if ( GetLastError() == 1006 )
  {
    v23 = *((_QWORD *)this + 15);
    if ( v23 )
      CDlpLogT<CEmptyType>::DlpLogFormat(
        v23,
        2,
        L"Wim Capture: Lost underlying device handle. Retrying in [%u] ms",
        2000);
    Sleep(0x7D0u);
    v24 = *((_QWORD *)this + 15);
    if ( v24 )
      CDlpLogT<CEmptyType>::DlpLogFormat(v24, 2, L"Wim Capture: Timeout elapsed, refreshing device handles ...");
    refreshed = CDlpWimCapture::RefreshWimHandles(this);
    v26 = *((_QWORD *)this + 15);
    if ( refreshed < 0 )
    {
      if ( v26 )
        CDlpLogT<CEmptyType>::DlpLogFormat(
          v26,
          3,
          L"Wim Capture: Failed to refresh device handles (0x%08x)",
          (unsigned int)refreshed);
    }
    else if ( v26 )
    {
      CDlpLogT<CEmptyType>::DlpLogFormat(v26, 2, L"Wim Capture: Reopened WIM handles successfully");
    }
    goto LABEL_50;
  }
  v30 = GetLastError();
  v5 = v30;
  if ( v30 )
  {
    if ( v30 > 0 )
      v5 = (unsigned __int16)v30 | 0x80070000;
  }
  else
  {
    v5 = -2147467259;
  }
  if ( !*((_QWORD *)this + 15) )
    goto LABEL_57;
  v10 = 0;
  if ( v5 >= 0 )
    goto LABEL_56;
  LODWORD(v32) = v5;
  LODWORD(v31) = 577;
LABEL_14:
  v6 = *((_QWORD *)this + 15);
LABEL_54:
  v28 = CDlpLogT<CEmptyType>::DlpLogFormat(
          v6,
          4,
          L"%s(%d): Result = 0x%X",
          L"CDlpWimCapture::WimSplitCaptureFile",
          v31,
          v32);
  v10 = (unsigned int)v28;
  if ( v28 < 0 )
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v28);
LABEL_56:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v10);
LABEL_57:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v7 )
  {
    v29 = GetProcessHeap();
    HeapFree(v29, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800309dc  mov     rax, rsp
0x1800309df  mov     [rax+10h], rbx
0x1800309e3  push    rsi
0x1800309e4  push    rdi
0x1800309e5  push    r12
0x1800309e7  push    r13
0x1800309e9  push    r15
0x1800309eb  sub     rsp, 30h
0x1800309ef  mov     r13, rdx
0x1800309f2  mov     rbx, rcx
0x1800309f5  mov     qword ptr [rax+18h], 0
0x1800309fd  mov     qword ptr [rax+8], 0
0x180030a05  lea     r9, [rax+18h]
0x180030a09  xor     r8d, r8d
0x180030a0c  mov     rcx, [rcx+38h]
0x180030a10  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180030a15  mov     edi, eax
0x180030a17  mov     rcx, [rbx+78h]
0x180030a1b  mov     rsi, [rsp+58h+lpFileName]
0x180030a20  test    eax, eax
0x180030a22  jns     short loc_180030A3E
0x180030a24  test    rcx, rcx
0x180030a27  jz      loc_180030D20
0x180030a2d  mov     dword ptr [rsp+58h+var_30], eax
0x180030a31  mov     dword ptr [rsp+58h+var_38], 200h
0x180030a39  jmp     loc_180030CF8
0x180030a3e  test    rcx, rcx
0x180030a41  jz      short loc_180030A5C
0x180030a43  mov     [rsp+58h+var_38], r13
0x180030a48  mov     r9, rsi
0x180030a4b  lea     r8, aWimCaptureCapt; "Wim Capture: Capturing [%s] to [%s]"
0x180030a52  mov     edx, 2
0x180030a57  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030a5c  mov     rcx, rsi; lpFileName
0x180030a5f  call    cs:__imp_GetFileAttributesW
0x180030a65  cmp     eax, 0FFFFFFFFh
0x180030a68  jnz     short loc_180030AB2
0x180030a6a  call    cs:__imp_GetLastError
0x180030a70  mov     edi, eax
0x180030a72  test    eax, eax
0x180030a74  jnz     short loc_180030A7D
0x180030a76  mov     edi, 80004005h
0x180030a7b  jmp     short loc_180030A88
0x180030a7d  jle     short loc_180030A88
0x180030a7f  movzx   edi, ax
0x180030a82  or      edi, 80070000h
0x180030a88  cmp     qword ptr [rbx+78h], 0
0x180030a8d  jz      loc_180030D20
0x180030a93  xor     ecx, ecx
0x180030a95  test    edi, edi
0x180030a97  jns     loc_180030D1B
0x180030a9d  mov     dword ptr [rsp+58h+var_30], edi
0x180030aa1  mov     dword ptr [rsp+58h+var_38], 205h
0x180030aa9  mov     rcx, [rbx+78h]
0x180030aad  jmp     loc_180030CF8
0x180030ab2  test    al, 10h
0x180030ab4  jz      short loc_180030AC7
0x180030ab6  mov     [rsp+58h+arg_0], 0
0x180030abf  mov     r12d, 8000000h
0x180030ac5  jmp     short loc_180030B27
0x180030ac7  lea     rdx, [rsp+58h+arg_0]
0x180030acc  mov     rcx, rsi
0x180030acf  call    ?GetFileSize@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAT_LARGE_INTEGER@@@Z; CDlpHelpersT<CEmptyType>::GetFileSize(ushort const *,_LARGE_INTEGER *)
0x180030ad4  cmp     eax, 80070005h
0x180030ad9  jnz     short loc_180030B21
0x180030adb  mov     rcx, [rbx+78h]
0x180030adf  test    rcx, rcx
0x180030ae2  jz      short loc_180030AF9
0x180030ae4  mov     r9, rsi
0x180030ae7  lea     r8, aWimCaptureSkip; "Wim Capture: Skipping [%s] because acce"...
0x180030aee  mov     edx, 3
0x180030af3  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030af8  nop
0x180030af9  test    rsi, rsi
0x180030afc  jz      short loc_180030B1A
0x180030afe  call    cs:__imp_GetProcessHeap
0x180030b04  mov     rcx, rax; hHeap
0x180030b07  lea     r8, [rsi-4]; lpMem
0x180030b0b  xor     edx, edx; dwFlags
0x180030b0d  call    cs:__imp_HeapFree
0x180030b13  xor     ecx, ecx
0x180030b15  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030b1a  xor     eax, eax
0x180030b1c  jmp     loc_180030D4B
0x180030b21  mov     r12d, 10200000h
0x180030b27  mov     [rsp+58h+arg_18], 0
0x180030b30  lea     rdx, [rsp+58h+arg_18]
0x180030b35  mov     rcx, [rbx+30h]
0x180030b39  call    ?GetFileSize@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBGPEAT_LARGE_INTEGER@@@Z; CDlpHelpersT<CEmptyType>::GetFileSize(ushort const *,_LARGE_INTEGER *)
0x180030b3e  mov     edi, eax
0x180030b40  test    eax, eax
0x180030b42  jns     short loc_180030B86
0x180030b44  xor     r15b, r15b
0x180030b47  mov     rcx, [rbx+78h]
0x180030b4b  test    rcx, rcx
0x180030b4e  jz      short loc_180030B9B
0x180030b50  mov     dword ptr [rsp+58h+var_30], eax
0x180030b54  mov     dword ptr [rsp+58h+var_38], 25Dh
0x180030b5c  lea     r9, aCdlpwimcapture_3; "CDlpWimCapture::WimSplitThresholdReache"...
0x180030b63  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180030b6a  mov     edx, 4
0x180030b6f  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030b74  mov     ecx, eax
0x180030b76  test    eax, eax
0x180030b78  jns     short loc_180030B7F
0x180030b7a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180030b7f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030b84  jmp     short loc_180030B9B
0x180030b86  mov     rcx, [rsp+58h+arg_0]
0x180030b8b  add     rcx, [rsp+58h+arg_18]
0x180030b90  cmp     rcx, [rbx+90h]
0x180030b97  setnl   r15b
0x180030b9b  mov     ecx, edi
0x180030b9d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030ba2  test    edi, edi
0x180030ba4  jns     short loc_180030BC4
0x180030ba6  mov     rcx, [rbx+78h]
0x180030baa  test    rcx, rcx
0x180030bad  jz      loc_180030D20
0x180030bb3  mov     dword ptr [rsp+58h+var_30], edi
0x180030bb7  mov     dword ptr [rsp+58h+var_38], 21Ah
0x180030bbf  jmp     loc_180030CF8
0x180030bc4  test    r15b, r15b
0x180030bc7  jz      short loc_180030BF5
0x180030bc9  mov     rcx, rbx; this
0x180030bcc  call    ?CreateNextSplitCaptureWim@CDlpWimCapture@@AEAAJXZ; CDlpWimCapture::CreateNextSplitCaptureWim(void)
0x180030bd1  mov     edi, eax
0x180030bd3  test    eax, eax
0x180030bd5  jns     short loc_180030BF5
0x180030bd7  mov     rcx, [rbx+78h]
0x180030bdb  test    rcx, rcx
0x180030bde  jz      loc_180030D20
0x180030be4  mov     dword ptr [rsp+58h+var_30], eax
0x180030be8  mov     dword ptr [rsp+58h+var_38], 21Dh
0x180030bf0  jmp     loc_180030CF8
0x180030bf5  xor     edi, edi
0x180030bf7  lea     r15d, [rdi+2]
0x180030bfb  mov     r9d, r12d
0x180030bfe  mov     r8, r13
0x180030c01  mov     rdx, rsi
0x180030c04  mov     rcx, [rbx+58h]
0x180030c08  call    cs:__imp_WIMAddImagePath
0x180030c0e  cmp     eax, 1
0x180030c11  jz      loc_180030CBB
0x180030c17  test    eax, eax
0x180030c19  jnz     loc_180030CB0
0x180030c1f  call    cs:__imp_GetLastError
0x180030c25  cmp     eax, 3EEh
0x180030c2a  jnz     loc_180030D5D
0x180030c30  mov     rcx, [rbx+78h]
0x180030c34  test    rcx, rcx
0x180030c37  jz      short loc_180030C4E
0x180030c39  mov     r9d, 7D0h
0x180030c3f  lea     r8, aWimCaptureLost; "Wim Capture: Lost underlying device han"...
0x180030c46  mov     edx, r15d
0x180030c49  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030c4e  mov     ecx, 7D0h; dwMilliseconds
0x180030c53  call    cs:__imp_Sleep
0x180030c59  mov     rcx, [rbx+78h]
0x180030c5d  test    rcx, rcx
0x180030c60  jz      short loc_180030C71
0x180030c62  lea     r8, aWimCaptureTime; "Wim Capture: Timeout elapsed, refreshin"...
0x180030c69  mov     edx, r15d
0x180030c6c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030c71  mov     rcx, rbx; this
0x180030c74  call    ?RefreshWimHandles@CDlpWimCapture@@AEAAJXZ; CDlpWimCapture::RefreshWimHandles(void)
0x180030c79  mov     rcx, [rbx+78h]
0x180030c7d  test    eax, eax
0x180030c7f  js      short loc_180030C97
0x180030c81  test    rcx, rcx
0x180030c84  jz      short loc_180030CB0
0x180030c86  lea     r8, aWimCaptureReop; "Wim Capture: Reopened WIM handles succe"...
0x180030c8d  mov     edx, r15d
0x180030c90  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030c95  jmp     short loc_180030CB0
0x180030c97  test    rcx, rcx
0x180030c9a  jz      short loc_180030CB0
0x180030c9c  mov     r9d, eax
0x180030c9f  lea     r8, aWimCaptureFail; "Wim Capture: Failed to refresh device h"...
0x180030ca6  mov     edx, 3
0x180030cab  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030cb0  inc     edi
0x180030cb2  cmp     edi, 3
0x180030cb5  jb      loc_180030BFB
0x180030cbb  mov     rax, [rsp+58h+arg_0]
0x180030cc0  add     [rbx+98h], rax
0x180030cc7  mov     r8, [rbx+0A0h]; unsigned __int64
0x180030cce  mov     rdx, [rbx+98h]; unsigned __int64
0x180030cd5  mov     rcx, rbx; this
0x180030cd8  call    ?InvokeCallback@CDlpWimCapture@@AEAAJ_K0@Z; CDlpWimCapture::InvokeCallback(unsigned __int64,unsigned __int64)
0x180030cdd  mov     edi, eax
0x180030cdf  test    eax, eax
0x180030ce1  jns     short loc_180030D20
0x180030ce3  mov     rcx, [rbx+78h]
0x180030ce7  test    rcx, rcx
0x180030cea  jz      short loc_180030D20
0x180030cec  mov     dword ptr [rsp+58h+var_30], eax
0x180030cf0  mov     dword ptr [rsp+58h+var_38], 247h
0x180030cf8  lea     r9, aCdlpwimcapture_6; "CDlpWimCapture::WimSplitCaptureFile"
0x180030cff  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180030d06  mov     edx, 4
0x180030d0b  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030d10  test    eax, eax
0x180030d12  mov     ecx, eax
0x180030d14  jns     short loc_180030D1B
0x180030d16  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180030d1b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030d20  mov     ecx, edi
0x180030d22  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030d27  nop
0x180030d28  test    rsi, rsi
0x180030d2b  jz      short loc_180030D49
0x180030d2d  call    cs:__imp_GetProcessHeap
0x180030d33  mov     rcx, rax; hHeap
0x180030d36  lea     r8, [rsi-4]; lpMem
0x180030d3a  xor     edx, edx; dwFlags
0x180030d3c  call    cs:__imp_HeapFree
0x180030d42  xor     ecx, ecx
0x180030d44  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030d49  mov     eax, edi
0x180030d4b  mov     rbx, [rsp+58h+arg_8]
0x180030d50  add     rsp, 30h
0x180030d54  pop     r15
0x180030d56  pop     r13
0x180030d58  pop     r12
0x180030d5a  pop     rdi
0x180030d5b  pop     rsi
0x180030d5c  retn
0x180030d5d  call    cs:__imp_GetLastError
0x180030d63  nop
0x180030d64  mov     edi, eax
0x180030d66  test    eax, eax
0x180030d68  jnz     short loc_180030D71
0x180030d6a  mov     edi, 80004005h
0x180030d6f  jmp     short loc_180030D7C
0x180030d71  jle     short loc_180030D7C
0x180030d73  movzx   edi, ax
0x180030d76  or      edi, 80070000h
0x180030d7c  cmp     qword ptr [rbx+78h], 0
0x180030d81  jz      short loc_180030D20
0x180030d83  xor     ecx, ecx
0x180030d85  test    edi, edi
0x180030d87  jns     short loc_180030D1B
0x180030d89  mov     dword ptr [rsp+58h+var_30], edi
0x180030d8d  mov     dword ptr [rsp+58h+var_38], 241h
0x180030d95  jmp     loc_180030AA9
```

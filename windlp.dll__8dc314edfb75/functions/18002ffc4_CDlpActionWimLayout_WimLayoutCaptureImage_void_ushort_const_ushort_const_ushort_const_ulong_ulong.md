# CDlpActionWimLayout::WimLayoutCaptureImage(void *,ushort const *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18002ffc4`
- end: `0x1800302ca`
- name: `?WimLayoutCaptureImage@CDlpActionWimLayout@@AEAAJPEAXPEBG11KK@Z`
- size: `774`
- prototype: `__int64 __fastcall(CDlpActionWimLayout *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, HLOCAL hMem, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180004b4c`

## callees

- `0x18000aba4`
- `0x180012f5c`
- `0x18001fd60`
- `0x18002ffc4`

## import_xrefs

- `WIMGAPI!WIMCloseHandle` at `0x1800302af`
- `WIMGAPI!WIMCloseHandle` at `0x1800302af`
- `WIMGAPI!WIMGetImageInformation` at `0x1800300b4`
- `WIMGAPI!WIMGetImageInformation` at `0x1800300b4`
- `WIMGAPI!WIMSetImageInformation` at `0x1800301f4`
- `WIMGAPI!WIMSetImageInformation` at `0x1800301f4`
- `WIMGAPI!WIMCaptureImage` at `0x180030048`
- `WIMGAPI!WIMCaptureImage` at `0x180030048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003027c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003027c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003028a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003028a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003005d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800300be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800301fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003029d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003029d`
- `UNATTEND!UnattendCtxSetString` at `0x18003014d`
- `UNATTEND!UnattendCtxSetString` at `0x18003018c`
- `UNATTEND!UnattendCtxSetString` at `0x18003014d`
- `UNATTEND!UnattendCtxSetString` at `0x18003018c`
- `UNATTEND!UnattendCtxCleanup` at `0x180030265`
- `UNATTEND!UnattendCtxCleanup` at `0x180030265`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800301c2`
- `UNATTEND!UnattendCtxSerializeToBuffer` at `0x1800301c2`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18003010e`
- `UNATTEND!UnattendCtxDeserializeBuffer` at `0x18003010e`

## string_xrefs

- `0x18003002c`: `WimLayoutCaptureImage: Capturing image from [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionWimLayout::WimLayoutCaptureImage(
        CDlpActionWimLayout *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HLOCAL hMem,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rbx
  signed int v13; // eax
  signed int v14; // edi
  __int64 v15; // rcx
  signed int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  signed int LastError; // eax
  int v23; // eax
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  int v27; // [rsp+20h] [rbp-20h]
  int v28; // [rsp+28h] [rbp-18h]
  __int64 v29; // [rsp+30h] [rbp-10h]
  __int64 v30; // [rsp+38h] [rbp-8h] BYREF
  LPVOID lpMem; // [rsp+60h] [rbp+20h] BYREF
  __int64 v32; // [rsp+78h] [rbp+38h] BYREF

  hMem = 0;
  a7 = 0;
  lpMem = 0;
  v30 = 0;
  v32 = 0;
  *((_DWORD *)this + 195) = a6;
  *((_DWORD *)this + 196) = 100;
  *(_QWORD *)((char *)this + 788) = 1;
  v10 = *((_QWORD *)this + 11);
  if ( v10 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v10, 2u, (__int64)L"WimLayoutCaptureImage: Capturing image from [%s]", a3);
  v11 = WIMCaptureImage(a2, a3, 131376);
  v12 = v11;
  if ( v11 )
  {
    v29 = v11;
    a7 = 0;
    if ( (unsigned int)WIMGetImageInformation(v11, &hMem, &a7) )
    {
      v17 = UnattendCtxDeserializeBuffer(&v32, hMem, a7);
      v14 = v17;
      if ( v17 < 0 )
      {
        v18 = *((_QWORD *)this + 11);
        if ( !v18 )
          goto LABEL_43;
        v28 = v17;
        v27 = 2288;
        goto LABEL_40;
      }
      v19 = UnattendCtxSetString(&v32, L"IMAGE\\NAME", 0, L"Windows Setup Media");
      v14 = v19;
      if ( v19 < 0 )
      {
        v18 = *((_QWORD *)this + 11);
        if ( !v18 )
          goto LABEL_43;
        v28 = v19;
        v27 = 2292;
        goto LABEL_40;
      }
      v20 = UnattendCtxSetString(&v32, L"IMAGE\\DESCRIPTION", 0, L"Windows Setup Media");
      v14 = v20;
      if ( v20 < 0 )
      {
        v18 = *((_QWORD *)this + 11);
        if ( !v18 )
          goto LABEL_43;
        v28 = v20;
        v27 = 2297;
        goto LABEL_40;
      }
      v21 = UnattendCtxSerializeToBuffer(&v32, &lpMem, &v30);
      v14 = v21;
      if ( v21 < 0 )
      {
        v18 = *((_QWORD *)this + 11);
        if ( !v18 )
          goto LABEL_43;
        v28 = v21;
        v27 = 2302;
        goto LABEL_40;
      }
      if ( !(unsigned int)WIMSetImageInformation(v12, lpMem, (unsigned int)v30) )
      {
        LastError = GetLastError();
        v14 = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v14 = -2147467259;
        }
        if ( *((_QWORD *)this + 11) )
        {
          v15 = 0;
          if ( v14 < 0 )
          {
            v28 = v14;
            v27 = 2304;
            goto LABEL_39;
          }
          goto LABEL_42;
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v14 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v14 = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        v14 = -2147467259;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v15 = 0;
        if ( v14 < 0 )
        {
          v28 = v14;
          v27 = 2284;
          goto LABEL_39;
        }
LABEL_42:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v15);
      }
    }
  }
  else
  {
    v12 = 0;
    v29 = 0;
    v13 = GetLastError();
    v14 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v14 = (unsigned __int16)v13 | 0x80070000;
    }
    else
    {
      v14 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v15 = 0;
      if ( v14 < 0 )
      {
        v28 = v14;
        v27 = 2278;
LABEL_39:
        v18 = *((_QWORD *)this + 11);
LABEL_40:
        v23 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v18,
                4u,
                (__int64)L"%s(%d): Result = 0x%X",
                L"CDlpActionWimLayout::WimLayoutCaptureImage",
                v27,
                v28,
                v29);
        v15 = (unsigned int)v23;
        if ( v23 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v23);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
  }
LABEL_43:
  UnattendCtxCleanup(&v32);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v14);
  v24 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v24);
    lpMem = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v12 )
    WIMCloseHandle(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002ffc4  mov     [rsp-18h+arg_8], rbx
0x18002ffc9  mov     [rsp-18h+arg_10], rsi
0x18002ffce  mov     [rsp-18h+arg_18], r9
0x18002ffd3  push    rbp
0x18002ffd4  push    rdi
0x18002ffd5  push    r14
0x18002ffd7  mov     rbp, rsp
0x18002ffda  sub     rsp, 40h
0x18002ffde  mov     rbx, r8
0x18002ffe1  mov     rdi, rdx
0x18002ffe4  mov     rsi, rcx
0x18002ffe7  xor     r14d, r14d
0x18002ffea  mov     [rbp+var_10], r14
0x18002ffee  mov     [rbp+hMem], r14
0x18002fff2  mov     [rbp+arg_30], r14d
0x18002fff6  mov     [rbp+lpMem], r14
0x18002fffa  mov     [rbp+var_8], r14
0x18002fffe  mov     [rbp+arg_18], r14
0x180030002  mov     eax, [rbp+arg_28]
0x180030005  mov     [rcx+30Ch], eax
0x18003000b  mov     dword ptr [rcx+310h], 64h ; 'd'
0x180030015  mov     qword ptr [rcx+314h], 1
0x180030020  mov     rcx, [rcx+58h]
0x180030024  test    rcx, rcx
0x180030027  jz      short loc_18003003C
0x180030029  mov     r9, rbx
0x18003002c  lea     r8, aWimlayoutcaptu; "WimLayoutCaptureImage: Capturing image "...
0x180030033  lea     edx, [r14+2]
0x180030037  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18003003c  mov     r8d, 20130h
0x180030042  mov     rdx, rbx
0x180030045  mov     rcx, rdi
0x180030048  call    cs:__imp_WIMCaptureImage
0x18003004e  mov     rbx, rax
0x180030051  test    rax, rax
0x180030054  jnz     short loc_1800300A1
0x180030056  mov     rbx, r14
0x180030059  mov     [rbp+var_10], rbx
0x18003005d  call    cs:__imp_GetLastError
0x180030063  mov     edi, eax
0x180030065  test    eax, eax
0x180030067  jnz     short loc_180030070
0x180030069  mov     edi, 80004005h
0x18003006e  jmp     short loc_18003007B
0x180030070  jle     short loc_18003007B
0x180030072  movzx   edi, ax
0x180030075  or      edi, 80070000h
0x18003007b  cmp     [rsi+58h], r14
0x18003007f  jz      loc_180030261
0x180030085  mov     ecx, r14d
0x180030088  test    edi, edi
0x18003008a  jns     loc_18003025C
0x180030090  mov     [rsp+40h+var_18], edi
0x180030094  mov     [rsp+40h+var_20], 8E6h
0x18003009c  jmp     loc_180030235
0x1800300a1  mov     [rbp+var_10], rbx
0x1800300a5  mov     [rbp+arg_30], r14d
0x1800300a9  lea     r8, [rbp+arg_30]
0x1800300ad  lea     rdx, [rbp+hMem]
0x1800300b1  mov     rcx, rbx
0x1800300b4  call    cs:__imp_WIMGetImageInformation
0x1800300ba  test    eax, eax
0x1800300bc  jnz     short loc_180030102
0x1800300be  call    cs:__imp_GetLastError
0x1800300c4  mov     edi, eax
0x1800300c6  test    eax, eax
0x1800300c8  jnz     short loc_1800300D1
0x1800300ca  mov     edi, 80004005h
0x1800300cf  jmp     short loc_1800300DC
0x1800300d1  jle     short loc_1800300DC
0x1800300d3  movzx   edi, ax
0x1800300d6  or      edi, 80070000h
0x1800300dc  cmp     [rsi+58h], r14
0x1800300e0  jz      loc_180030261
0x1800300e6  mov     ecx, r14d
0x1800300e9  test    edi, edi
0x1800300eb  jns     loc_18003025C
0x1800300f1  mov     [rsp+40h+var_18], edi
0x1800300f5  mov     [rsp+40h+var_20], 8ECh
0x1800300fd  jmp     loc_180030235
0x180030102  mov     r8d, [rbp+arg_30]
0x180030106  mov     rdx, [rbp+hMem]
0x18003010a  lea     rcx, [rbp+arg_18]
0x18003010e  call    cs:__imp_UnattendCtxDeserializeBuffer
0x180030114  mov     edi, eax
0x180030116  test    eax, eax
0x180030118  jns     short loc_180030138
0x18003011a  mov     rcx, [rsi+58h]
0x18003011e  test    rcx, rcx
0x180030121  jz      loc_180030261
0x180030127  mov     [rsp+40h+var_18], eax
0x18003012b  mov     [rsp+40h+var_20], 8F0h
0x180030133  jmp     loc_180030239
0x180030138  lea     r9, aWindowsSetupMe; "Windows Setup Media"
0x18003013f  xor     r8d, r8d
0x180030142  lea     rdx, aImageName; "IMAGE\\NAME"
0x180030149  lea     rcx, [rbp+arg_18]
0x18003014d  call    cs:__imp_UnattendCtxSetString
0x180030153  mov     edi, eax
0x180030155  test    eax, eax
0x180030157  jns     short loc_180030177
0x180030159  mov     rcx, [rsi+58h]
0x18003015d  test    rcx, rcx
0x180030160  jz      loc_180030261
0x180030166  mov     [rsp+40h+var_18], eax
0x18003016a  mov     [rsp+40h+var_20], 8F4h
0x180030172  jmp     loc_180030239
0x180030177  lea     r9, aWindowsSetupMe; "Windows Setup Media"
0x18003017e  xor     r8d, r8d
0x180030181  lea     rdx, aImageDescripti; "IMAGE\\DESCRIPTION"
0x180030188  lea     rcx, [rbp+arg_18]
0x18003018c  call    cs:__imp_UnattendCtxSetString
0x180030192  mov     edi, eax
0x180030194  test    eax, eax
0x180030196  jns     short loc_1800301B6
0x180030198  mov     rcx, [rsi+58h]
0x18003019c  test    rcx, rcx
0x18003019f  jz      loc_180030261
0x1800301a5  mov     [rsp+40h+var_18], eax
0x1800301a9  mov     [rsp+40h+var_20], 8F9h
0x1800301b1  jmp     loc_180030239
0x1800301b6  lea     r8, [rbp+var_8]
0x1800301ba  lea     rdx, [rbp+lpMem]
0x1800301be  lea     rcx, [rbp+arg_18]
0x1800301c2  call    cs:__imp_UnattendCtxSerializeToBuffer
0x1800301c8  mov     edi, eax
0x1800301ca  test    eax, eax
0x1800301cc  jns     short loc_1800301E9
0x1800301ce  mov     rcx, [rsi+58h]
0x1800301d2  test    rcx, rcx
0x1800301d5  jz      loc_180030261
0x1800301db  mov     [rsp+40h+var_18], eax
0x1800301df  mov     [rsp+40h+var_20], 8FEh
0x1800301e7  jmp     short loc_180030239
0x1800301e9  mov     r8d, dword ptr [rbp+var_8]
0x1800301ed  mov     rdx, [rbp+lpMem]
0x1800301f1  mov     rcx, rbx
0x1800301f4  call    cs:__imp_WIMSetImageInformation
0x1800301fa  test    eax, eax
0x1800301fc  jnz     short loc_180030261
0x1800301fe  call    cs:__imp_GetLastError
0x180030204  mov     edi, eax
0x180030206  test    eax, eax
0x180030208  jnz     short loc_180030211
0x18003020a  mov     edi, 80004005h
0x18003020f  jmp     short loc_18003021C
0x180030211  jle     short loc_18003021C
0x180030213  movzx   edi, ax
0x180030216  or      edi, 80070000h
0x18003021c  cmp     [rsi+58h], r14
0x180030220  jz      short loc_180030261
0x180030222  mov     ecx, r14d
0x180030225  test    edi, edi
0x180030227  jns     short loc_18003025C
0x180030229  mov     [rsp+40h+var_18], edi
0x18003022d  mov     [rsp+40h+var_20], 900h
0x180030235  mov     rcx, [rsi+58h]
0x180030239  lea     r9, aCdlpactionwiml_16; "CDlpActionWimLayout::WimLayoutCaptureIm"...
0x180030240  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180030247  mov     edx, 4
0x18003024c  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180030251  mov     ecx, eax
0x180030253  test    eax, eax
0x180030255  jns     short loc_18003025C
0x180030257  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003025c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030261  lea     rcx, [rbp+arg_18]
0x180030265  call    cs:__imp_UnattendCtxCleanup
0x18003026b  mov     ecx, edi
0x18003026d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180030272  nop
0x180030273  mov     rsi, [rbp+lpMem]
0x180030277  test    rsi, rsi
0x18003027a  jz      short loc_180030294
0x18003027c  call    cs:__imp_GetProcessHeap
0x180030282  mov     rcx, rax; hHeap
0x180030285  mov     r8, rsi; lpMem
0x180030288  xor     edx, edx; dwFlags
0x18003028a  call    cs:__imp_HeapFree
0x180030290  mov     [rbp+lpMem], r14
0x180030294  mov     rcx, [rbp+hMem]; hMem
0x180030298  test    rcx, rcx
0x18003029b  jz      short loc_1800302A7
0x18003029d  call    cs:__imp_LocalFree
0x1800302a3  mov     [rbp+hMem], r14
0x1800302a7  test    rbx, rbx
0x1800302aa  jz      short loc_1800302B5
0x1800302ac  mov     rcx, rbx
0x1800302af  call    cs:__imp_WIMCloseHandle
0x1800302b5  mov     eax, edi
0x1800302b7  mov     rbx, [rsp+40h+arg_8]
0x1800302bc  mov     rsi, [rsp+40h+arg_10]
0x1800302c1  add     rsp, 40h
0x1800302c5  pop     r14
0x1800302c7  pop     rdi
0x1800302c8  pop     rbp
0x1800302c9  retn
```

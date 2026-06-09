# CDlpActionLayoutUsb::PopulateWimPath(int,ushort const *,ushort const *)

- ea: `0x1800239e0`
- end: `0x180023f3c`
- name: `?PopulateWimPath@CDlpActionLayoutUsb@@AEAAJHPEBG0@Z`
- size: `1372`
- prototype: `int(CDlpActionLayoutUsb *__hidden this, int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dda0`
- `0x180023210`
- `0x180023f44`

## callees

- `0x180002898`
- `0x180007bbc`
- `0x18000aba4`
- `0x18000b9a8`
- `0x18000ea20`
- `0x180012f5c`
- `0x18001fd60`
- `0x180020468`
- `0x1800239e0`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023a8e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180023a8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ef4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e3b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023e7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ea6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ecd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023ef4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023edc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e4a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e8e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023eb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023edc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023f03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023a98`

## string_xrefs

- `0x180023b1e`: `CDlpActionLayoutUsb::PopulateWimPath`
- `0x180023c0a`: `CDlpActionLayoutUsb::PopulateWimPath`
- `0x180023e06`: `CDlpActionLayoutUsb::PopulateWimPath`
- `0x180023c54`: `LayoutUsb: Populating WIM Path: [%s] -> [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CDlpActionLayoutUsb::PopulateWimPath(
        CDlpActionLayoutUsb *this,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // r13
  char *v9; // rsi
  signed int v10; // edi
  __int64 v11; // rcx
  signed int LastError; // eax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  int StringCch; // eax
  int Internal; // eax
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
  char *v26; // r14
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v34; // rax
  __int64 v35; // rbx
  HANDLE v36; // rax
  __int64 v37; // rbx
  HANDLE v38; // rax
  __int64 v39; // rbx
  HANDLE v40; // rax
  __int64 v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+28h] [rbp-D8h]
  __int64 v44; // [rsp+30h] [rbp-D0h] BYREF
  char *v45; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-C0h]
  __int64 v47; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v50; // [rsp+60h] [rbp-A0h]
  WCHAR Buffer[520]; // [rsp+70h] [rbp-90h] BYREF

  v49 = 0;
  v48 = 0;
  v50 = 0;
  v46 = 0;
  v8 = 0;
  v47 = 0;
  v9 = 0;
  v45 = 0;
  if ( !a3 )
  {
    v10 = -2147024809;
    v11 = *((_QWORD *)this + 11);
    if ( !v11 )
      goto LABEL_67;
    v43 = -2147024809;
    LODWORD(v42) = 2485;
    goto LABEL_64;
  }
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( !GetFullPathNameW(a3, 0x208u, Buffer, 0) )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v13 = 0;
      if ( v10 >= 0 )
      {
LABEL_66:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
        goto LABEL_67;
      }
      v43 = v10;
      LODWORD(v42) = 2490;
      v11 = *((_QWORD *)this + 11);
LABEL_64:
      v32 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v11,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::PopulateWimPath",
              v42,
              v43,
              v44);
      v13 = (unsigned int)v32;
      if ( v32 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v32);
      goto LABEL_66;
    }
    goto LABEL_67;
  }
  v14 = CMiscHelpersT<CEmptyType>::ParseFileName(Buffer, (__int64)&v47);
  v10 = v14;
  if ( v14 < 0 )
  {
    v15 = *((_QWORD *)this + 11);
    if ( v15 )
    {
      LODWORD(v42) = 2495;
      v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v15,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::PopulateWimPath",
              v42,
              v14);
      v17 = (unsigned int)v16;
      if ( v16 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
    }
    v8 = v47;
    goto LABEL_67;
  }
  v8 = v47;
  if ( a4 )
  {
    LODWORD(v44) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a4, &v44);
    v10 = StringCch;
    if ( StringCch >= 0 )
    {
      Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a4);
      v10 = Internal;
      if ( Internal < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal);
      v9 = v45;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
    if ( v10 < 0 )
    {
      v11 = *((_QWORD *)this + 11);
      if ( !v11 )
        goto LABEL_67;
      v43 = v10;
      LODWORD(v42) = 2501;
      goto LABEL_64;
    }
  }
  else
  {
    v20 = CMiscHelpersT<CEmptyType>::CombinePath(L"sources", v46, v47, &v45);
    v10 = v20;
    if ( v20 < 0 )
    {
      v21 = *((_QWORD *)this + 11);
      if ( v21 )
      {
        LODWORD(v42) = 2505;
        v22 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v21,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::PopulateWimPath",
                v42,
                v20);
        v23 = (unsigned int)v22;
        if ( v22 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v22);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v23);
      }
      v9 = v45;
      goto LABEL_67;
    }
    v9 = v45;
  }
  v24 = *((_QWORD *)this + 11);
  if ( v24 )
    CDlpLogT<CEmptyType>::DlpLogFormat(v24, 2, L"LayoutUsb: Populating WIM Path: [%s] -> [%s]", Buffer, v9);
  LODWORD(v44) = 0;
  v25 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v44);
  v10 = v25;
  if ( v25 < 0
    || (v25 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer),
        v10 = v25,
        v25 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v25);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v10 < 0 )
  {
    v11 = *((_QWORD *)this + 11);
    if ( !v11 )
      goto LABEL_67;
    v43 = v10;
    LODWORD(v42) = 2510;
    goto LABEL_64;
  }
  if ( !v9 )
  {
    v26 = 0;
    goto LABEL_44;
  }
  v26 = v9;
  LODWORD(v44) = 0;
  v27 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v9, &v44);
  v10 = v27;
  if ( v27 >= 0 )
  {
LABEL_44:
    v27 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v26);
    v10 = v27;
    if ( v27 >= 0 )
      goto LABEL_46;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v27);
LABEL_46:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v10 < 0 )
  {
    v11 = *((_QWORD *)this + 11);
    if ( !v11 )
      goto LABEL_67;
    v43 = v10;
    LODWORD(v42) = 2511;
    goto LABEL_64;
  }
  if ( a2 )
  {
    v28 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1032, &v49);
    v10 = v28;
    if ( v28 < 0 )
    {
      v11 = *((_QWORD *)this + 11);
      if ( !v11 )
        goto LABEL_67;
      v43 = v28;
      LODWORD(v42) = 2515;
      goto LABEL_64;
    }
    v29 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1048, &v48);
    v10 = v29;
    if ( v29 < 0 )
    {
      v11 = *((_QWORD *)this + 11);
      if ( v11 )
      {
        v43 = v29;
        LODWORD(v42) = 2516;
        goto LABEL_64;
      }
    }
  }
  else
  {
    v30 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1000, &v49);
    v10 = v30;
    if ( v30 < 0 )
    {
      v11 = *((_QWORD *)this + 11);
      if ( !v11 )
        goto LABEL_67;
      v43 = v30;
      LODWORD(v42) = 2520;
      goto LABEL_64;
    }
    v31 = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append((char *)this + 1016, &v48);
    v10 = v31;
    if ( v31 < 0 )
    {
      v11 = *((_QWORD *)this + 11);
      if ( v11 )
      {
        v43 = v31;
        LODWORD(v42) = 2521;
        goto LABEL_64;
      }
    }
  }
LABEL_67:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v10);
  if ( v9 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v9 - 4);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v8 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, (LPVOID)(v8 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v35 = v50;
  if ( v50 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, (LPVOID)(v35 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v37 = v48;
  if ( v48 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, (LPVOID)(v37 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v39 = v49;
  if ( v49 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, (LPVOID)(v39 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800239e0  mov     [rsp-8+arg_8], rbx
0x1800239e5  push    rbp
0x1800239e6  push    rsi
0x1800239e7  push    rdi
0x1800239e8  push    r12
0x1800239ea  push    r13
0x1800239ec  push    r14
0x1800239ee  push    r15
0x1800239f0  lea     rbp, [rsp-390h]
0x1800239f8  sub     rsp, 490h
0x1800239ff  mov     rax, cs:__security_cookie
0x180023a06  xor     rax, rsp
0x180023a09  mov     [rbp+3C0h+var_40], rax
0x180023a10  mov     r14, r9
0x180023a13  mov     rdi, r8
0x180023a16  mov     r12d, edx
0x180023a19  mov     rbx, rcx
0x180023a1c  xor     eax, eax
0x180023a1e  mov     [rsp+4C0h+var_468], rax
0x180023a23  mov     [rsp+4C0h+var_470], rax
0x180023a28  mov     [rsp+4C0h+var_460], rax
0x180023a2d  mov     r15d, eax
0x180023a30  mov     [rsp+4C0h+var_480], rax
0x180023a35  mov     r13d, eax
0x180023a38  mov     [rsp+4C0h+var_478], rax
0x180023a3d  mov     esi, eax
0x180023a3f  mov     [rsp+4C0h+var_488], rax
0x180023a44  test    r8, r8
0x180023a47  jnz     short loc_180023A6C
0x180023a49  mov     edi, 80070057h
0x180023a4e  mov     rcx, [rcx+58h]
0x180023a52  test    rcx, rcx
0x180023a55  jz      loc_180023E2E
0x180023a5b  mov     [rsp+4C0h+var_498], edi
0x180023a5f  mov     dword ptr [rsp+4C0h+var_4A0], 9B5h
0x180023a67  jmp     loc_180023E06
0x180023a6c  xor     edx, edx; Val
0x180023a6e  mov     r8d, 410h; Size
0x180023a74  lea     rcx, [rsp+4C0h+Buffer]; void *
0x180023a79  call    memset_0
0x180023a7e  xor     r9d, r9d; lpFilePart
0x180023a81  lea     r8, [rsp+4C0h+Buffer]; lpBuffer
0x180023a86  mov     edx, 208h; nBufferLength
0x180023a8b  mov     rcx, rdi; lpFileName
0x180023a8e  call    cs:__imp_GetFullPathNameW
0x180023a94  test    eax, eax
0x180023a96  jnz     short loc_180023AE0
0x180023a98  call    cs:__imp_GetLastError
0x180023a9e  mov     edi, eax
0x180023aa0  test    eax, eax
0x180023aa2  jnz     short loc_180023AAB
0x180023aa4  mov     edi, 80004005h
0x180023aa9  jmp     short loc_180023AB6
0x180023aab  jle     short loc_180023AB6
0x180023aad  movzx   edi, ax
0x180023ab0  or      edi, 80070000h
0x180023ab6  cmp     qword ptr [rbx+58h], 0
0x180023abb  jz      loc_180023E2E
0x180023ac1  xor     ecx, ecx
0x180023ac3  test    edi, edi
0x180023ac5  jns     loc_180023E29
0x180023acb  mov     [rsp+4C0h+var_498], edi
0x180023acf  mov     dword ptr [rsp+4C0h+var_4A0], 9BAh
0x180023ad7  mov     rcx, [rbx+58h]
0x180023adb  jmp     loc_180023E06
0x180023ae0  lea     rax, [rsp+4C0h+var_478]
0x180023ae5  mov     [rsp+4C0h+var_4A0], rax; __int64
0x180023aea  lea     r9, [rsp+4C0h+var_480]
0x180023aef  lea     r8, [rsp+4C0h+var_460]
0x180023af4  lea     rdx, [rsp+4C0h+var_490]
0x180023af9  lea     rcx, [rsp+4C0h+Buffer]; Src
0x180023afe  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x180023b03  mov     edi, eax
0x180023b05  test    eax, eax
0x180023b07  jns     short loc_180023B55
0x180023b09  mov     rcx, [rbx+58h]
0x180023b0d  test    rcx, rcx
0x180023b10  jz      short loc_180023B46
0x180023b12  mov     [rsp+4C0h+var_498], eax
0x180023b16  mov     dword ptr [rsp+4C0h+var_4A0], 9BFh
0x180023b1e  lea     r9, aCdlpactionlayo_7; "CDlpActionLayoutUsb::PopulateWimPath"
0x180023b25  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180023b2c  mov     edx, 4
0x180023b31  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180023b36  mov     ecx, eax
0x180023b38  test    eax, eax
0x180023b3a  jns     short loc_180023B41
0x180023b3c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023b41  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023b46  mov     r15, [rsp+4C0h+var_480]
0x180023b4b  mov     r13, [rsp+4C0h+var_478]
0x180023b50  jmp     loc_180023E2E
0x180023b55  mov     r15, [rsp+4C0h+var_480]
0x180023b5a  mov     r13, [rsp+4C0h+var_478]
0x180023b5f  test    r14, r14
0x180023b62  jz      short loc_180023BD8
0x180023b64  mov     dword ptr [rsp+4C0h+var_490], 0
0x180023b6c  lea     rdx, [rsp+4C0h+var_490]
0x180023b71  mov     rcx, r14
0x180023b74  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180023b79  mov     edi, eax
0x180023b7b  test    eax, eax
0x180023b7d  jns     short loc_180023B88
0x180023b7f  mov     ecx, eax
0x180023b81  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023b86  jmp     short loc_180023BAB
0x180023b88  lea     r8, [rsp+4C0h+var_488]
0x180023b8d  mov     edx, dword ptr [rsp+4C0h+var_490]
0x180023b91  mov     rcx, r14; Src
0x180023b94  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180023b99  mov     edi, eax
0x180023b9b  test    eax, eax
0x180023b9d  jns     short loc_180023BA6
0x180023b9f  mov     ecx, eax
0x180023ba1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023ba6  mov     rsi, [rsp+4C0h+var_488]
0x180023bab  mov     ecx, edi
0x180023bad  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023bb2  test    edi, edi
0x180023bb4  jns     loc_180023C41
0x180023bba  mov     rcx, [rbx+58h]
0x180023bbe  test    rcx, rcx
0x180023bc1  jz      loc_180023E2E
0x180023bc7  mov     [rsp+4C0h+var_498], edi
0x180023bcb  mov     dword ptr [rsp+4C0h+var_4A0], 9C5h
0x180023bd3  jmp     loc_180023E06
0x180023bd8  lea     r9, [rsp+4C0h+var_488]
0x180023bdd  mov     r8, r13
0x180023be0  mov     rdx, r15
0x180023be3  lea     rcx, aSources; "sources"
0x180023bea  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180023bef  mov     edi, eax
0x180023bf1  test    eax, eax
0x180023bf3  jns     short loc_180023C3C
0x180023bf5  mov     rcx, [rbx+58h]
0x180023bf9  test    rcx, rcx
0x180023bfc  jz      short loc_180023C32
0x180023bfe  mov     [rsp+4C0h+var_498], eax
0x180023c02  mov     dword ptr [rsp+4C0h+var_4A0], 9C9h
0x180023c0a  lea     r9, aCdlpactionlayo_7; "CDlpActionLayoutUsb::PopulateWimPath"
0x180023c11  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180023c18  mov     edx, 4
0x180023c1d  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180023c22  mov     ecx, eax
0x180023c24  test    eax, eax
0x180023c26  jns     short loc_180023C2D
0x180023c28  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023c2d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023c32  mov     rsi, [rsp+4C0h+var_488]
0x180023c37  jmp     loc_180023E2E
0x180023c3c  mov     rsi, [rsp+4C0h+var_488]
0x180023c41  mov     rcx, [rbx+58h]
0x180023c45  test    rcx, rcx
0x180023c48  jz      short loc_180023C65
0x180023c4a  mov     [rsp+4C0h+var_4A0], rsi
0x180023c4f  lea     r9, [rsp+4C0h+Buffer]
0x180023c54  lea     r8, aLayoutusbPopul; "LayoutUsb: Populating WIM Path: [%s] ->"...
0x180023c5b  mov     edx, 2
0x180023c60  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180023c65  mov     dword ptr [rsp+4C0h+var_490], 0
0x180023c6d  lea     rdx, [rsp+4C0h+var_490]
0x180023c72  lea     rcx, [rsp+4C0h+Buffer]
0x180023c77  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180023c7c  mov     edi, eax
0x180023c7e  test    eax, eax
0x180023c80  js      short loc_180023C9B
0x180023c82  lea     r8, [rsp+4C0h+var_468]
0x180023c87  mov     edx, dword ptr [rsp+4C0h+var_490]
0x180023c8b  lea     rcx, [rsp+4C0h+Buffer]; Src
0x180023c90  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180023c95  mov     edi, eax
0x180023c97  test    eax, eax
0x180023c99  jns     short loc_180023CA2
0x180023c9b  mov     ecx, eax
0x180023c9d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023ca2  mov     ecx, edi
0x180023ca4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023ca9  test    edi, edi
0x180023cab  jns     short loc_180023CCB
0x180023cad  mov     rcx, [rbx+58h]
0x180023cb1  test    rcx, rcx
0x180023cb4  jz      loc_180023E2E
0x180023cba  mov     [rsp+4C0h+var_498], edi
0x180023cbe  mov     dword ptr [rsp+4C0h+var_4A0], 9CEh
0x180023cc6  jmp     loc_180023E06
0x180023ccb  test    rsi, rsi
0x180023cce  jnz     short loc_180023D18
0x180023cd0  xor     r14d, r14d
0x180023cd3  xor     edx, edx
0x180023cd5  lea     r8, [rsp+4C0h+var_470]
0x180023cda  mov     rcx, r14; Src
0x180023cdd  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x180023ce2  mov     edi, eax
0x180023ce4  test    eax, eax
0x180023ce6  jns     short loc_180023CEF
0x180023ce8  mov     ecx, eax
0x180023cea  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023cef  mov     ecx, edi
0x180023cf1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023cf6  test    edi, edi
0x180023cf8  jns     short loc_180023D41
0x180023cfa  mov     rcx, [rbx+58h]
0x180023cfe  test    rcx, rcx
0x180023d01  jz      loc_180023E2E
0x180023d07  mov     [rsp+4C0h+var_498], edi
0x180023d0b  mov     dword ptr [rsp+4C0h+var_4A0], 9CFh
0x180023d13  jmp     loc_180023E06
0x180023d18  mov     r14, rsi
0x180023d1b  mov     dword ptr [rsp+4C0h+var_490], 0
0x180023d23  test    rsi, rsi
0x180023d26  jz      short loc_180023CD3
0x180023d28  lea     rdx, [rsp+4C0h+var_490]
0x180023d2d  mov     rcx, rsi
0x180023d30  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x180023d35  mov     edi, eax
0x180023d37  test    eax, eax
0x180023d39  js      short loc_180023CE8
0x180023d3b  mov     edx, dword ptr [rsp+4C0h+var_490]
0x180023d3f  jmp     short loc_180023CD5
0x180023d41  lea     rdx, [rsp+4C0h+var_468]
0x180023d46  test    r12d, r12d
0x180023d49  jz      short loc_180023DB1
0x180023d4b  lea     rcx, [rbx+408h]
0x180023d52  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180023d57  mov     edi, eax
0x180023d59  test    eax, eax
0x180023d5b  jns     short loc_180023D7B
0x180023d5d  mov     rcx, [rbx+58h]
0x180023d61  test    rcx, rcx
0x180023d64  jz      loc_180023E2E
0x180023d6a  mov     [rsp+4C0h+var_498], eax
0x180023d6e  mov     dword ptr [rsp+4C0h+var_4A0], 9D3h
0x180023d76  jmp     loc_180023E06
0x180023d7b  lea     rcx, [rbx+418h]
0x180023d82  lea     rdx, [rsp+4C0h+var_470]
0x180023d87  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180023d8c  mov     edi, eax
0x180023d8e  test    eax, eax
0x180023d90  jns     loc_180023E2E
0x180023d96  mov     rcx, [rbx+58h]
0x180023d9a  test    rcx, rcx
0x180023d9d  jz      loc_180023E2E
0x180023da3  mov     [rsp+4C0h+var_498], eax
0x180023da7  mov     dword ptr [rsp+4C0h+var_4A0], 9D4h
0x180023daf  jmp     short loc_180023E06
0x180023db1  lea     rcx, [rbx+3E8h]
0x180023db8  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180023dbd  mov     edi, eax
0x180023dbf  test    eax, eax
0x180023dc1  jns     short loc_180023DDA
0x180023dc3  mov     rcx, [rbx+58h]
0x180023dc7  test    rcx, rcx
0x180023dca  jz      short loc_180023E2E
0x180023dcc  mov     [rsp+4C0h+var_498], eax
0x180023dd0  mov     dword ptr [rsp+4C0h+var_4A0], 9D8h
0x180023dd8  jmp     short loc_180023E06
0x180023dda  lea     rcx, [rbx+3F8h]
0x180023de1  lea     rdx, [rsp+4C0h+var_470]
0x180023de6  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x180023deb  mov     edi, eax
0x180023ded  test    eax, eax
0x180023def  jns     short loc_180023E2E
0x180023df1  mov     rcx, [rbx+58h]
0x180023df5  test    rcx, rcx
0x180023df8  jz      short loc_180023E2E
0x180023dfa  mov     [rsp+4C0h+var_498], eax
0x180023dfe  mov     dword ptr [rsp+4C0h+var_4A0], 9D9h
0x180023e06  lea     r9, aCdlpactionlayo_7; "CDlpActionLayoutUsb::PopulateWimPath"
0x180023e0d  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180023e14  mov     edx, 4
0x180023e19  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180023e1e  mov     ecx, eax
0x180023e20  test    eax, eax
0x180023e22  jns     short loc_180023E29
0x180023e24  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023e29  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023e2e  mov     ecx, edi
0x180023e30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023e35  nop
0x180023e36  test    rsi, rsi
0x180023e39  jz      short loc_180023E58
0x180023e3b  call    cs:__imp_GetProcessHeap
0x180023e41  mov     rcx, rax; hHeap
0x180023e44  lea     r8, [rsi-4]; lpMem
0x180023e48  xor     edx, edx; dwFlags
0x180023e4a  call    cs:__imp_HeapFree
0x180023e50  xor     ecx, ecx
0x180023e52  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023e57  nop
0x180023e58  test    r13, r13
0x180023e5b  jz      short loc_180023E7A
0x180023e5d  call    cs:__imp_GetProcessHeap
0x180023e63  mov     rcx, rax; hHeap
0x180023e66  lea     r8, [r13-4]; lpMem
0x180023e6a  xor     edx, edx; dwFlags
0x180023e6c  call    cs:__imp_HeapFree
0x180023e72  xor     ecx, ecx
0x180023e74  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180023e79  nop
0x180023e7a  test    r15, r15
  ... truncated ...
```

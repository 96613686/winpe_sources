# CDlpActionLayoutUsb::PopulateBootPaths(void)

- ea: `0x180020cb4`
- end: `0x180021171`
- name: `?PopulateBootPaths@CDlpActionLayoutUsb@@AEAAJXZ`
- size: `1213`
- prototype: `__int64 __fastcall(CDlpActionLayoutUsb *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001dda0`

## callees

- `0x18000aba4`
- `0x18000b9a8`
- `0x180012f5c`
- `0x18001fd60`
- `0x180020a70`
- `0x180020cb4`
- `0x180028640`
- `0x18007ec9a`
- `0x18007ed40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180020d1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180020d1f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020fe6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002100e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180020fe6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002100e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800210e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021128`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800210e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021106`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021128`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021137`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800210f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021115`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d29`
- `bcd!SyspartGetSystemPartition` at `0x180020ebd`
- `bcd!SyspartGetSystemPartition` at `0x180020ebd`

## string_xrefs

- `0x180020da5`: `CDlpActionLayoutUsb::PopulateBootPaths`
- `0x180020f43`: `CDlpActionLayoutUsb::PopulateBootPaths`
- `0x180020fac`: `CDlpActionLayoutUsb::PopulateBootPaths`
- `0x1800210af`: `CDlpActionLayoutUsb::PopulateBootPaths`
- `0x180020ed5`: `LayoutUsb: Failed to run SyspartGetSystemPartition with Error [0x%08x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpActionLayoutUsb::PopulateBootPaths(CDlpActionLayoutUsb *this)
{
  unsigned __int16 *v2; // r15
  const WCHAR *v3; // r14
  unsigned __int16 *v4; // r13
  signed int LastError; // eax
  int v6; // edi
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  int v15; // eax
  unsigned int SystemPartition; // eax
  unsigned int v17; // edi
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  DWORD FileAttributesW; // esi
  int v28; // esi
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // eax
  int v33; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v35; // rax
  HANDLE v36; // rax
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v40; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v41; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[520]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v45[1040]; // [rsp+460h] [rbp+360h] BYREF

  v2 = 0;
  v40 = 0;
  v3 = 0;
  lpFileName = 0;
  v4 = 0;
  v41 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( GetSystemWindowsDirectoryW(Buffer, 0x208u) )
  {
    v9 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"Boot", 0, &v40);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v2 = v40;
      v13 = CDlpActionLayoutUsb::PopulateBootPath(this, v40, L"DVD\\PCAT\\BCD", L"boot\\BCD");
      v6 = v13;
      if ( v13 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_60;
        v39 = v13;
        v38 = 1956;
        goto LABEL_57;
      }
      v14 = CDlpActionLayoutUsb::PopulateBootPath(this, v2, L"DVD\\EFI\\boot.sdi", L"boot\\boot.sdi");
      v6 = v14;
      if ( v14 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_60;
        v39 = v14;
        v38 = 1960;
        goto LABEL_57;
      }
      v15 = CDlpActionLayoutUsb::PopulateBootPath(this, v2, L"DVD\\EFI\\BCD", L"efi\\microsoft\\boot\\BCD");
      v6 = v15;
      if ( v15 < 0 )
      {
        v8 = *((_QWORD *)this + 11);
        if ( !v8 )
          goto LABEL_60;
        v39 = v15;
        v38 = 1961;
        goto LABEL_57;
      }
      v43 = 0;
      memset_0(v45, 0, sizeof(v45));
      SystemPartition = SyspartGetSystemPartition(v45, 520, &v43);
      v17 = SystemPartition;
      if ( SystemPartition )
      {
        v18 = *((_QWORD *)this + 11);
        if ( v18 )
          CDlpLogT<CEmptyType>::DlpLogFormat(
            v18,
            4,
            L"LayoutUsb: Failed to run SyspartGetSystemPartition with Error [0x%08x]",
            SystemPartition);
        v6 = v17 | 0x10000000;
        if ( v6 < 0 )
        {
          v8 = *((_QWORD *)this + 11);
          if ( v8 )
          {
            v39 = v6;
            v38 = 1974;
            goto LABEL_57;
          }
        }
      }
      else
      {
        v19 = STRAPI_Format(&v41, L"\\\\?\\GLOBALROOT%s", v45);
        v6 = v19;
        if ( v19 >= 0 )
        {
          v4 = v41;
          v23 = CMiscHelpersT<CEmptyType>::CombinePath(v41, L"EFI\\Microsoft\\Boot\\Policies", 0, &lpFileName);
          v6 = v23;
          if ( v23 >= 0 )
          {
            v3 = lpFileName;
            FileAttributesW = GetFileAttributesW(lpFileName);
            if ( FileAttributesW == -1 )
              v28 = 0;
            else
              v28 = (FileAttributesW >> 4) & 1;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            v29 = GetFileAttributesW(v3);
            v6 = v29 != -1 && (v29 & 0x10) == 0;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            if ( v28 || v6 )
            {
              v31 = *((_QWORD *)this + 11);
              if ( v31 )
                CDlpLogT<CEmptyType>::DlpLogFormat(v31, 2, L"LayoutUsb: OCDUS blob [%s] exists, back up into USB", v3);
              v32 = CDlpActionLayoutUsb::PopulateBootPath(
                      this,
                      v4,
                      L"EFI\\Microsoft\\Boot\\Policies",
                      L"OCDUS\\Policies");
              v6 = v32;
              if ( v32 < 0 )
              {
                v8 = *((_QWORD *)this + 11);
                if ( v8 )
                {
                  v39 = v32;
                  v38 = 1989;
                  goto LABEL_57;
                }
              }
            }
            else
            {
              v30 = *((_QWORD *)this + 11);
              if ( v30 )
                CDlpLogT<CEmptyType>::DlpLogFormat(v30, 2, L"LayoutUsb: OCDUS blob [%s] does not exist", v3);
            }
          }
          else
          {
            v24 = *((_QWORD *)this + 11);
            if ( v24 )
            {
              v25 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v24,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpActionLayoutUsb::PopulateBootPaths",
                      1979,
                      v23);
              v26 = (unsigned int)v25;
              if ( v25 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v25);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
            }
            v3 = lpFileName;
          }
        }
        else
        {
          v20 = *((_QWORD *)this + 11);
          if ( v20 )
          {
            v21 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v20,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpActionLayoutUsb::PopulateBootPaths",
                    1978,
                    v19);
            v22 = (unsigned int)v21;
            if ( v21 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v21);
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v22);
          }
          v4 = v41;
        }
      }
    }
    else
    {
      v10 = *((_QWORD *)this + 11);
      if ( v10 )
      {
        v11 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v10,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpActionLayoutUsb::PopulateBootPaths",
                1952,
                v9);
        v12 = (unsigned int)v11;
        if ( v11 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v11);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v12);
      }
      v2 = v40;
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v6 = -2147467259;
    }
    if ( *((_QWORD *)this + 11) )
    {
      v7 = 0;
      if ( v6 >= 0 )
      {
LABEL_59:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
        goto LABEL_60;
      }
      v39 = v6;
      v38 = 1951;
      v8 = *((_QWORD *)this + 11);
LABEL_57:
      v33 = CDlpLogT<CEmptyType>::DlpLogFormat(
              v8,
              4,
              L"%s(%d): Result = 0x%X",
              L"CDlpActionLayoutUsb::PopulateBootPaths",
              v38,
              v39);
      v7 = (unsigned int)v33;
      if ( v33 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v33);
      goto LABEL_59;
    }
  }
LABEL_60:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v6);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v2 )
  {
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v2 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020cb4  mov     [rsp-8+arg_8], rbx
0x180020cb9  mov     [rsp-8+arg_10], rsi
0x180020cbe  push    rbp
0x180020cbf  push    rdi
0x180020cc0  push    r13
0x180020cc2  push    r14
0x180020cc4  push    r15
0x180020cc6  lea     rbp, [rsp-780h]
0x180020cce  sub     rsp, 880h
0x180020cd5  mov     rax, cs:__security_cookie
0x180020cdc  xor     rax, rsp
0x180020cdf  mov     [rbp+7A0h+var_30], rax
0x180020ce6  mov     rbx, rcx
0x180020ce9  xor     r15d, r15d
0x180020cec  mov     [rsp+8A0h+var_870], r15
0x180020cf1  xor     r14d, r14d
0x180020cf4  mov     [rsp+8A0h+lpFileName], r14
0x180020cf9  xor     r13d, r13d
0x180020cfc  mov     [rsp+8A0h+var_868], r13
0x180020d01  mov     esi, 410h
0x180020d06  mov     r8d, esi; Size
0x180020d09  xor     edx, edx; Val
0x180020d0b  lea     rcx, [rsp+8A0h+Buffer]; void *
0x180020d10  call    memset_0
0x180020d15  mov     edx, 208h; uSize
0x180020d1a  lea     rcx, [rsp+8A0h+Buffer]; lpBuffer
0x180020d1f  call    cs:__imp_GetSystemWindowsDirectoryW
0x180020d25  test    eax, eax
0x180020d27  jnz     short loc_180020D71
0x180020d29  call    cs:__imp_GetLastError
0x180020d2f  mov     edi, eax
0x180020d31  test    eax, eax
0x180020d33  jnz     short loc_180020D3C
0x180020d35  mov     edi, 80004005h
0x180020d3a  jmp     short loc_180020D47
0x180020d3c  jle     short loc_180020D47
0x180020d3e  movzx   edi, ax
0x180020d41  or      edi, 80070000h
0x180020d47  cmp     qword ptr [rbx+58h], 0
0x180020d4c  jz      loc_1800210D7
0x180020d52  xor     ecx, ecx
0x180020d54  test    edi, edi
0x180020d56  jns     loc_1800210D2
0x180020d5c  mov     [rsp+8A0h+var_878], edi
0x180020d60  mov     [rsp+8A0h+var_880], 79Fh
0x180020d68  mov     rcx, [rbx+58h]
0x180020d6c  jmp     loc_1800210AF
0x180020d71  lea     r9, [rsp+8A0h+var_870]
0x180020d76  xor     r8d, r8d
0x180020d79  lea     rdx, aBoot; "Boot"
0x180020d80  lea     rcx, [rsp+8A0h+Buffer]
0x180020d85  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180020d8a  mov     edi, eax
0x180020d8c  test    eax, eax
0x180020d8e  jns     short loc_180020DD7
0x180020d90  mov     rcx, [rbx+58h]
0x180020d94  test    rcx, rcx
0x180020d97  jz      short loc_180020DCD
0x180020d99  mov     [rsp+8A0h+var_878], eax
0x180020d9d  mov     [rsp+8A0h+var_880], 7A0h
0x180020da5  lea     r9, aCdlpactionlayo_21; "CDlpActionLayoutUsb::PopulateBootPaths"
0x180020dac  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180020db3  mov     edx, 4
0x180020db8  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180020dbd  mov     ecx, eax
0x180020dbf  test    eax, eax
0x180020dc1  jns     short loc_180020DC8
0x180020dc3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020dc8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020dcd  mov     r15, [rsp+8A0h+var_870]
0x180020dd2  jmp     loc_1800210D7
0x180020dd7  mov     r15, [rsp+8A0h+var_870]
0x180020ddc  lea     r9, aBootBcd; "boot\\BCD"
0x180020de3  lea     r8, aDvdPcatBcd; "DVD\\PCAT\\BCD"
0x180020dea  mov     rdx, r15; unsigned __int16 *
0x180020ded  mov     rcx, rbx; this
0x180020df0  call    ?PopulateBootPath@CDlpActionLayoutUsb@@AEAAJPEBG00@Z; CDlpActionLayoutUsb::PopulateBootPath(ushort const *,ushort const *,ushort const *)
0x180020df5  mov     edi, eax
0x180020df7  test    eax, eax
0x180020df9  jns     short loc_180020E19
0x180020dfb  mov     rcx, [rbx+58h]
0x180020dff  test    rcx, rcx
0x180020e02  jz      loc_1800210D7
0x180020e08  mov     [rsp+8A0h+var_878], eax
0x180020e0c  mov     [rsp+8A0h+var_880], 7A4h
0x180020e14  jmp     loc_1800210AF
0x180020e19  lea     r9, aBootBootSdi; "boot\\boot.sdi"
0x180020e20  lea     r8, aDvdEfiBootSdi; "DVD\\EFI\\boot.sdi"
0x180020e27  mov     rdx, r15; unsigned __int16 *
0x180020e2a  mov     rcx, rbx; this
0x180020e2d  call    ?PopulateBootPath@CDlpActionLayoutUsb@@AEAAJPEBG00@Z; CDlpActionLayoutUsb::PopulateBootPath(ushort const *,ushort const *,ushort const *)
0x180020e32  mov     edi, eax
0x180020e34  test    eax, eax
0x180020e36  jns     short loc_180020E56
0x180020e38  mov     rcx, [rbx+58h]
0x180020e3c  test    rcx, rcx
0x180020e3f  jz      loc_1800210D7
0x180020e45  mov     [rsp+8A0h+var_878], eax
0x180020e49  mov     [rsp+8A0h+var_880], 7A8h
0x180020e51  jmp     loc_1800210AF
0x180020e56  lea     r9, aEfiMicrosoftBo_0; "efi\\microsoft\\boot\\BCD"
0x180020e5d  lea     r8, aDvdEfiBcd; "DVD\\EFI\\BCD"
0x180020e64  mov     rdx, r15; unsigned __int16 *
0x180020e67  mov     rcx, rbx; this
0x180020e6a  call    ?PopulateBootPath@CDlpActionLayoutUsb@@AEAAJPEBG00@Z; CDlpActionLayoutUsb::PopulateBootPath(ushort const *,ushort const *,ushort const *)
0x180020e6f  mov     edi, eax
0x180020e71  test    eax, eax
0x180020e73  jns     short loc_180020E93
0x180020e75  mov     rcx, [rbx+58h]
0x180020e79  test    rcx, rcx
0x180020e7c  jz      loc_1800210D7
0x180020e82  mov     [rsp+8A0h+var_878], eax
0x180020e86  mov     [rsp+8A0h+var_880], 7A9h
0x180020e8e  jmp     loc_1800210AF
0x180020e93  mov     [rsp+8A0h+var_858], 0
0x180020e9b  mov     r8, rsi; Size
0x180020e9e  xor     edx, edx; Val
0x180020ea0  lea     rcx, [rbp+7A0h+var_440]; void *
0x180020ea7  call    memset_0
0x180020eac  lea     r8, [rsp+8A0h+var_858]
0x180020eb1  mov     edx, 208h
0x180020eb6  lea     rcx, [rbp+7A0h+var_440]
0x180020ebd  call    cs:__imp_SyspartGetSystemPartition
0x180020ec3  mov     edi, eax
0x180020ec5  test    eax, eax
0x180020ec7  jz      short loc_180020F10
0x180020ec9  mov     rcx, [rbx+58h]
0x180020ecd  test    rcx, rcx
0x180020ed0  jz      short loc_180020EE6
0x180020ed2  mov     r9d, eax
0x180020ed5  lea     r8, aLayoutusbFaile_3; "LayoutUsb: Failed to run SyspartGetSyst"...
0x180020edc  mov     edx, 4
0x180020ee1  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180020ee6  or      edi, 10000000h
0x180020eec  jge     loc_1800210D7
0x180020ef2  mov     rcx, [rbx+58h]
0x180020ef6  test    rcx, rcx
0x180020ef9  jz      loc_1800210D7
0x180020eff  mov     [rsp+8A0h+var_878], edi
0x180020f03  mov     [rsp+8A0h+var_880], 7B6h
0x180020f0b  jmp     loc_1800210AF
0x180020f10  lea     r8, [rbp+7A0h+var_440]
0x180020f17  lea     rdx, aGlobalrootS; "\\\\?\\GLOBALROOT%s"
0x180020f1e  lea     rcx, [rsp+8A0h+var_868]; unsigned __int16 **
0x180020f23  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180020f28  mov     edi, eax
0x180020f2a  test    eax, eax
0x180020f2c  jns     short loc_180020F75
0x180020f2e  mov     rcx, [rbx+58h]
0x180020f32  test    rcx, rcx
0x180020f35  jz      short loc_180020F6B
0x180020f37  mov     [rsp+8A0h+var_878], eax
0x180020f3b  mov     [rsp+8A0h+var_880], 7BAh
0x180020f43  lea     r9, aCdlpactionlayo_21; "CDlpActionLayoutUsb::PopulateBootPaths"
0x180020f4a  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180020f51  mov     edx, 4
0x180020f56  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180020f5b  mov     ecx, eax
0x180020f5d  test    eax, eax
0x180020f5f  jns     short loc_180020F66
0x180020f61  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020f66  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020f6b  mov     r13, [rsp+8A0h+var_868]
0x180020f70  jmp     loc_1800210D7
0x180020f75  mov     r13, [rsp+8A0h+var_868]
0x180020f7a  lea     r9, [rsp+8A0h+lpFileName]
0x180020f7f  xor     r8d, r8d
0x180020f82  lea     rdx, aEfiMicrosoftBo_1; "EFI\\Microsoft\\Boot\\Policies"
0x180020f89  mov     rcx, r13
0x180020f8c  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x180020f91  mov     edi, eax
0x180020f93  test    eax, eax
0x180020f95  jns     short loc_180020FDE
0x180020f97  mov     rcx, [rbx+58h]
0x180020f9b  test    rcx, rcx
0x180020f9e  jz      short loc_180020FD4
0x180020fa0  mov     [rsp+8A0h+var_878], eax
0x180020fa4  mov     [rsp+8A0h+var_880], 7BBh
0x180020fac  lea     r9, aCdlpactionlayo_21; "CDlpActionLayoutUsb::PopulateBootPaths"
0x180020fb3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180020fba  mov     edx, 4
0x180020fbf  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x180020fc4  mov     ecx, eax
0x180020fc6  test    eax, eax
0x180020fc8  jns     short loc_180020FCF
0x180020fca  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020fcf  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020fd4  mov     r14, [rsp+8A0h+lpFileName]
0x180020fd9  jmp     loc_1800210D7
0x180020fde  mov     r14, [rsp+8A0h+lpFileName]
0x180020fe3  mov     rcx, r14; lpFileName
0x180020fe6  call    cs:__imp_GetFileAttributesW
0x180020fec  mov     esi, eax
0x180020fee  cmp     eax, 0FFFFFFFFh
0x180020ff1  jz      short loc_180020FFB
0x180020ff3  shr     esi, 4
0x180020ff6  and     esi, 1
0x180020ff9  jmp     short loc_180020FFD
0x180020ffb  xor     esi, esi
0x180020ffd  xor     ecx, ecx
0x180020fff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021004  xor     ecx, ecx
0x180021006  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002100b  mov     rcx, r14; lpFileName
0x18002100e  call    cs:__imp_GetFileAttributesW
0x180021014  mov     edi, eax
0x180021016  cmp     eax, 0FFFFFFFFh
0x180021019  jz      short loc_180021025
0x18002101b  shr     edi, 4
0x18002101e  not     edi
0x180021020  and     edi, 1
0x180021023  jmp     short loc_180021027
0x180021025  xor     edi, edi
0x180021027  xor     ecx, ecx
0x180021029  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002102e  xor     ecx, ecx
0x180021030  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021035  test    esi, esi
0x180021037  jnz     short loc_18002105E
0x180021039  test    edi, edi
0x18002103b  jnz     short loc_18002105E
0x18002103d  mov     rcx, [rbx+58h]
0x180021041  test    rcx, rcx
0x180021044  jz      loc_1800210D7
0x18002104a  mov     r9, r14
0x18002104d  lea     r8, aLayoutusbOcdus; "LayoutUsb: OCDUS blob [%s] does not exi"...
0x180021054  lea     edx, [rsi+2]
0x180021057  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002105c  jmp     short loc_1800210D7
0x18002105e  mov     rcx, [rbx+58h]
0x180021062  test    rcx, rcx
0x180021065  jz      short loc_18002107B
0x180021067  mov     r9, r14
0x18002106a  lea     r8, aLayoutusbOcdus_0; "LayoutUsb: OCDUS blob [%s] exists, back"...
0x180021071  mov     edx, 2
0x180021076  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x18002107b  lea     r9, aOcdusPolicies; "OCDUS\\Policies"
0x180021082  lea     r8, aEfiMicrosoftBo_1; "EFI\\Microsoft\\Boot\\Policies"
0x180021089  mov     rdx, r13; unsigned __int16 *
0x18002108c  mov     rcx, rbx; this
0x18002108f  call    ?PopulateBootPath@CDlpActionLayoutUsb@@AEAAJPEBG00@Z; CDlpActionLayoutUsb::PopulateBootPath(ushort const *,ushort const *,ushort const *)
0x180021094  mov     edi, eax
0x180021096  test    eax, eax
0x180021098  jns     short loc_1800210D7
0x18002109a  mov     rcx, [rbx+58h]
0x18002109e  test    rcx, rcx
0x1800210a1  jz      short loc_1800210D7
0x1800210a3  mov     [rsp+8A0h+var_878], eax
0x1800210a7  mov     [rsp+8A0h+var_880], 7C5h
0x1800210af  lea     r9, aCdlpactionlayo_21; "CDlpActionLayoutUsb::PopulateBootPaths"
0x1800210b6  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1800210bd  mov     edx, 4
0x1800210c2  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1800210c7  test    eax, eax
0x1800210c9  mov     ecx, eax
0x1800210cb  jns     short loc_1800210D2
0x1800210cd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800210d2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800210d7  mov     ecx, edi
0x1800210d9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800210de  nop
0x1800210df  test    r13, r13
0x1800210e2  jz      short loc_180021101
0x1800210e4  call    cs:__imp_GetProcessHeap
0x1800210ea  mov     rcx, rax; hHeap
0x1800210ed  lea     r8, [r13-4]; lpMem
0x1800210f1  xor     edx, edx; dwFlags
0x1800210f3  call    cs:__imp_HeapFree
0x1800210f9  xor     ecx, ecx
0x1800210fb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021100  nop
0x180021101  test    r14, r14
0x180021104  jz      short loc_180021123
0x180021106  call    cs:__imp_GetProcessHeap
0x18002110c  mov     rcx, rax; hHeap
0x18002110f  lea     r8, [r14-4]; lpMem
0x180021113  xor     edx, edx; dwFlags
0x180021115  call    cs:__imp_HeapFree
0x18002111b  xor     ecx, ecx
0x18002111d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021122  nop
0x180021123  test    r15, r15
0x180021126  jz      short loc_180021144
0x180021128  call    cs:__imp_GetProcessHeap
0x18002112e  mov     rcx, rax; hHeap
0x180021131  lea     r8, [r15-4]; lpMem
0x180021135  xor     edx, edx; dwFlags
0x180021137  call    cs:__imp_HeapFree
0x18002113d  xor     ecx, ecx
0x18002113f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180021144  mov     eax, edi
0x180021146  mov     rcx, [rbp+7A0h+var_30]
0x18002114d  xor     rcx, rsp; StackCookie
0x180021150  call    __security_check_cookie
0x180021155  lea     r11, [rsp+8A0h+var_20]
0x18002115d  mov     rbx, [r11+38h]
0x180021161  mov     rsi, [r11+40h]
0x180021165  mov     rsp, r11
0x180021168  pop     r15
0x18002116a  pop     r14
  ... truncated ...
```

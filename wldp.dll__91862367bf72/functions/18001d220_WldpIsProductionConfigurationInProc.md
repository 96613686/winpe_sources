# WldpIsProductionConfigurationInProc

- ea: `0x18001d220`
- end: `0x18001d604`
- name: `WldpIsProductionConfigurationInProc`
- size: `996`
- prototype: `__int64 __fastcall(BOOL *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800083a0`
- `0x180018434`
- `0x180019350`
- `0x18001942c`
- `0x180019ba4`
- `0x18001d1f0`
- `0x18001d220`
- `0x180021ec0`
- `0x1800229ec`
- `0x180024430`
- `0x18002a7dc`
- `0x18002a900`
- `0x18002ace8`
- `0x18002ad60`
- `0x18002ade4`
- `0x18002b540`
- `0x18002b670`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d39a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3ac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d39a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3ac`

## string_xrefs

- `0x18001d2b9`: `%SystemRoot%\System32\CodeIntegrity\Data`
- `0x18001d426`: `%SystemRoot%\System32\CodeIntegrity\Data\WatermarkHSTITestComplete.bin`
- `0x18001d4e9`: `%SystemRoot%\System32\CodeIntegrity\Data\WatermarkSecurityTestComplete.bin`
- `0x18001d2e5`: `ERROR: Failed initializing required file path: %S\n`
- `0x18001d525`: `Security`

## pseudocode

```c
__int64 __fastcall WldpIsProductionConfigurationInProc(BOOL *a1)
{
  unsigned __int16 *v1; // rsi
  unsigned __int16 *v3; // rdi
  unsigned __int16 *v4; // r14
  int RequiredChecks; // ebx
  int v6; // eax
  BOOL v7; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  int v12; // eax
  DWORD v13; // ebx
  int WatermarkState; // eax
  unsigned int v15; // ebx
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v17; // [rsp+54h] [rbp-ACh] BYREF
  size_t Size; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v19; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v20; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  _OWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD Buf1[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v25[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v26; // [rsp+D0h] [rbp-30h]
  _OWORD Buf2[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int8 Buffer[16]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v29; // [rsp+110h] [rbp+10h]

  v17 = 0;
  v16 = 0;
  v1 = 0;
  v3 = 0;
  v20 = 0;
  v4 = 0;
  v19 = 0;
  v21 = 0;
  *(_OWORD *)Buffer = 0;
  v29 = 0;
  Size = 0;
  memset(Buf2, 0, sizeof(Buf2));
  *(_OWORD *)v25 = 0;
  v26 = 0;
  memset(Buf1, 0, sizeof(Buf1));
  RequiredChecks = FindRequiredChecks(&v17);
  if ( RequiredChecks < 0 )
    goto LABEL_6;
  if ( !v17 )
  {
LABEL_35:
    v7 = (v16 & v17) == 0;
    goto LABEL_7;
  }
  v6 = ExpandRequiredPaths(L"%SystemRoot%\\System32\\CodeIntegrity\\Data", &v19);
  v3 = v19;
  RequiredChecks = v6;
  if ( v6 >= 0 )
  {
    RequiredChecks = InitializeWatermarkPath(v19);
    if ( RequiredChecks < 0 )
    {
      LogFormatOut("ERROR: Failed initializing required file path: %S\n");
      goto LABEL_6;
    }
    LODWORD(v19) = 32;
    memset(v23, 0, sizeof(v23));
    RequiredChecks = GetUnlockID(&v19, v23);
    if ( RequiredChecks < 0 )
      goto LABEL_6;
    if ( (v17 & 2) != 0 )
    {
      RequiredChecks = VerifyPreCondition(&v16);
      if ( RequiredChecks < 0 )
        goto LABEL_6;
    }
    if ( (v17 & 1) == 0 )
    {
LABEL_26:
      if ( (v17 & 0x3C) != 0 )
      {
        RequiredChecks = ExpandRequiredPaths(
                           L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\WatermarkSecurityTestComplete.bin",
                           &v20);
        if ( RequiredChecks < 0
          || (HIDWORD(Size) = 32,
              RequiredChecks = GetUniqueID("Security", 9u, v23, 0x20u, (__int64)&Size + 4, (__int64)v25),
              RequiredChecks < 0) )
        {
          v1 = v20;
          goto LABEL_6;
        }
        v1 = v20;
        if ( (v16 & 2) != 0 )
        {
LABEL_32:
          v15 = HIDWORD(Size);
          goto LABEL_33;
        }
        WatermarkState = GetWatermarkState(v20, 0, HIDWORD(Size), Buffer);
        RequiredChecks = WatermarkState;
        if ( WatermarkState < 0 )
        {
          if ( WatermarkState != -2147024894 )
            goto LABEL_24;
          goto LABEL_32;
        }
        v15 = HIDWORD(Size);
        if ( memcmp_0(v25, Buffer, HIDWORD(Size)) )
        {
LABEL_33:
          RequiredChecks = VerifySecurityChecks(v17, v15, v25, v1, &v16);
          if ( RequiredChecks < 0 )
            goto LABEL_6;
        }
      }
      RequiredChecks = 0;
      goto LABEL_35;
    }
    RequiredChecks = ExpandRequiredPaths(
                       L"%SystemRoot%\\System32\\CodeIntegrity\\Data\\WatermarkHSTITestComplete.bin",
                       &v21);
    if ( RequiredChecks < 0
      || (LODWORD(Size) = 32,
          RequiredChecks = GetUniqueID("HSTI", 5u, v23, 0x20u, (__int64)&Size, (__int64)Buf1),
          RequiredChecks < 0) )
    {
      v4 = v21;
      goto LABEL_6;
    }
    v4 = v21;
    if ( (v16 & 2) == 0 )
    {
      v12 = GetWatermarkState(v21, 0, Size, (unsigned __int8 *)Buf2);
      RequiredChecks = v12;
      if ( v12 >= 0 )
      {
        v13 = Size;
        if ( !memcmp_0(Buf1, Buf2, (unsigned int)Size) )
          goto LABEL_26;
        goto LABEL_37;
      }
      if ( v12 != -2147024894 )
      {
LABEL_24:
        LogFormatOut("ERROR: Couldn't get watermark state in required location.\n");
        goto LABEL_6;
      }
    }
    v13 = Size;
LABEL_37:
    RequiredChecks = VerifyHSTIChecks(v13, Buf1, v4, &v16);
    if ( RequiredChecks < 0 )
      goto LABEL_6;
    goto LABEL_26;
  }
LABEL_6:
  v7 = 0;
LABEL_7:
  *a1 = v7;
  if ( (unsigned int)dword_18005A210 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005A210, 0x800000000000LL) )
  {
    LODWORD(v20) = v17;
    LODWORD(v21) = *a1;
    LODWORD(v19) = RequiredChecks;
    v22 = 2048;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)word_18004FBAA,
      v9,
      v10,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20,
      (__int64)&v16,
      (__int64)&v19);
  }
  if ( hFile != (HANDLE)-1LL )
    CloseLogFile();
  if ( *a1 )
    DeleteLogFile();
  LocalFree(v3);
  LocalFree(v4);
  LocalFree(v1);
  return (unsigned int)RequiredChecks;
}

```

## disassembly

```asm
0x18001d220  push    rbp
0x18001d222  push    rbx
0x18001d223  push    rsi
0x18001d224  push    rdi
0x18001d225  push    r14
0x18001d227  push    r15
0x18001d229  lea     rbp, [rsp-38h]
0x18001d22e  sub     rsp, 138h
0x18001d235  mov     rax, cs:__security_cookie
0x18001d23c  xor     rax, rsp
0x18001d23f  mov     [rbp+60h+var_40], rax
0x18001d243  xorps   xmm0, xmm0
0x18001d246  mov     [rsp+160h+var_10C], 0
0x18001d24e  xorps   xmm1, xmm1
0x18001d251  mov     [rsp+160h+var_110], 0
0x18001d259  xor     esi, esi
0x18001d25b  mov     r15, rcx
0x18001d25e  xor     edi, edi
0x18001d260  mov     [rsp+160h+var_F8], rsi
0x18001d265  xor     r14d, r14d
0x18001d268  mov     [rsp+160h+var_100], rdi
0x18001d26d  lea     rcx, [rsp+160h+var_10C]; unsigned int *
0x18001d272  mov     [rsp+160h+var_F0], r14
0x18001d277  movups  xmmword ptr [rbp+60h+Buffer], xmm0
0x18001d27b  mov     dword ptr [rsp+160h+Size+4], esi
0x18001d27f  movups  [rbp+60h+var_50], xmm0
0x18001d283  mov     dword ptr [rsp+160h+Size], esi
0x18001d287  movups  [rbp+60h+Buf2], xmm1
0x18001d28b  movups  [rbp+60h+var_70], xmm1
0x18001d28f  movups  xmmword ptr [rbp+60h+var_A0], xmm0
0x18001d293  movups  [rbp+60h+var_90], xmm0
0x18001d297  movups  [rbp+60h+Buf1], xmm1
0x18001d29b  movups  [rbp+60h+var_B0], xmm1
0x18001d29f  call    ?FindRequiredChecks@@YAJPEAK@Z; FindRequiredChecks(ulong *)
0x18001d2a4  mov     ebx, eax
0x18001d2a6  test    eax, eax
0x18001d2a8  js      short loc_18001D2F1
0x18001d2aa  cmp     [rsp+160h+var_10C], esi
0x18001d2ae  jz      loc_18001D597
0x18001d2b4  lea     rdx, [rsp+160h+var_100]; unsigned __int16 **
0x18001d2b9  lea     rcx, aSystemrootSyst_2; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18001d2c0  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18001d2c5  mov     rdi, [rsp+160h+var_100]
0x18001d2ca  mov     ebx, eax
0x18001d2cc  test    eax, eax
0x18001d2ce  js      short loc_18001D2F1
0x18001d2d0  mov     rcx, rdi; unsigned __int16 *
0x18001d2d3  call    ?InitializeWatermarkPath@@YAJPEBG@Z; InitializeWatermarkPath(ushort const *)
0x18001d2d8  mov     ebx, eax
0x18001d2da  test    eax, eax
0x18001d2dc  jns     loc_18001D3D0
0x18001d2e2  mov     rdx, rdi
0x18001d2e5  lea     rcx, aErrorFailedIni; "ERROR: Failed initializing required fil"...
0x18001d2ec  call    LogFormatOut
0x18001d2f1  xor     eax, eax
0x18001d2f3  mov     [r15], eax
0x18001d2f6  mov     eax, cs:dword_18005A210
0x18001d2fc  cmp     eax, 5
0x18001d2ff  jbe     short loc_18001D37D
0x18001d301  mov     rdx, 800000000000h
0x18001d30b  lea     rcx, dword_18005A210
0x18001d312  call    _tlgKeywordOn
0x18001d317  test    al, al
0x18001d319  jz      short loc_18001D37D
0x18001d31b  mov     eax, [rsp+160h+var_110]
0x18001d31f  lea     rdx, word_18004FBAA
0x18001d326  mov     [rsp+160h+var_110], eax
0x18001d32a  mov     eax, [rsp+160h+var_10C]
0x18001d32e  mov     dword ptr [rsp+160h+var_F8], eax
0x18001d332  mov     eax, [r15]
0x18001d335  mov     dword ptr [rsp+160h+var_F0], eax
0x18001d339  lea     rax, [rsp+160h+var_100]
0x18001d33e  mov     [rsp+160h+var_120], rax
0x18001d343  lea     rax, [rsp+160h+var_110]
0x18001d348  mov     [rsp+160h+var_128], rax
0x18001d34d  lea     rax, [rsp+160h+var_F8]
0x18001d352  mov     [rsp+160h+var_130], rax
0x18001d357  lea     rax, [rsp+160h+var_F0]
0x18001d35c  mov     [rsp+160h+var_138], rax
0x18001d361  lea     rax, [rsp+160h+var_E8]
0x18001d366  mov     [rsp+160h+var_140], rax
0x18001d36b  mov     dword ptr [rsp+160h+var_100], ebx
0x18001d36f  mov     [rsp+160h+var_E8], 800h
0x18001d378  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d37d  cmp     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x18001d385  jz      short loc_18001D38C
0x18001d387  call    ?CloseLogFile@@YAXXZ; CloseLogFile(void)
0x18001d38c  cmp     dword ptr [r15], 0
0x18001d390  jz      short loc_18001D397
0x18001d392  call    ?DeleteLogFile@@YAJXZ; DeleteLogFile(void)
0x18001d397  mov     rcx, rdi; hMem
0x18001d39a  call    cs:__imp_LocalFree
0x18001d3a0  mov     rcx, r14; hMem
0x18001d3a3  call    cs:__imp_LocalFree
0x18001d3a9  mov     rcx, rsi; hMem
0x18001d3ac  call    cs:__imp_LocalFree
0x18001d3b2  mov     eax, ebx
0x18001d3b4  mov     rcx, [rbp+60h+var_40]
0x18001d3b8  xor     rcx, rsp; StackCookie
0x18001d3bb  call    __security_check_cookie
0x18001d3c0  add     rsp, 138h
0x18001d3c7  pop     r15
0x18001d3c9  pop     r14
0x18001d3cb  pop     rdi
0x18001d3cc  pop     rsi
0x18001d3cd  pop     rbx
0x18001d3ce  pop     rbp
0x18001d3cf  retn
0x18001d3d0  xorps   xmm0, xmm0
0x18001d3d3  mov     dword ptr [rsp+160h+var_100], 20h ; ' '
0x18001d3db  lea     rdx, [rbp+60h+var_E0]
0x18001d3df  lea     rcx, [rsp+160h+var_100]
0x18001d3e4  movups  [rbp+60h+var_E0], xmm0
0x18001d3e8  movups  [rbp+60h+var_D0], xmm0
0x18001d3ec  call    GetUnlockID
0x18001d3f1  mov     ebx, eax
0x18001d3f3  test    eax, eax
0x18001d3f5  js      loc_18001D2F1
0x18001d3fb  test    byte ptr [rsp+160h+var_10C], 2
0x18001d400  jz      short loc_18001D416
0x18001d402  lea     rcx, [rsp+160h+var_110]; unsigned int *
0x18001d407  call    ?VerifyPreCondition@@YAJPEAK@Z; VerifyPreCondition(ulong *)
0x18001d40c  mov     ebx, eax
0x18001d40e  test    eax, eax
0x18001d410  js      loc_18001D2F1
0x18001d416  test    byte ptr [rsp+160h+var_10C], 1
0x18001d41b  jz      loc_18001D4D9
0x18001d421  lea     rdx, [rsp+160h+var_F0]; unsigned __int16 **
0x18001d426  lea     rcx, aSystemrootSyst_0; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18001d42d  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18001d432  mov     ebx, eax
0x18001d434  test    eax, eax
0x18001d436  js      loc_18001D5D2
0x18001d43c  mov     r9d, 20h ; ' '; size_t
0x18001d442  lea     rax, [rbp+60h+Buf1]
0x18001d446  mov     [rsp+160h+var_138], rax; __int64
0x18001d44b  lea     r8, [rbp+60h+var_E0]; void *
0x18001d44f  lea     rax, [rsp+160h+Size]
0x18001d454  mov     dword ptr [rsp+160h+Size], r9d
0x18001d459  lea     rcx, aHsti; "HSTI"
0x18001d460  mov     [rsp+160h+var_140], rax; __int64
0x18001d465  lea     edx, [r9-1Bh]; Size
0x18001d469  call    GetUniqueID
0x18001d46e  mov     ebx, eax
0x18001d470  test    eax, eax
0x18001d472  js      loc_18001D5D2
0x18001d478  test    byte ptr [rsp+160h+var_110], 2
0x18001d47d  mov     r14, [rsp+160h+var_F0]
0x18001d482  jnz     loc_18001D5AC
0x18001d488  mov     r8d, dword ptr [rsp+160h+Size]; nNumberOfBytesToRead
0x18001d48d  lea     r9, [rbp+60h+Buf2]; lpBuffer
0x18001d491  xor     edx, edx; unsigned __int16 *
0x18001d493  mov     rcx, r14; unsigned __int16 *
0x18001d496  call    ?GetWatermarkState@@YAJPEBG0KPEAE@Z; GetWatermarkState(ushort const *,ushort const *,ulong,uchar *)
0x18001d49b  mov     ebx, eax
0x18001d49d  test    eax, eax
0x18001d49f  jns     short loc_18001D4BD
0x18001d4a1  cmp     eax, 80070002h
0x18001d4a6  jz      loc_18001D5AC
0x18001d4ac  lea     rcx, aErrorCouldnTGe; "ERROR: Couldn't get watermark state in "...
0x18001d4b3  call    LogFormatOut
0x18001d4b8  jmp     loc_18001D2F1
0x18001d4bd  mov     ebx, dword ptr [rsp+160h+Size]
0x18001d4c1  lea     rdx, [rbp+60h+Buf2]; Buf2
0x18001d4c5  mov     r8d, ebx; Size
0x18001d4c8  lea     rcx, [rbp+60h+Buf1]; Buf1
0x18001d4cc  call    memcmp_0
0x18001d4d1  test    eax, eax
0x18001d4d3  jnz     loc_18001D5B0
0x18001d4d9  test    byte ptr [rsp+160h+var_10C], 3Ch
0x18001d4de  jz      loc_18001D595
0x18001d4e4  lea     rdx, [rsp+160h+var_F8]; unsigned __int16 **
0x18001d4e9  lea     rcx, aSystemrootSyst_1; "%SystemRoot%\\System32\\CodeIntegrity\\"...
0x18001d4f0  call    ?ExpandRequiredPaths@@YAJPEBGPEAPEAG@Z; ExpandRequiredPaths(ushort const *,ushort * *)
0x18001d4f5  mov     ebx, eax
0x18001d4f7  test    eax, eax
0x18001d4f9  js      loc_18001D5FA
0x18001d4ff  mov     ecx, 20h ; ' '
0x18001d504  lea     rax, [rbp+60h+var_A0]
0x18001d508  mov     [rsp+160h+var_138], rax; __int64
0x18001d50d  lea     r8, [rbp+60h+var_E0]; void *
0x18001d511  mov     dword ptr [rsp+160h+Size+4], ecx
0x18001d515  lea     rax, [rsp+160h+Size+4]
0x18001d51a  mov     r9d, ecx; size_t
0x18001d51d  mov     [rsp+160h+var_140], rax; __int64
0x18001d522  lea     edx, [rcx-17h]; Size
0x18001d525  lea     rcx, aSecurity; "Security"
0x18001d52c  call    GetUniqueID
0x18001d531  mov     ebx, eax
0x18001d533  test    eax, eax
0x18001d535  js      loc_18001D5FA
0x18001d53b  test    byte ptr [rsp+160h+var_110], 2
0x18001d540  mov     rsi, [rsp+160h+var_F8]
0x18001d545  jnz     short loc_18001D56B
0x18001d547  mov     r8d, dword ptr [rsp+160h+Size+4]; nNumberOfBytesToRead
0x18001d54c  lea     r9, [rbp+60h+Buffer]; lpBuffer
0x18001d550  xor     edx, edx; unsigned __int16 *
0x18001d552  mov     rcx, rsi; unsigned __int16 *
0x18001d555  call    ?GetWatermarkState@@YAJPEBG0KPEAE@Z; GetWatermarkState(ushort const *,ushort const *,ulong,uchar *)
0x18001d55a  mov     ebx, eax
0x18001d55c  test    eax, eax
0x18001d55e  jns     short loc_18001D5DC
0x18001d560  cmp     eax, 80070002h
0x18001d565  jnz     loc_18001D4AC
0x18001d56b  mov     ebx, dword ptr [rsp+160h+Size+4]
0x18001d56f  mov     ecx, [rsp+160h+var_10C]; unsigned int
0x18001d573  lea     rax, [rsp+160h+var_110]
0x18001d578  mov     r9, rsi; unsigned __int16 *
0x18001d57b  mov     [rsp+160h+var_140], rax; unsigned int *
0x18001d580  lea     r8, [rbp+60h+var_A0]; unsigned __int8 *
0x18001d584  mov     edx, ebx; unsigned int
0x18001d586  call    ?VerifySecurityChecks@@YAJKKPEBEPEBGPEAK@Z; VerifySecurityChecks(ulong,ulong,uchar const *,ushort const *,ulong *)
0x18001d58b  mov     ebx, eax
0x18001d58d  test    eax, eax
0x18001d58f  js      loc_18001D2F1
0x18001d595  xor     ebx, ebx
0x18001d597  mov     eax, [rsp+160h+var_110]
0x18001d59b  test    [rsp+160h+var_10C], eax
0x18001d59f  mov     eax, 0
0x18001d5a4  setz    al
0x18001d5a7  jmp     loc_18001D2F3
0x18001d5ac  mov     ebx, dword ptr [rsp+160h+Size]
0x18001d5b0  lea     r9, [rsp+160h+var_110]; unsigned int *
0x18001d5b5  mov     r8, r14; unsigned __int16 *
0x18001d5b8  lea     rdx, [rbp+60h+Buf1]; lpBuffer
0x18001d5bc  mov     ecx, ebx; nNumberOfBytesToWrite
0x18001d5be  call    ?VerifyHSTIChecks@@YAJKPEBEPEBGPEAK@Z; VerifyHSTIChecks(ulong,uchar const *,ushort const *,ulong *)
0x18001d5c3  mov     ebx, eax
0x18001d5c5  test    eax, eax
0x18001d5c7  jns     loc_18001D4D9
0x18001d5cd  jmp     loc_18001D2F1
0x18001d5d2  mov     r14, [rsp+160h+var_F0]
0x18001d5d7  jmp     loc_18001D2F1
0x18001d5dc  mov     ebx, dword ptr [rsp+160h+Size+4]
0x18001d5e0  lea     rdx, [rbp+60h+Buffer]; Buf2
0x18001d5e4  mov     r8d, ebx; Size
0x18001d5e7  lea     rcx, [rbp+60h+var_A0]; Buf1
0x18001d5eb  call    memcmp_0
0x18001d5f0  test    eax, eax
0x18001d5f2  jnz     loc_18001D56F
0x18001d5f8  jmp     short loc_18001D595
0x18001d5fa  mov     rsi, [rsp+160h+var_F8]
0x18001d5ff  jmp     loc_18001D2F1
```

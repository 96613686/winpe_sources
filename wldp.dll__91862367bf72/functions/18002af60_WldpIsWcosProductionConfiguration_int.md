# WldpIsWcosProductionConfiguration(int *)

- ea: `0x18002af60`
- end: `0x18002b384`
- name: `?WldpIsWcosProductionConfiguration@@YAJPEAH@Z`
- size: `1060`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180019350`
- `0x18001942c`
- `0x180019c50`
- `0x18001b50c`
- `0x18001d1f0`
- `0x18001fdb4`
- `0x180021ec0`
- `0x1800229ec`
- `0x180023ff0`
- `0x180024370`
- `0x18002a480`
- `0x18002a7dc`
- `0x18002a940`
- `0x18002ab90`
- `0x18002af60`
- `0x18002b480`
- `0x18002b670`
- `0x180036ee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b043`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18002b039`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18002b039`

## string_xrefs

- `0x18002b0c8`: `Microsoft\WatermarkHSTITestComplete.bin`
- `0x18002b13e`: `Microsoft\WatermarkHSTITestComplete.bin`
- `0x18002b156`: `Microsoft\WatermarkHSTITestComplete.bin`
- `0x18002b17a`: `Microsoft\WatermarkSBTestComplete.bin`
- `0x18002b1f4`: `Microsoft\WatermarkSBTestComplete.bin`
- `0x18002b227`: `Microsoft\WatermarkSBTestComplete.bin`
- `0x18002b241`: `Microsoft\WatermarkSBTestComplete.bin`
- `0x18002b25e`: `Microsoft\WatermarkSBTestComplete.bin`
- `0x18002affc`: `ERROR: Failed initializing required file path: %S\n`
- `0x18002b06c`: `TEST FAIL: ManufacturingMode is on\n`

## pseudocode

```c
__int64 __fastcall WldpIsWcosProductionConfiguration(int *a1)
{
  int v1; // edi
  int v3; // r14d
  int v4; // esi
  bool v5; // r15
  int UniqueIDs; // ebx
  signed int LastError; // eax
  int WatermarkState; // eax
  struct _NGSCB_HSTI_PARSING_STATUS *v9; // r8
  int v10; // eax
  int v11; // esi
  int v12; // ebx
  bool v14; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+34h] [rbp-CCh] BYREF
  size_t Size; // [rsp+38h] [rbp-C8h] BYREF
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh] BYREF
  struct _NGSCB_HSTI_RESULTS *v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v21[32]; // [rsp+60h] [rbp-A0h] BYREF
  int *v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  int *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+98h] [rbp-68h]
  int *v26; // [rsp+A0h] [rbp-60h]
  __int64 v27; // [rsp+A8h] [rbp-58h]
  struct _NGSCB_HSTI_RESULTS **v28; // [rsp+B0h] [rbp-50h]
  __int64 v29; // [rsp+B8h] [rbp-48h]
  _OWORD Buf1[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v32; // [rsp+F0h] [rbp-10h]
  _OWORD Buf2[2]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 Buffer[16]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v35; // [rsp+130h] [rbp+30h]

  v1 = 0;
  Size = 0;
  v20[0] = 0;
  v17 = 0;
  v3 = 1;
  v19 = 0;
  v4 = 1;
  v15 = 1;
  v5 = 1;
  v14 = 1;
  *(_OWORD *)Buffer = 0;
  *a1 = 0;
  v35 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  *(_OWORD *)v31 = 0;
  v32 = 0;
  memset(Buf1, 0, sizeof(Buf1));
  UniqueIDs = InitializeWcosWatermarkPath();
  if ( UniqueIDs < 0 )
  {
    LogFormatOut("ERROR: Failed initializing required file path: %S\n");
    goto LABEL_41;
  }
  CheckRetailUnlock(1, v20);
  if ( v20[0] )
  {
    v1 = 2;
    UniqueIDs = WldpResetWcosProductionConfiguration();
    if ( UniqueIDs < 0 )
      goto LABEL_41;
  }
  if ( (unsigned int)GetOsManufacturingMode(&v17) )
  {
    if ( v17 )
    {
      v1 |= 0x10u;
      LogFormatOut("TEST FAIL: ManufacturingMode is on\n");
      UniqueIDs = WldpResetWcosProductionConfiguration();
      if ( UniqueIDs < 0 )
        goto LABEL_41;
    }
    Size = 0x2000000020LL;
    UniqueIDs = GetUniqueIDs((__int64)&Size + 4, (__int64)&Size, (__int64)v31, (__int64)Buf1);
    if ( UniqueIDs < 0 )
      goto LABEL_41;
    WatermarkState = GetWatermarkState(
                       L"Microsoft\\WatermarkHSTITestComplete.bin",
                       qword_18005ADE0,
                       Size,
                       (unsigned __int8 *)Buf2);
    UniqueIDs = WatermarkState;
    if ( WatermarkState >= 0 )
    {
      if ( !memcmp_0(Buf1, Buf2, (unsigned int)Size) )
        goto LABEL_21;
    }
    else if ( WatermarkState != -2147024894 )
    {
      LogFormatOut("ERROR: Couldn't get watermark state in required location.\n");
      goto LABEL_41;
    }
    UniqueIDs = NgscbCheckIsHSTIVerified(&v14, &v19, v9);
    if ( UniqueIDs < 0 )
      goto LABEL_41;
    v5 = v14;
    if ( v14 )
    {
      UpdateWatermarkState(Size, Buf1, L"Microsoft\\WatermarkHSTITestComplete.bin", qword_18005ADE0);
    }
    else
    {
      LogFormatOut("TEST FAIL: HSTI: Failed to reteive result or HSTI not verified\n");
      v1 |= 1u;
      DeleteWatermarkState(L"Microsoft\\WatermarkHSTITestComplete.bin", qword_18005ADE0);
    }
LABEL_21:
    v10 = GetWatermarkState(L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0, HIDWORD(Size), Buffer);
    UniqueIDs = v10;
    if ( v10 >= 0 )
    {
      if ( !memcmp_0(v31, Buffer, HIDWORD(Size)) )
        goto LABEL_34;
    }
    else if ( v10 != -2147024894 )
    {
      goto LABEL_41;
    }
    LODWORD(v19) = 0;
    v18 = 0;
    UniqueIDs = WldpCheckRetailConfiguration2(7, &v15, &v19, &v18);
    if ( UniqueIDs < 0 )
      goto LABEL_41;
    v11 = v15;
    if ( !v15 )
    {
      v1 |= 8u;
      DeleteWatermarkState(L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0);
    }
    v15 = 1;
    UniqueIDs = CheckFveBinding(&v15);
    if ( UniqueIDs < 0 )
      goto LABEL_41;
    v12 = v15;
    if ( !v15 )
    {
      v1 |= 4u;
      DeleteWatermarkState(L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0);
    }
    v4 = v12 & v11;
    if ( v4 )
      UpdateWatermarkState(HIDWORD(Size), v31, L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0);
    else
      DeleteWatermarkState(L"Microsoft\\WatermarkSBTestComplete.bin", qword_18005ADE0);
LABEL_34:
    UniqueIDs = 0;
LABEL_35:
    if ( v17 || v20[0] || !v4 || !v5 )
      v3 = 0;
    *a1 = v3;
    goto LABEL_41;
  }
  LastError = GetLastError();
  UniqueIDs = LastError;
  if ( LastError > 0 )
    UniqueIDs = (unsigned __int16)LastError | 0x80070000;
  if ( UniqueIDs >= 0 )
    goto LABEL_35;
LABEL_41:
  if ( (unsigned int)dword_18005A280 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005A280, 0x200000000000LL) )
  {
    v15 = *a1;
    LODWORD(v19) = UniqueIDs;
    v28 = &v19;
    v18 = v1;
    v26 = &v18;
    *(_QWORD *)v20 = 2048;
    v24 = &v15;
    v22 = v20;
    v29 = 4;
    v27 = 4;
    v25 = 4;
    v23 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A280, byte_18004FC4B, 0, 0, 6, v21);
  }
  if ( hFile != (HANDLE)-1LL )
    CloseLogFile();
  if ( *a1 )
    DeleteLogFile();
  return (unsigned int)UniqueIDs;
}

```

## disassembly

```asm
0x18002af60  mov     [rsp-8+arg_8], rbx
0x18002af65  mov     [rsp-8+arg_10], rsi
0x18002af6a  push    rbp
0x18002af6b  push    rdi
0x18002af6c  push    r12
0x18002af6e  push    r14
0x18002af70  push    r15
0x18002af72  lea     rbp, [rsp-50h]
0x18002af77  sub     rsp, 150h
0x18002af7e  mov     rax, cs:__security_cookie
0x18002af85  xor     rax, rsp
0x18002af88  mov     [rbp+70h+var_30], rax
0x18002af8c  xor     edi, edi
0x18002af8e  mov     dword ptr [rsp+170h+Size+4], 0
0x18002af96  xorps   xmm0, xmm0
0x18002af99  mov     dword ptr [rsp+170h+Size], 0
0x18002afa1  xorps   xmm1, xmm1
0x18002afa4  mov     [rsp+170h+var_120], edi
0x18002afa8  mov     r12, rcx
0x18002afab  mov     [rsp+170h+var_130], edi
0x18002afaf  lea     r14d, [rdi+1]
0x18002afb3  mov     [rsp+170h+var_128], rdi
0x18002afb8  mov     esi, r14d
0x18002afbb  mov     [rsp+170h+var_13C], r14d
0x18002afc0  mov     r15b, r14b
0x18002afc3  mov     [rsp+170h+var_140], r14b
0x18002afc8  movups  xmmword ptr [rbp+70h+Buffer], xmm0
0x18002afcc  mov     [rcx], edi
0x18002afce  movups  [rbp+70h+var_40], xmm0
0x18002afd2  movups  [rbp+70h+Buf2], xmm1
0x18002afd6  movups  [rbp+70h+var_60], xmm1
0x18002afda  movups  xmmword ptr [rbp+70h+var_90], xmm0
0x18002afde  movups  [rbp+70h+var_80], xmm0
0x18002afe2  movups  [rbp+70h+Buf1], xmm1
0x18002afe6  movups  [rbp+70h+var_A0], xmm1
0x18002afea  call    ?InitializeWcosWatermarkPath@@YAJXZ; InitializeWcosWatermarkPath(void)
0x18002afef  mov     ebx, eax
0x18002aff1  test    eax, eax
0x18002aff3  jns     short loc_18002B00D
0x18002aff5  lea     rdx, aMicrosoft; "Microsoft"
0x18002affc  lea     rcx, aErrorFailedIni; "ERROR: Failed initializing required fil"...
0x18002b003  call    LogFormatOut
0x18002b008  jmp     loc_18002B28A
0x18002b00d  lea     rdx, [rsp+170h+var_120]; int *
0x18002b012  mov     ecx, r14d; int
0x18002b015  call    ?CheckRetailUnlock@@YAJHPEAH@Z; CheckRetailUnlock(int,int *)
0x18002b01a  cmp     [rsp+170h+var_120], edi
0x18002b01e  jz      short loc_18002B034
0x18002b020  mov     edi, 2
0x18002b025  call    ?WldpResetWcosProductionConfiguration@@YAJXZ; WldpResetWcosProductionConfiguration(void)
0x18002b02a  mov     ebx, eax
0x18002b02c  test    eax, eax
0x18002b02e  js      loc_18002B28A
0x18002b034  lea     rcx, [rsp+170h+var_130]
0x18002b039  call    cs:__imp_GetOsManufacturingMode
0x18002b03f  test    eax, eax
0x18002b041  jnz     short loc_18002B065
0x18002b043  call    cs:__imp_GetLastError
0x18002b049  mov     ebx, eax
0x18002b04b  test    eax, eax
0x18002b04d  jle     short loc_18002B058
0x18002b04f  movzx   ebx, ax
0x18002b052  or      ebx, 80070000h
0x18002b058  test    ebx, ebx
0x18002b05a  js      loc_18002B28A
0x18002b060  jmp     loc_18002B26C
0x18002b065  cmp     [rsp+170h+var_130], 0
0x18002b06a  jz      short loc_18002B08A
0x18002b06c  lea     rcx, aTestFailManufa; "TEST FAIL: ManufacturingMode is on\n"
0x18002b073  or      edi, 10h
0x18002b076  call    LogFormatOut
0x18002b07b  call    ?WldpResetWcosProductionConfiguration@@YAJXZ; WldpResetWcosProductionConfiguration(void)
0x18002b080  mov     ebx, eax
0x18002b082  test    eax, eax
0x18002b084  js      loc_18002B28A
0x18002b08a  mov     eax, 20h ; ' '
0x18002b08f  lea     r9, [rbp+70h+Buf1]; __int64
0x18002b093  lea     r8, [rbp+70h+var_90]; __int64
0x18002b097  mov     dword ptr [rsp+170h+Size+4], eax
0x18002b09b  lea     rdx, [rsp+170h+Size]; __int64
0x18002b0a0  mov     dword ptr [rsp+170h+Size], eax
0x18002b0a4  lea     rcx, [rsp+170h+Size+4]; __int64
0x18002b0a9  call    GetUniqueIDs
0x18002b0ae  mov     ebx, eax
0x18002b0b0  test    eax, eax
0x18002b0b2  js      loc_18002B28A
0x18002b0b8  mov     r8d, dword ptr [rsp+170h+Size]; nNumberOfBytesToRead
0x18002b0bd  lea     r9, [rbp+70h+Buf2]; lpBuffer
0x18002b0c1  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b0c8  lea     rcx, aMicrosoftWater_0; "Microsoft\\WatermarkHSTITestComplete.bi"...
0x18002b0cf  call    ?GetWatermarkState@@YAJPEBG0KPEAE@Z; GetWatermarkState(ushort const *,ushort const *,ulong,uchar *)
0x18002b0d4  mov     ebx, eax
0x18002b0d6  test    eax, eax
0x18002b0d8  jns     short loc_18002B0F2
0x18002b0da  cmp     eax, 80070002h
0x18002b0df  jz      short loc_18002B108
0x18002b0e1  lea     rcx, aErrorCouldnTGe; "ERROR: Couldn't get watermark state in "...
0x18002b0e8  call    LogFormatOut
0x18002b0ed  jmp     loc_18002B28A
0x18002b0f2  mov     r8d, dword ptr [rsp+170h+Size]; Size
0x18002b0f7  lea     rdx, [rbp+70h+Buf2]; Buf2
0x18002b0fb  lea     rcx, [rbp+70h+Buf1]; Buf1
0x18002b0ff  call    memcmp_0
0x18002b104  test    eax, eax
0x18002b106  jz      short loc_18002B16A
0x18002b108  lea     rdx, [rsp+170h+var_128]; struct _NGSCB_HSTI_RESULTS **
0x18002b10d  lea     rcx, [rsp+170h+var_140]; bool *
0x18002b112  call    ?NgscbCheckIsHSTIVerified@@YAJPEA_NPEAPEAU_NGSCB_HSTI_RESULTS@@PEAU_NGSCB_HSTI_PARSING_STATUS@@@Z; NgscbCheckIsHSTIVerified(bool *,_NGSCB_HSTI_RESULTS * *,_NGSCB_HSTI_PARSING_STATUS *)
0x18002b117  mov     ebx, eax
0x18002b119  test    eax, eax
0x18002b11b  js      loc_18002B28A
0x18002b121  mov     r15b, [rsp+170h+var_140]
0x18002b126  test    r15b, r15b
0x18002b129  jnz     short loc_18002B14F
0x18002b12b  lea     rcx, aTestFailHstiFa; "TEST FAIL: HSTI: Failed to reteive resu"...
0x18002b132  call    LogFormatOut
0x18002b137  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b13e  lea     rcx, aMicrosoftWater_0; "Microsoft\\WatermarkHSTITestComplete.bi"...
0x18002b145  or      edi, r14d
0x18002b148  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b14d  jmp     short loc_18002B16A
0x18002b14f  mov     r9, cs:qword_18005ADE0; unsigned __int16 *
0x18002b156  lea     r8, aMicrosoftWater_0; "Microsoft\\WatermarkHSTITestComplete.bi"...
0x18002b15d  mov     ecx, dword ptr [rsp+170h+Size]; nNumberOfBytesToWrite
0x18002b161  lea     rdx, [rbp+70h+Buf1]; lpBuffer
0x18002b165  call    ?UpdateWatermarkState@@YAJKPEBEPEBG1@Z; UpdateWatermarkState(ulong,uchar const *,ushort const *,ushort const *)
0x18002b16a  mov     r8d, dword ptr [rsp+170h+Size+4]; nNumberOfBytesToRead
0x18002b16f  lea     r9, [rbp+70h+Buffer]; lpBuffer
0x18002b173  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b17a  lea     rcx, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b181  call    ?GetWatermarkState@@YAJPEBG0KPEAE@Z; GetWatermarkState(ushort const *,ushort const *,ulong,uchar *)
0x18002b186  mov     ebx, eax
0x18002b188  test    eax, eax
0x18002b18a  jns     short loc_18002B198
0x18002b18c  cmp     eax, 80070002h
0x18002b191  jz      short loc_18002B1B2
0x18002b193  jmp     loc_18002B28A
0x18002b198  mov     r8d, dword ptr [rsp+170h+Size+4]; Size
0x18002b19d  lea     rdx, [rbp+70h+Buffer]; Buf2
0x18002b1a1  lea     rcx, [rbp+70h+var_90]; Buf1
0x18002b1a5  call    memcmp_0
0x18002b1aa  test    eax, eax
0x18002b1ac  jz      loc_18002B26A
0x18002b1b2  lea     r9, [rsp+170h+var_12C]
0x18002b1b7  mov     dword ptr [rsp+170h+var_128], 0
0x18002b1bf  lea     r8, [rsp+170h+var_128]
0x18002b1c4  mov     [rsp+170h+var_12C], 0
0x18002b1cc  lea     rdx, [rsp+170h+var_13C]
0x18002b1d1  mov     ecx, 7
0x18002b1d6  call    WldpCheckRetailConfiguration2
0x18002b1db  mov     ebx, eax
0x18002b1dd  test    eax, eax
0x18002b1df  js      loc_18002B28A
0x18002b1e5  mov     esi, [rsp+170h+var_13C]
0x18002b1e9  test    esi, esi
0x18002b1eb  jnz     short loc_18002B203
0x18002b1ed  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b1f4  lea     rcx, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b1fb  or      edi, 8
0x18002b1fe  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b203  lea     rcx, [rsp+170h+var_13C]; int *
0x18002b208  mov     [rsp+170h+var_13C], r14d
0x18002b20d  call    ?CheckFveBinding@@YAJPEAH@Z; CheckFveBinding(int *)
0x18002b212  mov     ebx, eax
0x18002b214  test    eax, eax
0x18002b216  js      short loc_18002B28A
0x18002b218  mov     ebx, [rsp+170h+var_13C]
0x18002b21c  test    ebx, ebx
0x18002b21e  jnz     short loc_18002B236
0x18002b220  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b227  lea     rcx, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b22e  or      edi, 4
0x18002b231  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b236  and     esi, ebx
0x18002b238  jz      short loc_18002B257
0x18002b23a  mov     r9, cs:qword_18005ADE0; unsigned __int16 *
0x18002b241  lea     r8, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b248  mov     ecx, dword ptr [rsp+170h+Size+4]; nNumberOfBytesToWrite
0x18002b24c  lea     rdx, [rbp+70h+var_90]; lpBuffer
0x18002b250  call    ?UpdateWatermarkState@@YAJKPEBEPEBG1@Z; UpdateWatermarkState(ulong,uchar const *,ushort const *,ushort const *)
0x18002b255  jmp     short loc_18002B26A
0x18002b257  mov     rdx, cs:qword_18005ADE0; unsigned __int16 *
0x18002b25e  lea     rcx, aMicrosoftWater; "Microsoft\\WatermarkSBTestComplete.bin"
0x18002b265  call    ?DeleteWatermarkState@@YAJPEBG0@Z; DeleteWatermarkState(ushort const *,ushort const *)
0x18002b26a  xor     ebx, ebx
0x18002b26c  cmp     [rsp+170h+var_130], 0
0x18002b271  jnz     short loc_18002B283
0x18002b273  cmp     [rsp+170h+var_120], 0
0x18002b278  jnz     short loc_18002B283
0x18002b27a  test    esi, esi
0x18002b27c  jz      short loc_18002B283
0x18002b27e  test    r15b, r15b
0x18002b281  jnz     short loc_18002B286
0x18002b283  xor     r14d, r14d
0x18002b286  mov     [r12], r14d
0x18002b28a  mov     eax, cs:dword_18005A280
0x18002b290  cmp     eax, 5
0x18002b293  jbe     loc_18002B33F
0x18002b299  mov     rdx, 200000000000h
0x18002b2a3  lea     rcx, dword_18005A280
0x18002b2aa  call    _tlgKeywordOn
0x18002b2af  test    al, al
0x18002b2b1  jz      loc_18002B33F
0x18002b2b7  mov     eax, [r12]
0x18002b2bb  lea     rdx, byte_18004FC4B
0x18002b2c2  mov     [rsp+170h+var_13C], eax
0x18002b2c6  lea     rcx, dword_18005A280
0x18002b2cd  lea     rax, [rsp+170h+var_128]
0x18002b2d2  mov     dword ptr [rsp+170h+var_128], ebx
0x18002b2d6  mov     [rbp+70h+var_C0], rax
0x18002b2da  xor     r9d, r9d
0x18002b2dd  lea     rax, [rsp+170h+var_12C]
0x18002b2e2  mov     [rsp+170h+var_12C], edi
0x18002b2e6  mov     [rbp+70h+var_D0], rax
0x18002b2ea  xor     r8d, r8d
0x18002b2ed  lea     rax, [rsp+170h+var_13C]
0x18002b2f2  mov     qword ptr [rsp+170h+var_120], 800h
0x18002b2fb  mov     [rbp+70h+var_E0], rax
0x18002b2ff  lea     rax, [rsp+170h+var_120]
0x18002b304  mov     [rbp+70h+var_F0], rax
0x18002b308  lea     rax, [rsp+170h+var_110]
0x18002b30d  mov     [rsp+170h+var_148], rax
0x18002b312  mov     [rsp+170h+var_150], 6
0x18002b31a  mov     [rbp+70h+var_B8], 4
0x18002b322  mov     [rbp+70h+var_C8], 4
0x18002b32a  mov     [rbp+70h+var_D8], 4
0x18002b332  mov     [rbp+70h+var_E8], 8
0x18002b33a  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b33f  cmp     cs:hFile, 0FFFFFFFFFFFFFFFFh
0x18002b347  jz      short loc_18002B34E
0x18002b349  call    ?CloseLogFile@@YAXXZ; CloseLogFile(void)
0x18002b34e  cmp     dword ptr [r12], 0
0x18002b353  jz      short loc_18002B35A
0x18002b355  call    ?DeleteLogFile@@YAJXZ; DeleteLogFile(void)
0x18002b35a  mov     eax, ebx
0x18002b35c  mov     rcx, [rbp+70h+var_30]
0x18002b360  xor     rcx, rsp; StackCookie
0x18002b363  call    __security_check_cookie
0x18002b368  lea     r11, [rsp+170h+var_20]
0x18002b370  mov     rbx, [r11+38h]
0x18002b374  mov     rsi, [r11+40h]
0x18002b378  mov     rsp, r11
0x18002b37b  pop     r15
0x18002b37d  pop     r14
0x18002b37f  pop     r12
0x18002b381  pop     rdi
0x18002b382  pop     rbp
0x18002b383  retn
```

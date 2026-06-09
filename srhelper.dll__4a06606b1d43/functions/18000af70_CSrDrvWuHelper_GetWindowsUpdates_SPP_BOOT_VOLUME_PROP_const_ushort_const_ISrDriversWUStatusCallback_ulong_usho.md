# CSrDrvWuHelper::GetWindowsUpdates(_SPP_BOOT_VOLUME_PROP const *,ushort const *,ISrDriversWUStatusCallback *,ulong *,ushort * * *)

- ea: `0x18000af70`
- end: `0x18000b3a8`
- name: `?GetWindowsUpdates@CSrDrvWuHelper@@UEAAJPEBU_SPP_BOOT_VOLUME_PROP@@PEBGPEAUISrDriversWUStatusCallback@@PEAKPEAPEAPEAG@Z`
- size: `1080`
- prototype: `__int64 __fastcall(CSrDrvWuHelper *this, const struct _SPP_BOOT_VOLUME_PROP *, const unsigned __int16 *, struct ISrDriversWUStatusCallback *, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, service_task, installer_update`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x180003ce0`
- `0x180003d08`
- `0x18000a6a8`
- `0x18000af70`
- `0x18000bbe0`
- `0x18000bf70`
- `0x18000c468`
- `0x18000c890`
- `0x18000cc20`
- `0x18000d0e0`
- `0x18000d348`
- `0x18000d43c`
- `0x180014dd0`
- `0x180015760`

## import_xrefs

- `msvcrt!qsort` at `0x18000b23f`
- `msvcrt!qsort` at `0x18000b23f`
- `ole32!CoTaskMemFree` at `0x18000b356`
- `ole32!CoTaskMemFree` at `0x18000b356`

## string_xrefs

- `0x18000afca`: `CSrDrvWuHelper::GetWindowsUpdates`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::GetWindowsUpdates(
        CSrDrvWuHelper *this,
        const struct _SPP_BOOT_VOLUME_PROP *a2,
        const unsigned __int16 *a3,
        struct ISrDriversWUStatusCallback *a4,
        unsigned int *a5,
        unsigned __int16 ***a6)
{
  void *v8; // rbx
  __int64 v9; // r15
  unsigned __int16 *v10; // r13
  __int64 v11; // rcx
  __int128 *v12; // rax
  __int64 v13; // rcx
  unsigned __int16 ***v14; // rax
  __int16 v15; // ax
  _QWORD *v16; // rax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // rcx
  int DriverWUInfoFromCache; // eax
  int v20; // r8d
  const unsigned __int16 *v21; // rcx
  int updated; // eax
  bool v23; // sf
  __int64 v24; // rcx
  unsigned __int16 ***v25; // rax
  unsigned int v26; // eax
  unsigned __int16 **v27; // rcx
  const unsigned __int16 *v28; // rcx
  int v29; // eax
  __int64 v30; // rcx
  unsigned __int16 ***v31; // rax
  unsigned __int16 ***v32; // rax
  unsigned int v33; // edi
  int (__high *v35)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *); // [rsp+20h] [rbp-89h]
  unsigned __int16 **v36[2]; // [rsp+30h] [rbp-79h] BYREF
  int WindirPathFromBootVolumeProp; // [rsp+40h] [rbp-69h] BYREF
  __int16 v38; // [rsp+44h] [rbp-65h]
  __int16 v39; // [rsp+46h] [rbp-63h]
  unsigned __int16 *v40; // [rsp+78h] [rbp-31h] BYREF
  const unsigned __int16 *v41; // [rsp+80h] [rbp-29h] BYREF
  __int64 v42; // [rsp+88h] [rbp-21h]
  __int128 v43; // [rsp+90h] [rbp-19h] BYREF
  struct _GUID v44; // [rsp+A0h] [rbp-9h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&WindirPathFromBootVolumeProp,
    "CSrDrvWuHelper::GetWindowsUpdates",
    0x2A9u,
    (unsigned __int16)a4);
  v41 = (const unsigned __int16 *)qword_18001A620;
  v42 = 0;
  v8 = 0;
  v40 = 0;
  v9 = 16;
  v10 = 0;
  v11 = 16;
  v12 = &v43;
  v43 = 0;
  *(_OWORD *)v36 = 0;
  do
  {
    *(_BYTE *)v12 = 0;
    v12 = (__int128 *)((char *)v12 + 1);
    --v11;
  }
  while ( v11 );
  v13 = 16;
  v14 = v36;
  do
  {
    *(_BYTE *)v14 = 0;
    v14 = (unsigned __int16 ***)((char *)v14 + 1);
    --v13;
  }
  while ( v13 );
  v15 = 692;
  if ( !a5 || (v38 = 692, v15 = 693, !a6) )
  {
    WindirPathFromBootVolumeProp = -2147024809;
LABEL_45:
    v39 = v15;
    goto LABEL_46;
  }
  v38 = 693;
  if ( a2 && a3 )
  {
    WindirPathFromBootVolumeProp = -2147024809;
    v15 = 694;
    goto LABEL_45;
  }
  WindirPathFromBootVolumeProp = 0;
  v38 = 694;
  *a5 = 0;
  *a6 = 0;
  v16 = operator new(0x18u);
  v8 = v16;
  if ( !v16 )
  {
    v8 = 0;
    WindirPathFromBootVolumeProp = -2147024882;
    v15 = 699;
    goto LABEL_45;
  }
  *(_DWORD *)v16 = 1;
  v16[1] = 0;
  v16[2] = 0;
  WindirPathFromBootVolumeProp = 0;
  v38 = 699;
  if ( a2 )
  {
    WindirPathFromBootVolumeProp = CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(a2, (struct CBsString *)&v41);
    v15 = 703;
    if ( WindirPathFromBootVolumeProp < 0 )
      goto LABEL_45;
    v38 = 703;
    if ( !(_DWORD)v42 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
      }
      WindirPathFromBootVolumeProp = -2147024809;
      v15 = 712;
      goto LABEL_45;
    }
    v18 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    v44 = *(struct _GUID *)a2;
    DriverWUInfoFromCache = CSrDrvWuHelper::_GetDriverWUInfoFromCache(
                              v18,
                              &v44,
                              0,
                              (struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)v36);
    WindirPathFromBootVolumeProp = DriverWUInfoFromCache;
    if ( DriverWUInfoFromCache >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
      }
      *a5 = (unsigned int)v36[0];
      *a6 = v36[1];
      v38 = 732;
      LODWORD(v36[0]) = 0;
      v36[1] = 0;
      WindirPathFromBootVolumeProp = 0;
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      WPP_SF_S_guid_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        v20,
        *((_QWORD *)a2 + 5),
        (__int64)a2,
        DriverWUInfoFromCache);
    v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    WindirPathFromBootVolumeProp = 0;
    updated = CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(v21, &v40);
    v10 = v40;
    v23 = updated < 0;
    WindirPathFromBootVolumeProp = updated;
    v15 = 737;
    if ( v23 )
      goto LABEL_45;
    a3 = v41;
    v38 = 737;
  }
  *((_QWORD *)&v43 + 1) = a4;
  *(_QWORD *)&v43 = v8;
  WindirPathFromBootVolumeProp = CSrDrvWuHelper::_GetWindowsUpdates(a3, v17, v10, a2 != 0, v35, &v43);
  v15 = 748;
  if ( WindirPathFromBootVolumeProp < 0 )
    goto LABEL_45;
  v38 = 748;
  Free_StringArray((unsigned int *)v36, &v36[1]);
  v24 = 16;
  v25 = v36;
  do
  {
    *(_BYTE *)v25 = 0;
    v25 = (unsigned __int16 ***)((char *)v25 + 1);
    --v24;
  }
  while ( v24 );
  v26 = *((_DWORD *)v8 + 4);
  v27 = (unsigned __int16 **)*((_QWORD *)v8 + 1);
  *((_QWORD *)v8 + 1) = 0;
  *((_QWORD *)v8 + 2) = 0;
  v36[1] = v27;
  LODWORD(v36[0]) = v26;
  qsort(v27, v26, 8u, CSrDrvWuHelper::_StringSortRoutine);
  if ( a2 )
  {
    v28 = (const unsigned __int16 *)*((_QWORD *)a2 + 5);
    v44 = *(struct _GUID *)a2;
    v29 = CSrDrvWuHelper::_AddDriverWUInfoToCache(v28, &v44, 0, (struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)v36);
    WindirPathFromBootVolumeProp = v29;
    if ( v29 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
      {
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids,
          *((_QWORD *)a2 + 5),
          v29);
      }
      WindirPathFromBootVolumeProp = 0;
    }
  }
  v30 = 16;
  *a6 = v36[1];
  *a5 = (unsigned int)v36[0];
  v31 = v36;
  do
  {
    *(_BYTE *)v31 = 0;
    v31 = (unsigned __int16 ***)((char *)v31 + 1);
    --v30;
  }
  while ( v30 );
LABEL_46:
  Free_StringArray((unsigned int *)v36, &v36[1]);
  v32 = v36;
  do
  {
    *(_BYTE *)v32 = 0;
    v32 = (unsigned __int16 ***)((char *)v32 + 1);
    --v9;
  }
  while ( v9 );
  CoTaskMemFree(v10);
  v33 = WindirPathFromBootVolumeProp;
  CBsString::_Release((CBsString *)&v41);
  if ( v8 && _InterlockedExchangeAdd((volatile signed __int32 *)v8, 0xFFFFFFFF) == 1 )
  {
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::~CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>(v8);
    operator delete(v8);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&WindirPathFromBootVolumeProp);
  return v33;
}

```

## disassembly

```asm
0x18000af70  mov     [rsp-8+arg_18], r9
0x18000af75  push    rbp
0x18000af76  push    rbx
0x18000af77  push    rsi
0x18000af78  push    rdi
0x18000af79  push    r12
0x18000af7b  push    r13
0x18000af7d  push    r14
0x18000af7f  push    r15
0x18000af81  lea     rbp, [rsp-0Fh]
0x18000af86  sub     rsp, 0B8h
0x18000af8d  mov     r14, r8
0x18000af90  mov     rdi, rdx
0x18000af93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000af9a  lea     rax, WPP_GLOBAL_Control
0x18000afa1  cmp     rcx, rax
0x18000afa4  jz      short loc_18000AFC4
0x18000afa6  test    dword ptr [rcx+1Ch], 20000000h
0x18000afad  jz      short loc_18000AFC4
0x18000afaf  mov     rcx, [rcx+10h]
0x18000afb3  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000afba  mov     edx, 1Dh
0x18000afbf  call    WPP_SF_
0x18000afc4  mov     r8d, 2A9h; unsigned __int16
0x18000afca  lea     rdx, aCsrdrvwuhelper_7; "CSrDrvWuHelper::GetWindowsUpdates"
0x18000afd1  lea     rcx, [rbp+47h+var_B0]; this
0x18000afd5  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000afda  xor     edx, edx
0x18000afdc  lea     rax, qword_18001A620
0x18000afe3  xorps   xmm0, xmm0
0x18000afe6  mov     [rbp+47h+var_70], rax
0x18000afea  xorps   xmm1, xmm1
0x18000afed  mov     [rbp+47h+var_68], rdx
0x18000aff1  mov     ebx, edx
0x18000aff3  mov     [rbp+47h+var_78], rdx
0x18000aff7  lea     r15d, [rdx+10h]
0x18000affb  mov     r13d, edx
0x18000affe  mov     ecx, r15d
0x18000b001  lea     rax, [rbp+47h+var_60]
0x18000b005  movups  [rbp+47h+var_60], xmm0
0x18000b009  movups  xmmword ptr [rbp+47h+var_C0], xmm1
0x18000b00d  mov     [rax], dl
0x18000b00f  inc     rax
0x18000b012  sub     rcx, 1
0x18000b016  jnz     short loc_18000B00D
0x18000b018  mov     rcx, r15
0x18000b01b  lea     rax, [rbp+47h+var_C0]
0x18000b01f  mov     [rax], dl
0x18000b021  inc     rax
0x18000b024  sub     rcx, 1
0x18000b028  jnz     short loc_18000B01F
0x18000b02a  mov     rsi, [rbp+47h+arg_20]
0x18000b02e  mov     eax, 2B4h
0x18000b033  test    rsi, rsi
0x18000b036  jnz     short loc_18000B044
0x18000b038  mov     [rbp+47h+var_B0], 80070057h
0x18000b03f  jmp     loc_18000B332
0x18000b044  mov     r12, [rbp+47h+arg_28]
0x18000b048  mov     [rbp+47h+var_AC], ax
0x18000b04c  mov     eax, 2B5h
0x18000b051  test    r12, r12
0x18000b054  jz      short loc_18000B038
0x18000b056  mov     [rbp+47h+var_AC], ax
0x18000b05a  test    rdi, rdi
0x18000b05d  jz      short loc_18000B075
0x18000b05f  test    r14, r14
0x18000b062  jz      short loc_18000B075
0x18000b064  mov     [rbp+47h+var_B0], 80070057h
0x18000b06b  mov     eax, 2B6h
0x18000b070  jmp     loc_18000B332
0x18000b075  mov     eax, 2B6h
0x18000b07a  mov     [rbp+47h+var_B0], edx
0x18000b07d  mov     [rbp+47h+var_AC], ax
0x18000b081  mov     ecx, 18h; Size
0x18000b086  mov     [rsi], edx
0x18000b088  mov     [r12], rdx
0x18000b08c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b091  mov     rbx, rax
0x18000b094  test    rax, rax
0x18000b097  jz      loc_18000B324
0x18000b09d  mov     dword ptr [rax], 1
0x18000b0a3  mov     [rax+8], r13
0x18000b0a7  mov     [rax+10h], r13
0x18000b0ab  mov     [rbp+47h+var_B0], r13d
0x18000b0af  mov     eax, 2BBh
0x18000b0b4  mov     [rbp+47h+var_AC], ax
0x18000b0b8  test    rdi, rdi
0x18000b0bb  jz      loc_18000B1B4
0x18000b0c1  lea     rdx, [rbp+47h+var_70]; struct CBsString *
0x18000b0c5  mov     rcx, rdi; struct _SPP_BOOT_VOLUME_PROP *
0x18000b0c8  call    ?_GetWindirPathFromBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_BOOT_VOLUME_PROP@@PEAVCBsString@@@Z; CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(_SPP_BOOT_VOLUME_PROP const *,CBsString *)
0x18000b0cd  mov     [rbp+47h+var_B0], eax
0x18000b0d0  test    eax, eax
0x18000b0d2  mov     eax, 2BFh
0x18000b0d7  js      loc_18000B332
0x18000b0dd  mov     [rbp+47h+var_AC], ax
0x18000b0e1  cmp     dword ptr [rbp+47h+var_68], r13d
0x18000b0e5  jnz     short loc_18000B129
0x18000b0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0ee  lea     rax, WPP_GLOBAL_Control
0x18000b0f5  cmp     rcx, rax
0x18000b0f8  jz      short loc_18000B118
0x18000b0fa  test    dword ptr [rcx+1Ch], 2000000h
0x18000b101  jz      short loc_18000B118
0x18000b103  mov     rcx, [rcx+10h]
0x18000b107  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000b10e  mov     edx, 1Eh
0x18000b113  call    WPP_SF_
0x18000b118  mov     [rbp+47h+var_B0], 80070057h
0x18000b11f  mov     eax, 2C8h
0x18000b124  jmp     loc_18000B332
0x18000b129  movups  xmm0, xmmword ptr [rdi]
0x18000b12c  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18000b130  lea     r9, [rbp+47h+var_C0]; struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *
0x18000b134  xor     r8d, r8d; struct _DRVWUHELPER_ONDISK_DRIVER_INFO *
0x18000b137  lea     rdx, [rbp+47h+var_50]; struct _GUID
0x18000b13b  movdqu  xmmword ptr [rbp+47h+var_50.Data1], xmm0
0x18000b140  call    ?_GetDriverWUInfoFromCache@CSrDrvWuHelper@@CAJPEBGU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z; CSrDrvWuHelper::_GetDriverWUInfoFromCache(ushort const *,_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x18000b145  mov     [rbp+47h+var_B0], eax
0x18000b148  test    eax, eax
0x18000b14a  jns     loc_18000B2CF
0x18000b150  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b157  lea     rdx, WPP_GLOBAL_Control
0x18000b15e  cmp     rcx, rdx
0x18000b161  jz      short loc_18000B187
0x18000b163  test    dword ptr [rcx+1Ch], 4000000h
0x18000b16a  jz      short loc_18000B187
0x18000b16c  mov     r9, [rdi+28h]
0x18000b170  mov     edx, 1Fh
0x18000b175  mov     rcx, [rcx+10h]
0x18000b179  mov     dword ptr [rsp+0F0h+var_C8], eax
0x18000b17d  mov     [rsp+0F0h+var_D0], rdi; int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *)
0x18000b182  call    WPP_SF_S_guid_D
0x18000b187  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18000b18b  lea     rdx, [rbp+47h+var_78]; unsigned __int16 **
0x18000b18f  mov     [rbp+47h+var_B0], r13d
0x18000b193  call    ?_CreateTempDirectoryForWindowsUpdateEnumeration@CSrDrvWuHelper@@CAJPEBGPEAPEAG@Z; CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(ushort const *,ushort * *)
0x18000b198  mov     r13, [rbp+47h+var_78]
0x18000b19c  test    eax, eax
0x18000b19e  mov     [rbp+47h+var_B0], eax
0x18000b1a1  mov     eax, 2E1h
0x18000b1a6  js      loc_18000B332
0x18000b1ac  mov     r14, [rbp+47h+var_70]
0x18000b1b0  mov     [rbp+47h+var_AC], ax
0x18000b1b4  mov     rax, [rbp+47h+arg_18]
0x18000b1b8  xor     r9d, r9d
0x18000b1bb  mov     qword ptr [rbp+47h+var_60+8], rax
0x18000b1bf  test    rdi, rdi
0x18000b1c2  lea     rax, [rbp+47h+var_60]
0x18000b1c6  mov     qword ptr [rbp+47h+var_60], rbx
0x18000b1ca  setnz   r9b; int
0x18000b1ce  mov     [rsp+0F0h+var_C8], rax; void *
0x18000b1d3  mov     r8, r13; unsigned __int16 *
0x18000b1d6  mov     rcx, r14; unsigned __int16 *
0x18000b1d9  call    ?_GetWindowsUpdates@CSrDrvWuHelper@@CAJPEBG00HP6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z; CSrDrvWuHelper::_GetWindowsUpdates(ushort const *,ushort const *,ushort const *,int,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)
0x18000b1de  mov     [rbp+47h+var_B0], eax
0x18000b1e1  test    eax, eax
0x18000b1e3  mov     eax, 2ECh
0x18000b1e8  js      loc_18000B332
0x18000b1ee  lea     rdx, [rbp+47h+var_C0+8]; unsigned __int16 ***
0x18000b1f2  mov     [rbp+47h+var_AC], ax
0x18000b1f6  lea     rcx, [rbp+47h+var_C0]; unsigned int *
0x18000b1fa  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x18000b1ff  mov     rcx, r15
0x18000b202  lea     rax, [rbp+47h+var_C0]
0x18000b206  mov     byte ptr [rax], 0
0x18000b209  inc     rax
0x18000b20c  sub     rcx, 1
0x18000b210  jnz     short loc_18000B206
0x18000b212  mov     eax, [rbx+10h]
0x18000b215  lea     r9, ?_StringSortRoutine@CSrDrvWuHelper@@CAHPEBX0@Z; CompareFunction
0x18000b21c  mov     rcx, [rbx+8]; Base
0x18000b220  mov     edx, eax; NumOfElements
0x18000b222  mov     qword ptr [rbx+8], 0
0x18000b22a  mov     r8d, 8; SizeOfElements
0x18000b230  mov     qword ptr [rbx+10h], 0
0x18000b238  mov     [rbp+47h+var_C0+8], rcx
0x18000b23c  mov     dword ptr [rbp+47h+var_C0], eax
0x18000b23f  call    cs:__imp_qsort
0x18000b245  test    rdi, rdi
0x18000b248  jz      short loc_18000B2AD
0x18000b24a  movups  xmm0, xmmword ptr [rdi]
0x18000b24d  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18000b251  lea     r9, [rbp+47h+var_C0]; struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *
0x18000b255  xor     r8d, r8d; struct _DRVWUHELPER_ONDISK_DRIVER_INFO *
0x18000b258  lea     rdx, [rbp+47h+var_50]; struct _GUID
0x18000b25c  movdqu  xmmword ptr [rbp+47h+var_50.Data1], xmm0
0x18000b261  call    ?_AddDriverWUInfoToCache@CSrDrvWuHelper@@CAJPEBGU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z; CSrDrvWuHelper::_AddDriverWUInfoToCache(ushort const *,_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x18000b266  mov     [rbp+47h+var_B0], eax
0x18000b269  test    eax, eax
0x18000b26b  jns     short loc_18000B2AD
0x18000b26d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b274  lea     rdx, WPP_GLOBAL_Control
0x18000b27b  cmp     rcx, rdx
0x18000b27e  jz      short loc_18000B2A6
0x18000b280  test    dword ptr [rcx+1Ch], 4000000h
0x18000b287  jz      short loc_18000B2A6
0x18000b289  mov     r9, [rdi+28h]
0x18000b28d  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000b294  mov     rcx, [rcx+10h]
0x18000b298  mov     edx, 21h ; '!'
0x18000b29d  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18000b2a1  call    WPP_SF_SD
0x18000b2a6  mov     [rbp+47h+var_B0], 0
0x18000b2ad  mov     rax, [rbp+47h+var_C0+8]
0x18000b2b1  mov     rcx, r15
0x18000b2b4  mov     [r12], rax
0x18000b2b8  mov     eax, dword ptr [rbp+47h+var_C0]
0x18000b2bb  mov     [rsi], eax
0x18000b2bd  lea     rax, [rbp+47h+var_C0]
0x18000b2c1  mov     byte ptr [rax], 0
0x18000b2c4  inc     rax
0x18000b2c7  sub     rcx, 1
0x18000b2cb  jnz     short loc_18000B2C1
0x18000b2cd  jmp     short loc_18000B336
0x18000b2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2d6  lea     rax, WPP_GLOBAL_Control
0x18000b2dd  cmp     rcx, rax
0x18000b2e0  jz      short loc_18000B300
0x18000b2e2  test    dword ptr [rcx+1Ch], 8000000h
0x18000b2e9  jz      short loc_18000B300
0x18000b2eb  mov     rcx, [rcx+10h]
0x18000b2ef  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000b2f6  mov     edx, 20h ; ' '
0x18000b2fb  call    WPP_SF_
0x18000b300  mov     eax, dword ptr [rbp+47h+var_C0]
0x18000b303  mov     [rsi], eax
0x18000b305  mov     rax, [rbp+47h+var_C0+8]
0x18000b309  mov     [r12], rax
0x18000b30d  mov     eax, 2DCh
0x18000b312  mov     [rbp+47h+var_AC], ax
0x18000b316  mov     dword ptr [rbp+47h+var_C0], r13d
0x18000b31a  mov     [rbp+47h+var_C0+8], r13
0x18000b31e  mov     [rbp+47h+var_B0], r13d
0x18000b322  jmp     short loc_18000B336
0x18000b324  xor     ebx, ebx
0x18000b326  mov     [rbp+47h+var_B0], 8007000Eh
0x18000b32d  mov     eax, 2BBh
0x18000b332  mov     [rbp+47h+var_AA], ax
0x18000b336  lea     rdx, [rbp+47h+var_C0+8]; unsigned __int16 ***
0x18000b33a  lea     rcx, [rbp+47h+var_C0]; unsigned int *
0x18000b33e  call    ?Free_StringArray@@YAXPEAKPEAPEAPEAG@Z; Free_StringArray(ulong *,ushort * * *)
0x18000b343  lea     rax, [rbp+47h+var_C0]
0x18000b347  mov     byte ptr [rax], 0
0x18000b34a  inc     rax
0x18000b34d  sub     r15, 1
0x18000b351  jnz     short loc_18000B347
0x18000b353  mov     rcx, r13; pv
0x18000b356  call    cs:__imp_CoTaskMemFree
0x18000b35c  mov     edi, [rbp+47h+var_B0]
0x18000b35f  lea     rcx, [rbp+47h+var_70]; this
0x18000b363  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000b368  test    rbx, rbx
0x18000b36b  jz      short loc_18000B389
0x18000b36d  or      ecx, 0FFFFFFFFh
0x18000b370  lock xadd [rbx], ecx
0x18000b374  cmp     ecx, 1
0x18000b377  jnz     short loc_18000B389
0x18000b379  mov     rcx, rbx
0x18000b37c  call    ??1?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@AEAA@XZ; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::~CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>(void)
0x18000b381  mov     rcx, rbx; Block
0x18000b384  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b389  lea     rcx, [rbp+47h+var_B0]; this
0x18000b38d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000b392  mov     eax, edi
0x18000b394  add     rsp, 0B8h
0x18000b39b  pop     r15
0x18000b39d  pop     r14
0x18000b39f  pop     r13
0x18000b3a1  pop     r12
0x18000b3a3  pop     rdi
0x18000b3a4  pop     rsi
0x18000b3a5  pop     rbx
0x18000b3a6  pop     rbp
0x18000b3a7  retn
```

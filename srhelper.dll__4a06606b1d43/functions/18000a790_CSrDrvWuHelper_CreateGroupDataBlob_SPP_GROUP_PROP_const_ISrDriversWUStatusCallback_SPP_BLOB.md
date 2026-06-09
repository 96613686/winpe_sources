# CSrDrvWuHelper::CreateGroupDataBlob(_SPP_GROUP_PROP const *,ISrDriversWUStatusCallback *,_SPP_BLOB *)

- ea: `0x18000a790`
- end: `0x18000ab7a`
- name: `?CreateGroupDataBlob@CSrDrvWuHelper@@UEAAJPEBU_SPP_GROUP_PROP@@PEAUISrDriversWUStatusCallback@@PEAU_SPP_BLOB@@@Z`
- size: `1002`
- prototype: `__int64 __fastcall(CSrDrvWuHelper *this, const struct _SPP_GROUP_PROP *, struct ISrDriversWUStatusCallback *, struct _SPP_BLOB *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1800012d4`
- `0x1800012f8`
- `0x180003ce0`
- `0x180003d08`
- `0x18000a6a8`
- `0x18000a790`
- `0x18000bbe0`
- `0x18000bf70`
- `0x18000c258`
- `0x18000c6e0`
- `0x18000c890`
- `0x18000cc20`
- `0x18000d348`
- `0x18000d43c`
- `0x180015760`
- `0x1800157be`
- `0x1800157f0`
- `0x180016010`

## import_xrefs

- `msvcrt!qsort` at `0x18000a9b5`
- `msvcrt!qsort` at `0x18000aa14`
- `msvcrt!qsort` at `0x18000a9b5`
- `msvcrt!qsort` at `0x18000aa14`
- `ole32!CoCreateInstance` at `0x18000aa92`
- `ole32!CoCreateInstance` at `0x18000aa92`

## string_xrefs

- `0x18000a7f6`: `CSrDrvWuHelper::CreateGroupDataBlob`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::CreateGroupDataBlob(
        CSrDrvWuHelper *this,
        const struct _SPP_GROUP_PROP *a2,
        struct ISrDriversWUStatusCallback *a3,
        struct _SPP_BLOB *a4)
{
  __int64 v7; // rcx
  __int128 *v8; // rax
  void *v9; // rbx
  __int64 v10; // rdx
  __int16 v11; // ax
  int BootVolumeProp; // edi
  struct _SPP_BLOB *v13; // rax
  _DWORD *v14; // rax
  unsigned __int16 *v15; // rdx
  struct _TOKEN_PRIVILEGES *v16; // r8
  __int64 v17; // rdx
  void *v18; // rcx
  unsigned int v19; // eax
  const unsigned __int16 *v20; // rdx
  __int64 v21; // rdx
  void *v22; // rcx
  unsigned int v23; // eax
  int v24; // eax
  int (__high *ppv)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *); // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v29; // [rsp+4Ch] [rbp-B4h]
  __int16 v30; // [rsp+4Eh] [rbp-B2h]
  LPVOID v31; // [rsp+80h] [rbp-80h] BYREF
  __int128 v32; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v33; // [rsp+98h] [rbp-68h] BYREF
  __int64 v34; // [rsp+A0h] [rbp-60h]
  __int128 v35; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v37; // [rsp+D0h] [rbp-30h] BYREF
  int v38; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v39[36]; // [rsp+E4h] [rbp-1Ch] BYREF
  unsigned __int16 *v40; // [rsp+108h] [rbp+8h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v28,
    "CSrDrvWuHelper::CreateGroupDataBlob",
    0x3FFu,
    (unsigned __int16)a4);
  v38 = 0;
  memset_0(v39, 0, 0x4Cu);
  v27 = 0;
  v33 = (unsigned __int16 *)qword_18001A620;
  *(_QWORD *)&v37.Data1 = 0;
  v7 = 16;
  v31 = 0;
  v8 = &v32;
  v34 = 0;
  v36 = 0;
  v9 = 0;
  v10 = 16;
  v35 = 0;
  v32 = 0;
  do
  {
    *(_BYTE *)v8 = 0;
    v8 = (__int128 *)((char *)v8 + 1);
    --v10;
  }
  while ( v10 );
  v11 = 1039;
  if ( !a2 || (v29 = 1039, v11 = 1040, !a4) )
  {
    BootVolumeProp = -2147024809;
LABEL_8:
    v28 = BootVolumeProp;
    goto LABEL_9;
  }
  v29 = 1040;
  v13 = a4;
  v28 = 0;
  do
  {
    *(_BYTE *)v13 = 0;
    v13 = (struct _SPP_BLOB *)((char *)v13 + 1);
    --v7;
  }
  while ( v7 );
  BootVolumeProp = CSrDrvWuHelper::_GetBootVolumeProp(a2, (struct _SPP_BOOT_VOLUME_PROP *)&v38, &v27);
  v28 = BootVolumeProp;
  v11 = 1044;
  if ( BootVolumeProp < 0 )
    goto LABEL_9;
  v29 = 1044;
  if ( !v27 )
    goto LABEL_25;
  BootVolumeProp = CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(
                     (const struct _SPP_BOOT_VOLUME_PROP *)&v38,
                     (struct CBsString *)&v33);
  v28 = BootVolumeProp;
  v11 = 1047;
  if ( BootVolumeProp < 0 )
    goto LABEL_9;
  v29 = 1047;
  if ( !(_DWORD)v34 )
    goto LABEL_25;
  v14 = operator new(0x18u);
  v9 = v14;
  if ( !v14 )
  {
    v9 = 0;
    BootVolumeProp = -2147024882;
    v11 = 1054;
    goto LABEL_8;
  }
  *v14 = 1;
  *((_QWORD *)v14 + 1) = 0;
  *((_QWORD *)v14 + 2) = 0;
  v28 = 0;
  v29 = 1054;
  *((_QWORD *)&v32 + 1) = a3;
  *(_QWORD *)&v32 = v14;
  BootVolumeProp = CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(v40, (unsigned __int16 **)&v37);
  v28 = BootVolumeProp;
  v11 = 1061;
  if ( BootVolumeProp < 0 )
    goto LABEL_9;
  v29 = 1061;
  BootVolumeProp = CSrDrvWuHelper::_GetDrivers(v33, v15, v16, &v32);
  v28 = BootVolumeProp;
  v11 = 1064;
  if ( BootVolumeProp < 0 )
    goto LABEL_9;
  v17 = v32;
  v29 = 1064;
  v18 = *(void **)(v32 + 8);
  v19 = *(_DWORD *)(v32 + 16);
  *(_QWORD *)(v32 + 8) = 0;
  *(_QWORD *)(v17 + 16) = 0;
  *((_QWORD *)&v36 + 1) = v18;
  LODWORD(v36) = v19;
  qsort(v18, v19, 8u, CSrDrvWuHelper::_StringSortRoutine);
  BootVolumeProp = CSrDrvWuHelper::_GetWindowsUpdates(v33, v20, *(const unsigned __int16 **)&v37.Data1, 1, ppv, &v32);
  v28 = BootVolumeProp;
  v11 = 1071;
  if ( BootVolumeProp < 0 )
    goto LABEL_9;
  v21 = v32;
  v29 = 1071;
  v22 = *(void **)(v32 + 8);
  v23 = *(_DWORD *)(v32 + 16);
  *(_QWORD *)(v32 + 8) = 0;
  *(_QWORD *)(v21 + 16) = 0;
  *((_QWORD *)&v35 + 1) = v22;
  LODWORD(v35) = v23;
  qsort(v22, v23, 8u, CSrDrvWuHelper::_StringSortRoutine);
  v37 = *(struct _GUID *)a2;
  v24 = CSrDrvWuHelper::_AddDriverWUInfoToCache(
          v40,
          &v37,
          (struct _DRVWUHELPER_ONDISK_DRIVER_INFO *)&v36,
          (struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)&v35);
  if ( v24 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
  {
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      (unsigned int)WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids,
      (_DWORD)v40,
      v24);
  }
LABEL_25:
  BootVolumeProp = CoCreateInstance(&CLSID_SPP, 0, 1u, &IID_ISharedProtectionPoints, &v31);
  v28 = BootVolumeProp;
  v11 = 1087;
  if ( BootVolumeProp >= 0 )
  {
    v29 = 1087;
    BootVolumeProp = (*(__int64 (__fastcall **)(LPVOID, const struct _SPP_GROUP_PROP *, _QWORD, _QWORD, _DWORD, _QWORD, struct _SPP_BLOB *))(*(_QWORD *)v31 + 216LL))(
                       v31,
                       a2,
                       (unsigned int)v36,
                       *((_QWORD *)&v36 + 1),
                       v35,
                       *((_QWORD *)&v35 + 1),
                       a4);
    v28 = BootVolumeProp;
    v11 = 1095;
    if ( BootVolumeProp >= 0 )
    {
      v29 = 1095;
      goto LABEL_28;
    }
  }
LABEL_9:
  v30 = v11;
LABEL_28:
  CBsString::_Release((CBsString *)&v33);
  if ( v9 && _InterlockedExchangeAdd((volatile signed __int32 *)v9, 0xFFFFFFFF) == 1 )
  {
    CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>::~CSxArrayBuilder<unsigned short *,&void Free_String(unsigned short * *),&void SxDefaultInit<unsigned short *>(unsigned short * *),&void SxDefaultTransfer<unsigned short *>(unsigned short * *,unsigned short * *)>(v9);
    operator delete(v9);
  }
  if ( v31 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v31 + 16LL))(v31);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v28);
  return (unsigned int)BootVolumeProp;
}

```

## disassembly

```asm
0x18000a790  push    rbp
0x18000a792  push    rbx
0x18000a793  push    rdi
0x18000a794  push    r12
0x18000a796  push    r13
0x18000a798  push    r14
0x18000a79a  push    r15
0x18000a79c  lea     rbp, [rsp-40h]
0x18000a7a1  sub     rsp, 140h
0x18000a7a8  mov     rax, cs:__security_cookie
0x18000a7af  xor     rax, rsp
0x18000a7b2  mov     [rbp+70h+var_40], rax
0x18000a7b6  mov     r15, r9
0x18000a7b9  mov     r12, r8
0x18000a7bc  mov     r14, rdx
0x18000a7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7c6  lea     rax, WPP_GLOBAL_Control
0x18000a7cd  cmp     rcx, rax
0x18000a7d0  jz      short loc_18000A7F0
0x18000a7d2  test    dword ptr [rcx+1Ch], 20000000h
0x18000a7d9  jz      short loc_18000A7F0
0x18000a7db  mov     rcx, [rcx+10h]
0x18000a7df  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000a7e6  mov     edx, 29h ; ')'
0x18000a7eb  call    WPP_SF_
0x18000a7f0  mov     r8d, 3FFh; unsigned __int16
0x18000a7f6  lea     rdx, aCsrdrvwuhelper_10; "CSrDrvWuHelper::CreateGroupDataBlob"
0x18000a7fd  lea     rcx, [rsp+170h+var_128]; this
0x18000a802  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a807  xor     r13d, r13d
0x18000a80a  lea     rcx, [rbp+70h+var_8C]; void *
0x18000a80e  xor     edx, edx; Val
0x18000a810  mov     [rbp+70h+var_90], r13d
0x18000a814  lea     r8d, [r13+4Ch]; Size
0x18000a818  call    memset_0
0x18000a81d  lea     rax, qword_18001A620
0x18000a824  mov     [rsp+170h+var_130], r13d
0x18000a829  xorps   xmm0, xmm0
0x18000a82c  mov     [rbp+70h+var_D8], rax
0x18000a830  xorps   xmm1, xmm1
0x18000a833  mov     qword ptr [rbp+70h+var_A0.Data1], r13
0x18000a837  lea     ecx, [r13+10h]
0x18000a83b  mov     [rbp+70h+var_F0], r13
0x18000a83f  lea     rax, [rbp+70h+var_E8]
0x18000a843  mov     [rbp+70h+var_D0], r13
0x18000a847  movups  [rbp+70h+var_B8], xmm0
0x18000a84b  mov     ebx, r13d
0x18000a84e  mov     edx, ecx
0x18000a850  movups  [rbp+70h+var_C8], xmm1
0x18000a854  movups  [rbp+70h+var_E8], xmm0
0x18000a858  mov     [rax], r13b
0x18000a85b  inc     rax
0x18000a85e  sub     rdx, 1
0x18000a862  jnz     short loc_18000A858
0x18000a864  mov     eax, 40Fh
0x18000a869  test    r14, r14
0x18000a86c  jnz     short loc_18000A881
0x18000a86e  mov     edi, 80070057h
0x18000a873  mov     [rsp+170h+var_128], edi
0x18000a877  mov     [rsp+170h+var_122], ax
0x18000a87c  jmp     loc_18000AAFE
0x18000a881  mov     [rsp+170h+var_124], ax
0x18000a886  mov     eax, 410h
0x18000a88b  test    r15, r15
0x18000a88e  jz      short loc_18000A86E
0x18000a890  mov     [rsp+170h+var_124], ax
0x18000a895  mov     rax, r15
0x18000a898  mov     [rsp+170h+var_128], r13d
0x18000a89d  mov     [rax], r13b
0x18000a8a0  inc     rax
0x18000a8a3  sub     rcx, 1
0x18000a8a7  jnz     short loc_18000A89D
0x18000a8a9  lea     r8, [rsp+170h+var_130]; int *
0x18000a8ae  mov     rcx, r14; struct _SPP_GROUP_PROP *
0x18000a8b1  lea     rdx, [rbp+70h+var_90]; struct _SPP_BOOT_VOLUME_PROP *
0x18000a8b5  call    ?_GetBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_GROUP_PROP@@PEAU_SPP_BOOT_VOLUME_PROP@@PEAH@Z; CSrDrvWuHelper::_GetBootVolumeProp(_SPP_GROUP_PROP const *,_SPP_BOOT_VOLUME_PROP *,int *)
0x18000a8ba  mov     edi, eax
0x18000a8bc  mov     [rsp+170h+var_128], eax
0x18000a8c0  test    eax, eax
0x18000a8c2  mov     eax, 414h
0x18000a8c7  js      short loc_18000A877
0x18000a8c9  mov     [rsp+170h+var_124], ax
0x18000a8ce  cmp     [rsp+170h+var_130], r13d
0x18000a8d3  jz      loc_18000AA75
0x18000a8d9  lea     rdx, [rbp+70h+var_D8]; struct CBsString *
0x18000a8dd  lea     rcx, [rbp+70h+var_90]; struct _SPP_BOOT_VOLUME_PROP *
0x18000a8e1  call    ?_GetWindirPathFromBootVolumeProp@CSrDrvWuHelper@@CAJPEBU_SPP_BOOT_VOLUME_PROP@@PEAVCBsString@@@Z; CSrDrvWuHelper::_GetWindirPathFromBootVolumeProp(_SPP_BOOT_VOLUME_PROP const *,CBsString *)
0x18000a8e6  mov     edi, eax
0x18000a8e8  mov     [rsp+170h+var_128], eax
0x18000a8ec  test    eax, eax
0x18000a8ee  mov     eax, 417h
0x18000a8f3  js      short loc_18000A877
0x18000a8f5  mov     [rsp+170h+var_124], ax
0x18000a8fa  cmp     dword ptr [rbp+70h+var_D0], r13d
0x18000a8fe  jz      loc_18000AA75
0x18000a904  mov     ecx, 18h; Size
0x18000a909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a90e  mov     rbx, rax
0x18000a911  test    rax, rax
0x18000a914  jz      loc_18000AB68
0x18000a91a  mov     dword ptr [rax], 1
0x18000a920  mov     [rax+8], r13
0x18000a924  mov     [rax+10h], r13
0x18000a928  mov     rcx, [rbp+70h+var_68]; unsigned __int16 *
0x18000a92c  lea     rdx, [rbp+70h+var_A0]; unsigned __int16 **
0x18000a930  mov     eax, 41Eh
0x18000a935  mov     [rsp+170h+var_128], r13d
0x18000a93a  mov     [rsp+170h+var_124], ax
0x18000a93f  mov     qword ptr [rbp+70h+var_E8+8], r12
0x18000a943  mov     qword ptr [rbp+70h+var_E8], rbx
0x18000a947  call    ?_CreateTempDirectoryForWindowsUpdateEnumeration@CSrDrvWuHelper@@CAJPEBGPEAPEAG@Z; CSrDrvWuHelper::_CreateTempDirectoryForWindowsUpdateEnumeration(ushort const *,ushort * *)
0x18000a94c  mov     edi, eax
0x18000a94e  mov     [rsp+170h+var_128], eax
0x18000a952  test    eax, eax
0x18000a954  mov     eax, 425h
0x18000a959  js      loc_18000A877
0x18000a95f  mov     rcx, [rbp+70h+var_D8]; unsigned __int16 *
0x18000a963  lea     r9, [rbp+70h+var_E8]; void *
0x18000a967  mov     [rsp+170h+var_124], ax
0x18000a96c  call    ?_GetDrivers@CSrDrvWuHelper@@CAJPEBG0P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z; CSrDrvWuHelper::_GetDrivers(ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)
0x18000a971  mov     edi, eax
0x18000a973  mov     [rsp+170h+var_128], eax
0x18000a977  test    eax, eax
0x18000a979  mov     eax, 428h
0x18000a97e  js      loc_18000A877
0x18000a984  mov     rdx, qword ptr [rbp+70h+var_E8]
0x18000a988  lea     r9, ?_StringSortRoutine@CSrDrvWuHelper@@CAHPEBX0@Z; CompareFunction
0x18000a98f  mov     [rsp+170h+var_124], ax
0x18000a994  mov     r12d, 8
0x18000a99a  mov     r8d, r12d; SizeOfElements
0x18000a99d  mov     rcx, [rdx+8]; Base
0x18000a9a1  mov     eax, [rdx+10h]
0x18000a9a4  mov     [rdx+8], r13
0x18000a9a8  mov     [rdx+10h], r13
0x18000a9ac  mov     edx, eax; NumOfElements
0x18000a9ae  mov     qword ptr [rbp+70h+var_B8+8], rcx
0x18000a9b2  mov     dword ptr [rbp+70h+var_B8], eax
0x18000a9b5  call    cs:__imp_qsort
0x18000a9bb  mov     r8, qword ptr [rbp+70h+var_A0.Data1]; unsigned __int16 *
0x18000a9bf  lea     rax, [rbp+70h+var_E8]
0x18000a9c3  mov     rcx, [rbp+70h+var_D8]; unsigned __int16 *
0x18000a9c7  lea     r9d, [r12-7]; int
0x18000a9cc  mov     [rsp+170h+var_148], rax; void *
0x18000a9d1  call    ?_GetWindowsUpdates@CSrDrvWuHelper@@CAJPEBG00HP6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z; CSrDrvWuHelper::_GetWindowsUpdates(ushort const *,ushort const *,ushort const *,int,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)
0x18000a9d6  mov     edi, eax
0x18000a9d8  mov     [rsp+170h+var_128], eax
0x18000a9dc  test    eax, eax
0x18000a9de  mov     eax, 42Fh
0x18000a9e3  js      loc_18000A877
0x18000a9e9  mov     rdx, qword ptr [rbp+70h+var_E8]
0x18000a9ed  lea     r9, ?_StringSortRoutine@CSrDrvWuHelper@@CAHPEBX0@Z; CompareFunction
0x18000a9f4  mov     [rsp+170h+var_124], ax
0x18000a9f9  mov     r8d, r12d; SizeOfElements
0x18000a9fc  mov     rcx, [rdx+8]; Base
0x18000aa00  mov     eax, [rdx+10h]
0x18000aa03  mov     [rdx+8], r13
0x18000aa07  mov     [rdx+10h], r13
0x18000aa0b  mov     edx, eax; NumOfElements
0x18000aa0d  mov     qword ptr [rbp+70h+var_C8+8], rcx
0x18000aa11  mov     dword ptr [rbp+70h+var_C8], eax
0x18000aa14  call    cs:__imp_qsort
0x18000aa1a  movups  xmm0, xmmword ptr [r14]
0x18000aa1e  mov     rcx, [rbp+70h+var_68]; unsigned __int16 *
0x18000aa22  lea     r9, [rbp+70h+var_C8]; struct _DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *
0x18000aa26  lea     r8, [rbp+70h+var_B8]; struct _DRVWUHELPER_ONDISK_DRIVER_INFO *
0x18000aa2a  lea     rdx, [rbp+70h+var_A0]; struct _GUID
0x18000aa2e  movdqu  xmmword ptr [rbp+70h+var_A0.Data1], xmm0
0x18000aa33  call    ?_AddDriverWUInfoToCache@CSrDrvWuHelper@@CAJPEBGU_GUID@@PEAU_DRVWUHELPER_ONDISK_DRIVER_INFO@@PEAU_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO@@@Z; CSrDrvWuHelper::_AddDriverWUInfoToCache(ushort const *,_GUID,_DRVWUHELPER_ONDISK_DRIVER_INFO *,_DRVWUHELPER_ONDISK_WINDOWS_UPDATE_INFO *)
0x18000aa38  test    eax, eax
0x18000aa3a  jns     short loc_18000AA75
0x18000aa3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa43  lea     rdx, WPP_GLOBAL_Control
0x18000aa4a  cmp     rcx, rdx
0x18000aa4d  jz      short loc_18000AA75
0x18000aa4f  test    dword ptr [rcx+1Ch], 4000000h
0x18000aa56  jz      short loc_18000AA75
0x18000aa58  mov     r9, [rbp+70h+var_68]
0x18000aa5c  lea     edx, [r12+22h]
0x18000aa61  mov     rcx, [rcx+10h]
0x18000aa65  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000aa6c  mov     dword ptr [rsp+170h+ppv], eax
0x18000aa70  call    WPP_SF_SD
0x18000aa75  xor     edx, edx; pUnkOuter
0x18000aa77  lea     rax, [rbp+70h+var_F0]
0x18000aa7b  lea     r9, IID_ISharedProtectionPoints; riid
0x18000aa82  mov     [rsp+170h+ppv], rax; ppv
0x18000aa87  lea     rcx, CLSID_SPP; rclsid
0x18000aa8e  lea     r8d, [rdx+1]; dwClsContext
0x18000aa92  call    cs:__imp_CoCreateInstance
0x18000aa98  mov     edi, eax
0x18000aa9a  mov     [rsp+170h+var_128], eax
0x18000aa9e  test    eax, eax
0x18000aaa0  mov     eax, 43Fh
0x18000aaa5  js      loc_18000A877
0x18000aaab  mov     rcx, [rbp+70h+var_F0]
0x18000aaaf  mov     rdx, r14
0x18000aab2  mov     r9, qword ptr [rbp+70h+var_B8+8]
0x18000aab6  mov     r8d, dword ptr [rbp+70h+var_B8]
0x18000aaba  mov     [rsp+170h+var_124], ax
0x18000aabf  mov     rax, [rcx]
0x18000aac2  mov     [rsp+170h+var_140], r15
0x18000aac7  mov     r10, [rax+0D8h]
0x18000aace  mov     rax, qword ptr [rbp+70h+var_C8+8]
0x18000aad2  mov     [rsp+170h+var_148], rax
0x18000aad7  mov     eax, dword ptr [rbp+70h+var_C8]
0x18000aada  mov     dword ptr [rsp+170h+ppv], eax
0x18000aade  mov     rax, r10
0x18000aae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aae6  mov     edi, eax
0x18000aae8  mov     [rsp+170h+var_128], eax
0x18000aaec  test    eax, eax
0x18000aaee  mov     eax, 447h
0x18000aaf3  js      loc_18000A877
0x18000aaf9  mov     [rsp+170h+var_124], ax
0x18000aafe  lea     rcx, [rbp+70h+var_D8]; this
0x18000ab02  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000ab07  test    rbx, rbx
0x18000ab0a  jz      short loc_18000AB28
0x18000ab0c  or      eax, 0FFFFFFFFh
0x18000ab0f  lock xadd [rbx], eax
0x18000ab13  cmp     eax, 1
0x18000ab16  jnz     short loc_18000AB28
0x18000ab18  mov     rcx, rbx
0x18000ab1b  call    ??1?$CSxArrayBuilder@PEAG$1?Free_String@@YAXPEAPEAG@Z$1??$SxDefaultInit@PEAG@@YAX0@Z$1??$SxDefaultTransfer@PEAG@@YAX00@Z@@AEAA@XZ; CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>::~CSxArrayBuilder<ushort *,&Free_String(ushort * *),&SxDefaultInit<ushort *>(ushort * *),&SxDefaultTransfer<ushort *>(ushort * *,ushort * *)>(void)
0x18000ab20  mov     rcx, rbx; Block
0x18000ab23  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ab28  mov     rcx, [rbp+70h+var_F0]
0x18000ab2c  test    rcx, rcx
0x18000ab2f  jz      short loc_18000AB3D
0x18000ab31  mov     rdx, [rcx]
0x18000ab34  mov     rax, [rdx+10h]
0x18000ab38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab3d  lea     rcx, [rsp+170h+var_128]; this
0x18000ab42  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ab47  mov     eax, edi
0x18000ab49  mov     rcx, [rbp+70h+var_40]
0x18000ab4d  xor     rcx, rsp; StackCookie
0x18000ab50  call    __security_check_cookie
0x18000ab55  add     rsp, 140h
0x18000ab5c  pop     r15
0x18000ab5e  pop     r14
0x18000ab60  pop     r13
0x18000ab62  pop     r12
0x18000ab64  pop     rdi
0x18000ab65  pop     rbx
0x18000ab66  pop     rbp
0x18000ab67  retn
0x18000ab68  mov     rbx, r13
0x18000ab6b  mov     edi, 8007000Eh
0x18000ab70  mov     eax, 41Eh
0x18000ab75  jmp     loc_18000A873
```

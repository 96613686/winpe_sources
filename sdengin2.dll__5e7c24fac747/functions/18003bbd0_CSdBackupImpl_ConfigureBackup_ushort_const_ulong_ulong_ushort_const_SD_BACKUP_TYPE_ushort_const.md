# CSdBackupImpl::ConfigureBackup(ushort const *,ulong,ulong,ushort const *,_SD_BACKUP_TYPE,ushort const *)

- ea: `0x18003bbd0`
- end: `0x18003bf12`
- name: `?ConfigureBackup@CSdBackupImpl@@UEAAJPEBGKK0W4_SD_BACKUP_TYPE@@0@Z`
- size: `834`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003450`
- `0x180009a98`
- `0x180011274`
- `0x18001b0fc`
- `0x18003bbd0`
- `0x1800430dc`
- `0x18004b444`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180070ac0`
- `0x180089eec`
- `0x180099bf4`
- `0x18009a24c`
- `0x1800c97da`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003bdc4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003bdc4`
- `ole32!CoCreateInstance` at `0x18003beb9`
- `ole32!CoCreateInstance` at `0x18003beb9`
- `ole32!CoCreateGuid` at `0x18003be15`
- `ole32!CoCreateGuid` at `0x18003be15`

## string_xrefs

- `0x18003bbfd`: `CSdBackupImpl::ConfigureBackup`

## pseudocode

```c
__int64 __fastcall CSdBackupImpl::ConfigureBackup(
        __int64 a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        int a4,
        unsigned __int16 *a5,
        int a6,
        const WCHAR *lpSrc)
{
  __int16 v11; // ax
  unsigned int v12; // ebx
  int v14; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT StorageDevice; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v16; // [rsp+3Ch] [rbp-C4h]
  __int16 v17; // [rsp+3Eh] [rbp-C2h]
  struct ISdGlobalCatalog *v18; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v19; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v20[7]; // [rsp+80h] [rbp-80h] BYREF
  int v21; // [rsp+B8h] [rbp-48h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&StorageDevice, "CSdBackupImpl::ConfigureBackup", 2309, 1);
  v19 = 0;
  v18 = 0;
  v14 = 0;
  memset_0(v20, 0, 0x90u);
  StorageDevice = VerifyCallerSystem();
  v11 = 2315;
  if ( StorageDevice < 0 )
    goto LABEL_2;
  v16 = 2315;
  v11 = 2317;
  if ( a2
    && (v16 = 2317, v11 = 2318, (a3 & 0xEFFFFF80) == 0)
    && (v16 = 2318, v11 = 2319, a6)
    && (v16 = 2319, v11 = 2320, lpSrc) )
  {
    StorageDevice = 0;
    v16 = 2320;
    *(_DWORD *)(a1 + 176) = a3;
    *(_DWORD *)(a1 + 180) = a4;
    *(_DWORD *)(a1 + 188) = a6;
    StorageDevice = SetStorageDeviceName(*(struct IMSDCommonImpl **)(a1 + 352), a2, (struct CBsString *)(a1 + 56));
    v11 = 2326;
    if ( StorageDevice < 0 )
      goto LABEL_2;
    v16 = 2326;
    StorageDevice = (*(__int64 (__fastcall **)(_QWORD, struct ISdGlobalCatalog **))(**(_QWORD **)(a1 + 352) + 168LL))(
                      *(_QWORD *)(a1 + 352),
                      &v18);
    v11 = 2328;
    if ( StorageDevice < 0 )
      goto LABEL_2;
    v16 = 2328;
    v11 = 2329;
    if ( v18 )
    {
      StorageDevice = 0;
      v16 = 2329;
      StorageDevice = QueryStorageDevice(a2, (struct _SD_STORAGE_DEVICE_PROP *)v20);
      v11 = 2334;
      if ( StorageDevice >= 0 )
      {
        v16 = 2334;
        if ( v21 == 7 )
        {
          StorageDevice = CSdBackupImpl::_VerifyStorageDeviceForNetShare(
                            (CSdBackupImpl *)a1,
                            v18,
                            a3,
                            (const struct _SD_STORAGE_DEVICE_PROP *)v20);
          v11 = 2337;
          if ( StorageDevice < 0 )
            goto LABEL_2;
          v16 = 2337;
        }
        if ( a5 && *a5 )
        {
          *(_DWORD *)(a1 + 88) = 1;
          StorageDevice = CBsString::Set((CBsString *)(a1 + 72), a5);
          v11 = 2346;
          if ( StorageDevice < 0 )
            goto LABEL_2;
          v16 = 2346;
        }
        GetSystemTimeAsFileTime((LPFILETIME)(a1 + 168));
        StorageDevice = CBsString::ExpandEnvironmentStringsW((CBsString *)(a1 + 96), lpSrc);
        v11 = 2351;
        if ( StorageDevice >= 0 )
        {
          v16 = 2351;
          StorageDevice = CSdBackupImpl::_InitializeBackupLog((CSdBackupImpl *)a1);
          v11 = 2352;
          if ( StorageDevice >= 0 )
          {
            v16 = 2352;
            StorageDevice = CoCreateGuid((GUID *)(a1 + 136));
            v11 = 2354;
            if ( StorageDevice >= 0 )
            {
              v16 = 2354;
              StorageDevice = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 352) + 184LL))(
                                *(_QWORD *)(a1 + 352),
                                &v14);
              v11 = 2356;
              if ( StorageDevice >= 0 )
              {
                v16 = 2356;
                v14 |= 1u;
                StorageDevice = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 352) + 192LL))(*(_QWORD *)(a1 + 352));
                v11 = 2358;
                if ( StorageDevice >= 0 )
                {
                  v16 = 2358;
                  StorageDevice = CoCreateInstance(
                                    &CLSID_SPP,
                                    0,
                                    1u,
                                    &IID_ISharedProtectionPoints,
                                    (LPVOID *)(a1 + 704));
                  v11 = 2361;
                  if ( StorageDevice >= 0 )
                  {
                    v16 = 2361;
                    goto LABEL_27;
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      StorageDevice = -2130706378;
    }
  }
  else
  {
    StorageDevice = -2147024809;
  }
LABEL_2:
  v17 = v11;
LABEL_27:
  CleanupStorageDeviceProp(v20);
  SdFreeString(&v19);
  v12 = StorageDevice;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StorageDevice);
  return v12;
}

```

## disassembly

```asm
0x18003bbd0  push    rbp
0x18003bbd2  push    rbx
0x18003bbd3  push    rsi
0x18003bbd4  push    rdi
0x18003bbd5  push    r12
0x18003bbd7  push    r15
0x18003bbd9  lea     rbp, [rsp-18h]
0x18003bbde  sub     rsp, 118h
0x18003bbe5  mov     r15d, r9d
0x18003bbe8  mov     esi, r8d
0x18003bbeb  mov     rdi, rdx
0x18003bbee  mov     rbx, rcx
0x18003bbf1  mov     r9d, 1; unsigned __int16
0x18003bbf7  mov     r8d, 905h; unsigned __int16
0x18003bbfd  lea     rdx, aCsdbackupimplC_3; "CSdBackupImpl::ConfigureBackup"
0x18003bc04  lea     rcx, [rsp+140h+var_108]; this
0x18003bc09  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003bc0e  xor     r12d, r12d
0x18003bc11  mov     [rsp+140h+var_C8], r12
0x18003bc16  mov     [rsp+140h+var_D0], r12
0x18003bc1b  mov     [rsp+140h+var_110], r12d
0x18003bc20  xor     edx, edx; Val
0x18003bc22  mov     r8d, 90h; Size
0x18003bc28  lea     rcx, [rbp+40h+var_C0]; void *
0x18003bc2c  call    memset_0
0x18003bc31  call    ?VerifyCallerSystem@@YAJXZ; VerifyCallerSystem(void)
0x18003bc36  mov     [rsp+140h+var_108], eax
0x18003bc3a  test    eax, eax
0x18003bc3c  mov     eax, 90Bh
0x18003bc41  jns     short loc_18003BC4D
0x18003bc43  mov     [rsp+140h+var_102], ax
0x18003bc48  jmp     loc_18003BED5
0x18003bc4d  mov     [rsp+140h+var_104], ax
0x18003bc52  mov     eax, 90Dh
0x18003bc57  test    rdi, rdi
0x18003bc5a  jnz     short loc_18003BC66
0x18003bc5c  mov     [rsp+140h+var_108], 80070057h
0x18003bc64  jmp     short loc_18003BC43
0x18003bc66  mov     [rsp+140h+var_104], ax
0x18003bc6b  mov     eax, 90Eh
0x18003bc70  test    esi, 0EFFFFF80h
0x18003bc76  jnz     short loc_18003BC5C
0x18003bc78  mov     [rsp+140h+var_104], ax
0x18003bc7d  mov     ecx, [rbp+40h+arg_28]
0x18003bc80  mov     eax, 90Fh
0x18003bc85  test    ecx, ecx
0x18003bc87  jz      short loc_18003BC5C
0x18003bc89  mov     [rsp+140h+var_104], ax
0x18003bc8e  mov     eax, 910h
0x18003bc93  cmp     [rbp+40h+lpSrc], r12
0x18003bc9a  jz      short loc_18003BC5C
0x18003bc9c  mov     [rsp+140h+var_108], r12d
0x18003bca1  mov     [rsp+140h+var_104], ax
0x18003bca6  mov     [rbx+0B0h], esi
0x18003bcac  mov     [rbx+0B4h], r15d
0x18003bcb3  mov     [rbx+0BCh], ecx
0x18003bcb9  lea     r8, [rbx+38h]; struct CBsString *
0x18003bcbd  mov     rdx, rdi; unsigned __int16 *
0x18003bcc0  mov     rcx, [rbx+160h]; struct IMSDCommonImpl *
0x18003bcc7  call    ?SetStorageDeviceName@@YAJPEAUIMSDCommonImpl@@PEBGPEAVCBsString@@@Z; SetStorageDeviceName(IMSDCommonImpl *,ushort const *,CBsString *)
0x18003bccc  mov     [rsp+140h+var_108], eax
0x18003bcd0  test    eax, eax
0x18003bcd2  mov     eax, 916h
0x18003bcd7  js      loc_18003BC43
0x18003bcdd  mov     [rsp+140h+var_104], ax
0x18003bce2  mov     rcx, [rbx+160h]
0x18003bce9  mov     rax, [rcx]
0x18003bcec  lea     rdx, [rsp+140h+var_D0]
0x18003bcf1  mov     rax, [rax+0A8h]
0x18003bcf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bcfd  mov     [rsp+140h+var_108], eax
0x18003bd01  test    eax, eax
0x18003bd03  mov     eax, 918h
0x18003bd08  js      loc_18003BC43
0x18003bd0e  mov     [rsp+140h+var_104], ax
0x18003bd13  mov     eax, 919h
0x18003bd18  cmp     [rsp+140h+var_D0], r12
0x18003bd1d  jnz     short loc_18003BD2C
0x18003bd1f  mov     [rsp+140h+var_108], 81000036h
0x18003bd27  jmp     loc_18003BC43
0x18003bd2c  mov     [rsp+140h+var_108], r12d
0x18003bd31  mov     [rsp+140h+var_104], ax
0x18003bd36  lea     rdx, [rbp+40h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x18003bd3a  mov     rcx, rdi; unsigned __int16 *
0x18003bd3d  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x18003bd42  mov     [rsp+140h+var_108], eax
0x18003bd46  test    eax, eax
0x18003bd48  mov     eax, 91Eh
0x18003bd4d  js      loc_18003BC43
0x18003bd53  mov     [rsp+140h+var_104], ax
0x18003bd58  cmp     [rbp+40h+var_88], 7
0x18003bd5c  jnz     short loc_18003BD88
0x18003bd5e  lea     r9, [rbp+40h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x18003bd62  mov     r8d, esi; unsigned int
0x18003bd65  mov     rdx, [rsp+140h+var_D0]; struct ISdGlobalCatalog *
0x18003bd6a  mov     rcx, rbx; this
0x18003bd6d  call    ?_VerifyStorageDeviceForNetShare@CSdBackupImpl@@AEAAJPEAUISdGlobalCatalog@@KPEBU_SD_STORAGE_DEVICE_PROP@@@Z; CSdBackupImpl::_VerifyStorageDeviceForNetShare(ISdGlobalCatalog *,ulong,_SD_STORAGE_DEVICE_PROP const *)
0x18003bd72  mov     [rsp+140h+var_108], eax
0x18003bd76  test    eax, eax
0x18003bd78  mov     eax, 921h
0x18003bd7d  js      loc_18003BC43
0x18003bd83  mov     [rsp+140h+var_104], ax
0x18003bd88  mov     rdx, [rbp+40h+arg_20]; unsigned __int16 *
0x18003bd8c  test    rdx, rdx
0x18003bd8f  jz      short loc_18003BDBD
0x18003bd91  cmp     [rdx], r12w
0x18003bd95  jz      short loc_18003BDBD
0x18003bd97  mov     dword ptr [rbx+58h], 1
0x18003bd9e  lea     rcx, [rbx+48h]; this
0x18003bda2  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003bda7  mov     [rsp+140h+var_108], eax
0x18003bdab  test    eax, eax
0x18003bdad  mov     eax, 92Ah
0x18003bdb2  js      loc_18003BC43
0x18003bdb8  mov     [rsp+140h+var_104], ax
0x18003bdbd  lea     rcx, [rbx+0A8h]; lpSystemTimeAsFileTime
0x18003bdc4  call    cs:__imp_GetSystemTimeAsFileTime
0x18003bdca  lea     rcx, [rbx+60h]; this
0x18003bdce  mov     rdx, [rbp+40h+lpSrc]; lpSrc
0x18003bdd5  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18003bdda  mov     [rsp+140h+var_108], eax
0x18003bdde  test    eax, eax
0x18003bde0  mov     eax, 92Fh
0x18003bde5  js      loc_18003BC43
0x18003bdeb  mov     [rsp+140h+var_104], ax
0x18003bdf0  mov     rcx, rbx; this
0x18003bdf3  call    ?_InitializeBackupLog@CSdBackupImpl@@AEAAJXZ; CSdBackupImpl::_InitializeBackupLog(void)
0x18003bdf8  mov     [rsp+140h+var_108], eax
0x18003bdfc  test    eax, eax
0x18003bdfe  mov     eax, 930h
0x18003be03  js      loc_18003BC43
0x18003be09  mov     [rsp+140h+var_104], ax
0x18003be0e  lea     rcx, [rbx+88h]; pguid
0x18003be15  call    cs:__imp_CoCreateGuid
0x18003be1b  mov     [rsp+140h+var_108], eax
0x18003be1f  test    eax, eax
0x18003be21  mov     eax, 932h
0x18003be26  js      loc_18003BC43
0x18003be2c  mov     [rsp+140h+var_104], ax
0x18003be31  mov     rcx, [rbx+160h]
0x18003be38  mov     rax, [rcx]
0x18003be3b  lea     rdx, [rsp+140h+var_110]
0x18003be40  mov     rax, [rax+0B8h]
0x18003be47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be4c  mov     [rsp+140h+var_108], eax
0x18003be50  test    eax, eax
0x18003be52  mov     eax, 934h
0x18003be57  js      loc_18003BC43
0x18003be5d  mov     [rsp+140h+var_104], ax
0x18003be62  mov     edx, [rsp+140h+var_110]
0x18003be66  or      edx, 1
0x18003be69  mov     [rsp+140h+var_110], edx
0x18003be6d  mov     rcx, [rbx+160h]
0x18003be74  mov     rax, [rcx]
0x18003be77  mov     rax, [rax+0C0h]
0x18003be7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be83  mov     [rsp+140h+var_108], eax
0x18003be87  test    eax, eax
0x18003be89  mov     eax, 936h
0x18003be8e  js      loc_18003BC43
0x18003be94  mov     [rsp+140h+var_104], ax
0x18003be99  lea     rax, [rbx+2C0h]
0x18003bea0  mov     [rsp+140h+ppv], rax; ppv
0x18003bea5  lea     r9, IID_ISharedProtectionPoints; riid
0x18003beac  xor     edx, edx; pUnkOuter
0x18003beae  lea     r8d, [rdx+1]; dwClsContext
0x18003beb2  lea     rcx, CLSID_SPP; rclsid
0x18003beb9  call    cs:__imp_CoCreateInstance
0x18003bebf  mov     [rsp+140h+var_108], eax
0x18003bec3  test    eax, eax
0x18003bec5  mov     eax, 939h
0x18003beca  js      loc_18003BC43
0x18003bed0  mov     [rsp+140h+var_104], ax
0x18003bed5  lea     rcx, [rbp+40h+var_C0]; unsigned __int16 **
0x18003bed9  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x18003bede  lea     rcx, [rsp+140h+var_C8]; unsigned __int16 **
0x18003bee3  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18003bee8  mov     ebx, [rsp+140h+var_108]
0x18003beec  lea     rcx, [rsp+140h+var_D0]
0x18003bef1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003bef6  lea     rcx, [rsp+140h+var_108]; this
0x18003befb  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003bf00  mov     eax, ebx
0x18003bf02  add     rsp, 118h
0x18003bf09  pop     r15
0x18003bf0b  pop     r12
0x18003bf0d  pop     rdi
0x18003bf0e  pop     rsi
0x18003bf0f  pop     rbx
0x18003bf10  pop     rbp
0x18003bf11  retn
```

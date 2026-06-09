# CSdBackupImpl::ConfigureBackup(ushort const *,ulong,ulong,ushort const *,_SD_BACKUP_TYPE,ushort const *)

- ea: `0x18003d210`
- end: `0x18003d565`
- name: `?ConfigureBackup@CSdBackupImpl@@UEAAJPEBGKK0W4_SD_BACKUP_TYPE@@0@Z`
- size: `853`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003540`
- `0x180009d0c`
- `0x1800119c4`
- `0x18001bba8`
- `0x18003d210`
- `0x1800449a8`
- `0x18004d0f4`
- `0x180072e08`
- `0x180072f14`
- `0x180073ad8`
- `0x18008daf0`
- `0x18009e24c`
- `0x18009e904`
- `0x1800cf56a`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003d404`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003d404`
- `ole32!CoCreateInstance` at `0x18003d505`
- `ole32!CoCreateInstance` at `0x18003d505`
- `ole32!CoCreateGuid` at `0x18003d45b`
- `ole32!CoCreateGuid` at `0x18003d45b`

## string_xrefs

- `0x18003d23d`: `CSdBackupImpl::ConfigureBackup`

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

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StorageDevice,
    "CSdBackupImpl::ConfigureBackup",
    0x905u,
    1u);
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
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StorageDevice);
  return v12;
}

```

## disassembly

```asm
0x18003d210  push    rbp
0x18003d212  push    rbx
0x18003d213  push    rsi
0x18003d214  push    rdi
0x18003d215  push    r12
0x18003d217  push    r15
0x18003d219  lea     rbp, [rsp-18h]
0x18003d21e  sub     rsp, 118h
0x18003d225  mov     r15d, r9d
0x18003d228  mov     esi, r8d
0x18003d22b  mov     rdi, rdx
0x18003d22e  mov     rbx, rcx
0x18003d231  mov     r9d, 1; unsigned __int16
0x18003d237  mov     r8d, 905h; unsigned __int16
0x18003d23d  lea     rdx, aCsdbackupimplC_3; "CSdBackupImpl::ConfigureBackup"
0x18003d244  lea     rcx, [rsp+140h+var_108]; this
0x18003d249  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003d24e  xor     r12d, r12d
0x18003d251  mov     [rsp+140h+var_C8], r12
0x18003d256  mov     [rsp+140h+var_D0], r12
0x18003d25b  mov     [rsp+140h+var_110], r12d
0x18003d260  xor     edx, edx; Val
0x18003d262  mov     r8d, 90h; Size
0x18003d268  lea     rcx, [rbp+40h+var_C0]; void *
0x18003d26c  call    memset_0
0x18003d271  call    ?VerifyCallerSystem@@YAJXZ; VerifyCallerSystem(void)
0x18003d276  mov     [rsp+140h+var_108], eax
0x18003d27a  test    eax, eax
0x18003d27c  mov     eax, 90Bh
0x18003d281  jns     short loc_18003D28D
0x18003d283  mov     [rsp+140h+var_102], ax
0x18003d288  jmp     loc_18003D527
0x18003d28d  mov     [rsp+140h+var_104], ax
0x18003d292  mov     eax, 90Dh
0x18003d297  test    rdi, rdi
0x18003d29a  jnz     short loc_18003D2A6
0x18003d29c  mov     [rsp+140h+var_108], 80070057h
0x18003d2a4  jmp     short loc_18003D283
0x18003d2a6  mov     [rsp+140h+var_104], ax
0x18003d2ab  mov     eax, 90Eh
0x18003d2b0  test    esi, 0EFFFFF80h
0x18003d2b6  jnz     short loc_18003D29C
0x18003d2b8  mov     [rsp+140h+var_104], ax
0x18003d2bd  mov     ecx, [rbp+40h+arg_28]
0x18003d2c0  mov     eax, 90Fh
0x18003d2c5  test    ecx, ecx
0x18003d2c7  jz      short loc_18003D29C
0x18003d2c9  mov     [rsp+140h+var_104], ax
0x18003d2ce  mov     eax, 910h
0x18003d2d3  cmp     [rbp+40h+lpSrc], r12
0x18003d2da  jz      short loc_18003D29C
0x18003d2dc  mov     [rsp+140h+var_108], r12d
0x18003d2e1  mov     [rsp+140h+var_104], ax
0x18003d2e6  mov     [rbx+0B0h], esi
0x18003d2ec  mov     [rbx+0B4h], r15d
0x18003d2f3  mov     [rbx+0BCh], ecx
0x18003d2f9  lea     r8, [rbx+38h]; struct CBsString *
0x18003d2fd  mov     rdx, rdi; unsigned __int16 *
0x18003d300  mov     rcx, [rbx+160h]; struct IMSDCommonImpl *
0x18003d307  call    ?SetStorageDeviceName@@YAJPEAUIMSDCommonImpl@@PEBGPEAVCBsString@@@Z; SetStorageDeviceName(IMSDCommonImpl *,ushort const *,CBsString *)
0x18003d30c  mov     [rsp+140h+var_108], eax
0x18003d310  test    eax, eax
0x18003d312  mov     eax, 916h
0x18003d317  js      loc_18003D283
0x18003d31d  mov     [rsp+140h+var_104], ax
0x18003d322  mov     rcx, [rbx+160h]
0x18003d329  mov     rax, [rcx]
0x18003d32c  lea     rdx, [rsp+140h+var_D0]
0x18003d331  mov     rax, [rax+0A8h]
0x18003d338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d33d  mov     [rsp+140h+var_108], eax
0x18003d341  test    eax, eax
0x18003d343  mov     eax, 918h
0x18003d348  js      loc_18003D283
0x18003d34e  mov     [rsp+140h+var_104], ax
0x18003d353  mov     eax, 919h
0x18003d358  cmp     [rsp+140h+var_D0], r12
0x18003d35d  jnz     short loc_18003D36C
0x18003d35f  mov     [rsp+140h+var_108], 81000036h
0x18003d367  jmp     loc_18003D283
0x18003d36c  mov     [rsp+140h+var_108], r12d
0x18003d371  mov     [rsp+140h+var_104], ax
0x18003d376  lea     rdx, [rbp+40h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x18003d37a  mov     rcx, rdi; unsigned __int16 *
0x18003d37d  call    ?QueryStorageDevice@@YAJPEBGPEAU_SD_STORAGE_DEVICE_PROP@@@Z; QueryStorageDevice(ushort const *,_SD_STORAGE_DEVICE_PROP *)
0x18003d382  mov     [rsp+140h+var_108], eax
0x18003d386  test    eax, eax
0x18003d388  mov     eax, 91Eh
0x18003d38d  js      loc_18003D283
0x18003d393  mov     [rsp+140h+var_104], ax
0x18003d398  cmp     [rbp+40h+var_88], 7
0x18003d39c  jnz     short loc_18003D3C8
0x18003d39e  lea     r9, [rbp+40h+var_C0]; struct _SD_STORAGE_DEVICE_PROP *
0x18003d3a2  mov     r8d, esi; unsigned int
0x18003d3a5  mov     rdx, [rsp+140h+var_D0]; struct ISdGlobalCatalog *
0x18003d3aa  mov     rcx, rbx; this
0x18003d3ad  call    ?_VerifyStorageDeviceForNetShare@CSdBackupImpl@@AEAAJPEAUISdGlobalCatalog@@KPEBU_SD_STORAGE_DEVICE_PROP@@@Z; CSdBackupImpl::_VerifyStorageDeviceForNetShare(ISdGlobalCatalog *,ulong,_SD_STORAGE_DEVICE_PROP const *)
0x18003d3b2  mov     [rsp+140h+var_108], eax
0x18003d3b6  test    eax, eax
0x18003d3b8  mov     eax, 921h
0x18003d3bd  js      loc_18003D283
0x18003d3c3  mov     [rsp+140h+var_104], ax
0x18003d3c8  mov     rdx, [rbp+40h+arg_20]; unsigned __int16 *
0x18003d3cc  test    rdx, rdx
0x18003d3cf  jz      short loc_18003D3FD
0x18003d3d1  cmp     [rdx], r12w
0x18003d3d5  jz      short loc_18003D3FD
0x18003d3d7  mov     dword ptr [rbx+58h], 1
0x18003d3de  lea     rcx, [rbx+48h]; this
0x18003d3e2  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18003d3e7  mov     [rsp+140h+var_108], eax
0x18003d3eb  test    eax, eax
0x18003d3ed  mov     eax, 92Ah
0x18003d3f2  js      loc_18003D283
0x18003d3f8  mov     [rsp+140h+var_104], ax
0x18003d3fd  lea     rcx, [rbx+0A8h]; lpSystemTimeAsFileTime
0x18003d404  call    cs:__imp_GetSystemTimeAsFileTime
0x18003d40b  nop     dword ptr [rax+rax+00h]
0x18003d410  lea     rcx, [rbx+60h]; this
0x18003d414  mov     rdx, [rbp+40h+lpSrc]; lpSrc
0x18003d41b  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18003d420  mov     [rsp+140h+var_108], eax
0x18003d424  test    eax, eax
0x18003d426  mov     eax, 92Fh
0x18003d42b  js      loc_18003D283
0x18003d431  mov     [rsp+140h+var_104], ax
0x18003d436  mov     rcx, rbx; this
0x18003d439  call    ?_InitializeBackupLog@CSdBackupImpl@@AEAAJXZ; CSdBackupImpl::_InitializeBackupLog(void)
0x18003d43e  mov     [rsp+140h+var_108], eax
0x18003d442  test    eax, eax
0x18003d444  mov     eax, 930h
0x18003d449  js      loc_18003D283
0x18003d44f  mov     [rsp+140h+var_104], ax
0x18003d454  lea     rcx, [rbx+88h]; pguid
0x18003d45b  call    cs:__imp_CoCreateGuid
0x18003d462  nop     dword ptr [rax+rax+00h]
0x18003d467  mov     [rsp+140h+var_108], eax
0x18003d46b  test    eax, eax
0x18003d46d  mov     eax, 932h
0x18003d472  js      loc_18003D283
0x18003d478  mov     [rsp+140h+var_104], ax
0x18003d47d  mov     rcx, [rbx+160h]
0x18003d484  mov     rax, [rcx]
0x18003d487  lea     rdx, [rsp+140h+var_110]
0x18003d48c  mov     rax, [rax+0B8h]
0x18003d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d498  mov     [rsp+140h+var_108], eax
0x18003d49c  test    eax, eax
0x18003d49e  mov     eax, 934h
0x18003d4a3  js      loc_18003D283
0x18003d4a9  mov     [rsp+140h+var_104], ax
0x18003d4ae  mov     edx, [rsp+140h+var_110]
0x18003d4b2  or      edx, 1
0x18003d4b5  mov     [rsp+140h+var_110], edx
0x18003d4b9  mov     rcx, [rbx+160h]
0x18003d4c0  mov     rax, [rcx]
0x18003d4c3  mov     rax, [rax+0C0h]
0x18003d4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4cf  mov     [rsp+140h+var_108], eax
0x18003d4d3  test    eax, eax
0x18003d4d5  mov     eax, 936h
0x18003d4da  js      loc_18003D283
0x18003d4e0  mov     [rsp+140h+var_104], ax
0x18003d4e5  lea     rax, [rbx+2C0h]
0x18003d4ec  mov     [rsp+140h+ppv], rax; ppv
0x18003d4f1  lea     r9, IID_ISharedProtectionPoints; riid
0x18003d4f8  xor     edx, edx; pUnkOuter
0x18003d4fa  lea     r8d, [rdx+1]; dwClsContext
0x18003d4fe  lea     rcx, CLSID_SPP; rclsid
0x18003d505  call    cs:__imp_CoCreateInstance
0x18003d50c  nop     dword ptr [rax+rax+00h]
0x18003d511  mov     [rsp+140h+var_108], eax
0x18003d515  test    eax, eax
0x18003d517  mov     eax, 939h
0x18003d51c  js      loc_18003D283
0x18003d522  mov     [rsp+140h+var_104], ax
0x18003d527  lea     rcx, [rbp+40h+var_C0]; unsigned __int16 **
0x18003d52b  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x18003d530  lea     rcx, [rsp+140h+var_C8]; unsigned __int16 **
0x18003d535  call    ?SdFreeString@@YAXPEAPEAG@Z; SdFreeString(ushort * *)
0x18003d53a  mov     ebx, [rsp+140h+var_108]
0x18003d53e  lea     rcx, [rsp+140h+var_D0]
0x18003d543  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003d548  lea     rcx, [rsp+140h+var_108]; this
0x18003d54d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003d552  mov     eax, ebx
0x18003d554  add     rsp, 118h
0x18003d55b  pop     r15
0x18003d55d  pop     r12
0x18003d55f  pop     rdi
0x18003d560  pop     rsi
0x18003d561  pop     rbx
0x18003d562  pop     rbp
0x18003d563  retn
```

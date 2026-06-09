# StorageService::SetStorageCardPowerPolicy(_STORAGE_DEVICE_TYPE,ulong)

- ea: `0x180029ee4`
- end: `0x18002a042`
- name: `?SetStorageCardPowerPolicy@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x180027858`
- `0x18002a3f8`

## callees

- `0x180001cf0`
- `0x18000d030`
- `0x18000d450`
- `0x18001bd98`
- `0x180029ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029f87`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180029f7d`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180029f7d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029f59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180029f59`

## pseudocode

```c
signed int __fastcall StorageService::SetStorageCardPowerPolicy(__int64 a1, int a2, unsigned int a3)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  signed int result; // eax
  int v7; // r8d
  int v8; // r9d
  bool v9; // sf
  __int64 v10; // rax
  unsigned __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  signed int v15; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h] BYREF
  _DWORD v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = a3;
  v4 = a2;
  pvData = 30000;
  pcbData = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\OEM\\Storage", L"SdIdlePowerTimeout", 0x10u, 0, &pvData, &pcbData);
  if ( GetVolumeNameForVolumeMountPointW(
         (LPCWSTR)(*(_QWORD *)(a1 + 8 * v4 + 40) + 4LL + 1112 * v3),
         szVolumeName,
         0x104u) )
  {
    v10 = -1;
    do
      ++v10;
    while ( szVolumeName[v10] );
    v11 = 2 * v10 - 2;
    if ( v11 >= 0x208 )
      _report_rangecheckfailure();
    v12 = pvData;
    *(WCHAR *)((char *)szVolumeName + v11) = 0;
    result = SetStorageIdlePowerTimeout(szVolumeName, v12);
  }
  else
  {
    result = GetLastError();
    v9 = result < 0;
    if ( result <= 0 )
      goto LABEL_9;
    result = (unsigned __int16)result | 0x80070000;
  }
  v9 = result < 0;
LABEL_9:
  if ( v9 && (unsigned int)dword_1800BF000 > 5 )
  {
    v15 = result;
    v16 = v3;
    v17[0] = v4;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
             (unsigned int)&dword_1800BF000,
             (unsigned int)&dword_1800A74BC,
             v7,
             v8,
             (__int64)v17,
             (__int64)&v16,
             (__int64)&v15);
  }
  return result;
}

```

## disassembly

```asm
0x180029ee4  push    rbp
0x180029ee6  push    rbx
0x180029ee7  push    rsi
0x180029ee8  push    rdi
0x180029ee9  push    r14
0x180029eeb  lea     rbp, [rsp-180h]
0x180029ef3  sub     rsp, 280h
0x180029efa  mov     rax, cs:__security_cookie
0x180029f01  xor     rax, rsp
0x180029f04  mov     [rbp+1A0h+var_30], rax
0x180029f0b  lea     rax, [rsp+2A0h+var_25C]
0x180029f10  mov     esi, r8d
0x180029f13  mov     [rsp+2A0h+pcbData], rax; pcbData
0x180029f18  lea     r8, aSdidlepowertim; "SdIdlePowerTimeout"
0x180029f1f  xor     r14d, r14d
0x180029f22  movsxd  rdi, edx
0x180029f25  lea     rax, [rsp+2A0h+var_260]
0x180029f2a  mov     [rsp+2A0h+var_260], 7530h
0x180029f32  mov     rbx, rcx
0x180029f35  mov     [rsp+2A0h+pvData], rax; pvData
0x180029f3a  lea     rdx, aSoftwareOemSto; "Software\\OEM\\Storage"
0x180029f41  mov     [rsp+2A0h+pdwType], r14; pdwType
0x180029f46  lea     r9d, [r14+10h]; dwFlags
0x180029f4a  mov     [rsp+2A0h+var_25C], 4
0x180029f52  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180029f59  call    cs:__imp_RegGetValueW
0x180029f5f  mov     rax, [rbx+rdi*8+28h]
0x180029f64  lea     rdx, [rsp+2A0h+szVolumeName]; lpszVolumeName
0x180029f69  add     rax, 4
0x180029f6d  mov     r8d, 104h; cchBufferLength
0x180029f73  imul    rcx, rsi, 458h
0x180029f7a  add     rcx, rax; lpszVolumeMountPoint
0x180029f7d  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180029f83  test    eax, eax
0x180029f85  jnz     short loc_180029F9B
0x180029f87  call    cs:__imp_GetLastError
0x180029f8d  test    eax, eax
0x180029f8f  jle     short loc_180029FD5
0x180029f91  movzx   eax, ax
0x180029f94  or      eax, 80070000h
0x180029f99  jmp     short loc_180029FD3
0x180029f9b  lea     rcx, [rsp+2A0h+szVolumeName]
0x180029fa0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029fa4  inc     rax
0x180029fa7  cmp     [rcx+rax*2], r14w
0x180029fac  jnz     short loc_180029FA4
0x180029fae  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180029fb6  cmp     rcx, 208h
0x180029fbd  jnb     short loc_18002A03C
0x180029fbf  mov     edx, [rsp+2A0h+var_260]; unsigned int
0x180029fc3  mov     [rsp+rcx+2A0h+szVolumeName], r14w
0x180029fc9  lea     rcx, [rsp+2A0h+szVolumeName]; unsigned __int16 *
0x180029fce  call    ?SetStorageIdlePowerTimeout@@YAJPEBGK@Z; SetStorageIdlePowerTimeout(ushort const *,ulong)
0x180029fd3  test    eax, eax
0x180029fd5  jns     short loc_18002A01F
0x180029fd7  mov     ecx, cs:dword_1800BF000
0x180029fdd  cmp     ecx, 5
0x180029fe0  jbe     short loc_18002A01F
0x180029fe2  mov     [rsp+2A0h+var_258], eax
0x180029fe6  lea     rdx, dword_1800A74BC
0x180029fed  lea     rax, [rsp+2A0h+var_258]
0x180029ff2  mov     [rsp+2A0h+var_254], esi
0x180029ff6  mov     [rsp+2A0h+pcbData], rax
0x180029ffb  lea     rcx, dword_1800BF000
0x18002a002  lea     rax, [rsp+2A0h+var_254]
0x18002a007  mov     [rsp+2A0h+var_250], edi
0x18002a00b  mov     [rsp+2A0h+pvData], rax
0x18002a010  lea     rax, [rsp+2A0h+var_250]
0x18002a015  mov     [rsp+2A0h+pdwType], rax
0x18002a01a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002a01f  mov     rcx, [rbp+1A0h+var_30]
0x18002a026  xor     rcx, rsp; StackCookie
0x18002a029  call    __security_check_cookie
0x18002a02e  add     rsp, 280h
0x18002a035  pop     r14
0x18002a037  pop     rdi
0x18002a038  pop     rsi
0x18002a039  pop     rbx
0x18002a03a  pop     rbp
0x18002a03b  retn
0x18002a03c  call    __report_rangecheckfailure
```

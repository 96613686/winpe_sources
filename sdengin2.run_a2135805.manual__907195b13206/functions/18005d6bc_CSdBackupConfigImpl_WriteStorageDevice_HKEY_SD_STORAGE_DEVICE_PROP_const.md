# CSdBackupConfigImpl::_WriteStorageDevice(HKEY__ *,_SD_STORAGE_DEVICE_PROP const *)

- ea: `0x18005d6bc`
- end: `0x18005db53`
- name: `?_WriteStorageDevice@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `1175`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, const struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18005a5b0`
- `0x18005cb48`

## callees

- `0x18005d6bc`
- `0x180072e08`
- `0x180072f14`
- `0x18008c0c4`
- `0x1800987fc`
- `0x18009892c`
- `0x1800991c8`
- `0x1800993dc`
- `0x1800994b8`
- `0x18009f560`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d8eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d937`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d983`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d9cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005da1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d8eb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d937`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d983`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005d9cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005da1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005db1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d7c1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005d7c1`

## string_xrefs

- `0x18005d6ec`: `CSdBackupConfigImpl::_WriteStorageDevice`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_WriteStorageDevice(
        CSdBackupConfigImpl *this,
        HKEY a2,
        const struct _SD_STORAGE_DEVICE_PROP *a3)
{
  __int16 v5; // ax
  _WORD *v6; // rax
  LSTATUS v7; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // r9d
  signed int LastSystemRestoreId; // ebx
  BYTE *v12; // r8
  BYTE *v13; // r8
  BYTE *v14; // r8
  BYTE *v15; // r8
  BYTE *v16; // r8
  BYTE *v18[2]; // [rsp+58h] [rbp-29h] BYREF
  BYTE *lpData[2]; // [rsp+68h] [rbp-19h] BYREF
  _QWORD v20[2]; // [rsp+78h] [rbp-9h] BYREF
  int v21; // [rsp+88h] [rbp+7h] BYREF
  __int16 v22; // [rsp+8Ch] [rbp+Bh]
  __int16 v23; // [rsp+8Eh] [rbp+Dh]
  CSdBackupConfigImpl *dwDisposition; // [rsp+E8h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+F0h] [rbp+6Fh] BYREF

  dwDisposition = this;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v21,
    "CSdBackupConfigImpl::_WriteStorageDevice",
    0x29Du,
    1u);
  LODWORD(dwDisposition) = 0;
  hKey = 0;
  v20[0] = qword_1800EE510;
  v20[1] = 0;
  lpData[0] = (BYTE *)qword_1800EE510;
  lpData[1] = 0;
  v18[0] = (BYTE *)qword_1800EE510;
  v18[1] = 0;
  v5 = 677;
  if ( !a2 )
    goto LABEL_43;
  v22 = 677;
  v5 = 678;
  if ( !a3 )
    goto LABEL_43;
  v21 = 0;
  v22 = 678;
  if ( !*(_QWORD *)a3 || !**(_WORD **)a3 )
  {
    v5 = 679;
    goto LABEL_43;
  }
  v22 = 679;
  v6 = (_WORD *)*((_QWORD *)a3 + 1);
  if ( !v6 || !*v6 )
  {
    v5 = 680;
LABEL_43:
    LastSystemRestoreId = -2147024809;
    v21 = -2147024809;
    goto LABEL_44;
  }
  v22 = 680;
  v7 = RegCreateKeyExW(a2, L"TargetDevice", 0, 0, 0, 0x2001Fu, 0, &hKey, (LPDWORD)&dwDisposition);
  LastSystemRestoreId = v7;
  if ( v7 > 0 )
    LastSystemRestoreId = (unsigned __int16)v7 | 0x80070000;
  v21 = LastSystemRestoreId;
  v5 = 690;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 690;
  LastSystemRestoreId = SetRegKeyVirtualization(hKey, v8, v9, v10);
  v21 = LastSystemRestoreId;
  v5 = 692;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 692;
  LastSystemRestoreId = SxRegWriteDWORD(hKey, L"Type", *((_DWORD *)a3 + 14));
  v21 = LastSystemRestoreId;
  v5 = 694;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 694;
  LastSystemRestoreId = SxRegWriteULONGLONG(hKey, L"TotalSize", *((_QWORD *)a3 + 8));
  v21 = LastSystemRestoreId;
  v5 = 695;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 695;
  LastSystemRestoreId = SxRegWriteULONGLONG(hKey, L"Freespace", *((_QWORD *)a3 + 9));
  v21 = LastSystemRestoreId;
  v5 = 696;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 696;
  LastSystemRestoreId = SxRegWriteString(hKey, L"PresentableName", *(BYTE **)a3);
  v21 = LastSystemRestoreId;
  v5 = 698;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 698;
  LastSystemRestoreId = SxRegWriteString(hKey, L"UniqueName", *((BYTE **)a3 + 1));
  v21 = LastSystemRestoreId;
  v5 = 699;
  if ( LastSystemRestoreId < 0 )
    goto LABEL_44;
  v22 = 699;
  RegDeleteValueW(hKey, L"Label");
  v12 = (BYTE *)*((_QWORD *)a3 + 2);
  if ( v12 && *(_WORD *)v12 )
  {
    LastSystemRestoreId = SxRegWriteString(hKey, L"Label", v12);
    v21 = LastSystemRestoreId;
    v5 = 704;
    if ( LastSystemRestoreId < 0 )
      goto LABEL_44;
    v22 = 704;
  }
  RegDeleteValueW(hKey, L"DeviceVendor");
  v13 = (BYTE *)*((_QWORD *)a3 + 3);
  if ( v13 && *(_WORD *)v13 )
  {
    LastSystemRestoreId = SxRegWriteString(hKey, L"DeviceVendor", v13);
    v21 = LastSystemRestoreId;
    v5 = 710;
    if ( LastSystemRestoreId < 0 )
      goto LABEL_44;
    v22 = 710;
  }
  RegDeleteValueW(hKey, L"DeviceProduct");
  v14 = (BYTE *)*((_QWORD *)a3 + 4);
  if ( v14 && *(_WORD *)v14 )
  {
    LastSystemRestoreId = SxRegWriteString(hKey, L"DeviceProduct", v14);
    v21 = LastSystemRestoreId;
    v5 = 716;
    if ( LastSystemRestoreId < 0 )
      goto LABEL_44;
    v22 = 716;
  }
  RegDeleteValueW(hKey, L"DeviceVersion");
  v15 = (BYTE *)*((_QWORD *)a3 + 5);
  if ( v15 && *(_WORD *)v15 )
  {
    LastSystemRestoreId = SxRegWriteString(hKey, L"DeviceVersion", v15);
    v21 = LastSystemRestoreId;
    v5 = 722;
    if ( LastSystemRestoreId < 0 )
      goto LABEL_44;
    v22 = 722;
  }
  RegDeleteValueW(hKey, L"DeviceSerial");
  v16 = (BYTE *)*((_QWORD *)a3 + 6);
  if ( v16 && *(_WORD *)v16 )
  {
    LastSystemRestoreId = SxRegWriteString(hKey, L"DeviceSerial", v16);
    v21 = LastSystemRestoreId;
    v5 = 728;
    if ( LastSystemRestoreId < 0 )
      goto LABEL_44;
    v22 = 728;
  }
  LastSystemRestoreId = SxGetLastSystemRestoreId((struct CBsString *)lpData);
  v21 = LastSystemRestoreId;
  v5 = 735;
  if ( LastSystemRestoreId >= 0 )
  {
    v22 = 735;
    LastSystemRestoreId = SxRegWriteString(a2, L"LastSystemRestoreId", lpData[0]);
    v21 = LastSystemRestoreId;
    v5 = 736;
    if ( LastSystemRestoreId >= 0 )
    {
      v22 = 736;
      LastSystemRestoreId = SxGetLastAsrRestoreId((struct CBsString *)v18);
      v21 = LastSystemRestoreId;
      v5 = 743;
      if ( LastSystemRestoreId >= 0 )
      {
        v22 = 743;
        LastSystemRestoreId = SxRegWriteString(a2, L"LastAsrRestoreId", v18[0]);
        v21 = LastSystemRestoreId;
        v5 = 744;
        if ( LastSystemRestoreId >= 0 )
        {
          v22 = 744;
          goto LABEL_45;
        }
      }
    }
  }
LABEL_44:
  v23 = v5;
LABEL_45:
  CBsString::_Release((CBsString *)v18);
  CBsString::_Release((CBsString *)lpData);
  CBsString::_Release((CBsString *)v20);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v21);
  return (unsigned int)LastSystemRestoreId;
}

```

## disassembly

```asm
0x18005d6bc  mov     rax, rsp
0x18005d6bf  mov     [rax+18h], rbx
0x18005d6c3  mov     [rax+20h], rsi
0x18005d6c7  mov     [rax+8], rcx
0x18005d6cb  push    rbp
0x18005d6cc  push    rdi
0x18005d6cd  push    r14
0x18005d6cf  lea     rbp, [rax-5Fh]
0x18005d6d3  sub     rsp, 0C0h
0x18005d6da  mov     rdi, r8
0x18005d6dd  mov     rsi, rdx
0x18005d6e0  mov     r9d, 1; unsigned __int16
0x18005d6e6  mov     r8d, 29Dh; unsigned __int16
0x18005d6ec  lea     rdx, aCsdbackupconfi_30; "CSdBackupConfigImpl::_WriteStorageDevic"...
0x18005d6f3  lea     rcx, [rbp+57h+var_50]; this
0x18005d6f7  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005d6fc  xor     r14d, r14d
0x18005d6ff  mov     dword ptr [rbp+57h+dwDisposition], r14d
0x18005d703  mov     [rbp+57h+hKey], r14
0x18005d707  lea     rax, qword_1800EE510
0x18005d70e  mov     [rbp+57h+var_60], rax
0x18005d712  mov     [rbp+57h+var_58], r14
0x18005d716  mov     [rbp+57h+lpData], rax
0x18005d71a  mov     [rbp+57h+var_68], r14
0x18005d71e  mov     [rbp+57h+var_80], rax
0x18005d722  mov     [rbp+57h+var_78], r14
0x18005d726  mov     eax, 2A5h
0x18005d72b  test    rsi, rsi
0x18005d72e  jz      loc_18005DAEA
0x18005d734  mov     [rbp+57h+var_4C], ax
0x18005d738  mov     eax, 2A6h
0x18005d73d  test    rdi, rdi
0x18005d740  jz      loc_18005DAEA
0x18005d746  mov     [rbp+57h+var_50], r14d
0x18005d74a  mov     [rbp+57h+var_4C], ax
0x18005d74e  mov     rax, [rdi]
0x18005d751  test    rax, rax
0x18005d754  jz      loc_18005DAE5
0x18005d75a  cmp     [rax], r14w
0x18005d75e  jz      loc_18005DAE5
0x18005d764  mov     eax, 2A7h
0x18005d769  mov     [rbp+57h+var_4C], ax
0x18005d76d  mov     rax, [rdi+8]
0x18005d771  test    rax, rax
0x18005d774  jz      loc_18005DADE
0x18005d77a  cmp     [rax], r14w
0x18005d77e  jz      loc_18005DADE
0x18005d784  mov     eax, 2A8h
0x18005d789  mov     [rbp+57h+var_4C], ax
0x18005d78d  lea     rax, [rbp+57h+dwDisposition]
0x18005d791  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005d796  lea     rax, [rbp+57h+hKey]
0x18005d79a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18005d79f  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18005d7a4  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005d7ac  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x18005d7b1  xor     r9d, r9d; lpClass
0x18005d7b4  xor     r8d, r8d; Reserved
0x18005d7b7  lea     rdx, c_wszSafedocsDeviceTarget; "TargetDevice"
0x18005d7be  mov     rcx, rsi; hKey
0x18005d7c1  call    cs:__imp_RegCreateKeyExW
0x18005d7c8  nop     dword ptr [rax+rax+00h]
0x18005d7cd  mov     ebx, eax
0x18005d7cf  test    eax, eax
0x18005d7d1  jle     short loc_18005D7DC
0x18005d7d3  movzx   ebx, ax
0x18005d7d6  or      ebx, 80070000h
0x18005d7dc  mov     [rbp+57h+var_50], ebx
0x18005d7df  mov     eax, 2B2h
0x18005d7e4  test    ebx, ebx
0x18005d7e6  js      loc_18005DAF2
0x18005d7ec  mov     [rbp+57h+var_4C], ax
0x18005d7f0  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005d7f4  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005d7f9  mov     ebx, eax
0x18005d7fb  mov     [rbp+57h+var_50], eax
0x18005d7fe  test    eax, eax
0x18005d800  mov     eax, 2B4h
0x18005d805  js      loc_18005DAF2
0x18005d80b  mov     [rbp+57h+var_4C], ax
0x18005d80f  mov     r8d, [rdi+38h]; unsigned int
0x18005d813  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x18005d81a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d81e  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005d823  mov     ebx, eax
0x18005d825  mov     [rbp+57h+var_50], eax
0x18005d828  test    eax, eax
0x18005d82a  mov     eax, 2B6h
0x18005d82f  js      loc_18005DAF2
0x18005d835  mov     [rbp+57h+var_4C], ax
0x18005d839  mov     r8, [rdi+40h]; unsigned __int64
0x18005d83d  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x18005d844  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d848  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18005d84d  mov     ebx, eax
0x18005d84f  mov     [rbp+57h+var_50], eax
0x18005d852  test    eax, eax
0x18005d854  mov     eax, 2B7h
0x18005d859  js      loc_18005DAF2
0x18005d85f  mov     [rbp+57h+var_4C], ax
0x18005d863  mov     r8, [rdi+48h]; unsigned __int64
0x18005d867  lea     rdx, c_wszSafedocsDeviceFree; "Freespace"
0x18005d86e  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d872  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18005d877  mov     ebx, eax
0x18005d879  mov     [rbp+57h+var_50], eax
0x18005d87c  test    eax, eax
0x18005d87e  mov     eax, 2B8h
0x18005d883  js      loc_18005DAF2
0x18005d889  mov     [rbp+57h+var_4C], ax
0x18005d88d  mov     r8, [rdi]; lpData
0x18005d890  lea     rdx, c_wszSafedocsDevicePresentableName; "PresentableName"
0x18005d897  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d89b  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d8a0  mov     ebx, eax
0x18005d8a2  mov     [rbp+57h+var_50], eax
0x18005d8a5  test    eax, eax
0x18005d8a7  mov     eax, 2BAh
0x18005d8ac  js      loc_18005DAF2
0x18005d8b2  mov     [rbp+57h+var_4C], ax
0x18005d8b6  mov     r8, [rdi+8]; lpData
0x18005d8ba  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x18005d8c1  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d8c5  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d8ca  mov     ebx, eax
0x18005d8cc  mov     [rbp+57h+var_50], eax
0x18005d8cf  test    eax, eax
0x18005d8d1  mov     eax, 2BBh
0x18005d8d6  js      loc_18005DAF2
0x18005d8dc  mov     [rbp+57h+var_4C], ax
0x18005d8e0  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x18005d8e7  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d8eb  call    cs:__imp_RegDeleteValueW
0x18005d8f2  nop     dword ptr [rax+rax+00h]
0x18005d8f7  mov     r8, [rdi+10h]; lpData
0x18005d8fb  test    r8, r8
0x18005d8fe  jz      short loc_18005D92C
0x18005d900  cmp     [r8], r14w
0x18005d904  jz      short loc_18005D92C
0x18005d906  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x18005d90d  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d911  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d916  mov     ebx, eax
0x18005d918  mov     [rbp+57h+var_50], eax
0x18005d91b  test    eax, eax
0x18005d91d  mov     eax, 2C0h
0x18005d922  js      loc_18005DAF2
0x18005d928  mov     [rbp+57h+var_4C], ax
0x18005d92c  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x18005d933  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d937  call    cs:__imp_RegDeleteValueW
0x18005d93e  nop     dword ptr [rax+rax+00h]
0x18005d943  mov     r8, [rdi+18h]; lpData
0x18005d947  test    r8, r8
0x18005d94a  jz      short loc_18005D978
0x18005d94c  cmp     [r8], r14w
0x18005d950  jz      short loc_18005D978
0x18005d952  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x18005d959  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d95d  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d962  mov     ebx, eax
0x18005d964  mov     [rbp+57h+var_50], eax
0x18005d967  test    eax, eax
0x18005d969  mov     eax, 2C6h
0x18005d96e  js      loc_18005DAF2
0x18005d974  mov     [rbp+57h+var_4C], ax
0x18005d978  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x18005d97f  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d983  call    cs:__imp_RegDeleteValueW
0x18005d98a  nop     dword ptr [rax+rax+00h]
0x18005d98f  mov     r8, [rdi+20h]; lpData
0x18005d993  test    r8, r8
0x18005d996  jz      short loc_18005D9C4
0x18005d998  cmp     [r8], r14w
0x18005d99c  jz      short loc_18005D9C4
0x18005d99e  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x18005d9a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d9a9  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d9ae  mov     ebx, eax
0x18005d9b0  mov     [rbp+57h+var_50], eax
0x18005d9b3  test    eax, eax
0x18005d9b5  mov     eax, 2CCh
0x18005d9ba  js      loc_18005DAF2
0x18005d9c0  mov     [rbp+57h+var_4C], ax
0x18005d9c4  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x18005d9cb  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d9cf  call    cs:__imp_RegDeleteValueW
0x18005d9d6  nop     dword ptr [rax+rax+00h]
0x18005d9db  mov     r8, [rdi+28h]; lpData
0x18005d9df  test    r8, r8
0x18005d9e2  jz      short loc_18005DA10
0x18005d9e4  cmp     [r8], r14w
0x18005d9e8  jz      short loc_18005DA10
0x18005d9ea  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x18005d9f1  mov     rcx, [rbp+57h+hKey]; hKey
0x18005d9f5  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005d9fa  mov     ebx, eax
0x18005d9fc  mov     [rbp+57h+var_50], eax
0x18005d9ff  test    eax, eax
0x18005da01  mov     eax, 2D2h
0x18005da06  js      loc_18005DAF2
0x18005da0c  mov     [rbp+57h+var_4C], ax
0x18005da10  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x18005da17  mov     rcx, [rbp+57h+hKey]; hKey
0x18005da1b  call    cs:__imp_RegDeleteValueW
0x18005da22  nop     dword ptr [rax+rax+00h]
0x18005da27  mov     r8, [rdi+30h]; lpData
0x18005da2b  test    r8, r8
0x18005da2e  jz      short loc_18005DA5C
0x18005da30  cmp     [r8], r14w
0x18005da34  jz      short loc_18005DA5C
0x18005da36  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x18005da3d  mov     rcx, [rbp+57h+hKey]; hKey
0x18005da41  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005da46  mov     ebx, eax
0x18005da48  mov     [rbp+57h+var_50], eax
0x18005da4b  test    eax, eax
0x18005da4d  mov     eax, 2D8h
0x18005da52  js      loc_18005DAF2
0x18005da58  mov     [rbp+57h+var_4C], ax
0x18005da5c  lea     rcx, [rbp+57h+lpData]; this
0x18005da60  call    ?SxGetLastSystemRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastSystemRestoreId(CBsString *)
0x18005da65  mov     ebx, eax
0x18005da67  mov     [rbp+57h+var_50], eax
0x18005da6a  test    eax, eax
0x18005da6c  mov     eax, 2DFh
0x18005da71  js      short loc_18005DAF2
0x18005da73  mov     [rbp+57h+var_4C], ax
0x18005da77  mov     r8, [rbp+57h+lpData]; lpData
0x18005da7b  lea     rdx, c_wszSafedocsScheduleLastSystemRestoreId; "LastSystemRestoreId"
0x18005da82  mov     rcx, rsi; hKey
0x18005da85  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005da8a  mov     ebx, eax
0x18005da8c  mov     [rbp+57h+var_50], eax
0x18005da8f  test    eax, eax
0x18005da91  mov     eax, 2E0h
0x18005da96  js      short loc_18005DAF2
0x18005da98  mov     [rbp+57h+var_4C], ax
0x18005da9c  lea     rcx, [rbp+57h+var_80]; this
0x18005daa0  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x18005daa5  mov     ebx, eax
0x18005daa7  mov     [rbp+57h+var_50], eax
0x18005daaa  test    eax, eax
0x18005daac  mov     eax, 2E7h
0x18005dab1  js      short loc_18005DAF2
0x18005dab3  mov     [rbp+57h+var_4C], ax
0x18005dab7  mov     r8, [rbp+57h+var_80]; lpData
0x18005dabb  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005dac2  mov     rcx, rsi; hKey
0x18005dac5  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005daca  mov     ebx, eax
0x18005dacc  mov     [rbp+57h+var_50], eax
0x18005dacf  test    eax, eax
0x18005dad1  mov     eax, 2E8h
0x18005dad6  js      short loc_18005DAF2
0x18005dad8  mov     [rbp+57h+var_4C], ax
0x18005dadc  jmp     short loc_18005DAF6
0x18005dade  mov     eax, 2A8h
0x18005dae3  jmp     short loc_18005DAEA
0x18005dae5  mov     eax, 2A7h
0x18005daea  mov     ebx, 80070057h
0x18005daef  mov     [rbp+57h+var_50], ebx
0x18005daf2  mov     [rbp+57h+var_4A], ax
0x18005daf6  lea     rcx, [rbp+57h+var_80]; this
0x18005dafa  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005daff  lea     rcx, [rbp+57h+lpData]; this
0x18005db03  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005db08  lea     rcx, [rbp+57h+var_60]; this
0x18005db0c  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005db11  mov     rcx, [rbp+57h+hKey]; hKey
0x18005db15  lea     rdx, [rcx-1]
0x18005db19  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005db1d  ja      short loc_18005DB2F
0x18005db1f  call    cs:__imp_RegCloseKey
0x18005db26  nop     dword ptr [rax+rax+00h]
0x18005db2b  mov     [rbp+57h+hKey], r14
0x18005db2f  lea     rcx, [rbp+57h+var_50]; this
0x18005db33  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005db38  mov     eax, ebx
0x18005db3a  lea     r11, [rsp+0D0h+var_10]
0x18005db42  mov     rbx, [r11+30h]
0x18005db46  mov     rsi, [r11+38h]
0x18005db4a  mov     rsp, r11
0x18005db4d  pop     r14
0x18005db4f  pop     rdi
0x18005db50  pop     rbp
0x18005db51  retn
```

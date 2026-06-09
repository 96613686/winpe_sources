# CSdBackupConfigImpl::_WriteStorageDevice(HKEY__ *,_SD_STORAGE_DEVICE_PROP const *)

- ea: `0x18005af80`
- end: `0x18005b3ec`
- name: `?_WriteStorageDevice@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEBU_SD_STORAGE_DEVICE_PROP@@@Z`
- size: `1132`
- prototype: `int(CSdBackupConfigImpl *__hidden this, HKEY, const struct _SD_STORAGE_DEVICE_PROP *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180058070`
- `0x18005a49c`

## callees

- `0x18005af80`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180088640`
- `0x180094518`
- `0x180094638`
- `0x180094e88`
- `0x180095090`
- `0x180095164`
- `0x18009ae34`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b1a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b1ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b235`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b27b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b2c1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b1a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b1ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b235`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b27b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b2c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b3bf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b085`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005b085`

## string_xrefs

- `0x18005afb0`: `CSdBackupConfigImpl::_WriteStorageDevice`

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
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v21, "CSdBackupConfigImpl::_WriteStorageDevice", 669, 1);
  LODWORD(dwDisposition) = 0;
  hKey = 0;
  v20[0] = qword_1800E8530;
  v20[1] = 0;
  lpData[0] = (BYTE *)qword_1800E8530;
  lpData[1] = 0;
  v18[0] = (BYTE *)qword_1800E8530;
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
0x18005af80  mov     rax, rsp
0x18005af83  mov     [rax+18h], rbx
0x18005af87  mov     [rax+20h], rsi
0x18005af8b  mov     [rax+8], rcx
0x18005af8f  push    rbp
0x18005af90  push    rdi
0x18005af91  push    r14
0x18005af93  lea     rbp, [rax-5Fh]
0x18005af97  sub     rsp, 0C0h
0x18005af9e  mov     rdi, r8
0x18005afa1  mov     rsi, rdx
0x18005afa4  mov     r9d, 1; unsigned __int16
0x18005afaa  mov     r8d, 29Dh; unsigned __int16
0x18005afb0  lea     rdx, aCsdbackupconfi_30; "CSdBackupConfigImpl::_WriteStorageDevic"...
0x18005afb7  lea     rcx, [rbp+57h+var_50]; this
0x18005afbb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005afc0  xor     r14d, r14d
0x18005afc3  mov     dword ptr [rbp+57h+dwDisposition], r14d
0x18005afc7  mov     [rbp+57h+hKey], r14
0x18005afcb  lea     rax, qword_1800E8530
0x18005afd2  mov     [rbp+57h+var_60], rax
0x18005afd6  mov     [rbp+57h+var_58], r14
0x18005afda  mov     [rbp+57h+lpData], rax
0x18005afde  mov     [rbp+57h+var_68], r14
0x18005afe2  mov     [rbp+57h+var_80], rax
0x18005afe6  mov     [rbp+57h+var_78], r14
0x18005afea  mov     eax, 2A5h
0x18005afef  test    rsi, rsi
0x18005aff2  jz      loc_18005B38A
0x18005aff8  mov     [rbp+57h+var_4C], ax
0x18005affc  mov     eax, 2A6h
0x18005b001  test    rdi, rdi
0x18005b004  jz      loc_18005B38A
0x18005b00a  mov     [rbp+57h+var_50], r14d
0x18005b00e  mov     [rbp+57h+var_4C], ax
0x18005b012  mov     rax, [rdi]
0x18005b015  test    rax, rax
0x18005b018  jz      loc_18005B385
0x18005b01e  cmp     [rax], r14w
0x18005b022  jz      loc_18005B385
0x18005b028  mov     eax, 2A7h
0x18005b02d  mov     [rbp+57h+var_4C], ax
0x18005b031  mov     rax, [rdi+8]
0x18005b035  test    rax, rax
0x18005b038  jz      loc_18005B37E
0x18005b03e  cmp     [rax], r14w
0x18005b042  jz      loc_18005B37E
0x18005b048  mov     eax, 2A8h
0x18005b04d  mov     [rbp+57h+var_4C], ax
0x18005b051  lea     rax, [rbp+57h+dwDisposition]
0x18005b055  mov     [rsp+0D0h+lpdwDisposition], rax; lpdwDisposition
0x18005b05a  lea     rax, [rbp+57h+hKey]
0x18005b05e  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18005b063  mov     [rsp+0D0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18005b068  mov     [rsp+0D0h+samDesired], 2001Fh; samDesired
0x18005b070  mov     [rsp+0D0h+dwOptions], r14d; dwOptions
0x18005b075  xor     r9d, r9d; lpClass
0x18005b078  xor     r8d, r8d; Reserved
0x18005b07b  lea     rdx, c_wszSafedocsDeviceTarget; "TargetDevice"
0x18005b082  mov     rcx, rsi; hKey
0x18005b085  call    cs:__imp_RegCreateKeyExW
0x18005b08b  mov     ebx, eax
0x18005b08d  test    eax, eax
0x18005b08f  jle     short loc_18005B09A
0x18005b091  movzx   ebx, ax
0x18005b094  or      ebx, 80070000h
0x18005b09a  mov     [rbp+57h+var_50], ebx
0x18005b09d  mov     eax, 2B2h
0x18005b0a2  test    ebx, ebx
0x18005b0a4  js      loc_18005B392
0x18005b0aa  mov     [rbp+57h+var_4C], ax
0x18005b0ae  mov     rcx, [rbp+57h+hKey]; KeyHandle
0x18005b0b2  call    ?SetRegKeyVirtualization@@YAJPEAUHKEY__@@HHH@Z; SetRegKeyVirtualization(HKEY__ *,int,int,int)
0x18005b0b7  mov     ebx, eax
0x18005b0b9  mov     [rbp+57h+var_50], eax
0x18005b0bc  test    eax, eax
0x18005b0be  mov     eax, 2B4h
0x18005b0c3  js      loc_18005B392
0x18005b0c9  mov     [rbp+57h+var_4C], ax
0x18005b0cd  mov     r8d, [rdi+38h]; unsigned int
0x18005b0d1  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x18005b0d8  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b0dc  call    ?SxRegWriteDWORD@@YAJPEAUHKEY__@@PEBGK@Z; SxRegWriteDWORD(HKEY__ *,ushort const *,ulong)
0x18005b0e1  mov     ebx, eax
0x18005b0e3  mov     [rbp+57h+var_50], eax
0x18005b0e6  test    eax, eax
0x18005b0e8  mov     eax, 2B6h
0x18005b0ed  js      loc_18005B392
0x18005b0f3  mov     [rbp+57h+var_4C], ax
0x18005b0f7  mov     r8, [rdi+40h]; unsigned __int64
0x18005b0fb  lea     rdx, c_wszSafedocsDeviceSize; "TotalSize"
0x18005b102  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b106  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18005b10b  mov     ebx, eax
0x18005b10d  mov     [rbp+57h+var_50], eax
0x18005b110  test    eax, eax
0x18005b112  mov     eax, 2B7h
0x18005b117  js      loc_18005B392
0x18005b11d  mov     [rbp+57h+var_4C], ax
0x18005b121  mov     r8, [rdi+48h]; unsigned __int64
0x18005b125  lea     rdx, c_wszSafedocsDeviceFree; "Freespace"
0x18005b12c  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b130  call    ?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z; SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)
0x18005b135  mov     ebx, eax
0x18005b137  mov     [rbp+57h+var_50], eax
0x18005b13a  test    eax, eax
0x18005b13c  mov     eax, 2B8h
0x18005b141  js      loc_18005B392
0x18005b147  mov     [rbp+57h+var_4C], ax
0x18005b14b  mov     r8, [rdi]; lpData
0x18005b14e  lea     rdx, c_wszSafedocsDevicePresentableName; "PresentableName"
0x18005b155  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b159  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b15e  mov     ebx, eax
0x18005b160  mov     [rbp+57h+var_50], eax
0x18005b163  test    eax, eax
0x18005b165  mov     eax, 2BAh
0x18005b16a  js      loc_18005B392
0x18005b170  mov     [rbp+57h+var_4C], ax
0x18005b174  mov     r8, [rdi+8]; lpData
0x18005b178  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x18005b17f  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b183  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b188  mov     ebx, eax
0x18005b18a  mov     [rbp+57h+var_50], eax
0x18005b18d  test    eax, eax
0x18005b18f  mov     eax, 2BBh
0x18005b194  js      loc_18005B392
0x18005b19a  mov     [rbp+57h+var_4C], ax
0x18005b19e  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x18005b1a5  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b1a9  call    cs:__imp_RegDeleteValueW
0x18005b1af  mov     r8, [rdi+10h]; lpData
0x18005b1b3  test    r8, r8
0x18005b1b6  jz      short loc_18005B1E4
0x18005b1b8  cmp     [r8], r14w
0x18005b1bc  jz      short loc_18005B1E4
0x18005b1be  lea     rdx, c_wszSafedocsDeviceLabel; "Label"
0x18005b1c5  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b1c9  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b1ce  mov     ebx, eax
0x18005b1d0  mov     [rbp+57h+var_50], eax
0x18005b1d3  test    eax, eax
0x18005b1d5  mov     eax, 2C0h
0x18005b1da  js      loc_18005B392
0x18005b1e0  mov     [rbp+57h+var_4C], ax
0x18005b1e4  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x18005b1eb  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b1ef  call    cs:__imp_RegDeleteValueW
0x18005b1f5  mov     r8, [rdi+18h]; lpData
0x18005b1f9  test    r8, r8
0x18005b1fc  jz      short loc_18005B22A
0x18005b1fe  cmp     [r8], r14w
0x18005b202  jz      short loc_18005B22A
0x18005b204  lea     rdx, c_wszSafedocsDeviceVendor; "DeviceVendor"
0x18005b20b  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b20f  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b214  mov     ebx, eax
0x18005b216  mov     [rbp+57h+var_50], eax
0x18005b219  test    eax, eax
0x18005b21b  mov     eax, 2C6h
0x18005b220  js      loc_18005B392
0x18005b226  mov     [rbp+57h+var_4C], ax
0x18005b22a  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x18005b231  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b235  call    cs:__imp_RegDeleteValueW
0x18005b23b  mov     r8, [rdi+20h]; lpData
0x18005b23f  test    r8, r8
0x18005b242  jz      short loc_18005B270
0x18005b244  cmp     [r8], r14w
0x18005b248  jz      short loc_18005B270
0x18005b24a  lea     rdx, c_wszSafedocsDeviceProduct; "DeviceProduct"
0x18005b251  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b255  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b25a  mov     ebx, eax
0x18005b25c  mov     [rbp+57h+var_50], eax
0x18005b25f  test    eax, eax
0x18005b261  mov     eax, 2CCh
0x18005b266  js      loc_18005B392
0x18005b26c  mov     [rbp+57h+var_4C], ax
0x18005b270  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x18005b277  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b27b  call    cs:__imp_RegDeleteValueW
0x18005b281  mov     r8, [rdi+28h]; lpData
0x18005b285  test    r8, r8
0x18005b288  jz      short loc_18005B2B6
0x18005b28a  cmp     [r8], r14w
0x18005b28e  jz      short loc_18005B2B6
0x18005b290  lea     rdx, c_wszSafedocsDeviceVersion; "DeviceVersion"
0x18005b297  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b29b  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b2a0  mov     ebx, eax
0x18005b2a2  mov     [rbp+57h+var_50], eax
0x18005b2a5  test    eax, eax
0x18005b2a7  mov     eax, 2D2h
0x18005b2ac  js      loc_18005B392
0x18005b2b2  mov     [rbp+57h+var_4C], ax
0x18005b2b6  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x18005b2bd  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b2c1  call    cs:__imp_RegDeleteValueW
0x18005b2c7  mov     r8, [rdi+30h]; lpData
0x18005b2cb  test    r8, r8
0x18005b2ce  jz      short loc_18005B2FC
0x18005b2d0  cmp     [r8], r14w
0x18005b2d4  jz      short loc_18005B2FC
0x18005b2d6  lea     rdx, c_wszSafedocsDeviceSerial; "DeviceSerial"
0x18005b2dd  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b2e1  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b2e6  mov     ebx, eax
0x18005b2e8  mov     [rbp+57h+var_50], eax
0x18005b2eb  test    eax, eax
0x18005b2ed  mov     eax, 2D8h
0x18005b2f2  js      loc_18005B392
0x18005b2f8  mov     [rbp+57h+var_4C], ax
0x18005b2fc  lea     rcx, [rbp+57h+lpData]; this
0x18005b300  call    ?SxGetLastSystemRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastSystemRestoreId(CBsString *)
0x18005b305  mov     ebx, eax
0x18005b307  mov     [rbp+57h+var_50], eax
0x18005b30a  test    eax, eax
0x18005b30c  mov     eax, 2DFh
0x18005b311  js      short loc_18005B392
0x18005b313  mov     [rbp+57h+var_4C], ax
0x18005b317  mov     r8, [rbp+57h+lpData]; lpData
0x18005b31b  lea     rdx, c_wszSafedocsScheduleLastSystemRestoreId; "LastSystemRestoreId"
0x18005b322  mov     rcx, rsi; hKey
0x18005b325  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b32a  mov     ebx, eax
0x18005b32c  mov     [rbp+57h+var_50], eax
0x18005b32f  test    eax, eax
0x18005b331  mov     eax, 2E0h
0x18005b336  js      short loc_18005B392
0x18005b338  mov     [rbp+57h+var_4C], ax
0x18005b33c  lea     rcx, [rbp+57h+var_80]; this
0x18005b340  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x18005b345  mov     ebx, eax
0x18005b347  mov     [rbp+57h+var_50], eax
0x18005b34a  test    eax, eax
0x18005b34c  mov     eax, 2E7h
0x18005b351  js      short loc_18005B392
0x18005b353  mov     [rbp+57h+var_4C], ax
0x18005b357  mov     r8, [rbp+57h+var_80]; lpData
0x18005b35b  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005b362  mov     rcx, rsi; hKey
0x18005b365  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b36a  mov     ebx, eax
0x18005b36c  mov     [rbp+57h+var_50], eax
0x18005b36f  test    eax, eax
0x18005b371  mov     eax, 2E8h
0x18005b376  js      short loc_18005B392
0x18005b378  mov     [rbp+57h+var_4C], ax
0x18005b37c  jmp     short loc_18005B396
0x18005b37e  mov     eax, 2A8h
0x18005b383  jmp     short loc_18005B38A
0x18005b385  mov     eax, 2A7h
0x18005b38a  mov     ebx, 80070057h
0x18005b38f  mov     [rbp+57h+var_50], ebx
0x18005b392  mov     [rbp+57h+var_4A], ax
0x18005b396  lea     rcx, [rbp+57h+var_80]; this
0x18005b39a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005b39f  lea     rcx, [rbp+57h+lpData]; this
0x18005b3a3  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005b3a8  lea     rcx, [rbp+57h+var_60]; this
0x18005b3ac  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005b3b1  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b3b5  lea     rdx, [rcx-1]
0x18005b3b9  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005b3bd  ja      short loc_18005B3C9
0x18005b3bf  call    cs:__imp_RegCloseKey
0x18005b3c5  mov     [rbp+57h+hKey], r14
0x18005b3c9  lea     rcx, [rbp+57h+var_50]; this
0x18005b3cd  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005b3d2  mov     eax, ebx
0x18005b3d4  lea     r11, [rsp+0D0h+var_10]
0x18005b3dc  mov     rbx, [r11+30h]
0x18005b3e0  mov     rsi, [r11+38h]
0x18005b3e4  mov     rsp, r11
0x18005b3e7  pop     r14
0x18005b3e9  pop     rdi
0x18005b3ea  pop     rbp
0x18005b3eb  retn
```

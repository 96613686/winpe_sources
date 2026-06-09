# CSdBackupConfigImpl::_ReadConfig(_SD_BACKUP_CONFIG *)

- ea: `0x180058eb4`
- end: `0x1800593d2`
- name: `?_ReadConfig@CSdBackupConfigImpl@@AEAAJPEAU_SD_BACKUP_CONFIG@@@Z`
- size: `1310`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180057490`

## callees

- `0x180003430`
- `0x180003450`
- `0x180058eb4`
- `0x1800595a4`
- `0x180059924`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180087d38`
- `0x1800885bc`
- `0x18008dc68`
- `0x180094518`
- `0x180094758`
- `0x180095090`
- `0x180099bb0`
- `0x18009ae34`
- `0x1800c97da`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058f9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800593a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180058f9f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800593a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058f86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058fcb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058f86`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058fcb`
- `ole32!CoCreateInstance` at `0x18005926d`
- `ole32!CoCreateInstance` at `0x18005926d`

## string_xrefs

- `0x180058edf`: `CSdBackupConfigImpl::_ReadConfig`

## pseudocode

```c
__int64 __fastcall CSdBackupConfigImpl::_ReadConfig(CSdBackupConfigImpl *this, struct _SD_BACKUP_CONFIG *a2)
{
  __int64 v4; // rcx
  struct _SD_BACKUP_CONFIG *v5; // rax
  int v6; // esi
  int v7; // eax
  bool v8; // sf
  __int16 v9; // ax
  int v10; // ecx
  unsigned int v11; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HRESULT StringFromRegistry; // [rsp+38h] [rbp-C8h] BYREF
  __int16 v15; // [rsp+3Ch] [rbp-C4h]
  __int16 v16; // [rsp+3Eh] [rbp-C2h]
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  BYTE *lpData[3]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v19[2]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v20[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SD_BACKUP_ROOT *v21[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v22; // [rsp+C0h] [rbp-40h]
  __int128 v23; // [rsp+D0h] [rbp-30h]
  __int128 v24; // [rsp+E0h] [rbp-20h]
  __int128 v25; // [rsp+F0h] [rbp-10h]
  __int128 v26; // [rsp+100h] [rbp+0h]
  __int128 v27; // [rsp+110h] [rbp+10h]
  __int128 v28; // [rsp+120h] [rbp+20h]
  __int128 v29; // [rsp+130h] [rbp+30h]
  __int128 v30; // [rsp+140h] [rbp+40h] BYREF
  unsigned int v31[4]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v32; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 *v33[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v34; // [rsp+180h] [rbp+80h]
  unsigned int v35; // [rsp+1C8h] [rbp+C8h] BYREF
  unsigned int v36; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned int v37; // [rsp+1D8h] [rbp+D8h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StringFromRegistry,
    "CSdBackupConfigImpl::_ReadConfig",
    0x7Au,
    1u);
  hKey = 0;
  ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(&ppv);
  lpData[0] = (BYTE *)qword_1800E8530;
  lpData[1] = 0;
  v35 = 0;
  v37 = 0;
  v36 = 0;
  memset_0(v19, 0, 0xF8u);
  if ( !a2 )
  {
    StringFromRegistry = -2147024809;
    v9 = 137;
    goto LABEL_31;
  }
  v4 = 248;
  v5 = a2;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (struct _SD_BACKUP_CONFIG *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  v6 = 1;
  StringFromRegistry = 0;
  v15 = 137;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams",
         0,
         0x2001Fu,
         &hKey) )
  {
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams",
           0,
           0x20019u,
           &hKey);
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    StringFromRegistry = v7;
    v8 = v7 < 0;
    v9 = 141;
    if ( v8 )
      goto LABEL_31;
    v15 = 141;
    v6 = 0;
  }
  StringFromRegistry = SxRegReadDWORD(hKey, L"BackupType", &v35, 0);
  v9 = 148;
  if ( StringFromRegistry >= 0 )
  {
    v15 = 148;
    LODWORD(v33[1]) = v35;
    StringFromRegistry = ReadStringFromRegistry(hKey, L"Name", &v19[1], 0);
    v9 = 154;
    if ( StringFromRegistry >= 0 )
    {
      v15 = 154;
      StringFromRegistry = ReadStringFromRegistry(hKey, L"Description", v20, 0);
      v9 = 159;
      if ( StringFromRegistry >= 0 )
      {
        v15 = 159;
        StringFromRegistry = SxRegReadDWORD(hKey, L"BackupFlags", (unsigned int *)v19, 0);
        v9 = 164;
        if ( StringFromRegistry >= 0 )
        {
          v15 = 164;
          StringFromRegistry = SxRegReadDWORD(hKey, L"IncludeFutureUsers", &v36, 0);
          v9 = 169;
          if ( StringFromRegistry >= 0 )
          {
            v15 = 169;
            HIDWORD(v33[1]) = v36 == 1;
            StringFromRegistry = ReadStringFromRegistry(hKey, L"LastSystemRestoreId", (unsigned __int16 **)&v32 + 1, 0);
            v9 = 176;
            if ( StringFromRegistry >= 0 )
            {
              v15 = 176;
              v10 = ReadStringFromRegistry(hKey, L"LastAsrRestoreId", v33, 1);
              StringFromRegistry = v10;
              v9 = 181;
              if ( v10 >= 0 )
              {
                v15 = 181;
                if ( v10 == 1 )
                {
                  StringFromRegistry = SxGetLastAsrRestoreId((struct CBsString *)lpData);
                  v9 = 192;
                  if ( StringFromRegistry < 0 )
                    goto LABEL_31;
                  v15 = 192;
                  if ( v6 )
                  {
                    StringFromRegistry = SxRegWriteString(hKey, L"LastAsrRestoreId", lpData[0]);
                    v9 = 196;
                    if ( StringFromRegistry < 0 )
                      goto LABEL_31;
                    v15 = 196;
                  }
                  CBsString::Detach((CBsString *)lpData, v33);
                }
                StringFromRegistry = ReadDevicePropFromRegistry((struct _SD_STORAGE_DEVICE_PROP *)&v21[1]);
                v9 = 211;
                if ( StringFromRegistry >= 0 )
                {
                  v15 = 211;
                  StringFromRegistry = CSdBackupConfigImpl::_ReadRules(this, hKey, (unsigned int *)&v20[1], v21);
                  v9 = 216;
                  if ( StringFromRegistry >= 0 )
                  {
                    v15 = 216;
                    StringFromRegistry = CSdBackupConfigImpl::_ReadUserSettings(
                                           this,
                                           hKey,
                                           v31,
                                           (struct _SD_BACKUP_USER_DATA **)&v30 + 1,
                                           &v37);
                    v9 = 221;
                    if ( StringFromRegistry >= 0 )
                    {
                      v15 = 221;
                      LODWORD(v34) = v37 != 0;
                      StringFromRegistry = CoCreateInstance(&CLSID_CSdController, 0, 4u, &IID_ISdScheduledBackup, &ppv);
                      v9 = 227;
                      if ( StringFromRegistry >= 0 )
                      {
                        v15 = 227;
                        StringFromRegistry = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 104LL))(
                                               ppv,
                                               &v31[2]);
                        v9 = 228;
                        if ( StringFromRegistry >= 0 )
                        {
                          v15 = 228;
                          *(_OWORD *)a2 = *(_OWORD *)v19;
                          *((_OWORD *)a2 + 1) = *(_OWORD *)v20;
                          *((_OWORD *)a2 + 2) = *(_OWORD *)v21;
                          *((_OWORD *)a2 + 3) = v22;
                          *((_OWORD *)a2 + 4) = v23;
                          *((_OWORD *)a2 + 5) = v24;
                          *((_OWORD *)a2 + 6) = v25;
                          *((_OWORD *)a2 + 7) = v26;
                          *((_OWORD *)a2 + 8) = v27;
                          *((_OWORD *)a2 + 9) = v28;
                          *((_OWORD *)a2 + 10) = v29;
                          *((_OWORD *)a2 + 11) = v30;
                          *((_OWORD *)a2 + 12) = *(_OWORD *)v31;
                          *((_OWORD *)a2 + 13) = v32;
                          *((_OWORD *)a2 + 14) = *(_OWORD *)v33;
                          *((_QWORD *)a2 + 30) = v34;
                          memset_0(v19, 0, 0xF8u);
                          goto LABEL_32;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_31:
  v16 = v9;
LABEL_32:
  CleanupBackupConfigFields((struct _SD_BACKUP_CONFIG *)v19);
  v11 = StringFromRegistry;
  CBsString::_Release((CBsString *)lpData);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry);
  return v11;
}

```

## disassembly

```asm
0x180058eb4  mov     [rsp-8+arg_0], rbx
0x180058eb9  push    rbp
0x180058eba  push    rsi
0x180058ebb  push    rdi
0x180058ebc  push    r13
0x180058ebe  push    r14
0x180058ec0  lea     rbp, [rsp-90h]
0x180058ec8  sub     rsp, 190h
0x180058ecf  mov     rdi, rdx
0x180058ed2  mov     r14, rcx
0x180058ed5  mov     r9d, 1; unsigned __int16
0x180058edb  lea     r8d, [r9+79h]; unsigned __int16
0x180058edf  lea     rdx, aCsdbackupconfi_19; "CSdBackupConfigImpl::_ReadConfig"
0x180058ee6  lea     rcx, [rsp+1B0h+var_178]; this
0x180058eeb  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180058ef0  xor     ebx, ebx
0x180058ef2  mov     [rsp+1B0h+hKey], rbx
0x180058ef7  lea     rcx, [rsp+1B0h+ppv]; void *
0x180058efc  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x180058f01  lea     rcx, qword_1800E8530
0x180058f08  mov     [rsp+1B0h+lpData], rcx
0x180058f0d  mov     [rbp+0B0h+var_130], rbx
0x180058f11  mov     [rbp+0B0h+arg_8], ebx
0x180058f17  mov     [rbp+0B0h+arg_18], ebx
0x180058f1d  mov     [rbp+0B0h+arg_10], ebx
0x180058f23  mov     r13d, 0F8h
0x180058f29  mov     r8d, r13d; Size
0x180058f2c  xor     edx, edx; Val
0x180058f2e  lea     rcx, [rbp+0B0h+var_120]; void *
0x180058f32  call    memset_0
0x180058f37  test    rdi, rdi
0x180058f3a  jz      loc_18005935E
0x180058f40  mov     ecx, r13d
0x180058f43  mov     rax, rdi
0x180058f46  mov     [rax], bl
0x180058f48  inc     rax
0x180058f4b  sub     rcx, 1
0x180058f4f  jnz     short loc_180058F46
0x180058f51  lea     esi, [rcx+1]
0x180058f54  mov     [rsp+1B0h+var_178], ebx
0x180058f58  mov     eax, 89h
0x180058f5d  mov     [rsp+1B0h+var_174], ax
0x180058f62  lea     rax, [rsp+1B0h+hKey]
0x180058f67  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180058f6c  mov     r9d, 2001Fh; samDesired
0x180058f72  xor     r8d, r8d; ulOptions
0x180058f75  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180058f7c  mov     rbx, 0FFFFFFFF80000002h
0x180058f83  mov     rcx, rbx; hKey
0x180058f86  call    cs:__imp_RegOpenKeyExW
0x180058f8c  test    eax, eax
0x180058f8e  jz      short loc_180058FF5
0x180058f90  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180058f95  lea     rax, [rcx-1]
0x180058f99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180058f9d  ja      short loc_180058FAE
0x180058f9f  call    cs:__imp_RegCloseKey
0x180058fa5  mov     [rsp+1B0h+hKey], 0
0x180058fae  lea     rax, [rsp+1B0h+hKey]
0x180058fb3  mov     [rsp+1B0h+phkResult], rax; phkResult
0x180058fb8  mov     r9d, 20019h; samDesired
0x180058fbe  xor     r8d, r8d; ulOptions
0x180058fc1  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180058fc8  mov     rcx, rbx; hKey
0x180058fcb  call    cs:__imp_RegOpenKeyExW
0x180058fd1  test    eax, eax
0x180058fd3  jle     short loc_180058FDD
0x180058fd5  movzx   eax, ax
0x180058fd8  or      eax, 80070000h
0x180058fdd  mov     [rsp+1B0h+var_178], eax
0x180058fe1  test    eax, eax
0x180058fe3  mov     eax, 8Dh
0x180058fe8  js      loc_18005936B
0x180058fee  mov     [rsp+1B0h+var_174], ax
0x180058ff3  xor     esi, esi
0x180058ff5  xor     r9d, r9d; int
0x180058ff8  lea     r8, [rbp+0B0h+arg_8]; unsigned int *
0x180058fff  lea     rdx, c_wszSafedocsScheduleBackupType; "BackupType"
0x180059006  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005900b  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180059010  mov     [rsp+1B0h+var_178], eax
0x180059014  test    eax, eax
0x180059016  mov     eax, 94h
0x18005901b  js      loc_18005936B
0x180059021  mov     [rsp+1B0h+var_174], ax
0x180059026  mov     eax, [rbp+0B0h+arg_8]
0x18005902c  mov     dword ptr [rbp+0B0h+var_40+8], eax
0x18005902f  xor     r9d, r9d; int
0x180059032  lea     r8, [rbp+0B0h+var_120+8]; unsigned __int16 **
0x180059036  lea     rdx, c_wszSafedocsScheduleName; "Name"
0x18005903d  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180059042  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180059047  mov     [rsp+1B0h+var_178], eax
0x18005904b  test    eax, eax
0x18005904d  mov     eax, 9Ah
0x180059052  js      loc_18005936B
0x180059058  mov     [rsp+1B0h+var_174], ax
0x18005905d  xor     r9d, r9d; int
0x180059060  lea     r8, [rbp+0B0h+var_110]; unsigned __int16 **
0x180059064  lea     rdx, c_wszSafedocsScheduleDescription; "Description"
0x18005906b  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180059070  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180059075  mov     [rsp+1B0h+var_178], eax
0x180059079  test    eax, eax
0x18005907b  mov     eax, 9Fh
0x180059080  js      loc_18005936B
0x180059086  mov     [rsp+1B0h+var_174], ax
0x18005908b  xor     r9d, r9d; int
0x18005908e  lea     r8, [rbp+0B0h+var_120]; unsigned int *
0x180059092  lea     rdx, c_wszSafedocsScheduleBackupFlags; "BackupFlags"
0x180059099  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005909e  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800590a3  mov     [rsp+1B0h+var_178], eax
0x1800590a7  test    eax, eax
0x1800590a9  mov     eax, 0A4h
0x1800590ae  js      loc_18005936B
0x1800590b4  mov     [rsp+1B0h+var_174], ax
0x1800590b9  xor     r9d, r9d; int
0x1800590bc  lea     r8, [rbp+0B0h+arg_10]; unsigned int *
0x1800590c3  lea     rdx, c_wszSafedocsScheduleIncludeFutureUsers; "IncludeFutureUsers"
0x1800590ca  mov     rcx, [rsp+1B0h+hKey]; hKey
0x1800590cf  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800590d4  mov     [rsp+1B0h+var_178], eax
0x1800590d8  test    eax, eax
0x1800590da  mov     eax, 0A9h
0x1800590df  js      loc_18005936B
0x1800590e5  mov     [rsp+1B0h+var_174], ax
0x1800590ea  xor     eax, eax
0x1800590ec  cmp     [rbp+0B0h+arg_10], 1
0x1800590f3  setz    al
0x1800590f6  mov     dword ptr [rbp+0B0h+var_40+0Ch], eax
0x1800590f9  xor     r9d, r9d; int
0x1800590fc  lea     r8, [rbp+0B0h+var_48]; unsigned __int16 **
0x180059100  lea     rdx, c_wszSafedocsScheduleLastSystemRestoreId; "LastSystemRestoreId"
0x180059107  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005910c  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180059111  mov     [rsp+1B0h+var_178], eax
0x180059115  test    eax, eax
0x180059117  mov     eax, 0B0h
0x18005911c  js      loc_18005936B
0x180059122  mov     [rsp+1B0h+var_174], ax
0x180059127  mov     r9d, 1; int
0x18005912d  lea     r8, [rbp+0B0h+var_40]; unsigned __int16 **
0x180059131  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x180059138  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005913d  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180059142  mov     ecx, eax
0x180059144  mov     [rsp+1B0h+var_178], eax
0x180059148  test    eax, eax
0x18005914a  mov     eax, 0B5h
0x18005914f  js      loc_18005936B
0x180059155  mov     [rsp+1B0h+var_174], ax
0x18005915a  cmp     ecx, 1
0x18005915d  jnz     short loc_1800591BD
0x18005915f  lea     rcx, [rsp+1B0h+lpData]; this
0x180059164  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x180059169  mov     [rsp+1B0h+var_178], eax
0x18005916d  test    eax, eax
0x18005916f  mov     eax, 0C0h
0x180059174  js      loc_18005936B
0x18005917a  mov     [rsp+1B0h+var_174], ax
0x18005917f  test    esi, esi
0x180059181  jz      short loc_1800591AF
0x180059183  mov     r8, [rsp+1B0h+lpData]; lpData
0x180059188  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005918f  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180059194  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x180059199  mov     [rsp+1B0h+var_178], eax
0x18005919d  test    eax, eax
0x18005919f  mov     eax, 0C4h
0x1800591a4  js      loc_18005936B
0x1800591aa  mov     [rsp+1B0h+var_174], ax
0x1800591af  lea     rdx, [rbp+0B0h+var_40]; unsigned __int16 **
0x1800591b3  lea     rcx, [rsp+1B0h+lpData]; this
0x1800591b8  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x1800591bd  lea     rcx, [rbp+0B0h+var_100+8]; struct _SD_STORAGE_DEVICE_PROP *
0x1800591c1  call    ?ReadDevicePropFromRegistry@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z; ReadDevicePropFromRegistry(_SD_STORAGE_DEVICE_PROP *)
0x1800591c6  mov     [rsp+1B0h+var_178], eax
0x1800591ca  test    eax, eax
0x1800591cc  mov     eax, 0D3h
0x1800591d1  js      loc_18005936B
0x1800591d7  mov     [rsp+1B0h+var_174], ax
0x1800591dc  lea     r9, [rbp+0B0h+var_100]; struct _SD_BACKUP_ROOT **
0x1800591e0  lea     r8, [rbp+0B0h+var_110+8]; unsigned int *
0x1800591e4  mov     rdx, [rsp+1B0h+hKey]; hKey
0x1800591e9  mov     rcx, r14; this
0x1800591ec  call    ?_ReadRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_ReadRules(HKEY__ *,ulong *,_SD_BACKUP_ROOT * *)
0x1800591f1  mov     [rsp+1B0h+var_178], eax
0x1800591f5  test    eax, eax
0x1800591f7  mov     eax, 0D8h
0x1800591fc  js      loc_18005936B
0x180059202  mov     [rsp+1B0h+var_174], ax
0x180059207  lea     rax, [rbp+0B0h+arg_18]
0x18005920e  mov     [rsp+1B0h+phkResult], rax; unsigned int *
0x180059213  lea     r9, [rbp+0B0h+var_68]; struct _SD_BACKUP_USER_DATA **
0x180059217  lea     r8, [rbp+0B0h+var_60]; unsigned int *
0x18005921b  mov     rdx, [rsp+1B0h+hKey]; HKEY
0x180059220  mov     rcx, r14; this
0x180059223  call    ?_ReadUserSettings@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_USER_DATA@@1@Z; CSdBackupConfigImpl::_ReadUserSettings(HKEY__ *,ulong *,_SD_BACKUP_USER_DATA * *,ulong *)
0x180059228  mov     [rsp+1B0h+var_178], eax
0x18005922c  test    eax, eax
0x18005922e  mov     eax, 0DDh
0x180059233  js      loc_18005936B
0x180059239  mov     [rsp+1B0h+var_174], ax
0x18005923e  xor     eax, eax
0x180059240  cmp     [rbp+0B0h+arg_18], eax
0x180059246  setnz   al
0x180059249  mov     dword ptr [rbp+0B0h+var_30], eax
0x18005924f  lea     rax, [rsp+1B0h+ppv]
0x180059254  mov     [rsp+1B0h+phkResult], rax; ppv
0x180059259  lea     r9, IID_ISdScheduledBackup; riid
0x180059260  xor     edx, edx; pUnkOuter
0x180059262  lea     r8d, [rdx+4]; dwClsContext
0x180059266  lea     rcx, CLSID_CSdController; rclsid
0x18005926d  call    cs:__imp_CoCreateInstance
0x180059273  mov     [rsp+1B0h+var_178], eax
0x180059277  test    eax, eax
0x180059279  mov     eax, 0E3h
0x18005927e  js      loc_18005936B
0x180059284  mov     [rsp+1B0h+var_174], ax
0x180059289  mov     rcx, [rsp+1B0h+ppv]
0x18005928e  mov     rax, [rcx]
0x180059291  lea     rdx, [rbp+0B0h+var_60+8]
0x180059295  mov     rax, [rax+68h]
0x180059299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005929e  mov     [rsp+1B0h+var_178], eax
0x1800592a2  test    eax, eax
0x1800592a4  mov     eax, 0E4h
0x1800592a9  js      loc_18005936B
0x1800592af  mov     [rsp+1B0h+var_174], ax
0x1800592b4  movaps  xmm0, xmmword ptr [rbp+0B0h+var_120]
0x1800592b8  movups  xmmword ptr [rdi], xmm0
0x1800592bb  movaps  xmm1, xmmword ptr [rbp+0B0h+var_110]
0x1800592bf  movups  xmmword ptr [rdi+10h], xmm1
0x1800592c3  movaps  xmm0, xmmword ptr [rbp+0B0h+var_100]
0x1800592c7  movups  xmmword ptr [rdi+20h], xmm0
0x1800592cb  movaps  xmm1, [rbp+0B0h+var_F0]
0x1800592cf  movups  xmmword ptr [rdi+30h], xmm1
0x1800592d3  movaps  xmm0, [rbp+0B0h+var_E0]
0x1800592d7  movups  xmmword ptr [rdi+40h], xmm0
0x1800592db  movaps  xmm1, [rbp+0B0h+var_D0]
0x1800592df  movups  xmmword ptr [rdi+50h], xmm1
0x1800592e3  movaps  xmm0, [rbp+0B0h+var_C0]
0x1800592e7  movups  xmmword ptr [rdi+60h], xmm0
0x1800592eb  movaps  xmm1, [rbp+0B0h+var_B0]
0x1800592ef  movups  xmmword ptr [rdi+70h], xmm1
0x1800592f3  movaps  xmm0, [rbp+0B0h+var_A0]
0x1800592f7  movups  xmmword ptr [rdi+80h], xmm0
0x1800592fe  movaps  xmm1, [rbp+0B0h+var_90]
0x180059302  movups  xmmword ptr [rdi+90h], xmm1
0x180059309  movaps  xmm0, [rbp+0B0h+var_80]
0x18005930d  movups  xmmword ptr [rdi+0A0h], xmm0
0x180059314  movaps  xmm1, xmmword ptr [rbp+40h]
0x180059318  movups  xmmword ptr [rdi+0B0h], xmm1
0x18005931f  movaps  xmm0, xmmword ptr [rbp+0B0h+var_60]
0x180059323  movups  xmmword ptr [rdi+0C0h], xmm0
0x18005932a  movaps  xmm1, xmmword ptr [rbp+60h]
0x18005932e  movups  xmmword ptr [rdi+0D0h], xmm1
0x180059335  movaps  xmm0, xmmword ptr [rbp+0B0h+var_40]
0x180059339  movups  xmmword ptr [rdi+0E0h], xmm0
0x180059340  mov     rax, [rbp+0B0h+var_30]
0x180059347  mov     [rdi+0F0h], rax
0x18005934e  mov     r8, r13; Size
0x180059351  xor     edx, edx; Val
0x180059353  lea     rcx, [rbp+0B0h+var_120]; void *
0x180059357  call    memset_0
0x18005935c  jmp     short loc_180059370
0x18005935e  mov     [rsp+1B0h+var_178], 80070057h
0x180059366  mov     eax, 89h
0x18005936b  mov     [rsp+1B0h+var_172], ax
0x180059370  lea     rcx, [rbp+0B0h+var_120]; struct _SD_BACKUP_CONFIG *
0x180059374  call    ?CleanupBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z; CleanupBackupConfigFields(_SD_BACKUP_CONFIG *)
0x180059379  mov     ebx, [rsp+1B0h+var_178]
0x18005937d  lea     rcx, [rsp+1B0h+lpData]; this
0x180059382  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180059387  lea     rcx, [rsp+1B0h+ppv]
0x18005938c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180059391  mov     rcx, [rsp+1B0h+hKey]; hKey
0x180059396  lea     rdx, [rcx-1]
0x18005939a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005939e  ja      short loc_1800593AF
0x1800593a0  call    cs:__imp_RegCloseKey
0x1800593a6  mov     [rsp+1B0h+hKey], 0
0x1800593af  lea     rcx, [rsp+1B0h+var_178]; this
0x1800593b4  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800593b9  mov     eax, ebx
0x1800593bb  mov     rbx, [rsp+1B0h+arg_0]
0x1800593c3  add     rsp, 190h
0x1800593ca  pop     r14
0x1800593cc  pop     r13
0x1800593ce  pop     rdi
0x1800593cf  pop     rsi
0x1800593d0  pop     rbp
0x1800593d1  retn
```

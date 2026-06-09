# CSdBackupConfigImpl::_ReadConfig(_SD_BACKUP_CONFIG *)

- ea: `0x18005b46c`
- end: `0x18005b9a9`
- name: `?_ReadConfig@CSdBackupConfigImpl@@AEAAJPEAU_SD_BACKUP_CONFIG@@@Z`
- size: `1341`
- prototype: `__int64 __fastcall(CSdBackupConfigImpl *__hidden this, struct _SD_BACKUP_CONFIG *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180059960`

## callees

- `0x180003520`
- `0x180003540`
- `0x18005b46c`
- `0x18005bb8c`
- `0x18005bf50`
- `0x180072e08`
- `0x180072f14`
- `0x18008b774`
- `0x18008c040`
- `0x180091b6c`
- `0x1800987fc`
- `0x180098a5c`
- `0x1800993dc`
- `0x18009e208`
- `0x18009f560`
- `0x1800cf56a`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b55d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b970`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b55d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005b970`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b53e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b58f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b53e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b58f`
- `ole32!CoCreateInstance` at `0x18005b837`
- `ole32!CoCreateInstance` at `0x18005b837`

## string_xrefs

- `0x18005b497`: `CSdBackupConfigImpl::_ReadConfig`

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
  int StringFromRegistry; // [rsp+38h] [rbp-C8h] BYREF
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
  lpData[0] = (BYTE *)qword_1800EE510;
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
0x18005b46c  mov     [rsp-8+arg_0], rbx
0x18005b471  push    rbp
0x18005b472  push    rsi
0x18005b473  push    rdi
0x18005b474  push    r13
0x18005b476  push    r14
0x18005b478  lea     rbp, [rsp-90h]
0x18005b480  sub     rsp, 190h
0x18005b487  mov     rdi, rdx
0x18005b48a  mov     r14, rcx
0x18005b48d  mov     r9d, 1; unsigned __int16
0x18005b493  lea     r8d, [r9+79h]; unsigned __int16
0x18005b497  lea     rdx, aCsdbackupconfi_19; "CSdBackupConfigImpl::_ReadConfig"
0x18005b49e  lea     rcx, [rsp+1B0h+var_178]; this
0x18005b4a3  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005b4a8  xor     ebx, ebx
0x18005b4aa  mov     [rsp+1B0h+hKey], rbx
0x18005b4af  lea     rcx, [rsp+1B0h+ppv]; void *
0x18005b4b4  call    ??0?$CComPtr@UISdUniCursor@@@ATL@@QEAA@XZ; ATL::CComPtr<ISdUniCursor>::CComPtr<ISdUniCursor>(void)
0x18005b4b9  lea     rcx, qword_1800EE510
0x18005b4c0  mov     [rsp+1B0h+lpData], rcx
0x18005b4c5  mov     [rbp+0B0h+var_130], rbx
0x18005b4c9  mov     [rbp+0B0h+arg_8], ebx
0x18005b4cf  mov     [rbp+0B0h+arg_18], ebx
0x18005b4d5  mov     [rbp+0B0h+arg_10], ebx
0x18005b4db  mov     r13d, 0F8h
0x18005b4e1  mov     r8d, r13d; Size
0x18005b4e4  xor     edx, edx; Val
0x18005b4e6  lea     rcx, [rbp+0B0h+var_120]; void *
0x18005b4ea  call    memset_0
0x18005b4ef  test    rdi, rdi
0x18005b4f2  jz      loc_18005B92E
0x18005b4f8  mov     ecx, r13d
0x18005b4fb  mov     rax, rdi
0x18005b4fe  mov     [rax], bl
0x18005b500  inc     rax
0x18005b503  sub     rcx, 1
0x18005b507  jnz     short loc_18005B4FE
0x18005b509  lea     esi, [rcx+1]
0x18005b50c  mov     [rsp+1B0h+var_178], ebx
0x18005b510  mov     eax, 89h
0x18005b515  mov     [rsp+1B0h+var_174], ax
0x18005b51a  lea     rax, [rsp+1B0h+hKey]
0x18005b51f  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18005b524  mov     r9d, 2001Fh; samDesired
0x18005b52a  xor     r8d, r8d; ulOptions
0x18005b52d  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005b534  mov     rbx, 0FFFFFFFF80000002h
0x18005b53b  mov     rcx, rbx; hKey
0x18005b53e  call    cs:__imp_RegOpenKeyExW
0x18005b545  nop     dword ptr [rax+rax+00h]
0x18005b54a  test    eax, eax
0x18005b54c  jz      short loc_18005B5BF
0x18005b54e  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b553  lea     rax, [rcx-1]
0x18005b557  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005b55b  ja      short loc_18005B572
0x18005b55d  call    cs:__imp_RegCloseKey
0x18005b564  nop     dword ptr [rax+rax+00h]
0x18005b569  mov     [rsp+1B0h+hKey], 0
0x18005b572  lea     rax, [rsp+1B0h+hKey]
0x18005b577  mov     [rsp+1B0h+phkResult], rax; phkResult
0x18005b57c  mov     r9d, 20019h; samDesired
0x18005b582  xor     r8d, r8d; ulOptions
0x18005b585  lea     rdx, c_wszSafedocsSchedulingKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005b58c  mov     rcx, rbx; hKey
0x18005b58f  call    cs:__imp_RegOpenKeyExW
0x18005b596  nop     dword ptr [rax+rax+00h]
0x18005b59b  test    eax, eax
0x18005b59d  jle     short loc_18005B5A7
0x18005b59f  movzx   eax, ax
0x18005b5a2  or      eax, 80070000h
0x18005b5a7  mov     [rsp+1B0h+var_178], eax
0x18005b5ab  test    eax, eax
0x18005b5ad  mov     eax, 8Dh
0x18005b5b2  js      loc_18005B93B
0x18005b5b8  mov     [rsp+1B0h+var_174], ax
0x18005b5bd  xor     esi, esi
0x18005b5bf  xor     r9d, r9d; int
0x18005b5c2  lea     r8, [rbp+0B0h+arg_8]; unsigned int *
0x18005b5c9  lea     rdx, c_wszSafedocsScheduleBackupType; "BackupType"
0x18005b5d0  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b5d5  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005b5da  mov     [rsp+1B0h+var_178], eax
0x18005b5de  test    eax, eax
0x18005b5e0  mov     eax, 94h
0x18005b5e5  js      loc_18005B93B
0x18005b5eb  mov     [rsp+1B0h+var_174], ax
0x18005b5f0  mov     eax, [rbp+0B0h+arg_8]
0x18005b5f6  mov     dword ptr [rbp+0B0h+var_40+8], eax
0x18005b5f9  xor     r9d, r9d; int
0x18005b5fc  lea     r8, [rbp+0B0h+var_120+8]; unsigned __int16 **
0x18005b600  lea     rdx, c_wszSafedocsScheduleName; "Name"
0x18005b607  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b60c  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005b611  mov     [rsp+1B0h+var_178], eax
0x18005b615  test    eax, eax
0x18005b617  mov     eax, 9Ah
0x18005b61c  js      loc_18005B93B
0x18005b622  mov     [rsp+1B0h+var_174], ax
0x18005b627  xor     r9d, r9d; int
0x18005b62a  lea     r8, [rbp+0B0h+var_110]; unsigned __int16 **
0x18005b62e  lea     rdx, c_wszSafedocsScheduleDescription; "Description"
0x18005b635  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b63a  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005b63f  mov     [rsp+1B0h+var_178], eax
0x18005b643  test    eax, eax
0x18005b645  mov     eax, 9Fh
0x18005b64a  js      loc_18005B93B
0x18005b650  mov     [rsp+1B0h+var_174], ax
0x18005b655  xor     r9d, r9d; int
0x18005b658  lea     r8, [rbp+0B0h+var_120]; unsigned int *
0x18005b65c  lea     rdx, c_wszSafedocsScheduleBackupFlags; "BackupFlags"
0x18005b663  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b668  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005b66d  mov     [rsp+1B0h+var_178], eax
0x18005b671  test    eax, eax
0x18005b673  mov     eax, 0A4h
0x18005b678  js      loc_18005B93B
0x18005b67e  mov     [rsp+1B0h+var_174], ax
0x18005b683  xor     r9d, r9d; int
0x18005b686  lea     r8, [rbp+0B0h+arg_10]; unsigned int *
0x18005b68d  lea     rdx, c_wszSafedocsScheduleIncludeFutureUsers; "IncludeFutureUsers"
0x18005b694  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b699  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18005b69e  mov     [rsp+1B0h+var_178], eax
0x18005b6a2  test    eax, eax
0x18005b6a4  mov     eax, 0A9h
0x18005b6a9  js      loc_18005B93B
0x18005b6af  mov     [rsp+1B0h+var_174], ax
0x18005b6b4  xor     eax, eax
0x18005b6b6  cmp     [rbp+0B0h+arg_10], 1
0x18005b6bd  setz    al
0x18005b6c0  mov     dword ptr [rbp+0B0h+var_40+0Ch], eax
0x18005b6c3  xor     r9d, r9d; int
0x18005b6c6  lea     r8, [rbp+0B0h+var_48]; unsigned __int16 **
0x18005b6ca  lea     rdx, c_wszSafedocsScheduleLastSystemRestoreId; "LastSystemRestoreId"
0x18005b6d1  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b6d6  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005b6db  mov     [rsp+1B0h+var_178], eax
0x18005b6df  test    eax, eax
0x18005b6e1  mov     eax, 0B0h
0x18005b6e6  js      loc_18005B93B
0x18005b6ec  mov     [rsp+1B0h+var_174], ax
0x18005b6f1  mov     r9d, 1; int
0x18005b6f7  lea     r8, [rbp+0B0h+var_40]; unsigned __int16 **
0x18005b6fb  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005b702  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b707  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18005b70c  mov     ecx, eax
0x18005b70e  mov     [rsp+1B0h+var_178], eax
0x18005b712  test    eax, eax
0x18005b714  mov     eax, 0B5h
0x18005b719  js      loc_18005B93B
0x18005b71f  mov     [rsp+1B0h+var_174], ax
0x18005b724  cmp     ecx, 1
0x18005b727  jnz     short loc_18005B787
0x18005b729  lea     rcx, [rsp+1B0h+lpData]; this
0x18005b72e  call    ?SxGetLastAsrRestoreId@@YAJPEAVCBsString@@@Z; SxGetLastAsrRestoreId(CBsString *)
0x18005b733  mov     [rsp+1B0h+var_178], eax
0x18005b737  test    eax, eax
0x18005b739  mov     eax, 0C0h
0x18005b73e  js      loc_18005B93B
0x18005b744  mov     [rsp+1B0h+var_174], ax
0x18005b749  test    esi, esi
0x18005b74b  jz      short loc_18005B779
0x18005b74d  mov     r8, [rsp+1B0h+lpData]; lpData
0x18005b752  lea     rdx, c_wszSafedocsScheduleLastAsrRestoreId; "LastAsrRestoreId"
0x18005b759  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b75e  call    ?SxRegWriteString@@YAJPEAUHKEY__@@PEBG1@Z; SxRegWriteString(HKEY__ *,ushort const *,ushort const *)
0x18005b763  mov     [rsp+1B0h+var_178], eax
0x18005b767  test    eax, eax
0x18005b769  mov     eax, 0C4h
0x18005b76e  js      loc_18005B93B
0x18005b774  mov     [rsp+1B0h+var_174], ax
0x18005b779  lea     rdx, [rbp+0B0h+var_40]; unsigned __int16 **
0x18005b77d  lea     rcx, [rsp+1B0h+lpData]; this
0x18005b782  call    ?Detach@CBsString@@QEAAXPEAPEAG@Z; CBsString::Detach(ushort * *)
0x18005b787  lea     rcx, [rbp+0B0h+var_100+8]; struct _SD_STORAGE_DEVICE_PROP *
0x18005b78b  call    ?ReadDevicePropFromRegistry@@YAJPEAU_SD_STORAGE_DEVICE_PROP@@@Z; ReadDevicePropFromRegistry(_SD_STORAGE_DEVICE_PROP *)
0x18005b790  mov     [rsp+1B0h+var_178], eax
0x18005b794  test    eax, eax
0x18005b796  mov     eax, 0D3h
0x18005b79b  js      loc_18005B93B
0x18005b7a1  mov     [rsp+1B0h+var_174], ax
0x18005b7a6  lea     r9, [rbp+0B0h+var_100]; struct _SD_BACKUP_ROOT **
0x18005b7aa  lea     r8, [rbp+0B0h+var_110+8]; unsigned int *
0x18005b7ae  mov     rdx, [rsp+1B0h+hKey]; hKey
0x18005b7b3  mov     rcx, r14; this
0x18005b7b6  call    ?_ReadRules@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_ROOT@@@Z; CSdBackupConfigImpl::_ReadRules(HKEY__ *,ulong *,_SD_BACKUP_ROOT * *)
0x18005b7bb  mov     [rsp+1B0h+var_178], eax
0x18005b7bf  test    eax, eax
0x18005b7c1  mov     eax, 0D8h
0x18005b7c6  js      loc_18005B93B
0x18005b7cc  mov     [rsp+1B0h+var_174], ax
0x18005b7d1  lea     rax, [rbp+0B0h+arg_18]
0x18005b7d8  mov     [rsp+1B0h+phkResult], rax; unsigned int *
0x18005b7dd  lea     r9, [rbp+0B0h+var_68]; struct _SD_BACKUP_USER_DATA **
0x18005b7e1  lea     r8, [rbp+0B0h+var_60]; unsigned int *
0x18005b7e5  mov     rdx, [rsp+1B0h+hKey]; HKEY
0x18005b7ea  mov     rcx, r14; this
0x18005b7ed  call    ?_ReadUserSettings@CSdBackupConfigImpl@@AEAAJPEAUHKEY__@@PEAKPEAPEAU_SD_BACKUP_USER_DATA@@1@Z; CSdBackupConfigImpl::_ReadUserSettings(HKEY__ *,ulong *,_SD_BACKUP_USER_DATA * *,ulong *)
0x18005b7f2  mov     [rsp+1B0h+var_178], eax
0x18005b7f6  test    eax, eax
0x18005b7f8  mov     eax, 0DDh
0x18005b7fd  js      loc_18005B93B
0x18005b803  mov     [rsp+1B0h+var_174], ax
0x18005b808  xor     eax, eax
0x18005b80a  cmp     [rbp+0B0h+arg_18], eax
0x18005b810  setnz   al
0x18005b813  mov     dword ptr [rbp+0B0h+var_30], eax
0x18005b819  lea     rax, [rsp+1B0h+ppv]
0x18005b81e  mov     [rsp+1B0h+phkResult], rax; ppv
0x18005b823  lea     r9, IID_ISdScheduledBackup; riid
0x18005b82a  xor     edx, edx; pUnkOuter
0x18005b82c  lea     r8d, [rdx+4]; dwClsContext
0x18005b830  lea     rcx, CLSID_CSdController; rclsid
0x18005b837  call    cs:__imp_CoCreateInstance
0x18005b83e  nop     dword ptr [rax+rax+00h]
0x18005b843  mov     [rsp+1B0h+var_178], eax
0x18005b847  test    eax, eax
0x18005b849  mov     eax, 0E3h
0x18005b84e  js      loc_18005B93B
0x18005b854  mov     [rsp+1B0h+var_174], ax
0x18005b859  mov     rcx, [rsp+1B0h+ppv]
0x18005b85e  mov     rax, [rcx]
0x18005b861  lea     rdx, [rbp+0B0h+var_60+8]
0x18005b865  mov     rax, [rax+68h]
0x18005b869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b86e  mov     [rsp+1B0h+var_178], eax
0x18005b872  test    eax, eax
0x18005b874  mov     eax, 0E4h
0x18005b879  js      loc_18005B93B
0x18005b87f  mov     [rsp+1B0h+var_174], ax
0x18005b884  movaps  xmm0, xmmword ptr [rbp+0B0h+var_120]
0x18005b888  movups  xmmword ptr [rdi], xmm0
0x18005b88b  movaps  xmm1, xmmword ptr [rbp+0B0h+var_110]
0x18005b88f  movups  xmmword ptr [rdi+10h], xmm1
0x18005b893  movaps  xmm0, xmmword ptr [rbp+0B0h+var_100]
0x18005b897  movups  xmmword ptr [rdi+20h], xmm0
0x18005b89b  movaps  xmm1, [rbp+0B0h+var_F0]
0x18005b89f  movups  xmmword ptr [rdi+30h], xmm1
0x18005b8a3  movaps  xmm0, [rbp+0B0h+var_E0]
0x18005b8a7  movups  xmmword ptr [rdi+40h], xmm0
0x18005b8ab  movaps  xmm1, [rbp+0B0h+var_D0]
0x18005b8af  movups  xmmword ptr [rdi+50h], xmm1
0x18005b8b3  movaps  xmm0, [rbp+0B0h+var_C0]
0x18005b8b7  movups  xmmword ptr [rdi+60h], xmm0
0x18005b8bb  movaps  xmm1, [rbp+0B0h+var_B0]
0x18005b8bf  movups  xmmword ptr [rdi+70h], xmm1
0x18005b8c3  movaps  xmm0, [rbp+0B0h+var_A0]
0x18005b8c7  movups  xmmword ptr [rdi+80h], xmm0
0x18005b8ce  movaps  xmm1, [rbp+0B0h+var_90]
0x18005b8d2  movups  xmmword ptr [rdi+90h], xmm1
0x18005b8d9  movaps  xmm0, [rbp+0B0h+var_80]
0x18005b8dd  movups  xmmword ptr [rdi+0A0h], xmm0
0x18005b8e4  movaps  xmm1, xmmword ptr [rbp+40h]
0x18005b8e8  movups  xmmword ptr [rdi+0B0h], xmm1
0x18005b8ef  movaps  xmm0, xmmword ptr [rbp+0B0h+var_60]
0x18005b8f3  movups  xmmword ptr [rdi+0C0h], xmm0
0x18005b8fa  movaps  xmm1, xmmword ptr [rbp+60h]
0x18005b8fe  movups  xmmword ptr [rdi+0D0h], xmm1
0x18005b905  movaps  xmm0, xmmword ptr [rbp+0B0h+var_40]
0x18005b909  movups  xmmword ptr [rdi+0E0h], xmm0
0x18005b910  mov     rax, [rbp+0B0h+var_30]
0x18005b917  mov     [rdi+0F0h], rax
0x18005b91e  mov     r8, r13; Size
0x18005b921  xor     edx, edx; Val
0x18005b923  lea     rcx, [rbp+0B0h+var_120]; void *
0x18005b927  call    memset_0
0x18005b92c  jmp     short loc_18005B940
0x18005b92e  mov     [rsp+1B0h+var_178], 80070057h
0x18005b936  mov     eax, 89h
0x18005b93b  mov     [rsp+1B0h+var_172], ax
0x18005b940  lea     rcx, [rbp+0B0h+var_120]; struct _SD_BACKUP_CONFIG *
0x18005b944  call    ?CleanupBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z; CleanupBackupConfigFields(_SD_BACKUP_CONFIG *)
0x18005b949  mov     ebx, [rsp+1B0h+var_178]
0x18005b94d  lea     rcx, [rsp+1B0h+lpData]; this
0x18005b952  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18005b957  lea     rcx, [rsp+1B0h+ppv]
0x18005b95c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005b961  mov     rcx, [rsp+1B0h+hKey]; hKey
0x18005b966  lea     rdx, [rcx-1]
0x18005b96a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005b96e  ja      short loc_18005B985
0x18005b970  call    cs:__imp_RegCloseKey
0x18005b977  nop     dword ptr [rax+rax+00h]
0x18005b97c  mov     [rsp+1B0h+hKey], 0
0x18005b985  lea     rcx, [rsp+1B0h+var_178]; this
0x18005b98a  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18005b98f  mov     eax, ebx
0x18005b991  mov     rbx, [rsp+1B0h+arg_0]
0x18005b999  add     rsp, 190h
0x18005b9a0  pop     r14
0x18005b9a2  pop     r13
0x18005b9a4  pop     rdi
0x18005b9a5  pop     rsi
0x18005b9a6  pop     rbp
0x18005b9a7  retn
```

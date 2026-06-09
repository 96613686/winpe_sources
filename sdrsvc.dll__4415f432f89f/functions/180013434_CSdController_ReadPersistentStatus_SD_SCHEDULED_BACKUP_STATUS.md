# CSdController::_ReadPersistentStatus(_SD_SCHEDULED_BACKUP_STATUS *)

- ea: `0x180013434`
- end: `0x1800138b4`
- name: `?_ReadPersistentStatus@CSdController@@AEAAJPEAU_SD_SCHEDULED_BACKUP_STATUS@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(CSdController *__hidden this, struct _SD_SCHEDULED_BACKUP_STATUS *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fae0`

## callees

- `0x180013434`
- `0x18001586c`
- `0x180015974`
- `0x18001b4c0`
- `0x18001e67c`
- `0x18001e9d8`
- `0x18002170a`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001387c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001387c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800134f1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800134f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001383c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013846`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001385a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001383c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013846`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001385a`

## string_xrefs

- `0x180013466`: `CSdController::_ReadPersistentStatus`
- `0x180013822`: `CleanupScheduledBackupStatusFields`

## pseudocode

```c
__int64 __fastcall CSdController::_ReadPersistentStatus(CSdController *this, struct _SD_SCHEDULED_BACKUP_STATUS *a2)
{
  __int64 v3; // rcx
  struct _SD_SCHEDULED_BACKUP_STATUS *v4; // rax
  int v5; // eax
  int v6; // r9d
  bool v7; // sf
  __int16 v8; // ax
  int v9; // r9d
  int v10; // r9d
  int ULONGLONG; // ecx
  int v12; // r9d
  unsigned __int64 v13; // rax
  int v14; // ecx
  unsigned __int64 v15; // rax
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  unsigned int v18; // eax
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  unsigned int v22; // ebx
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int StringFromRegistry; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v27; // [rsp+44h] [rbp-BCh]
  __int16 v28; // [rsp+46h] [rbp-BAh]
  unsigned __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v30[64]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v31; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v32; // [rsp+D0h] [rbp-30h]
  LPVOID pv[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v34[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v35; // [rsp+100h] [rbp+0h]
  unsigned __int64 v36[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v37; // [rsp+120h] [rbp+20h]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&StringFromRegistry,
    "CSdController::_ReadPersistentStatus",
    1158,
    1);
  hKey = 0;
  v29 = 0;
  v24 = 0;
  memset_0(&v31, 0, 0x68u);
  if ( a2 )
  {
    v3 = 104;
    v4 = a2;
    do
    {
      *(_BYTE *)v4 = 0;
      v4 = (struct _SD_SCHEDULED_BACKUP_STATUS *)((char *)v4 + 1);
      --v3;
    }
    while ( v3 );
    StringFromRegistry = 0;
    v27 = 1169;
    *((_QWORD *)a2 + 10) = -1;
    *((_QWORD *)a2 + 11) = -1;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\Status",
           0,
           0x20019u,
           &hKey);
    if ( v5 == 2 )
    {
      *((_DWORD *)a2 + 4) = 1;
      v27 = 1179;
      StringFromRegistry = 1;
      goto LABEL_30;
    }
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    StringFromRegistry = v5;
    v7 = v5 < 0;
    v8 = 1181;
    if ( !v7 )
    {
      v27 = 1181;
      StringFromRegistry = SxRegReadULONGLONG(hKey, L"LastSuccess", &v29, v6);
      v8 = 1183;
      if ( StringFromRegistry >= 0 )
      {
        v27 = 1183;
        *((_QWORD *)&v35 + 1) = v29;
        StringFromRegistry = SxRegReadULONGLONG(hKey, L"LastResultTime", &v29, v9);
        v8 = 1186;
        if ( StringFromRegistry >= 0 )
        {
          v27 = 1186;
          *(_QWORD *)&v35 = v29;
          StringFromRegistry = SxRegReadDWORD(hKey, L"LastResultCode", &v24, 1);
          v8 = 1189;
          if ( StringFromRegistry >= 0 )
          {
            v27 = 1189;
            v8 = 1192;
            if ( v24 < 0xD )
            {
              LODWORD(v32) = v24;
              StringFromRegistry = 0;
              v27 = 1192;
              StringFromRegistry = SxRegReadDWORD(hKey, L"LastResultHr", &v24, 1);
              v8 = 1195;
              if ( StringFromRegistry >= 0 )
              {
                v27 = 1195;
                DWORD1(v32) = v24;
                StringFromRegistry = SxRegReadDWORD(hKey, L"LastResultDetailedHr", &v24, 1);
                v8 = 1198;
                if ( StringFromRegistry >= 0 )
                {
                  v27 = 1198;
                  DWORD2(v32) = v24;
                  StringFromRegistry = ReadStringFromRegistry(hKey, L"LastResultString", (unsigned __int16 **)pv, 1);
                  v8 = 1201;
                  if ( StringFromRegistry >= 0 )
                  {
                    v27 = 1201;
                    StringFromRegistry = ReadStringFromRegistry(
                                           hKey,
                                           L"LastResultTarget",
                                           (unsigned __int16 **)&pv[1],
                                           1);
                    v8 = 1202;
                    if ( StringFromRegistry >= 0 )
                    {
                      v27 = 1202;
                      StringFromRegistry = ReadStringFromRegistry(hKey, L"LastResultTargetPresentableName", v34, 1);
                      v8 = 1203;
                      if ( StringFromRegistry >= 0 )
                      {
                        v27 = 1203;
                        StringFromRegistry = ReadStringFromRegistry(hKey, L"LastResultTargetLabel", &v34[1], 1);
                        v8 = 1204;
                        if ( StringFromRegistry >= 0 )
                        {
                          v27 = 1204;
                          ULONGLONG = SxRegReadULONGLONG(hKey, L"BackupSpaceUsed", v36, v10);
                          StringFromRegistry = ULONGLONG;
                          v8 = 1208;
                          if ( ULONGLONG >= 0 )
                          {
                            v27 = 1208;
                            v13 = v36[0];
                            if ( ULONGLONG == 1 )
                              v13 = -1;
                            v36[0] = v13;
                            v14 = SxRegReadULONGLONG(hKey, L"LocalBackupSpaceUsed", &v36[1], v12);
                            StringFromRegistry = v14;
                            v8 = 1214;
                            if ( v14 >= 0 )
                            {
                              v27 = 1214;
                              v15 = v36[1];
                              if ( v14 == 1 )
                                v15 = -1;
                              v36[1] = v15;
                              StringFromRegistry = SxRegReadDWORD(hKey, L"ActionCenterState", &v24, 1);
                              v8 = 1220;
                              if ( StringFromRegistry >= 0 )
                              {
                                v16 = v32;
                                *(_OWORD *)a2 = v31;
                                v27 = 1220;
                                v17 = *(_OWORD *)pv;
                                v18 = v24;
                                *((_OWORD *)a2 + 1) = v16;
                                LODWORD(v37) = v18;
                                v19 = *(_OWORD *)v34;
                                *((_OWORD *)a2 + 2) = v17;
                                v20 = v35;
                                *((_OWORD *)a2 + 3) = v19;
                                v21 = *(_OWORD *)v36;
                                *((_OWORD *)a2 + 4) = v20;
                                *(_QWORD *)&v20 = v37;
                                *((_OWORD *)a2 + 5) = v21;
                                *((_QWORD *)a2 + 12) = v20;
                                memset_0(&v31, 0, 0x68u);
                                goto LABEL_30;
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
            else
            {
              StringFromRegistry = -2130706378;
            }
          }
        }
      }
    }
  }
  else
  {
    StringFromRegistry = -2147024809;
    v8 = 1169;
  }
  v28 = v8;
LABEL_30:
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v30, "CleanupScheduledBackupStatusFields", 55, 1);
  CoTaskMemFree(pv[0]);
  CoTaskMemFree(pv[1]);
  CoTaskMemFree(v34[0]);
  CoTaskMemFree(v34[1]);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v30);
  v22 = StringFromRegistry;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&StringFromRegistry);
  return v22;
}

```

## disassembly

```asm
0x180013434  push    rbp
0x180013436  push    rbx
0x180013437  push    rdi
0x180013438  push    r12
0x18001343a  push    r14
0x18001343c  push    r15
0x18001343e  lea     rbp, [rsp-48h]
0x180013443  sub     rsp, 148h
0x18001344a  mov     rax, cs:__security_cookie
0x180013451  xor     rax, rsp
0x180013454  mov     [rbp+70h+var_40], rax
0x180013458  mov     rdi, rdx
0x18001345b  lea     rcx, [rsp+170h+var_130]; this
0x180013460  mov     r14d, 1
0x180013466  lea     rdx, aCsdcontrollerR_1; "CSdController::_ReadPersistentStatus"
0x18001346d  mov     r9d, r14d; unsigned __int16
0x180013470  mov     r8d, 486h; unsigned __int16
0x180013476  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001347b  xor     ebx, ebx
0x18001347d  lea     r12d, [r14+67h]
0x180013481  mov     r8d, r12d; Size
0x180013484  mov     [rsp+170h+hKey], rbx
0x180013489  xor     edx, edx; Val
0x18001348b  mov     [rsp+170h+var_F8], rbx
0x180013490  lea     rcx, [rbp+70h+var_B0]; void *
0x180013494  mov     [rsp+170h+var_140], ebx
0x180013498  call    memset_0
0x18001349d  test    rdi, rdi
0x1800134a0  jz      loc_18001380D
0x1800134a6  mov     ecx, r12d
0x1800134a9  mov     rax, rdi
0x1800134ac  mov     [rax], bl
0x1800134ae  add     rax, r14
0x1800134b1  sub     rcx, r14
0x1800134b4  jnz     short loc_1800134AC
0x1800134b6  mov     eax, 491h
0x1800134bb  mov     [rsp+170h+var_130], ebx
0x1800134bf  mov     [rsp+170h+var_12C], ax
0x1800134c4  lea     rdx, c_wszSafedocsStatusKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800134cb  lea     rax, [rsp+170h+hKey]
0x1800134d0  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800134d4  mov     r9d, 20019h; samDesired
0x1800134da  mov     [rsp+170h+phkResult], rax; phkResult
0x1800134df  xor     r8d, r8d; ulOptions
0x1800134e2  mov     [rdi+50h], r15
0x1800134e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800134ed  mov     [rdi+58h], r15
0x1800134f1  call    cs:__imp_RegOpenKeyExW
0x1800134f7  cmp     eax, 2
0x1800134fa  jnz     short loc_180013514
0x1800134fc  mov     eax, 49Bh
0x180013501  mov     [rdi+10h], r14d
0x180013505  mov     [rsp+170h+var_12C], ax
0x18001350a  mov     [rsp+170h+var_130], r14d
0x18001350f  jmp     loc_18001381F
0x180013514  test    eax, eax
0x180013516  jle     short loc_180013520
0x180013518  movzx   eax, ax
0x18001351b  or      eax, 80070000h
0x180013520  mov     [rsp+170h+var_130], eax
0x180013524  test    eax, eax
0x180013526  mov     eax, 49Dh
0x18001352b  js      loc_18001381A
0x180013531  mov     rcx, [rsp+170h+hKey]; hKey
0x180013536  lea     r8, [rsp+170h+var_F8]; unsigned __int64 *
0x18001353b  lea     rdx, c_wszSafedocsScheduleLastSuccess; "LastSuccess"
0x180013542  mov     [rsp+170h+var_12C], ax
0x180013547  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18001354c  mov     [rsp+170h+var_130], eax
0x180013550  test    eax, eax
0x180013552  mov     eax, 49Fh
0x180013557  js      loc_18001381A
0x18001355d  mov     rcx, [rsp+170h+hKey]; hKey
0x180013562  lea     r8, [rsp+170h+var_F8]; unsigned __int64 *
0x180013567  mov     [rsp+170h+var_12C], ax
0x18001356c  lea     rdx, c_wszSafedocsScheduleLastResultTime; "LastResultTime"
0x180013573  mov     rax, [rsp+170h+var_F8]
0x180013578  mov     qword ptr [rbp+70h+var_70+8], rax
0x18001357c  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x180013581  mov     [rsp+170h+var_130], eax
0x180013585  test    eax, eax
0x180013587  mov     eax, 4A2h
0x18001358c  js      loc_18001381A
0x180013592  mov     rcx, [rsp+170h+hKey]; hKey
0x180013597  lea     r8, [rsp+170h+var_140]; unsigned int *
0x18001359c  mov     [rsp+170h+var_12C], ax
0x1800135a1  lea     rdx, c_wszSafedocsScheduleLastResultCode; "LastResultCode"
0x1800135a8  mov     rax, [rsp+170h+var_F8]
0x1800135ad  mov     r9d, r14d; int
0x1800135b0  mov     qword ptr [rbp+70h+var_70], rax
0x1800135b4  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800135b9  mov     [rsp+170h+var_130], eax
0x1800135bd  test    eax, eax
0x1800135bf  mov     eax, 4A5h
0x1800135c4  js      loc_18001381A
0x1800135ca  mov     ecx, [rsp+170h+var_140]
0x1800135ce  mov     [rsp+170h+var_12C], ax
0x1800135d3  mov     eax, 4A8h
0x1800135d8  cmp     ecx, 0Dh
0x1800135db  jb      short loc_1800135EA
0x1800135dd  mov     [rsp+170h+var_130], 81000036h
0x1800135e5  jmp     loc_18001381A
0x1800135ea  mov     dword ptr [rbp+70h+var_A0], ecx
0x1800135ed  lea     r8, [rsp+170h+var_140]; unsigned int *
0x1800135f2  mov     rcx, [rsp+170h+hKey]; hKey
0x1800135f7  lea     rdx, c_wszSafedocsScheduleLastResultHr; "LastResultHr"
0x1800135fe  mov     r9d, r14d; int
0x180013601  mov     [rsp+170h+var_130], ebx
0x180013605  mov     [rsp+170h+var_12C], ax
0x18001360a  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18001360f  mov     [rsp+170h+var_130], eax
0x180013613  test    eax, eax
0x180013615  mov     eax, 4ABh
0x18001361a  js      loc_18001381A
0x180013620  mov     rcx, [rsp+170h+hKey]; hKey
0x180013625  lea     r8, [rsp+170h+var_140]; unsigned int *
0x18001362a  mov     [rsp+170h+var_12C], ax
0x18001362f  lea     rdx, c_wszSafedocsScheduleLastResultDetailedHr; "LastResultDetailedHr"
0x180013636  mov     eax, [rsp+170h+var_140]
0x18001363a  mov     r9d, r14d; int
0x18001363d  mov     dword ptr [rbp+70h+var_A0+4], eax
0x180013640  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x180013645  mov     [rsp+170h+var_130], eax
0x180013649  test    eax, eax
0x18001364b  mov     eax, 4AEh
0x180013650  js      loc_18001381A
0x180013656  mov     rcx, [rsp+170h+hKey]; hKey
0x18001365b  lea     r8, [rbp+70h+pv]; unsigned __int16 **
0x18001365f  mov     [rsp+170h+var_12C], ax
0x180013664  lea     rdx, c_wszSafedocsScheduleLastResultString; "LastResultString"
0x18001366b  mov     eax, [rsp+170h+var_140]
0x18001366f  mov     r9d, r14d; int
0x180013672  mov     dword ptr [rbp+70h+var_A0+8], eax
0x180013675  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x18001367a  mov     [rsp+170h+var_130], eax
0x18001367e  test    eax, eax
0x180013680  mov     eax, 4B1h
0x180013685  js      loc_18001381A
0x18001368b  mov     rcx, [rsp+170h+hKey]; hKey
0x180013690  lea     r8, [rbp+70h+pv+8]; unsigned __int16 **
0x180013694  mov     r9d, r14d; int
0x180013697  mov     [rsp+170h+var_12C], ax
0x18001369c  lea     rdx, c_wszSafedocsScheduleLastResultTarget; "LastResultTarget"
0x1800136a3  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x1800136a8  mov     [rsp+170h+var_130], eax
0x1800136ac  test    eax, eax
0x1800136ae  mov     eax, 4B2h
0x1800136b3  js      loc_18001381A
0x1800136b9  mov     rcx, [rsp+170h+hKey]; hKey
0x1800136be  lea     r8, [rbp+70h+var_80]; unsigned __int16 **
0x1800136c2  mov     r9d, r14d; int
0x1800136c5  mov     [rsp+170h+var_12C], ax
0x1800136ca  lea     rdx, c_wszSafedocsScheduleLastResultTargetPresName; "LastResultTargetPresentableName"
0x1800136d1  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x1800136d6  mov     [rsp+170h+var_130], eax
0x1800136da  test    eax, eax
0x1800136dc  mov     eax, 4B3h
0x1800136e1  js      loc_18001381A
0x1800136e7  mov     rcx, [rsp+170h+hKey]; hKey
0x1800136ec  lea     r8, [rbp+70h+var_80+8]; unsigned __int16 **
0x1800136f0  mov     r9d, r14d; int
0x1800136f3  mov     [rsp+170h+var_12C], ax
0x1800136f8  lea     rdx, c_wszSafedocsScheduleLastResultTargetLabel; "LastResultTargetLabel"
0x1800136ff  call    ?ReadStringFromRegistry@@YAJPEAUHKEY__@@PEBGPEAPEAGH@Z; ReadStringFromRegistry(HKEY__ *,ushort const *,ushort * *,int)
0x180013704  mov     [rsp+170h+var_130], eax
0x180013708  test    eax, eax
0x18001370a  mov     eax, 4B4h
0x18001370f  js      loc_18001381A
0x180013715  mov     rcx, [rsp+170h+hKey]; hKey
0x18001371a  lea     r8, [rbp+70h+var_60]; unsigned __int64 *
0x18001371e  lea     rdx, c_wszSafedocsScheduleTotalBackupSpaceUsed; "BackupSpaceUsed"
0x180013725  mov     [rsp+170h+var_12C], ax
0x18001372a  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18001372f  mov     ecx, eax
0x180013731  mov     [rsp+170h+var_130], eax
0x180013735  test    eax, eax
0x180013737  mov     eax, 4B8h
0x18001373c  js      loc_18001381A
0x180013742  mov     [rsp+170h+var_12C], ax
0x180013747  lea     r8, [rbp+70h+var_60+8]; unsigned __int64 *
0x18001374b  mov     rax, [rbp+70h+var_60]
0x18001374f  lea     rdx, c_wszSafedocsScheduleLocalBackupSpaceUsed; "LocalBackupSpaceUsed"
0x180013756  cmp     ecx, r14d
0x180013759  mov     rcx, [rsp+170h+hKey]; hKey
0x18001375e  cmovz   rax, r15
0x180013762  mov     [rbp+70h+var_60], rax
0x180013766  call    ?SxRegReadULONGLONG@@YAJPEAUHKEY__@@PEBGPEA_KH@Z; SxRegReadULONGLONG(HKEY__ *,ushort const *,unsigned __int64 *,int)
0x18001376b  mov     ecx, eax
0x18001376d  mov     [rsp+170h+var_130], eax
0x180013771  test    eax, eax
0x180013773  mov     eax, 4BEh
0x180013778  js      loc_18001381A
0x18001377e  mov     [rsp+170h+var_12C], ax
0x180013783  lea     r8, [rsp+170h+var_140]; unsigned int *
0x180013788  mov     rax, [rbp+70h+var_60+8]
0x18001378c  lea     rdx, c_wszSafedocsScheduleActionCenterstate; "ActionCenterState"
0x180013793  cmp     ecx, r14d
0x180013796  mov     r9d, r14d; int
0x180013799  mov     rcx, [rsp+170h+hKey]; hKey
0x18001379e  cmovz   rax, r15
0x1800137a2  mov     [rbp+70h+var_60+8], rax
0x1800137a6  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800137ab  mov     [rsp+170h+var_130], eax
0x1800137af  test    eax, eax
0x1800137b1  mov     eax, 4C4h
0x1800137b6  js      short loc_18001381A
0x1800137b8  movaps  xmm0, [rbp+70h+var_B0]
0x1800137bc  lea     rcx, [rbp+70h+var_B0]; void *
0x1800137c0  movaps  xmm1, [rbp+70h+var_A0]
0x1800137c4  mov     r8, r12; Size
0x1800137c7  movups  xmmword ptr [rdi], xmm0
0x1800137ca  xor     edx, edx; Val
0x1800137cc  mov     [rsp+170h+var_12C], ax
0x1800137d1  movaps  xmm0, xmmword ptr [rbp+70h+pv]
0x1800137d5  mov     eax, [rsp+170h+var_140]
0x1800137d9  movups  xmmword ptr [rdi+10h], xmm1
0x1800137dd  mov     dword ptr [rbp+70h+var_50], eax
0x1800137e0  movaps  xmm1, xmmword ptr [rbp+70h+var_80]
0x1800137e4  movups  xmmword ptr [rdi+20h], xmm0
0x1800137e8  movaps  xmm0, [rbp+70h+var_70]
0x1800137ec  movups  xmmword ptr [rdi+30h], xmm1
0x1800137f0  movaps  xmm1, xmmword ptr [rbp+70h+var_60]
0x1800137f4  movups  xmmword ptr [rdi+40h], xmm0
0x1800137f8  movsd   xmm0, [rbp+70h+var_50]
0x1800137fd  movups  xmmword ptr [rdi+50h], xmm1
0x180013801  movsd   qword ptr [rdi+60h], xmm0
0x180013806  call    memset_0
0x18001380b  jmp     short loc_18001381F
0x18001380d  mov     [rsp+170h+var_130], 80070057h
0x180013815  mov     eax, 491h
0x18001381a  mov     [rsp+170h+var_12A], ax
0x18001381f  mov     r9d, r14d; unsigned __int16
0x180013822  lea     rdx, aCleanupschedul; "CleanupScheduledBackupStatusFields"
0x180013829  mov     r8d, 37h ; '7'; unsigned __int16
0x18001382f  lea     rcx, [rbp+70h+var_F0]; this
0x180013833  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180013838  mov     rcx, [rbp+70h+pv]; pv
0x18001383c  call    cs:__imp_CoTaskMemFree
0x180013842  mov     rcx, [rbp+70h+pv+8]; pv
0x180013846  call    cs:__imp_CoTaskMemFree
0x18001384c  mov     rcx, [rbp+70h+var_80]; pv
0x180013850  call    cs:__imp_CoTaskMemFree
0x180013856  mov     rcx, [rbp+70h+var_80+8]; pv
0x18001385a  call    cs:__imp_CoTaskMemFree
0x180013860  lea     rcx, [rbp+70h+var_F0]; this
0x180013864  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013869  mov     rcx, [rsp+170h+hKey]; hKey
0x18001386e  mov     ebx, [rsp+170h+var_130]
0x180013872  lea     rdx, [rcx-1]
0x180013876  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18001387a  ja      short loc_18001388B
0x18001387c  call    cs:__imp_RegCloseKey
0x180013882  mov     [rsp+170h+hKey], 0
0x18001388b  lea     rcx, [rsp+170h+var_130]; this
0x180013890  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180013895  mov     eax, ebx
0x180013897  mov     rcx, [rbp+70h+var_40]
0x18001389b  xor     rcx, rsp; StackCookie
0x18001389e  call    __security_check_cookie
0x1800138a3  add     rsp, 148h
0x1800138aa  pop     r15
0x1800138ac  pop     r14
0x1800138ae  pop     r12
0x1800138b0  pop     rdi
0x1800138b1  pop     rbx
0x1800138b2  pop     rbp
0x1800138b3  retn
```

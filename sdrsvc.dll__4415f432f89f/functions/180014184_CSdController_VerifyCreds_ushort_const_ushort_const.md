# CSdController::_VerifyCreds(ushort const *,ushort const *)

- ea: `0x180014184`
- end: `0x180014453`
- name: `?_VerifyCreds@CSdController@@CAJPEBG0@Z`
- size: `719`
- prototype: `__int64 __fastcall(wchar_t *Str, LPCWSTR lpszPassword)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800147fc`

## callees

- `0x1800127d0`
- `0x180014184`
- `0x18001586c`
- `0x180015974`
- `0x180015fc4`
- `0x18001764c`
- `0x180017f18`
- `0x18001c58c`
- `0x18002170a`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800143fa`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800142da`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800142da`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014253`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001432c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014253`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001432c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800143e3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800143e3`

## pseudocode

```c
__int64 __fastcall CSdController::_VerifyCreds(wchar_t *Str, LPCWSTR lpszPassword)
{
  char *v4; // rbx
  int v5; // r14d
  __int16 v6; // ax
  int v7; // eax
  bool v8; // sf
  __int64 v9; // rcx
  unsigned int v10; // edi
  HRESULT LastFailureAsHRESULT; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v13; // [rsp+34h] [rbp-CCh]
  __int16 v14; // [rsp+36h] [rbp-CAh]
  _BYTE v15[88]; // [rsp+70h] [rbp-90h] BYREF
  int v16; // [rsp+C8h] [rbp-38h]
  int v17; // [rsp+D0h] [rbp-30h]
  int v18; // [rsp+D4h] [rbp-2Ch]
  _BYTE v19[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v20[8]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v21; // [rsp+130h] [rbp+30h]
  HANDLE hToken; // [rsp+230h] [rbp+130h] BYREF
  LPVOID ppv; // [rsp+240h] [rbp+140h] BYREF
  LPVOID v24; // [rsp+248h] [rbp+148h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdController::_VerifyCreds",
    405,
    1);
  v4 = 0;
  v24 = 0;
  hToken = 0;
  ppv = 0;
  memset_0(v15, 0, 0x90u);
  memset_0(v19, 0, 0xF8u);
  v5 = 0;
  v6 = 414;
  if ( Str && (v13 = 414, v6 = 415, lpszPassword) )
  {
    v13 = 415;
    LastFailureAsHRESULT = 0;
    LastFailureAsHRESULT = CoCreateInstance(&CLSID_SdBackupConfig, 0, 1u, &IID_ISdBackupConfig, &ppv);
    v6 = 422;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    v13 = 422;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(LPVOID, _BYTE *))(*(_QWORD *)ppv + 24LL))(ppv, v19);
    v6 = 425;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_20;
    v13 = 425;
    if ( *Str && *lpszPassword )
    {
      v7 = CreateNetworkAccessTokenFromCreds(Str, lpszPassword, &hToken);
      v4 = (char *)hToken;
      v8 = v7 < 0;
      LastFailureAsHRESULT = v7;
      v6 = 430;
      if ( v8 )
        goto LABEL_20;
      v13 = 430;
      if ( !ImpersonateLoggedOnUser(hToken) )
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v9);
        v6 = 432;
        goto LABEL_20;
      }
      LastFailureAsHRESULT = 0;
      v13 = 432;
      v5 = 1;
    }
    LastFailureAsHRESULT = CoCreateInstance(&CLSID_SdEngine2, 0, 1u, &IID_ISdCommon2, &v24);
    v6 = 438;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v13 = 438;
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(LPVOID, __int64, _BYTE *))(*(_QWORD *)v24 + 104LL))(
                               v24,
                               v21,
                               v15);
      v6 = 442;
      if ( LastFailureAsHRESULT >= 0 )
      {
        v13 = 442;
        LastFailureAsHRESULT = CSdController::_MatchDevice(
                                 (struct _SD_STORAGE_DEVICE_PROP *)v20,
                                 (struct _SD_STORAGE_DEVICE_PROP *)v15);
        v6 = 445;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v13 = 445;
          if ( v18 && v16 && v17 )
          {
            LastFailureAsHRESULT = 0;
            v13 = 449;
            goto LABEL_21;
          }
          LastFailureAsHRESULT = -2130706430;
          v6 = 449;
        }
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
  }
LABEL_20:
  v14 = v6;
LABEL_21:
  CleanupStorageDeviceProp((struct _SD_STORAGE_DEVICE_PROP *)v15);
  CleanupBackupConfigFields((struct _SD_BACKUP_CONFIG *)v19);
  if ( v5 )
    CoRevertToSelf();
  v10 = LastFailureAsHRESULT;
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v24 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v24 + 16LL))(v24);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x180014184  mov     [rsp-8+arg_8], rbx
0x180014189  push    rbp
0x18001418a  push    rsi
0x18001418b  push    rdi
0x18001418c  push    r14
0x18001418e  push    r15
0x180014190  lea     rbp, [rsp-100h]
0x180014198  sub     rsp, 200h
0x18001419f  mov     rdi, rdx
0x1800141a2  mov     rsi, rcx
0x1800141a5  lea     rdx, aCsdcontrollerV; "CSdController::_VerifyCreds"
0x1800141ac  mov     r9d, 1; unsigned __int16
0x1800141b2  lea     rcx, [rsp+220h+var_1F0]; this
0x1800141b7  mov     r8d, 195h; unsigned __int16
0x1800141bd  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800141c2  xor     r15d, r15d
0x1800141c5  lea     rcx, [rsp+220h+var_1B0]; void *
0x1800141ca  mov     ebx, r15d
0x1800141cd  mov     [rbp+120h+arg_18], r15
0x1800141d4  xor     edx, edx; Val
0x1800141d6  mov     [rbp+120h+hToken], rbx
0x1800141dd  mov     r8d, 90h; Size
0x1800141e3  mov     [rbp+120h+arg_10], r15
0x1800141ea  call    memset_0
0x1800141ef  xor     edx, edx; Val
0x1800141f1  lea     rcx, [rbp+120h+var_120]; void *
0x1800141f5  mov     r8d, 0F8h; Size
0x1800141fb  call    memset_0
0x180014200  mov     r14d, r15d
0x180014203  mov     eax, 19Eh
0x180014208  test    rsi, rsi
0x18001420b  jnz     short loc_18001421A
0x18001420d  mov     [rsp+220h+var_1F0], 80070057h
0x180014215  jmp     loc_1800143C6
0x18001421a  mov     [rsp+220h+var_1EC], ax
0x18001421f  mov     eax, 19Fh
0x180014224  test    rdi, rdi
0x180014227  jz      short loc_18001420D
0x180014229  xor     edx, edx; pUnkOuter
0x18001422b  mov     [rsp+220h+var_1EC], ax
0x180014230  lea     rax, [rbp+120h+arg_10]
0x180014237  mov     [rsp+220h+var_1F0], r15d
0x18001423c  lea     r9, IID_ISdBackupConfig; riid
0x180014243  mov     [rsp+220h+ppv], rax; ppv
0x180014248  lea     rcx, CLSID_SdBackupConfig; rclsid
0x18001424f  lea     r8d, [rdx+1]; dwClsContext
0x180014253  call    cs:__imp_CoCreateInstance
0x180014259  mov     [rsp+220h+var_1F0], eax
0x18001425d  test    eax, eax
0x18001425f  mov     eax, 1A6h
0x180014264  js      loc_1800143C6
0x18001426a  mov     rcx, [rbp+120h+arg_10]
0x180014271  lea     rdx, [rbp+120h+var_120]
0x180014275  mov     [rsp+220h+var_1EC], ax
0x18001427a  mov     rax, [rcx]
0x18001427d  mov     rax, [rax+18h]
0x180014281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014286  mov     [rsp+220h+var_1F0], eax
0x18001428a  test    eax, eax
0x18001428c  mov     eax, 1A9h
0x180014291  js      loc_1800143C6
0x180014297  mov     [rsp+220h+var_1EC], ax
0x18001429c  cmp     [rsi], r15w
0x1800142a0  jz      short loc_18001430C
0x1800142a2  cmp     [rdi], r15w
0x1800142a6  jz      short loc_18001430C
0x1800142a8  lea     r8, [rbp+120h+hToken]; void **
0x1800142af  mov     rdx, rdi; lpszPassword
0x1800142b2  mov     rcx, rsi; Str
0x1800142b5  call    ?CreateNetworkAccessTokenFromCreds@@YAJPEBG0PEAPEAX@Z; CreateNetworkAccessTokenFromCreds(ushort const *,ushort const *,void * *)
0x1800142ba  mov     rbx, [rbp+120h+hToken]
0x1800142c1  test    eax, eax
0x1800142c3  mov     [rsp+220h+var_1F0], eax
0x1800142c7  mov     eax, 1AEh
0x1800142cc  js      loc_1800143C6
0x1800142d2  mov     rcx, rbx; hToken
0x1800142d5  mov     [rsp+220h+var_1EC], ax
0x1800142da  call    cs:__imp_ImpersonateLoggedOnUser
0x1800142e0  test    eax, eax
0x1800142e2  jnz     short loc_1800142F7
0x1800142e4  call    GetLastFailureAsHRESULT
0x1800142e9  mov     [rsp+220h+var_1F0], eax
0x1800142ed  mov     eax, 1B0h
0x1800142f2  jmp     loc_1800143C6
0x1800142f7  mov     eax, 1B0h
0x1800142fc  mov     [rsp+220h+var_1F0], r15d
0x180014301  mov     [rsp+220h+var_1EC], ax
0x180014306  mov     r14d, 1
0x18001430c  xor     edx, edx; pUnkOuter
0x18001430e  lea     rax, [rbp+120h+arg_18]
0x180014315  lea     r9, IID_ISdCommon2; riid
0x18001431c  mov     [rsp+220h+ppv], rax; ppv
0x180014321  lea     rcx, CLSID_SdEngine2; rclsid
0x180014328  lea     r8d, [rdx+1]; dwClsContext
0x18001432c  call    cs:__imp_CoCreateInstance
0x180014332  mov     [rsp+220h+var_1F0], eax
0x180014336  test    eax, eax
0x180014338  mov     eax, 1B6h
0x18001433d  js      loc_1800143C6
0x180014343  mov     rcx, [rbp+120h+arg_18]
0x18001434a  lea     r8, [rsp+220h+var_1B0]
0x18001434f  mov     rdx, [rbp+120h+var_F0]
0x180014353  mov     [rsp+220h+var_1EC], ax
0x180014358  mov     rax, [rcx]
0x18001435b  mov     rax, [rax+68h]
0x18001435f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014364  mov     [rsp+220h+var_1F0], eax
0x180014368  test    eax, eax
0x18001436a  mov     eax, 1BAh
0x18001436f  js      short loc_1800143C6
0x180014371  lea     rdx, [rsp+220h+var_1B0]; struct _SD_STORAGE_DEVICE_PROP *
0x180014376  mov     [rsp+220h+var_1EC], ax
0x18001437b  lea     rcx, [rbp+120h+var_F8]; struct _SD_STORAGE_DEVICE_PROP *
0x18001437f  call    ?_MatchDevice@CSdController@@CAJPEAU_SD_STORAGE_DEVICE_PROP@@0@Z; CSdController::_MatchDevice(_SD_STORAGE_DEVICE_PROP *,_SD_STORAGE_DEVICE_PROP *)
0x180014384  mov     [rsp+220h+var_1F0], eax
0x180014388  test    eax, eax
0x18001438a  mov     eax, 1BDh
0x18001438f  js      short loc_1800143C6
0x180014391  mov     [rsp+220h+var_1EC], ax
0x180014396  cmp     [rbp+120h+var_14C], r15d
0x18001439a  jz      short loc_1800143B9
0x18001439c  cmp     [rbp+120h+var_158], r15d
0x1800143a0  jz      short loc_1800143B9
0x1800143a2  cmp     [rbp+120h+var_150], r15d
0x1800143a6  jz      short loc_1800143B9
0x1800143a8  mov     eax, 1C1h
0x1800143ad  mov     [rsp+220h+var_1F0], r15d
0x1800143b2  mov     [rsp+220h+var_1EC], ax
0x1800143b7  jmp     short loc_1800143CB
0x1800143b9  mov     [rsp+220h+var_1F0], 81000002h
0x1800143c1  mov     eax, 1C1h
0x1800143c6  mov     [rsp+220h+var_1EA], ax
0x1800143cb  lea     rcx, [rsp+220h+var_1B0]; struct _SD_STORAGE_DEVICE_PROP *
0x1800143d0  call    ?CleanupStorageDeviceProp@@YAXPEAU_SD_STORAGE_DEVICE_PROP@@@Z; CleanupStorageDeviceProp(_SD_STORAGE_DEVICE_PROP *)
0x1800143d5  lea     rcx, [rbp+120h+var_120]; struct _SD_BACKUP_CONFIG *
0x1800143d9  call    ?CleanupBackupConfigFields@@YAJPEAU_SD_BACKUP_CONFIG@@@Z; CleanupBackupConfigFields(_SD_BACKUP_CONFIG *)
0x1800143de  test    r14d, r14d
0x1800143e1  jz      short loc_1800143E9
0x1800143e3  call    cs:__imp_CoRevertToSelf
0x1800143e9  mov     edi, [rsp+220h+var_1F0]
0x1800143ed  lea     rax, [rbx-1]
0x1800143f1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800143f5  ja      short loc_180014400
0x1800143f7  mov     rcx, rbx; hObject
0x1800143fa  call    cs:__imp_CloseHandle
0x180014400  mov     rcx, [rbp+120h+arg_10]
0x180014407  test    rcx, rcx
0x18001440a  jz      short loc_180014418
0x18001440c  mov     rax, [rcx]
0x18001440f  mov     rax, [rax+10h]
0x180014413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014418  mov     rcx, [rbp+120h+arg_18]
0x18001441f  test    rcx, rcx
0x180014422  jz      short loc_180014430
0x180014424  mov     rdx, [rcx]
0x180014427  mov     rax, [rdx+10h]
0x18001442b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014430  lea     rcx, [rsp+220h+var_1F0]; this
0x180014435  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001443a  mov     rbx, [rsp+220h+arg_8]
0x180014442  mov     eax, edi
0x180014444  add     rsp, 200h
0x18001444b  pop     r15
0x18001444d  pop     r14
0x18001444f  pop     rdi
0x180014450  pop     rsi
0x180014451  pop     rbp
0x180014452  retn
```

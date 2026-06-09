# CSdCommonImpl::PopulateSpecialRuleTagMap(CSdSpecialRuleTagMap *)

- ea: `0x18004882c`
- end: `0x1800489b7`
- name: `?PopulateSpecialRuleTagMap@CSdCommonImpl@@SAJPEAVCSdSpecialRuleTagMap@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(struct CSdSpecialRuleTagMap *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027220`
- `0x180041b90`

## callees

- `0x18004882c`
- `0x18005dfbc`
- `0x18005e24c`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008b924`
- `0x18008baec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004898d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004898d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800488a8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800488a8`
- `ole32!CoTaskMemFree` at `0x1800488e2`
- `ole32!CoTaskMemFree` at `0x18004896e`
- `ole32!CoTaskMemFree` at `0x1800488e2`
- `ole32!CoTaskMemFree` at `0x18004896e`

## string_xrefs

- `0x180048848`: `CSdCommonImpl::PopulateSpecialRuleTagMap`

## pseudocode

```c
__int64 __fastcall CSdCommonImpl::PopulateSpecialRuleTagMap(struct CSdSpecialRuleTagMap *a1)
{
  __int16 v2; // ax
  int v3; // eax
  bool v4; // sf
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+30h] [rbp-40h] BYREF
  __int16 i; // [rsp+34h] [rbp-3Ch]
  __int16 v10; // [rsp+36h] [rbp-3Ah]
  unsigned int v11; // [rsp+90h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+30h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CSdCommonImpl::PopulateSpecialRuleTagMap", 2726, 0);
  hKey = 0;
  v11 = 0;
  pv = 0;
  v2 = 2732;
  if ( !a1 )
  {
    v8 = -2147024809;
LABEL_15:
    v10 = v2;
    goto LABEL_16;
  }
  v8 = 0;
  i = 2732;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hKey);
  if ( v3 > 0 )
    v3 = (unsigned __int16)v3 | 0x80070000;
  v8 = v3;
  v4 = v3 < 0;
  v2 = 2735;
  if ( v4 )
    goto LABEL_15;
  for ( i = 2735; ; i = 2751 )
  {
    FreeUserProfileData((struct _UserProfileData *)pv);
    CoTaskMemFree(pv);
    pv = 0;
    v5 = EnumUserProfilePaths(hKey, &v11, (struct _UserProfileData **)&pv);
    v8 = v5;
    if ( v5 < 0 )
    {
      v10 = 2744;
      goto LABEL_16;
    }
    i = 2744;
    if ( v5 == 1 )
      break;
    v8 = _AddUserProfileInfo(a1, (struct _UserProfileData *)pv);
    if ( v8 < 0 )
    {
      v10 = 2751;
      goto LABEL_16;
    }
  }
  v8 = 0;
  v8 = _AddHKLMProfileInfo(a1);
  v2 = 2755;
  if ( v8 < 0 )
    goto LABEL_15;
  i = 2755;
LABEL_16:
  FreeUserProfileData((struct _UserProfileData *)pv);
  CoTaskMemFree(pv);
  pv = 0;
  v6 = v8;
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v8);
  return v6;
}

```

## disassembly

```asm
0x18004882c  mov     [rsp-18h+arg_18], rbx
0x180048831  push    rbp
0x180048832  push    rsi
0x180048833  push    r14
0x180048835  mov     rbp, rsp
0x180048838  sub     rsp, 70h
0x18004883c  mov     rbx, rcx
0x18004883f  xor     r9d, r9d; unsigned __int16
0x180048842  mov     r8d, 0AA6h; unsigned __int16
0x180048848  lea     rdx, aCsdcommonimplP_1; "CSdCommonImpl::PopulateSpecialRuleTagMa"...
0x18004884f  lea     rcx, [rbp+var_40]; this
0x180048853  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180048858  mov     [rbp+hKey], 0
0x180048860  mov     [rbp+arg_0], 0
0x180048867  mov     [rbp+pv], 0
0x18004886f  mov     eax, 0AACh
0x180048874  test    rbx, rbx
0x180048877  jz      loc_180048956
0x18004887d  mov     [rbp+var_40], 0
0x180048884  mov     [rbp+var_3C], ax
0x180048888  lea     rax, [rbp+hKey]
0x18004888c  mov     [rsp+70h+phkResult], rax; phkResult
0x180048891  mov     r9d, 20019h; samDesired
0x180048897  xor     r8d, r8d; ulOptions
0x18004889a  lea     rdx, c_wszProfileList; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800488a1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800488a8  call    cs:__imp_RegOpenKeyExW
0x1800488ae  test    eax, eax
0x1800488b0  jle     short loc_1800488BA
0x1800488b2  movzx   eax, ax
0x1800488b5  or      eax, 80070000h
0x1800488ba  mov     [rbp+var_40], eax
0x1800488bd  test    eax, eax
0x1800488bf  mov     eax, 0AAFh
0x1800488c4  js      loc_18004895D
0x1800488ca  mov     [rbp+var_3C], ax
0x1800488ce  lea     esi, [rax+10h]
0x1800488d1  lea     r14d, [rax+9]
0x1800488d5  mov     rcx, [rbp+pv]; struct _UserProfileData *
0x1800488d9  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x1800488de  mov     rcx, [rbp+pv]; pv
0x1800488e2  call    cs:__imp_CoTaskMemFree
0x1800488e8  mov     [rbp+pv], 0
0x1800488f0  lea     r8, [rbp+pv]; struct _UserProfileData **
0x1800488f4  lea     rdx, [rbp+arg_0]; unsigned int *
0x1800488f8  mov     rcx, [rbp+hKey]; hKey
0x1800488fc  call    ?EnumUserProfilePaths@@YAJPEAUHKEY__@@PEAKPEAPEAU_UserProfileData@@@Z; EnumUserProfilePaths(HKEY__ *,ulong *,_UserProfileData * *)
0x180048901  mov     [rbp+var_40], eax
0x180048904  test    eax, eax
0x180048906  js      short loc_18004894F
0x180048908  mov     [rbp+var_3C], r14w
0x18004890d  mov     rcx, rbx; struct CSdSpecialRuleTagMap *
0x180048910  cmp     eax, 1
0x180048913  jz      short loc_180048931
0x180048915  mov     rdx, [rbp+pv]; struct _UserProfileData *
0x180048919  call    ?_AddUserProfileInfo@@YAJPEAVCSdSpecialRuleTagMap@@PEAU_UserProfileData@@@Z; _AddUserProfileInfo(CSdSpecialRuleTagMap *,_UserProfileData *)
0x18004891e  mov     [rbp+var_40], eax
0x180048921  test    eax, eax
0x180048923  js      short loc_18004892B
0x180048925  mov     [rbp+var_3C], si
0x180048929  jmp     short loc_1800488D5
0x18004892b  mov     [rbp+var_3A], si
0x18004892f  jmp     short loc_180048961
0x180048931  mov     [rbp+var_40], 0
0x180048938  call    ?_AddHKLMProfileInfo@@YAJPEAVCSdSpecialRuleTagMap@@@Z; _AddHKLMProfileInfo(CSdSpecialRuleTagMap *)
0x18004893d  mov     [rbp+var_40], eax
0x180048940  test    eax, eax
0x180048942  mov     eax, 0AC3h
0x180048947  js      short loc_18004895D
0x180048949  mov     [rbp+var_3C], ax
0x18004894d  jmp     short loc_180048961
0x18004894f  mov     [rbp+var_3A], r14w
0x180048954  jmp     short loc_180048961
0x180048956  mov     [rbp+var_40], 80070057h
0x18004895d  mov     [rbp+var_3A], ax
0x180048961  mov     rcx, [rbp+pv]; struct _UserProfileData *
0x180048965  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x18004896a  mov     rcx, [rbp+pv]; pv
0x18004896e  call    cs:__imp_CoTaskMemFree
0x180048974  mov     [rbp+pv], 0
0x18004897c  mov     ebx, [rbp+var_40]
0x18004897f  mov     rcx, [rbp+hKey]; hKey
0x180048983  lea     rdx, [rcx-1]
0x180048987  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004898b  ja      short loc_18004899B
0x18004898d  call    cs:__imp_RegCloseKey
0x180048993  mov     [rbp+hKey], 0
0x18004899b  lea     rcx, [rbp+var_40]; this
0x18004899f  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800489a4  mov     eax, ebx
0x1800489a6  mov     rbx, [rsp+70h+arg_18]
0x1800489ae  add     rsp, 70h
0x1800489b2  pop     r14
0x1800489b4  pop     rsi
0x1800489b5  pop     rbp
0x1800489b6  retn
```

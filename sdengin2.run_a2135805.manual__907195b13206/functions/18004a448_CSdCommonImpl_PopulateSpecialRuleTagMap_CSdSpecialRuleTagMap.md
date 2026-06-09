# CSdCommonImpl::PopulateSpecialRuleTagMap(CSdSpecialRuleTagMap *)

- ea: `0x18004a448`
- end: `0x18004a5ec`
- name: `?PopulateSpecialRuleTagMap@CSdCommonImpl@@SAJPEAVCSdSpecialRuleTagMap@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(struct CSdSpecialRuleTagMap *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028258`
- `0x1800433d8`

## callees

- `0x18004a448`
- `0x180060780`
- `0x180060a20`
- `0x180072e08`
- `0x180072f14`
- `0x18008f6dc`
- `0x18008f8b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a5bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004a5bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a4c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004a4c4`
- `ole32!CoTaskMemFree` at `0x18004a504`
- `ole32!CoTaskMemFree` at `0x18004a596`
- `ole32!CoTaskMemFree` at `0x18004a504`
- `ole32!CoTaskMemFree` at `0x18004a596`

## string_xrefs

- `0x18004a464`: `CSdCommonImpl::PopulateSpecialRuleTagMap`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v8, "CSdCommonImpl::PopulateSpecialRuleTagMap", 0xAA6u, 0);
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
0x18004a448  mov     [rsp-18h+arg_18], rbx
0x18004a44d  push    rbp
0x18004a44e  push    rsi
0x18004a44f  push    r14
0x18004a451  mov     rbp, rsp
0x18004a454  sub     rsp, 70h
0x18004a458  mov     rbx, rcx
0x18004a45b  xor     r9d, r9d; unsigned __int16
0x18004a45e  mov     r8d, 0AA6h; unsigned __int16
0x18004a464  lea     rdx, aCsdcommonimplP_1; "CSdCommonImpl::PopulateSpecialRuleTagMa"...
0x18004a46b  lea     rcx, [rbp+var_40]; this
0x18004a46f  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18004a474  mov     [rbp+hKey], 0
0x18004a47c  mov     [rbp+arg_0], 0
0x18004a483  mov     [rbp+pv], 0
0x18004a48b  mov     eax, 0AACh
0x18004a490  test    rbx, rbx
0x18004a493  jz      loc_18004A57E
0x18004a499  mov     [rbp+var_40], 0
0x18004a4a0  mov     [rbp+var_3C], ax
0x18004a4a4  lea     rax, [rbp+hKey]
0x18004a4a8  mov     [rsp+70h+phkResult], rax; phkResult
0x18004a4ad  mov     r9d, 20019h; samDesired
0x18004a4b3  xor     r8d, r8d; ulOptions
0x18004a4b6  lea     rdx, c_wszProfileList; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004a4bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004a4c4  call    cs:__imp_RegOpenKeyExW
0x18004a4cb  nop     dword ptr [rax+rax+00h]
0x18004a4d0  test    eax, eax
0x18004a4d2  jle     short loc_18004A4DC
0x18004a4d4  movzx   eax, ax
0x18004a4d7  or      eax, 80070000h
0x18004a4dc  mov     [rbp+var_40], eax
0x18004a4df  test    eax, eax
0x18004a4e1  mov     eax, 0AAFh
0x18004a4e6  js      loc_18004A585
0x18004a4ec  mov     [rbp+var_3C], ax
0x18004a4f0  lea     esi, [rax+10h]
0x18004a4f3  lea     r14d, [rax+9]
0x18004a4f7  mov     rcx, [rbp+pv]; struct _UserProfileData *
0x18004a4fb  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x18004a500  mov     rcx, [rbp+pv]; pv
0x18004a504  call    cs:__imp_CoTaskMemFree
0x18004a50b  nop     dword ptr [rax+rax+00h]
0x18004a510  mov     [rbp+pv], 0
0x18004a518  lea     r8, [rbp+pv]; struct _UserProfileData **
0x18004a51c  lea     rdx, [rbp+arg_0]; unsigned int *
0x18004a520  mov     rcx, [rbp+hKey]; hKey
0x18004a524  call    ?EnumUserProfilePaths@@YAJPEAUHKEY__@@PEAKPEAPEAU_UserProfileData@@@Z; EnumUserProfilePaths(HKEY__ *,ulong *,_UserProfileData * *)
0x18004a529  mov     [rbp+var_40], eax
0x18004a52c  test    eax, eax
0x18004a52e  js      short loc_18004A577
0x18004a530  mov     [rbp+var_3C], r14w
0x18004a535  mov     rcx, rbx; struct CSdSpecialRuleTagMap *
0x18004a538  cmp     eax, 1
0x18004a53b  jz      short loc_18004A559
0x18004a53d  mov     rdx, [rbp+pv]; struct _UserProfileData *
0x18004a541  call    ?_AddUserProfileInfo@@YAJPEAVCSdSpecialRuleTagMap@@PEAU_UserProfileData@@@Z; _AddUserProfileInfo(CSdSpecialRuleTagMap *,_UserProfileData *)
0x18004a546  mov     [rbp+var_40], eax
0x18004a549  test    eax, eax
0x18004a54b  js      short loc_18004A553
0x18004a54d  mov     [rbp+var_3C], si
0x18004a551  jmp     short loc_18004A4F7
0x18004a553  mov     [rbp+var_3A], si
0x18004a557  jmp     short loc_18004A589
0x18004a559  mov     [rbp+var_40], 0
0x18004a560  call    ?_AddHKLMProfileInfo@@YAJPEAVCSdSpecialRuleTagMap@@@Z; _AddHKLMProfileInfo(CSdSpecialRuleTagMap *)
0x18004a565  mov     [rbp+var_40], eax
0x18004a568  test    eax, eax
0x18004a56a  mov     eax, 0AC3h
0x18004a56f  js      short loc_18004A585
0x18004a571  mov     [rbp+var_3C], ax
0x18004a575  jmp     short loc_18004A589
0x18004a577  mov     [rbp+var_3A], r14w
0x18004a57c  jmp     short loc_18004A589
0x18004a57e  mov     [rbp+var_40], 80070057h
0x18004a585  mov     [rbp+var_3A], ax
0x18004a589  mov     rcx, [rbp+pv]; struct _UserProfileData *
0x18004a58d  call    ?FreeUserProfileData@@YAXPEAU_UserProfileData@@@Z; FreeUserProfileData(_UserProfileData *)
0x18004a592  mov     rcx, [rbp+pv]; pv
0x18004a596  call    cs:__imp_CoTaskMemFree
0x18004a59d  nop     dword ptr [rax+rax+00h]
0x18004a5a2  mov     [rbp+pv], 0
0x18004a5aa  mov     ebx, [rbp+var_40]
0x18004a5ad  mov     rcx, [rbp+hKey]; hKey
0x18004a5b1  lea     rdx, [rcx-1]
0x18004a5b5  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004a5b9  ja      short loc_18004A5CF
0x18004a5bb  call    cs:__imp_RegCloseKey
0x18004a5c2  nop     dword ptr [rax+rax+00h]
0x18004a5c7  mov     [rbp+hKey], 0
0x18004a5cf  lea     rcx, [rbp+var_40]; this
0x18004a5d3  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18004a5d8  mov     eax, ebx
0x18004a5da  mov     rbx, [rsp+70h+arg_18]
0x18004a5e2  add     rsp, 70h
0x18004a5e6  pop     r14
0x18004a5e8  pop     rsi
0x18004a5e9  pop     rbp
0x18004a5ea  retn
```

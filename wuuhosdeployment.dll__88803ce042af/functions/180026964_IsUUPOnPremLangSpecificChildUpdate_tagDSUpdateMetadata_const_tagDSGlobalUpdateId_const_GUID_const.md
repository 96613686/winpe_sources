# IsUUPOnPremLangSpecificChildUpdate(tagDSUpdateMetadata const &,tagDSGlobalUpdateId const &,_GUID const &)

- ea: `0x180026964`
- end: `0x180026ac9`
- name: `?IsUUPOnPremLangSpecificChildUpdate@@YA_NAEBUtagDSUpdateMetadata@@AEBUtagDSGlobalUpdateId@@AEBU_GUID@@@Z`
- size: `357`
- prototype: `bool __fastcall(const struct tagDSUpdateMetadata *, const struct tagDSGlobalUpdateId *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028ea8`
- `0x18002a83c`

## callees

- `0x18000956c`
- `0x18000fcfc`
- `0x180010f54`
- `0x180026964`
- `0x18002dc7c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026aa2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026aa2`

## string_xrefs

- `0x18002699b`: `SkipUUPOnPremServiceIdCheck`
- `0x1800269a8`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
char __fastcall IsUUPOnPremLangSpecificChildUpdate(
        const struct tagDSUpdateMetadata *a1,
        const struct tagDSGlobalUpdateId *a2,
        const struct _GUID *a3)
{
  bool v6; // cl
  __int64 v7; // rcx
  __int64 v8; // rax
  bool v9; // zf
  int v10; // eax
  char v11; // di
  const WCHAR *lpString2; // rcx

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned int)AreTestKeysAllowed(v6)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v7,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"SkipUUPOnPremServiceIdCheck",
                         0) )
    {
      WUTrace(0, 0, 32, 4);
      goto LABEL_11;
    }
    v8 = *(_QWORD *)&a3->Data1 - c_idSrvPolicyDriven;
    if ( *(_QWORD *)&a3->Data1 == c_idSrvPolicyDriven )
      v8 = *(_QWORD *)a3->Data4 + 0x484E4388C74BB476LL;
    v9 = v8 == 0;
  }
  else
  {
    if ( *(_QWORD *)&a3->Data1 != c_idSrvPolicyDriven )
      return 0;
    v9 = *(_QWORD *)a3->Data4 == 0xB7B1BC7738B44B8AuLL;
  }
  if ( !v9 )
    return 0;
LABEL_11:
  if ( *(_DWORD *)a2 == *((_DWORD *)a1 + 1)
    && *((_DWORD *)a2 + 1) == *((_DWORD *)a1 + 2)
    && *((_DWORD *)a2 + 2) == *((_DWORD *)a1 + 3)
    && *((_DWORD *)a2 + 3) == *((_DWORD *)a1 + 4)
    && *((_DWORD *)a2 + 4) == *((_DWORD *)a1 + 5) )
  {
    return 0;
  }
  if ( *((_DWORD *)a1 + 128) )
    return 0;
  v10 = *((_DWORD *)a1 + 7);
  if ( (v10 & 0x200) == 0 )
    return 0;
  if ( *((_DWORD *)a1 + 30) != 12 )
    return 0;
  v11 = 1;
  if ( (v10 & 0x800) != 0 && *((_DWORD *)a1 + 100) == 1 )
  {
    lpString2 = (const WCHAR *)**((_QWORD **)a1 + 51);
    if ( L"all" == lpString2 || lpString2 && CompareStringW(0x7Fu, 1u, L"all", -1, lpString2, -1) == 2 )
      return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x180026964  mov     [rsp+arg_0], rbx
0x180026969  mov     [rsp+arg_8], rsi
0x18002696e  mov     [rsp+arg_10], rdi
0x180026973  push    r14
0x180026975  sub     rsp, 40h
0x180026979  mov     rsi, r8
0x18002697c  mov     rdi, rdx
0x18002697f  mov     rbx, rcx
0x180026982  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580>::GetImpl(void)'::`2'::impl
0x180026989  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPOnPremTestHook_58037580>::__private_IsEnabled(void)
0x18002698e  test    al, al
0x180026990  jz      short loc_180026A01
0x180026992  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x180026997  test    eax, eax
0x180026999  jz      short loc_1800269E5
0x18002699b  lea     r14, aSkipuuponprems; "SkipUUPOnPremServiceIdCheck"
0x1800269a2  xor     r9d, r9d
0x1800269a5  mov     r8, r14
0x1800269a8  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800269af  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1800269b4  test    eax, eax
0x1800269b6  jz      short loc_1800269E5
0x1800269b8  xor     edx, edx
0x1800269ba  mov     [rsp+48h+var_18], r14
0x1800269bf  lea     rax, aUsingTestOverr; " Using Test Override: %ws"
0x1800269c6  xor     ecx, ecx
0x1800269c8  mov     qword ptr [rsp+48h+cchCount2], rax
0x1800269cd  mov     [rsp+48h+lpString2], 0
0x1800269d6  lea     r9d, [rdx+4]
0x1800269da  lea     r8d, [rdx+20h]
0x1800269de  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800269e3  jmp     short loc_180026A22
0x1800269e5  mov     rax, [rsi]
0x1800269e8  sub     rax, cs:c_idSrvPolicyDriven
0x1800269ef  jnz     short loc_1800269FC
0x1800269f1  mov     rax, [rsi+8]
0x1800269f5  sub     rax, cs:qword_1800679D8
0x1800269fc  test    rax, rax
0x1800269ff  jmp     short loc_180026A1C
0x180026a01  mov     rax, [rsi]
0x180026a04  cmp     rax, cs:c_idSrvPolicyDriven
0x180026a0b  jnz     loc_180026AAD
0x180026a11  mov     rax, [rsi+8]
0x180026a15  cmp     rax, cs:qword_1800679D8
0x180026a1c  jnz     loc_180026AAD
0x180026a22  mov     eax, [rbx+4]
0x180026a25  cmp     [rdi], eax
0x180026a27  jnz     short loc_180026A49
0x180026a29  mov     eax, [rbx+8]
0x180026a2c  cmp     [rdi+4], eax
0x180026a2f  jnz     short loc_180026A49
0x180026a31  mov     eax, [rbx+0Ch]
0x180026a34  cmp     [rdi+8], eax
0x180026a37  jnz     short loc_180026A49
0x180026a39  mov     eax, [rbx+10h]
0x180026a3c  cmp     [rdi+0Ch], eax
0x180026a3f  jnz     short loc_180026A49
0x180026a41  mov     eax, [rbx+14h]
0x180026a44  cmp     [rdi+10h], eax
0x180026a47  jz      short loc_180026AAD
0x180026a49  cmp     dword ptr [rbx+200h], 0
0x180026a50  jnz     short loc_180026AAD
0x180026a52  mov     eax, [rbx+1Ch]
0x180026a55  bt      eax, 9
0x180026a59  jnb     short loc_180026AAD
0x180026a5b  cmp     dword ptr [rbx+78h], 0Ch
0x180026a5f  jnz     short loc_180026AAD
0x180026a61  mov     edi, 1
0x180026a66  bt      eax, 0Bh
0x180026a6a  jnb     short loc_180026AB0
0x180026a6c  cmp     [rbx+190h], edi
0x180026a72  jnz     short loc_180026AB0
0x180026a74  mov     rax, [rbx+198h]
0x180026a7b  lea     r8, aAll; "all"
0x180026a82  mov     rcx, [rax]
0x180026a85  cmp     r8, rcx
0x180026a88  jz      short loc_180026AAD
0x180026a8a  test    rcx, rcx
0x180026a8d  jz      short loc_180026AB0
0x180026a8f  or      r9d, 0FFFFFFFFh; cchCount1
0x180026a93  mov     edx, edi; dwCmpFlags
0x180026a95  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180026a9a  mov     [rsp+48h+lpString2], rcx; lpString2
0x180026a9f  lea     ecx, [rdi+7Eh]; Locale
0x180026aa2  call    cs:__imp_CompareStringW
0x180026aa8  cmp     eax, 2
0x180026aab  jnz     short loc_180026AB0
0x180026aad  xor     dil, dil
0x180026ab0  mov     rbx, [rsp+48h+arg_0]
0x180026ab5  mov     al, dil
0x180026ab8  mov     rdi, [rsp+48h+arg_10]
0x180026abd  mov     rsi, [rsp+48h+arg_8]
0x180026ac2  add     rsp, 40h
0x180026ac6  pop     r14
0x180026ac8  retn
```

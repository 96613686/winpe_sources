# CThemeFile::get_AppMode(int *)

- ea: `0x18000b6c0`
- end: `0x18000b784`
- name: `?get_AppMode@CThemeFile@@UEAAJPEAH@Z`
- size: `196`
- prototype: `__int64 __fastcall(CThemeFile *__hidden this, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000b6c0`
- `0x18000b78c`
- `0x18000cc2c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b731`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b75d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b731`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000b75d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b771`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b771`

## pseudocode

```c
__int64 __fastcall CThemeFile::get_AppMode(CThemeFile *this, int *a2)
{
  WCHAR *v4; // rbx
  LPCWCH lpString1; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl'::`2'::impl);
  lpString1 = 0;
  if ( (int)CThemeFile::_getThemeSetting(
              (CThemeFile *)((char *)this - 16),
              L"VisualStyles",
              L"AppMode",
              0,
              (unsigned __int16 **)&lpString1) >= 0 )
  {
    v4 = (WCHAR *)lpString1;
    if ( CompareStringOrdinal(lpString1, -1, L"Light", -1, 1) == 2 )
    {
      *a2 = 1;
    }
    else if ( CompareStringOrdinal(v4, -1, L"Dark", -1, 1) == 2 )
    {
      *a2 = 0;
    }
    CoTaskMemFree(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000b6c0  mov     [rsp+arg_0], rbx
0x18000b6c5  push    rdi
0x18000b6c6  sub     rsp, 30h
0x18000b6ca  mov     rdi, rdx
0x18000b6cd  mov     dword ptr [rdx], 1
0x18000b6d3  mov     rbx, rcx
0x18000b6d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SystemLightTheme@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme> `wil::Feature<__WilFeatureTraits_Feature_SystemLightTheme>::GetImpl(void)'::`2'::impl
0x18000b6dd  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_SystemLightTheme@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemLightTheme>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000b6e2  lea     rax, [rsp+38h+lpString1]
0x18000b6e7  mov     [rsp+38h+lpString1], 0
0x18000b6f0  lea     rcx, [rbx-10h]; this
0x18000b6f4  mov     qword ptr [rsp+38h+bIgnoreCase], rax; unsigned __int16 **
0x18000b6f9  xor     r9d, r9d; unsigned int
0x18000b6fc  lea     r8, aAppmode; "AppMode"
0x18000b703  lea     rdx, aVisualstyles; "VisualStyles"
0x18000b70a  call    ?_getThemeSetting@CThemeFile@@AEAAJPEBG0KPEAPEAG@Z; CThemeFile::_getThemeSetting(ushort const *,ushort const *,ulong,ushort * *)
0x18000b70f  test    eax, eax
0x18000b711  js      short loc_18000B777
0x18000b713  mov     rbx, [rsp+38h+lpString1]
0x18000b718  lea     r8, aLight; "Light"
0x18000b71f  or      r9d, 0FFFFFFFFh; cchCount2
0x18000b723  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000b72b  or      edx, r9d; cchCount1
0x18000b72e  mov     rcx, rbx; lpString1
0x18000b731  call    cs:__imp_CompareStringOrdinal
0x18000b737  cmp     eax, 2
0x18000b73a  jnz     short loc_18000B744
0x18000b73c  mov     dword ptr [rdi], 1
0x18000b742  jmp     short loc_18000B76E
0x18000b744  or      r9d, 0FFFFFFFFh; cchCount2
0x18000b748  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000b750  or      edx, r9d; cchCount1
0x18000b753  lea     r8, aDark_0; "Dark"
0x18000b75a  mov     rcx, rbx; lpString1
0x18000b75d  call    cs:__imp_CompareStringOrdinal
0x18000b763  cmp     eax, 2
0x18000b766  jnz     short loc_18000B76E
0x18000b768  mov     dword ptr [rdi], 0
0x18000b76e  mov     rcx, rbx; pv
0x18000b771  call    cs:__imp_CoTaskMemFree
0x18000b777  mov     rbx, [rsp+38h+arg_0]
0x18000b77c  xor     eax, eax
0x18000b77e  add     rsp, 30h
0x18000b782  pop     rdi
0x18000b783  retn
```

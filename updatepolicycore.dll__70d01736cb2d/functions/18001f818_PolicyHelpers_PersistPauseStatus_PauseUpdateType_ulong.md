# PolicyHelpers::PersistPauseStatus(PauseUpdateType,ulong)

- ea: `0x18001f818`
- end: `0x18001f878`
- name: `?PersistPauseStatus@PolicyHelpers@@SAJW4PauseUpdateType@@K@Z`
- size: `96`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180017014`
- `0x1800176d4`

## callees

- `0x18001f818`
- `0x180027234`

## string_xrefs

- `0x18001f843`: `\UpdatePolicy\Settings`
- `0x18001f866`: `\UpdatePolicy\Settings`

## pseudocode

```c
__int64 __fastcall PolicyHelpers::PersistPauseStatus(const wchar_t *a1, unsigned int a2)
{
  __int64 result; // rax
  const wchar_t *v4; // r8

  if ( !(_DWORD)a1 )
  {
    v4 = L"PausedFeatureStatus";
    return PolicyRegistryHelper::SetHKLMValue(a1, L"\\UpdatePolicy\\Settings", v4, a2);
  }
  a1 = (const wchar_t *)(unsigned int)((_DWORD)a1 - 1);
  if ( !(_DWORD)a1 )
    goto LABEL_6;
  if ( (_DWORD)a1 != 1 )
    return 2147549183LL;
  result = PolicyRegistryHelper::SetHKLMValue(a1, L"\\UpdatePolicy\\Settings", L"PausedFeatureStatus", a2);
  if ( (int)result >= 0 )
  {
LABEL_6:
    v4 = L"PausedQualityStatus";
    return PolicyRegistryHelper::SetHKLMValue(a1, L"\\UpdatePolicy\\Settings", v4, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18001f818  push    rbx
0x18001f81a  sub     rsp, 20h
0x18001f81e  mov     ebx, edx
0x18001f820  test    ecx, ecx
0x18001f822  jz      short loc_18001F85C
0x18001f824  sub     ecx, 1; wchar_t *
0x18001f827  jz      short loc_18001F853
0x18001f829  cmp     ecx, 1
0x18001f82c  jz      short loc_18001F839
0x18001f82e  mov     eax, 8000FFFFh
0x18001f833  add     rsp, 20h
0x18001f837  pop     rbx
0x18001f838  retn
0x18001f839  mov     r9d, ebx; unsigned int
0x18001f83c  lea     r8, aPausedfeatures; "PausedFeatureStatus"
0x18001f843  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f84a  call    ?SetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00K@Z; PolicyRegistryHelper::SetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,ulong)
0x18001f84f  test    eax, eax
0x18001f851  js      short loc_18001F872
0x18001f853  lea     r8, aPausedqualitys; "PausedQualityStatus"
0x18001f85a  jmp     short loc_18001F863
0x18001f85c  lea     r8, aPausedfeatures; "PausedFeatureStatus"
0x18001f863  mov     r9d, ebx; unsigned int
0x18001f866  lea     rdx, aUpdatepolicySe; "\\UpdatePolicy\\Settings"
0x18001f86d  call    ?SetHKLMValue@PolicyRegistryHelper@@SAJPEB_W00K@Z; PolicyRegistryHelper::SetHKLMValue(wchar_t const *,wchar_t const *,wchar_t const *,ulong)
0x18001f872  add     rsp, 20h
0x18001f876  pop     rbx
0x18001f877  retn
```

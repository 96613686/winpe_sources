# Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180029e70`
- end: `0x180029e8d`
- name: `?GetRuntimeClassName@CrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029ea0`
- `0x180029eb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029e86`

## string_xrefs

- `0x180029e77`: `Microsoft.Internal.UI.Composition.Effects.CrossFadeEffect`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect::GetRuntimeClassName(
        Microsoft::Internal::UI::Composition::Effects::CrossFadeEffect *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Microsoft.Internal.UI.Composition.Effects.CrossFadeEffect", 0x39u, a2);
}

```

## disassembly

```asm
0x180029e70  mov     qword ptr [rdx], 0
0x180029e77  lea     rcx, ?RuntimeClass_Microsoft_Internal_UI_Composition_Effects_CrossFadeEffect@@3QBGB; "Microsoft.Internal.UI.Composition.Effec"...
0x180029e7e  mov     r8, rdx
0x180029e81  mov     edx, 39h ; '9'
0x180029e86  jmp     cs:__imp_WindowsCreateString
```

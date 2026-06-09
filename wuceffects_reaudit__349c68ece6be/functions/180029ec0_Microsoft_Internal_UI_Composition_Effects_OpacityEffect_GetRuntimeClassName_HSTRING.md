# Microsoft::Internal::UI::Composition::Effects::OpacityEffect::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180029ec0`
- end: `0x180029edd`
- name: `?GetRuntimeClassName@OpacityEffect@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(Microsoft::Internal::UI::Composition::Effects::OpacityEffect *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180029ef0`
- `0x180029f00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180029ed6`

## string_xrefs

- `0x180029ec7`: `Microsoft.Internal.UI.Composition.Effects.OpacityEffect`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::OpacityEffect::GetRuntimeClassName(
        Microsoft::Internal::UI::Composition::Effects::OpacityEffect *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"Microsoft.Internal.UI.Composition.Effects.OpacityEffect", 0x37u, a2);
}

```

## disassembly

```asm
0x180029ec0  mov     qword ptr [rdx], 0
0x180029ec7  lea     rcx, ?RuntimeClass_Microsoft_Internal_UI_Composition_Effects_OpacityEffect@@3QBGB; "Microsoft.Internal.UI.Composition.Effec"...
0x180029ece  mov     r8, rdx
0x180029ed1  mov     edx, 37h ; '7'
0x180029ed6  jmp     cs:__imp_WindowsCreateString
```

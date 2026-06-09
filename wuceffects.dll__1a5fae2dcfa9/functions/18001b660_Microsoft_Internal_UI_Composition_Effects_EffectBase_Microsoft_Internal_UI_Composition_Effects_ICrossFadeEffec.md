# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::ICrossFadeEffect>::put_Name(HSTRING__ *)

- ea: `0x18001b660`
- end: `0x18001b6a4`
- name: `?put_Name@?$EffectBase@UICrossFadeEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAUHSTRING__@@@Z`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001b660`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18001b693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b680`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b680`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::ICrossFadeEffect>::put_Name(
        __int64 a1,
        HSTRING a2)
{
  HSTRING *v2; // rbx
  HRESULT result; // eax

  v2 = (HSTRING *)(a1 + 56);
  if ( !a2 || (result = 0, a2 != *v2) )
  {
    WindowsDeleteString(*v2);
    *v2 = 0;
    return WindowsDuplicateString(a2, v2);
  }
  return result;
}

```

## disassembly

```asm
0x18001b660  mov     [rsp+arg_0], rbx
0x18001b665  push    rdi
0x18001b666  sub     rsp, 20h
0x18001b66a  lea     rbx, [rcx+38h]
0x18001b66e  mov     rdi, rdx
0x18001b671  test    rdx, rdx
0x18001b674  jz      short loc_18001B67D
0x18001b676  xor     eax, eax
0x18001b678  cmp     rdx, [rbx]
0x18001b67b  jz      short loc_18001B699
0x18001b67d  mov     rcx, [rbx]; string
0x18001b680  call    cs:__imp_WindowsDeleteString
0x18001b686  mov     rdx, rbx; newString
0x18001b689  mov     qword ptr [rbx], 0
0x18001b690  mov     rcx, rdi; string
0x18001b693  call    cs:__imp_WindowsDuplicateString
0x18001b699  mov     rbx, [rsp+28h+arg_0]
0x18001b69e  add     rsp, 20h
0x18001b6a2  pop     rdi
0x18001b6a3  retn
```

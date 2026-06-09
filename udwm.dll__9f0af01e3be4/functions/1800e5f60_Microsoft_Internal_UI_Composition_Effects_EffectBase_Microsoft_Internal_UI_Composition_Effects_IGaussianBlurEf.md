# Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::put_Name(HSTRING__ *)

- ea: `0x1800e5f60`
- end: `0x1800e5fa4`
- name: `?put_Name@?$EffectBase@UIGaussianBlurEffect@Effects@Composition@UI@Internal@Microsoft@@@Effects@Composition@UI@Internal@Microsoft@@UEAAJPEAUHSTRING__@@@Z`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800e5f60`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800e5f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800e5f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5f80`

## pseudocode

```c
HRESULT __fastcall Microsoft::Internal::UI::Composition::Effects::EffectBase<Microsoft::Internal::UI::Composition::Effects::IGaussianBlurEffect>::put_Name(
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
0x1800e5f60  mov     [rsp+arg_0], rbx
0x1800e5f65  push    rdi
0x1800e5f66  sub     rsp, 20h
0x1800e5f6a  lea     rbx, [rcx+38h]
0x1800e5f6e  mov     rdi, rdx
0x1800e5f71  test    rdx, rdx
0x1800e5f74  jz      short loc_1800E5F7D
0x1800e5f76  xor     eax, eax
0x1800e5f78  cmp     rdx, [rbx]
0x1800e5f7b  jz      short loc_1800E5F99
0x1800e5f7d  mov     rcx, [rbx]; string
0x1800e5f80  call    cs:__imp_WindowsDeleteString
0x1800e5f86  mov     rdx, rbx; newString
0x1800e5f89  mov     qword ptr [rbx], 0
0x1800e5f90  mov     rcx, rdi; string
0x1800e5f93  call    cs:__imp_WindowsDuplicateString
0x1800e5f99  mov     rbx, [rsp+28h+arg_0]
0x1800e5f9e  add     rsp, 20h
0x1800e5fa2  pop     rdi
0x1800e5fa3  retn
```

# CDataPackagePropertySet::put_LogoBackgroundColor(Windows::UI::Color)

- ea: `0x18005cde0`
- end: `0x18005cfae`
- name: `?put_LogoBackgroundColor@CDataPackagePropertySet@@UEAAJUColor@UI@Windows@@@Z`
- size: `462`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180043b6c`
- `0x18005cde0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005ce4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cf0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005ce4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cf0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cf24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cf24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ce89`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ce89`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDataPackagePropertySet::put_LogoBackgroundColor(__int64 a1, unsigned int a2)
{
  unsigned __int8 v2; // bl
  unsigned int v4; // r14d
  unsigned int v5; // r15d
  unsigned int v6; // esi
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rdi
  void (__fastcall *v12)(__int64, _QWORD, __int64 *); // rsi
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, PVOID, __int64, _BYTE *); // rsi
  __int64 v15; // rdi
  unsigned int v16; // ebx
  __int64 v17; // rcx
  __int64 v18; // rcx
  _BYTE v20[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  __int64 v22; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF

  v2 = a2;
  v4 = a2 >> 8;
  v5 = HIWORD(a2);
  v6 = HIBYTE(a2);
  v22 = 0;
  v21 = 0;
  string = 0;
  v7 = WindowsCreateStringReference(L"Windows.Foundation.PropertyValue", 0x20u, &hstringHeader, &string);
  if ( v7 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    JUMPOUT(0x18005CFADLL);
  }
  if ( (int)RoGetActivationFactory(string, &GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858, &v21) >= 0 )
  {
    v10 = (unsigned __int8)v4 | (v6 << 16) | (((unsigned __int8)v5 | (v2 << 16)) << 8);
    v11 = v21;
    v12 = *(void (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 88LL);
    v13 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    v12(v11, v10, &v22);
  }
  v20[0] = 0;
  v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64, _BYTE *))(*(_QWORD *)(a1 + 40) + 80LL);
  v15 = v22;
  if ( WindowsCreateStringReference(
         L"LogoBackgroundColor",
         0x13u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v16 = v14(a1 + 40, hstringHeader.Reserved.Reserved1, v15, v20);
  v17 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return v16;
}

```

## disassembly

```asm
0x18005cde0  mov     [rsp-28h+arg_10], rbx
0x18005cde5  mov     [rsp-28h+arg_18], rsi
0x18005cdea  push    rbp
0x18005cdeb  push    rdi
0x18005cdec  push    r13
0x18005cdee  push    r14
0x18005cdf0  push    r15
0x18005cdf2  mov     rbp, rsp
0x18005cdf5  sub     rsp, 70h
0x18005cdf9  mov     rax, cs:__security_cookie
0x18005ce00  xor     rax, rsp
0x18005ce03  mov     [rbp+var_8], rax
0x18005ce07  mov     ebx, edx
0x18005ce09  mov     r13, rcx
0x18005ce0c  mov     r14d, edx
0x18005ce0f  shr     r14d, 8
0x18005ce13  mov     r15d, edx
0x18005ce16  shr     r15d, 10h
0x18005ce1a  mov     esi, edx
0x18005ce1c  shr     esi, 18h
0x18005ce1f  mov     [rbp+var_30], 0
0x18005ce27  mov     [rbp+var_38], 0
0x18005ce2f  mov     [rbp+string], 0
0x18005ce37  lea     r9, [rbp+string]; string
0x18005ce3b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005ce3f  mov     edx, 20h ; ' '; length
0x18005ce44  lea     rcx, ?RuntimeClass_Windows_Foundation_PropertyValue@@3QBGB; "Windows.Foundation.PropertyValue"
0x18005ce4b  call    cs:__imp_WindowsCreateStringReference
0x18005ce51  test    eax, eax
0x18005ce53  js      loc_18005CFA6
0x18005ce59  mov     rdi, [rbp+string]
0x18005ce5d  mov     rcx, [rbp+var_38]
0x18005ce61  test    rcx, rcx
0x18005ce64  jz      short loc_18005CE7B
0x18005ce66  mov     [rbp+var_38], 0
0x18005ce6e  mov     rax, [rcx]
0x18005ce71  mov     rax, [rax+10h]
0x18005ce75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce7a  nop
0x18005ce7b  lea     r8, [rbp+var_38]
0x18005ce7f  lea     rdx, _GUID_629bdbc8_d932_4ff4_96b9_8d96c5c1e858
0x18005ce86  mov     rcx, rdi
0x18005ce89  call    cs:__imp_RoGetActivationFactory
0x18005ce8f  test    eax, eax
0x18005ce91  js      short loc_18005CEE7
0x18005ce93  movzx   ebx, bl
0x18005ce96  shl     ebx, 10h
0x18005ce99  movzx   eax, r15b
0x18005ce9d  or      ebx, eax
0x18005ce9f  shl     ebx, 8
0x18005cea2  shl     esi, 10h
0x18005cea5  or      ebx, esi
0x18005cea7  movzx   eax, r14b
0x18005ceab  or      ebx, eax
0x18005cead  mov     rdi, [rbp+var_38]
0x18005ceb1  mov     rax, [rdi]
0x18005ceb4  mov     rsi, [rax+58h]
0x18005ceb8  mov     rcx, [rbp+var_30]
0x18005cebc  test    rcx, rcx
0x18005cebf  jz      short loc_18005CED6
0x18005cec1  mov     [rbp+var_30], 0
0x18005cec9  mov     r8, [rcx]
0x18005cecc  mov     rax, [r8+10h]
0x18005ced0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ced5  nop
0x18005ced6  lea     r8, [rbp+var_30]
0x18005ceda  mov     edx, ebx
0x18005cedc  mov     rcx, rdi
0x18005cedf  mov     rax, rsi
0x18005cee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cee7  mov     [rbp+var_40], 0
0x18005ceeb  mov     rax, [r13+28h]
0x18005ceef  mov     rsi, [rax+50h]
0x18005cef3  mov     rdi, [rbp+var_30]
0x18005cef7  lea     r9, [rbp+hstringHeader]; string
0x18005cefb  lea     r8, [rbp+hstringHeader.Reserved+8]; hstringHeader
0x18005ceff  mov     edx, 13h; length
0x18005cf04  lea     rcx, aLogobackground; "LogoBackgroundColor"
0x18005cf0b  call    cs:__imp_WindowsCreateStringReference
0x18005cf11  test    eax, eax
0x18005cf13  jns     short loc_18005CF2A
0x18005cf15  xor     r9d, r9d; lpArguments
0x18005cf18  xor     r8d, r8d; nNumberOfArguments
0x18005cf1b  lea     edx, [r9+1]; dwExceptionFlags
0x18005cf1f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005cf24  call    cs:__imp_RaiseException
0x18005cf2a  lea     r9, [rbp+var_40]
0x18005cf2e  mov     r8, rdi
0x18005cf31  mov     rdx, qword ptr [rbp+hstringHeader.Reserved]
0x18005cf35  lea     rcx, [r13+28h]
0x18005cf39  mov     rax, rsi
0x18005cf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf41  mov     ebx, eax
0x18005cf43  mov     rcx, [rbp+var_38]
0x18005cf47  test    rcx, rcx
0x18005cf4a  jz      short loc_18005CF61
0x18005cf4c  mov     [rbp+var_38], 0
0x18005cf54  mov     rdx, [rcx]
0x18005cf57  mov     rax, [rdx+10h]
0x18005cf5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf60  nop
0x18005cf61  mov     rcx, [rbp+var_30]
0x18005cf65  test    rcx, rcx
0x18005cf68  jz      short loc_18005CF7F
0x18005cf6a  mov     [rbp+var_30], 0
0x18005cf72  mov     rax, [rcx]
0x18005cf75  mov     rax, [rax+10h]
0x18005cf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf7e  nop
0x18005cf7f  mov     eax, ebx
0x18005cf81  mov     rcx, [rbp+var_8]
0x18005cf85  xor     rcx, rsp; StackCookie
0x18005cf88  call    __security_check_cookie
0x18005cf8d  lea     r11, [rsp+70h+var_s0]
0x18005cf92  mov     rbx, [r11+40h]
0x18005cf96  mov     rsi, [r11+48h]
0x18005cf9a  mov     rsp, r11
0x18005cf9d  pop     r15
0x18005cf9f  pop     r14
0x18005cfa1  pop     r13
0x18005cfa3  pop     rdi
0x18005cfa4  pop     rbp
0x18005cfa5  retn
0x18005cfa6  mov     ecx, eax; this
0x18005cfa8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

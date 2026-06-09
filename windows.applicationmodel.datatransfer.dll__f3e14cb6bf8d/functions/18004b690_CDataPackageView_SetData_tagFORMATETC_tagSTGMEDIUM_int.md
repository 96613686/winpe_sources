# CDataPackageView::SetData(tagFORMATETC *,tagSTGMEDIUM *,int)

- ea: `0x18004b690`
- end: `0x18004b801`
- name: `?SetData@CDataPackageView@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@H@Z`
- size: `369`
- prototype: `__int64 __fastcall(CDataPackageView *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002ad0`
- `0x180043b6c`
- `0x18004b690`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b71a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b71a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004b7b3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b7c8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b7c8`

## string_xrefs

- `0x18004b7ac`: `The attempt to set clipboard data using the specified format is disallowed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDataPackageView::SetData(
        CDataPackageView *this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3,
        unsigned int a4)
{
  CLIPFORMAT cfFormat; // ax
  HRESULT v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  unsigned int v11; // ebx
  int v12; // esi
  __int64 v13; // rcx
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  __int64 v18; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  if ( !a2
    || (cfFormat = a2->cfFormat, a2->cfFormat != word_1800AA62C)
    && cfFormat != word_1800AA62E
    && cfFormat != word_1800AA640
    && cfFormat != word_1800AA630
    && cfFormat != g_cfDropDescription )
  {
    string = 0;
    v15 = WindowsCreateStringReference(
            L"The attempt to set clipboard data using the specified format is disallowed.",
            0x4Bu,
            &hstringHeader,
            &string);
    if ( v15 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
      __debugbreak();
    }
    v11 = -2147221404;
    goto LABEL_18;
  }
  if ( !a3 && MEMORY[0] != 1 )
  {
    string = 0;
    v8 = WindowsCreateStringReference(
           L"Setting clipboard data via the indicated medium is not supported.",
           0x41u,
           &hstringHeader,
           &string);
    if ( v8 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
      JUMPOUT(0x18004B800LL);
    }
    v11 = -2147221399;
LABEL_18:
    RoOriginateError(v11, string);
    return v11;
  }
  v18 = 0;
  v12 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 13))(
          *((_QWORD *)this + 13),
          &GUID_0000010e_0000_0000_c000_000000000046,
          &v18);
  if ( v12 >= 0 )
    v12 = (*(__int64 (__fastcall **)(__int64, struct tagFORMATETC *, struct tagSTGMEDIUM *, _QWORD))(*(_QWORD *)v18 + 56LL))(
            v18,
            a2,
            a3,
            a4);
  v13 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004b690  mov     [rsp-18h+arg_8], rbx
0x18004b695  mov     [rsp-18h+arg_10], rsi
0x18004b69a  push    rbp
0x18004b69b  push    rdi
0x18004b69c  push    r14
0x18004b69e  mov     rbp, rsp
0x18004b6a1  sub     rsp, 60h
0x18004b6a5  mov     rax, cs:__security_cookie
0x18004b6ac  xor     rax, rsp
0x18004b6af  mov     [rbp+var_8], rax
0x18004b6b3  mov     r14d, r9d
0x18004b6b6  mov     rbx, r8
0x18004b6b9  mov     rdi, rdx
0x18004b6bc  test    rdx, rdx
0x18004b6bf  jz      loc_18004B797
0x18004b6c5  movzx   eax, word ptr [rdx]
0x18004b6c8  cmp     ax, cs:word_1800AA62C
0x18004b6cf  jz      short loc_18004B6F9
0x18004b6d1  cmp     ax, cs:word_1800AA62E
0x18004b6d8  jz      short loc_18004B6F9
0x18004b6da  cmp     ax, cs:word_1800AA640
0x18004b6e1  jz      short loc_18004B6F9
0x18004b6e3  cmp     ax, cs:word_1800AA630
0x18004b6ea  jz      short loc_18004B6F9
0x18004b6ec  cmp     ax, cs:g_cfDropDescription
0x18004b6f3  jnz     loc_18004B797
0x18004b6f9  test    rbx, rbx
0x18004b6fc  jnz     short loc_18004B732
0x18004b6fe  cmp     dword ptr [r8], 1
0x18004b702  jz      short loc_18004B732
0x18004b704  mov     [rbp+string], rbx
0x18004b708  lea     r9, [rbp+string]; string
0x18004b70c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004b710  lea     edx, [rbx+41h]; length
0x18004b713  lea     rcx, aSettingClipboa; "Setting clipboard data via the indicate"...
0x18004b71a  call    cs:__imp_WindowsCreateStringReference
0x18004b720  test    eax, eax
0x18004b722  js      loc_18004B7F9
0x18004b728  mov     ebx, 80040069h
0x18004b72d  jmp     loc_18004B7C2
0x18004b732  mov     [rbp+var_30], 0
0x18004b73a  mov     rcx, [rcx+68h]
0x18004b73e  mov     rax, [rcx]
0x18004b741  lea     r8, [rbp+var_30]
0x18004b745  lea     rdx, _GUID_0000010e_0000_0000_c000_000000000046
0x18004b74c  mov     rax, [rax]
0x18004b74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b754  mov     esi, eax
0x18004b756  test    eax, eax
0x18004b758  js      short loc_18004B775
0x18004b75a  mov     rcx, [rbp+var_30]
0x18004b75e  mov     rax, [rcx]
0x18004b761  mov     r9d, r14d
0x18004b764  mov     r8, rbx
0x18004b767  mov     rdx, rdi
0x18004b76a  mov     rax, [rax+38h]
0x18004b76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b773  mov     esi, eax
0x18004b775  mov     rcx, [rbp+var_30]
0x18004b779  test    rcx, rcx
0x18004b77c  jz      short loc_18004B793
0x18004b77e  mov     [rbp+var_30], 0
0x18004b786  mov     rax, [rcx]
0x18004b789  mov     rax, [rax+10h]
0x18004b78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b792  nop
0x18004b793  mov     eax, esi
0x18004b795  jmp     short loc_18004B7D0
0x18004b797  mov     [rbp+string], 0
0x18004b79f  lea     r9, [rbp+string]; string
0x18004b7a3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004b7a7  mov     edx, 4Bh ; 'K'; length
0x18004b7ac  lea     rcx, aTheAttemptToSe; "The attempt to set clipboard data using"...
0x18004b7b3  call    cs:__imp_WindowsCreateStringReference
0x18004b7b9  test    eax, eax
0x18004b7bb  js      short loc_18004B7F1
0x18004b7bd  mov     ebx, 80040064h
0x18004b7c2  mov     rdx, [rbp+string]
0x18004b7c6  mov     ecx, ebx
0x18004b7c8  call    cs:__imp_RoOriginateError
0x18004b7ce  mov     eax, ebx
0x18004b7d0  mov     rcx, [rbp+var_8]
0x18004b7d4  xor     rcx, rsp; StackCookie
0x18004b7d7  call    __security_check_cookie
0x18004b7dc  lea     r11, [rsp+60h+var_s0]
0x18004b7e1  mov     rbx, [r11+28h]
0x18004b7e5  mov     rsi, [r11+30h]
0x18004b7e9  mov     rsp, r11
0x18004b7ec  pop     r14
0x18004b7ee  pop     rdi
0x18004b7ef  pop     rbp
0x18004b7f0  retn
0x18004b7f1  mov     ecx, eax; this
0x18004b7f3  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18004b7f8  int     3; Trap to Debugger
0x18004b7f9  mov     ecx, eax; this
0x18004b7fb  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

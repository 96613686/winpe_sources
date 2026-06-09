# CFciPropertiesShellExt::PostCreateSingleSelection(HWND__ *)

- ea: `0x18000ca10`
- end: `0x18000cb47`
- name: `?PostCreateSingleSelection@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@@Z`
- size: `311`
- prototype: `void __fastcall(CFciPropertiesShellExt *this, HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c398`

## callees

- `0x18000a87c`
- `0x18000ca10`
- `0x18001b420`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000cac1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb20`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cac1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cb20`
- `USER32!SendMessageW` at `0x18000cab8`
- `USER32!SendMessageW` at `0x18000caff`
- `USER32!SendMessageW` at `0x18000cb16`
- `USER32!SendMessageW` at `0x18000cab8`
- `USER32!SendMessageW` at `0x18000caff`
- `USER32!SendMessageW` at `0x18000cb16`
- `USER32!GetSystemMetrics` at `0x18000ca4f`
- `USER32!GetSystemMetrics` at `0x18000ca4f`
- `USER32!GetClientRect` at `0x18000ca44`
- `USER32!GetClientRect` at `0x18000ca44`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::PostCreateSingleSelection(CFciPropertiesShellExt *this, HWND a2)
{
  int SystemMetrics; // ecx
  LONG right; // eax
  OLECHAR *v5; // rbx
  OLECHAR *v6; // rbx
  BSTR bstrString; // [rsp+20h] [rbp-60h] BYREF
  LPARAM lParam[2]; // [rsp+28h] [rbp-58h] BYREF
  __int128 v9; // [rsp+38h] [rbp-48h]
  __int128 v10; // [rsp+48h] [rbp-38h]
  __int64 v11; // [rsp+58h] [rbp-28h]
  struct tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

  Rect = 0;
  GetClientRect(a2, &Rect);
  SystemMetrics = GetSystemMetrics(2);
  right = Rect.right;
  if ( Rect.right > SystemMetrics )
  {
    right = Rect.right - SystemMetrics;
    Rect.right -= SystemMetrics;
  }
  *(_OWORD *)lParam = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  LODWORD(lParam[0]) = 6;
  LODWORD(lParam[1]) = right / 2;
  bstrString = 0;
  CSrmComBSTR::LoadStringW(&bstrString, off_18002B230, 0x2459u);
  v5 = bstrString;
  *(_QWORD *)&v9 = bstrString;
  SendMessageW(a2, 0x1061u, 0, (LPARAM)lParam);
  SysFreeString(v5);
  bstrString = 0;
  CSrmComBSTR::LoadStringW(&bstrString, off_18002B230, 0x247Au);
  v6 = bstrString;
  *(_QWORD *)&v9 = bstrString;
  SendMessageW(a2, 0x1061u, 1u, (LPARAM)lParam);
  SendMessageW(a2, 0x1036u, 0x420u, 1056);
  SysFreeString(v6);
}

```

## disassembly

```asm
0x18000ca10  mov     [rsp-8+arg_0], rbx
0x18000ca15  mov     [rsp-8+arg_10], rdi
0x18000ca1a  push    rbp
0x18000ca1b  mov     rbp, rsp
0x18000ca1e  sub     rsp, 80h
0x18000ca25  mov     rax, cs:__security_cookie
0x18000ca2c  xor     rax, rsp
0x18000ca2f  mov     [rbp+var_10], rax
0x18000ca33  mov     rdi, rdx
0x18000ca36  xorps   xmm0, xmm0
0x18000ca39  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18000ca3d  lea     rdx, [rbp+Rect]; lpRect
0x18000ca41  mov     rcx, rdi; hWnd
0x18000ca44  call    cs:__imp_GetClientRect
0x18000ca4a  mov     ecx, 2; nIndex
0x18000ca4f  call    cs:__imp_GetSystemMetrics
0x18000ca55  mov     ecx, eax
0x18000ca57  mov     eax, [rbp+Rect.right]
0x18000ca5a  cmp     eax, ecx
0x18000ca5c  jle     short loc_18000CA63
0x18000ca5e  sub     eax, ecx
0x18000ca60  mov     [rbp+Rect.right], eax
0x18000ca63  xorps   xmm0, xmm0
0x18000ca66  xor     ecx, ecx
0x18000ca68  movups  xmmword ptr [rbp+lParam], xmm0
0x18000ca6c  movups  [rbp+var_48], xmm0
0x18000ca70  movups  [rbp+var_38], xmm0
0x18000ca74  mov     [rbp+var_28], rcx
0x18000ca78  mov     dword ptr [rbp+lParam], 6
0x18000ca7f  cdq
0x18000ca80  sub     eax, edx
0x18000ca82  sar     eax, 1
0x18000ca84  mov     dword ptr [rbp+lParam+8], eax
0x18000ca87  mov     [rbp+bstrString], rcx
0x18000ca8b  mov     r8d, 2459h; unsigned int
0x18000ca91  mov     rdx, cs:off_18002B230; HINSTANCE
0x18000ca98  lea     rcx, [rbp+bstrString]; this
0x18000ca9c  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000caa1  mov     rbx, [rbp+bstrString]
0x18000caa5  mov     qword ptr [rbp+var_48], rbx
0x18000caa9  lea     r9, [rbp+lParam]; lParam
0x18000caad  xor     r8d, r8d; wParam
0x18000cab0  mov     edx, 1061h; Msg
0x18000cab5  mov     rcx, rdi; hWnd
0x18000cab8  call    cs:__imp_SendMessageW
0x18000cabe  mov     rcx, rbx; bstrString
0x18000cac1  call    cs:__imp_SysFreeString
0x18000cac7  mov     [rbp+bstrString], 0
0x18000cacf  mov     r8d, 247Ah; unsigned int
0x18000cad5  mov     rdx, cs:off_18002B230; HINSTANCE
0x18000cadc  lea     rcx, [rbp+bstrString]; this
0x18000cae0  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000cae5  mov     rbx, [rbp+bstrString]
0x18000cae9  mov     qword ptr [rbp+var_48], rbx
0x18000caed  lea     r9, [rbp+lParam]; lParam
0x18000caf1  mov     edx, 1061h; Msg
0x18000caf6  mov     r8d, 1; wParam
0x18000cafc  mov     rcx, rdi; hWnd
0x18000caff  call    cs:__imp_SendMessageW
0x18000cb05  mov     r8d, 420h; wParam
0x18000cb0b  mov     r9d, r8d; lParam
0x18000cb0e  mov     edx, 1036h; Msg
0x18000cb13  mov     rcx, rdi; hWnd
0x18000cb16  call    cs:__imp_SendMessageW
0x18000cb1c  nop
0x18000cb1d  mov     rcx, rbx; bstrString
0x18000cb20  call    cs:__imp_SysFreeString
0x18000cb26  mov     rcx, [rbp+var_10]
0x18000cb2a  xor     rcx, rsp; StackCookie
0x18000cb2d  call    __security_check_cookie
0x18000cb32  lea     r11, [rsp+80h+var_s0]
0x18000cb3a  mov     rbx, [r11+10h]
0x18000cb3e  mov     rdi, [r11+20h]
0x18000cb42  mov     rsp, r11
0x18000cb45  pop     rbp
0x18000cb46  retn
```

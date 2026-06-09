# CFciPropertiesShellExt::PostCreateMultiChoiceList(HWND__ *)

- ea: `0x18000c8b0`
- end: `0x18000c9e7`
- name: `?PostCreateMultiChoiceList@CFciPropertiesShellExt@@AEAAXPEAUHWND__@@@Z`
- size: `311`
- prototype: `void __fastcall(CFciPropertiesShellExt *this, HWND)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a87c`
- `0x18000c8b0`
- `0x18001b420`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000c961`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c9c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c961`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c9c0`
- `USER32!SendMessageW` at `0x18000c958`
- `USER32!SendMessageW` at `0x18000c99f`
- `USER32!SendMessageW` at `0x18000c9b6`
- `USER32!SendMessageW` at `0x18000c958`
- `USER32!SendMessageW` at `0x18000c99f`
- `USER32!SendMessageW` at `0x18000c9b6`
- `USER32!GetSystemMetrics` at `0x18000c8ef`
- `USER32!GetSystemMetrics` at `0x18000c8ef`
- `USER32!GetClientRect` at `0x18000c8e4`
- `USER32!GetClientRect` at `0x18000c8e4`

## pseudocode

```c
void __fastcall CFciPropertiesShellExt::PostCreateMultiChoiceList(CFciPropertiesShellExt *this, HWND a2)
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
  tagRECT Rect; // [rsp+60h] [rbp-20h] BYREF

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
  SendMessageW(a2, 0x1036u, 0x424u, 1060);
  SysFreeString(v6);
}

```

## disassembly

```asm
0x18000c8b0  mov     [rsp-8+arg_0], rbx
0x18000c8b5  mov     [rsp-8+arg_10], rdi
0x18000c8ba  push    rbp
0x18000c8bb  mov     rbp, rsp
0x18000c8be  sub     rsp, 80h
0x18000c8c5  mov     rax, cs:__security_cookie
0x18000c8cc  xor     rax, rsp
0x18000c8cf  mov     [rbp+var_10], rax
0x18000c8d3  mov     rdi, rdx
0x18000c8d6  xorps   xmm0, xmm0
0x18000c8d9  movups  xmmword ptr [rbp+Rect.left], xmm0
0x18000c8dd  lea     rdx, [rbp+Rect]; lpRect
0x18000c8e1  mov     rcx, rdi; hWnd
0x18000c8e4  call    cs:__imp_GetClientRect
0x18000c8ea  mov     ecx, 2; nIndex
0x18000c8ef  call    cs:__imp_GetSystemMetrics
0x18000c8f5  mov     ecx, eax
0x18000c8f7  mov     eax, [rbp+Rect.right]
0x18000c8fa  cmp     eax, ecx
0x18000c8fc  jle     short loc_18000C903
0x18000c8fe  sub     eax, ecx
0x18000c900  mov     [rbp+Rect.right], eax
0x18000c903  xorps   xmm0, xmm0
0x18000c906  xor     ecx, ecx
0x18000c908  movups  xmmword ptr [rbp+lParam], xmm0
0x18000c90c  movups  [rbp+var_48], xmm0
0x18000c910  movups  [rbp+var_38], xmm0
0x18000c914  mov     [rbp+var_28], rcx
0x18000c918  mov     dword ptr [rbp+lParam], 6
0x18000c91f  cdq
0x18000c920  sub     eax, edx
0x18000c922  sar     eax, 1
0x18000c924  mov     dword ptr [rbp+lParam+8], eax
0x18000c927  mov     [rbp+bstrString], rcx
0x18000c92b  mov     r8d, 2459h; unsigned int
0x18000c931  mov     rdx, cs:off_18002B230; HINSTANCE
0x18000c938  lea     rcx, [rbp+bstrString]; this
0x18000c93c  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000c941  mov     rbx, [rbp+bstrString]
0x18000c945  mov     qword ptr [rbp+var_48], rbx
0x18000c949  lea     r9, [rbp+lParam]; lParam
0x18000c94d  xor     r8d, r8d; wParam
0x18000c950  mov     edx, 1061h; Msg
0x18000c955  mov     rcx, rdi; hWnd
0x18000c958  call    cs:__imp_SendMessageW
0x18000c95e  mov     rcx, rbx; bstrString
0x18000c961  call    cs:__imp_SysFreeString
0x18000c967  mov     [rbp+bstrString], 0
0x18000c96f  mov     r8d, 247Ah; unsigned int
0x18000c975  mov     rdx, cs:off_18002B230; HINSTANCE
0x18000c97c  lea     rcx, [rbp+bstrString]; this
0x18000c980  call    ?LoadStringW@CSrmComBSTR@@QEAA_NPEAUHINSTANCE__@@I@Z; CSrmComBSTR::LoadStringW(HINSTANCE__ *,uint)
0x18000c985  mov     rbx, [rbp+bstrString]
0x18000c989  mov     qword ptr [rbp+var_48], rbx
0x18000c98d  lea     r9, [rbp+lParam]; lParam
0x18000c991  mov     edx, 1061h; Msg
0x18000c996  mov     r8d, 1; wParam
0x18000c99c  mov     rcx, rdi; hWnd
0x18000c99f  call    cs:__imp_SendMessageW
0x18000c9a5  mov     r8d, 424h; wParam
0x18000c9ab  mov     r9d, r8d; lParam
0x18000c9ae  mov     edx, 1036h; Msg
0x18000c9b3  mov     rcx, rdi; hWnd
0x18000c9b6  call    cs:__imp_SendMessageW
0x18000c9bc  nop
0x18000c9bd  mov     rcx, rbx; bstrString
0x18000c9c0  call    cs:__imp_SysFreeString
0x18000c9c6  mov     rcx, [rbp+var_10]
0x18000c9ca  xor     rcx, rsp; StackCookie
0x18000c9cd  call    __security_check_cookie
0x18000c9d2  lea     r11, [rsp+80h+var_s0]
0x18000c9da  mov     rbx, [r11+10h]
0x18000c9de  mov     rdi, [r11+20h]
0x18000c9e2  mov     rsp, r11
0x18000c9e5  pop     rbp
0x18000c9e6  retn
```

# AdjustComboboxWidth(DirectUI::Combobox *)

- ea: `0x180008c54`
- end: `0x180008e7e`
- name: `?AdjustComboboxWidth@@YAXPEAVCombobox@DirectUI@@@Z`
- size: `554`
- prototype: `void __fastcall(struct DirectUI::Combobox *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180010bec`

## callees

- `0x180001d60`
- `0x180001da0`
- `0x18000291e`
- `0x1800075c0`
- `0x180008c54`
- `0x18001e010`

## import_xrefs

- `GDI32!GetTextExtentPoint32W` at `0x180008db7`
- `GDI32!GetTextExtentPoint32W` at `0x180008db7`
- `GDI32!SelectObject` at `0x180008cf8`
- `GDI32!SelectObject` at `0x180008e43`
- `GDI32!SelectObject` at `0x180008cf8`
- `GDI32!SelectObject` at `0x180008e43`
- `USER32!GetSystemMetrics` at `0x180008e09`
- `USER32!GetSystemMetrics` at `0x180008e16`
- `USER32!GetSystemMetrics` at `0x180008e09`
- `USER32!GetSystemMetrics` at `0x180008e16`
- `USER32!ReleaseDC` at `0x180008e4f`
- `USER32!ReleaseDC` at `0x180008e4f`
- `USER32!GetDC` at `0x180008cbd`
- `USER32!GetDC` at `0x180008cbd`
- `USER32!SendMessageW` at `0x180008ce4`
- `USER32!SendMessageW` at `0x180008d11`
- `USER32!SendMessageW` at `0x180008d25`
- `USER32!SendMessageW` at `0x180008d5e`
- `USER32!SendMessageW` at `0x180008d82`
- `USER32!SendMessageW` at `0x180008ce4`
- `USER32!SendMessageW` at `0x180008d11`
- `USER32!SendMessageW` at `0x180008d25`
- `USER32!SendMessageW` at `0x180008d5e`
- `USER32!SendMessageW` at `0x180008d82`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180008e32`
- `DUI70!?SetWidth@Element@DirectUI@@QEAAJH@Z` at `0x180008e32`

## pseudocode

```c
void __fastcall AdjustComboboxWidth(struct DirectUI::Combobox *a1)
{
  int cx; // esi
  __int64 v3; // rax
  HWND v4; // rdi
  HDC DC; // r14
  void *v6; // rax
  HGDIOBJ v7; // r15
  unsigned int v8; // r13d
  int v9; // ebx
  int v10; // ebx
  int SystemMetrics; // eax
  int v12[2]; // [rsp+20h] [rbp-E0h] BYREF
  struct tagSIZE psizl; // [rsp+28h] [rbp-D8h] BYREF
  _DWORD lParam[5]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh]
  int v16; // [rsp+4Ch] [rbp-B4h]
  WCHAR v17[264]; // [rsp+70h] [rbp-90h] BYREF

  if ( a1 )
  {
    cx = 0;
    memset_0(lParam, 0, 0x40u);
    v3 = *(_QWORD *)a1;
    lParam[0] = 64;
    v4 = (HWND)(*(__int64 (__fastcall **)(struct DirectUI::Combobox *))(v3 + 360))(a1);
    DC = GetDC(v4);
    if ( DC )
    {
      if ( v4 )
      {
        v6 = (void *)SendMessageW(v4, 0x31u, 0, 0);
        v7 = 0;
        if ( v6 )
          v7 = SelectObject(DC, v6);
        SendMessageW(v4, 0x164u, 0, (LPARAM)lParam);
        *(_QWORD *)v12 = SendMessageW(v4, 0x146u, 0, 0);
        memset_0(v17, 0, 0x208u);
        v8 = 0;
        if ( v12[0] > 0 )
        {
          while ( 1 )
          {
            v9 = SendMessageW(v4, 0x149u, v8, 0);
            if ( v9 + 1 > 260 )
              break;
            SendMessageW(v4, 0x148u, v8, (LPARAM)v17);
            if ( (unsigned __int64)(2LL * v9) >= 0x208 )
              _report_rangecheckfailure();
            v17[v9] = 0;
            psizl = 0;
            GetTextExtentPoint32W(DC, v17, v9, &psizl);
            if ( psizl.cx > cx )
              cx = psizl.cx;
            if ( (int)++v8 >= v12[0] )
              goto LABEL_14;
          }
          v12[0] = 600;
          GetLogicalToPhysicalDPI(v12, 0);
          cx = v12[0];
LABEL_14:
          if ( cx )
          {
            v12[0] = 5;
            GetLogicalToPhysicalDPI(v12, 0);
            v10 = 2 * GetSystemMetrics(45);
            SystemMetrics = GetSystemMetrics(5);
            DirectUI::Element::SetWidth(a1, cx + v12[0] + v16 + 2 * (v10 + SystemMetrics) - v15);
          }
        }
        if ( v7 )
          SelectObject(DC, v7);
        ReleaseDC(v4, DC);
      }
    }
  }
}

```

## disassembly

```asm
0x180008c54  test    rcx, rcx
0x180008c57  jz      locret_180008E77
0x180008c5d  push    rbp
0x180008c5e  push    rbx
0x180008c5f  push    rsi
0x180008c60  push    rdi
0x180008c61  push    r12
0x180008c63  push    r13
0x180008c65  push    r14
0x180008c67  push    r15
0x180008c69  lea     rbp, [rsp-198h]
0x180008c71  sub     rsp, 298h
0x180008c78  mov     rax, cs:__security_cookie
0x180008c7f  xor     rax, rsp
0x180008c82  mov     [rbp+1D0h+var_50], rax
0x180008c89  mov     r12, rcx
0x180008c8c  xor     esi, esi
0x180008c8e  xor     edx, edx; Val
0x180008c90  lea     rcx, [rsp+2D0h+lParam]; void *
0x180008c95  lea     ebx, [rsi+40h]
0x180008c98  mov     r8d, ebx; Size
0x180008c9b  call    memset_0
0x180008ca0  mov     rax, [r12]
0x180008ca4  mov     rcx, r12
0x180008ca7  mov     [rsp+2D0h+lParam], ebx
0x180008cab  mov     rax, [rax+168h]
0x180008cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cb7  mov     rcx, rax; hWnd
0x180008cba  mov     rdi, rax
0x180008cbd  call    cs:__imp_GetDC
0x180008cc3  mov     r14, rax
0x180008cc6  test    rax, rax
0x180008cc9  jz      loc_180008E55
0x180008ccf  test    rdi, rdi
0x180008cd2  jz      loc_180008E55
0x180008cd8  xor     r9d, r9d; lParam
0x180008cdb  lea     edx, [rsi+31h]; Msg
0x180008cde  xor     r8d, r8d; wParam
0x180008ce1  mov     rcx, rdi; hWnd
0x180008ce4  call    cs:__imp_SendMessageW
0x180008cea  xor     r15d, r15d
0x180008ced  test    rax, rax
0x180008cf0  jz      short loc_180008D01
0x180008cf2  mov     rdx, rax; h
0x180008cf5  mov     rcx, r14; hdc
0x180008cf8  call    cs:__imp_SelectObject
0x180008cfe  mov     r15, rax
0x180008d01  lea     r9, [rsp+2D0h+lParam]; lParam
0x180008d06  xor     r8d, r8d; wParam
0x180008d09  mov     edx, 164h; Msg
0x180008d0e  mov     rcx, rdi; hWnd
0x180008d11  call    cs:__imp_SendMessageW
0x180008d17  xor     r9d, r9d; lParam
0x180008d1a  xor     r8d, r8d; wParam
0x180008d1d  mov     edx, 146h; Msg
0x180008d22  mov     rcx, rdi; hWnd
0x180008d25  call    cs:__imp_SendMessageW
0x180008d2b  xor     edx, edx; Val
0x180008d2d  lea     rcx, [rsp+2D0h+var_260]; void *
0x180008d32  mov     r8d, 208h; Size
0x180008d38  mov     qword ptr [rsp+2D0h+var_2B0], rax
0x180008d3d  mov     rbx, rax
0x180008d40  call    memset_0
0x180008d45  xor     r13d, r13d
0x180008d48  test    ebx, ebx
0x180008d4a  jle     loc_180008E38
0x180008d50  mov     r8d, r13d; wParam
0x180008d53  xor     r9d, r9d; lParam
0x180008d56  mov     edx, 149h; Msg
0x180008d5b  mov     rcx, rdi; hWnd
0x180008d5e  call    cs:__imp_SendMessageW
0x180008d64  mov     rbx, rax
0x180008d67  lea     ecx, [rax+1]
0x180008d6a  cmp     ecx, 104h
0x180008d70  jg      short loc_180008DD2
0x180008d72  lea     r9, [rsp+2D0h+var_260]; lParam
0x180008d77  mov     r8d, r13d; wParam
0x180008d7a  mov     edx, 148h; Msg
0x180008d7f  mov     rcx, rdi; hWnd
0x180008d82  call    cs:__imp_SendMessageW
0x180008d88  movsxd  rcx, ebx
0x180008d8b  add     rcx, rcx
0x180008d8e  cmp     rcx, 208h
0x180008d95  jnb     loc_180008E78
0x180008d9b  xor     eax, eax
0x180008d9d  lea     r9, [rsp+2D0h+psizl]; psizl
0x180008da2  mov     [rsp+rcx+2D0h+var_260], ax
0x180008da7  lea     rdx, [rsp+2D0h+var_260]; lpString
0x180008dac  mov     rcx, r14; hdc
0x180008daf  mov     qword ptr [rsp+2D0h+psizl.cx], rax
0x180008db4  mov     r8d, ebx; c
0x180008db7  call    cs:__imp_GetTextExtentPoint32W
0x180008dbd  cmp     [rsp+2D0h+psizl.cx], esi
0x180008dc1  cmovg   esi, [rsp+2D0h+psizl.cx]
0x180008dc6  inc     r13d
0x180008dc9  cmp     r13d, [rsp+2D0h+var_2B0]
0x180008dce  jl      short loc_180008D50
0x180008dd0  jmp     short loc_180008DEA
0x180008dd2  xor     edx, edx; int *
0x180008dd4  mov     [rsp+2D0h+var_2B0], 258h
0x180008ddc  lea     rcx, [rsp+2D0h+var_2B0]; int *
0x180008de1  call    ?GetLogicalToPhysicalDPI@@YAXPEAH0@Z; GetLogicalToPhysicalDPI(int *,int *)
0x180008de6  mov     esi, [rsp+2D0h+var_2B0]
0x180008dea  test    esi, esi
0x180008dec  jz      short loc_180008E38
0x180008dee  mov     r13d, 5
0x180008df4  lea     rcx, [rsp+2D0h+var_2B0]; int *
0x180008df9  xor     edx, edx; int *
0x180008dfb  mov     [rsp+2D0h+var_2B0], r13d
0x180008e00  call    ?GetLogicalToPhysicalDPI@@YAXPEAH0@Z; GetLogicalToPhysicalDPI(int *,int *)
0x180008e05  lea     ecx, [r13+28h]; nIndex
0x180008e09  call    cs:__imp_GetSystemMetrics
0x180008e0f  mov     ebx, eax
0x180008e11  mov     ecx, r13d; nIndex
0x180008e14  add     ebx, ebx
0x180008e16  call    cs:__imp_GetSystemMetrics
0x180008e1c  add     eax, ebx
0x180008e1e  mov     rcx, r12
0x180008e21  lea     edx, [rax+rax]
0x180008e24  sub     edx, [rsp+2D0h+var_28C]
0x180008e28  add     edx, [rsp+2D0h+var_284]
0x180008e2c  add     edx, [rsp+2D0h+var_2B0]
0x180008e30  add     edx, esi
0x180008e32  call    cs:__imp_?SetWidth@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetWidth(int)
0x180008e38  test    r15, r15
0x180008e3b  jz      short loc_180008E49
0x180008e3d  mov     rdx, r15; h
0x180008e40  mov     rcx, r14; hdc
0x180008e43  call    cs:__imp_SelectObject
0x180008e49  mov     rdx, r14; hDC
0x180008e4c  mov     rcx, rdi; hWnd
0x180008e4f  call    cs:__imp_ReleaseDC
0x180008e55  mov     rcx, [rbp+1D0h+var_50]
0x180008e5c  xor     rcx, rsp; StackCookie
0x180008e5f  call    __security_check_cookie
0x180008e64  add     rsp, 298h
0x180008e6b  pop     r15
0x180008e6d  pop     r14
0x180008e6f  pop     r13
0x180008e71  pop     r12
0x180008e73  pop     rdi
0x180008e74  pop     rsi
0x180008e75  pop     rbx
0x180008e76  pop     rbp
0x180008e77  retn
0x180008e78  call    __report_rangecheckfailure
```

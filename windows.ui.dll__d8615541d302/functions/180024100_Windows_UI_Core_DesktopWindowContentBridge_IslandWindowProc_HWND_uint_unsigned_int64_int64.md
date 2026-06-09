# Windows::UI::Core::DesktopWindowContentBridge::IslandWindowProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180024100`
- end: `0x1800243a4`
- name: `?IslandWindowProc@DesktopWindowContentBridge@Core@UI@Windows@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `676`
- prototype: `__int64 __fastcall(HWND, UINT Msg, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800038e0`
- `0x180023ad4`
- `0x180024100`
- `0x1800243ac`
- `0x180026b84`
- `0x180026c00`
- `0x180026cd8`
- `0x18004ed78`
- `0x180050360`
- `0x18005f1a4`
- `0x1800ca010`

## import_xrefs

- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x180024232`
- `ext-ms-win-uiacore-l1-1-0!UiaReturnRawElementProvider` at `0x180024232`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18002411b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18002411b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x180024173`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DefWindowProcW` at `0x180024173`

## string_xrefs

- `0x180024267`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x18002429d`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800242b7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x1800242fa`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`
- `0x180024332`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\desktopwindowcontentbridge.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LONG_PTR __fastcall Windows::UI::Core::DesktopWindowContentBridge::IslandWindowProc(
        HWND a1,
        UINT Msg,
        WPARAM wParam,
        LPARAM lParam)
{
  Windows::UI::Core::DesktopWindowContentBridge *WindowLongPtrW; // rax
  Windows::UI::Core::DesktopWindowContentBridge *v9; // rdi
  __int64 v11; // rcx
  int v12; // eax
  Windows::UI::Core::DesktopWindowContentBridgeProvider *v13; // rax
  __int64 v14; // rsi
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // eax
  int v18; // eax
  int updated; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rax
  float Window_ScaleFactor; // xmm0_4
  int v24[14]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  WindowLongPtrW = (Windows::UI::Core::DesktopWindowContentBridge *)GetWindowLongPtrW(a1, -21);
  v9 = WindowLongPtrW;
  if ( !WindowLongPtrW )
    return DefWindowProcW(a1, Msg, wParam, lParam);
  LOBYTE(v24[0]) = 0;
  if ( Msg == 7 )
  {
    v11 = *((_QWORD *)WindowLongPtrW + 27);
    if ( !v11 )
      return DefWindowProcW(a1, Msg, wParam, lParam);
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v11 + 24LL))(v11, v24);
    if ( v12 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1C5,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
        (const char *)(unsigned int)v12,
        v24[0]);
    goto LABEL_11;
  }
  if ( Msg != 61 )
  {
    if ( Msg != 71 )
    {
      if ( Msg == 130 )
      {
        Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)WindowLongPtrW + 176);
        *((_QWORD *)v9 + 13) = 0;
        updated = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v9 + 2) + 48LL))((__int64)v9 + 16);
        if ( updated >= 0 )
          goto LABEL_11;
        v20 = 445;
      }
      else
      {
        if ( Msg != 736 && Msg != 738 )
          return DefWindowProcW(a1, Msg, wParam, lParam);
        Window_ScaleFactor = Windows::UI::Core::DesktopWindowContentBridge::Get_Window_ScaleFactor(WindowLongPtrW);
        updated = Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(v9, Window_ScaleFactor);
        if ( updated >= 0 )
        {
          LOBYTE(v24[0]) = 1;
          goto LABEL_11;
        }
        v20 = 482;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
        (const char *)(unsigned int)updated,
        v24[0]);
      goto LABEL_11;
    }
    if ( (*(_BYTE *)(lParam + 32) & 1) == 0 )
    {
      v21 = Windows::UI::Core::DesktopWindowContentBridge::OnWindowResized(
              WindowLongPtrW,
              *(_DWORD *)(lParam + 24),
              *(_DWORD *)(lParam + 28));
      if ( v21 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1D0,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
          (const char *)(unsigned int)v21,
          v24[0]);
    }
    if ( (*(_BYTE *)(lParam + 32) & 0x40) != 0 )
    {
      v17 = Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(v9, 1);
      if ( v17 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1D5,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
          (const char *)(unsigned int)v17,
          v24[0]);
    }
    else if ( *(char *)(lParam + 32) < 0 )
    {
      v18 = Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(v9, 0);
      if ( v18 < 0 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0x1D9,
          (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\desktopwindowcontentbridge.cpp",
          (const char *)(unsigned int)v18,
          v24[0]);
    }
LABEL_11:
    if ( LOBYTE(v24[0]) )
      return 0;
    return DefWindowProcW(a1, Msg, wParam, lParam);
  }
  if ( lParam != -25 )
    return DefWindowProcW(a1, Msg, wParam, lParam);
  if ( !*((_QWORD *)WindowLongPtrW + 22) )
  {
    v13 = (Windows::UI::Core::DesktopWindowContentBridgeProvider *)operator new(
                                                                     0x30u,
                                                                     (const struct std::nothrow_t *)std::nothrow);
    if ( v13 )
    {
      v22 = Windows::UI::Core::DesktopWindowContentBridgeProvider::DesktopWindowContentBridgeProvider(v13, a1);
      v14 = v22;
      if ( v22 )
      {
        v15 = v22 + 8;
        goto LABEL_18;
      }
    }
    else
    {
      v14 = 0;
    }
    v15 = 0;
LABEL_18:
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    v16 = *((_QWORD *)v9 + 22);
    *((_QWORD *)v9 + 22) = v15;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return UiaReturnRawElementProvider(a1, wParam, -25, *((IRawElementProviderSimple **)v9 + 22));
}

```

## disassembly

```asm
0x180024100  push    rbx
0x180024102  push    rbp
0x180024103  push    rsi
0x180024104  push    rdi
0x180024105  push    r14
0x180024107  sub     rsp, 30h
0x18002410b  mov     rbx, r9
0x18002410e  mov     r14, r8
0x180024111  mov     esi, edx
0x180024113  mov     rbp, rcx
0x180024116  mov     edx, 0FFFFFFEBh; nIndex
0x18002411b  call    cs:__imp_GetWindowLongPtrW
0x180024121  mov     rdi, rax
0x180024124  test    rax, rax
0x180024127  jz      short loc_180024168
0x180024129  mov     byte ptr [rsp+58h+var_38], 0; int
0x18002412e  mov     r10d, esi
0x180024131  sub     r10d, 7
0x180024135  jz      short loc_180024184
0x180024137  sub     r10d, 36h ; '6'
0x18002413b  jz      short loc_1800241B4
0x18002413d  sub     r10d, 0Ah
0x180024141  jz      loc_18002423D
0x180024147  sub     r10d, 3Bh ; ';'
0x18002414b  jz      loc_1800242C9
0x180024151  sub     r10d, 25Eh
0x180024158  jz      loc_180024364
0x18002415e  cmp     r10d, 2
0x180024162  jz      loc_180024364
0x180024168  mov     r9, rbx; lParam
0x18002416b  mov     r8, r14; wParam
0x18002416e  mov     edx, esi; Msg
0x180024170  mov     rcx, rbp; hWnd
0x180024173  call    cs:__imp_DefWindowProcW
0x180024179  add     rsp, 30h
0x18002417d  pop     r14
0x18002417f  pop     rdi
0x180024180  pop     rsi
0x180024181  pop     rbp
0x180024182  pop     rbx
0x180024183  retn
0x180024184  mov     rcx, [rax+0D8h]
0x18002418b  test    rcx, rcx
0x18002418e  jz      short loc_180024168
0x180024190  mov     rax, [rcx]
0x180024193  lea     rdx, [rsp+58h+var_38]
0x180024198  mov     rax, [rax+18h]
0x18002419c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241a1  test    eax, eax
0x1800241a3  js      loc_1800242AF
0x1800241a9  cmp     byte ptr [rsp+58h+var_38], 0
0x1800241ae  jz      short loc_180024168
0x1800241b0  xor     eax, eax
0x1800241b2  jmp     short loc_180024179
0x1800241b4  cmp     rbx, 0FFFFFFFFFFFFFFE7h
0x1800241b8  jnz     short loc_180024168
0x1800241ba  cmp     qword ptr [rax+0B0h], 0
0x1800241c2  jnz     short loc_18002421E
0x1800241c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800241cb  lea     ecx, [rbx+49h]; unsigned __int64
0x1800241ce  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800241d3  test    rax, rax
0x1800241d6  jnz     loc_180024344
0x1800241dc  xor     esi, esi
0x1800241de  xor     ebx, ebx
0x1800241e0  test    rbx, rbx
0x1800241e3  jz      short loc_1800241F5
0x1800241e5  mov     rax, [rbx]
0x1800241e8  mov     rcx, rbx
0x1800241eb  mov     rax, [rax+8]
0x1800241ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241f4  nop
0x1800241f5  mov     rcx, [rdi+0B0h]
0x1800241fc  mov     [rdi+0B0h], rbx
0x180024203  test    rcx, rcx
0x180024206  jz      short loc_180024215
0x180024208  mov     rax, [rcx]
0x18002420b  mov     rax, [rax+10h]
0x18002420f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024214  nop
0x180024215  test    rsi, rsi
0x180024218  jnz     loc_18002438F
0x18002421e  mov     r9, [rdi+0B0h]; el
0x180024225  mov     r8, 0FFFFFFFFFFFFFFE7h; lParam
0x18002422c  mov     rdx, r14; wParam
0x18002422f  mov     rcx, rbp; hwnd
0x180024232  call    cs:__imp_UiaReturnRawElementProvider
0x180024238  jmp     loc_180024179
0x18002423d  test    byte ptr [rbx+20h], 1
0x180024241  jz      loc_180024313
0x180024247  test    byte ptr [rbx+20h], 40h
0x18002424b  jz      short loc_180024279
0x18002424d  mov     dl, 1; bool
0x18002424f  mov     rcx, rdi; this
0x180024252  call    ?ShowIslandSite@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJ_N@Z; Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(bool)
0x180024257  test    eax, eax
0x180024259  jns     loc_1800241A9
0x18002425f  mov     rcx, [rsp+58h]; this
0x180024264  mov     r9d, eax; char *
0x180024267  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x18002426e  mov     edx, 1D5h; void *
0x180024273  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180024279  test    byte ptr [rbx+20h], 80h
0x18002427d  jz      loc_1800241A9
0x180024283  xor     edx, edx; bool
0x180024285  mov     rcx, rdi; this
0x180024288  call    ?ShowIslandSite@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJ_N@Z; Windows::UI::Core::DesktopWindowContentBridge::ShowIslandSite(bool)
0x18002428d  test    eax, eax
0x18002428f  jns     loc_1800241A9
0x180024295  mov     rcx, [rsp+58h]; this
0x18002429a  mov     r9d, eax; char *
0x18002429d  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800242a4  mov     edx, 1D9h; void *
0x1800242a9  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800242af  mov     rcx, [rsp+58h]; this
0x1800242b4  mov     r9d, eax; char *
0x1800242b7  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x1800242be  mov     edx, 1C5h; void *
0x1800242c3  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800242c9  lea     rcx, [rax+0B0h]
0x1800242d0  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800242d5  mov     qword ptr [rdi+68h], 0
0x1800242dd  lea     rcx, [rdi+10h]
0x1800242e1  mov     rax, [rcx]
0x1800242e4  mov     rax, [rax+30h]
0x1800242e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800242ed  test    eax, eax
0x1800242ef  jns     loc_1800241A9
0x1800242f5  mov     edx, 1BDh; void *
0x1800242fa  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180024301  mov     r9d, eax; char *
0x180024304  mov     rcx, [rsp+58h]; this
0x180024309  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002430e  jmp     loc_1800241A9
0x180024313  mov     r8d, [rbx+1Ch]; int
0x180024317  mov     edx, [rbx+18h]; int
0x18002431a  mov     rcx, rdi; this
0x18002431d  call    ?OnWindowResized@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJHH@Z; Windows::UI::Core::DesktopWindowContentBridge::OnWindowResized(int,int)
0x180024322  test    eax, eax
0x180024324  jns     loc_180024247
0x18002432a  mov     rcx, [rsp+58h]; this
0x18002432f  mov     r9d, eax; char *
0x180024332  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180024339  mov     edx, 1D0h; void *
0x18002433e  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x180024344  mov     rdx, rbp; HWND
0x180024347  mov     rcx, rax; this
0x18002434a  call    ??0DesktopWindowContentBridgeProvider@Core@UI@Windows@@QEAA@PEAUHWND__@@@Z; Windows::UI::Core::DesktopWindowContentBridgeProvider::DesktopWindowContentBridgeProvider(HWND__ *)
0x18002434f  mov     rsi, rax
0x180024352  test    rax, rax
0x180024355  jz      loc_1800241DE
0x18002435b  lea     rbx, [rax+8]
0x18002435f  jmp     loc_1800241E0
0x180024364  mov     rcx, rdi; this
0x180024367  call    ?Get_Window_ScaleFactor@DesktopWindowContentBridge@Core@UI@Windows@@AEAAMXZ; Windows::UI::Core::DesktopWindowContentBridge::Get_Window_ScaleFactor(void)
0x18002436c  movaps  xmm1, xmm0; float
0x18002436f  mov     rcx, rdi; this
0x180024372  call    ?UpdateScaleFactor@DesktopWindowContentBridge@Core@UI@Windows@@AEAAJM@Z; Windows::UI::Core::DesktopWindowContentBridge::UpdateScaleFactor(float)
0x180024377  test    eax, eax
0x180024379  js      short loc_180024385
0x18002437b  mov     byte ptr [rsp+58h+var_38], 1
0x180024380  jmp     loc_1800241A9
0x180024385  mov     edx, 1E2h
0x18002438a  jmp     loc_1800242FA
0x18002438f  mov     rax, [rsi]
0x180024392  mov     rcx, rsi
0x180024395  mov     rax, [rax+10h]
0x180024399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002439e  jmp     loc_18002421E
```

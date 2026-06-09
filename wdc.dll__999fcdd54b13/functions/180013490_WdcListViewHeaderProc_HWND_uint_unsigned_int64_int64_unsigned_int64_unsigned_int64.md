# WdcListViewHeaderProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)

- ea: `0x180013490`
- end: `0x1800137c9`
- name: `?WdcListViewHeaderProc@@YA_JPEAUHWND__@@I_K_J11@Z`
- size: `825`
- prototype: `LRESULT __stdcall(HWND hWnd, UINT uMsg, WPARAM wParam, LPARAM lParam, UINT_PTR uIdSubclass, DWORD_PTR dwRefData)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180013490`
- `0x18007b1bc`
- `0x180086010`

## import_xrefs

- `DUser!ForwardGadgetMessage` at `0x18001359f`
- `DUser!ForwardGadgetMessage` at `0x18001359f`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x1800137bc`
- `COMCTL32!__imp_RemoveWindowSubclass` at `0x1800137bc`
- `COMCTL32!__imp_DefSubclassProc` at `0x18001352c`
- `COMCTL32!__imp_DefSubclassProc` at `0x18001352c`
- `USER32!GetKeyState` at `0x1800135b7`
- `USER32!GetKeyState` at `0x1800135cb`
- `USER32!GetKeyState` at `0x18001366d`
- `USER32!GetKeyState` at `0x180013681`
- `USER32!GetKeyState` at `0x18001370d`
- `USER32!GetKeyState` at `0x180013721`
- `USER32!GetKeyState` at `0x180013735`
- `USER32!GetKeyState` at `0x1800135b7`
- `USER32!GetKeyState` at `0x1800135cb`
- `USER32!GetKeyState` at `0x18001366d`
- `USER32!GetKeyState` at `0x180013681`
- `USER32!GetKeyState` at `0x18001370d`
- `USER32!GetKeyState` at `0x180013721`
- `USER32!GetKeyState` at `0x180013735`
- `USER32!SetFocus` at `0x180013762`
- `USER32!SetFocus` at `0x180013762`
- `USER32!SendMessageW` at `0x1800135f4`
- `USER32!SendMessageW` at `0x180013611`
- `USER32!SendMessageW` at `0x1800136d2`
- `USER32!SendMessageW` at `0x1800135f4`
- `USER32!SendMessageW` at `0x180013611`
- `USER32!SendMessageW` at `0x1800136d2`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180013584`
- `DUI70!?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ` at `0x180013584`

## pseudocode

```c
LRESULT __fastcall WdcListViewHeaderProc(
        HWND hWnd,
        UINT uMsg,
        WPARAM wParam,
        struct tagNMTTDISPINFOW *lParam,
        UINT_PTR uIdSubclass,
        WdcListView *dwRefData)
{
  struct HGADGET__ *DisplayNode; // rax
  __int64 v12; // rax
  HWND v13; // rax
  UINT code; // eax
  __int64 v15; // [rsp+30h] [rbp-A9h] BYREF
  HWND v16; // [rsp+38h] [rbp-A1h] BYREF
  __int128 v17; // [rsp+40h] [rbp-99h]
  __int128 v18; // [rsp+50h] [rbp-89h]
  __int64 v19; // [rsp+60h] [rbp-79h] BYREF
  __int128 v20; // [rsp+68h] [rbp-71h]
  __int128 v21; // [rsp+78h] [rbp-61h]
  __int128 v22; // [rsp+88h] [rbp-51h]
  __int64 v23; // [rsp+98h] [rbp-41h]
  _DWORD lParama[5]; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v25; // [rsp+B4h] [rbp-25h]
  __int128 v26; // [rsp+C4h] [rbp-15h]
  __int128 v27; // [rsp+D4h] [rbp-5h]
  int v28; // [rsp+E4h] [rbp+Bh]

  lParama[0] = 4;
  v23 = 0;
  v28 = 0;
  v15 = 0;
  v19 = 0;
  v16 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v17 = 0;
  v18 = 0;
  *(_OWORD *)&lParama[1] = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  if ( uMsg == 2 )
  {
    RemoveWindowSubclass(hWnd, WdcListViewHeaderProc, 0);
  }
  else if ( uMsg == 78 )
  {
    code = lParam->hdr.code;
    if ( code == -530 )
    {
      if ( WdcListView::OnTooltipNotify(dwRefData, hWnd, lParam) >= 0 )
        return 1;
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    }
    if ( code != -521 )
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    WdcListView::OnTooltipNotify(dwRefData, hWnd, 0);
  }
  else
  {
    if ( uMsg != 256 && uMsg - 257 >= 2 )
      return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
    switch ( wParam )
    {
      case 9uLL:
        if ( GetKeyState(16) >= 0 && GetKeyState(17) >= 0 && GetKeyState(18) >= 0 )
        {
          if ( uMsg == 258 )
          {
            v13 = (HWND)(*(__int64 (__fastcall **)(WdcListView *))(*(_QWORD *)dwRefData + 360LL))(dwRefData);
            SetFocus(v13);
          }
          return 0;
        }
LABEL_10:
        (*(void (__fastcall **)(WdcListView *))(*(_QWORD *)dwRefData + 168LL))(dwRefData);
        DisplayNode = DirectUI::Element::GetDisplayNode(dwRefData);
        if ( (unsigned int)ForwardGadgetMessage(DisplayNode, uMsg, wParam, lParam, &v15) )
          return 0;
        return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
      case 0xDuLL:
        if ( GetKeyState(17) < 0 || GetKeyState(18) < 0 || uMsg != 258 )
          return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
        v19 = (*(__int64 (__fastcall **)(WdcListView *))(*(_QWORD *)dwRefData + 360LL))(dwRefData);
        DWORD2(v20) = -108;
        LODWORD(v21) = -1;
        DWORD1(v21) = SendMessageW(hWnd, 0x121Bu, 0, 0);
        (*(void (__fastcall **)(WdcListView *, __int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)dwRefData + 368LL))(
          dwRefData,
          78,
          0,
          &v19,
          &v15);
        break;
      case 0x20uLL:
        if ( GetKeyState(17) < 0
          || GetKeyState(18) < 0
          || uMsg != 258
          || (unsigned int)SendMessageW(hWnd, 0x121Bu, 0, 0)
          || !(unsigned int)SendMessageW(hWnd, 0x120Bu, 0, (LPARAM)lParama) )
        {
          return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
        }
        *((_QWORD *)&v18 + 1) = lParama;
        v16 = hWnd;
        v12 = *(_QWORD *)dwRefData;
        DWORD2(v17) = -316;
        LODWORD(v18) = 0;
        (*(void (__fastcall **)(WdcListView *, __int64, _QWORD, HWND *, __int64 *))(v12 + 368))(
          dwRefData,
          78,
          0,
          &v16,
          &v15);
        break;
      default:
        if ( wParam - 33 > 1 )
          return DefSubclassProc(hWnd, uMsg, wParam, (LPARAM)lParam);
        goto LABEL_10;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180013490  push    rbp
0x180013492  push    rbx
0x180013493  push    rsi
0x180013494  push    rdi
0x180013495  push    r14
0x180013497  push    r15
0x180013499  lea     rbp, [rsp-1Fh]
0x18001349e  sub     rsp, 0F8h
0x1800134a5  xorps   xmm0, xmm0
0x1800134a8  mov     dword ptr [rbp+47h+lParam], 4
0x1800134af  xor     eax, eax
0x1800134b1  xor     ebx, ebx
0x1800134b3  xorps   xmm1, xmm1
0x1800134b6  mov     [rbp+47h+var_88], rax
0x1800134ba  mov     [rbp+47h+var_3C], eax
0x1800134bd  mov     r14, r9
0x1800134c0  mov     eax, edx
0x1800134c2  mov     [rsp+120h+var_F0], rbx
0x1800134c7  mov     [rbp+47h+var_C0], rbx
0x1800134cb  mov     r15, r8
0x1800134ce  mov     [rsp+120h+var_E8], rbx
0x1800134d3  mov     edi, edx
0x1800134d5  mov     rsi, rcx
0x1800134d8  movups  [rbp+47h+var_B8], xmm0
0x1800134dc  movups  [rbp+47h+var_A8], xmm0
0x1800134e0  movups  [rbp+47h+var_98], xmm0
0x1800134e4  movups  [rsp+120h+var_E0], xmm0
0x1800134e9  movups  [rsp+120h+var_D0], xmm0
0x1800134ee  movups  xmmword ptr [rbp+47h+lParam+4], xmm1
0x1800134f2  movups  [rbp+47h+var_6C], xmm1
0x1800134f6  movups  [rbp+47h+var_5C], xmm1
0x1800134fa  movups  [rbp+47h+var_4C], xmm1
0x1800134fe  sub     eax, 2
0x180013501  jz      loc_1800137B2
0x180013507  sub     eax, 4Ch ; 'L'
0x18001350a  jz      loc_18001376A
0x180013510  sub     eax, 0B2h
0x180013515  jz      short loc_180013542
0x180013517  sub     eax, 1
0x18001351a  jz      short loc_180013542
0x18001351c  cmp     eax, 1
0x18001351f  jz      short loc_180013542
0x180013521  mov     r9, r14; lParam
0x180013524  mov     r8, r15; wParam
0x180013527  mov     edx, edi; uMsg
0x180013529  mov     rcx, rsi; hWnd
0x18001352c  call    cs:__imp_DefSubclassProc
0x180013532  add     rsp, 0F8h
0x180013539  pop     r15
0x18001353b  pop     r14
0x18001353d  pop     rdi
0x18001353e  pop     rsi
0x18001353f  pop     rbx
0x180013540  pop     rbp
0x180013541  retn
0x180013542  mov     rax, r15
0x180013545  sub     rax, 9
0x180013549  jz      loc_180013708
0x18001354f  sub     rax, 4
0x180013553  jz      loc_180013668
0x180013559  sub     rax, 13h
0x18001355d  jz      short loc_1800135B2
0x18001355f  sub     rax, 1
0x180013563  jz      short loc_18001356B
0x180013565  cmp     rax, 1
0x180013569  jnz     short loc_180013521
0x18001356b  mov     rbx, [rbp+47h+dwRefData]
0x18001356f  mov     rcx, rbx
0x180013572  mov     rax, [rbx]
0x180013575  mov     rax, [rax+0A8h]
0x18001357c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013581  mov     rcx, rbx
0x180013584  call    cs:__imp_?GetDisplayNode@Element@DirectUI@@QEAAPEAUHGADGET__@@XZ; DirectUI::Element::GetDisplayNode(void)
0x18001358a  mov     r9, r14
0x18001358d  mov     r8, r15
0x180013590  mov     rcx, rax
0x180013593  mov     edx, edi
0x180013595  lea     rax, [rsp+120h+var_F0]
0x18001359a  mov     [rsp+120h+var_100], rax
0x18001359f  call    cs:__imp_ForwardGadgetMessage
0x1800135a5  test    eax, eax
0x1800135a7  jz      loc_180013521
0x1800135ad  jmp     loc_1800137C2
0x1800135b2  mov     ecx, 11h; nVirtKey
0x1800135b7  call    cs:__imp_GetKeyState
0x1800135bd  test    ax, ax
0x1800135c0  js      loc_180013521
0x1800135c6  mov     ecx, 12h; nVirtKey
0x1800135cb  call    cs:__imp_GetKeyState
0x1800135d1  test    ax, ax
0x1800135d4  js      loc_180013521
0x1800135da  cmp     edi, 102h
0x1800135e0  jnz     loc_180013521
0x1800135e6  xor     r9d, r9d; lParam
0x1800135e9  xor     r8d, r8d; wParam
0x1800135ec  mov     edx, 121Bh; Msg
0x1800135f1  mov     rcx, rsi; hWnd
0x1800135f4  call    cs:__imp_SendMessageW
0x1800135fa  test    eax, eax
0x1800135fc  jnz     loc_180013521
0x180013602  lea     r9, [rbp+47h+lParam]; lParam
0x180013606  xor     r8d, r8d; wParam
0x180013609  mov     edx, 120Bh; Msg
0x18001360e  mov     rcx, rsi; hWnd
0x180013611  call    cs:__imp_SendMessageW
0x180013617  test    eax, eax
0x180013619  jz      loc_180013521
0x18001361f  mov     rcx, [rbp+47h+dwRefData]
0x180013623  lea     rdx, [rsp+120h+var_F0]
0x180013628  lea     rax, [rbp+47h+lParam]
0x18001362c  mov     [rsp+120h+var_100], rdx
0x180013631  mov     qword ptr [rsp+120h+var_D0+8], rax
0x180013636  lea     r9, [rsp+120h+var_E8]
0x18001363b  xor     r8d, r8d
0x18001363e  mov     [rsp+120h+var_E8], rsi
0x180013643  mov     rax, [rcx]
0x180013646  mov     edx, 4Eh ; 'N'
0x18001364b  mov     dword ptr [rsp+120h+var_E0+8], 0FFFFFEC4h
0x180013653  mov     dword ptr [rsp+120h+var_D0], ebx
0x180013657  mov     rax, [rax+170h]
0x18001365e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013663  jmp     loc_1800137C2
0x180013668  mov     ecx, 11h; nVirtKey
0x18001366d  call    cs:__imp_GetKeyState
0x180013673  test    ax, ax
0x180013676  js      loc_180013521
0x18001367c  mov     ecx, 12h; nVirtKey
0x180013681  call    cs:__imp_GetKeyState
0x180013687  test    ax, ax
0x18001368a  js      loc_180013521
0x180013690  cmp     edi, 102h
0x180013696  jnz     loc_180013521
0x18001369c  mov     rbx, [rbp+47h+dwRefData]
0x1800136a0  mov     rcx, rbx
0x1800136a3  mov     rax, [rbx]
0x1800136a6  mov     rax, [rax+168h]
0x1800136ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800136b2  xor     r9d, r9d; lParam
0x1800136b5  mov     [rbp+47h+var_C0], rax
0x1800136b9  xor     r8d, r8d; wParam
0x1800136bc  mov     dword ptr [rbp+47h+var_B8+8], 0FFFFFF94h
0x1800136c3  mov     edx, 121Bh; Msg
0x1800136c8  mov     dword ptr [rbp+47h+var_A8], 0FFFFFFFFh
0x1800136cf  mov     rcx, rsi; hWnd
0x1800136d2  call    cs:__imp_SendMessageW
0x1800136d8  mov     dword ptr [rbp+47h+var_A8+4], eax
0x1800136db  lea     rcx, [rsp+120h+var_F0]
0x1800136e0  mov     rax, [rbx]
0x1800136e3  xor     r8d, r8d
0x1800136e6  mov     [rsp+120h+var_100], rcx
0x1800136eb  lea     r9, [rbp+47h+var_C0]
0x1800136ef  mov     edx, 4Eh ; 'N'
0x1800136f4  mov     rcx, rbx
0x1800136f7  mov     rax, [rax+170h]
0x1800136fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013703  jmp     loc_1800137C2
0x180013708  mov     ecx, 10h; nVirtKey
0x18001370d  call    cs:__imp_GetKeyState
0x180013713  test    ax, ax
0x180013716  js      loc_18001356B
0x18001371c  mov     ecx, 11h; nVirtKey
0x180013721  call    cs:__imp_GetKeyState
0x180013727  test    ax, ax
0x18001372a  js      loc_18001356B
0x180013730  mov     ecx, 12h; nVirtKey
0x180013735  call    cs:__imp_GetKeyState
0x18001373b  test    ax, ax
0x18001373e  js      loc_18001356B
0x180013744  cmp     edi, 102h
0x18001374a  jnz     short loc_1800137C2
0x18001374c  mov     rcx, [rbp+47h+dwRefData]
0x180013750  mov     rax, [rcx]
0x180013753  mov     rax, [rax+168h]
0x18001375a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001375f  mov     rcx, rax; hWnd
0x180013762  call    cs:__imp_SetFocus
0x180013768  jmp     short loc_1800137C2
0x18001376a  mov     eax, [r9+10h]
0x18001376e  cmp     eax, 0FFFFFDEEh
0x180013773  jz      short loc_180013791
0x180013775  cmp     eax, 0FFFFFDF7h
0x18001377a  jnz     loc_180013521
0x180013780  mov     rcx, [rbp+47h+dwRefData]; this
0x180013784  xor     r8d, r8d; struct tagNMTTDISPINFOW *
0x180013787  mov     rdx, rsi; HWND
0x18001378a  call    ?OnTooltipNotify@WdcListView@@QEAAJPEAUHWND__@@PEAUtagNMTTDISPINFOW@@@Z; WdcListView::OnTooltipNotify(HWND__ *,tagNMTTDISPINFOW *)
0x18001378f  jmp     short loc_1800137C2
0x180013791  mov     rcx, [rbp+47h+dwRefData]; this
0x180013795  mov     r8, r14; struct tagNMTTDISPINFOW *
0x180013798  mov     rdx, rsi; HWND
0x18001379b  call    ?OnTooltipNotify@WdcListView@@QEAAJPEAUHWND__@@PEAUtagNMTTDISPINFOW@@@Z; WdcListView::OnTooltipNotify(HWND__ *,tagNMTTDISPINFOW *)
0x1800137a0  test    eax, eax
0x1800137a2  js      loc_180013521
0x1800137a8  mov     eax, 1
0x1800137ad  jmp     loc_180013532
0x1800137b2  xor     r8d, r8d; uIdSubclass
0x1800137b5  lea     rdx, ?WdcListViewHeaderProc@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x1800137bc  call    cs:__imp_RemoveWindowSubclass
0x1800137c2  xor     eax, eax
0x1800137c4  jmp     loc_180013532
```

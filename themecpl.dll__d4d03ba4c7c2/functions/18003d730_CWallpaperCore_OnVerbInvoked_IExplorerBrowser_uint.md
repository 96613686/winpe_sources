# CWallpaperCore::OnVerbInvoked(IExplorerBrowser *,uint)

- ea: `0x18003d730`
- end: `0x18003dad3`
- name: `?OnVerbInvoked@CWallpaperCore@@UEAAJPEAUIExplorerBrowser@@I@Z`
- size: `931`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, struct IExplorerBrowser *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18003d730`
- `0x18003fba8`
- `0x18003fe5c`
- `0x180042204`
- `0x180042808`
- `0x18004289c`
- `0x180043094`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d96e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d96e`
- `ntdll!WinSqmSetDWORD` at `0x18003daaa`
- `ntdll!WinSqmSetDWORD` at `0x18003daaa`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003d94d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003da4e`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003d94d`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003da4e`
- `DUI70!StrToID` at `0x18003d93b`
- `DUI70!StrToID` at `0x18003da3c`
- `DUI70!StrToID` at `0x18003d93b`
- `DUI70!StrToID` at `0x18003da3c`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003d95e`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003da5f`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003d95e`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003da5f`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::OnVerbInvoked(DirectUI::Element **this, struct IExplorerBrowser *a2, int a3)
{
  struct IExplorerBrowserVtbl *lpVtbl; // rax
  CWallpaperCore *v7; // rcx
  int v8; // edi
  DirectUI::Element *v9; // rcx
  DirectUI::Element *v10; // rbx
  unsigned __int16 v11; // ax
  DirectUI::Element *v12; // rax
  LPVOID v13; // rcx
  int v14; // eax
  DirectUI::Element *v15; // rbx
  unsigned __int16 v16; // ax
  DirectUI::Element *Descendent; // rax
  int v19; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h] BYREF
  __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-18h] BYREF
  void *v23; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v24; // [rsp+88h] [rbp+28h] BYREF
  int v25; // [rsp+98h] [rbp+38h] BYREF

  CWallpaperCore::_PrepareForChange((CWallpaperCore *)this);
  lpVtbl = a2->lpVtbl;
  v20 = 0;
  v8 = ((__int64 (__fastcall *)(struct IExplorerBrowser *, GUID *, __int64 *))lpVtbl->GetCurrentView)(
         a2,
         &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
         &v20);
  if ( v8 < 0 )
    goto LABEL_34;
  v19 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v20 + 56LL))(v20, 2, &v19);
  if ( v8 >= 0 )
  {
    v21 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v20 + 64LL))(
           v20,
           2147483649LL,
           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
           &v21);
    if ( v8 >= 0 )
    {
      v24 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 56LL))(v21, &v24);
      if ( v8 >= 0 )
      {
        if ( v24 != 1 )
        {
          if ( v24 <= 1 )
            goto LABEL_31;
          pv = 0;
          v25 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v20 + 56LL))(v20, 2, &v25);
          if ( v8 < 0 )
            goto LABEL_31;
          v14 = v24 == v25
              ? (*(__int64 (__fastcall **)(__int64, GUID *, LPVOID *))(*(_QWORD *)v20 + 40LL))(
                  v20,
                  &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                  &pv)
              : (**(unsigned __int64 (__fastcall ***)(__int64, GUID *, LPVOID *))v21)(
                  v21,
                  &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                  &pv);
          v8 = v14;
          if ( v14 < 0 )
            goto LABEL_31;
          v8 = (*(__int64 (__fastcall **)(DirectUI::Element *, LPVOID))(*(_QWORD *)this[52] + 96LL))(this[52], pv);
          if ( v8 >= 0 )
          {
            v8 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 1, 0);
            if ( v8 >= 0 )
            {
              *((_BYTE *)this + 185) = 0;
              CWallpaperCore::_SetClearAllEnabled((CWallpaperCore *)this, 1);
              v15 = this[4];
              v16 = StrToID(L"Button_OK");
              Descendent = DirectUI::Element::FindDescendent(v15, v16);
              DirectUI::Element::SetEnabled(Descendent, 1);
            }
          }
          v13 = pv;
          goto LABEL_30;
        }
        v23 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v21 + 64LL))(v21, 0, &v23);
        if ( v8 >= 0 )
        {
          pv = 0;
          v8 = (*(__int64 (__fastcall **)(void *, __int64, LPVOID *))(*(_QWORD *)v23 + 40LL))(v23, 2147647488LL, &pv);
          if ( v8 >= 0 )
          {
            v9 = this[52];
            if ( a3 )
            {
              v25 = 0;
              if ( (*(int (__fastcall **)(DirectUI::Element *, int *))(*(_QWORD *)v9 + 88LL))(v9, &v25) >= 0
                && ((v25 - 1) & 0xFFFFFFFB) == 0 )
              {
                CWallpaperCore::_OnChangePosition((__int64)this, 4);
              }
              v8 = (*(__int64 (__fastcall **)(DirectUI::Element *, DirectUI::Element *, LPVOID))(*(_QWORD *)this[52]
                                                                                               + 24LL))(
                     this[52],
                     this[(unsigned int)(a3 - 1) + 28],
                     pv);
              if ( v8 >= 0 )
              {
                v8 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 0, 0);
                if ( v8 >= 0 )
                {
                  CWallpaperCore::_EnterStaticImageMode((CWallpaperCore *)this);
                  v10 = this[4];
                  v11 = StrToID(L"Button_OK");
                  v12 = DirectUI::Element::FindDescendent(v10, v11);
                  DirectUI::Element::SetEnabled(v12, 1);
                }
              }
            }
            else
            {
              v8 = (*(__int64 (__fastcall **)(DirectUI::Element *, _QWORD, LPVOID))(*(_QWORD *)v9 + 24LL))(v9, 0, pv);
              if ( v8 >= 0 )
              {
                v8 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 0, 0);
                if ( v8 >= 0 )
                {
                  *((_BYTE *)this + 185) = 0;
                  CWallpaperCore::_SetClearAllEnabled((CWallpaperCore *)this, 1);
                }
              }
            }
            CoTaskMemFree(pv);
          }
          v13 = v23;
LABEL_30:
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
LABEL_31:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v8 >= 0 )
    WinSqmSetDWORD(0, 7476, 3);
LABEL_34:
  CWallpaperCore::_PostChange(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003d730  mov     [rsp-18h+arg_0], rbx
0x18003d735  mov     [rsp-18h+arg_10], rsi
0x18003d73a  push    rbp
0x18003d73b  push    rdi
0x18003d73c  push    r14
0x18003d73e  mov     rbp, rsp
0x18003d741  sub     rsp, 60h
0x18003d745  mov     r14d, r8d
0x18003d748  mov     rbx, rdx
0x18003d74b  mov     rsi, rcx
0x18003d74e  call    ?_PrepareForChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PrepareForChange(void)
0x18003d753  mov     rax, [rbx]
0x18003d756  lea     r8, [rbp+var_28]
0x18003d75a  lea     rdx, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9
0x18003d761  mov     [rbp+var_28], 0
0x18003d769  mov     rcx, rbx
0x18003d76c  mov     rax, [rax+88h]
0x18003d773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d778  mov     edi, eax
0x18003d77a  test    eax, eax
0x18003d77c  js      loc_18003DAB6
0x18003d782  mov     rcx, [rbp+var_28]
0x18003d786  lea     r8, [rbp+var_30]
0x18003d78a  mov     [rbp+var_30], 0
0x18003d791  mov     edx, 2
0x18003d796  mov     rax, [rcx]
0x18003d799  mov     rax, [rax+38h]
0x18003d79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7a2  mov     edi, eax
0x18003d7a4  test    eax, eax
0x18003d7a6  js      loc_18003DA8B
0x18003d7ac  mov     rcx, [rbp+var_28]
0x18003d7b0  lea     rbx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18003d7b7  mov     [rbp+var_20], 0
0x18003d7bf  lea     r9, [rbp+var_20]
0x18003d7c3  mov     r8, rbx
0x18003d7c6  mov     edx, 80000001h
0x18003d7cb  mov     rax, [rcx]
0x18003d7ce  mov     rax, [rax+40h]
0x18003d7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7d7  mov     edi, eax
0x18003d7d9  test    eax, eax
0x18003d7db  js      loc_18003DA8B
0x18003d7e1  mov     rcx, [rbp+var_20]
0x18003d7e5  lea     rdx, [rbp+arg_8]
0x18003d7e9  mov     [rbp+arg_8], 0
0x18003d7f0  mov     rax, [rcx]
0x18003d7f3  mov     rax, [rax+38h]
0x18003d7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7fc  mov     edi, eax
0x18003d7fe  test    eax, eax
0x18003d800  js      loc_18003DA7B
0x18003d806  cmp     [rbp+arg_8], 1
0x18003d80a  jnz     loc_18003D983
0x18003d810  mov     rcx, [rbp+var_20]
0x18003d814  lea     r8, [rbp+var_10]
0x18003d818  mov     [rbp+var_10], 0
0x18003d820  xor     edx, edx
0x18003d822  mov     rax, [rcx]
0x18003d825  mov     rax, [rax+40h]
0x18003d829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d82e  mov     edi, eax
0x18003d830  test    eax, eax
0x18003d832  js      loc_18003DA7B
0x18003d838  mov     rcx, [rbp+var_10]
0x18003d83c  lea     r8, [rbp+pv]
0x18003d840  mov     [rbp+pv], 0
0x18003d848  mov     edx, 80028000h
0x18003d84d  mov     rax, [rcx]
0x18003d850  mov     rax, [rax+28h]
0x18003d854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d859  mov     edi, eax
0x18003d85b  test    eax, eax
0x18003d85d  js      loc_18003D97A
0x18003d863  mov     rcx, [rsi+1A0h]
0x18003d86a  test    r14d, r14d
0x18003d86d  jnz     short loc_18003D8B8
0x18003d86f  mov     rax, [rcx]
0x18003d872  xor     edx, edx
0x18003d874  mov     r8, [rbp+pv]
0x18003d878  mov     rax, [rax+18h]
0x18003d87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d881  mov     edi, eax
0x18003d883  test    eax, eax
0x18003d885  js      loc_18003D96A
0x18003d88b  xor     r8d, r8d; bool
0x18003d88e  xor     edx, edx; bool
0x18003d890  mov     rcx, rsi; this
0x18003d893  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003d898  mov     edi, eax
0x18003d89a  test    eax, eax
0x18003d89c  js      loc_18003D96A
0x18003d8a2  mov     dl, 1; bool
0x18003d8a4  mov     [rsi+0B9h], r14b
0x18003d8ab  mov     rcx, rsi; this
0x18003d8ae  call    ?_SetClearAllEnabled@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetClearAllEnabled(bool)
0x18003d8b3  jmp     loc_18003D96A
0x18003d8b8  mov     [rbp+arg_18], 0
0x18003d8bf  lea     rdx, [rbp+arg_18]
0x18003d8c3  mov     rax, [rcx]
0x18003d8c6  mov     rax, [rax+58h]
0x18003d8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8cf  test    eax, eax
0x18003d8d1  js      short loc_18003D8EC
0x18003d8d3  mov     eax, [rbp+arg_18]
0x18003d8d6  dec     eax
0x18003d8d8  test    eax, 0FFFFFFFBh
0x18003d8dd  jnz     short loc_18003D8EC
0x18003d8df  mov     edx, 4
0x18003d8e4  mov     rcx, rsi
0x18003d8e7  call    ?_OnChangePosition@CWallpaperCore@@AEAAXW4DESKTOP_WALLPAPER_POSITION@@@Z; CWallpaperCore::_OnChangePosition(DESKTOP_WALLPAPER_POSITION)
0x18003d8ec  mov     rcx, [rsi+1A0h]
0x18003d8f3  lea     edx, [r14-1]
0x18003d8f7  mov     rdx, [rsi+rdx*8+0E0h]
0x18003d8ff  mov     r8, [rcx]
0x18003d902  mov     rax, [r8+18h]
0x18003d906  mov     r8, [rbp+pv]
0x18003d90a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d90f  mov     edi, eax
0x18003d911  test    eax, eax
0x18003d913  js      short loc_18003D96A
0x18003d915  xor     r8d, r8d; bool
0x18003d918  xor     edx, edx; bool
0x18003d91a  mov     rcx, rsi; this
0x18003d91d  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003d922  mov     edi, eax
0x18003d924  test    eax, eax
0x18003d926  js      short loc_18003D96A
0x18003d928  mov     rcx, rsi; this
0x18003d92b  call    ?_EnterStaticImageMode@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_EnterStaticImageMode(void)
0x18003d930  mov     rbx, [rsi+20h]
0x18003d934  lea     rcx, aButtonOk; "Button_OK"
0x18003d93b  call    cs:__imp_StrToID
0x18003d942  nop     dword ptr [rax+rax+00h]
0x18003d947  movzx   edx, ax
0x18003d94a  mov     rcx, rbx
0x18003d94d  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003d954  nop     dword ptr [rax+rax+00h]
0x18003d959  mov     rcx, rax
0x18003d95c  mov     dl, 1
0x18003d95e  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003d965  nop     dword ptr [rax+rax+00h]
0x18003d96a  mov     rcx, [rbp+pv]; pv
0x18003d96e  call    cs:__imp_CoTaskMemFree
0x18003d975  nop     dword ptr [rax+rax+00h]
0x18003d97a  mov     rcx, [rbp+var_10]
0x18003d97e  jmp     loc_18003DA6F
0x18003d983  jbe     loc_18003DA7B
0x18003d989  mov     rcx, [rbp+var_28]
0x18003d98d  lea     r8, [rbp+arg_18]
0x18003d991  mov     [rbp+pv], 0
0x18003d999  mov     edx, 2
0x18003d99e  mov     [rbp+arg_18], 0
0x18003d9a5  mov     rax, [rcx]
0x18003d9a8  mov     rax, [rax+38h]
0x18003d9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9b1  mov     edi, eax
0x18003d9b3  test    eax, eax
0x18003d9b5  js      loc_18003DA7B
0x18003d9bb  mov     eax, [rbp+arg_18]
0x18003d9be  lea     r8, [rbp+pv]
0x18003d9c2  mov     rdx, rbx
0x18003d9c5  cmp     [rbp+arg_8], eax
0x18003d9c8  jnz     short loc_18003D9D7
0x18003d9ca  mov     rcx, [rbp+var_28]
0x18003d9ce  mov     rax, [rcx]
0x18003d9d1  mov     rax, [rax+28h]
0x18003d9d5  jmp     short loc_18003D9E1
0x18003d9d7  mov     rcx, [rbp+var_20]
0x18003d9db  mov     rax, [rcx]
0x18003d9de  mov     rax, [rax]
0x18003d9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9e6  mov     edi, eax
0x18003d9e8  test    eax, eax
0x18003d9ea  js      loc_18003DA7B
0x18003d9f0  mov     rcx, [rsi+1A0h]
0x18003d9f7  mov     rdx, [rbp+pv]
0x18003d9fb  mov     rax, [rcx]
0x18003d9fe  mov     rax, [rax+60h]
0x18003da02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da07  mov     edi, eax
0x18003da09  test    eax, eax
0x18003da0b  js      short loc_18003DA6B
0x18003da0d  xor     r8d, r8d; bool
0x18003da10  mov     dl, 1; bool
0x18003da12  mov     rcx, rsi; this
0x18003da15  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003da1a  mov     edi, eax
0x18003da1c  test    eax, eax
0x18003da1e  js      short loc_18003DA6B
0x18003da20  mov     dl, 1; bool
0x18003da22  mov     byte ptr [rsi+0B9h], 0
0x18003da29  mov     rcx, rsi; this
0x18003da2c  call    ?_SetClearAllEnabled@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetClearAllEnabled(bool)
0x18003da31  mov     rbx, [rsi+20h]
0x18003da35  lea     rcx, aButtonOk; "Button_OK"
0x18003da3c  call    cs:__imp_StrToID
0x18003da43  nop     dword ptr [rax+rax+00h]
0x18003da48  movzx   edx, ax
0x18003da4b  mov     rcx, rbx
0x18003da4e  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003da55  nop     dword ptr [rax+rax+00h]
0x18003da5a  mov     rcx, rax
0x18003da5d  mov     dl, 1
0x18003da5f  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003da66  nop     dword ptr [rax+rax+00h]
0x18003da6b  mov     rcx, [rbp+pv]
0x18003da6f  mov     rax, [rcx]
0x18003da72  mov     rax, [rax+10h]
0x18003da76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da7b  mov     rcx, [rbp+var_20]
0x18003da7f  mov     rax, [rcx]
0x18003da82  mov     rax, [rax+10h]
0x18003da86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da8b  mov     rcx, [rbp+var_28]
0x18003da8f  mov     rax, [rcx]
0x18003da92  mov     rax, [rax+10h]
0x18003da96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da9b  test    edi, edi
0x18003da9d  js      short loc_18003DAB6
0x18003da9f  xor     ecx, ecx
0x18003daa1  mov     edx, 1D34h
0x18003daa6  lea     r8d, [rcx+3]
0x18003daaa  call    cs:__imp_WinSqmSetDWORD
0x18003dab1  nop     dword ptr [rax+rax+00h]
0x18003dab6  call    ?_PostChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PostChange(void)
0x18003dabb  lea     r11, [rsp+60h+var_s0]
0x18003dac0  mov     eax, edi
0x18003dac2  mov     rbx, [r11+20h]
0x18003dac6  mov     rsi, [r11+30h]
0x18003daca  mov     rsp, r11
0x18003dacd  pop     r14
0x18003dacf  pop     rdi
0x18003dad0  pop     rbp
0x18003dad1  retn
```

# CGallery::OnEvent(DirectUI::Event *)

- ea: `0x180020424`
- end: `0x1800207bd`
- name: `?OnEvent@CGallery@@QEAAXPEAUEvent@DirectUI@@@Z`
- size: `921`
- prototype: `void __fastcall(CGallery *__hidden this, struct DirectUI::Event *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180036314`

## callees

- `0x180002280`
- `0x18000af30`
- `0x180020424`
- `0x180021f4c`
- `0x18004ef88`
- `0x18004f064`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002056d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002056d`
- `USER32!TrackPopupMenu` at `0x180020755`
- `USER32!TrackPopupMenu` at `0x180020755`
- `USER32!GetSystemMetrics` at `0x1800206fe`
- `USER32!GetSystemMetrics` at `0x18002071b`
- `USER32!GetSystemMetrics` at `0x1800206fe`
- `USER32!GetSystemMetrics` at `0x18002071b`
- `USER32!UpdateWindow` at `0x1800205c8`
- `USER32!UpdateWindow` at `0x1800205c8`
- `USER32!DestroyMenu` at `0x18002078b`
- `USER32!DestroyMenu` at `0x18002078b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020592`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180020592`
- `DUI70!StrToID` at `0x180020580`
- `DUI70!StrToID` at `0x180020580`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x180020477`
- `DUI70!?Click@Button@DirectUI@@SA?AVUID@@XZ` at `0x180020477`
- `DUI70!?Context@Button@DirectUI@@SA?AVUID@@XZ` at `0x1800205f9`
- `DUI70!?Context@Button@DirectUI@@SA?AVUID@@XZ` at `0x1800205f9`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002055e`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800205ad`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x18002055e`
- `DUI70!?SetClass@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800205ad`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800206a0`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x1800206a0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800206c5`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800206c5`

## pseudocode

```c
void __fastcall CGallery::OnEvent(CGallery *this, struct DirectUI::Element **a2)
{
  char v4; // r14
  unsigned int v5; // esi
  struct _DPA *v6; // rcx
  int v7; // eax
  struct DirectUI::Element *Ptr; // r12
  __int64 v9; // rcx
  __int64 v10; // r8
  struct DirectUI::Element *v11; // rcx
  DirectUI::Element *v12; // r14
  const unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // r15
  unsigned __int16 v15; // ax
  DirectUI::Element *Descendent; // rax
  __int64 v17; // rcx
  unsigned int i; // esi
  struct _DPA *v19; // rcx
  int v20; // eax
  HMENU v21; // r14
  struct DirectUI::Element *v22; // rcx
  int v23; // ecx
  DirectUI::Element *v24; // rcx
  const struct tagSIZE *Extent; // rax
  HWND v26; // r15
  UINT v27; // edx
  unsigned int v28; // eax
  HWND hWnd; // [rsp+40h] [rbp-30h] BYREF
  struct DirectUI::Value *v30; // [rsp+48h] [rbp-28h] BYREF
  HWND v31[2]; // [rsp+50h] [rbp-20h] BYREF

  if ( !*((_BYTE *)this + 40)
    && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1)) )
  {
    if ( a2[1] == *(struct DirectUI::Element **)DirectUI::Button::Click(v31) )
    {
      v4 = 0;
      v5 = 0;
      do
      {
        v6 = (struct _DPA *)*((_QWORD *)this + 4);
        v7 = v6 ? *(_DWORD *)v6 : 0;
        if ( (int)v5 >= v7 )
          break;
        Ptr = (struct DirectUI::Element *)DPA_GetPtr(v6, (int)v5);
        if ( Ptr == *a2 )
        {
          v4 = 1;
          if ( v5 != *((_DWORD *)this + 6)
            && !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 64LL))(
                  *((_QWORD *)this + 1),
                  v5) )
          {
            if ( (Microsoft_Windows_ThemeCPLEnableBits & 8) != 0 )
              McGenEventWrite_EventWriteTransfer(v9, Personalization_ThemeSwitch_Start, v10, 1, v31);
            v11 = *a2;
            hWnd = 0;
            if ( (int)DUI_GetElementRootHWND(v11, &hWnd) >= 0 )
            {
              v12 = (DirectUI::Element *)DPA_GetPtr(*((HDPA *)this + 4), *((int *)this + 6));
              if ( v12 )
              {
                v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1)
                                                                                           + 8LL))(
                                                  *((_QWORD *)this + 1),
                                                  4);
                v14 = (unsigned __int16 *)v13;
                if ( v13 )
                {
                  DirectUI::Element::SetClass(v12, v13);
                  CoTaskMemFree(v14);
                  v15 = StrToID(L"Name");
                  Descendent = DirectUI::Element::FindDescendent(v12, v15);
                  if ( Descendent )
                    DirectUI::Element::SetClass(Descendent, &cchOriginalDestLength);
                }
              }
              CGallery::_UpdateSelectedItemStatus(this, Ptr);
              UpdateWindow(hWnd);
              v17 = *((_QWORD *)this + 1);
              *((_DWORD *)this + 7) = v5;
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 136LL))(v17, v5);
              *((_BYTE *)a2 + 16) = 1;
              return;
            }
          }
        }
        ++v5;
      }
      while ( !v4 );
    }
    else if ( a2[1] == *(struct DirectUI::Element **)DirectUI::Button::Context(v31) )
    {
      for ( i = 0; ; ++i )
      {
        v19 = (struct _DPA *)*((_QWORD *)this + 4);
        v20 = v19 ? *(_DWORD *)v19 : 0;
        if ( (int)i >= v20 )
          break;
        if ( DPA_GetPtr(v19, (int)i) == *a2 )
        {
          v21 = (HMENU)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 112LL))(
                         *((_QWORD *)this + 1),
                         i);
          if ( v21 )
          {
            v22 = *a2;
            v31[0] = 0;
            if ( (int)DUI_GetElementRootHWND(v22, v31) >= 0 )
            {
              v23 = *((_DWORD *)a2 + 10);
              LODWORD(hWnd) = *((_DWORD *)a2 + 9);
              HIDWORD(hWnd) = v23;
              if ( (int)hWnd <= 0 )
              {
                v24 = *a2;
                v30 = 0;
                hWnd = (HWND)0x500000005LL;
                Extent = DirectUI::Element::GetExtent(v24, &v30);
                if ( Extent )
                  HIDWORD(hWnd) = Extent->cy / 2;
                if ( v30 )
                  DirectUI::Value::Release(v30);
              }
              if ( (int)DUI_GetMouseEventAbsolutePos(*a2, (const struct tagPOINT *)&hWnd, (struct tagPOINT *)&hWnd) >= 0 )
              {
                v26 = v31[0];
                v27 = (*((_BYTE *)*a2 + 152) & 0x40) != 0
                    ? (GetSystemMetrics(40) == 0 ? 8 : 0) | 0x8182
                    : GetSystemMetrics(40) != 0
                    ? 394
                    : 386;
                v28 = TrackPopupMenu(v21, v27, (int)hWnd, SHIDWORD(hWnd), 0, v26, 0);
                if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
                       *((_QWORD *)this + 1),
                       i,
                       v28,
                       *((_QWORD *)this + 8)) >= 0 )
                  *((_BYTE *)a2 + 16) = 1;
              }
            }
            DestroyMenu(v21);
          }
          return;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180020424  mov     [rsp-28h+arg_10], rbx
0x180020429  mov     [rsp-28h+arg_18], rsi
0x18002042e  push    rbp
0x18002042f  push    rdi
0x180020430  push    r12
0x180020432  push    r14
0x180020434  push    r15
0x180020436  mov     rbp, rsp
0x180020439  sub     rsp, 70h
0x18002043d  mov     rax, cs:__security_cookie
0x180020444  xor     rax, rsp
0x180020447  mov     [rbp+var_10], rax
0x18002044b  cmp     byte ptr [rcx+28h], 0
0x18002044f  mov     rbx, rdx
0x180020452  mov     rdi, rcx
0x180020455  jnz     loc_180020797
0x18002045b  mov     rcx, [rcx+8]
0x18002045f  mov     rax, [rcx]
0x180020462  mov     rax, [rax+20h]
0x180020466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002046b  test    eax, eax
0x18002046d  jz      loc_180020797
0x180020473  lea     rcx, [rbp+var_20]
0x180020477  call    cs:__imp_?Click@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Click(void)
0x18002047e  nop     dword ptr [rax+rax+00h]
0x180020483  mov     rax, [rax]
0x180020486  cmp     [rbx+8], rax
0x18002048a  jnz     loc_1800205F5
0x180020490  xor     r14b, r14b
0x180020493  xor     esi, esi
0x180020495  mov     rcx, [rdi+20h]; hdpa
0x180020499  test    rcx, rcx
0x18002049c  jz      short loc_1800204A2
0x18002049e  mov     eax, [rcx]
0x1800204a0  jmp     short loc_1800204A4
0x1800204a2  xor     eax, eax
0x1800204a4  cmp     esi, eax
0x1800204a6  jge     loc_180020797
0x1800204ac  movsxd  rdx, esi; i
0x1800204af  call    DPA_GetPtr
0x1800204b4  mov     r12, rax
0x1800204b7  cmp     rax, [rbx]
0x1800204ba  jnz     short loc_180020516
0x1800204bc  mov     r14b, 1
0x1800204bf  cmp     esi, [rdi+18h]
0x1800204c2  jz      short loc_180020516
0x1800204c4  mov     rcx, [rdi+8]
0x1800204c8  mov     rdx, [rcx]
0x1800204cb  mov     rax, [rdx+40h]
0x1800204cf  mov     edx, esi
0x1800204d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204d6  test    al, al
0x1800204d8  jnz     short loc_180020516
0x1800204da  test    byte ptr cs:Microsoft_Windows_ThemeCPLEnableBits, 8
0x1800204e1  jz      short loc_1800204FE
0x1800204e3  lea     rax, [rbp+var_20]
0x1800204e7  mov     r9d, 1
0x1800204ed  lea     rdx, Personalization_ThemeSwitch_Start
0x1800204f4  mov     qword ptr [rsp+70h+nReserved], rax
0x1800204f9  call    McGenEventWrite_EventWriteTransfer
0x1800204fe  mov     rcx, [rbx]; struct DirectUI::Element *
0x180020501  lea     rdx, [rbp+hWnd]; HWND *
0x180020505  mov     [rbp+hWnd], 0
0x18002050d  call    ?DUI_GetElementRootHWND@@YAJPEAVElement@DirectUI@@PEAPEAUHWND__@@@Z; DUI_GetElementRootHWND(DirectUI::Element *,HWND__ * *)
0x180020512  test    eax, eax
0x180020514  jns     short loc_180020526
0x180020516  inc     esi
0x180020518  test    r14b, r14b
0x18002051b  jz      loc_180020495
0x180020521  jmp     loc_180020797
0x180020526  movsxd  rdx, dword ptr [rdi+18h]; i
0x18002052a  mov     rcx, [rdi+20h]; hdpa
0x18002052e  call    DPA_GetPtr
0x180020533  mov     r14, rax
0x180020536  test    rax, rax
0x180020539  jz      short loc_1800205B9
0x18002053b  mov     rcx, [rdi+8]
0x18002053f  mov     rdx, [rcx]
0x180020542  mov     rax, [rdx+8]
0x180020546  mov     edx, 4
0x18002054b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020550  mov     r15, rax
0x180020553  test    rax, rax
0x180020556  jz      short loc_1800205B9
0x180020558  mov     rdx, rax
0x18002055b  mov     rcx, r14
0x18002055e  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x180020565  nop     dword ptr [rax+rax+00h]
0x18002056a  mov     rcx, r15; pv
0x18002056d  call    cs:__imp_CoTaskMemFree
0x180020574  nop     dword ptr [rax+rax+00h]
0x180020579  lea     rcx, aName; "Name"
0x180020580  call    cs:__imp_StrToID
0x180020587  nop     dword ptr [rax+rax+00h]
0x18002058c  movzx   edx, ax
0x18002058f  mov     rcx, r14
0x180020592  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180020599  nop     dword ptr [rax+rax+00h]
0x18002059e  test    rax, rax
0x1800205a1  jz      short loc_1800205B9
0x1800205a3  lea     rdx, cchOriginalDestLength
0x1800205aa  mov     rcx, rax
0x1800205ad  call    cs:__imp_?SetClass@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetClass(ushort const *)
0x1800205b4  nop     dword ptr [rax+rax+00h]
0x1800205b9  mov     rdx, r12; struct DirectUI::Element *
0x1800205bc  mov     rcx, rdi; this
0x1800205bf  call    ?_UpdateSelectedItemStatus@CGallery@@AEAAJPEAVElement@DirectUI@@@Z; CGallery::_UpdateSelectedItemStatus(DirectUI::Element *)
0x1800205c4  mov     rcx, [rbp+hWnd]; hWnd
0x1800205c8  call    cs:__imp_UpdateWindow
0x1800205cf  nop     dword ptr [rax+rax+00h]
0x1800205d4  mov     rcx, [rdi+8]
0x1800205d8  mov     edx, esi
0x1800205da  mov     [rdi+1Ch], esi
0x1800205dd  mov     rax, [rcx]
0x1800205e0  mov     rax, [rax+88h]
0x1800205e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205ec  mov     byte ptr [rbx+10h], 1
0x1800205f0  jmp     loc_180020797
0x1800205f5  lea     rcx, [rbp+var_20]
0x1800205f9  call    cs:__imp_?Context@Button@DirectUI@@SA?AVUID@@XZ; DirectUI::Button::Context(void)
0x180020600  nop     dword ptr [rax+rax+00h]
0x180020605  mov     rcx, [rax]
0x180020608  cmp     [rbx+8], rcx
0x18002060c  jnz     loc_180020797
0x180020612  xor     esi, esi
0x180020614  mov     rcx, [rdi+20h]; hdpa
0x180020618  test    rcx, rcx
0x18002061b  jz      short loc_180020621
0x18002061d  mov     eax, [rcx]
0x18002061f  jmp     short loc_180020623
0x180020621  xor     eax, eax
0x180020623  cmp     esi, eax
0x180020625  jge     loc_180020797
0x18002062b  movsxd  rdx, esi; i
0x18002062e  call    DPA_GetPtr
0x180020633  cmp     rax, [rbx]
0x180020636  jz      short loc_18002063C
0x180020638  inc     esi
0x18002063a  jmp     short loc_180020614
0x18002063c  mov     rcx, [rdi+8]
0x180020640  mov     edx, esi
0x180020642  mov     rax, [rcx]
0x180020645  mov     rax, [rax+70h]
0x180020649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002064e  mov     r14, rax
0x180020651  test    rax, rax
0x180020654  jz      loc_180020797
0x18002065a  mov     rcx, [rbx]; struct DirectUI::Element *
0x18002065d  lea     rdx, [rbp+var_20]; HWND *
0x180020661  mov     [rbp+var_20], 0
0x180020669  call    ?DUI_GetElementRootHWND@@YAJPEAVElement@DirectUI@@PEAPEAUHWND__@@@Z; DUI_GetElementRootHWND(DirectUI::Element *,HWND__ * *)
0x18002066e  test    eax, eax
0x180020670  js      loc_180020788
0x180020676  mov     edx, [rbx+24h]
0x180020679  mov     ecx, [rbx+28h]
0x18002067c  mov     dword ptr [rbp+hWnd], edx
0x18002067f  mov     dword ptr [rbp+hWnd+4], ecx
0x180020682  test    edx, edx
0x180020684  jg      short loc_1800206D1
0x180020686  mov     rcx, [rbx]
0x180020689  lea     rdx, [rbp+var_28]
0x18002068d  mov     eax, 5
0x180020692  mov     [rbp+var_28], 0
0x18002069a  mov     dword ptr [rbp+hWnd+4], eax
0x18002069d  mov     dword ptr [rbp+hWnd], eax
0x1800206a0  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x1800206a7  nop     dword ptr [rax+rax+00h]
0x1800206ac  test    rax, rax
0x1800206af  jz      short loc_1800206BC
0x1800206b1  mov     eax, [rax+4]
0x1800206b4  cdq
0x1800206b5  sub     eax, edx
0x1800206b7  sar     eax, 1
0x1800206b9  mov     dword ptr [rbp+hWnd+4], eax
0x1800206bc  mov     rcx, [rbp+var_28]
0x1800206c0  test    rcx, rcx
0x1800206c3  jz      short loc_1800206D1
0x1800206c5  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800206cc  nop     dword ptr [rax+rax+00h]
0x1800206d1  mov     rcx, [rbx]; struct DirectUI::Element *
0x1800206d4  lea     r8, [rbp+hWnd]; struct tagPOINT *
0x1800206d8  lea     rdx, [rbp+hWnd]; struct tagPOINT *
0x1800206dc  call    ?DUI_GetMouseEventAbsolutePos@@YAJPEAVElement@DirectUI@@PEBUtagPOINT@@PEAU3@@Z; DUI_GetMouseEventAbsolutePos(DirectUI::Element *,tagPOINT const *,tagPOINT *)
0x1800206e1  test    eax, eax
0x1800206e3  js      loc_180020788
0x1800206e9  mov     rax, [rbx]
0x1800206ec  mov     ecx, 28h ; '('; nIndex
0x1800206f1  mov     r15, [rbp+var_20]
0x1800206f5  test    byte ptr [rax+98h], 40h
0x1800206fc  jz      short loc_18002071B
0x1800206fe  call    cs:__imp_GetSystemMetrics
0x180020705  nop     dword ptr [rax+rax+00h]
0x18002070a  neg     eax
0x18002070c  sbb     edx, edx
0x18002070e  not     edx
0x180020710  and     edx, 8
0x180020713  or      edx, 8182h
0x180020719  jmp     short loc_180020734
0x18002071b  call    cs:__imp_GetSystemMetrics
0x180020722  nop     dword ptr [rax+rax+00h]
0x180020727  neg     eax
0x180020729  sbb     edx, edx
0x18002072b  and     edx, 8
0x18002072e  add     edx, 182h; uFlags
0x180020734  mov     r9d, dword ptr [rbp+hWnd+4]; y
0x180020738  mov     rcx, r14; hMenu
0x18002073b  mov     r8d, dword ptr [rbp+hWnd]; x
0x18002073f  mov     [rsp+70h+prcRect], 0; prcRect
0x180020748  mov     [rsp+70h+var_48], r15; hWnd
0x18002074d  mov     [rsp+70h+nReserved], 0; nReserved
0x180020755  call    cs:__imp_TrackPopupMenu
0x18002075c  nop     dword ptr [rax+rax+00h]
0x180020761  mov     rcx, [rdi+8]
0x180020765  mov     edx, esi
0x180020767  mov     r9, [rdi+40h]
0x18002076b  mov     r8, [rcx]
0x18002076e  mov     r10, [r8+80h]
0x180020775  mov     r8d, eax
0x180020778  mov     rax, r10
0x18002077b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020780  test    eax, eax
0x180020782  js      short loc_180020788
0x180020784  mov     byte ptr [rbx+10h], 1
0x180020788  mov     rcx, r14; hMenu
0x18002078b  call    cs:__imp_DestroyMenu
0x180020792  nop     dword ptr [rax+rax+00h]
0x180020797  mov     rcx, [rbp+var_10]
0x18002079b  xor     rcx, rsp; StackCookie
0x18002079e  call    __security_check_cookie
0x1800207a3  lea     r11, [rsp+70h+var_s0]
0x1800207a8  mov     rbx, [r11+40h]
0x1800207ac  mov     rsi, [r11+48h]
0x1800207b0  mov     rsp, r11
0x1800207b3  pop     r15
0x1800207b5  pop     r14
0x1800207b7  pop     r12
0x1800207b9  pop     rdi
0x1800207ba  pop     rbp
0x1800207bb  retn
```

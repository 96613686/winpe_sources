# CWallpaperCore::OnFileSelectionChanged(IExplorerBrowser *)

- ea: `0x18003cc80`
- end: `0x18003cf47`
- name: `?OnFileSelectionChanged@CWallpaperCore@@UEAAJPEAUIExplorerBrowser@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this, struct IExplorerBrowser *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18003cc80`
- `0x18003fba8`
- `0x180042808`
- `0x18004289c`
- `0x180043094`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ce36`
- `ntdll!WinSqmSetDWORD` at `0x18003cf06`
- `ntdll!WinSqmSetDWORD` at `0x18003cf06`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003cd1b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18003cd1b`
- `DUI70!StrToID` at `0x18003cd09`
- `DUI70!StrToID` at `0x18003cd09`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003cd3d`
- `DUI70!?SetEnabled@Element@DirectUI@@QEAAJ_N@Z` at `0x18003cd3d`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::OnFileSelectionChanged(
        DirectUI::Element **this,
        struct IExplorerBrowser *a2,
        __int64 a3)
{
  int v3; // edi
  struct IExplorerBrowserVtbl *lpVtbl; // rax
  CWallpaperCore *v7; // rcx
  int v8; // eax
  DirectUI::Element *v9; // rbx
  unsigned __int16 v10; // ax
  DirectUI::Element *Descendent; // rax
  bool v12; // dl
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+38h] [rbp-8h] BYREF
  int v17; // [rsp+60h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF

  v3 = 0;
  if ( !*((_BYTE *)this + 180) )
  {
    CWallpaperCore::_PrepareForChange((CWallpaperCore *)this, (__int64)a2, a3);
    lpVtbl = a2->lpVtbl;
    v15 = 0;
    v3 = ((__int64 (__fastcall *)(struct IExplorerBrowser *, GUID *, __int64 *))lpVtbl->GetCurrentView)(
           a2,
           &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
           &v15);
    if ( v3 < 0 )
    {
LABEL_30:
      CWallpaperCore::_PostChange(v7);
      return (unsigned int)v3;
    }
    v19 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v15 + 64LL))(
           v15,
           2147483649LL,
           &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
           &v19);
    v9 = this[4];
    v3 = v8;
    v10 = StrToID(L"Button_OK");
    Descendent = DirectUI::Element::FindDescendent(v9, v10);
    v12 = v3 >= 0 || *((_BYTE *)this + 185);
    DirectUI::Element::SetEnabled(Descendent, v12);
    if ( v3 == -2147023728 )
    {
      v3 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 0, 1);
LABEL_29:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_30;
    }
    if ( v3 < 0 )
      goto LABEL_29;
    v17 = 0;
    v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 56LL))(v19, &v17);
    if ( v3 >= 0 )
    {
      v16 = 0;
      if ( v17 != 1 )
      {
        LODWORD(pv) = 0;
        v3 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v15 + 56LL))(v15, 2, &pv);
        if ( v3 < 0 )
          goto LABEL_28;
        v13 = v17 == (_DWORD)pv
            ? (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v15 + 40LL))(
                v15,
                &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                &v16)
            : (**(unsigned __int64 (__fastcall ***)(__int64, GUID *, __int64 *))v19)(
                v19,
                &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                &v16);
        v3 = v13;
        if ( v13 < 0 )
          goto LABEL_28;
        v3 = (*(__int64 (__fastcall **)(DirectUI::Element *, __int64))(*(_QWORD *)this[52] + 96LL))(this[52], v16);
        if ( v3 >= 0 )
        {
          v3 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 1, 0);
          if ( v3 >= 0 )
          {
            *((_BYTE *)this + 185) = 0;
            CWallpaperCore::_SetClearAllEnabled((CWallpaperCore *)this, 1);
          }
        }
        goto LABEL_26;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 64LL))(v19, 0, &v16);
      if ( v3 >= 0 )
      {
        pv = 0;
        v3 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v16 + 40LL))(v16, 2147647488LL, &pv);
        if ( v3 >= 0 )
        {
          v3 = (*(__int64 (__fastcall **)(DirectUI::Element *, _QWORD, LPVOID))(*(_QWORD *)this[52] + 24LL))(
                 this[52],
                 0,
                 pv);
          if ( v3 >= 0 )
          {
            v3 = CWallpaperCore::_EnableSlideshow((CWallpaperCore *)this, 0, 0);
            if ( v3 >= 0 )
            {
              *((_BYTE *)this + 185) = 0;
              CWallpaperCore::_SetClearAllEnabled((CWallpaperCore *)this, 1);
            }
          }
          CoTaskMemFree(pv);
        }
LABEL_26:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        if ( v3 >= 0 )
          WinSqmSetDWORD(0, 7476, 1);
      }
    }
LABEL_28:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_29;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003cc80  mov     [rsp-18h+arg_8], rbx
0x18003cc85  push    rbp
0x18003cc86  push    rsi
0x18003cc87  push    rdi
0x18003cc88  mov     rbp, rsp
0x18003cc8b  sub     rsp, 40h
0x18003cc8f  xor     edi, edi
0x18003cc91  mov     rbx, rdx
0x18003cc94  mov     rsi, rcx
0x18003cc97  cmp     [rcx+0B4h], dil
0x18003cc9e  jnz     loc_18003CF37
0x18003cca4  call    ?_PrepareForChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PrepareForChange(void)
0x18003cca9  mov     rax, [rbx]
0x18003ccac  lea     r8, [rbp+var_10]
0x18003ccb0  lea     rdx, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9
0x18003ccb7  mov     [rbp+var_10], rdi
0x18003ccbb  mov     rcx, rbx
0x18003ccbe  mov     rax, [rax+88h]
0x18003ccc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccca  mov     edi, eax
0x18003cccc  test    eax, eax
0x18003ccce  js      loc_18003CF32
0x18003ccd4  mov     rcx, [rbp+var_10]
0x18003ccd8  lea     r9, [rbp+arg_18]
0x18003ccdc  mov     [rbp+arg_18], 0
0x18003cce4  lea     r8, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18003cceb  mov     edx, 80000001h
0x18003ccf0  mov     rax, [rcx]
0x18003ccf3  mov     rax, [rax+40h]
0x18003ccf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccfc  mov     rbx, [rsi+20h]
0x18003cd00  lea     rcx, aButtonOk; "Button_OK"
0x18003cd07  mov     edi, eax
0x18003cd09  call    cs:__imp_StrToID
0x18003cd10  nop     dword ptr [rax+rax+00h]
0x18003cd15  movzx   edx, ax
0x18003cd18  mov     rcx, rbx
0x18003cd1b  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18003cd22  nop     dword ptr [rax+rax+00h]
0x18003cd27  test    edi, edi
0x18003cd29  jns     short loc_18003CD38
0x18003cd2b  cmp     byte ptr [rsi+0B9h], 0
0x18003cd32  jnz     short loc_18003CD38
0x18003cd34  xor     edx, edx
0x18003cd36  jmp     short loc_18003CD3A
0x18003cd38  mov     dl, 1
0x18003cd3a  mov     rcx, rax
0x18003cd3d  call    cs:__imp_?SetEnabled@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetEnabled(bool)
0x18003cd44  nop     dword ptr [rax+rax+00h]
0x18003cd49  cmp     edi, 80070490h
0x18003cd4f  jnz     short loc_18003CD65
0x18003cd51  mov     r8b, 1; bool
0x18003cd54  xor     edx, edx; bool
0x18003cd56  mov     rcx, rsi; this
0x18003cd59  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003cd5e  mov     edi, eax
0x18003cd60  jmp     loc_18003CF22
0x18003cd65  test    edi, edi
0x18003cd67  js      loc_18003CF22
0x18003cd6d  mov     rcx, [rbp+arg_18]
0x18003cd71  lea     rdx, [rbp+arg_0]
0x18003cd75  mov     [rbp+arg_0], 0
0x18003cd7c  mov     rax, [rcx]
0x18003cd7f  mov     rax, [rax+38h]
0x18003cd83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd88  mov     edi, eax
0x18003cd8a  test    eax, eax
0x18003cd8c  js      loc_18003CF12
0x18003cd92  cmp     [rbp+arg_0], 1
0x18003cd96  mov     [rbp+var_8], 0
0x18003cd9e  jnz     loc_18003CE47
0x18003cda4  mov     rcx, [rbp+arg_18]
0x18003cda8  lea     r8, [rbp+var_8]
0x18003cdac  xor     edx, edx
0x18003cdae  mov     rax, [rcx]
0x18003cdb1  mov     rax, [rax+40h]
0x18003cdb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdba  mov     edi, eax
0x18003cdbc  test    eax, eax
0x18003cdbe  js      loc_18003CF12
0x18003cdc4  mov     rcx, [rbp+var_8]
0x18003cdc8  lea     r8, [rbp+pv]
0x18003cdcc  mov     [rbp+pv], 0
0x18003cdd4  mov     edx, 80028000h
0x18003cdd9  mov     rax, [rcx]
0x18003cddc  mov     rax, [rax+28h]
0x18003cde0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cde5  mov     edi, eax
0x18003cde7  test    eax, eax
0x18003cde9  js      loc_18003CEE7
0x18003cdef  mov     rcx, [rsi+1A0h]
0x18003cdf6  xor     edx, edx
0x18003cdf8  mov     r8, [rbp+pv]
0x18003cdfc  mov     rax, [rcx]
0x18003cdff  mov     rax, [rax+18h]
0x18003ce03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce08  mov     edi, eax
0x18003ce0a  test    eax, eax
0x18003ce0c  js      short loc_18003CE32
0x18003ce0e  xor     r8d, r8d; bool
0x18003ce11  xor     edx, edx; bool
0x18003ce13  mov     rcx, rsi; this
0x18003ce16  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003ce1b  mov     edi, eax
0x18003ce1d  test    eax, eax
0x18003ce1f  js      short loc_18003CE32
0x18003ce21  mov     dl, 1; bool
0x18003ce23  mov     byte ptr [rsi+0B9h], 0
0x18003ce2a  mov     rcx, rsi; this
0x18003ce2d  call    ?_SetClearAllEnabled@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetClearAllEnabled(bool)
0x18003ce32  mov     rcx, [rbp+pv]; pv
0x18003ce36  call    cs:__imp_CoTaskMemFree
0x18003ce3d  nop     dword ptr [rax+rax+00h]
0x18003ce42  jmp     loc_18003CEE7
0x18003ce47  mov     rcx, [rbp+var_10]
0x18003ce4b  lea     r8, [rbp+pv]
0x18003ce4f  mov     dword ptr [rbp+pv], 0
0x18003ce56  mov     edx, 2
0x18003ce5b  mov     rax, [rcx]
0x18003ce5e  mov     rax, [rax+38h]
0x18003ce62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce67  mov     edi, eax
0x18003ce69  test    eax, eax
0x18003ce6b  js      loc_18003CF12
0x18003ce71  mov     eax, dword ptr [rbp+pv]
0x18003ce74  lea     r8, [rbp+var_8]
0x18003ce78  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x18003ce7f  cmp     [rbp+arg_0], eax
0x18003ce82  jnz     short loc_18003CE91
0x18003ce84  mov     rcx, [rbp+var_10]
0x18003ce88  mov     rax, [rcx]
0x18003ce8b  mov     rax, [rax+28h]
0x18003ce8f  jmp     short loc_18003CE9B
0x18003ce91  mov     rcx, [rbp+arg_18]
0x18003ce95  mov     rax, [rcx]
0x18003ce98  mov     rax, [rax]
0x18003ce9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cea0  mov     edi, eax
0x18003cea2  test    eax, eax
0x18003cea4  js      short loc_18003CF12
0x18003cea6  mov     rcx, [rsi+1A0h]
0x18003cead  mov     rdx, [rbp+var_8]
0x18003ceb1  mov     rax, [rcx]
0x18003ceb4  mov     rax, [rax+60h]
0x18003ceb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cebd  mov     edi, eax
0x18003cebf  test    eax, eax
0x18003cec1  js      short loc_18003CEE7
0x18003cec3  xor     r8d, r8d; bool
0x18003cec6  mov     dl, 1; bool
0x18003cec8  mov     rcx, rsi; this
0x18003cecb  call    ?_EnableSlideshow@CWallpaperCore@@AEAAJ_N0@Z; CWallpaperCore::_EnableSlideshow(bool,bool)
0x18003ced0  mov     edi, eax
0x18003ced2  test    eax, eax
0x18003ced4  js      short loc_18003CEE7
0x18003ced6  mov     dl, 1; bool
0x18003ced8  mov     byte ptr [rsi+0B9h], 0
0x18003cedf  mov     rcx, rsi; this
0x18003cee2  call    ?_SetClearAllEnabled@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_SetClearAllEnabled(bool)
0x18003cee7  mov     rcx, [rbp+var_8]
0x18003ceeb  mov     rax, [rcx]
0x18003ceee  mov     rax, [rax+10h]
0x18003cef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cef7  test    edi, edi
0x18003cef9  js      short loc_18003CF12
0x18003cefb  xor     ecx, ecx
0x18003cefd  mov     edx, 1D34h
0x18003cf02  lea     r8d, [rcx+1]
0x18003cf06  call    cs:__imp_WinSqmSetDWORD
0x18003cf0d  nop     dword ptr [rax+rax+00h]
0x18003cf12  mov     rcx, [rbp+arg_18]
0x18003cf16  mov     rax, [rcx]
0x18003cf19  mov     rax, [rax+10h]
0x18003cf1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf22  mov     rcx, [rbp+var_10]
0x18003cf26  mov     rax, [rcx]
0x18003cf29  mov     rax, [rax+10h]
0x18003cf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cf32  call    ?_PostChange@CWallpaperCore@@AEAAXXZ; CWallpaperCore::_PostChange(void)
0x18003cf37  mov     rbx, [rsp+40h+arg_8]
0x18003cf3c  mov     eax, edi
0x18003cf3e  add     rsp, 40h
0x18003cf42  pop     rdi
0x18003cf43  pop     rsi
0x18003cf44  pop     rbp
0x18003cf45  retn
```

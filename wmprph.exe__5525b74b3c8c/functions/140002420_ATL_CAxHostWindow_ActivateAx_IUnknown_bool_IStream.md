# ATL::CAxHostWindow::ActivateAx(IUnknown *,bool,IStream *)

- ea: `0x140002420`
- end: `0x1400029c0`
- name: `?ActivateAx@CAxHostWindow@ATL@@QEAAJPEAUIUnknown@@_NPEAUIStream@@@Z`
- size: `1440`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, struct IUnknown *, bool, struct IStream *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002f70`
- `0x140003470`

## callees

- `0x140002420`
- `0x14000f010`

## import_xrefs

- `GDI32!GetDeviceCaps` at `0x140002740`
- `GDI32!GetDeviceCaps` at `0x140002751`
- `GDI32!GetDeviceCaps` at `0x1400027f1`
- `GDI32!GetDeviceCaps` at `0x140002802`
- `GDI32!GetDeviceCaps` at `0x140002740`
- `GDI32!GetDeviceCaps` at `0x140002751`
- `GDI32!GetDeviceCaps` at `0x1400027f1`
- `GDI32!GetDeviceCaps` at `0x140002802`
- `USER32!ReleaseDC` at `0x14000275f`
- `USER32!ReleaseDC` at `0x140002810`
- `USER32!ReleaseDC` at `0x14000275f`
- `USER32!ReleaseDC` at `0x140002810`
- `USER32!RedrawWindow` at `0x140002905`
- `USER32!RedrawWindow` at `0x140002905`
- `USER32!GetDC` at `0x14000272a`
- `USER32!GetDC` at `0x1400027db`
- `USER32!GetDC` at `0x14000272a`
- `USER32!GetDC` at `0x1400027db`
- `USER32!GetClientRect` at `0x140002700`
- `USER32!GetClientRect` at `0x140002700`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::ActivateAx(
        ATL::CAxHostWindow *this,
        struct IUnknown *a2,
        char a3,
        struct IStream *a4)
{
  _QWORD *v8; // rbx
  _QWORD *v9; // rbx
  int v10; // r14d
  void (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rax
  __int64 v12; // r8
  __int64 v13; // rdx
  void (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // r9
  void (__fastcall ***v15)(_QWORD, GUID *, __int64 **); // r9
  __int64 *v16; // rcx
  __int64 v17; // rax
  void (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rax
  __int64 v19; // r8
  __int64 v20; // rdx
  void (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // r9
  int (__fastcall ***v22)(_QWORD, GUID *, char *); // rcx
  _QWORD *v23; // r15
  int v24; // eax
  void (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rax
  __int64 v26; // rdx
  void (__fastcall ***v27)(_QWORD, GUID *, _QWORD *); // r9
  HDC DC; // rax
  HDC v29; // r15
  int DeviceCaps; // r13d
  int v31; // r8d
  HDC v32; // rax
  HDC v33; // r13
  int v34; // r15d
  int v35; // r8d
  int v36; // ecx
  _QWORD *v37; // rax
  void (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // rax
  struct IUnknownVtbl *lpVtbl; // rax
  __int64 v40; // rbx
  void (__fastcall *v41)(__int64, __int64); // rdi
  __int64 v42; // rax
  __int64 v44; // [rsp+40h] [rbp-28h] BYREF
  __int64 v45; // [rsp+48h] [rbp-20h] BYREF
  __int64 *v46; // [rsp+50h] [rbp-18h] BYREF
  __int64 v47; // [rsp+58h] [rbp-10h] BYREF
  __int64 v48; // [rsp+B8h] [rbp+50h] BYREF

  if ( a2 )
  {
    v8 = (_QWORD *)((char *)this + 160);
    if ( this != (ATL::CAxHostWindow *)-160LL )
    {
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
      if ( *v8 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
      *v8 = a2;
    }
    v9 = (_QWORD *)((char *)this + 168);
    ((void (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
      a2,
      &IID_IOleObject,
      (char *)this + 168);
    if ( *((_QWORD *)this + 21) )
    {
      v10 = 1;
      (*(void (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 21) + 176LL))(
        *((_QWORD *)this + 21),
        1,
        (char *)this + 256);
      if ( (*((_DWORD *)this + 64) & 0x20000) != 0 )
      {
        v11 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(ATL::CAxHostWindow *))(*(_QWORD *)this + 24LL))(this);
        v13 = 0;
        v14 = v11;
        v48 = 0;
        if ( v11 )
        {
          (**v11)(v11, &GUID_00000118_0000_0000_c000_000000000046, &v48);
          v13 = v48;
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)*v9 + 24LL))(
          *v9,
          v13,
          v12,
          v14);
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v15 = (void (__fastcall ***)(_QWORD, GUID *, __int64 **))*v9;
      v16 = 0;
      v46 = 0;
      if ( v15 )
      {
        (**v15)(v15, &IID_IPersistStreamInit, &v46);
        v16 = v46;
      }
      if ( !a3 && v16 )
      {
        v17 = *v16;
        if ( a4 )
          (*(void (__fastcall **)(__int64 *, struct IStream *))(v17 + 40))(v16, a4);
        else
          (*(void (**)(void))(v17 + 64))();
      }
      if ( (*((_DWORD *)this + 64) & 0x20000) == 0 )
      {
        v18 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(ATL::CAxHostWindow *))(*(_QWORD *)this + 24LL))(this);
        v20 = 0;
        v21 = v18;
        v48 = 0;
        if ( v18 )
        {
          (**v18)(v18, &GUID_00000118_0000_0000_c000_000000000046, &v48);
          v20 = v48;
        }
        (*(void (__fastcall **)(_QWORD, __int64, __int64, void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)*v9 + 24LL))(
          *v9,
          v20,
          v19,
          v21);
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      }
      v22 = (int (__fastcall ***)(_QWORD, GUID *, char *))*v9;
      v23 = (_QWORD *)((char *)this + 192);
      *((_DWORD *)this + 60) = 0;
      if ( (**v22)(v22, &IID_IViewObjectEx, (char *)this + 192) >= 0 )
      {
        *((_DWORD *)this + 60) = 7;
      }
      else
      {
        v24 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v9)(*v9, &IID_IViewObject2, (char *)this + 192);
        *((_DWORD *)this + 60) = 3;
        if ( v24 < 0 )
        {
          (**(void (__fastcall ***)(_QWORD, GUID *, char *))*v9)(*v9, &IID_IViewObject, (char *)this + 192);
          *((_DWORD *)this + 60) = 1;
        }
      }
      v25 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(ATL::CAxHostWindow *))(*(_QWORD *)this + 24LL))(this);
      v26 = 0;
      v27 = v25;
      v44 = 0;
      if ( v25 )
      {
        (**v25)(v25, &GUID_0000010f_0000_0000_c000_000000000046, &v44);
        v26 = v44;
      }
      (*(void (__fastcall **)(_QWORD, __int64, char *, void (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)*v9 + 152LL))(
        *v9,
        v26,
        (char *)this + 252,
        v27);
      if ( *v23 )
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(*(_QWORD *)*v23 + 56LL))(*v23, 1, 0, v44);
      (*(void (__fastcall **)(_QWORD, const wchar_t *, _QWORD))(*(_QWORD *)*v9 + 40LL))(*v9, L"AXWIN", 0);
      GetClientRect(*((HWND *)this + 1), (LPRECT)((char *)this + 276));
      *((_DWORD *)this + 67) = *((_DWORD *)this + 71) - *((_DWORD *)this + 69);
      *((_DWORD *)this + 68) = *((_DWORD *)this + 72) - *((_DWORD *)this + 70);
      DC = GetDC(0);
      v29 = DC;
      if ( DC )
      {
        DeviceCaps = GetDeviceCaps(DC, 88);
        LODWORD(v48) = GetDeviceCaps(v29, 90);
        ReleaseDC(0, v29);
        v31 = v48;
      }
      else
      {
        v31 = 1;
        DeviceCaps = 1;
      }
      *((_DWORD *)this + 65) = ((DeviceCaps >> 1) + 2540 * *((_DWORD *)this + 67)) / DeviceCaps;
      *((_DWORD *)this + 66) = ((v31 >> 1) + 2540 * *((_DWORD *)this + 68)) / v31;
      (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 136LL))(*v9, 1, (char *)this + 260);
      (*(void (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v9 + 144LL))(*v9, 1, (char *)this + 260);
      v32 = GetDC(0);
      v33 = v32;
      if ( v32 )
      {
        v10 = GetDeviceCaps(v32, 88);
        v34 = GetDeviceCaps(v33, 90);
        ReleaseDC(0, v33);
      }
      else
      {
        v34 = 1;
      }
      v35 = (*((_DWORD *)this + 65) * v10 + 1270) / 2540;
      *((_DWORD *)this + 67) = v35;
      *((_DWORD *)this + 68) = (*((_DWORD *)this + 66) * v34 + 1270) / 2540;
      v36 = *((_DWORD *)this + 69);
      *((_DWORD *)this + 72) = *((_DWORD *)this + 68) + *((_DWORD *)this + 70);
      v37 = *(_QWORD **)this;
      *((_DWORD *)this + 71) = v35 + v36;
      v38 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))((__int64 (__fastcall *)(ATL::CAxHostWindow *))v37[3])(this);
      v45 = 0;
      if ( v38 )
        (**v38)(v38, &GUID_00000118_0000_0000_c000_000000000046, &v45);
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v9 + 88LL))(*v9, 4294967291LL);
      RedrawWindow(*((HWND *)this + 1), 0, 0, 0x507u);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v46 )
        (*(void (__fastcall **)(__int64 *))(*v46 + 16))(v46);
    }
    lpVtbl = a2->lpVtbl;
    v47 = 0;
    ((void (__fastcall *)(struct IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(a2, &IID_IObjectWithSite, &v47);
    v40 = v47;
    if ( v47 )
    {
      v41 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 24LL);
      v42 = (*(__int64 (__fastcall **)(ATL::CAxHostWindow *))(*(_QWORD *)this + 24LL))(this);
      v41(v40, v42);
      if ( v47 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140002420  push    rbp
0x140002422  push    rbx
0x140002423  push    rsi
0x140002424  push    rdi
0x140002425  push    r12
0x140002427  push    r13
0x140002429  push    r14
0x14000242b  push    r15
0x14000242d  mov     rbp, rsp
0x140002430  sub     rsp, 68h
0x140002434  mov     r12, r9
0x140002437  mov     r13b, r8b
0x14000243a  mov     rdi, rdx
0x14000243d  mov     rsi, rcx
0x140002440  test    rdx, rdx
0x140002443  jz      loc_1400029AD
0x140002449  lea     rbx, [rcx+0A0h]
0x140002450  test    rbx, rbx
0x140002453  jz      short loc_14000247B
0x140002455  mov     rax, [rdx]
0x140002458  mov     rcx, rdx
0x14000245b  mov     rax, [rax+8]
0x14000245f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002464  mov     rcx, [rbx]
0x140002467  test    rcx, rcx
0x14000246a  jz      short loc_140002478
0x14000246c  mov     rax, [rcx]
0x14000246f  mov     rax, [rax+10h]
0x140002473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002478  mov     [rbx], rdi
0x14000247b  mov     rax, [rdi]
0x14000247e  lea     rbx, [rsi+0A8h]
0x140002485  mov     r8, rbx
0x140002488  lea     rdx, IID_IOleObject
0x14000248f  mov     rcx, rdi
0x140002492  mov     rax, [rax]
0x140002495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000249a  mov     rcx, [rbx]
0x14000249d  test    rcx, rcx
0x1400024a0  jz      loc_14000294A
0x1400024a6  mov     rax, [rcx]
0x1400024a9  lea     r15, [rsi+100h]
0x1400024b0  mov     r14d, 1
0x1400024b6  mov     r8, r15
0x1400024b9  mov     edx, r14d
0x1400024bc  mov     rax, [rax+0B0h]
0x1400024c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024c8  test    dword ptr [r15], 20000h
0x1400024cf  jz      short loc_14000252F
0x1400024d1  mov     rax, [rsi]
0x1400024d4  mov     rcx, rsi
0x1400024d7  mov     rax, [rax+18h]
0x1400024db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024e0  xor     edx, edx
0x1400024e2  mov     r9, rax
0x1400024e5  mov     [rbp+arg_8], rdx
0x1400024e9  test    rax, rax
0x1400024ec  jz      short loc_14000250B
0x1400024ee  mov     rcx, [rax]
0x1400024f1  lea     r8, [rbp+arg_8]
0x1400024f5  lea     rdx, _GUID_00000118_0000_0000_c000_000000000046
0x1400024fc  mov     rax, [rcx]
0x1400024ff  mov     rcx, r9
0x140002502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002507  mov     rdx, [rbp+arg_8]
0x14000250b  mov     rcx, [rbx]
0x14000250e  mov     rax, [rcx]
0x140002511  mov     rax, [rax+18h]
0x140002515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000251a  mov     rcx, [rbp+arg_8]
0x14000251e  test    rcx, rcx
0x140002521  jz      short loc_14000252F
0x140002523  mov     rax, [rcx]
0x140002526  mov     rax, [rax+10h]
0x14000252a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000252f  mov     r9, [rbx]
0x140002532  xor     ecx, ecx
0x140002534  mov     [rbp+var_18], rcx
0x140002538  test    r9, r9
0x14000253b  jz      short loc_14000255A
0x14000253d  mov     rax, [r9]
0x140002540  lea     r8, [rbp+var_18]
0x140002544  lea     rdx, IID_IPersistStreamInit
0x14000254b  mov     rcx, r9
0x14000254e  mov     rax, [rax]
0x140002551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002556  mov     rcx, [rbp+var_18]
0x14000255a  test    r13b, r13b
0x14000255d  jnz     short loc_140002583
0x14000255f  test    rcx, rcx
0x140002562  jz      short loc_140002583
0x140002564  mov     rax, [rcx]
0x140002567  test    r12, r12
0x14000256a  jz      short loc_14000257A
0x14000256c  mov     rax, [rax+28h]
0x140002570  mov     rdx, r12
0x140002573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002578  jmp     short loc_140002583
0x14000257a  mov     rax, [rax+40h]
0x14000257e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002583  test    dword ptr [r15], 20000h
0x14000258a  jnz     short loc_1400025EA
0x14000258c  mov     rax, [rsi]
0x14000258f  mov     rcx, rsi
0x140002592  mov     rax, [rax+18h]
0x140002596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000259b  xor     edx, edx
0x14000259d  mov     r9, rax
0x1400025a0  mov     [rbp+arg_8], rdx
0x1400025a4  test    rax, rax
0x1400025a7  jz      short loc_1400025C6
0x1400025a9  mov     rcx, [rax]
0x1400025ac  lea     r8, [rbp+arg_8]
0x1400025b0  lea     rdx, _GUID_00000118_0000_0000_c000_000000000046
0x1400025b7  mov     rax, [rcx]
0x1400025ba  mov     rcx, r9
0x1400025bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025c2  mov     rdx, [rbp+arg_8]
0x1400025c6  mov     rcx, [rbx]
0x1400025c9  mov     rax, [rcx]
0x1400025cc  mov     rax, [rax+18h]
0x1400025d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025d5  mov     rcx, [rbp+arg_8]
0x1400025d9  test    rcx, rcx
0x1400025dc  jz      short loc_1400025EA
0x1400025de  mov     rax, [rcx]
0x1400025e1  mov     rax, [rax+10h]
0x1400025e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ea  mov     rcx, [rbx]
0x1400025ed  lea     r15, [rsi+0C0h]
0x1400025f4  mov     dword ptr [rsi+0F0h], 0
0x1400025fe  lea     rdx, IID_IViewObjectEx
0x140002605  mov     r8, r15
0x140002608  mov     rax, [rcx]
0x14000260b  mov     rax, [rax]
0x14000260e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002613  test    eax, eax
0x140002615  jns     short loc_14000265E
0x140002617  mov     rcx, [rbx]
0x14000261a  lea     rdx, IID_IViewObject2
0x140002621  mov     r8, r15
0x140002624  mov     rax, [rcx]
0x140002627  mov     rax, [rax]
0x14000262a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000262f  mov     dword ptr [rsi+0F0h], 3
0x140002639  test    eax, eax
0x14000263b  jns     short loc_140002668
0x14000263d  mov     rcx, [rbx]
0x140002640  lea     rdx, IID_IViewObject
0x140002647  mov     r8, r15
0x14000264a  mov     rax, [rcx]
0x14000264d  mov     rax, [rax]
0x140002650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002655  mov     [rsi+0F0h], r14d
0x14000265c  jmp     short loc_140002668
0x14000265e  mov     dword ptr [rsi+0F0h], 7
0x140002668  mov     rax, [rsi]
0x14000266b  mov     rcx, rsi
0x14000266e  mov     rax, [rax+18h]
0x140002672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002677  xor     edx, edx
0x140002679  mov     r9, rax
0x14000267c  mov     [rbp+var_28], rdx
0x140002680  test    rax, rax
0x140002683  jz      short loc_1400026A2
0x140002685  mov     rcx, [rax]
0x140002688  lea     r8, [rbp+var_28]
0x14000268c  lea     rdx, _GUID_0000010f_0000_0000_c000_000000000046
0x140002693  mov     rax, [rcx]
0x140002696  mov     rcx, r9
0x140002699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000269e  mov     rdx, [rbp+var_28]
0x1400026a2  mov     rcx, [rbx]
0x1400026a5  lea     r8, [rsi+0FCh]
0x1400026ac  mov     rax, [rcx]
0x1400026af  mov     rax, [rax+98h]
0x1400026b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026bb  mov     rcx, [r15]
0x1400026be  test    rcx, rcx
0x1400026c1  jz      short loc_1400026D9
0x1400026c3  mov     rax, [rcx]
0x1400026c6  xor     r8d, r8d
0x1400026c9  mov     r9, [rbp+var_28]
0x1400026cd  mov     edx, r14d
0x1400026d0  mov     rax, [rax+38h]
0x1400026d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026d9  mov     rcx, [rbx]
0x1400026dc  lea     rdx, aAxwin; "AXWIN"
0x1400026e3  xor     r8d, r8d
0x1400026e6  mov     rax, [rcx]
0x1400026e9  mov     rax, [rax+28h]
0x1400026ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026f2  mov     rcx, [rsi+8]; hWnd
0x1400026f6  lea     r12, [rsi+114h]
0x1400026fd  mov     rdx, r12; lpRect
0x140002700  call    cs:__imp_GetClientRect
0x140002706  mov     eax, [rsi+11Ch]
0x14000270c  xor     ecx, ecx; hWnd
0x14000270e  sub     eax, [r12]
0x140002712  mov     [rsi+10Ch], eax
0x140002718  mov     eax, [rsi+120h]
0x14000271e  sub     eax, [rsi+118h]
0x140002724  mov     [rsi+110h], eax
0x14000272a  call    cs:__imp_GetDC
0x140002730  mov     r15, rax
0x140002733  test    rax, rax
0x140002736  jz      short loc_14000276B
0x140002738  mov     edx, 58h ; 'X'; index
0x14000273d  mov     rcx, rax; hdc
0x140002740  call    cs:__imp_GetDeviceCaps
0x140002746  mov     edx, 5Ah ; 'Z'; index
0x14000274b  mov     rcx, r15; hdc
0x14000274e  mov     r13d, eax
0x140002751  call    cs:__imp_GetDeviceCaps
0x140002757  mov     rdx, r15; hDC
0x14000275a  xor     ecx, ecx; hWnd
0x14000275c  mov     dword ptr [rbp+arg_8], eax
0x14000275f  call    cs:__imp_ReleaseDC
0x140002765  mov     r8d, dword ptr [rbp+arg_8]
0x140002769  jmp     short loc_140002771
0x14000276b  mov     r8d, r14d
0x14000276e  mov     r13d, r14d
0x140002771  imul    eax, [rsi+10Ch], 9ECh
0x14000277b  lea     r15, [rsi+104h]
0x140002782  mov     ecx, r13d
0x140002785  sar     ecx, 1
0x140002787  add     eax, ecx
0x140002789  mov     ecx, r8d
0x14000278c  cdq
0x14000278d  sar     ecx, 1
0x14000278f  idiv    r13d
0x140002792  mov     [r15], eax
0x140002795  imul    eax, [rsi+110h], 9ECh
0x14000279f  add     eax, ecx
0x1400027a1  cdq
0x1400027a2  idiv    r8d
0x1400027a5  mov     r8, r15
0x1400027a8  mov     edx, r14d
0x1400027ab  mov     [r15+4], eax
0x1400027af  mov     rcx, [rbx]
0x1400027b2  mov     rax, [rcx]
0x1400027b5  mov     rax, [rax+88h]
0x1400027bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027c1  mov     rcx, [rbx]
0x1400027c4  mov     r8, r15
0x1400027c7  mov     edx, r14d
0x1400027ca  mov     rax, [rcx]
0x1400027cd  mov     rax, [rax+90h]
0x1400027d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027d9  xor     ecx, ecx; hWnd
0x1400027db  call    cs:__imp_GetDC
0x1400027e1  mov     r13, rax
0x1400027e4  test    rax, rax
0x1400027e7  jz      short loc_140002818
0x1400027e9  mov     edx, 58h ; 'X'; index
0x1400027ee  mov     rcx, rax; hdc
0x1400027f1  call    cs:__imp_GetDeviceCaps
0x1400027f7  mov     edx, 5Ah ; 'Z'; index
0x1400027fc  mov     rcx, r13; hdc
0x1400027ff  mov     r14d, eax
0x140002802  call    cs:__imp_GetDeviceCaps
0x140002808  mov     rdx, r13; hDC
0x14000280b  xor     ecx, ecx; hWnd
0x14000280d  mov     r15d, eax
0x140002810  call    cs:__imp_ReleaseDC
0x140002816  jmp     short loc_14000281B
0x140002818  mov     r15d, r14d
0x14000281b  lea     r9, [rsi+104h]
0x140002822  mov     r11d, 4F6h
0x140002828  imul    r14d, [r9]
0x14000282c  mov     r10d, 6734D007h
0x140002832  mov     eax, r10d
0x140002835  add     r14d, r11d
0x140002838  imul    r14d
0x14000283b  mov     eax, r10d
0x14000283e  mov     r8d, edx
0x140002841  sar     r8d, 0Ah
0x140002845  mov     ecx, r8d
0x140002848  shr     ecx, 1Fh
0x14000284b  add     r8d, ecx
0x14000284e  mov     [rsi+10Ch], r8d
0x140002855  imul    r15d, [r9+4]
0x14000285a  add     r15d, r11d
0x14000285d  imul    r15d
0x140002860  sar     edx, 0Ah
0x140002863  mov     eax, edx
0x140002865  shr     eax, 1Fh
0x140002868  add     edx, eax
0x14000286a  mov     [rsi+110h], edx
0x140002870  mov     eax, [rsi+118h]
0x140002876  add     eax, [rsi+110h]
0x14000287c  mov     ecx, [r12]
0x140002880  mov     [rsi+120h], eax
0x140002886  add     ecx, r8d
0x140002889  mov     rax, [rsi]
0x14000288c  mov     [rsi+11Ch], ecx
0x140002892  mov     rcx, rsi
0x140002895  mov     rax, [rax+18h]
0x140002899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000289e  xor     r9d, r9d
  ... truncated ...
```

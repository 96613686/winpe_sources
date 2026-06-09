# ATL::CComControlBase::InPlaceActivate(long,tagRECT const *)

- ea: `0x1800064e0`
- end: `0x1800069bd`
- name: `?InPlaceActivate@CComControlBase@ATL@@QEAAJJPEBUtagRECT@@@Z`
- size: `1245`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, int, const struct tagRECT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004810`
- `0x180004a14`
- `0x1800064e0`

## callees

- `0x1800064e0`
- `0x180014270`
- `0x180015010`

## import_xrefs

- `USER32!IsChild` at `0x1800068b3`
- `USER32!IsChild` at `0x1800068b3`
- `USER32!SetFocus` at `0x1800068c0`
- `USER32!SetFocus` at `0x1800068c0`
- `USER32!ShowWindow` at `0x1800066f0`
- `USER32!ShowWindow` at `0x1800066f0`
- `USER32!GetFocus` at `0x1800068a7`
- `USER32!GetFocus` at `0x1800068a7`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::InPlaceActivate(ATL::CComControlBase *this, int a2, const struct tagRECT *a3)
{
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  int v8; // ecx
  unsigned int v9; // ecx
  __int64 *v10; // rcx
  bool v11; // zf
  __int64 v12; // rax
  __int64 v13; // r8
  unsigned int v14; // edi
  void (*v15)(void); // rax
  __int64 v17; // rcx
  HWND v18; // rcx
  __int64 v19; // rax
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ecx
  HWND v25; // rdi
  HWND Focus; // rax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // rcx
  __int64 v30; // [rsp+40h] [rbp-49h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h] BYREF
  __int64 v32; // [rsp+50h] [rbp-39h] BYREF
  int v33; // [rsp+58h] [rbp-31h] BYREF
  __int64 v34; // [rsp+60h] [rbp-29h] BYREF
  __int64 v35; // [rsp+68h] [rbp-21h] BYREF
  _OWORD v36[2]; // [rsp+70h] [rbp-19h] BYREF
  __int128 v37; // [rsp+90h] [rbp+7h] BYREF
  __int128 v38; // [rsp+A0h] [rbp+17h] BYREF

  if ( !*((_QWORD *)this + 4) )
    return 0;
  v5 = *(_QWORD *)this;
  v32 = 0;
  (*(void (__fastcall **)(ATL::CComControlBase *, GUID *, __int64 *))(v5 + 16))(
    this,
    &GUID_00000113_0000_0000_c000_000000000046,
    &v32);
  if ( (*((_BYTE *)this + 100) & 1) == 0 )
  {
    if ( (*((_BYTE *)this + 100) & 0x40) == 0 )
      (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 4))(
        *((_QWORD *)this + 4),
        &GUID_922eada0_3424_11cf_b670_00aa004cd6d8,
        (char *)this + 8);
    v6 = *((_QWORD *)this + 1);
    if ( v6 )
    {
      *((_DWORD *)this + 25) |= 0x20u;
      v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 144LL))(v6);
      v8 = *((_DWORD *)this + 25);
      if ( v7 )
        v9 = v8 & 0xFFFFFFFD;
      else
        v9 = v8 | 0x102;
      *((_DWORD *)this + 25) = v9;
    }
    else
    {
      (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 4))(
        *((_QWORD *)this + 4),
        &GUID_9c2cad80_3424_11cf_b670_00aa004cd6d8,
        (char *)this + 8);
      if ( *((_QWORD *)this + 1) )
        *((_DWORD *)this + 25) |= 0x20u;
      else
        (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 4))(
          *((_QWORD *)this + 4),
          &GUID_00000119_0000_0000_c000_000000000046,
          (char *)this + 8);
    }
  }
  v10 = (__int64 *)*((_QWORD *)this + 1);
  if ( !v10 )
    goto LABEL_53;
  *((_DWORD *)this + 25) |= 1u;
  if ( (*((_BYTE *)this + 100) & 4) == 0 )
  {
    v11 = (*((_BYTE *)this + 100) & 2) == 0;
    v33 = 0;
    v12 = *v10;
    if ( v11 )
    {
      if ( (*((_BYTE *)this + 100) & 0x20) == 0 )
      {
        v14 = (*(__int64 (**)(void))(v12 + 40))();
        if ( (v14 & 0x80000000) != 0 )
        {
          if ( !v32 )
            return v14;
          v15 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
LABEL_23:
          v15();
          return v14;
        }
        if ( v14 )
          goto LABEL_53;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
        goto LABEL_27;
      }
      v13 = 0;
    }
    else
    {
      v13 = 1;
    }
    (*(void (__fastcall **)(__int64 *, int *, __int64))(v12 + 120))(v10, &v33, v13);
  }
LABEL_27:
  v17 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 25) |= 4u;
  memset(v36, 0, sizeof(v36));
  v31 = 0;
  v30 = 0;
  LODWORD(v36[0]) = 32;
  v37 = 0;
  v35 = 0;
  v38 = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v35) )
  {
LABEL_32:
    v19 = *(_QWORD *)this;
    v34 = 0;
    (*(void (__fastcall **)(ATL::CComControlBase *, GUID *, __int64 *))(v19 + 16))(
      this,
      &GUID_00000117_0000_0000_c000_000000000046,
      &v34);
    if ( a2 == -4 || (v20 = 0, !a2) )
      v20 = 1;
    if ( (((a2 + 5) & 0xFFFFFFFA) != 0 || *((_QWORD *)this + 6)) && !v20 )
      goto LABEL_75;
    v21 = *((_DWORD *)this + 25);
    if ( (v21 & 8) != 0 )
      goto LABEL_75;
    v22 = *((_QWORD *)this + 1);
    *((_DWORD *)this + 25) = v21 | 8;
    v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 56LL))(v22);
    v24 = *((_DWORD *)this + 25);
    v14 = v23;
    if ( v23 < 0 )
    {
      *((_DWORD *)this + 25) = v24 & 0xFFFFFFF7;
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      if ( !v32 )
        return v14;
      v15 = *(void (**)(void))(*(_QWORD *)v32 + 16LL);
      goto LABEL_23;
    }
    if ( (v24 & 2) != 0 )
    {
      if ( (v24 & 8) != 0 || (int)ATL::CComControlBase::InPlaceActivate(this, -4, 0) >= 0 )
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1) + 176LL))(*((_QWORD *)this + 1), 1);
    }
    else if ( (v24 & 4) != 0 )
    {
      if ( (v24 & 8) != 0 )
      {
        v25 = (HWND)**((_QWORD **)this + 11);
        Focus = GetFocus();
        if ( !IsChild(v25, Focus) )
          SetFocus(v25);
      }
      else
      {
        ATL::CComControlBase::InPlaceActivate(this, -4, 0);
      }
    }
    v27 = v34;
    v28 = v31;
    if ( v34 )
    {
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v31 + 64LL))(v31, v34, 0);
        v28 = v31;
        v27 = v34;
      }
      v29 = v30;
      if ( !v30 )
        goto LABEL_71;
      (*(void (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v30 + 64LL))(v30, v27, 0, v28);
      v28 = v31;
    }
    v29 = v30;
LABEL_71:
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 56LL))(v28, 0);
      v29 = v30;
    }
    if ( v29 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v29 + 56LL))(v29, 0);
LABEL_75:
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 48LL))(*((_QWORD *)this + 4));
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    return 0;
  }
  (*(void (__fastcall **)(_QWORD, __int64 *, __int64 *, __int128 *, __int128 *, _OWORD *))(**((_QWORD **)this + 1) + 64LL))(
    *((_QWORD *)this + 1),
    &v31,
    &v30,
    &v37,
    &v38,
    v36);
  if ( (*((_BYTE *)this + 100) & 2) != 0 )
  {
LABEL_31:
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *))(*(_QWORD *)v32 + 56LL))(v32, &v37, &v38);
    goto LABEL_32;
  }
  v18 = (HWND)**((_QWORD **)this + 11);
  if ( v18 )
  {
    ShowWindow(v18, 5);
    goto LABEL_31;
  }
  if ( (*(__int64 (__fastcall **)(ATL::CComControlBase *, __int64, __int128 *))(*(_QWORD *)this + 8LL))(this, v35, &v37) )
    goto LABEL_31;
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
LABEL_53:
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  return 2147500037LL;
}

```

## disassembly

```asm
0x1800064e0  push    rbp
0x1800064e2  push    rbx
0x1800064e3  push    rsi
0x1800064e4  push    rdi
0x1800064e5  lea     rbp, [rsp-3Fh]
0x1800064ea  sub     rsp, 0C8h
0x1800064f1  mov     rax, cs:__security_cookie
0x1800064f8  xor     rax, rsp
0x1800064fb  mov     [rbp+57h+var_30], rax
0x1800064ff  cmp     qword ptr [rcx+20h], 0
0x180006504  mov     esi, edx
0x180006506  mov     rbx, rcx
0x180006509  jz      loc_1800069A3
0x18000650f  mov     rax, [rcx]
0x180006512  lea     r8, [rbp+57h+var_90]
0x180006516  lea     rdx, _GUID_00000113_0000_0000_c000_000000000046
0x18000651d  mov     [rbp+57h+var_90], 0
0x180006525  mov     rax, [rax+10h]
0x180006529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000652e  test    byte ptr [rbx+64h], 1
0x180006532  jnz     loc_1800065CC
0x180006538  test    byte ptr [rbx+64h], 40h
0x18000653c  jnz     short loc_180006558
0x18000653e  mov     rcx, [rbx+20h]
0x180006542  lea     r8, [rbx+8]
0x180006546  lea     rdx, _GUID_922eada0_3424_11cf_b670_00aa004cd6d8
0x18000654d  mov     rax, [rcx]
0x180006550  mov     rax, [rax]
0x180006553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006558  lea     rdi, [rbx+8]
0x18000655c  mov     rcx, [rdi]
0x18000655f  test    rcx, rcx
0x180006562  jz      short loc_18000658E
0x180006564  or      dword ptr [rbx+64h], 20h
0x180006568  mov     rax, [rcx]
0x18000656b  mov     rax, [rax+90h]
0x180006572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006577  mov     ecx, [rbx+64h]
0x18000657a  test    eax, eax
0x18000657c  jnz     short loc_180006586
0x18000657e  or      ecx, 102h
0x180006584  jmp     short loc_180006589
0x180006586  and     ecx, 0FFFFFFFDh
0x180006589  mov     [rbx+64h], ecx
0x18000658c  jmp     short loc_1800065CC
0x18000658e  mov     rcx, [rbx+20h]
0x180006592  lea     rdx, _GUID_9c2cad80_3424_11cf_b670_00aa004cd6d8
0x180006599  mov     r8, rdi
0x18000659c  mov     rax, [rcx]
0x18000659f  mov     rax, [rax]
0x1800065a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a7  cmp     qword ptr [rdi], 0
0x1800065ab  jz      short loc_1800065B3
0x1800065ad  or      dword ptr [rbx+64h], 20h
0x1800065b1  jmp     short loc_1800065CC
0x1800065b3  mov     rcx, [rbx+20h]
0x1800065b7  lea     rdx, _GUID_00000119_0000_0000_c000_000000000046
0x1800065be  mov     r8, rdi
0x1800065c1  mov     rax, [rcx]
0x1800065c4  mov     rax, [rax]
0x1800065c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065cc  mov     rcx, [rbx+8]
0x1800065d0  test    rcx, rcx
0x1800065d3  jz      loc_18000682F
0x1800065d9  or      dword ptr [rbx+64h], 1
0x1800065dd  test    byte ptr [rbx+64h], 4
0x1800065e1  jnz     short loc_180006656
0x1800065e3  test    byte ptr [rbx+64h], 2
0x1800065e7  mov     [rbp+57h+var_88], 0
0x1800065ee  mov     rax, [rcx]
0x1800065f1  jz      short loc_1800065FB
0x1800065f3  mov     r8d, 1
0x1800065f9  jmp     short loc_180006604
0x1800065fb  test    byte ptr [rbx+64h], 20h
0x1800065ff  jz      short loc_180006613
0x180006601  xor     r8d, r8d
0x180006604  mov     rax, [rax+78h]
0x180006608  lea     rdx, [rbp+57h+var_88]
0x18000660c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006611  jmp     short loc_180006656
0x180006613  mov     rax, [rax+28h]
0x180006617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661c  mov     edi, eax
0x18000661e  test    eax, eax
0x180006620  jns     short loc_18000663E
0x180006622  mov     rcx, [rbp+57h+var_90]
0x180006626  test    rcx, rcx
0x180006629  jz      short loc_180006637
0x18000662b  mov     rdx, [rcx]
0x18000662e  mov     rax, [rdx+10h]
0x180006632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006637  mov     eax, edi
0x180006639  jmp     loc_1800069A5
0x18000663e  test    edi, edi
0x180006640  jnz     loc_18000682F
0x180006646  mov     rcx, [rbx+8]
0x18000664a  mov     rax, [rcx]
0x18000664d  mov     rax, [rax+30h]
0x180006651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006656  mov     rcx, [rbx+8]
0x18000665a  lea     rdx, [rbp+57h+var_78]
0x18000665e  or      dword ptr [rbx+64h], 4
0x180006662  xorps   xmm0, xmm0
0x180006665  movups  [rbp+57h+var_70], xmm0
0x180006669  mov     [rbp+57h+var_98], 0
0x180006671  xorps   xmm1, xmm1
0x180006674  mov     [rbp+57h+var_A0], 0
0x18000667c  movups  [rbp+57h+var_60], xmm0
0x180006680  mov     dword ptr [rbp+57h+var_70], 20h ; ' '
0x180006687  movups  [rbp+57h+var_50], xmm0
0x18000668b  mov     [rbp+57h+var_78], 0
0x180006693  movups  [rbp+57h+var_40], xmm1
0x180006697  mov     rax, [rcx]
0x18000669a  mov     rax, [rax+18h]
0x18000669e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a3  test    eax, eax
0x1800066a5  jnz     short loc_18000670E
0x1800066a7  mov     rcx, [rbx+8]
0x1800066ab  lea     rdx, [rbp+57h+var_70]
0x1800066af  mov     [rsp+0E0h+var_B8], rdx
0x1800066b4  lea     r9, [rbp+57h+var_50]
0x1800066b8  lea     rdx, [rbp+57h+var_40]
0x1800066bc  mov     [rsp+0E0h+var_C0], rdx
0x1800066c1  lea     r8, [rbp+57h+var_A0]
0x1800066c5  mov     rax, [rcx]
0x1800066c8  lea     rdx, [rbp+57h+var_98]
0x1800066cc  mov     rax, [rax+40h]
0x1800066d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d5  test    byte ptr [rbx+64h], 2
0x1800066d9  jnz     short loc_1800066F6
0x1800066db  mov     rax, [rbx+58h]
0x1800066df  mov     rcx, [rax]; hWnd
0x1800066e2  test    rcx, rcx
0x1800066e5  jz      loc_1800067E5
0x1800066eb  mov     edx, 5; nCmdShow
0x1800066f0  call    cs:__imp_ShowWindow
0x1800066f6  mov     rcx, [rbp+57h+var_90]
0x1800066fa  lea     r8, [rbp+57h+var_40]
0x1800066fe  lea     rdx, [rbp+57h+var_50]
0x180006702  mov     rax, [rcx]
0x180006705  mov     rax, [rax+38h]
0x180006709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670e  mov     rax, [rbx]
0x180006711  lea     r8, [rbp+57h+var_80]
0x180006715  lea     rdx, _GUID_00000117_0000_0000_c000_000000000046
0x18000671c  mov     [rbp+57h+var_80], 0
0x180006724  mov     rcx, rbx
0x180006727  mov     rax, [rax+10h]
0x18000672b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006730  cmp     esi, 0FFFFFFFCh
0x180006733  jz      short loc_18000673B
0x180006735  xor     ecx, ecx
0x180006737  test    esi, esi
0x180006739  jnz     short loc_180006740
0x18000673b  mov     ecx, 1
0x180006740  lea     eax, [rsi+5]
0x180006743  test    eax, 0FFFFFFFAh
0x180006748  jnz     short loc_180006751
0x18000674a  cmp     qword ptr [rbx+30h], 0
0x18000674f  jz      short loc_180006759
0x180006751  test    ecx, ecx
0x180006753  jz      loc_18000693F
0x180006759  mov     eax, [rbx+64h]
0x18000675c  test    al, 8
0x18000675e  jnz     loc_18000693F
0x180006764  mov     rcx, [rbx+8]
0x180006768  or      eax, 8
0x18000676b  mov     [rbx+64h], eax
0x18000676e  mov     rax, [rcx]
0x180006771  mov     rax, [rax+38h]
0x180006775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677a  mov     ecx, [rbx+64h]
0x18000677d  mov     edi, eax
0x18000677f  test    eax, eax
0x180006781  jns     loc_18000684E
0x180006787  and     ecx, 0FFFFFFF7h
0x18000678a  mov     [rbx+64h], ecx
0x18000678d  mov     rcx, [rbp+57h+var_80]
0x180006791  test    rcx, rcx
0x180006794  jz      short loc_1800067A2
0x180006796  mov     rdx, [rcx]
0x180006799  mov     rax, [rdx+10h]
0x18000679d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a2  mov     rcx, [rbp+57h+var_A0]
0x1800067a6  test    rcx, rcx
0x1800067a9  jz      short loc_1800067B7
0x1800067ab  mov     rax, [rcx]
0x1800067ae  mov     rax, [rax+10h]
0x1800067b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067b7  mov     rcx, [rbp+57h+var_98]
0x1800067bb  test    rcx, rcx
0x1800067be  jz      short loc_1800067CC
0x1800067c0  mov     rax, [rcx]
0x1800067c3  mov     rax, [rax+10h]
0x1800067c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067cc  mov     rcx, [rbp+57h+var_90]
0x1800067d0  test    rcx, rcx
0x1800067d3  jz      loc_180006637
0x1800067d9  mov     rax, [rcx]
0x1800067dc  mov     rax, [rax+10h]
0x1800067e0  jmp     loc_180006632
0x1800067e5  mov     rax, [rbx]
0x1800067e8  lea     r8, [rbp+57h+var_50]
0x1800067ec  mov     rdx, [rbp+57h+var_78]
0x1800067f0  mov     rcx, rbx
0x1800067f3  mov     rax, [rax+8]
0x1800067f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067fc  test    rax, rax
0x1800067ff  jnz     loc_1800066F6
0x180006805  mov     rcx, [rbp+57h+var_A0]
0x180006809  test    rcx, rcx
0x18000680c  jz      short loc_18000681A
0x18000680e  mov     rax, [rcx]
0x180006811  mov     rax, [rax+10h]
0x180006815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000681a  mov     rcx, [rbp+57h+var_98]
0x18000681e  test    rcx, rcx
0x180006821  jz      short loc_18000682F
0x180006823  mov     rax, [rcx]
0x180006826  mov     rax, [rax+10h]
0x18000682a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000682f  mov     rcx, [rbp+57h+var_90]
0x180006833  test    rcx, rcx
0x180006836  jz      short loc_180006844
0x180006838  mov     rax, [rcx]
0x18000683b  mov     rax, [rax+10h]
0x18000683f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006844  mov     eax, 80004005h
0x180006849  jmp     loc_1800069A5
0x18000684e  test    cl, 2
0x180006851  jz      short loc_180006885
0x180006853  test    cl, 8
0x180006856  jnz     short loc_18000686B
0x180006858  xor     r8d, r8d; struct tagRECT *
0x18000685b  mov     rcx, rbx; this
0x18000685e  lea     edx, [r8-4]; int
0x180006862  call    ?InPlaceActivate@CComControlBase@ATL@@QEAAJJPEBUtagRECT@@@Z; ATL::CComControlBase::InPlaceActivate(long,tagRECT const *)
0x180006867  test    eax, eax
0x180006869  js      short loc_1800068C6
0x18000686b  mov     rcx, [rbx+8]
0x18000686f  mov     edx, 1
0x180006874  mov     rax, [rcx]
0x180006877  mov     rax, [rax+0B0h]
0x18000687e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006883  jmp     short loc_1800068C6
0x180006885  test    cl, 4
0x180006888  jz      short loc_1800068C6
0x18000688a  test    cl, 8
0x18000688d  jnz     short loc_1800068A0
0x18000688f  xor     r8d, r8d; struct tagRECT *
0x180006892  mov     rcx, rbx; this
0x180006895  lea     edx, [r8-4]; int
0x180006899  call    ?InPlaceActivate@CComControlBase@ATL@@QEAAJJPEBUtagRECT@@@Z; ATL::CComControlBase::InPlaceActivate(long,tagRECT const *)
0x18000689e  jmp     short loc_1800068C6
0x1800068a0  mov     rax, [rbx+58h]
0x1800068a4  mov     rdi, [rax]
0x1800068a7  call    cs:__imp_GetFocus
0x1800068ad  mov     rdx, rax; hWnd
0x1800068b0  mov     rcx, rdi; hWndParent
0x1800068b3  call    cs:__imp_IsChild
0x1800068b9  test    eax, eax
0x1800068bb  jnz     short loc_1800068C6
0x1800068bd  mov     rcx, rdi; hWnd
0x1800068c0  call    cs:__imp_SetFocus
0x1800068c6  mov     rdx, [rbp+57h+var_80]
0x1800068ca  mov     r9, [rbp+57h+var_98]
0x1800068ce  test    rdx, rdx
0x1800068d1  jz      short loc_18000690E
0x1800068d3  test    r9, r9
0x1800068d6  jz      short loc_1800068F2
0x1800068d8  mov     rax, [r9]
0x1800068db  xor     r8d, r8d
0x1800068de  mov     rcx, r9
0x1800068e1  mov     rax, [rax+40h]
0x1800068e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ea  mov     r9, [rbp+57h+var_98]
0x1800068ee  mov     rdx, [rbp+57h+var_80]
0x1800068f2  mov     rcx, [rbp+57h+var_A0]
0x1800068f6  test    rcx, rcx
0x1800068f9  jz      short loc_180006912
0x1800068fb  mov     rax, [rcx]
0x1800068fe  xor     r8d, r8d
0x180006901  mov     rax, [rax+40h]
0x180006905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000690a  mov     r9, [rbp+57h+var_98]
0x18000690e  mov     rcx, [rbp+57h+var_A0]
0x180006912  test    r9, r9
0x180006915  jz      short loc_18000692C
0x180006917  mov     rax, [r9]
0x18000691a  xor     edx, edx
0x18000691c  mov     rcx, r9
0x18000691f  mov     rax, [rax+38h]
0x180006923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006928  mov     rcx, [rbp+57h+var_A0]
0x18000692c  test    rcx, rcx
0x18000692f  jz      short loc_18000693F
0x180006931  mov     rax, [rcx]
0x180006934  xor     edx, edx
0x180006936  mov     rax, [rax+38h]
0x18000693a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```

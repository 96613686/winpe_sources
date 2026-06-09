# ATL::CComControlBase::DoVerbProperties(tagRECT const *,HWND__ *)

- ea: `0x180004ba0`
- end: `0x180004e5a`
- name: `?DoVerbProperties@CComControlBase@ATL@@QEAAJPEBUtagRECT@@PEAUHWND__@@@Z`
- size: `698`
- prototype: `__int64 __fastcall(ATL::CComControlBase *__hidden this, const struct tagRECT *, HWND)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180004810`
- `0x180004abc`

## callees

- `0x180004ba0`
- `0x180005798`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180004dd5`
- `ole32!CoTaskMemFree` at `0x180004de6`
- `ole32!CoTaskMemFree` at `0x180004dd5`
- `ole32!CoTaskMemFree` at `0x180004de6`
- `OLEAUT32!__imp_OleCreatePropertyFrame` at `0x180004dc9`
- `OLEAUT32!__imp_OleCreatePropertyFrame` at `0x180004dc9`

## pseudocode

```c
__int64 __fastcall ATL::CComControlBase::DoVerbProperties(
        ATL::CComControlBase *this,
        const struct tagRECT *a2,
        HWND a3)
{
  void (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // ebx
  __int64 v8; // rax
  IUnknown *v9; // rbx
  HRESULT v10; // edi
  IUnknown *v11; // rcx
  IUnknown *v12; // rbx
  int AmbientLocaleID; // eax
  LCID lcid; // ecx
  LPUNKNOWN ppUnk; // [rsp+60h] [rbp+7h] BYREF
  __int64 v16; // [rsp+68h] [rbp+Fh] BYREF
  LPCOLESTR lpszCaption; // [rsp+70h] [rbp+17h] BYREF
  ULONG cPages[4]; // [rsp+78h] [rbp+1Fh] BYREF
  IUnknown *v19; // [rsp+C0h] [rbp+67h] BYREF
  const struct tagRECT *v20; // [rsp+C8h] [rbp+6Fh] BYREF
  IUnknown *v21; // [rsp+D8h] [rbp+7Fh] BYREF

  v20 = a2;
  v21 = 0;
  v4 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 4);
  v19 = 0;
  v16 = 0;
  if ( v4
    && ((**v4)(v4, &GUID_b196b289_bab4_101a_b69c_00aa00341d07, &v16), v16)
    && (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 72LL))(v16), v6 >= 0) )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v19 )
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
    if ( v21 )
      ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
    return (unsigned int)v6;
  }
  else
  {
    v8 = *(_QWORD *)this;
    ppUnk = 0;
    (*(void (__fastcall **)(ATL::CComControlBase *, GUID *, LPUNKNOWN *))(v8 + 16))(
      this,
      &GUID_00000000_0000_0000_c000_000000000046,
      &ppUnk);
    v9 = v21;
    *(_OWORD *)cPages = 0;
    if ( v21 != ppUnk )
    {
      v21 = 0;
      if ( ppUnk )
        ((void (__fastcall *)(LPUNKNOWN, GUID *, IUnknown **))ppUnk->lpVtbl->QueryInterface)(
          ppUnk,
          &GUID_b196b28b_bab4_101a_b69c_00aa00341d07,
          &v21);
      if ( v9 )
        ((void (__fastcall *)(IUnknown *))v9->lpVtbl->Release)(v9);
    }
    if ( v21 )
    {
      v10 = ((__int64 (__fastcall *)(IUnknown *, ULONG *))v21->lpVtbl[1].QueryInterface)(v21, cPages);
      if ( v10 >= 0 )
      {
        v11 = v19;
        if ( v19 != ppUnk )
        {
          v12 = v19;
          v11 = 0;
          v19 = 0;
          if ( ppUnk )
          {
            ((void (__fastcall *)(LPUNKNOWN, GUID *, IUnknown **))ppUnk->lpVtbl->QueryInterface)(
              ppUnk,
              &GUID_00000112_0000_0000_c000_000000000046,
              &v19);
            v11 = v19;
          }
          if ( v12 )
          {
            ((void (__fastcall *)(IUnknown *))v12->lpVtbl->Release)(v12);
            v11 = v19;
          }
        }
        if ( v11 )
        {
          lpszCaption = 0;
          ((void (__fastcall *)(IUnknown *, __int64, LPCOLESTR *))v11->lpVtbl[5].AddRef)(v11, 2, &lpszCaption);
          LODWORD(v20) = 0;
          AmbientLocaleID = ATL::CComControlBase::GetAmbientLocaleID(this, (unsigned int *)&v20);
          lcid = (unsigned int)v20;
          if ( AmbientLocaleID < 0 )
            lcid = 1024;
          v10 = OleCreatePropertyFrame(
                  a3,
                  *((_DWORD *)this + 19),
                  *((_DWORD *)this + 18),
                  lpszCaption,
                  1u,
                  &ppUnk,
                  cPages[0],
                  *(LPCLSID *)&cPages[2],
                  lcid,
                  0,
                  0);
          CoTaskMemFree((LPVOID)lpszCaption);
        }
        else
        {
          v10 = 262529;
        }
        CoTaskMemFree(*(LPVOID *)&cPages[2]);
      }
    }
    else
    {
      v10 = 262529;
    }
    if ( ppUnk )
      ((void (__fastcall *)(LPUNKNOWN))ppUnk->lpVtbl->Release)(ppUnk);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    if ( v19 )
      ((void (__fastcall *)(IUnknown *))v19->lpVtbl->Release)(v19);
    if ( v21 )
      ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
    return (unsigned int)v10;
  }
}

```

## disassembly

```asm
0x180004ba0  mov     [rsp-8+arg_8], rdx
0x180004ba5  push    rbp
0x180004ba6  push    rbx
0x180004ba7  push    rsi
0x180004ba8  push    rdi
0x180004ba9  push    r14
0x180004bab  lea     rbp, [rsp-37h]
0x180004bb0  sub     rsp, 90h
0x180004bb7  mov     rsi, rcx
0x180004bba  mov     [rbp+57h+arg_18], 0
0x180004bc2  mov     rcx, [rcx+20h]
0x180004bc6  mov     r14, r8
0x180004bc9  mov     [rbp+57h+arg_0], 0
0x180004bd1  mov     [rbp+57h+var_48], 0
0x180004bd9  test    rcx, rcx
0x180004bdc  jz      short loc_180004C55
0x180004bde  mov     rax, [rcx]
0x180004be1  lea     r8, [rbp+57h+var_48]
0x180004be5  lea     rdx, _GUID_b196b289_bab4_101a_b69c_00aa00341d07
0x180004bec  mov     rax, [rax]
0x180004bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf4  mov     rcx, [rbp+57h+var_48]
0x180004bf8  test    rcx, rcx
0x180004bfb  jz      short loc_180004C55
0x180004bfd  mov     rax, [rcx]
0x180004c00  mov     rax, [rax+48h]
0x180004c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c09  mov     ebx, eax
0x180004c0b  test    eax, eax
0x180004c0d  js      short loc_180004C55
0x180004c0f  mov     rcx, [rbp+57h+var_48]
0x180004c13  test    rcx, rcx
0x180004c16  jz      short loc_180004C24
0x180004c18  mov     rdx, [rcx]
0x180004c1b  mov     rax, [rdx+10h]
0x180004c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c24  mov     rcx, [rbp+57h+arg_0]
0x180004c28  test    rcx, rcx
0x180004c2b  jz      short loc_180004C39
0x180004c2d  mov     rax, [rcx]
0x180004c30  mov     rax, [rax+10h]
0x180004c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c39  mov     rcx, [rbp+57h+arg_18]
0x180004c3d  test    rcx, rcx
0x180004c40  jz      short loc_180004C4E
0x180004c42  mov     rax, [rcx]
0x180004c45  mov     rax, [rax+10h]
0x180004c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c4e  mov     eax, ebx
0x180004c50  jmp     loc_180004E4C
0x180004c55  mov     rax, [rsi]
0x180004c58  lea     r8, [rbp+57h+var_50]
0x180004c5c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180004c63  mov     [rbp+57h+var_50], 0
0x180004c6b  mov     rcx, rsi
0x180004c6e  mov     rax, [rax+10h]
0x180004c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c77  mov     rcx, [rbp+57h+var_50]
0x180004c7b  xorps   xmm0, xmm0
0x180004c7e  mov     rbx, [rbp+57h+arg_18]
0x180004c82  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x180004c86  cmp     rbx, rcx
0x180004c89  jz      short loc_180004CC2
0x180004c8b  mov     [rbp+57h+arg_18], 0
0x180004c93  test    rcx, rcx
0x180004c96  jz      short loc_180004CAE
0x180004c98  mov     rax, [rcx]
0x180004c9b  lea     r8, [rbp+57h+arg_18]
0x180004c9f  lea     rdx, _GUID_b196b28b_bab4_101a_b69c_00aa00341d07
0x180004ca6  mov     rax, [rax]
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  test    rbx, rbx
0x180004cb1  jz      short loc_180004CC2
0x180004cb3  mov     rax, [rbx]
0x180004cb6  mov     rcx, rbx
0x180004cb9  mov     rax, [rax+10h]
0x180004cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc2  mov     rbx, [rbp+57h+arg_18]
0x180004cc6  test    rbx, rbx
0x180004cc9  jz      loc_180004DEE
0x180004ccf  mov     rax, [rbx]
0x180004cd2  lea     rdx, [rbp+57h+var_38]
0x180004cd6  mov     rcx, rbx
0x180004cd9  mov     rax, [rax+18h]
0x180004cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ce2  mov     edi, eax
0x180004ce4  test    eax, eax
0x180004ce6  js      loc_180004DF3
0x180004cec  mov     r9, [rbp+57h+var_50]
0x180004cf0  mov     rcx, [rbp+57h+arg_0]
0x180004cf4  cmp     rcx, r9
0x180004cf7  jz      short loc_180004D3C
0x180004cf9  mov     rbx, rcx
0x180004cfc  xor     ecx, ecx
0x180004cfe  mov     [rbp+57h+arg_0], rcx
0x180004d02  test    r9, r9
0x180004d05  jz      short loc_180004D24
0x180004d07  mov     rax, [r9]
0x180004d0a  lea     r8, [rbp+57h+arg_0]
0x180004d0e  lea     rdx, _GUID_00000112_0000_0000_c000_000000000046
0x180004d15  mov     rcx, r9
0x180004d18  mov     rax, [rax]
0x180004d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d20  mov     rcx, [rbp+57h+arg_0]
0x180004d24  test    rbx, rbx
0x180004d27  jz      short loc_180004D3C
0x180004d29  mov     rax, [rbx]
0x180004d2c  mov     rcx, rbx
0x180004d2f  mov     rax, [rax+10h]
0x180004d33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d38  mov     rcx, [rbp+57h+arg_0]
0x180004d3c  test    rcx, rcx
0x180004d3f  jz      loc_180004DDD
0x180004d45  mov     [rbp+57h+lpszCaption], 0
0x180004d4d  lea     r8, [rbp+57h+lpszCaption]
0x180004d51  mov     rax, [rcx]
0x180004d54  mov     edx, 2
0x180004d59  mov     rax, [rax+80h]
0x180004d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d65  lea     rdx, [rbp+57h+arg_8]; unsigned int *
0x180004d69  mov     dword ptr [rbp+57h+arg_8], 0
0x180004d70  mov     rcx, rsi; this
0x180004d73  call    ?GetAmbientLocaleID@CComControlBase@ATL@@QEAAJAEAK@Z; ATL::CComControlBase::GetAmbientLocaleID(ulong &)
0x180004d78  mov     ecx, dword ptr [rbp+57h+arg_8]
0x180004d7b  test    eax, eax
0x180004d7d  mov     rax, qword ptr [rbp+57h+var_38+8]
0x180004d81  mov     edx, 400h
0x180004d86  mov     r9, [rbp+57h+lpszCaption]; lpszCaption
0x180004d8a  cmovs   ecx, edx
0x180004d8d  mov     r8d, [rsi+48h]; y
0x180004d91  mov     edx, [rsi+4Ch]; x
0x180004d94  mov     [rsp+0B0h+pvReserved], 0; pvReserved
0x180004d9d  mov     [rsp+0B0h+dwReserved], 0; dwReserved
0x180004da5  mov     [rsp+0B0h+lcid], ecx; lcid
0x180004da9  mov     rcx, r14; hwndOwner
0x180004dac  mov     [rsp+0B0h+pPageClsID], rax; pPageClsID
0x180004db1  mov     eax, [rbp+57h+var_38]
0x180004db4  mov     [rsp+0B0h+cPages], eax; cPages
0x180004db8  lea     rax, [rbp+57h+var_50]
0x180004dbc  mov     [rsp+0B0h+ppUnk], rax; ppUnk
0x180004dc1  mov     [rsp+0B0h+cObjects], 1; cObjects
0x180004dc9  call    cs:__imp_OleCreatePropertyFrame
0x180004dcf  mov     rcx, [rbp+57h+lpszCaption]; pv
0x180004dd3  mov     edi, eax
0x180004dd5  call    cs:__imp_CoTaskMemFree
0x180004ddb  jmp     short loc_180004DE2
0x180004ddd  mov     edi, 40181h
0x180004de2  mov     rcx, qword ptr [rbp+57h+var_38+8]; pv
0x180004de6  call    cs:__imp_CoTaskMemFree
0x180004dec  jmp     short loc_180004DF3
0x180004dee  mov     edi, 40181h
0x180004df3  mov     rcx, [rbp+57h+var_50]
0x180004df7  test    rcx, rcx
0x180004dfa  jz      short loc_180004E08
0x180004dfc  mov     rax, [rcx]
0x180004dff  mov     rax, [rax+10h]
0x180004e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e08  mov     rcx, [rbp+57h+var_48]
0x180004e0c  test    rcx, rcx
0x180004e0f  jz      short loc_180004E1D
0x180004e11  mov     rax, [rcx]
0x180004e14  mov     rax, [rax+10h]
0x180004e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e1d  mov     rcx, [rbp+57h+arg_0]
0x180004e21  test    rcx, rcx
0x180004e24  jz      short loc_180004E32
0x180004e26  mov     rax, [rcx]
0x180004e29  mov     rax, [rax+10h]
0x180004e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e32  mov     rbx, [rbp+57h+arg_18]
0x180004e36  test    rbx, rbx
0x180004e39  jz      short loc_180004E4A
0x180004e3b  mov     rax, [rbx]
0x180004e3e  mov     rcx, rbx
0x180004e41  mov     rax, [rax+10h]
0x180004e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e4a  mov     eax, edi
0x180004e4c  add     rsp, 90h
0x180004e53  pop     r14
0x180004e55  pop     rdi
0x180004e56  pop     rsi
0x180004e57  pop     rbx
0x180004e58  pop     rbp
0x180004e59  retn
```

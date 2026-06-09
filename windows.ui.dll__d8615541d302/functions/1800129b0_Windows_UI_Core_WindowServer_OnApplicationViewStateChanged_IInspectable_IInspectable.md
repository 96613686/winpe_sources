# Windows::UI::Core::WindowServer::OnApplicationViewStateChanged(IInspectable *,IInspectable *)

- ea: `0x1800129b0`
- end: `0x180012e8e`
- name: `?OnApplicationViewStateChanged@WindowServer@Core@UI@Windows@@AEAAJPEAUIInspectable@@0@Z`
- size: `1246`
- prototype: `__int64 __fastcall(Windows::UI::Core::WindowServer *__hidden this, struct IInspectable *, struct IInspectable *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800038e0`
- `0x1800129b0`
- `0x180014754`
- `0x1800581b8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180012ba3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendNotifyMessageW` at `0x180012ba3`

## string_xrefs

- `0x180012bb1`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012c85`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012cd7`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012d29`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012d7b`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012db3`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012e05`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012e30`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`
- `0x180012e52`: `onecoreuap\windows\advcore\winrt\onecoreiwindow\corewindow\common\windowserver.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::UI::Core::WindowServer::OnApplicationViewStateChanged(
        Windows::UI::Core::WindowServer *this,
        struct IInspectable *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v6; // eax
  unsigned int LastError; // ebx
  int v8; // eax
  int v9; // r15d
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rsi
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD *); // rbx
  int v21; // eax
  const char *v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rdx
  int v40; // [rsp+20h] [rbp-30h] BYREF
  int v41; // [rsp+24h] [rbp-2Ch] BYREF
  int v42; // [rsp+28h] [rbp-28h] BYREF
  __int64 v43; // [rsp+30h] [rbp-20h] BYREF
  __int64 v44; // [rsp+38h] [rbp-18h] BYREF
  _QWORD v45[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  char v47; // [rsp+A0h] [rbp+50h] BYREF
  char v48; // [rsp+A8h] [rbp+58h] BYREF

  v44 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
  v6 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_821b877f_178d_47fa_8983_87449a87e794,
         &v44);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1349,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v6,
      v40);
    v36 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return LastError;
  }
  v47 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v44 + 48LL))(v44, &v47);
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134C,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v8,
      v40);
LABEL_62:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v44);
    return LastError;
  }
  v9 = 0;
  if ( v47 )
    v9 = 2;
  v43 = 0;
  v10 = *((_QWORD *)this + 383);
  v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 32LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v43);
  v12 = v11(v10, &v43);
  LastError = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1355,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v12,
      v40);
    v30 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return LastError;
  }
  v48 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 72LL))(v43, &v48);
  LastError = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1358,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v13,
      v40);
    v37 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    }
    return LastError;
  }
  v14 = 1;
  if ( v48 )
    v9 |= 1u;
  LOBYTE(v40) = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 40LL))(v43, &v40);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1360,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v15,
      v40);
    v32 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return LastError;
  }
  BYTE1(v40) = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v43 + 48LL))(v43, (char *)&v40 + 1);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1363,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v16,
      v40);
    v34 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    v35 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    }
    return LastError;
  }
  v17 = (_BYTE)v40 != 0;
  if ( BYTE1(v40) )
    v17 |= 2u;
  v42 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v43 + 32LL))(v43, &v42);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1371,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v18,
      v40);
LABEL_61:
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v43);
    goto LABEL_62;
  }
  v45[0] = 0;
  v19 = *((_QWORD *)this + 383);
  v20 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v19 + 56LL);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v45);
  v21 = v20(v19, v45);
  LastError = v21;
  if ( v21 < 0 )
  {
    v39 = 4982;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
      (const char *)(unsigned int)v21,
      v40);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(v45);
    goto LABEL_61;
  }
  v41 = 0;
  v21 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v45[0] + 40LL))(v45[0], &v41);
  LastError = v21;
  if ( v21 < 0 )
  {
    v39 = 4985;
    goto LABEL_60;
  }
  if ( v41 == 1 || v41 == 4 )
    v14 = 0;
  if ( !SendNotifyMessageW(
          *((HWND *)this + 433),
          0x271u,
          (v14 << 16) | (unsigned __int16)v42,
          v17 | (unsigned __int64)(unsigned int)(v9 << 16)) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x1384,
                  (unsigned int)"onecoreuap\\windows\\advcore\\winrt\\onecoreiwindow\\corewindow\\common\\windowserver.cpp",
                  v22);
    v23 = v45[0];
    if ( v45[0] )
    {
      v45[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v43;
    if ( v43 )
    {
      v43 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v44;
    if ( v44 )
    {
      v44 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return LastError;
  }
  v27 = v45[0];
  if ( v45[0] )
  {
    v45[0] = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  v28 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  }
  v29 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return 0;
}

```

## disassembly

```asm
0x1800129b0  mov     [rsp-38h+arg_0], rbx
0x1800129b5  push    rbp
0x1800129b6  push    rsi
0x1800129b7  push    rdi
0x1800129b8  push    r12
0x1800129ba  push    r13
0x1800129bc  push    r14
0x1800129be  push    r15
0x1800129c0  mov     rbp, rsp
0x1800129c3  sub     rsp, 50h
0x1800129c7  mov     rdi, r8
0x1800129ca  mov     r13, rcx
0x1800129cd  xor     r12d, r12d
0x1800129d0  mov     [rbp+var_18], r12
0x1800129d4  mov     rax, [r8]
0x1800129d7  mov     rbx, [rax]
0x1800129da  lea     rcx, [rbp+var_18]
0x1800129de  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800129e3  lea     r8, [rbp+var_18]
0x1800129e7  lea     rdx, _GUID_821b877f_178d_47fa_8983_87449a87e794
0x1800129ee  mov     rcx, rdi
0x1800129f1  mov     rax, rbx
0x1800129f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129f9  mov     ebx, eax
0x1800129fb  test    eax, eax
0x1800129fd  js      loc_180012D74
0x180012a03  mov     [rbp+arg_10], r12b
0x180012a07  mov     rcx, [rbp+var_18]
0x180012a0b  mov     rax, [rcx]
0x180012a0e  lea     rdx, [rbp+arg_10]
0x180012a12  mov     rax, [rax+30h]
0x180012a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a1b  mov     ebx, eax
0x180012a1d  test    eax, eax
0x180012a1f  js      loc_180012DFE
0x180012a25  mov     r15d, r12d
0x180012a28  lea     eax, [r12+2]
0x180012a2d  cmp     [rbp+arg_10], r12b
0x180012a31  cmovnz  r15d, eax
0x180012a35  mov     [rbp+var_20], r12
0x180012a39  mov     rdi, [r13+0BF8h]
0x180012a40  mov     rax, [rdi]
0x180012a43  mov     rbx, [rax+20h]
0x180012a47  lea     rcx, [rbp+var_20]
0x180012a4b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180012a50  lea     rdx, [rbp+var_20]
0x180012a54  mov     rcx, rdi
0x180012a57  mov     rax, rbx
0x180012a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a5f  mov     ebx, eax
0x180012a61  test    eax, eax
0x180012a63  js      loc_180012C7E
0x180012a69  mov     [rbp+arg_18], r12b
0x180012a6d  mov     rcx, [rbp+var_20]
0x180012a71  mov     rax, [rcx]
0x180012a74  lea     rdx, [rbp+arg_18]
0x180012a78  mov     rax, [rax+48h]
0x180012a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a81  mov     ebx, eax
0x180012a83  test    eax, eax
0x180012a85  js      loc_180012DAC
0x180012a8b  lea     esi, [r12+1]
0x180012a90  cmp     [rbp+arg_18], r12b
0x180012a94  jnz     loc_180012E18
0x180012a9a  mov     [rbp+var_30], r12b
0x180012a9e  mov     rcx, [rbp+var_20]
0x180012aa2  mov     rax, [rcx]
0x180012aa5  lea     rdx, [rbp+var_30]
0x180012aa9  mov     rax, [rax+28h]
0x180012aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ab2  mov     ebx, eax
0x180012ab4  test    eax, eax
0x180012ab6  js      loc_180012CD0
0x180012abc  mov     [rbp+var_2F], r12b
0x180012ac0  mov     rcx, [rbp+var_20]
0x180012ac4  mov     rax, [rcx]
0x180012ac7  lea     rdx, [rbp+var_2F]
0x180012acb  mov     rax, [rax+30h]
0x180012acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ad4  mov     ebx, eax
0x180012ad6  test    eax, eax
0x180012ad8  js      loc_180012D22
0x180012ade  mov     r14d, r12d
0x180012ae1  cmp     [rbp+var_30], r12b
0x180012ae5  cmovnz  r14d, esi
0x180012ae9  cmp     [rbp+var_2F], r12b
0x180012aed  jnz     loc_180012E20
0x180012af3  mov     [rbp+var_28], r12d
0x180012af7  mov     rcx, [rbp+var_20]
0x180012afb  mov     rax, [rcx]
0x180012afe  lea     rdx, [rbp+var_28]
0x180012b02  mov     rax, [rax+20h]
0x180012b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b0b  mov     ebx, eax
0x180012b0d  test    eax, eax
0x180012b0f  js      loc_180012E29
0x180012b15  mov     [rbp+var_10], r12
0x180012b19  mov     rdi, [r13+0BF8h]
0x180012b20  mov     rax, [rdi]
0x180012b23  mov     rbx, [rax+38h]
0x180012b27  lea     rcx, [rbp+var_10]
0x180012b2b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x180012b30  lea     rdx, [rbp+var_10]
0x180012b34  mov     rcx, rdi
0x180012b37  mov     rax, rbx
0x180012b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b3f  mov     ebx, eax
0x180012b41  test    eax, eax
0x180012b43  js      loc_180012E43
0x180012b49  mov     [rbp+var_2C], r12d
0x180012b4d  mov     rcx, [rbp+var_10]
0x180012b51  mov     rax, [rcx]
0x180012b54  lea     rdx, [rbp+var_2C]
0x180012b58  mov     rax, [rax+28h]
0x180012b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b61  mov     ebx, eax
0x180012b63  test    eax, eax
0x180012b65  js      loc_180012E4A
0x180012b6b  cmp     [rbp+var_2C], esi
0x180012b6e  jz      loc_180012E85
0x180012b74  cmp     [rbp+var_2C], 4
0x180012b78  jz      loc_180012E85
0x180012b7e  shl     r15d, 10h
0x180012b82  mov     r9d, r15d
0x180012b85  mov     eax, r14d
0x180012b88  or      r9, rax; lParam
0x180012b8b  shl     rsi, 10h
0x180012b8f  movzx   r8d, word ptr [rbp+var_28]
0x180012b94  or      r8, rsi; wParam
0x180012b97  mov     edx, 271h; Msg
0x180012b9c  mov     rcx, [r13+0D88h]; hWnd
0x180012ba3  call    cs:__imp_SendNotifyMessageW
0x180012ba9  test    eax, eax
0x180012bab  jnz     short loc_180012C2C
0x180012bad  mov     rcx, [rbp+38h]; this
0x180012bb1  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012bb8  mov     edx, 1384h; void *
0x180012bbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180012bc2  mov     ebx, eax
0x180012bc4  mov     rcx, [rbp+var_10]
0x180012bc8  test    rcx, rcx
0x180012bcb  jz      short loc_180012BDE
0x180012bcd  mov     [rbp+var_10], r12
0x180012bd1  mov     rdx, [rcx]
0x180012bd4  mov     rax, [rdx+10h]
0x180012bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bdd  nop
0x180012bde  mov     rcx, [rbp+var_20]
0x180012be2  test    rcx, rcx
0x180012be5  jz      short loc_180012BF8
0x180012be7  mov     [rbp+var_20], r12
0x180012beb  mov     rax, [rcx]
0x180012bee  mov     rax, [rax+10h]
0x180012bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012bf7  nop
0x180012bf8  mov     rcx, [rbp+var_18]
0x180012bfc  test    rcx, rcx
0x180012bff  jz      short loc_180012C12
0x180012c01  mov     [rbp+var_18], r12
0x180012c05  mov     rax, [rcx]
0x180012c08  mov     rax, [rax+10h]
0x180012c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c11  nop
0x180012c12  mov     eax, ebx
0x180012c14  mov     rbx, [rsp+50h+arg_0]
0x180012c1c  add     rsp, 50h
0x180012c20  pop     r15
0x180012c22  pop     r14
0x180012c24  pop     r13
0x180012c26  pop     r12
0x180012c28  pop     rdi
0x180012c29  pop     rsi
0x180012c2a  pop     rbp
0x180012c2b  retn
0x180012c2c  mov     rcx, [rbp+var_10]
0x180012c30  test    rcx, rcx
0x180012c33  jz      short loc_180012C46
0x180012c35  mov     [rbp+var_10], r12
0x180012c39  mov     rax, [rcx]
0x180012c3c  mov     rax, [rax+10h]
0x180012c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c45  nop
0x180012c46  mov     rcx, [rbp+var_20]
0x180012c4a  test    rcx, rcx
0x180012c4d  jz      short loc_180012C60
0x180012c4f  mov     [rbp+var_20], r12
0x180012c53  mov     rax, [rcx]
0x180012c56  mov     rax, [rax+10h]
0x180012c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5f  nop
0x180012c60  mov     rcx, [rbp+var_18]
0x180012c64  test    rcx, rcx
0x180012c67  jz      short loc_180012C7A
0x180012c69  mov     [rbp+var_18], r12
0x180012c6d  mov     rax, [rcx]
0x180012c70  mov     rax, [rax+10h]
0x180012c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c79  nop
0x180012c7a  xor     eax, eax
0x180012c7c  jmp     short loc_180012C14
0x180012c7e  mov     rcx, [rbp+38h]; this
0x180012c82  mov     r9d, ebx; char *
0x180012c85  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012c8c  mov     edx, 1355h; void *
0x180012c91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012c96  nop
0x180012c97  mov     rcx, [rbp+var_20]
0x180012c9b  test    rcx, rcx
0x180012c9e  jz      short loc_180012CB1
0x180012ca0  mov     [rbp+var_20], r12
0x180012ca4  mov     rax, [rcx]
0x180012ca7  mov     rax, [rax+10h]
0x180012cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cb0  nop
0x180012cb1  mov     rcx, [rbp+var_18]
0x180012cb5  test    rcx, rcx
0x180012cb8  jz      short loc_180012CCB
0x180012cba  mov     [rbp+var_18], r12
0x180012cbe  mov     rax, [rcx]
0x180012cc1  mov     rax, [rax+10h]
0x180012cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cca  nop
0x180012ccb  jmp     loc_180012C12
0x180012cd0  mov     rcx, [rbp+38h]; this
0x180012cd4  mov     r9d, ebx; char *
0x180012cd7  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012cde  mov     edx, 1360h; void *
0x180012ce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ce8  nop
0x180012ce9  mov     rcx, [rbp+var_20]
0x180012ced  test    rcx, rcx
0x180012cf0  jz      short loc_180012D03
0x180012cf2  mov     [rbp+var_20], r12
0x180012cf6  mov     rax, [rcx]
0x180012cf9  mov     rax, [rax+10h]
0x180012cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d02  nop
0x180012d03  mov     rcx, [rbp+var_18]
0x180012d07  test    rcx, rcx
0x180012d0a  jz      short loc_180012D1D
0x180012d0c  mov     [rbp+var_18], r12
0x180012d10  mov     rax, [rcx]
0x180012d13  mov     rax, [rax+10h]
0x180012d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d1c  nop
0x180012d1d  jmp     loc_180012C12
0x180012d22  mov     rcx, [rbp+38h]; this
0x180012d26  mov     r9d, ebx; char *
0x180012d29  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012d30  mov     edx, 1363h; void *
0x180012d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d3a  nop
0x180012d3b  mov     rcx, [rbp+var_20]
0x180012d3f  test    rcx, rcx
0x180012d42  jz      short loc_180012D55
0x180012d44  mov     [rbp+var_20], r12
0x180012d48  mov     rax, [rcx]
0x180012d4b  mov     rax, [rax+10h]
0x180012d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d54  nop
0x180012d55  mov     rcx, [rbp+var_18]
0x180012d59  test    rcx, rcx
0x180012d5c  jz      short loc_180012D6F
0x180012d5e  mov     [rbp+var_18], r12
0x180012d62  mov     rax, [rcx]
0x180012d65  mov     rax, [rax+10h]
0x180012d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d6e  nop
0x180012d6f  jmp     loc_180012C12
0x180012d74  mov     rcx, [rbp+38h]; this
0x180012d78  mov     r9d, ebx; char *
0x180012d7b  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012d82  mov     edx, 1349h; void *
0x180012d87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d8c  nop
0x180012d8d  mov     rcx, [rbp+var_18]
0x180012d91  test    rcx, rcx
0x180012d94  jz      short loc_180012DA7
0x180012d96  mov     [rbp+var_18], r12
0x180012d9a  mov     rax, [rcx]
0x180012d9d  mov     rax, [rax+10h]
0x180012da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da6  nop
0x180012da7  jmp     loc_180012C12
0x180012dac  mov     rcx, [rbp+38h]; this
0x180012db0  mov     r9d, ebx; char *
0x180012db3  lea     r8, aOnecoreuapWind_28; "onecoreuap\\windows\\advcore\\winrt\\on"...
0x180012dba  mov     edx, 1358h; void *
0x180012dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012dc4  nop
0x180012dc5  mov     rcx, [rbp+var_20]
0x180012dc9  test    rcx, rcx
0x180012dcc  jz      short loc_180012DDF
0x180012dce  mov     [rbp+var_20], r12
0x180012dd2  mov     rax, [rcx]
0x180012dd5  mov     rax, [rax+10h]
0x180012dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dde  nop
0x180012ddf  mov     rcx, [rbp+var_18]
0x180012de3  test    rcx, rcx
  ... truncated ...
```

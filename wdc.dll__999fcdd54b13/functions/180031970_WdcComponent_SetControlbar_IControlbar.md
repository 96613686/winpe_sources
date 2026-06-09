# WdcComponent::SetControlbar(IControlbar *)

- ea: `0x180031970`
- end: `0x180031c47`
- name: `?SetControlbar@WdcComponent@@UEAAJPEAUIControlbar@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(WdcComponent *__hidden this, struct IControlbar *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x180031970`
- `0x1800481c0`
- `0x180086010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180031ab3`
- `KERNEL32!GetLastError` at `0x180031b73`
- `KERNEL32!GetLastError` at `0x180031bb9`
- `KERNEL32!GetLastError` at `0x180031ab3`
- `KERNEL32!GetLastError` at `0x180031b73`
- `KERNEL32!GetLastError` at `0x180031bb9`
- `USER32!LoadBitmapW` at `0x180031aa0`
- `USER32!LoadBitmapW` at `0x180031aa0`
- `USER32!LoadStringW` at `0x180031b69`
- `USER32!LoadStringW` at `0x180031baf`
- `USER32!LoadStringW` at `0x180031b69`
- `USER32!LoadStringW` at `0x180031baf`

## string_xrefs

- `0x180031a10`: `base\diagnosis\pdui\perfmon\mmc\component.cpp`
- `0x180031c13`: `base\diagnosis\pdui\perfmon\mmc\component.cpp`
- `0x180031a07`: `WdcComponent::SetControlbar`
- `0x180031c0c`: `WdcComponent::SetControlbar`

## pseudocode

```c
__int64 __fastcall WdcComponent::SetControlbar(unsigned __int64 this, struct IControlbar *a2, int a3)
{
  _QWORD *v3; // r13
  __int64 v6; // rcx
  signed int v7; // ebx
  _QWORD *v8; // rdi
  __int64 v9; // rcx
  WCHAR *v10; // rax
  const char *v11; // rdx
  int v12; // r8d
  WCHAR *v13; // r12
  WCHAR *v14; // rax
  WCHAR *v15; // r15
  int v16; // eax
  HBITMAP BitmapW; // rax
  HBITMAP v18; // rdi
  signed int v19; // eax
  const char *v20; // rdx
  int v21; // r8d
  __int64 *i; // rdi
  __int128 v23; // xmm0
  unsigned __int64 v24; // rcx
  signed int LastError; // eax
  signed int v26; // eax
  const char *v27; // rdx
  int v28; // r8d
  int v30; // [rsp+20h] [rbp-48h]
  __int128 v31; // [rsp+40h] [rbp-28h] BYREF
  __int128 v32; // [rsp+50h] [rbp-18h]
  UINT uID; // [rsp+B0h] [rbp+48h] BYREF

  v3 = (_QWORD *)(this + 48);
  uID = 0;
  v6 = *(_QWORD *)(this + 48);
  v7 = 0;
  v31 = 0;
  v32 = 0;
  if ( v6 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *v3 = 0;
  }
  v8 = (_QWORD *)(this + 40);
  v9 = *(_QWORD *)(this + 40);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *v8 = 0;
  }
  if ( a2 )
  {
    v10 = (WCHAR *)WdcAlloc(0x800u, (const char *)a2, a3);
    v13 = v10;
    if ( !v10 )
    {
      v7 = -2147024882;
      WdcDebugMessage(
        "base\\diagnosis\\pdui\\perfmon\\mmc\\component.cpp",
        "WdcComponent::SetControlbar",
        0,
        L"FAILURE: 0x%08x",
        -2147024882);
      return (unsigned int)v7;
    }
    *v10 = 0;
    v14 = (WCHAR *)WdcAlloc(0x800u, v11, v12);
    v15 = v14;
    if ( !v14 )
    {
      v16 = -2147024882;
      v7 = -2147024882;
LABEL_39:
      v30 = v16;
      goto LABEL_40;
    }
    *v14 = 0;
    v16 = ((__int64 (__fastcall *)(struct IControlbar *, GUID *, unsigned __int64))a2->lpVtbl->QueryInterface)(
            a2,
            &IID_IControlbar,
            this + 40);
    v7 = v16;
    if ( v16 < 0 )
      goto LABEL_39;
    v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, _QWORD *))(*(_QWORD *)*v8 + 24LL))(
            *v8,
            0,
            this & -(__int64)(this != 16),
            v3);
    v7 = v16;
    if ( v16 < 0 )
      goto LABEL_39;
    BitmapW = LoadBitmapW(g_hInstance, (LPCWSTR)0x7A);
    v18 = BitmapW;
    if ( BitmapW && BitmapW != HBITMAP_CALLBACK )
    {
LABEL_21:
      v16 = (*(__int64 (__fastcall **)(_QWORD, __int64, HBITMAP))(*(_QWORD *)*v3 + 24LL))(*v3, 8, v18);
      v7 = v16;
      if ( v16 >= 0 )
      {
        for ( i = qword_1800B0C50; *((_DWORD *)i + 1); i += 4 )
        {
          v23 = *(_OWORD *)i;
          v24 = i[2];
          *(_QWORD *)&v32 = v13;
          *((_QWORD *)&v32 + 1) = v15;
          v31 = v23;
          v16 = ULongLongToUInt(v24, &uID);
          v7 = v16;
          if ( v16 < 0 )
            goto LABEL_39;
          if ( LoadStringW(g_hInstance, uID, v13, 1024) <= 0 )
          {
            LastError = GetLastError();
            v7 = LastError;
            if ( !LastError )
              goto LABEL_38;
            if ( LastError > 0 )
              v7 = (unsigned __int16)LastError | 0x80070000;
            v16 = v7;
            if ( v7 < 0 )
              goto LABEL_39;
          }
          v16 = ULongLongToUInt(i[3], &uID);
          v7 = v16;
          if ( v16 < 0 )
            goto LABEL_39;
          if ( LoadStringW(g_hInstance, uID, v15, 1024) <= 0 )
          {
            v26 = GetLastError();
            v7 = v26;
            if ( !v26 )
            {
LABEL_38:
              v7 = -2147467259;
              v16 = -2147467259;
              goto LABEL_39;
            }
            if ( v26 > 0 )
              v7 = (unsigned __int16)v26 | 0x80070000;
            v16 = v7;
            if ( v7 < 0 )
              goto LABEL_39;
          }
          v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int128 *))(*(_QWORD *)*v3 + 40LL))(*v3, 0, &v31);
          v7 = v16;
          if ( v16 < 0 )
            goto LABEL_39;
        }
        goto LABEL_41;
      }
      goto LABEL_39;
    }
    v19 = GetLastError();
    v7 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v7 = (unsigned __int16)v19 | 0x80070000;
      if ( v7 >= 0 )
        goto LABEL_21;
    }
    else
    {
      v7 = -2147467259;
    }
    v30 = v7;
LABEL_40:
    WdcDebugMessage(
      "base\\diagnosis\\pdui\\perfmon\\mmc\\component.cpp",
      "WdcComponent::SetControlbar",
      0,
      L"FAILURE: 0x%08x",
      v30);
LABEL_41:
    WdcFree(v13, v20, v21);
    if ( v15 )
      WdcFree(v15, v27, v28);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180031970  push    rbp
0x180031972  push    rbx
0x180031973  push    rsi
0x180031974  push    rdi
0x180031975  push    r12
0x180031977  push    r13
0x180031979  push    r14
0x18003197b  push    r15
0x18003197d  mov     rbp, rsp
0x180031980  sub     rsp, 68h
0x180031984  xor     r15d, r15d
0x180031987  lea     r13, [rcx+30h]
0x18003198b  xorps   xmm0, xmm0
0x18003198e  mov     [rbp+uID], r15d
0x180031992  mov     rsi, rcx
0x180031995  mov     r14, rdx
0x180031998  mov     rcx, [r13+0]
0x18003199c  mov     ebx, r15d
0x18003199f  movups  [rbp+var_28], xmm0
0x1800319a3  movups  [rbp+var_18], xmm0
0x1800319a7  test    rcx, rcx
0x1800319aa  jz      short loc_1800319BC
0x1800319ac  mov     rax, [rcx]
0x1800319af  mov     rax, [rax+10h]
0x1800319b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319b8  mov     [r13+0], r15
0x1800319bc  lea     rdi, [rsi+28h]
0x1800319c0  mov     rcx, [rdi]
0x1800319c3  test    rcx, rcx
0x1800319c6  jz      short loc_1800319D7
0x1800319c8  mov     rax, [rcx]
0x1800319cb  mov     rax, [rax+10h]
0x1800319cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800319d4  mov     [rdi], r15
0x1800319d7  test    r14, r14
0x1800319da  jz      loc_180031C34
0x1800319e0  mov     ebx, 800h
0x1800319e5  mov     ecx, ebx; dwBytes
0x1800319e7  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x1800319ec  mov     r12, rax
0x1800319ef  test    rax, rax
0x1800319f2  jnz     short loc_180031A21
0x1800319f4  mov     eax, 8007000Eh
0x1800319f9  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180031a00  xor     r8d, r8d; int
0x180031a03  mov     [rsp+68h+var_48], eax
0x180031a07  lea     rdx, aWdccomponentSe; "WdcComponent::SetControlbar"
0x180031a0e  mov     ebx, eax
0x180031a10  lea     rcx, aBaseDiagnosisP_23; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180031a17  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180031a1c  jmp     loc_180031C34
0x180031a21  mov     rcx, rbx; dwBytes
0x180031a24  mov     [rax], r15w
0x180031a28  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180031a2d  mov     r15, rax
0x180031a30  test    rax, rax
0x180031a33  jnz     short loc_180031A41
0x180031a35  mov     eax, 8007000Eh
0x180031a3a  mov     ebx, eax
0x180031a3c  jmp     loc_180031BFE
0x180031a41  xor     eax, eax
0x180031a43  lea     rdx, IID_IControlbar
0x180031a4a  mov     [r15], ax
0x180031a4e  mov     r8, rdi
0x180031a51  mov     rax, [r14]
0x180031a54  mov     rcx, r14
0x180031a57  mov     rax, [rax]
0x180031a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a5f  mov     ebx, eax
0x180031a61  test    eax, eax
0x180031a63  js      loc_180031BFE
0x180031a69  mov     rcx, [rdi]
0x180031a6c  lea     rax, [rsi-10h]
0x180031a70  neg     rax
0x180031a73  mov     r9, r13
0x180031a76  sbb     r8, r8
0x180031a79  mov     rdx, [rcx]
0x180031a7c  and     r8, rsi
0x180031a7f  mov     rax, [rdx+18h]
0x180031a83  xor     edx, edx
0x180031a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031a8a  mov     ebx, eax
0x180031a8c  test    eax, eax
0x180031a8e  js      loc_180031BFE
0x180031a94  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180031a9b  mov     edx, 7Ah ; 'z'; lpBitmapName
0x180031aa0  call    cs:__imp_LoadBitmapW
0x180031aa6  mov     rdi, rax
0x180031aa9  mov     esi, 80070000h
0x180031aae  test    rax, rax
0x180031ab1  jnz     short loc_180031ADA
0x180031ab3  call    cs:__imp_GetLastError
0x180031ab9  mov     ebx, eax
0x180031abb  test    eax, eax
0x180031abd  jz      short loc_180031ACC
0x180031abf  jle     short loc_180031AC6
0x180031ac1  movzx   ebx, ax
0x180031ac4  or      ebx, esi
0x180031ac6  test    ebx, ebx
0x180031ac8  jns     short loc_180031AE0
0x180031aca  jmp     short loc_180031AD1
0x180031acc  mov     ebx, 80004005h
0x180031ad1  mov     [rsp+68h+var_48], ebx
0x180031ad5  jmp     loc_180031C02
0x180031ada  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180031ade  jz      short loc_180031AB3
0x180031ae0  mov     rcx, [r13+0]
0x180031ae4  mov     r9d, 10h
0x180031aea  mov     [rsp+68h+var_40], 808000h
0x180031af2  mov     r8, rdi
0x180031af5  mov     [rsp+68h+var_48], r9d
0x180031afa  mov     rax, [rcx]
0x180031afd  lea     edx, [r9-8]
0x180031b01  mov     rax, [rax+18h]
0x180031b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b0a  mov     ebx, eax
0x180031b0c  test    eax, eax
0x180031b0e  js      loc_180031BFE
0x180031b14  lea     rdi, qword_1800B0C50
0x180031b1b  mov     r14d, 400h
0x180031b21  cmp     dword ptr [rdi+4], 0
0x180031b25  jz      loc_180031C1F
0x180031b2b  movaps  xmm1, xmmword ptr [rdi+10h]
0x180031b2f  lea     rdx, [rbp+uID]; unsigned int *
0x180031b33  movaps  xmm0, xmmword ptr [rdi]
0x180031b36  mov     rcx, [rdi+10h]; unsigned __int64
0x180031b3a  movups  [rbp+var_18], xmm1
0x180031b3e  mov     qword ptr [rbp+var_18], r12
0x180031b42  mov     qword ptr [rbp+var_18+8], r15
0x180031b46  movups  [rbp+var_28], xmm0
0x180031b4a  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180031b4f  mov     ebx, eax
0x180031b51  test    eax, eax
0x180031b53  js      loc_180031BFE
0x180031b59  mov     edx, [rbp+uID]; uID
0x180031b5c  mov     r9d, r14d; cchBufferMax
0x180031b5f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180031b66  mov     r8, r12; lpBuffer
0x180031b69  call    cs:__imp_LoadStringW
0x180031b6f  test    eax, eax
0x180031b71  jg      short loc_180031B8C
0x180031b73  call    cs:__imp_GetLastError
0x180031b79  mov     ebx, eax
0x180031b7b  test    eax, eax
0x180031b7d  jz      short loc_180031BF7
0x180031b7f  jle     short loc_180031B86
0x180031b81  movzx   ebx, ax
0x180031b84  or      ebx, esi
0x180031b86  mov     eax, ebx
0x180031b88  test    ebx, ebx
0x180031b8a  js      short loc_180031BFE
0x180031b8c  mov     rcx, [rdi+18h]; unsigned __int64
0x180031b90  lea     rdx, [rbp+uID]; unsigned int *
0x180031b94  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180031b99  mov     ebx, eax
0x180031b9b  test    eax, eax
0x180031b9d  js      short loc_180031BFE
0x180031b9f  mov     edx, [rbp+uID]; uID
0x180031ba2  mov     r9d, r14d; cchBufferMax
0x180031ba5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180031bac  mov     r8, r15; lpBuffer
0x180031baf  call    cs:__imp_LoadStringW
0x180031bb5  test    eax, eax
0x180031bb7  jg      short loc_180031BD2
0x180031bb9  call    cs:__imp_GetLastError
0x180031bbf  mov     ebx, eax
0x180031bc1  test    eax, eax
0x180031bc3  jz      short loc_180031BF7
0x180031bc5  jle     short loc_180031BCC
0x180031bc7  movzx   ebx, ax
0x180031bca  or      ebx, esi
0x180031bcc  mov     eax, ebx
0x180031bce  test    ebx, ebx
0x180031bd0  js      short loc_180031BFE
0x180031bd2  mov     rcx, [r13+0]
0x180031bd6  lea     r8, [rbp+var_28]
0x180031bda  xor     edx, edx
0x180031bdc  mov     rax, [rcx]
0x180031bdf  mov     rax, [rax+28h]
0x180031be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031be8  mov     ebx, eax
0x180031bea  test    eax, eax
0x180031bec  js      short loc_180031BFE
0x180031bee  add     rdi, 20h ; ' '
0x180031bf2  jmp     loc_180031B21
0x180031bf7  mov     ebx, 80004005h
0x180031bfc  mov     eax, ebx
0x180031bfe  mov     [rsp+68h+var_48], eax
0x180031c02  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180031c09  xor     r8d, r8d; int
0x180031c0c  lea     rdx, aWdccomponentSe; "WdcComponent::SetControlbar"
0x180031c13  lea     rcx, aBaseDiagnosisP_23; "base\\diagnosis\\pdui\\perfmon\\mmc\\co"...
0x180031c1a  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180031c1f  mov     rcx, r12; void *
0x180031c22  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180031c27  test    r15, r15
0x180031c2a  jz      short loc_180031C34
0x180031c2c  mov     rcx, r15; void *
0x180031c2f  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180031c34  mov     eax, ebx
0x180031c36  add     rsp, 68h
0x180031c3a  pop     r15
0x180031c3c  pop     r14
0x180031c3e  pop     r13
0x180031c40  pop     r12
0x180031c42  pop     rdi
0x180031c43  pop     rsi
0x180031c44  pop     rbx
0x180031c45  pop     rbp
0x180031c46  retn
```

# WpnDatabaseHelpers::FilterNotificationCollectionByType(INotificationCollection *,ushort const *,INotificationCollection * *)

- ea: `0x180029b68`
- end: `0x180029e2f`
- name: `?FilterNotificationCollectionByType@WpnDatabaseHelpers@@YAJPEAUINotificationCollection@@PEBGPEAPEAU2@@Z`
- size: `711`
- prototype: `__int64 __fastcall(WpnDatabaseHelpers *__hidden this, struct INotificationCollection *, const unsigned __int16 *, struct INotificationCollection **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180040454`

## callees

- `0x180004e38`
- `0x180011618`
- `0x180029750`
- `0x180029b68`
- `0x180029f44`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029cc3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180029cc3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029da6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029d3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029da6`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WpnDatabaseHelpers::FilterNotificationCollectionByType(
        WpnDatabaseHelpers *this,
        const WCHAR *a2,
        unsigned __int16 *a3,
        struct INotificationCollection **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  unsigned int v10; // esi
  NotificationCollection *v11; // rdi
  __int64 (__fastcall *v12)(WpnDatabaseHelpers *, _QWORD, struct IWpnNotification **); // rbx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  const WCHAR *v16; // r8
  __int64 v17; // rdx
  const WCHAR *v18; // rcx
  struct IWpnNotification *v19; // rcx
  int v20; // eax
  struct IWpnNotification *v21; // rcx
  struct IWpnNotification *v22; // rcx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  NotificationCollection *v24; // [rsp+30h] [rbp-20h] BYREF
  LPCWCH lpString1; // [rsp+38h] [rbp-18h] BYREF
  __int64 v26; // [rsp+40h] [rbp-10h]
  __int64 v27; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  unsigned int v29; // [rsp+90h] [rbp+40h] BYREF
  struct IWpnNotification *v30; // [rsp+A8h] [rbp+58h] BYREF

  v29 = 0;
  v7 = (*(__int64 (__fastcall **)(WpnDatabaseHelpers *, unsigned int *, unsigned __int16 *, struct INotificationCollection **))(*(_QWORD *)this + 32LL))(
         this,
         &v29,
         a3,
         a4);
  if ( (v7 & 0x80000000) != 0 )
  {
    v8 = 426;
    goto LABEL_4;
  }
  if ( !v29 )
  {
    v7 = -2147418113;
    v8 = 427;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
      (const char *)v7,
      bIgnoreCase);
    return v7;
  }
  Microsoft::WRL::Details::Make<NotificationCollection,>(&v24);
  v10 = 0;
  v11 = v24;
  while ( 1 )
  {
    if ( v10 >= v29 )
    {
      *(_QWORD *)a3 = ((unsigned __int64)v11 + 32) & -(__int64)(v11 != 0);
      return 0;
    }
    v30 = 0;
    v12 = *(__int64 (__fastcall **)(WpnDatabaseHelpers *, _QWORD, struct IWpnNotification **))(*(_QWORD *)this + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v13 = v12(this, v10, &v30);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B3,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
        (const char *)(unsigned int)v13,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      return v7;
    }
    lpString1 = 0;
    v26 = 0;
    v27 = 0;
    v14 = *(_QWORD *)v30;
    v26 = -1;
    v27 = -1;
    v15 = (*(__int64 (__fastcall **)(struct IWpnNotification *, LPCWCH *))(v14 + 40))(v30, &lpString1);
    v7 = v15;
    if ( v15 < 0 )
      break;
    v16 = a2;
    if ( !a2 )
      v16 = &word_180124798;
    v17 = v26;
    if ( v26 == -1 )
    {
      if ( lpString1 )
      {
        do
          ++v17;
        while ( lpString1[v17] );
      }
      else
      {
        LODWORD(v17) = 0;
      }
    }
    v18 = &word_180124798;
    if ( lpString1 )
      v18 = lpString1;
    if ( CompareStringOrdinal(v18, v17, v16, -(a2 != 0), 0) == 2 )
    {
      v20 = NotificationCollection::add_Notification(v11, v30);
      v7 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCase);
        if ( lpString1 )
        {
          CoTaskMemFree((LPVOID)lpString1);
          lpString1 = 0;
        }
        v26 = 0;
        v27 = 0;
        v21 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(struct IWpnNotification *))(*(_QWORD *)v21 + 16LL))(v21);
        }
        if ( v11 )
          (*(void (__fastcall **)(NotificationCollection *))(*(_QWORD *)v11 + 16LL))(v11);
        return v7;
      }
    }
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    v26 = 0;
    v27 = 0;
    v19 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(struct IWpnNotification *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    ++v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B5,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\database\\databasehelpers.cpp",
    (const char *)(unsigned int)v15,
    bIgnoreCase);
  if ( lpString1 )
  {
    CoTaskMemFree((LPVOID)lpString1);
    lpString1 = 0;
  }
  v26 = 0;
  v27 = 0;
  v22 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(struct IWpnNotification *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  if ( v11 )
    (*(void (__fastcall **)(NotificationCollection *))(*(_QWORD *)v11 + 16LL))(v11);
  return v7;
}

```

## disassembly

```asm
0x180029b68  mov     [rsp-38h+arg_8], rbx
0x180029b6d  push    rbp
0x180029b6e  push    rsi
0x180029b6f  push    rdi
0x180029b70  push    r12
0x180029b72  push    r13
0x180029b74  push    r14
0x180029b76  push    r15
0x180029b78  mov     rbp, rsp
0x180029b7b  sub     rsp, 50h
0x180029b7f  mov     r12, r8
0x180029b82  mov     r15, rdx
0x180029b85  mov     r14, rcx
0x180029b88  xor     r13d, r13d
0x180029b8b  mov     [rbp+arg_0], r13d
0x180029b8f  mov     rax, [rcx]
0x180029b92  lea     rdx, [rbp+arg_0]
0x180029b96  mov     rax, [rax+20h]
0x180029b9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b9f  mov     ebx, eax
0x180029ba1  test    eax, eax
0x180029ba3  js      loc_180029DEC
0x180029ba9  cmp     [rbp+arg_0], r13d
0x180029bad  ja      short loc_180029BFB
0x180029baf  mov     ebx, 8000FFFFh
0x180029bb4  mov     edx, 1ABh; void *
0x180029bb9  mov     r9d, ebx; char *
0x180029bbc  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029bc3  mov     rcx, [rbp+38h]; this
0x180029bc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029bcc  mov     eax, ebx
0x180029bce  jmp     short loc_180029BE3
0x180029bd0  lea     rcx, [rdi+20h]
0x180029bd4  neg     rdi
0x180029bd7  sbb     rax, rax
0x180029bda  and     rax, rcx
0x180029bdd  mov     [r12], rax
0x180029be1  xor     eax, eax
0x180029be3  mov     rbx, [rsp+50h+arg_8]
0x180029beb  add     rsp, 50h
0x180029bef  pop     r15
0x180029bf1  pop     r14
0x180029bf3  pop     r13
0x180029bf5  pop     r12
0x180029bf7  pop     rdi
0x180029bf8  pop     rsi
0x180029bf9  pop     rbp
0x180029bfa  retn
0x180029bfb  lea     rcx, [rbp+var_20]
0x180029bff  call    ??$Make@VNotificationCollection@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VNotificationCollection@@@12@XZ; Microsoft::WRL::Details::Make<NotificationCollection,>(void)
0x180029c04  nop
0x180029c05  mov     esi, r13d
0x180029c08  mov     rdi, [rbp+var_20]
0x180029c0c  cmp     esi, [rbp+arg_0]
0x180029c0f  jnb     short loc_180029BD0
0x180029c11  mov     [rbp+arg_18], r13
0x180029c15  mov     rax, [r14]
0x180029c18  mov     rbx, [rax+18h]
0x180029c1c  lea     rcx, [rbp+arg_18]
0x180029c20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029c25  lea     r8, [rbp+arg_18]
0x180029c29  mov     edx, esi
0x180029c2b  mov     rcx, r14
0x180029c2e  mov     rax, rbx
0x180029c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c36  mov     ebx, eax
0x180029c38  test    eax, eax
0x180029c3a  js      loc_180029DFE
0x180029c40  mov     [rbp+lpString1], r13
0x180029c44  mov     [rbp+var_10], r13
0x180029c48  mov     [rbp+var_8], r13
0x180029c4c  mov     rcx, [rbp+arg_18]
0x180029c50  mov     rax, [rcx]
0x180029c53  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180029c57  mov     [rbp+var_10], rdx
0x180029c5b  mov     [rbp+var_8], rdx
0x180029c5f  lea     rdx, [rbp+lpString1]
0x180029c63  mov     rax, [rax+28h]
0x180029c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c6c  mov     ebx, eax
0x180029c6e  test    eax, eax
0x180029c70  js      loc_180029D84
0x180029c76  mov     rax, r15
0x180029c79  neg     rax
0x180029c7c  sbb     r9d, r9d; cchCount2
0x180029c7f  mov     r8, r15
0x180029c82  test    r15, r15
0x180029c85  lea     rbx, word_180124798
0x180029c8c  cmovz   r8, rbx; lpString2
0x180029c90  mov     rdx, [rbp+var_10]
0x180029c94  mov     rax, [rbp+lpString1]
0x180029c98  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180029c9c  jnz     short loc_180029CB4
0x180029c9e  test    rax, rax
0x180029ca1  jz      loc_180029DF6
0x180029ca7  or      rdx, rdx
0x180029caa  inc     rdx; cchCount1
0x180029cad  cmp     [rax+rdx*2], r13w
0x180029cb2  jnz     short loc_180029CAA
0x180029cb4  mov     rcx, rbx
0x180029cb7  test    rax, rax
0x180029cba  cmovnz  rcx, rax; lpString1
0x180029cbe  mov     [rsp+50h+bIgnoreCase], r13d; int
0x180029cc3  call    cs:__imp_CompareStringOrdinal
0x180029cc9  cmp     eax, 2
0x180029ccc  jz      short loc_180029D0A
0x180029cce  mov     rcx, [rbp+lpString1]; pv
0x180029cd2  test    rcx, rcx
0x180029cd5  jz      short loc_180029CE1
0x180029cd7  call    cs:__imp_CoTaskMemFree
0x180029cdd  mov     [rbp+lpString1], r13
0x180029ce1  mov     [rbp+var_10], r13
0x180029ce5  mov     [rbp+var_8], r13
0x180029ce9  mov     rcx, [rbp+arg_18]
0x180029ced  test    rcx, rcx
0x180029cf0  jz      short loc_180029D03
0x180029cf2  mov     [rbp+arg_18], r13
0x180029cf6  mov     rax, [rcx]
0x180029cf9  mov     rax, [rax+10h]
0x180029cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d02  nop
0x180029d03  inc     esi
0x180029d05  jmp     loc_180029C0C
0x180029d0a  mov     rdx, [rbp+arg_18]; struct IWpnNotification *
0x180029d0e  mov     rcx, rdi; this
0x180029d11  call    ?add_Notification@NotificationCollection@@QEAAJPEAUIWpnNotification@@@Z; NotificationCollection::add_Notification(IWpnNotification *)
0x180029d16  mov     ebx, eax
0x180029d18  test    eax, eax
0x180029d1a  jns     short loc_180029CCE
0x180029d1c  mov     rcx, [rbp+38h]; this
0x180029d20  mov     r9d, eax; char *
0x180029d23  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029d2a  mov     edx, 1B9h; void *
0x180029d2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d34  nop
0x180029d35  mov     rcx, [rbp+lpString1]; pv
0x180029d39  test    rcx, rcx
0x180029d3c  jz      short loc_180029D48
0x180029d3e  call    cs:__imp_CoTaskMemFree
0x180029d44  mov     [rbp+lpString1], r13
0x180029d48  mov     [rbp+var_10], r13
0x180029d4c  mov     [rbp+var_8], r13
0x180029d50  mov     rcx, [rbp+arg_18]
0x180029d54  test    rcx, rcx
0x180029d57  jz      short loc_180029D6A
0x180029d59  mov     [rbp+arg_18], r13
0x180029d5d  mov     rax, [rcx]
0x180029d60  mov     rax, [rax+10h]
0x180029d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d69  nop
0x180029d6a  test    rdi, rdi
0x180029d6d  jz      short loc_180029D7F
0x180029d6f  mov     rax, [rdi]
0x180029d72  mov     rcx, rdi
0x180029d75  mov     rax, [rax+10h]
0x180029d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d7e  nop
0x180029d7f  jmp     loc_180029BCC
0x180029d84  mov     rcx, [rbp+38h]; this
0x180029d88  mov     r9d, ebx; char *
0x180029d8b  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029d92  mov     edx, 1B5h; void *
0x180029d97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d9c  nop
0x180029d9d  mov     rcx, [rbp+lpString1]; pv
0x180029da1  test    rcx, rcx
0x180029da4  jz      short loc_180029DB0
0x180029da6  call    cs:__imp_CoTaskMemFree
0x180029dac  mov     [rbp+lpString1], r13
0x180029db0  mov     [rbp+var_10], r13
0x180029db4  mov     [rbp+var_8], r13
0x180029db8  mov     rcx, [rbp+arg_18]
0x180029dbc  test    rcx, rcx
0x180029dbf  jz      short loc_180029DD2
0x180029dc1  mov     [rbp+arg_18], r13
0x180029dc5  mov     rax, [rcx]
0x180029dc8  mov     rax, [rax+10h]
0x180029dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dd1  nop
0x180029dd2  test    rdi, rdi
0x180029dd5  jz      short loc_180029DE7
0x180029dd7  mov     rax, [rdi]
0x180029dda  mov     rcx, rdi
0x180029ddd  mov     rax, [rax+10h]
0x180029de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de6  nop
0x180029de7  jmp     loc_180029BCC
0x180029dec  mov     edx, 1AAh
0x180029df1  jmp     loc_180029BB9
0x180029df6  mov     rdx, r13
0x180029df9  jmp     loc_180029CB4
0x180029dfe  mov     rcx, [rbp+38h]; this
0x180029e02  mov     r9d, ebx; char *
0x180029e05  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180029e0c  mov     edx, 1B3h; void *
0x180029e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e16  nop
0x180029e17  lea     rcx, [rbp+arg_18]
0x180029e1b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029e20  nop
0x180029e21  lea     rcx, [rbp+var_20]
0x180029e25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029e2a  jmp     loc_180029BCC
```

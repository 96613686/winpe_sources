# pExecuteWmiQuery(IEnumWbemClassObject * *,ushort const *)

- ea: `0x180039f70`
- end: `0x18003a41c`
- name: `?pExecuteWmiQuery@@YAJPEAPEAUIEnumWbemClassObject@@PEBG@Z`
- size: `1196`
- prototype: `int(struct IEnumWbemClassObject **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036fd0`

## callees

- `0x1800066cc`
- `0x180039f70`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a045`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a16e`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a045`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a16e`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003a1b6`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18003a1b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180039ffe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a093`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a141`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a165`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a229`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a24d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a2a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a32f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a36a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a3b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a406`
- `OLEAUT32!__imp_SysFreeString` at `0x180039ffe`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a093`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a0b6`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a141`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a165`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a229`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a24d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a2a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a32f`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a36a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a3b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a406`
- `KERNEL32!MultiByteToWideChar` at `0x18003a1a8`
- `KERNEL32!MultiByteToWideChar` at `0x18003a1de`
- `KERNEL32!MultiByteToWideChar` at `0x18003a1a8`
- `KERNEL32!MultiByteToWideChar` at `0x18003a1de`
- `ole32!CoSetProxyBlanket` at `0x18003a11d`
- `ole32!CoSetProxyBlanket` at `0x18003a30a`
- `ole32!CoSetProxyBlanket` at `0x18003a11d`
- `ole32!CoSetProxyBlanket` at `0x18003a30a`
- `ole32!CoCreateInstance` at `0x180039fda`
- `ole32!CoCreateInstance` at `0x180039fda`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 __fastcall pExecuteWmiQuery(IUnknown **a1, const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  LPVOID v6; // r14
  __int64 v7; // r15
  BSTR v8; // rax
  OLECHAR *v9; // rbx
  int v10; // r14d
  OLECHAR *v11; // rbx
  IUnknown *v12; // r15
  struct IUnknownVtbl *lpVtbl; // r13
  int v14; // r14d
  WCHAR *v15; // rax
  OLECHAR *v16; // rdi
  HRESULT v17; // edi
  IUnknown *pProxy; // [rsp+50h] [rbp-19h] BYREF
  __int64 v19; // [rsp+58h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-9h] BYREF
  OLECHAR *v21; // [rsp+68h] [rbp-1h]
  __int64 v22; // [rsp+70h] [rbp+7h]

  v22 = -2;
  ppv = 0;
  pProxy = 0;
  v21 = 0;
  v19 = 0;
  if ( !a1 || !a2 )
  {
    SysFreeString(0);
    return 2147942487LL;
  }
  v4 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  if ( v4 < 0 )
  {
    SysFreeString(0);
LABEL_5:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v4;
  }
  v6 = ppv;
  v7 = *(_QWORD *)ppv;
  v8 = SysAllocString(L"ROOT\\CIMV2");
  v9 = v8;
  if ( !v8 )
    goto LABEL_56;
  v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(v7 + 24))(
          v6,
          v8,
          0,
          0,
          0,
          0,
          0,
          0,
          &pProxy);
  SysFreeString(v9);
  if ( v10 < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(0);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
LABEL_14:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v10;
  }
  v4 = CoSetProxyBlanket(
         pProxy,
         0xFFFFFFFF,
         0xFFFFFFFF,
         (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
         0,
         3u,
         (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
         0x800u);
  if ( v4 < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(0);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_5;
  }
  SysFreeString(0);
  v11 = SysAllocString(a2);
  v21 = v11;
  if ( !v11 )
LABEL_56:
    ATL::AtlThrowImpl(-2147024882);
  v12 = pProxy;
  lpVtbl = pProxy->lpVtbl;
  v14 = MultiByteToWideChar(3u, 0, "WQL", -1, 0, 0);
  v15 = SysAllocStringLen(0, v14 - 1);
  v16 = v15;
  if ( v15 && MultiByteToWideChar(3u, 0, "WQL", -1, v15, v14) != v14 )
  {
    SysFreeString(v16);
    goto LABEL_56;
  }
  if ( !v16 )
    goto LABEL_56;
  v10 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))lpVtbl[6].Release)(
          v12,
          v16,
          v11,
          48,
          0,
          &v19);
  SysFreeString(v16);
  if ( v10 < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(v11);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_14;
  }
  v17 = (**(__int64 (__fastcall ***)(__int64, GUID *, IUnknown **))v19)(v19, &IID_IEnumWbemClassObject, a1);
  if ( v17 < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(v11);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
LABEL_38:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return (unsigned int)v17;
  }
  v17 = CoSetProxyBlanket(
          *a1,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x800u);
  if ( v17 < 0 )
  {
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    SysFreeString(v11);
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_38;
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  SysFreeString(v11);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x180039f70  push    rbp
0x180039f72  push    rbx
0x180039f73  push    rsi
0x180039f74  push    rdi
0x180039f75  push    r12
0x180039f77  push    r13
0x180039f79  push    r14
0x180039f7b  push    r15
0x180039f7d  lea     rbp, [rsp-1Fh]
0x180039f82  sub     rsp, 88h
0x180039f89  mov     [rbp+57h+var_50], 0FFFFFFFFFFFFFFFEh
0x180039f91  mov     rdi, rdx
0x180039f94  mov     rsi, rcx
0x180039f97  xor     r12d, r12d
0x180039f9a  mov     [rbp+57h+var_60], r12
0x180039f9e  mov     [rbp+57h+pProxy], r12
0x180039fa2  mov     [rbp+57h+var_58], r12
0x180039fa6  mov     [rbp+57h+var_68], r12
0x180039faa  test    rcx, rcx
0x180039fad  jz      loc_18003A3A0
0x180039fb3  test    rdx, rdx
0x180039fb6  jz      loc_18003A3A0
0x180039fbc  lea     rax, [rbp+57h+var_60]
0x180039fc0  mov     [rsp+0C0h+ppv], rax; ppv
0x180039fc5  lea     r9, IID_IWbemLocator; riid
0x180039fcc  xor     edx, edx; pUnkOuter
0x180039fce  lea     r8d, [r12+1]; dwClsContext
0x180039fd3  lea     rcx, CLSID_WbemLocator; rclsid
0x180039fda  call    cs:__imp_CoCreateInstance
0x180039fe0  mov     ebx, eax
0x180039fe2  test    eax, eax
0x180039fe4  jns     short loc_18003A037
0x180039fe6  mov     rcx, [rbp+57h+var_68]
0x180039fea  test    rcx, rcx
0x180039fed  jz      short loc_180039FFC
0x180039fef  mov     rdx, [rcx]
0x180039ff2  mov     rax, [rdx+10h]
0x180039ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039ffb  nop
0x180039ffc  xor     ecx, ecx; bstrString
0x180039ffe  call    cs:__imp_SysFreeString
0x18003a004  nop
0x18003a005  mov     rcx, [rbp+57h+pProxy]
0x18003a009  test    rcx, rcx
0x18003a00c  jz      short loc_18003A01B
0x18003a00e  mov     rax, [rcx]
0x18003a011  mov     rax, [rax+10h]
0x18003a015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a01a  nop
0x18003a01b  mov     rcx, [rbp+57h+var_60]
0x18003a01f  test    rcx, rcx
0x18003a022  jz      short loc_18003A030
0x18003a024  mov     rax, [rcx]
0x18003a027  mov     rax, [rax+10h]
0x18003a02b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a030  mov     eax, ebx
0x18003a032  jmp     loc_18003A3EF
0x18003a037  mov     r14, [rbp+57h+var_60]
0x18003a03b  mov     r15, [r14]
0x18003a03e  lea     rcx, psz; "ROOT\\CIMV2"
0x18003a045  call    cs:__imp_SysAllocString
0x18003a04b  mov     rbx, rax
0x18003a04e  mov     [rbp+57h+arg_0], rax
0x18003a052  test    rax, rax
0x18003a055  jz      loc_18003A411
0x18003a05b  lea     rax, [rbp+57h+pProxy]
0x18003a05f  mov     [rsp+0C0h+var_80], rax
0x18003a064  mov     qword ptr [rsp+0C0h+dwCapabilities], r12
0x18003a069  mov     [rsp+0C0h+pAuthInfo], r12
0x18003a06e  mov     [rsp+0C0h+dwImpLevel], r12d
0x18003a073  mov     [rsp+0C0h+ppv], r12
0x18003a078  xor     r9d, r9d
0x18003a07b  xor     r8d, r8d
0x18003a07e  mov     rdx, rbx
0x18003a081  mov     rcx, r14
0x18003a084  mov     rax, [r15+18h]
0x18003a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a08d  mov     r14d, eax
0x18003a090  mov     rcx, rbx; bstrString
0x18003a093  call    cs:__imp_SysFreeString
0x18003a099  test    r14d, r14d
0x18003a09c  jns     short loc_18003A0F0
0x18003a09e  mov     rcx, [rbp+57h+var_68]
0x18003a0a2  test    rcx, rcx
0x18003a0a5  jz      short loc_18003A0B4
0x18003a0a7  mov     rax, [rcx]
0x18003a0aa  mov     rax, [rax+10h]
0x18003a0ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0b3  nop
0x18003a0b4  xor     ecx, ecx; bstrString
0x18003a0b6  call    cs:__imp_SysFreeString
0x18003a0bc  nop
0x18003a0bd  mov     rcx, [rbp+57h+pProxy]
0x18003a0c1  test    rcx, rcx
0x18003a0c4  jz      short loc_18003A0D3
0x18003a0c6  mov     rax, [rcx]
0x18003a0c9  mov     rax, [rax+10h]
0x18003a0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0d2  nop
0x18003a0d3  mov     rcx, [rbp+57h+var_60]
0x18003a0d7  test    rcx, rcx
0x18003a0da  jz      short loc_18003A0E8
0x18003a0dc  mov     rax, [rcx]
0x18003a0df  mov     rax, [rax+10h]
0x18003a0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a0e8  mov     eax, r14d
0x18003a0eb  jmp     loc_18003A3EF
0x18003a0f0  mov     [rsp+0C0h+dwCapabilities], 800h; dwCapabilities
0x18003a0f8  or      r14, 0FFFFFFFFFFFFFFFFh
0x18003a0fc  mov     [rsp+0C0h+pAuthInfo], r14; pAuthInfo
0x18003a101  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x18003a109  mov     dword ptr [rsp+0C0h+ppv], r12d; dwAuthnLevel
0x18003a10e  mov     r9, r14; pServerPrincName
0x18003a111  or      eax, 0FFFFFFFFh
0x18003a114  mov     r8d, eax; dwAuthzSvc
0x18003a117  mov     edx, eax; dwAuthnSvc
0x18003a119  mov     rcx, [rbp+57h+pProxy]; pProxy
0x18003a11d  call    cs:__imp_CoSetProxyBlanket
0x18003a123  mov     ebx, eax
0x18003a125  test    eax, eax
0x18003a127  jns     short loc_18003A163
0x18003a129  mov     rcx, [rbp+57h+var_68]
0x18003a12d  test    rcx, rcx
0x18003a130  jz      short loc_18003A13F
0x18003a132  mov     rdx, [rcx]
0x18003a135  mov     rax, [rdx+10h]
0x18003a139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a13e  nop
0x18003a13f  xor     ecx, ecx; bstrString
0x18003a141  call    cs:__imp_SysFreeString
0x18003a147  nop
0x18003a148  mov     rcx, [rbp+57h+pProxy]
0x18003a14c  test    rcx, rcx
0x18003a14f  jz      short loc_18003A15E
0x18003a151  mov     rax, [rcx]
0x18003a154  mov     rax, [rax+10h]
0x18003a158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a15d  nop
0x18003a15e  jmp     loc_18003A01B
0x18003a163  xor     ecx, ecx; bstrString
0x18003a165  call    cs:__imp_SysFreeString
0x18003a16b  mov     rcx, rdi; psz
0x18003a16e  call    cs:__imp_SysAllocString
0x18003a174  mov     rbx, rax
0x18003a177  mov     [rbp+57h+var_58], rax
0x18003a17b  test    rax, rax
0x18003a17e  jz      loc_18003A411
0x18003a184  mov     r15, [rbp+57h+pProxy]
0x18003a188  mov     r13, [r15]
0x18003a18b  mov     [rbp+57h+arg_0], r12
0x18003a18f  mov     [rsp+0C0h+dwImpLevel], r12d; cchWideChar
0x18003a194  mov     [rsp+0C0h+ppv], r12; lpWideCharStr
0x18003a199  mov     r9d, r14d; cbMultiByte
0x18003a19c  lea     r8, MultiByteStr; "WQL"
0x18003a1a3  xor     edx, edx; dwFlags
0x18003a1a5  lea     ecx, [rdx+3]; CodePage
0x18003a1a8  call    cs:__imp_MultiByteToWideChar
0x18003a1ae  mov     r14d, eax
0x18003a1b1  lea     edx, [rax-1]; ui
0x18003a1b4  xor     ecx, ecx; strIn
0x18003a1b6  call    cs:__imp_SysAllocStringLen
0x18003a1bc  mov     rdi, rax
0x18003a1bf  test    rax, rax
0x18003a1c2  jz      short loc_18003A1ED
0x18003a1c4  mov     [rsp+0C0h+dwImpLevel], r14d; cchWideChar
0x18003a1c9  mov     [rsp+0C0h+ppv], rax; lpWideCharStr
0x18003a1ce  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18003a1d2  lea     r8, MultiByteStr; "WQL"
0x18003a1d9  xor     edx, edx; dwFlags
0x18003a1db  lea     ecx, [rdx+3]; CodePage
0x18003a1de  call    cs:__imp_MultiByteToWideChar
0x18003a1e4  cmp     eax, r14d
0x18003a1e7  jnz     loc_18003A403
0x18003a1ed  mov     [rbp+57h+arg_0], rdi
0x18003a1f1  test    rdi, rdi
0x18003a1f4  jz      loc_18003A411
0x18003a1fa  lea     rax, [rbp+57h+var_68]
0x18003a1fe  mov     qword ptr [rsp+0C0h+dwImpLevel], rax
0x18003a203  mov     [rsp+0C0h+ppv], r12
0x18003a208  mov     r9d, 30h ; '0'
0x18003a20e  mov     r8, rbx
0x18003a211  mov     rdx, rdi
0x18003a214  mov     rcx, r15
0x18003a217  mov     rax, [r13+0A0h]
0x18003a21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a223  mov     r14d, eax
0x18003a226  mov     rcx, rdi; bstrString
0x18003a229  call    cs:__imp_SysFreeString
0x18003a22f  test    r14d, r14d
0x18003a232  jns     short loc_18003A26F
0x18003a234  mov     rcx, [rbp+57h+var_68]
0x18003a238  test    rcx, rcx
0x18003a23b  jz      short loc_18003A24A
0x18003a23d  mov     rax, [rcx]
0x18003a240  mov     rax, [rax+10h]
0x18003a244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a249  nop
0x18003a24a  mov     rcx, rbx; bstrString
0x18003a24d  call    cs:__imp_SysFreeString
0x18003a253  nop
0x18003a254  mov     rcx, [rbp+57h+pProxy]
0x18003a258  test    rcx, rcx
0x18003a25b  jz      short loc_18003A26A
0x18003a25d  mov     rax, [rcx]
0x18003a260  mov     rax, [rax+10h]
0x18003a264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a269  nop
0x18003a26a  jmp     loc_18003A0D3
0x18003a26f  mov     rcx, [rbp+57h+var_68]
0x18003a273  mov     rax, [rcx]
0x18003a276  mov     r8, rsi
0x18003a279  lea     rdx, IID_IEnumWbemClassObject
0x18003a280  mov     rax, [rax]
0x18003a283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a288  mov     edi, eax
0x18003a28a  test    eax, eax
0x18003a28c  jns     short loc_18003A2E0
0x18003a28e  mov     rcx, [rbp+57h+var_68]
0x18003a292  test    rcx, rcx
0x18003a295  jz      short loc_18003A2A4
0x18003a297  mov     rdx, [rcx]
0x18003a29a  mov     rax, [rdx+10h]
0x18003a29e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2a3  nop
0x18003a2a4  mov     rcx, rbx; bstrString
0x18003a2a7  call    cs:__imp_SysFreeString
0x18003a2ad  nop
0x18003a2ae  mov     rcx, [rbp+57h+pProxy]
0x18003a2b2  test    rcx, rcx
0x18003a2b5  jz      short loc_18003A2C4
0x18003a2b7  mov     rax, [rcx]
0x18003a2ba  mov     rax, [rax+10h]
0x18003a2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2c3  nop
0x18003a2c4  mov     rcx, [rbp+57h+var_60]
0x18003a2c8  test    rcx, rcx
0x18003a2cb  jz      short loc_18003A2D9
0x18003a2cd  mov     rax, [rcx]
0x18003a2d0  mov     rax, [rax+10h]
0x18003a2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a2d9  mov     eax, edi
0x18003a2db  jmp     loc_18003A3EF
0x18003a2e0  mov     [rsp+0C0h+dwCapabilities], 800h; dwCapabilities
0x18003a2e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003a2ec  mov     [rsp+0C0h+pAuthInfo], rax; pAuthInfo
0x18003a2f1  mov     [rsp+0C0h+dwImpLevel], 3; dwImpLevel
0x18003a2f9  mov     dword ptr [rsp+0C0h+ppv], r12d; dwAuthnLevel
0x18003a2fe  mov     r9, rax; pServerPrincName
0x18003a301  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18003a304  mov     r8d, edx; dwAuthzSvc
0x18003a307  mov     rcx, [rsi]; pProxy
0x18003a30a  call    cs:__imp_CoSetProxyBlanket
0x18003a310  mov     edi, eax
0x18003a312  test    eax, eax
0x18003a314  jns     short loc_18003A351
0x18003a316  mov     rcx, [rbp+57h+var_68]
0x18003a31a  test    rcx, rcx
0x18003a31d  jz      short loc_18003A32C
0x18003a31f  mov     rdx, [rcx]
0x18003a322  mov     rax, [rdx+10h]
0x18003a326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a32b  nop
0x18003a32c  mov     rcx, rbx; bstrString
0x18003a32f  call    cs:__imp_SysFreeString
0x18003a335  nop
0x18003a336  mov     rcx, [rbp+57h+pProxy]
0x18003a33a  test    rcx, rcx
0x18003a33d  jz      short loc_18003A34C
0x18003a33f  mov     rax, [rcx]
0x18003a342  mov     rax, [rax+10h]
0x18003a346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a34b  nop
0x18003a34c  jmp     loc_18003A2C4
0x18003a351  mov     rcx, [rbp+57h+var_68]
0x18003a355  test    rcx, rcx
0x18003a358  jz      short loc_18003A367
0x18003a35a  mov     rax, [rcx]
0x18003a35d  mov     rax, [rax+10h]
0x18003a361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a366  nop
0x18003a367  mov     rcx, rbx; bstrString
0x18003a36a  call    cs:__imp_SysFreeString
0x18003a370  nop
0x18003a371  mov     rcx, [rbp+57h+pProxy]
0x18003a375  test    rcx, rcx
0x18003a378  jz      short loc_18003A387
0x18003a37a  mov     rax, [rcx]
0x18003a37d  mov     rax, [rax+10h]
0x18003a381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a386  nop
0x18003a387  mov     rcx, [rbp+57h+var_60]
0x18003a38b  test    rcx, rcx
0x18003a38e  jz      short loc_18003A39C
0x18003a390  mov     rax, [rcx]
0x18003a393  mov     rax, [rax+10h]
0x18003a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a39c  xor     eax, eax
0x18003a39e  jmp     short loc_18003A3EF
0x18003a3a0  mov     rcx, [rbp+57h+var_68]
0x18003a3a4  test    rcx, rcx
  ... truncated ...
```

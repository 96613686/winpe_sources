# CUrlDownload::GetBrowser(void)

- ea: `0x180006c60`
- end: `0x180006ede`
- name: `?GetBrowser@CUrlDownload@@IEAAJXZ`
- size: `638`
- prototype: `__int64 __fastcall(CUrlDownload *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800062d0`

## callees

- `0x180006c60`
- `0x18002a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180006cb2`
- `ole32!CoCreateInstance` at `0x180006cb2`

## pseudocode

```c
__int64 __fastcall CUrlDownload::GetBrowser(CUrlDownload *this)
{
  _DWORD *v1; // r15
  HRESULT Instance; // ebx
  _QWORD *v5; // rsi
  __int64 (__fastcall ***v6)(_QWORD, GUID *, char *); // rcx
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  BOOL v8; // r14d
  int v9; // r14d
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  _QWORD v11[4]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF
  __int64 v13; // [rsp+98h] [rbp+38h] BYREF

  v1 = (_DWORD *)((char *)this + 144);
  if ( *((_DWORD *)this + 36) )
    return 0;
  Instance = 0;
  v5 = (_QWORD *)((char *)this + 112);
  if ( !*((_QWORD *)this + 14) )
  {
    Instance = CoCreateInstance(&CLSID_HTMLDocument, 0, 3u, &IID_IHTMLDocument2, (LPVOID *)this + 14);
    if ( Instance >= 0 )
    {
      v6 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v5;
      v13 = 0;
      Instance = (**v6)(v6, &IID_IOleObject, (char *)&v13);
      if ( Instance >= 0 )
      {
        (*(void (__fastcall **)(__int64, CUrlDownload *))(*(_QWORD *)v13 + 24LL))(v13, this);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v5)(
                     *v5,
                     &IID_IPersistMoniker,
                     (char *)this + 104);
        if ( Instance >= 0 )
          Instance = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v5)(
                       *v5,
                       &IID_IOleCommandTarget,
                       (char *)this + 120);
      }
    }
  }
  v12 = 0;
  if ( Instance < 0
    || (*(int (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 10) + 32LL))(*((_QWORD *)this + 10), &v12) < 0
    || !v12 )
  {
    goto LABEL_15;
  }
  v7 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v5;
  v8 = 0;
  v13 = 0;
  if ( (**v7)(v7, &IID_IOleCommandTarget, &v13) >= 0 && v13 )
  {
    v11[2] = 0;
    v11[0] = 13;
    v11[1] = v12;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, _QWORD, _QWORD *, _QWORD))(*(_QWORD *)v13 + 32LL))(
           v13,
           CGID_DownloadHost,
           0,
           0,
           v11,
           0);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v8 = v9 >= 0;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( !v8 )
  {
LABEL_15:
    if ( (*((_BYTE *)this + 720) & 2) != 0 )
      Instance = -2147467259;
  }
  if ( *((_QWORD *)this + 17) )
    goto LABEL_21;
  if ( Instance >= 0 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v5;
    v13 = 0;
    Instance = (**v10)(v10, &IID_IConnectionPointContainer, &v13);
    if ( Instance >= 0 )
    {
      Instance = (*(__int64 (__fastcall **)(__int64, GUID *, char *))(*(_QWORD *)v13 + 32LL))(
                   v13,
                   &IID_IPropertyNotifySink,
                   (char *)this + 136);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
LABEL_21:
      if ( Instance >= 0 )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, char *))(**((_QWORD **)this + 17) + 40LL))(
                     *((_QWORD *)this + 17),
                     ((unsigned __int64)this + 8) & -(__int64)(this != 0),
                     (char *)this + 148);
        if ( Instance >= 0 )
          *v1 = 1;
      }
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180006c60  mov     [rsp-28h+arg_10], rbx
0x180006c65  push    rbp
0x180006c66  push    rsi
0x180006c67  push    rdi
0x180006c68  push    r14
0x180006c6a  push    r15
0x180006c6c  mov     rbp, rsp
0x180006c6f  sub     rsp, 60h
0x180006c73  lea     r15, [rcx+90h]
0x180006c7a  mov     rdi, rcx
0x180006c7d  cmp     dword ptr [r15], 0
0x180006c81  jz      short loc_180006C8A
0x180006c83  xor     eax, eax
0x180006c85  jmp     loc_180006ECA
0x180006c8a  xor     ebx, ebx
0x180006c8c  lea     rsi, [rcx+70h]
0x180006c90  cmp     [rsi], rbx
0x180006c93  jnz     loc_180006D46
0x180006c99  lea     r9, IID_IHTMLDocument2; riid
0x180006ca0  mov     [rsp+60h+ppv], rsi; ppv
0x180006ca5  xor     edx, edx; pUnkOuter
0x180006ca7  lea     r8d, [rbx+3]; dwClsContext
0x180006cab  lea     rcx, CLSID_HTMLDocument; rclsid
0x180006cb2  call    cs:__imp_CoCreateInstance
0x180006cb8  mov     ebx, eax
0x180006cba  test    eax, eax
0x180006cbc  js      loc_180006D46
0x180006cc2  mov     rcx, [rsi]
0x180006cc5  lea     r8, [rbp+arg_8]
0x180006cc9  mov     [rbp+arg_8], 0
0x180006cd1  lea     rdx, IID_IOleObject
0x180006cd8  mov     rax, [rcx]
0x180006cdb  mov     rax, [rax]
0x180006cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce3  mov     ebx, eax
0x180006ce5  test    eax, eax
0x180006ce7  js      short loc_180006D46
0x180006ce9  mov     rcx, [rbp+arg_8]
0x180006ced  mov     rdx, rdi
0x180006cf0  mov     rax, [rcx]
0x180006cf3  mov     rax, [rax+18h]
0x180006cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cfc  mov     rcx, [rbp+arg_8]
0x180006d00  mov     rax, [rcx]
0x180006d03  mov     rax, [rax+10h]
0x180006d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0c  mov     rcx, [rsi]
0x180006d0f  lea     r8, [rdi+68h]
0x180006d13  lea     rdx, IID_IPersistMoniker
0x180006d1a  mov     rax, [rcx]
0x180006d1d  mov     rax, [rax]
0x180006d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d25  mov     ebx, eax
0x180006d27  test    eax, eax
0x180006d29  js      short loc_180006D46
0x180006d2b  mov     rcx, [rsi]
0x180006d2e  lea     r8, [rdi+78h]
0x180006d32  lea     rdx, IID_IOleCommandTarget
0x180006d39  mov     rax, [rcx]
0x180006d3c  mov     rax, [rax]
0x180006d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d44  mov     ebx, eax
0x180006d46  mov     [rbp+arg_0], 0
0x180006d4e  test    ebx, ebx
0x180006d50  js      loc_180006E1D
0x180006d56  mov     rcx, [rdi+50h]
0x180006d5a  lea     rdx, [rbp+arg_0]
0x180006d5e  mov     rax, [rcx]
0x180006d61  mov     rax, [rax+20h]
0x180006d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6a  test    eax, eax
0x180006d6c  js      loc_180006E1D
0x180006d72  cmp     [rbp+arg_0], 0
0x180006d77  jz      loc_180006E1D
0x180006d7d  mov     rcx, [rsi]
0x180006d80  lea     r8, [rbp+arg_8]
0x180006d84  xor     r14d, r14d
0x180006d87  lea     rdx, IID_IOleCommandTarget
0x180006d8e  mov     [rbp+arg_8], r14
0x180006d92  mov     rax, [rcx]
0x180006d95  mov     rax, [rax]
0x180006d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9d  test    eax, eax
0x180006d9f  js      short loc_180006E08
0x180006da1  mov     rcx, [rbp+arg_8]
0x180006da5  test    rcx, rcx
0x180006da8  jz      short loc_180006E08
0x180006daa  xor     eax, eax
0x180006dac  mov     [rsp+60h+var_38], r14
0x180006db1  mov     [rbp+var_10], rax
0x180006db5  lea     rdx, [rbp+var_20]
0x180006db9  xorps   xmm0, xmm0
0x180006dbc  mov     [rsp+60h+ppv], rdx
0x180006dc1  movups  [rbp+var_20], xmm0
0x180006dc5  lea     eax, [r14+0Dh]
0x180006dc9  xor     r9d, r9d
0x180006dcc  mov     word ptr [rbp+var_20], ax
0x180006dd0  lea     rdx, CGID_DownloadHost
0x180006dd7  mov     rax, [rbp+arg_0]
0x180006ddb  xor     r8d, r8d
0x180006dde  mov     qword ptr [rbp+var_20+8], rax
0x180006de2  mov     rax, [rcx]
0x180006de5  mov     rax, [rax+20h]
0x180006de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dee  mov     rcx, [rbp+arg_8]
0x180006df2  mov     r14d, eax
0x180006df5  mov     rdx, [rcx]
0x180006df8  mov     rax, [rdx+10h]
0x180006dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e01  not     r14d
0x180006e04  shr     r14d, 1Fh
0x180006e08  mov     rcx, [rbp+arg_0]
0x180006e0c  mov     rax, [rcx]
0x180006e0f  mov     rax, [rax+10h]
0x180006e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e18  test    r14d, r14d
0x180006e1b  jnz     short loc_180006E2C
0x180006e1d  test    byte ptr [rdi+2D0h], 2
0x180006e24  mov     eax, 80004005h
0x180006e29  cmovnz  ebx, eax
0x180006e2c  lea     r14, [rdi+88h]
0x180006e33  cmp     qword ptr [r14], 0
0x180006e37  jnz     short loc_180006E94
0x180006e39  test    ebx, ebx
0x180006e3b  js      loc_180006EC8
0x180006e41  mov     rcx, [rsi]
0x180006e44  lea     r8, [rbp+arg_8]
0x180006e48  mov     [rbp+arg_8], 0
0x180006e50  lea     rdx, IID_IConnectionPointContainer
0x180006e57  mov     rax, [rcx]
0x180006e5a  mov     rax, [rax]
0x180006e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e62  mov     ebx, eax
0x180006e64  test    eax, eax
0x180006e66  js      short loc_180006EC8
0x180006e68  mov     rcx, [rbp+arg_8]
0x180006e6c  lea     rdx, IID_IPropertyNotifySink
0x180006e73  mov     r8, r14
0x180006e76  mov     rax, [rcx]
0x180006e79  mov     rax, [rax+20h]
0x180006e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e82  mov     rcx, [rbp+arg_8]
0x180006e86  mov     ebx, eax
0x180006e88  mov     rax, [rcx]
0x180006e8b  mov     rax, [rax+10h]
0x180006e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e94  test    ebx, ebx
0x180006e96  js      short loc_180006EC8
0x180006e98  mov     rcx, [r14]
0x180006e9b  lea     rax, [rdi+8]
0x180006e9f  lea     r8, [rdi+94h]
0x180006ea6  neg     rdi
0x180006ea9  sbb     rdx, rdx
0x180006eac  mov     r9, [rcx]
0x180006eaf  and     rdx, rax
0x180006eb2  mov     rax, [r9+28h]
0x180006eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebb  mov     ebx, eax
0x180006ebd  test    eax, eax
0x180006ebf  js      short loc_180006EC8
0x180006ec1  mov     dword ptr [r15], 1
0x180006ec8  mov     eax, ebx
0x180006eca  mov     rbx, [rsp+60h+arg_10]
0x180006ed2  add     rsp, 60h
0x180006ed6  pop     r15
0x180006ed8  pop     r14
0x180006eda  pop     rdi
0x180006edb  pop     rsi
0x180006edc  pop     rbp
0x180006edd  retn
```

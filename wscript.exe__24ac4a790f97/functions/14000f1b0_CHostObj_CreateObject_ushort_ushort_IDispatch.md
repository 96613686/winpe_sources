# CHostObj::CreateObject(ushort *,ushort *,IDispatch * *)

- ea: `0x14000f1b0`
- end: `0x14000f2e8`
- name: `?CreateObject@CHostObj@@UEAAJPEAG0PEAPEAUIDispatch@@@Z`
- size: `312`
- prototype: `__int64 __fastcall(CHostObj *__hidden this, unsigned __int16 *, unsigned __int16 *, struct IDispatch **)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x14000a098`
- `0x14000e9f4`
- `0x14000f1b0`
- `0x14000f2f0`
- `0x1400175a0`
- `0x140018010`

## string_xrefs

- `0x14000f275`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::CreateObject(
        CHostObj *this,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        struct IDispatch **a4)
{
  unsigned __int64 v5; // rdi
  struct IDispatch *v8; // rcx
  int v9; // ebx
  struct IDispatch *v10; // [rsp+20h] [rbp-38h] BYREF
  struct IUnknown *v11; // [rsp+28h] [rbp-30h] BYREF
  struct _GUID v12; // [rsp+30h] [rbp-28h] BYREF

  v5 = a3;
  if ( !a4 )
    return 2147500035LL;
  v8 = 0;
  v11 = 0;
  v10 = 0;
  *a4 = 0;
  v12 = 0;
  if ( !a2 || !*a2 )
  {
    v9 = -2147024809;
LABEL_15:
    if ( v8 )
      ((void (__fastcall *)(struct IDispatch *))v8->lpVtbl->Release)(v8);
    goto LABEL_17;
  }
  if ( a3 )
    v5 = -(__int64)(*(_WORD *)a3 != 0) & a3;
  v9 = CHostObj::CreateObjectHelper(this, a2, &v12, (LPVOID *)&v11);
  if ( v9 < 0
    || (v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDispatch **))v11->lpVtbl->QueryInterface)(
               v11,
               &IID_IDispatch,
               &v10),
        v9 < 0) )
  {
LABEL_12:
    v8 = v10;
    goto LABEL_15;
  }
  if ( v5 && (int)ConnectObject(&v12, v10, v5) < 0 )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Eu);
    v9 = -2147352567;
    goto LABEL_12;
  }
  v9 = 0;
  *a4 = v10;
  v10 = 0;
LABEL_17:
  if ( v11 )
    ((void (__fastcall *)(struct IUnknown *))v11->lpVtbl->Release)(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000f1b0  push    rbp
0x14000f1b2  push    rbx
0x14000f1b3  push    rsi
0x14000f1b4  push    rdi
0x14000f1b5  mov     rbp, rsp
0x14000f1b8  sub     rsp, 58h
0x14000f1bc  mov     rax, cs:__security_cookie
0x14000f1c3  xor     rax, rsp
0x14000f1c6  mov     [rbp+var_18], rax
0x14000f1ca  mov     rsi, r9
0x14000f1cd  mov     rdi, r8
0x14000f1d0  mov     r10, rcx
0x14000f1d3  test    r9, r9
0x14000f1d6  jnz     short loc_14000F1E2
0x14000f1d8  mov     eax, 80004003h
0x14000f1dd  jmp     loc_14000F2D3
0x14000f1e2  xor     ecx, ecx
0x14000f1e4  mov     [rbp+var_30], 0
0x14000f1ec  mov     [rbp+var_38], rcx
0x14000f1f0  xorps   xmm0, xmm0
0x14000f1f3  mov     [r9], rcx
0x14000f1f6  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x14000f1fa  test    rdx, rdx
0x14000f1fd  jz      loc_14000F2A6
0x14000f203  xor     eax, eax
0x14000f205  cmp     ax, [rdx]
0x14000f208  jz      loc_14000F2A6
0x14000f20e  test    rdi, rdi
0x14000f211  jz      short loc_14000F220
0x14000f213  movzx   eax, word ptr [r8]
0x14000f217  neg     ax
0x14000f21a  sbb     r8, r8
0x14000f21d  and     rdi, r8
0x14000f220  lea     r9, [rbp+var_30]; struct IUnknown **
0x14000f224  mov     rcx, r10; this
0x14000f227  lea     r8, [rbp+var_28]; struct _GUID *
0x14000f22b  call    ?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z; CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)
0x14000f230  mov     ebx, eax
0x14000f232  test    eax, eax
0x14000f234  js      short loc_14000F28D
0x14000f236  mov     rcx, [rbp+var_30]
0x14000f23a  lea     r8, [rbp+var_38]
0x14000f23e  lea     rdx, IID_IDispatch
0x14000f245  mov     rax, [rcx]
0x14000f248  mov     rax, [rax]
0x14000f24b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f250  mov     ebx, eax
0x14000f252  test    eax, eax
0x14000f254  js      short loc_14000F28D
0x14000f256  test    rdi, rdi
0x14000f259  jz      short loc_14000F293
0x14000f25b  mov     rdx, [rbp+var_38]
0x14000f25f  lea     rcx, [rbp+var_28]
0x14000f263  mov     r8, rdi
0x14000f266  call    ConnectObject
0x14000f26b  test    eax, eax
0x14000f26d  jns     short loc_14000F293
0x14000f26f  mov     r8d, 0C1Eh; unsigned int
0x14000f275  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14000f27c  lea     rcx, IID_IHost; struct _GUID *
0x14000f283  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14000f288  mov     ebx, 80020009h
0x14000f28d  mov     rcx, [rbp+var_38]
0x14000f291  jmp     short loc_14000F2AB
0x14000f293  mov     rax, [rbp+var_38]
0x14000f297  xor     ebx, ebx
0x14000f299  mov     [rsi], rax
0x14000f29c  mov     [rbp+var_38], 0
0x14000f2a4  jmp     short loc_14000F2BC
0x14000f2a6  mov     ebx, 80070057h
0x14000f2ab  test    rcx, rcx
0x14000f2ae  jz      short loc_14000F2BC
0x14000f2b0  mov     rax, [rcx]
0x14000f2b3  mov     rax, [rax+10h]
0x14000f2b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2bc  mov     rcx, [rbp+var_30]
0x14000f2c0  test    rcx, rcx
0x14000f2c3  jz      short loc_14000F2D1
0x14000f2c5  mov     rax, [rcx]
0x14000f2c8  mov     rax, [rax+10h]
0x14000f2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f2d1  mov     eax, ebx
0x14000f2d3  mov     rcx, [rbp+var_18]
0x14000f2d7  xor     rcx, rsp; StackCookie
0x14000f2da  call    __security_check_cookie
0x14000f2df  add     rsp, 58h
0x14000f2e3  pop     rdi
0x14000f2e4  pop     rsi
0x14000f2e5  pop     rbx
0x14000f2e6  pop     rbp
0x14000f2e7  retn
```

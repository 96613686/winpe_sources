# MakeTypeInfo(int,int,ushort * *,ITypeInfo * *)

- ea: `0x18004c7c8`
- end: `0x18004ca77`
- name: `?MakeTypeInfo@@YAJHHPEAPEAGPEAPEAUITypeInfo@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(int, int, unsigned __int16 **, struct ITypeInfo **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18004bd00`
- `0x18004bea0`
- `0x18006303c`

## callees

- `0x18004ada4`
- `0x18004c7c8`
- `0x180076746`
- `0x1800767a0`
- `0x180076830`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18004c848`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18004c848`

## pseudocode

```c
__int64 __fastcall MakeTypeInfo(int a1, int a2, unsigned __int16 **a3, struct ITypeInfo **a4)
{
  unsigned __int64 v4; // rdi
  HRESULT v8; // ebx
  size_t v9; // r8
  __int64 v10; // rax
  void *v11; // rsp
  struct ITypeInfo *v12; // rcx
  __int64 result; // rax
  int i; // ecx
  __int64 v15; // rax
  __int64 v16; // [rsp+30h] [rbp+0h] BYREF
  struct ITypeInfo *v17; // [rsp+38h] [rbp+8h] BYREF
  ICreateTypeLib2 *ppctlib; // [rsp+40h] [rbp+10h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp+20h] BYREF
  __int64 *v20; // [rsp+60h] [rbp+30h]
  int v21; // [rsp+68h] [rbp+38h]
  int v22; // [rsp+6Ch] [rbp+3Ch]
  int v23; // [rsp+70h] [rbp+40h]
  __int16 v24; // [rsp+74h] [rbp+44h]
  __int16 v25; // [rsp+7Ah] [rbp+4Ah]
  __int128 v26; // [rsp+80h] [rbp+50h]
  __int128 v27; // [rsp+90h] [rbp+60h]
  _BYTE v28[32]; // [rsp+B0h] [rbp+80h] BYREF
  __int16 v29; // [rsp+D0h] [rbp+A0h]
  int v30; // [rsp+ECh] [rbp+BCh]

  v4 = a2;
  memset_0(v28, 0, 0x40u);
  memset_0(v19, 0, 0x58u);
  v17 = 0;
  ppctlib = 0;
  v16 = 0;
  v8 = CreateTypeLib2(SYS_WIN32, L"VBSSig.tlb", &ppctlib);
  if ( v8 < 0 )
    goto LABEL_10;
  v8 = ((__int64 (__fastcall *)(ICreateTypeLib2 *, _QWORD, __int64, __int64 *))ppctlib->lpVtbl->CreateTypeInfo)(
         ppctlib,
         *a3,
         4,
         &v16);
  if ( v8 < 0 )
    goto LABEL_10;
  if ( a1 == 1 )
  {
    if ( (v4 & 0x80000000) != 0LL || v4 > 0x3FFFFFF )
      goto LABEL_9;
    v9 = 32 * v4;
    v10 = 32 * v4 + 15;
    if ( v9 + 15 < v9 )
      v10 = 0xFFFFFFFFFFFFFF0LL;
    v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
    if ( !&v16 )
    {
LABEL_9:
      v8 = -2147024882;
LABEL_10:
      v12 = v17;
      goto LABEL_11;
    }
    memset_0(&v16, 0, v9);
    for ( i = 0; i < (int)v4; *((_WORD *)&v16 + 16 * v15 + 4) = 12 )
      v15 = (unsigned int)i++;
    memset_0(v19, 0, 0x58u);
    v20 = &v16;
    v21 = 4;
    v23 = 4;
    v22 = 1;
    v24 = v4 - 1;
    v26 = 0;
    v25 = -1;
    v27 = 0;
    WORD4(v26) = 12;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 72LL))(v16, 0, v19);
    if ( v8 < 0 )
      goto LABEL_10;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **, _QWORD))(*(_QWORD *)v16 + 120LL))(
           v16,
           0,
           a3,
           (unsigned int)v4);
    if ( v8 < 0 )
      goto LABEL_10;
  }
  else
  {
    memset_0(v28, 0, 0x40u);
    v30 = 3;
    v29 = 12;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v16 + 112LL))(v16, 0, v28);
    if ( (int)result < 0 )
      return result;
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v16 + 128LL))(v16, 0, *a3);
    if ( (int)result < 0 )
      return result;
  }
  v8 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct ITypeInfo **))v16)(v16, &IID_ITypeInfo, &v17);
  if ( v8 < 0 )
    goto LABEL_10;
  v12 = v17;
  v8 = 0;
  *a4 = v17;
LABEL_11:
  if ( v12 && v8 < 0 )
    ((void (__fastcall *)(struct ITypeInfo *))v12->lpVtbl->Release)(v12);
  if ( ppctlib )
    ((void (__fastcall *)(ICreateTypeLib2 *))ppctlib->lpVtbl->Release)(ppctlib);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  FreeNames(a3, (unsigned int)v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004c7c8  push    rbp
0x18004c7ca  push    rbx
0x18004c7cb  push    rsi
0x18004c7cc  push    rdi
0x18004c7cd  push    r13
0x18004c7cf  push    r14
0x18004c7d1  push    r15
0x18004c7d3  sub     rsp, 100h
0x18004c7da  lea     rbp, [rsp+30h]
0x18004c7df  mov     rax, cs:__security_cookie
0x18004c7e6  xor     rax, rbp
0x18004c7e9  mov     [rbp+100h+var_40], rax
0x18004c7f0  movsxd  rdi, edx
0x18004c7f3  mov     r14, r8
0x18004c7f6  xor     edx, edx; Val
0x18004c7f8  mov     esi, ecx
0x18004c7fa  lea     rcx, [rbp+100h+var_80]; void *
0x18004c801  mov     r15, r9
0x18004c804  lea     r8d, [rdx+40h]; Size
0x18004c808  call    memset_0
0x18004c80d  xor     edx, edx; Val
0x18004c80f  lea     rcx, [rbp+100h+var_E0]; void *
0x18004c813  lea     r8d, [rdx+58h]; Size
0x18004c817  call    memset_0
0x18004c81c  mov     r13d, 1
0x18004c822  mov     [rbp+100h+var_F8], 0
0x18004c82a  mov     ecx, r13d; syskind
0x18004c82d  mov     [rbp+100h+ppctlib], 0
0x18004c835  lea     r8, [rbp+100h+ppctlib]; ppctlib
0x18004c839  mov     [rbp+100h+var_100], 0
0x18004c841  lea     rdx, aVbssigTlb; "VBSSig.tlb"
0x18004c848  call    cs:__imp_CreateTypeLib2
0x18004c84e  mov     ebx, eax
0x18004c850  test    eax, eax
0x18004c852  js      short loc_18004C8C0
0x18004c854  mov     rcx, [rbp+100h+ppctlib]
0x18004c858  lea     r9, [rbp+100h+var_100]
0x18004c85c  mov     rdx, [r14]
0x18004c85f  lea     r8d, [r13+3]
0x18004c863  mov     rax, [rcx]
0x18004c866  mov     rax, [rax+18h]
0x18004c86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c86f  mov     ebx, eax
0x18004c871  test    eax, eax
0x18004c873  js      short loc_18004C8C0
0x18004c875  cmp     esi, r13d
0x18004c878  jnz     loc_18004C9DC
0x18004c87e  test    edi, edi
0x18004c880  js      short loc_18004C8BB
0x18004c882  mov     r8, rdi
0x18004c885  cmp     rdi, 3FFFFFFh
0x18004c88c  ja      short loc_18004C8BB
0x18004c88e  shl     r8, 5
0x18004c892  lea     rax, [r8+0Fh]
0x18004c896  cmp     rax, r8
0x18004c899  ja      short loc_18004C8A5
0x18004c89b  mov     rax, 0FFFFFFFFFFFFFF0h
0x18004c8a5  and     rax, 0FFFFFFFFFFFFFFF0h
0x18004c8a9  call    _alloca_probe
0x18004c8ae  sub     rsp, rax
0x18004c8b1  lea     rbx, [rsp+130h+var_100]
0x18004c8b6  test    rbx, rbx
0x18004c8b9  jnz     short loc_18004C930
0x18004c8bb  mov     ebx, 8007000Eh
0x18004c8c0  mov     rcx, [rbp+100h+var_F8]
0x18004c8c4  test    rcx, rcx
0x18004c8c7  jz      short loc_18004C8D9
0x18004c8c9  test    ebx, ebx
0x18004c8cb  jns     short loc_18004C8D9
0x18004c8cd  mov     rax, [rcx]
0x18004c8d0  mov     rax, [rax+10h]
0x18004c8d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8d9  mov     rcx, [rbp+100h+ppctlib]
0x18004c8dd  test    rcx, rcx
0x18004c8e0  jz      short loc_18004C8EE
0x18004c8e2  mov     rax, [rcx]
0x18004c8e5  mov     rax, [rax+10h]
0x18004c8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c8ee  mov     rcx, [rbp+100h+var_100]
0x18004c8f2  test    rcx, rcx
0x18004c8f5  jz      short loc_18004C903
0x18004c8f7  mov     rax, [rcx]
0x18004c8fa  mov     rax, [rax+10h]
0x18004c8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c903  mov     edx, edi
0x18004c905  mov     rcx, r14
0x18004c908  call    FreeNames
0x18004c90d  mov     eax, ebx
0x18004c90f  mov     rcx, [rbp+100h+var_40]
0x18004c916  xor     rcx, rbp; StackCookie
0x18004c919  call    __security_check_cookie
0x18004c91e  lea     rsp, [rbp+0D0h]
0x18004c925  pop     r15
0x18004c927  pop     r14
0x18004c929  pop     r13
0x18004c92b  pop     rdi
0x18004c92c  pop     rsi
0x18004c92d  pop     rbx
0x18004c92e  pop     rbp
0x18004c92f  retn
0x18004c930  xor     edx, edx; Val
0x18004c932  mov     rcx, rbx; void *
0x18004c935  call    memset_0
0x18004c93a  xor     ecx, ecx
0x18004c93c  lea     esi, [rcx+0Ch]
0x18004c93f  test    edi, edi
0x18004c941  jle     short loc_18004C955
0x18004c943  mov     eax, ecx
0x18004c945  add     ecx, r13d
0x18004c948  shl     rax, 5
0x18004c94c  mov     [rax+rbx+8], si
0x18004c951  cmp     ecx, edi
0x18004c953  jl      short loc_18004C943
0x18004c955  xor     edx, edx; Val
0x18004c957  lea     rcx, [rbp+100h+var_E0]; void *
0x18004c95b  lea     r8d, [rdx+58h]; Size
0x18004c95f  call    memset_0
0x18004c964  mov     rcx, [rbp+100h+var_100]
0x18004c968  lea     r8, [rbp+100h+var_E0]
0x18004c96c  mov     eax, 4
0x18004c971  mov     [rbp+100h+var_D0], rbx
0x18004c975  mov     [rbp+100h+var_C8], eax
0x18004c978  xorps   xmm0, xmm0
0x18004c97b  mov     [rbp+100h+var_C0], eax
0x18004c97e  xor     edx, edx
0x18004c980  movzx   eax, di
0x18004c983  mov     [rbp+100h+var_C4], r13d
0x18004c987  sub     ax, r13w
0x18004c98b  mov     [rbp+100h+var_BC], ax
0x18004c98f  or      eax, 0FFFFFFFFh
0x18004c992  movups  [rbp+100h+var_B0], xmm0
0x18004c996  mov     [rbp+100h+var_B6], ax
0x18004c99a  movups  [rbp+100h+var_A0], xmm0
0x18004c99e  mov     word ptr [rbp+100h+var_B0+8], si
0x18004c9a2  mov     rax, [rcx]
0x18004c9a5  mov     rax, [rax+48h]
0x18004c9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9ae  mov     ebx, eax
0x18004c9b0  test    eax, eax
0x18004c9b2  js      loc_18004C8C0
0x18004c9b8  mov     rcx, [rbp+100h+var_100]
0x18004c9bc  mov     r9d, edi
0x18004c9bf  mov     r8, r14
0x18004c9c2  xor     edx, edx
0x18004c9c4  mov     rax, [rcx]
0x18004c9c7  mov     rax, [rax+78h]
0x18004c9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9d0  mov     ebx, eax
0x18004c9d2  test    eax, eax
0x18004c9d4  js      loc_18004C8C0
0x18004c9da  jmp     short loc_18004CA45
0x18004c9dc  xor     edx, edx; Val
0x18004c9de  lea     rcx, [rbp+100h+var_80]; void *
0x18004c9e5  lea     r8d, [rdx+40h]; Size
0x18004c9e9  call    memset_0
0x18004c9ee  mov     rcx, [rbp+100h+var_100]
0x18004c9f2  lea     r8, [rbp+100h+var_80]
0x18004c9f9  mov     [rbp+100h+var_44], 3
0x18004ca03  mov     esi, 0Ch
0x18004ca08  mov     [rbp+100h+var_60], si
0x18004ca0f  xor     edx, edx
0x18004ca11  mov     rax, [rcx]
0x18004ca14  mov     rax, [rax+70h]
0x18004ca18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca1d  test    eax, eax
0x18004ca1f  js      loc_18004C90F
0x18004ca25  mov     rcx, [rbp+100h+var_100]
0x18004ca29  xor     edx, edx
0x18004ca2b  mov     r8, [r14]
0x18004ca2e  mov     rax, [rcx]
0x18004ca31  mov     rax, [rax+80h]
0x18004ca38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca3d  test    eax, eax
0x18004ca3f  js      loc_18004C90F
0x18004ca45  mov     rcx, [rbp+100h+var_100]
0x18004ca49  lea     r8, [rbp+100h+var_F8]
0x18004ca4d  lea     rdx, IID_ITypeInfo
0x18004ca54  mov     rax, [rcx]
0x18004ca57  mov     rax, [rax]
0x18004ca5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ca5f  mov     ebx, eax
0x18004ca61  test    eax, eax
0x18004ca63  js      loc_18004C8C0
0x18004ca69  mov     rcx, [rbp+100h+var_F8]
0x18004ca6d  xor     ebx, ebx
0x18004ca6f  mov     [r15], rcx
0x18004ca72  jmp     loc_18004C8C4
```

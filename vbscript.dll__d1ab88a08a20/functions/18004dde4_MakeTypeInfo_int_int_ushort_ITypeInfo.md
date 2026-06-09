# MakeTypeInfo(int,int,ushort * *,ITypeInfo * *)

- ea: `0x18004dde4`
- end: `0x18004e09a`
- name: `?MakeTypeInfo@@YAJHHPEAPEAGPEAPEAUITypeInfo@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(int, int, unsigned __int16 **, struct ITypeInfo **)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18004d380`
- `0x18004d520`
- `0x180064ddc`

## callees

- `0x18004c3c0`
- `0x18004dde4`
- `0x180079436`
- `0x180079490`
- `0x180079520`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_CreateTypeLib2` at `0x18004de64`
- `OLEAUT32!__imp_CreateTypeLib2` at `0x18004de64`

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
0x18004dde4  push    rbp
0x18004dde6  push    rbx
0x18004dde7  push    rsi
0x18004dde8  push    rdi
0x18004dde9  push    r13
0x18004ddeb  push    r14
0x18004dded  push    r15
0x18004ddef  sub     rsp, 100h
0x18004ddf6  lea     rbp, [rsp+30h]
0x18004ddfb  mov     rax, cs:__security_cookie
0x18004de02  xor     rax, rbp
0x18004de05  mov     [rbp+100h+var_40], rax
0x18004de0c  movsxd  rdi, edx
0x18004de0f  mov     r14, r8
0x18004de12  xor     edx, edx; Val
0x18004de14  mov     esi, ecx
0x18004de16  lea     rcx, [rbp+100h+var_80]; void *
0x18004de1d  mov     r15, r9
0x18004de20  lea     r8d, [rdx+40h]; Size
0x18004de24  call    memset_0
0x18004de29  xor     edx, edx; Val
0x18004de2b  lea     rcx, [rbp+100h+var_E0]; void *
0x18004de2f  lea     r8d, [rdx+58h]; Size
0x18004de33  call    memset_0
0x18004de38  mov     r13d, 1
0x18004de3e  mov     [rbp+100h+var_F8], 0
0x18004de46  mov     ecx, r13d; syskind
0x18004de49  mov     [rbp+100h+ppctlib], 0
0x18004de51  lea     r8, [rbp+100h+ppctlib]; ppctlib
0x18004de55  mov     [rbp+100h+var_100], 0
0x18004de5d  lea     rdx, aVbssigTlb; "VBSSig.tlb"
0x18004de64  call    cs:__imp_CreateTypeLib2
0x18004de6b  nop     dword ptr [rax+rax+00h]
0x18004de70  mov     ebx, eax
0x18004de72  test    eax, eax
0x18004de74  js      short loc_18004DEE2
0x18004de76  mov     rcx, [rbp+100h+ppctlib]
0x18004de7a  lea     r9, [rbp+100h+var_100]
0x18004de7e  mov     rdx, [r14]
0x18004de81  lea     r8d, [r13+3]
0x18004de85  mov     rax, [rcx]
0x18004de88  mov     rax, [rax+18h]
0x18004de8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004de91  mov     ebx, eax
0x18004de93  test    eax, eax
0x18004de95  js      short loc_18004DEE2
0x18004de97  cmp     esi, r13d
0x18004de9a  jnz     loc_18004DFFF
0x18004dea0  test    edi, edi
0x18004dea2  js      short loc_18004DEDD
0x18004dea4  mov     r8, rdi
0x18004dea7  cmp     rdi, 3FFFFFFh
0x18004deae  ja      short loc_18004DEDD
0x18004deb0  shl     r8, 5
0x18004deb4  lea     rax, [r8+0Fh]
0x18004deb8  cmp     rax, r8
0x18004debb  ja      short loc_18004DEC7
0x18004debd  mov     rax, 0FFFFFFFFFFFFFF0h
0x18004dec7  and     rax, 0FFFFFFFFFFFFFFF0h
0x18004decb  call    _alloca_probe
0x18004ded0  sub     rsp, rax
0x18004ded3  lea     rbx, [rsp+130h+var_100]
0x18004ded8  test    rbx, rbx
0x18004dedb  jnz     short loc_18004DF53
0x18004dedd  mov     ebx, 8007000Eh
0x18004dee2  mov     rcx, [rbp+100h+var_F8]
0x18004dee6  test    rcx, rcx
0x18004dee9  jz      short loc_18004DEFB
0x18004deeb  test    ebx, ebx
0x18004deed  jns     short loc_18004DEFB
0x18004deef  mov     rax, [rcx]
0x18004def2  mov     rax, [rax+10h]
0x18004def6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004defb  mov     rcx, [rbp+100h+ppctlib]
0x18004deff  test    rcx, rcx
0x18004df02  jz      short loc_18004DF10
0x18004df04  mov     rax, [rcx]
0x18004df07  mov     rax, [rax+10h]
0x18004df0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df10  mov     rcx, [rbp+100h+var_100]
0x18004df14  test    rcx, rcx
0x18004df17  jz      short loc_18004DF25
0x18004df19  mov     rax, [rcx]
0x18004df1c  mov     rax, [rax+10h]
0x18004df20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004df25  mov     edx, edi
0x18004df27  mov     rcx, r14
0x18004df2a  call    FreeNames
0x18004df2f  mov     eax, ebx
0x18004df31  mov     rcx, [rbp+100h+var_40]
0x18004df38  xor     rcx, rbp; StackCookie
0x18004df3b  call    __security_check_cookie
0x18004df40  lea     rsp, [rbp+0D0h]
0x18004df47  pop     r15
0x18004df49  pop     r14
0x18004df4b  pop     r13
0x18004df4d  pop     rdi
0x18004df4e  pop     rsi
0x18004df4f  pop     rbx
0x18004df50  pop     rbp
0x18004df51  retn
0x18004df53  xor     edx, edx; Val
0x18004df55  mov     rcx, rbx; void *
0x18004df58  call    memset_0
0x18004df5d  xor     ecx, ecx
0x18004df5f  lea     esi, [rcx+0Ch]
0x18004df62  test    edi, edi
0x18004df64  jle     short loc_18004DF78
0x18004df66  mov     eax, ecx
0x18004df68  add     ecx, r13d
0x18004df6b  shl     rax, 5
0x18004df6f  mov     [rax+rbx+8], si
0x18004df74  cmp     ecx, edi
0x18004df76  jl      short loc_18004DF66
0x18004df78  xor     edx, edx; Val
0x18004df7a  lea     rcx, [rbp+100h+var_E0]; void *
0x18004df7e  lea     r8d, [rdx+58h]; Size
0x18004df82  call    memset_0
0x18004df87  mov     rcx, [rbp+100h+var_100]
0x18004df8b  lea     r8, [rbp+100h+var_E0]
0x18004df8f  mov     eax, 4
0x18004df94  mov     [rbp+100h+var_D0], rbx
0x18004df98  mov     [rbp+100h+var_C8], eax
0x18004df9b  xorps   xmm0, xmm0
0x18004df9e  mov     [rbp+100h+var_C0], eax
0x18004dfa1  xor     edx, edx
0x18004dfa3  movzx   eax, di
0x18004dfa6  mov     [rbp+100h+var_C4], r13d
0x18004dfaa  sub     ax, r13w
0x18004dfae  mov     [rbp+100h+var_BC], ax
0x18004dfb2  or      eax, 0FFFFFFFFh
0x18004dfb5  movups  [rbp+100h+var_B0], xmm0
0x18004dfb9  mov     [rbp+100h+var_B6], ax
0x18004dfbd  movups  [rbp+100h+var_A0], xmm0
0x18004dfc1  mov     word ptr [rbp+100h+var_B0+8], si
0x18004dfc5  mov     rax, [rcx]
0x18004dfc8  mov     rax, [rax+48h]
0x18004dfcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dfd1  mov     ebx, eax
0x18004dfd3  test    eax, eax
0x18004dfd5  js      loc_18004DEE2
0x18004dfdb  mov     rcx, [rbp+100h+var_100]
0x18004dfdf  mov     r9d, edi
0x18004dfe2  mov     r8, r14
0x18004dfe5  xor     edx, edx
0x18004dfe7  mov     rax, [rcx]
0x18004dfea  mov     rax, [rax+78h]
0x18004dfee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dff3  mov     ebx, eax
0x18004dff5  test    eax, eax
0x18004dff7  js      loc_18004DEE2
0x18004dffd  jmp     short loc_18004E068
0x18004dfff  xor     edx, edx; Val
0x18004e001  lea     rcx, [rbp+100h+var_80]; void *
0x18004e008  lea     r8d, [rdx+40h]; Size
0x18004e00c  call    memset_0
0x18004e011  mov     rcx, [rbp+100h+var_100]
0x18004e015  lea     r8, [rbp+100h+var_80]
0x18004e01c  mov     [rbp+100h+var_44], 3
0x18004e026  mov     esi, 0Ch
0x18004e02b  mov     [rbp+100h+var_60], si
0x18004e032  xor     edx, edx
0x18004e034  mov     rax, [rcx]
0x18004e037  mov     rax, [rax+70h]
0x18004e03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e040  test    eax, eax
0x18004e042  js      loc_18004DF31
0x18004e048  mov     rcx, [rbp+100h+var_100]
0x18004e04c  xor     edx, edx
0x18004e04e  mov     r8, [r14]
0x18004e051  mov     rax, [rcx]
0x18004e054  mov     rax, [rax+80h]
0x18004e05b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e060  test    eax, eax
0x18004e062  js      loc_18004DF31
0x18004e068  mov     rcx, [rbp+100h+var_100]
0x18004e06c  lea     r8, [rbp+100h+var_F8]
0x18004e070  lea     rdx, IID_ITypeInfo
0x18004e077  mov     rax, [rcx]
0x18004e07a  mov     rax, [rax]
0x18004e07d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e082  mov     ebx, eax
0x18004e084  test    eax, eax
0x18004e086  js      loc_18004DEE2
0x18004e08c  mov     rcx, [rbp+100h+var_F8]
0x18004e090  xor     ebx, ebx
0x18004e092  mov     [r15], rcx
0x18004e095  jmp     loc_18004DEE6
```

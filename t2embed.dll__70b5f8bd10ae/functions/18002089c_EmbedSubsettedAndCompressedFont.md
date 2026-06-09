# EmbedSubsettedAndCompressedFont

- ea: `0x18002089c`
- end: `0x180020c37`
- name: `EmbedSubsettedAndCompressedFont`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180021394`

## callees

- `0x180010018`
- `0x180019014`
- `0x180019dc0`
- `0x180020588`
- `0x18002089c`
- `0x180021020`
- `0x180021aa4`
- `0x180021d54`
- `0x180022ba4`
- `0x180027480`
- `0x18002a566`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall EmbedSubsettedAndCompressedFont(
        int a1,
        int a2,
        void *a3,
        int a4,
        unsigned int a5,
        _DWORD *a6,
        __int16 a7,
        int a8,
        __int16 a9,
        __int64 a10,
        __int16 a11,
        int a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17)
{
  __int64 result; // rax
  void *v20; // rbx
  void *v21; // rsi
  int v22; // r15d
  unsigned int AllocEmbedHeaderData; // edi
  int v24; // eax
  int DeltaTTF; // eax
  void *v26; // rdi
  int v27; // eax
  void *v28; // rcx
  void *v29; // rbx
  int v30; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v31; // [rsp+74h] [rbp-8Ch] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  int v33; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+84h] [rbp-7Ch] BYREF
  void *v35; // [rsp+88h] [rbp-78h] BYREF
  int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  __int64 v38; // [rsp+98h] [rbp-68h]
  _QWORD v39[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+B0h] [rbp-50h]
  __int64 v41; // [rsp+B8h] [rbp-48h]
  LPVOID v42; // [rsp+C0h] [rbp-40h] BYREF
  int v43; // [rsp+C8h] [rbp-38h]
  int v44; // [rsp+CCh] [rbp-34h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  _BYTE v46[208]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v47[3]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v48; // [rsp+1E0h] [rbp+E0h]
  _BYTE v49[96]; // [rsp+1F0h] [rbp+F0h] BYREF

  v41 = a13;
  v40 = a16;
  v35 = a3;
  v38 = a17;
  v37 = a4;
  v39[1] = a10;
  memset_0(v46, 0, sizeof(v46));
  v30 = 0;
  v31 = 0;
  memset_0(v49, 0, 0x58u);
  v48 = 0;
  v33 = 0;
  v36 = (a5 >> 29) & 1;
  memset(v47, 0, sizeof(v47));
  lpMem = 0;
  result = T2OSSvcCreateDeltaTTF(a1, a2, (unsigned int)&lpMem, (unsigned int)&v30, a7);
  v20 = 0;
  if ( !(_DWORD)result )
  {
    v21 = lpMem;
    v22 = v30;
    v42 = lpMem;
    v43 = v30;
    v44 = 0;
    v45 = 0;
    if ( !(unsigned int)GetSmartOS2(&v42, v49, &v33) )
    {
      AllocEmbedHeaderData = 260;
LABEL_16:
      T2free(v21);
      return AllocEmbedHeaderData;
    }
    if ( !(unsigned int)GetGeneric(&v42, v47, 0) )
    {
      AllocEmbedHeaderData = 267;
      goto LABEL_16;
    }
    lpMem = 0;
    AllocEmbedHeaderData = CompressBuffer((_DWORD)v21, v22, (unsigned int)&lpMem, (unsigned int)&v31, v38);
    if ( AllocEmbedHeaderData )
      goto LABEL_16;
    v24 = (int)v35;
    v39[0] = 0;
    v34 = 0;
    if ( v35 )
    {
      v30 = 0;
      v35 = 0;
      DeltaTTF = T2OSSvcCreateDeltaTTF(v24, v37, (unsigned int)&v35, (unsigned int)&v30, a7);
      v26 = v35;
      if ( DeltaTTF )
        v26 = 0;
      v27 = CompressBuffer((_DWORD)v26, v30, (unsigned int)v39, (unsigned int)&v34, v38);
      v20 = (void *)v39[0];
      if ( v27 )
        v20 = 0;
      if ( v26 )
        T2free(v26);
    }
    AllocEmbedHeaderData = GetAllocEmbedHeaderData(
                             (_DWORD)v21,
                             v22,
                             v31,
                             (_DWORD)v20,
                             v34,
                             a5,
                             a5,
                             DWORD2(v47[0]),
                             (__int64)v49,
                             v33,
                             v41,
                             v40,
                             (__int64)v46);
    if ( AllocEmbedHeaderData )
    {
      T2free(v20);
      T2free(lpMem);
      goto LABEL_16;
    }
    T2free(v21);
    AllocEmbedHeaderData = WriteEmbeddedHeader(a14, a15, v46);
    if ( AllocEmbedHeaderData )
    {
      T2free(v20);
      v28 = lpMem;
LABEL_20:
      T2free(v28);
      DeallocEmbedHeaderData(v46);
      return AllocEmbedHeaderData;
    }
    if ( v20 )
    {
      *a6 |= 2u;
      T2free(v20);
    }
    v29 = lpMem;
    AllocEmbedHeaderData = WriteFontImage(lpMem, v31, a5 & 0x10000000, a14, a15);
    if ( AllocEmbedHeaderData )
    {
      v28 = v29;
      goto LABEL_20;
    }
    DeallocEmbedHeaderData(v46);
    T2free(v29);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002089c  push    rbp
0x18002089e  push    rbx
0x18002089f  push    rsi
0x1800208a0  push    rdi
0x1800208a1  push    r12
0x1800208a3  push    r13
0x1800208a5  push    r14
0x1800208a7  push    r15
0x1800208a9  lea     rbp, [rsp-168h]
0x1800208b1  sub     rsp, 268h
0x1800208b8  mov     rax, cs:__security_cookie
0x1800208bf  xor     rax, rsp
0x1800208c2  mov     [rbp+1A0h+var_50], rax
0x1800208c9  mov     rax, [rbp+1A0h+arg_60]
0x1800208d0  mov     edi, edx
0x1800208d2  mov     rsi, [rbp+1A0h+arg_48]
0x1800208d9  mov     rbx, rcx
0x1800208dc  mov     r12, [rbp+1A0h+arg_28]
0x1800208e3  lea     rcx, [rbp+1A0h+var_1C0]; void *
0x1800208e7  mov     r13, [rbp+1A0h+arg_70]
0x1800208ee  xor     edx, edx; Val
0x1800208f0  mov     [rbp+1A0h+var_1E8], rax
0x1800208f4  mov     rax, [rbp+1A0h+arg_78]
0x1800208fb  mov     [rbp+1A0h+var_1F0], rax
0x1800208ff  mov     rax, [rbp+1A0h+arg_80]
0x180020906  mov     [rbp+1A0h+var_218], r8
0x18002090a  mov     r8d, 0D0h; Size
0x180020910  mov     [rbp+1A0h+var_208], rax
0x180020914  mov     [rbp+1A0h+var_20C], r9d
0x180020918  mov     [rbp+1A0h+var_1F8], rsi
0x18002091c  call    memset_0
0x180020921  xor     r15d, r15d
0x180020924  lea     rcx, [rbp+1A0h+var_B0]; void *
0x18002092b  xor     edx, edx; Val
0x18002092d  mov     [rsp+2A0h+var_230], r15d
0x180020932  mov     [rsp+2A0h+var_22C], r15d
0x180020937  lea     r8d, [r15+58h]; Size
0x18002093b  call    memset_0
0x180020940  movzx   ecx, [rbp+1A0h+arg_50]
0x180020947  lea     r9, [rsp+2A0h+var_230]
0x18002094c  mov     r14d, [rbp+1A0h+arg_20]
0x180020953  lea     r8, [rsp+2A0h+lpMem]
0x180020958  xor     eax, eax
0x18002095a  mov     word ptr [rsp+2A0h+var_258], cx
0x18002095f  mov     [rbp+1A0h+var_C0], rax
0x180020966  xorps   xmm0, xmm0
0x180020969  mov     [rsp+2A0h+var_260], rsi
0x18002096e  mov     eax, r14d
0x180020971  shr     eax, 1Dh
0x180020974  mov     edx, edi
0x180020976  and     ax, 1
0x18002097a  mov     [rbp+1A0h+var_220], r15d
0x18002097e  mov     word ptr [rsp+2A0h+var_268], ax
0x180020983  mov     rcx, rbx
0x180020986  mov     [rbp+1A0h+var_210], eax
0x180020989  movzx   eax, [rbp+1A0h+arg_40]
0x180020990  mov     word ptr [rsp+2A0h+var_270], ax
0x180020995  movzx   eax, [rbp+1A0h+arg_30]
0x18002099c  mov     word ptr [rsp+2A0h+var_280], ax
0x1800209a1  movups  [rbp+1A0h+var_F0], xmm0
0x1800209a8  mov     [rsp+2A0h+lpMem], r15
0x1800209ad  movups  [rbp+1A0h+var_E0], xmm0
0x1800209b4  movups  [rbp+1A0h+var_D0], xmm0
0x1800209bb  call    T2OSSvcCreateDeltaTTF
0x1800209c0  xor     ebx, ebx
0x1800209c2  test    eax, eax
0x1800209c4  jnz     loc_180020C14
0x1800209ca  mov     rsi, [rsp+2A0h+lpMem]
0x1800209cf  lea     r8, [rbp+1A0h+var_220]
0x1800209d3  mov     r15d, [rsp+2A0h+var_230]
0x1800209d8  lea     rdx, [rbp+1A0h+var_B0]
0x1800209df  lea     rcx, [rbp+1A0h+var_1E0]
0x1800209e3  mov     [rbp+1A0h+var_1E0], rsi
0x1800209e7  mov     [rbp+1A0h+var_1D8], r15d
0x1800209eb  mov     [rbp+1A0h+var_1D4], ebx
0x1800209ee  mov     [rbp+1A0h+var_1D0], rbx
0x1800209f2  call    GetSmartOS2
0x1800209f7  test    eax, eax
0x1800209f9  jnz     short loc_180020A05
0x1800209fb  mov     edi, 104h
0x180020a00  jmp     loc_180020B70
0x180020a05  xor     r8d, r8d
0x180020a08  lea     rdx, [rbp+1A0h+var_F0]
0x180020a0f  lea     rcx, [rbp+1A0h+var_1E0]
0x180020a13  call    GetGeneric
0x180020a18  test    eax, eax
0x180020a1a  jnz     short loc_180020A26
0x180020a1c  mov     edi, 10Bh
0x180020a21  jmp     loc_180020B70
0x180020a26  mov     rax, [rbp+1A0h+var_208]
0x180020a2a  lea     r9, [rsp+2A0h+var_22C]
0x180020a2f  lea     r8, [rsp+2A0h+lpMem]
0x180020a34  mov     [rsp+2A0h+var_280], rax
0x180020a39  mov     edx, r15d
0x180020a3c  mov     [rsp+2A0h+lpMem], rbx
0x180020a41  mov     rcx, rsi
0x180020a44  call    CompressBuffer
0x180020a49  mov     edi, eax
0x180020a4b  test    eax, eax
0x180020a4d  jnz     loc_180020B70
0x180020a53  mov     rax, [rbp+1A0h+var_218]
0x180020a57  xor     ecx, ecx
0x180020a59  mov     [rbp+1A0h+var_200], rbx
0x180020a5d  mov     [rbp+1A0h+var_21C], ecx
0x180020a60  test    rax, rax
0x180020a63  jz      loc_180020AFC
0x180020a69  mov     edx, [rbp+1A0h+var_20C]
0x180020a6c  lea     r9, [rsp+2A0h+var_230]
0x180020a71  mov     [rsp+2A0h+var_230], ecx
0x180020a75  lea     r8, [rbp+1A0h+var_218]
0x180020a79  mov     [rbp+1A0h+var_218], rcx
0x180020a7d  movzx   ecx, [rbp+1A0h+arg_50]
0x180020a84  mov     word ptr [rsp+2A0h+var_258], cx
0x180020a89  mov     rcx, [rbp+1A0h+var_1F8]
0x180020a8d  mov     [rsp+2A0h+var_260], rcx
0x180020a92  mov     ecx, [rbp+1A0h+var_210]
0x180020a95  mov     word ptr [rsp+2A0h+var_268], cx
0x180020a9a  movzx   ecx, [rbp+1A0h+arg_40]
0x180020aa1  mov     word ptr [rsp+2A0h+var_270], cx
0x180020aa6  movzx   ecx, [rbp+1A0h+arg_30]
0x180020aad  mov     word ptr [rsp+2A0h+var_280], cx
0x180020ab2  mov     rcx, rax
0x180020ab5  call    T2OSSvcCreateDeltaTTF
0x180020aba  mov     rdi, [rbp+1A0h+var_218]
0x180020abe  lea     r9, [rbp+1A0h+var_21C]
0x180020ac2  mov     edx, [rsp+2A0h+var_230]
0x180020ac6  lea     r8, [rbp+1A0h+var_200]
0x180020aca  xor     ecx, ecx
0x180020acc  test    eax, eax
0x180020ace  mov     rax, [rbp+1A0h+var_208]
0x180020ad2  mov     [rsp+2A0h+var_280], rax
0x180020ad7  cmovnz  rdi, rcx
0x180020adb  mov     rcx, rdi
0x180020ade  call    CompressBuffer
0x180020ae3  mov     rbx, [rbp+1A0h+var_200]
0x180020ae7  xor     edx, edx
0x180020ae9  test    eax, eax
0x180020aeb  cmovnz  rbx, rdx
0x180020aef  test    rdi, rdi
0x180020af2  jz      short loc_180020AFC
0x180020af4  mov     rcx, rdi; lpMem
0x180020af7  call    T2free
0x180020afc  mov     r8d, [rsp+2A0h+var_22C]
0x180020b01  lea     rax, [rbp+1A0h+var_1C0]
0x180020b05  mov     [rsp+2A0h+var_240], rax
0x180020b0a  mov     r9, rbx
0x180020b0d  mov     rax, [rbp+1A0h+var_1F0]
0x180020b11  mov     edx, r15d
0x180020b14  mov     [rsp+2A0h+var_248], rax
0x180020b19  mov     rcx, rsi
0x180020b1c  mov     rax, [rbp+1A0h+var_1E8]
0x180020b20  mov     [rsp+2A0h+var_250], rax
0x180020b25  mov     eax, [rbp+1A0h+var_220]
0x180020b28  mov     [rsp+2A0h+var_258], eax
0x180020b2c  lea     rax, [rbp+1A0h+var_B0]
0x180020b33  mov     [rsp+2A0h+var_260], rax
0x180020b38  mov     eax, dword ptr [rbp+1A0h+var_F0+8]
0x180020b3e  mov     [rsp+2A0h+var_268], eax
0x180020b42  mov     eax, [rbp+1A0h+var_21C]
0x180020b45  mov     [rsp+2A0h+var_270], r14d
0x180020b4a  mov     [rsp+2A0h+var_278], r14d
0x180020b4f  mov     dword ptr [rsp+2A0h+var_280], eax
0x180020b53  call    GetAllocEmbedHeaderData
0x180020b58  mov     edi, eax
0x180020b5a  test    eax, eax
0x180020b5c  jz      short loc_180020B7F
0x180020b5e  mov     rcx, rbx; lpMem
0x180020b61  call    T2free
0x180020b66  mov     rcx, [rsp+2A0h+lpMem]; lpMem
0x180020b6b  call    T2free
0x180020b70  mov     rcx, rsi; lpMem
0x180020b73  call    T2free
0x180020b78  mov     eax, edi
0x180020b7a  jmp     loc_180020C14
0x180020b7f  mov     rcx, rsi; lpMem
0x180020b82  call    T2free
0x180020b87  mov     rcx, [rbp+1A0h+arg_68]
0x180020b8e  lea     r8, [rbp+1A0h+var_1C0]
0x180020b92  mov     rdx, r13
0x180020b95  call    WriteEmbeddedHeader
0x180020b9a  mov     edi, eax
0x180020b9c  test    eax, eax
0x180020b9e  jz      short loc_180020BBD
0x180020ba0  mov     rcx, rbx; lpMem
0x180020ba3  call    T2free
0x180020ba8  mov     rcx, [rsp+2A0h+lpMem]; lpMem
0x180020bad  call    T2free
0x180020bb2  lea     rcx, [rbp+1A0h+var_1C0]
0x180020bb6  call    DeallocEmbedHeaderData
0x180020bbb  jmp     short loc_180020B78
0x180020bbd  test    rbx, rbx
0x180020bc0  jz      short loc_180020BCF
0x180020bc2  or      dword ptr [r12], 2
0x180020bc7  mov     rcx, rbx; lpMem
0x180020bca  call    T2free
0x180020bcf  mov     rbx, [rsp+2A0h+lpMem]
0x180020bd4  and     r14d, 10000000h
0x180020bdb  mov     r9, [rbp+1A0h+arg_68]
0x180020be2  mov     r8d, r14d
0x180020be5  mov     edx, [rsp+2A0h+var_22C]
0x180020be9  mov     rcx, rbx
0x180020bec  mov     [rsp+2A0h+var_280], r13
0x180020bf1  call    WriteFontImage
0x180020bf6  mov     edi, eax
0x180020bf8  test    eax, eax
0x180020bfa  jz      short loc_180020C01
0x180020bfc  mov     rcx, rbx
0x180020bff  jmp     short loc_180020BAD
0x180020c01  lea     rcx, [rbp+1A0h+var_1C0]
0x180020c05  call    DeallocEmbedHeaderData
0x180020c0a  mov     rcx, rbx; lpMem
0x180020c0d  call    T2free
0x180020c12  xor     eax, eax
0x180020c14  mov     rcx, [rbp+1A0h+var_50]
0x180020c1b  xor     rcx, rsp; StackCookie
0x180020c1e  call    __security_check_cookie
0x180020c23  add     rsp, 268h
0x180020c2a  pop     r15
0x180020c2c  pop     r14
0x180020c2e  pop     r13
0x180020c30  pop     r12
0x180020c32  pop     rdi
0x180020c33  pop     rsi
0x180020c34  pop     rbx
0x180020c35  pop     rbp
0x180020c36  retn
```

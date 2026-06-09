# VsmmControlGpaAccessTracking

- ea: `0x1400d7d24`
- end: `0x1400d82e6`
- name: `VsmmControlGpaAccessTracking`
- size: `1474`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, unsigned __int64, volatile void *Address, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140031fa4`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x14002f524`
- `0x1400303c0`
- `0x140030760`
- `0x140038630`
- `0x1400d13a8`
- `0x1400d7d24`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400d7fc1`
- `ntoskrnl!ProbeForWrite` at `0x1400d7fc1`

## string_xrefs

- `0x1400d7ddb`: `VsmmControlGpaAccessTracking`
- `0x1400d7e0c`: `VsmmControlGpaAccessTracking`
- `0x1400d7e3b`: `VsmmControlGpaAccessTracking`
- `0x1400d7e6f`: `VsmmControlGpaAccessTracking`
- `0x1400d7ea0`: `VsmmControlGpaAccessTracking`
- `0x1400d7ecd`: `VsmmControlGpaAccessTracking`
- `0x1400d7f03`: `VsmmControlGpaAccessTracking`
- `0x1400d7f35`: `VsmmControlGpaAccessTracking`
- `0x1400d7f6b`: `VsmmControlGpaAccessTracking`
- `0x1400d7f97`: `VsmmControlGpaAccessTracking`
- `0x1400d7fe8`: `VsmmControlGpaAccessTracking`
- `0x1400d802f`: `VsmmControlGpaAccessTracking`
- `0x1400d8065`: `VsmmControlGpaAccessTracking`
- `0x1400d80b2`: `VsmmControlGpaAccessTracking`
- `0x1400d80d2`: `VsmmControlGpaAccessTracking`
- `0x1400d812e`: `VsmmControlGpaAccessTracking`

## pseudocode

```c
__int64 __fastcall VsmmControlGpaAccessTracking(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int64 a4,
        volatile void *Address,
        __int64 a6,
        __int64 a7,
        unsigned int a8)
{
  int v11; // edi
  unsigned int v12; // ebx
  __int64 v13; // r9
  int v14; // r10d
  char v16; // [rsp+40h] [rbp-178h]
  __int64 v17; // [rsp+48h] [rbp-170h] BYREF
  char v18; // [rsp+50h] [rbp-168h]
  int v19; // [rsp+58h] [rbp-160h] BYREF
  __int64 v20; // [rsp+60h] [rbp-158h] BYREF
  volatile void *v21; // [rsp+68h] [rbp-150h] BYREF
  __int64 v22; // [rsp+70h] [rbp-148h] BYREF
  unsigned __int64 v23; // [rsp+78h] [rbp-140h] BYREF
  unsigned __int64 v24; // [rsp+80h] [rbp-138h] BYREF
  _BYTE v25[32]; // [rsp+90h] [rbp-128h] BYREF
  _BYTE v26[16]; // [rsp+B0h] [rbp-108h] BYREF
  _BYTE v27[16]; // [rsp+C0h] [rbp-F8h] BYREF
  int *v28; // [rsp+D0h] [rbp-E8h]
  __int64 v29; // [rsp+D8h] [rbp-E0h]
  __int64 *v30; // [rsp+E0h] [rbp-D8h]
  __int64 v31; // [rsp+E8h] [rbp-D0h]
  __int64 v32; // [rsp+F0h] [rbp-C8h]
  __int64 v33; // [rsp+F8h] [rbp-C0h]
  _DWORD *v34; // [rsp+100h] [rbp-B8h]
  __int64 v35; // [rsp+108h] [rbp-B0h]
  __int64 v36; // [rsp+110h] [rbp-A8h]
  _DWORD v37[2]; // [rsp+118h] [rbp-A0h] BYREF
  __int64 *v38; // [rsp+120h] [rbp-98h]
  __int64 v39; // [rsp+128h] [rbp-90h]
  __int64 *v40; // [rsp+130h] [rbp-88h]
  __int64 v41; // [rsp+138h] [rbp-80h]
  volatile void **v42; // [rsp+140h] [rbp-78h]
  __int64 v43; // [rsp+148h] [rbp-70h]
  __int64 *v44; // [rsp+150h] [rbp-68h]
  __int64 v45; // [rsp+158h] [rbp-60h]
  __int64 *v46; // [rsp+160h] [rbp-58h]
  __int64 v47; // [rsp+168h] [rbp-50h]

  v17 = a2;
  v20 = a1;
  v22 = a2;
  v19 = a3;
  v23 = a4;
  v21 = Address;
  v16 = 0;
  v18 = 0;
  if ( a4 - 1 > 0xFFFFFFFFFFFFELL )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 168);
    goto LABEL_42;
  }
  if ( a3 > 2 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 175);
    goto LABEL_42;
  }
  if ( (((1LL << (9 * (unsigned __int8)a3)) - 1) & a2) != 0 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 185);
LABEL_42:
    v12 = a8;
    goto LABEL_43;
  }
  if ( a4 > (unsigned __int64)~a2 >> (9 * (unsigned __int8)a3) )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 192);
    goto LABEL_42;
  }
  v12 = a8;
  if ( a8 >= 0x20 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 199);
    goto LABEL_43;
  }
  if ( (a8 & 2) == 0 && (a8 & 4) == 0 && (a8 & 8) == 0 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 206);
    goto LABEL_43;
  }
  if ( (a8 & 4) != 0 )
  {
    if ( (a8 & 8) != 0 )
    {
      v11 = -1073741811;
      VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 213);
      goto LABEL_43;
    }
  }
  else if ( (a8 & 8) != 0 && a3 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 220);
    goto LABEL_43;
  }
  if ( (Address != 0) == ((a8 & 2) == 0) )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 230);
    goto LABEL_43;
  }
  if ( (a7 || a6) && a3 )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 241);
    goto LABEL_43;
  }
  if ( a7 && (a8 & 4) == 0 && ((a8 & 2) == 0 || (a8 & 0x10) != 0) )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 254);
    goto LABEL_43;
  }
  if ( a6 )
  {
    if ( (a8 & 2) == 0 )
    {
      v11 = -1073741811;
      VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 264);
      goto LABEL_43;
    }
  }
  else if ( (a8 & 2) == 0 )
  {
    if ( (a8 & 0x10) != 0 )
    {
      v11 = -1073741811;
      VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 287);
      goto LABEL_43;
    }
    goto LABEL_37;
  }
  ProbeForWrite(Address, 8 * ((a4 + 63) >> 6), 8u);
LABEL_37:
  if ( VidOpCtrlStart((volatile signed __int32 *)(a1 + 10664)) )
  {
    v16 = 1;
    v11 = VsmmHvControlGpaAccessTracking(a1, v14, a3, a4, v13, a6, a7, a8);
  }
  else
  {
    v11 = -1073741436;
    VidTraceErrorStatusInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 298);
  }
LABEL_43:
  if ( v16 )
    VidOpCtrlFinish(a1 + 10664);
  if ( v11 < 0 && (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v26, "VsmmControlGpaAccessTracking");
    tlgCreate1Sz_char(v27, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    v19 = 335;
    v28 = &v19;
    v29 = 4;
    LODWORD(v20) = v11;
    v30 = &v20;
    v31 = 4;
    v32 = a1 + 656;
    v33 = 16;
    v34 = v37;
    v35 = 2;
    v36 = *(_QWORD *)(a1 + 128);
    v37[0] = *(unsigned __int16 *)(a1 + 120);
    v37[1] = 0;
    v23 = *(_QWORD *)(a1 + 648);
    v38 = (__int64 *)&v23;
    v39 = 8;
    v22 = v17;
    v40 = &v22;
    v41 = 8;
    LODWORD(v21) = a3;
    v42 = &v21;
    v43 = 4;
    v24 = a4;
    v44 = (__int64 *)&v24;
    v45 = 8;
    LODWORD(v17) = v12;
    v46 = &v17;
    v47 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, &word_1400587A6, 0, 0, 14, v25);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400d7d24  push    rbx
0x1400d7d26  push    rdi
0x1400d7d27  push    r12
0x1400d7d29  push    r13
0x1400d7d2b  push    r14
0x1400d7d2d  push    r15
0x1400d7d2f  sub     rsp, 188h
0x1400d7d36  mov     rax, cs:__security_cookie
0x1400d7d3d  xor     rax, rsp
0x1400d7d40  mov     [rsp+1B8h+var_48], rax
0x1400d7d48  mov     r15, r9
0x1400d7d4b  mov     r14d, r8d
0x1400d7d4e  mov     r10, rdx
0x1400d7d51  mov     [rsp+1B8h+var_170], rdx
0x1400d7d56  mov     r13, rcx
0x1400d7d59  mov     [rsp+1B8h+var_158], rcx
0x1400d7d5e  mov     [rsp+1B8h+var_148], rdx
0x1400d7d63  mov     [rsp+1B8h+var_160], r8d
0x1400d7d68  mov     [rsp+1B8h+var_140], r9
0x1400d7d6d  mov     r9, [rsp+1B8h+Address]
0x1400d7d75  mov     [rsp+1B8h+var_150], r9
0x1400d7d7a  mov     rdi, [rsp+1B8h+arg_28]
0x1400d7d82  mov     r12, [rsp+1B8h+arg_30]
0x1400d7d8a  xor     al, al
0x1400d7d8c  mov     [rsp+1B8h+var_178], al
0x1400d7d90  mov     [rsp+1B8h+var_168], al
0x1400d7d94  lea     rax, [r15-1]
0x1400d7d98  mov     rcx, 0FFFFFFFFFFFFEh
0x1400d7da2  cmp     rax, rcx
0x1400d7da5  ja      loc_1400D80C0
0x1400d7dab  cmp     r8d, 2
0x1400d7daf  ja      loc_1400D80A0
0x1400d7db5  lea     ecx, [r8+r8*8]
0x1400d7db9  mov     eax, 1
0x1400d7dbe  shl     rax, cl
0x1400d7dc1  dec     rax
0x1400d7dc4  test    rdx, rax
0x1400d7dc7  jz      short loc_1400D7DEC
0x1400d7dc9  mov     edi, 0C000000Dh
0x1400d7dce  mov     r8d, 0B9h
0x1400d7dd4  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7ddb  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7de2  call    VidTraceErrorInternal0
0x1400d7de7  jmp     loc_1400D80DE
0x1400d7dec  mov     rax, rdx
0x1400d7def  not     rax
0x1400d7df2  shr     rax, cl
0x1400d7df5  cmp     r15, rax
0x1400d7df8  jbe     short loc_1400D7E1D
0x1400d7dfa  mov     edi, 0C000000Dh
0x1400d7dff  mov     r8d, 0C0h
0x1400d7e05  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7e0c  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7e13  call    VidTraceErrorInternal0
0x1400d7e18  jmp     loc_1400D80DE
0x1400d7e1d  mov     ebx, [rsp+1B8h+arg_38]
0x1400d7e24  cmp     ebx, 20h ; ' '
0x1400d7e27  jb      short loc_1400D7E4C
0x1400d7e29  mov     edi, 0C000000Dh
0x1400d7e2e  mov     r8d, 0C7h
0x1400d7e34  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7e3b  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7e42  call    VidTraceErrorInternal0
0x1400d7e47  jmp     loc_1400D80E5
0x1400d7e4c  mov     edx, ebx
0x1400d7e4e  and     edx, 2
0x1400d7e51  jnz     short loc_1400D7E80
0x1400d7e53  test    bl, 4
0x1400d7e56  jnz     short loc_1400D7E80
0x1400d7e58  test    bl, 8
0x1400d7e5b  jnz     short loc_1400D7E80
0x1400d7e5d  mov     edi, 0C000000Dh
0x1400d7e62  mov     r8d, 0CEh
0x1400d7e68  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7e6f  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7e76  call    VidTraceErrorInternal0
0x1400d7e7b  jmp     loc_1400D80E5
0x1400d7e80  mov     r8d, ebx
0x1400d7e83  and     r8d, 4
0x1400d7e87  jz      short loc_1400D7EB1
0x1400d7e89  test    bl, 8
0x1400d7e8c  jz      short loc_1400D7EDE
0x1400d7e8e  mov     edi, 0C000000Dh
0x1400d7e93  mov     r8d, 0D5h
0x1400d7e99  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7ea0  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7ea7  call    VidTraceErrorInternal0
0x1400d7eac  jmp     loc_1400D80E5
0x1400d7eb1  test    bl, 8
0x1400d7eb4  jz      short loc_1400D7EDE
0x1400d7eb6  test    r14d, r14d
0x1400d7eb9  jz      short loc_1400D7EDE
0x1400d7ebb  mov     edi, 0C000000Dh
0x1400d7ec0  mov     r8d, 0DCh
0x1400d7ec6  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7ecd  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7ed4  call    VidTraceErrorInternal0
0x1400d7ed9  jmp     loc_1400D80E5
0x1400d7ede  xor     ecx, ecx
0x1400d7ee0  test    edx, edx
0x1400d7ee2  setz    cl
0x1400d7ee5  xor     eax, eax
0x1400d7ee7  test    r9, r9
0x1400d7eea  setnz   al
0x1400d7eed  cmp     eax, ecx
0x1400d7eef  jnz     short loc_1400D7F14
0x1400d7ef1  mov     edi, 0C000000Dh
0x1400d7ef6  mov     r8d, 0E6h
0x1400d7efc  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7f03  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7f0a  call    VidTraceErrorInternal0
0x1400d7f0f  jmp     loc_1400D80E5
0x1400d7f14  test    r12, r12
0x1400d7f17  jnz     short loc_1400D7F1E
0x1400d7f19  test    rdi, rdi
0x1400d7f1c  jz      short loc_1400D7F46
0x1400d7f1e  test    r14d, r14d
0x1400d7f21  jz      short loc_1400D7F46
0x1400d7f23  mov     edi, 0C000000Dh
0x1400d7f28  mov     r8d, 0F1h
0x1400d7f2e  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7f35  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7f3c  call    VidTraceErrorInternal0
0x1400d7f41  jmp     loc_1400D80E5
0x1400d7f46  test    r12, r12
0x1400d7f49  jz      short loc_1400D7F7C
0x1400d7f4b  test    r8d, r8d
0x1400d7f4e  jnz     short loc_1400D7F7C
0x1400d7f50  test    edx, edx
0x1400d7f52  jz      short loc_1400D7F59
0x1400d7f54  test    bl, 10h
0x1400d7f57  jz      short loc_1400D7F7C
0x1400d7f59  mov     edi, 0C000000Dh
0x1400d7f5e  mov     r8d, 0FEh
0x1400d7f64  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7f6b  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7f72  call    VidTraceErrorInternal0
0x1400d7f77  jmp     loc_1400D80E5
0x1400d7f7c  test    rdi, rdi
0x1400d7f7f  jz      short loc_1400D7FA8
0x1400d7f81  test    edx, edx
0x1400d7f83  jnz     short loc_1400D7FAC
0x1400d7f85  mov     edi, 0C000000Dh
0x1400d7f8a  mov     r8d, 108h
0x1400d7f90  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7f97  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7f9e  call    VidTraceErrorInternal0
0x1400d7fa3  jmp     loc_1400D80E5
0x1400d7fa8  test    edx, edx
0x1400d7faa  jz      short loc_1400D8018
0x1400d7fac  lea     rdx, [r15+3Fh]
0x1400d7fb0  shr     rdx, 6
0x1400d7fb4  shl     rdx, 3; Length
0x1400d7fb8  mov     r8d, 8; Alignment
0x1400d7fbe  mov     rcx, r9; Address
0x1400d7fc1  call    cs:__imp_ProbeForWrite
0x1400d7fc8  nop     dword ptr [rax+rax+00h]
0x1400d7fcd  mov     r10, [rsp+1B8h+var_170]
0x1400d7fd2  mov     r9, [rsp+1B8h+var_150]
0x1400d7fd7  jmp     short loc_1400D8040
0x1400d7fd9  mov     edi, eax
0x1400d7fdb  mov     r8d, 118h
0x1400d7fe1  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d7fe8  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d7fef  call    VidTraceErrorInternal0
0x1400d7ff4  mov     ebx, [rsp+1B8h+arg_38]
0x1400d7ffb  mov     al, [rsp+1B8h+var_168]
0x1400d7fff  mov     r13, [rsp+1B8h+var_158]
0x1400d8004  mov     r12, [rsp+1B8h+var_148]
0x1400d8009  mov     r14d, [rsp+1B8h+var_160]
0x1400d800e  mov     r15, [rsp+1B8h+var_140]
0x1400d8013  jmp     loc_1400D80EE
0x1400d8018  test    bl, 10h
0x1400d801b  jz      short loc_1400D8040
0x1400d801d  mov     edi, 0C000000Dh
0x1400d8022  mov     r8d, 11Fh
0x1400d8028  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d802f  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d8036  call    VidTraceErrorInternal0
0x1400d803b  jmp     loc_1400D80E5
0x1400d8040  lea     rcx, [r13+29A8h]
0x1400d8047  call    VidOpCtrlStart
0x1400d804c  test    al, al
0x1400d804e  jnz     short loc_1400D8073
0x1400d8050  mov     edi, 0C0000184h
0x1400d8055  mov     r9d, edi
0x1400d8058  mov     r8d, 12Ah
0x1400d805e  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8065  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d806c  call    VidTraceErrorStatusInternal0
0x1400d8071  jmp     short loc_1400D80E5
0x1400d8073  mov     [rsp+1B8h+var_178], 1
0x1400d8078  mov     [rsp+1B8h+var_180], ebx
0x1400d807c  mov     [rsp+1B8h+var_188], r12
0x1400d8081  mov     [rsp+1B8h+var_190], rdi
0x1400d8086  mov     [rsp+1B8h+var_198], r9
0x1400d808b  mov     r9, r15
0x1400d808e  mov     r8d, r14d
0x1400d8091  mov     rdx, r10
0x1400d8094  mov     rcx, r13
0x1400d8097  call    VsmmHvControlGpaAccessTracking
0x1400d809c  mov     edi, eax
0x1400d809e  jmp     short loc_1400D80E5
0x1400d80a0  mov     edi, 0C000000Dh
0x1400d80a5  mov     r8d, 0AFh
0x1400d80ab  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d80b2  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d80b9  call    VidTraceErrorInternal0
0x1400d80be  jmp     short loc_1400D80DE
0x1400d80c0  mov     edi, 0C000000Dh
0x1400d80c5  mov     r8d, 0A8h
0x1400d80cb  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d80d2  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d80d9  call    VidTraceErrorInternal0
0x1400d80de  mov     ebx, [rsp+1B8h+arg_38]
0x1400d80e5  mov     r12, [rsp+1B8h+var_170]
0x1400d80ea  mov     al, [rsp+1B8h+var_178]
0x1400d80ee  test    al, al
0x1400d80f0  jz      short loc_1400D80FE
0x1400d80f2  lea     rcx, [r13+29A8h]
0x1400d80f9  call    VidOpCtrlFinish
0x1400d80fe  test    edi, edi
0x1400d8100  jns     loc_1400D82C1
0x1400d8106  mov     eax, cs:dword_140064110
0x1400d810c  cmp     eax, 2
0x1400d810f  jbe     loc_1400D82C1
0x1400d8115  mov     edx, 100h
0x1400d811a  lea     rcx, dword_140064110
0x1400d8121  call    _tlgKeywordOn
0x1400d8126  test    al, al
0x1400d8128  jz      loc_1400D82C1
0x1400d812e  lea     rdx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400d8135  lea     rcx, [rsp+1B8h+var_108]
0x1400d813d  call    _tlgCreate1Sz_char
0x1400d8142  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400d8149  lea     rcx, [rsp+1B8h+var_F8]
0x1400d8151  call    _tlgCreate1Sz_char
0x1400d8156  mov     [rsp+1B8h+var_160], 14Fh
0x1400d815e  lea     rax, [rsp+1B8h+var_160]
0x1400d8163  mov     [rsp+1B8h+var_E8], rax
0x1400d816b  mov     [rsp+1B8h+var_E0], 4
0x1400d8177  mov     dword ptr [rsp+1B8h+var_158], edi
0x1400d817b  lea     rax, [rsp+1B8h+var_158]
0x1400d8180  mov     [rsp+1B8h+var_D8], rax
0x1400d8188  mov     [rsp+1B8h+var_D0], 4
0x1400d8194  lea     rax, [r13+290h]
0x1400d819b  mov     [rsp+1B8h+var_C8], rax
0x1400d81a3  mov     [rsp+1B8h+var_C0], 10h
0x1400d81af  lea     rax, [rsp+1B8h+var_A0]
0x1400d81b7  mov     [rsp+1B8h+var_B8], rax
0x1400d81bf  mov     [rsp+1B8h+var_B0], 2
0x1400d81cb  mov     rax, [r13+80h]
0x1400d81d2  mov     [rsp+1B8h+var_A8], rax
0x1400d81da  movzx   eax, word ptr [r13+78h]
0x1400d81df  mov     [rsp+1B8h+var_A0], eax
0x1400d81e6  mov     [rsp+1B8h+var_9C], 0
0x1400d81f1  mov     rax, [r13+288h]
0x1400d81f8  mov     [rsp+1B8h+var_140], rax
0x1400d81fd  lea     rax, [rsp+1B8h+var_140]
0x1400d8202  mov     [rsp+1B8h+var_98], rax
0x1400d820a  mov     [rsp+1B8h+var_90], 8
0x1400d8216  mov     [rsp+1B8h+var_148], r12
0x1400d821b  lea     rax, [rsp+1B8h+var_148]
0x1400d8220  mov     [rsp+1B8h+var_88], rax
0x1400d8228  mov     [rsp+1B8h+var_80], 8
0x1400d8234  mov     dword ptr [rsp+1B8h+var_150], r14d
0x1400d8239  lea     rax, [rsp+1B8h+var_150]
0x1400d823e  mov     [rsp+1B8h+var_78], rax
0x1400d8246  mov     [rsp+1B8h+var_70], 4
0x1400d8252  mov     [rsp+1B8h+var_138], r15
0x1400d825a  lea     rax, [rsp+1B8h+var_138]
0x1400d8262  mov     [rsp+1B8h+var_68], rax
0x1400d826a  mov     [rsp+1B8h+var_60], 8
0x1400d8276  mov     dword ptr [rsp+1B8h+var_170], ebx
0x1400d827a  lea     rax, [rsp+1B8h+var_170]
0x1400d827f  mov     [rsp+1B8h+var_58], rax
0x1400d8287  mov     [rsp+1B8h+var_50], 4
0x1400d8293  lea     rax, [rsp+1B8h+var_128]
0x1400d829b  mov     [rsp+1B8h+var_190], rax
0x1400d82a0  mov     dword ptr [rsp+1B8h+var_198], 0Eh
0x1400d82a8  xor     r9d, r9d
0x1400d82ab  xor     r8d, r8d
0x1400d82ae  lea     rdx, word_1400587A6
0x1400d82b5  lea     rcx, dword_140064110
0x1400d82bc  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400d82c1  mov     eax, edi
0x1400d82c3  mov     rcx, [rsp+1B8h+var_48]
0x1400d82cb  xor     rcx, rsp; StackCookie
0x1400d82ce  call    __security_check_cookie
0x1400d82d3  add     rsp, 188h
0x1400d82da  pop     r15
0x1400d82dc  pop     r14
0x1400d82de  pop     r13
0x1400d82e0  pop     r12
0x1400d82e2  pop     rdi
0x1400d82e3  pop     rbx
0x1400d82e4  retn
```

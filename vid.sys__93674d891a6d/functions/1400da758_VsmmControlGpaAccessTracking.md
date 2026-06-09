# VsmmControlGpaAccessTracking

- ea: `0x1400da758`
- end: `0x1400dad1a`
- name: `VsmmControlGpaAccessTracking`
- size: `1474`
- prototype: `__int64 __fastcall(int, int, int, int, volatile void *Address, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400321a4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x14002f724`
- `0x1400305c0`
- `0x140030960`
- `0x1400386a0`
- `0x1400d3d48`
- `0x1400da758`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400da9f5`
- `ntoskrnl!ProbeForWrite` at `0x1400da9f5`

## string_xrefs

- `0x1400da80f`: `VsmmControlGpaAccessTracking`
- `0x1400da840`: `VsmmControlGpaAccessTracking`
- `0x1400da86f`: `VsmmControlGpaAccessTracking`
- `0x1400da8a3`: `VsmmControlGpaAccessTracking`
- `0x1400da8d4`: `VsmmControlGpaAccessTracking`
- `0x1400da901`: `VsmmControlGpaAccessTracking`
- `0x1400da937`: `VsmmControlGpaAccessTracking`
- `0x1400da969`: `VsmmControlGpaAccessTracking`
- `0x1400da99f`: `VsmmControlGpaAccessTracking`
- `0x1400da9cb`: `VsmmControlGpaAccessTracking`
- `0x1400daa1c`: `VsmmControlGpaAccessTracking`
- `0x1400daa63`: `VsmmControlGpaAccessTracking`
- `0x1400daa99`: `VsmmControlGpaAccessTracking`
- `0x1400daae6`: `VsmmControlGpaAccessTracking`
- `0x1400dab06`: `VsmmControlGpaAccessTracking`
- `0x1400dab62`: `VsmmControlGpaAccessTracking`

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
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // r9
  int v16; // r10d
  char v18; // [rsp+40h] [rbp-178h]
  __int64 v19; // [rsp+48h] [rbp-170h] BYREF
  char v20; // [rsp+50h] [rbp-168h]
  int v21; // [rsp+58h] [rbp-160h] BYREF
  __int64 v22; // [rsp+60h] [rbp-158h] BYREF
  volatile void *v23; // [rsp+68h] [rbp-150h] BYREF
  __int64 v24; // [rsp+70h] [rbp-148h] BYREF
  unsigned __int64 v25; // [rsp+78h] [rbp-140h] BYREF
  unsigned __int64 v26; // [rsp+80h] [rbp-138h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-128h] BYREF
  _BYTE v28[16]; // [rsp+B0h] [rbp-108h] BYREF
  _BYTE v29[16]; // [rsp+C0h] [rbp-F8h] BYREF
  int *v30; // [rsp+D0h] [rbp-E8h]
  __int64 v31; // [rsp+D8h] [rbp-E0h]
  __int64 *v32; // [rsp+E0h] [rbp-D8h]
  __int64 v33; // [rsp+E8h] [rbp-D0h]
  __int64 v34; // [rsp+F0h] [rbp-C8h]
  __int64 v35; // [rsp+F8h] [rbp-C0h]
  _DWORD *v36; // [rsp+100h] [rbp-B8h]
  __int64 v37; // [rsp+108h] [rbp-B0h]
  __int64 v38; // [rsp+110h] [rbp-A8h]
  _DWORD v39[2]; // [rsp+118h] [rbp-A0h] BYREF
  __int64 *v40; // [rsp+120h] [rbp-98h]
  __int64 v41; // [rsp+128h] [rbp-90h]
  __int64 *v42; // [rsp+130h] [rbp-88h]
  __int64 v43; // [rsp+138h] [rbp-80h]
  volatile void **v44; // [rsp+140h] [rbp-78h]
  __int64 v45; // [rsp+148h] [rbp-70h]
  __int64 *v46; // [rsp+150h] [rbp-68h]
  __int64 v47; // [rsp+158h] [rbp-60h]
  __int64 *v48; // [rsp+160h] [rbp-58h]
  __int64 v49; // [rsp+168h] [rbp-50h]

  v19 = a2;
  v22 = a1;
  v24 = a2;
  v21 = a3;
  v25 = a4;
  v23 = Address;
  v18 = 0;
  v20 = 0;
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
    v14 = a8;
    goto LABEL_43;
  }
  if ( a4 > (unsigned __int64)~a2 >> (9 * (unsigned __int8)a3) )
  {
    v11 = -1073741811;
    VidTraceErrorInternal0("VsmmControlGpaAccessTracking", "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c", 192);
    goto LABEL_42;
  }
  v14 = a8;
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
  if ( (unsigned __int8)VidOpCtrlStart(a1 + 10664) )
  {
    v18 = 1;
    v11 = VsmmHvControlGpaAccessTracking(a1, v16, a3, a4, v15, a6, a7, a8);
  }
  else
  {
    v11 = -1073741436;
    VidTraceErrorStatusInternal0(
      "VsmmControlGpaAccessTracking",
      "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c",
      298,
      3221225860LL);
  }
LABEL_43:
  if ( v18 )
    VidOpCtrlFinish(a1 + 10664, v12, v13);
  if ( v11 < 0 && (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v28, "VsmmControlGpaAccessTracking");
    tlgCreate1Sz_char(v29, "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c");
    v21 = 335;
    v30 = &v21;
    v31 = 4;
    LODWORD(v22) = v11;
    v32 = &v22;
    v33 = 4;
    v34 = a1 + 656;
    v35 = 16;
    v36 = v39;
    v37 = 2;
    v38 = *(_QWORD *)(a1 + 128);
    v39[0] = *(unsigned __int16 *)(a1 + 120);
    v39[1] = 0;
    v25 = *(_QWORD *)(a1 + 648);
    v40 = (__int64 *)&v25;
    v41 = 8;
    v24 = v19;
    v42 = &v24;
    v43 = 8;
    LODWORD(v23) = a3;
    v44 = &v23;
    v45 = 4;
    v26 = a4;
    v46 = (__int64 *)&v26;
    v47 = 8;
    LODWORD(v19) = v14;
    v48 = &v19;
    v49 = 4;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, qword_140058E90, 0, 0, 14, v27);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400da758  push    rbx
0x1400da75a  push    rdi
0x1400da75b  push    r12
0x1400da75d  push    r13
0x1400da75f  push    r14
0x1400da761  push    r15
0x1400da763  sub     rsp, 188h
0x1400da76a  mov     rax, cs:__security_cookie
0x1400da771  xor     rax, rsp
0x1400da774  mov     [rsp+1B8h+var_48], rax
0x1400da77c  mov     r15, r9
0x1400da77f  mov     r14d, r8d
0x1400da782  mov     r10, rdx
0x1400da785  mov     [rsp+1B8h+var_170], rdx
0x1400da78a  mov     r13, rcx
0x1400da78d  mov     [rsp+1B8h+var_158], rcx
0x1400da792  mov     [rsp+1B8h+var_148], rdx
0x1400da797  mov     [rsp+1B8h+var_160], r8d
0x1400da79c  mov     [rsp+1B8h+var_140], r9
0x1400da7a1  mov     r9, [rsp+1B8h+Address]
0x1400da7a9  mov     [rsp+1B8h+var_150], r9
0x1400da7ae  mov     rdi, [rsp+1B8h+arg_28]
0x1400da7b6  mov     r12, [rsp+1B8h+arg_30]
0x1400da7be  xor     al, al
0x1400da7c0  mov     [rsp+1B8h+var_178], al
0x1400da7c4  mov     [rsp+1B8h+var_168], al
0x1400da7c8  lea     rax, [r15-1]
0x1400da7cc  mov     rcx, 0FFFFFFFFFFFFEh
0x1400da7d6  cmp     rax, rcx
0x1400da7d9  ja      loc_1400DAAF4
0x1400da7df  cmp     r8d, 2
0x1400da7e3  ja      loc_1400DAAD4
0x1400da7e9  lea     ecx, [r8+r8*8]
0x1400da7ed  mov     eax, 1
0x1400da7f2  shl     rax, cl
0x1400da7f5  dec     rax
0x1400da7f8  test    rdx, rax
0x1400da7fb  jz      short loc_1400DA820
0x1400da7fd  mov     edi, 0C000000Dh
0x1400da802  mov     r8d, 0B9h
0x1400da808  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da80f  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da816  call    VidTraceErrorInternal0
0x1400da81b  jmp     loc_1400DAB12
0x1400da820  mov     rax, rdx
0x1400da823  not     rax
0x1400da826  shr     rax, cl
0x1400da829  cmp     r15, rax
0x1400da82c  jbe     short loc_1400DA851
0x1400da82e  mov     edi, 0C000000Dh
0x1400da833  mov     r8d, 0C0h
0x1400da839  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da840  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da847  call    VidTraceErrorInternal0
0x1400da84c  jmp     loc_1400DAB12
0x1400da851  mov     ebx, [rsp+1B8h+arg_38]
0x1400da858  cmp     ebx, 20h ; ' '
0x1400da85b  jb      short loc_1400DA880
0x1400da85d  mov     edi, 0C000000Dh
0x1400da862  mov     r8d, 0C7h
0x1400da868  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da86f  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da876  call    VidTraceErrorInternal0
0x1400da87b  jmp     loc_1400DAB19
0x1400da880  mov     edx, ebx
0x1400da882  and     edx, 2
0x1400da885  jnz     short loc_1400DA8B4
0x1400da887  test    bl, 4
0x1400da88a  jnz     short loc_1400DA8B4
0x1400da88c  test    bl, 8
0x1400da88f  jnz     short loc_1400DA8B4
0x1400da891  mov     edi, 0C000000Dh
0x1400da896  mov     r8d, 0CEh
0x1400da89c  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da8a3  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da8aa  call    VidTraceErrorInternal0
0x1400da8af  jmp     loc_1400DAB19
0x1400da8b4  mov     r8d, ebx
0x1400da8b7  and     r8d, 4
0x1400da8bb  jz      short loc_1400DA8E5
0x1400da8bd  test    bl, 8
0x1400da8c0  jz      short loc_1400DA912
0x1400da8c2  mov     edi, 0C000000Dh
0x1400da8c7  mov     r8d, 0D5h
0x1400da8cd  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da8d4  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da8db  call    VidTraceErrorInternal0
0x1400da8e0  jmp     loc_1400DAB19
0x1400da8e5  test    bl, 8
0x1400da8e8  jz      short loc_1400DA912
0x1400da8ea  test    r14d, r14d
0x1400da8ed  jz      short loc_1400DA912
0x1400da8ef  mov     edi, 0C000000Dh
0x1400da8f4  mov     r8d, 0DCh
0x1400da8fa  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da901  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da908  call    VidTraceErrorInternal0
0x1400da90d  jmp     loc_1400DAB19
0x1400da912  xor     ecx, ecx
0x1400da914  test    edx, edx
0x1400da916  setz    cl
0x1400da919  xor     eax, eax
0x1400da91b  test    r9, r9
0x1400da91e  setnz   al
0x1400da921  cmp     eax, ecx
0x1400da923  jnz     short loc_1400DA948
0x1400da925  mov     edi, 0C000000Dh
0x1400da92a  mov     r8d, 0E6h
0x1400da930  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da937  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da93e  call    VidTraceErrorInternal0
0x1400da943  jmp     loc_1400DAB19
0x1400da948  test    r12, r12
0x1400da94b  jnz     short loc_1400DA952
0x1400da94d  test    rdi, rdi
0x1400da950  jz      short loc_1400DA97A
0x1400da952  test    r14d, r14d
0x1400da955  jz      short loc_1400DA97A
0x1400da957  mov     edi, 0C000000Dh
0x1400da95c  mov     r8d, 0F1h
0x1400da962  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da969  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da970  call    VidTraceErrorInternal0
0x1400da975  jmp     loc_1400DAB19
0x1400da97a  test    r12, r12
0x1400da97d  jz      short loc_1400DA9B0
0x1400da97f  test    r8d, r8d
0x1400da982  jnz     short loc_1400DA9B0
0x1400da984  test    edx, edx
0x1400da986  jz      short loc_1400DA98D
0x1400da988  test    bl, 10h
0x1400da98b  jz      short loc_1400DA9B0
0x1400da98d  mov     edi, 0C000000Dh
0x1400da992  mov     r8d, 0FEh
0x1400da998  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da99f  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da9a6  call    VidTraceErrorInternal0
0x1400da9ab  jmp     loc_1400DAB19
0x1400da9b0  test    rdi, rdi
0x1400da9b3  jz      short loc_1400DA9DC
0x1400da9b5  test    edx, edx
0x1400da9b7  jnz     short loc_1400DA9E0
0x1400da9b9  mov     edi, 0C000000Dh
0x1400da9be  mov     r8d, 108h
0x1400da9c4  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400da9cb  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400da9d2  call    VidTraceErrorInternal0
0x1400da9d7  jmp     loc_1400DAB19
0x1400da9dc  test    edx, edx
0x1400da9de  jz      short loc_1400DAA4C
0x1400da9e0  lea     rdx, [r15+3Fh]
0x1400da9e4  shr     rdx, 6
0x1400da9e8  shl     rdx, 3; Length
0x1400da9ec  mov     r8d, 8; Alignment
0x1400da9f2  mov     rcx, r9; Address
0x1400da9f5  call    cs:__imp_ProbeForWrite
0x1400da9fc  nop     dword ptr [rax+rax+00h]
0x1400daa01  mov     r10, [rsp+1B8h+var_170]
0x1400daa06  mov     r9, [rsp+1B8h+var_150]
0x1400daa0b  jmp     short loc_1400DAA74
0x1400daa0d  mov     edi, eax
0x1400daa0f  mov     r8d, 118h
0x1400daa15  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400daa1c  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400daa23  call    VidTraceErrorInternal0
0x1400daa28  mov     ebx, [rsp+1B8h+arg_38]
0x1400daa2f  mov     al, [rsp+1B8h+var_168]
0x1400daa33  mov     r13, [rsp+1B8h+var_158]
0x1400daa38  mov     r12, [rsp+1B8h+var_148]
0x1400daa3d  mov     r14d, [rsp+1B8h+var_160]
0x1400daa42  mov     r15, [rsp+1B8h+var_140]
0x1400daa47  jmp     loc_1400DAB22
0x1400daa4c  test    bl, 10h
0x1400daa4f  jz      short loc_1400DAA74
0x1400daa51  mov     edi, 0C000000Dh
0x1400daa56  mov     r8d, 11Fh
0x1400daa5c  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400daa63  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400daa6a  call    VidTraceErrorInternal0
0x1400daa6f  jmp     loc_1400DAB19
0x1400daa74  lea     rcx, [r13+29A8h]
0x1400daa7b  call    VidOpCtrlStart
0x1400daa80  test    al, al
0x1400daa82  jnz     short loc_1400DAAA7
0x1400daa84  mov     edi, 0C0000184h
0x1400daa89  mov     r9d, edi
0x1400daa8c  mov     r8d, 12Ah
0x1400daa92  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400daa99  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400daaa0  call    VidTraceErrorStatusInternal0
0x1400daaa5  jmp     short loc_1400DAB19
0x1400daaa7  mov     [rsp+1B8h+var_178], 1
0x1400daaac  mov     [rsp+1B8h+var_180], ebx
0x1400daab0  mov     [rsp+1B8h+var_188], r12
0x1400daab5  mov     [rsp+1B8h+var_190], rdi
0x1400daaba  mov     [rsp+1B8h+var_198], r9
0x1400daabf  mov     r9, r15
0x1400daac2  mov     r8d, r14d
0x1400daac5  mov     rdx, r10
0x1400daac8  mov     rcx, r13
0x1400daacb  call    VsmmHvControlGpaAccessTracking
0x1400daad0  mov     edi, eax
0x1400daad2  jmp     short loc_1400DAB19
0x1400daad4  mov     edi, 0C000000Dh
0x1400daad9  mov     r8d, 0AFh
0x1400daadf  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400daae6  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400daaed  call    VidTraceErrorInternal0
0x1400daaf2  jmp     short loc_1400DAB12
0x1400daaf4  mov     edi, 0C000000Dh
0x1400daaf9  mov     r8d, 0A8h
0x1400daaff  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dab06  lea     rcx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400dab0d  call    VidTraceErrorInternal0
0x1400dab12  mov     ebx, [rsp+1B8h+arg_38]
0x1400dab19  mov     r12, [rsp+1B8h+var_170]
0x1400dab1e  mov     al, [rsp+1B8h+var_178]
0x1400dab22  test    al, al
0x1400dab24  jz      short loc_1400DAB32
0x1400dab26  lea     rcx, [r13+29A8h]
0x1400dab2d  call    VidOpCtrlFinish
0x1400dab32  test    edi, edi
0x1400dab34  jns     loc_1400DACF5
0x1400dab3a  mov     eax, cs:dword_140065110
0x1400dab40  cmp     eax, 2
0x1400dab43  jbe     loc_1400DACF5
0x1400dab49  mov     edx, 100h
0x1400dab4e  lea     rcx, dword_140065110
0x1400dab55  call    _tlgKeywordOn
0x1400dab5a  test    al, al
0x1400dab5c  jz      loc_1400DACF5
0x1400dab62  lea     rdx, aVsmmcontrolgpa; "VsmmControlGpaAccessTracking"
0x1400dab69  lea     rcx, [rsp+1B8h+var_108]
0x1400dab71  call    _tlgCreate1Sz_char
0x1400dab76  lea     rdx, aOnecoreVmVidSy_11; "onecore\\vm\\vid\\sys\\vsmm\\vsmmapi.c"
0x1400dab7d  lea     rcx, [rsp+1B8h+var_F8]
0x1400dab85  call    _tlgCreate1Sz_char
0x1400dab8a  mov     [rsp+1B8h+var_160], 14Fh
0x1400dab92  lea     rax, [rsp+1B8h+var_160]
0x1400dab97  mov     [rsp+1B8h+var_E8], rax
0x1400dab9f  mov     [rsp+1B8h+var_E0], 4
0x1400dabab  mov     dword ptr [rsp+1B8h+var_158], edi
0x1400dabaf  lea     rax, [rsp+1B8h+var_158]
0x1400dabb4  mov     [rsp+1B8h+var_D8], rax
0x1400dabbc  mov     [rsp+1B8h+var_D0], 4
0x1400dabc8  lea     rax, [r13+290h]
0x1400dabcf  mov     [rsp+1B8h+var_C8], rax
0x1400dabd7  mov     [rsp+1B8h+var_C0], 10h
0x1400dabe3  lea     rax, [rsp+1B8h+var_A0]
0x1400dabeb  mov     [rsp+1B8h+var_B8], rax
0x1400dabf3  mov     [rsp+1B8h+var_B0], 2
0x1400dabff  mov     rax, [r13+80h]
0x1400dac06  mov     [rsp+1B8h+var_A8], rax
0x1400dac0e  movzx   eax, word ptr [r13+78h]
0x1400dac13  mov     [rsp+1B8h+var_A0], eax
0x1400dac1a  mov     [rsp+1B8h+var_9C], 0
0x1400dac25  mov     rax, [r13+288h]
0x1400dac2c  mov     [rsp+1B8h+var_140], rax
0x1400dac31  lea     rax, [rsp+1B8h+var_140]
0x1400dac36  mov     [rsp+1B8h+var_98], rax
0x1400dac3e  mov     [rsp+1B8h+var_90], 8
0x1400dac4a  mov     [rsp+1B8h+var_148], r12
0x1400dac4f  lea     rax, [rsp+1B8h+var_148]
0x1400dac54  mov     [rsp+1B8h+var_88], rax
0x1400dac5c  mov     [rsp+1B8h+var_80], 8
0x1400dac68  mov     dword ptr [rsp+1B8h+var_150], r14d
0x1400dac6d  lea     rax, [rsp+1B8h+var_150]
0x1400dac72  mov     [rsp+1B8h+var_78], rax
0x1400dac7a  mov     [rsp+1B8h+var_70], 4
0x1400dac86  mov     [rsp+1B8h+var_138], r15
0x1400dac8e  lea     rax, [rsp+1B8h+var_138]
0x1400dac96  mov     [rsp+1B8h+var_68], rax
0x1400dac9e  mov     [rsp+1B8h+var_60], 8
0x1400dacaa  mov     dword ptr [rsp+1B8h+var_170], ebx
0x1400dacae  lea     rax, [rsp+1B8h+var_170]
0x1400dacb3  mov     [rsp+1B8h+var_58], rax
0x1400dacbb  mov     [rsp+1B8h+var_50], 4
0x1400dacc7  lea     rax, [rsp+1B8h+var_128]
0x1400daccf  mov     [rsp+1B8h+var_190], rax
0x1400dacd4  mov     dword ptr [rsp+1B8h+var_198], 0Eh
0x1400dacdc  xor     r9d, r9d
0x1400dacdf  xor     r8d, r8d
0x1400dace2  lea     rdx, qword_140058E90
0x1400dace9  lea     rcx, dword_140065110
0x1400dacf0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400dacf5  mov     eax, edi
0x1400dacf7  mov     rcx, [rsp+1B8h+var_48]
0x1400dacff  xor     rcx, rsp; StackCookie
0x1400dad02  call    __security_check_cookie
0x1400dad07  add     rsp, 188h
0x1400dad0e  pop     r15
0x1400dad10  pop     r14
0x1400dad12  pop     r13
0x1400dad14  pop     r12
0x1400dad16  pop     rdi
0x1400dad17  pop     rbx
0x1400dad18  retn
```

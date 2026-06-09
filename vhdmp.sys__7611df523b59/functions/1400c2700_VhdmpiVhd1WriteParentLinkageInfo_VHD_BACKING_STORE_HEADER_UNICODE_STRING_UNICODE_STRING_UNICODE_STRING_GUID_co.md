# VhdmpiVhd1WriteParentLinkageInfo(_VHD_BACKING_STORE_HEADER *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_GUID const *,_GUID const *,ulong *)

- ea: `0x1400c2700`
- end: `0x1400c2ceb`
- name: `?VhdmpiVhd1WriteParentLinkageInfo@@YAJPEAU_VHD_BACKING_STORE_HEADER@@PEAU_UNICODE_STRING@@11PEBU_GUID@@2PEAK@Z`
- size: `1515`
- prototype: `__int64 __usercall@<rax>(struct _VHD_BACKING_STORE_HEADER *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, const struct _GUID *, const struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140023560`
- `0x140035e94`
- `0x14003f11c`
- `0x14005d7c0`
- `0x14005da00`
- `0x14005dd00`
- `0x1400c1f98`
- `0x1400c2700`
- `0x1400e266c`
- `0x1400e7d68`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400c2b7c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400c2b7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2c90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2cb2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2b54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2c90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2cb2`
- `ntoskrnl!ExAllocatePool2` at `0x1400c27d5`
- `ntoskrnl!ExAllocatePool2` at `0x1400c27d5`

## string_xrefs

- `0x1400c2c28`: `VhdmpiWriteParentLocators: failed to write parent locator to offset 0x%I64x(0x%08x).`
- `0x1400c2bd6`: `VhdmpiSetParentFilename: failed to copy absolute locator to header (0x%08x)`
- `0x1400c2be7`: `VhdmpiVhd1WriteParentLinkageInfo`
- `0x1400c2c3e`: `VhdmpiVhd1WriteParentLinkageInfo`

## pseudocode

```c
__int64 __fastcall VhdmpiVhd1WriteParentLinkageInfo(
        struct _VHD_BACKING_STORE_HEADER *a1,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        const struct _GUID *a5,
        const struct _GUID *a6,
        unsigned int *a7)
{
  void *v10; // r13
  __int64 v11; // rsi
  signed int v12; // edi
  int v13; // r9d
  int v14; // r8d
  unsigned int v15; // r15d
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  unsigned __int16 *v27; // r13
  bool v28; // zf
  unsigned int *v29; // rdi
  unsigned __int64 *v30; // r12
  size_t v31; // r8
  const void *v32; // rdx
  unsigned __int64 v33; // r12
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm0
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  __int128 v41; // xmm0
  __int128 v42; // xmm1
  __int128 v43; // xmm0
  __int128 v44; // xmm1
  unsigned __int64 Length; // rcx
  _WORD *v46; // rdx
  USHORT MaximumLength; // ax
  PWSTR Buffer; // r8
  unsigned __int64 v49; // rcx
  _WORD *v50; // rcx
  __int64 v51; // rax
  unsigned __int16 v52; // dx
  char *v53; // rax
  __int64 i; // rsi
  void *v55; // rcx
  __int64 j; // rbx
  PWSTR v57; // rcx
  char v59[8]; // [rsp+28h] [rbp-D8h]
  void *Pool2; // [rsp+40h] [rbp-C0h]
  __int64 v61; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v62; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v63; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v64; // [rsp+70h] [rbp-90h]
  __int128 v65; // [rsp+80h] [rbp-80h]
  __int128 v66; // [rsp+90h] [rbp-70h]
  __int128 v67; // [rsp+A0h] [rbp-60h]
  __int128 v68; // [rsp+B0h] [rbp-50h]
  __int128 v69; // [rsp+C0h] [rbp-40h]
  __int128 v70; // [rsp+D0h] [rbp-30h]
  __int128 v71; // [rsp+E0h] [rbp-20h]
  __int128 v72; // [rsp+F0h] [rbp-10h]
  __int128 v73; // [rsp+100h] [rbp+0h]
  struct _UNICODE_STRING v74[8]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v75[32]; // [rsp+190h] [rbp+90h] BYREF

  v61 = 0;
  v10 = 0;
  memset(v74, 0, sizeof(v74));
  v11 = 256;
  memset(v75, 0, sizeof(v75));
  if ( a2->Length )
  {
    v12 = VhdmpiPrepareNewLocator(a1, (struct _LOCATOR_OPERATION *const)v75, v74, 0x756B3257u, a2);
    if ( v12 < 0 )
      goto LABEL_48;
  }
  if ( a3->Length )
  {
    v12 = VhdmpiPrepareNewLocator(a1, (struct _LOCATOR_OPERATION *const)v75, v74, 0x75723257u, a3);
    if ( v12 < 0 )
      goto LABEL_48;
  }
  Pool2 = (void *)ExAllocatePool2(256, 0x10000, 2051295318);
  v10 = Pool2;
  if ( !Pool2 )
  {
    v12 = -1073741670;
    goto LABEL_48;
  }
  LOBYTE(v13) = 2;
  LOBYTE(v14) = 1;
  VhdmpiLockUnlockVhdFile(
    (_DWORD)a1,
    (unsigned int)&v61,
    v14,
    v13,
    (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1metadata.c",
    374);
  v15 = 0;
  v16 = *(_OWORD *)((char *)a1 + 3032);
  v62 = *(_OWORD *)((char *)a1 + 3016);
  v17 = *(_OWORD *)((char *)a1 + 3048);
  v63 = v16;
  v18 = *(_OWORD *)((char *)a1 + 3064);
  v64 = v17;
  v19 = *(_OWORD *)((char *)a1 + 3080);
  v65 = v18;
  v20 = *(_OWORD *)((char *)a1 + 3096);
  v66 = v19;
  v21 = *(_OWORD *)((char *)a1 + 3112);
  v67 = v20;
  v22 = *(_OWORD *)((char *)a1 + 3128);
  v68 = v21;
  v23 = *(_OWORD *)((char *)a1 + 3144);
  v69 = v22;
  v24 = *(_OWORD *)((char *)a1 + 3160);
  v70 = v23;
  v25 = *(_OWORD *)((char *)a1 + 3176);
  v71 = v24;
  v26 = *(_OWORD *)((char *)a1 + 3192);
  v72 = v25;
  v73 = v26;
  while ( 1 )
  {
    v27 = (unsigned __int16 *)v75[4 * v15];
    if ( v27 )
      break;
    v10 = Pool2;
    *((_DWORD *)&v62 + 6 * v15) = 0;
    *((_DWORD *)&v62 + 6 * v15 + 2) = 0;
LABEL_13:
    if ( (int)++v15 >= 8 )
    {
      v34 = v63;
      *(_OWORD *)((char *)a1 + 3016) = v62;
      v35 = v64;
      *(_OWORD *)((char *)a1 + 3032) = v34;
      v36 = v65;
      *(_OWORD *)((char *)a1 + 3048) = v35;
      v37 = v66;
      *(_OWORD *)((char *)a1 + 3064) = v36;
      v38 = v67;
      *(_OWORD *)((char *)a1 + 3080) = v37;
      v39 = v68;
      *(_OWORD *)((char *)a1 + 3096) = v38;
      v40 = v69;
      *(_OWORD *)((char *)a1 + 3112) = v39;
      v41 = v70;
      *(_OWORD *)((char *)a1 + 3128) = v40;
      v42 = v71;
      *(_OWORD *)((char *)a1 + 3144) = v41;
      v43 = v72;
      *(_OWORD *)((char *)a1 + 3160) = v42;
      v44 = v73;
      *(_OWORD *)((char *)a1 + 3176) = v43;
      *(_OWORD *)((char *)a1 + 3192) = v44;
      *((struct _GUID *)a1 + 155) = *a5;
      if ( a7 )
        *((_DWORD *)a1 + 624) = *a7;
      Length = a2->Length;
      v46 = (_WORD *)((char *)a1 + 2504);
      if ( (Length & 1) != 0
        || (MaximumLength = a2->MaximumLength, (MaximumLength & 1) != 0)
        || (unsigned __int16)Length > MaximumLength
        || MaximumLength == 0xFFFF
        || (Buffer = a2->Buffer) == 0 && ((_WORD)Length || MaximumLength) )
      {
        *v46 = 0;
        v12 = -1073741811;
      }
      else
      {
        v49 = Length >> 1;
        do
        {
          if ( !v49 )
            break;
          --v49;
          *v46++ = *Buffer++;
          --v11;
        }
        while ( v11 );
        v50 = v46 - 1;
        if ( v11 )
          v50 = v46;
        *v50 = 0;
        v12 = v11 != 0 ? (v11 == 0 ? 0x80000005 : 0) : 0;
        if ( v12 >= 0 )
        {
          v51 = a2->Length;
          if ( (unsigned __int16)v51 < 0x200u )
            memset((char *)a1 + v51 + 2504, 0, 512 - v51);
          v12 = VhdmpiFlushDynamicHeader(a1);
          if ( v12 >= 0 )
          {
            for ( i = 0; i != 8; ++i )
            {
              v55 = (void *)*((_QWORD *)a1 + 2 * i + 434);
              if ( v55 )
                ExFreePoolWithTag(v55, 0x50444856u);
              *(struct _UNICODE_STRING *)((char *)a1 + 16 * i + 3464) = v74[i];
              RtlInitUnicodeStringEx(&v74[i], 0);
            }
            *((_DWORD *)a1 + 291) = 3;
            goto LABEL_48;
          }
          if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
            goto LABEL_48;
          v52 = 513;
          v53 = "VhdmpiSetParentFilename: failed to flush dynamic header (0x%08x)";
LABEL_44:
          *(_DWORD *)v59 = v12;
          TraceEvents("VhdmpiVhd1WriteParentLinkageInfo", v52, 2u, 8u, v53, *(_QWORD *)v59);
          goto LABEL_48;
        }
      }
      if ( (unsigned int)dword_140087708 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
        goto LABEL_48;
      v52 = 484;
      v53 = "VhdmpiSetParentFilename: failed to copy absolute locator to header (0x%08x)";
      goto LABEL_44;
    }
  }
  v28 = BYTE4(v75[4 * v15 + 1]) == 0;
  *((_DWORD *)&v62 + 6 * v15) = v75[4 * v15 + 1];
  v29 = (unsigned int *)&v62 + 6 * v15 + 1;
  v30 = (unsigned __int64 *)&v63 + 3 * v15;
  *((_DWORD *)&v62 + 6 * v15 + 2) = *v27;
  if ( !v28 )
  {
    *v29 = v75[4 * v15 + 3];
    *v30 = v75[4 * v15 + 2];
  }
  memset(Pool2, 0, 0x10000u);
  v31 = *v27;
  v32 = (const void *)*((_QWORD *)v27 + 1);
  v10 = Pool2;
  memmove(Pool2, v32, v31);
  v33 = *v30;
  v12 = VhdmpiMetadataSynchronousIo((struct _VHD_BACKING_STORE_HEADER *)((char *)a1 + 72), a1, 4u, Pool2, *v29, v33);
  if ( v12 >= 0 )
    goto LABEL_13;
  if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 8) )
    TraceEvents(
      "VhdmpiVhd1WriteParentLinkageInfo",
      0x1B3u,
      2u,
      8u,
      "VhdmpiWriteParentLocators: failed to write parent locator to offset 0x%I64x(0x%08x).",
      v33,
      v12);
LABEL_48:
  LOBYTE(v13) = 2;
  VhdmpiLockUnlockVhdFile(
    (_DWORD)a1,
    (unsigned int)&v61,
    0,
    v13,
    (char)"onecore\\vm\\dv\\storage\\vhd\\vhdmp\\vhd1metadata.c",
    560);
  for ( j = 0; j != 8; ++j )
  {
    v57 = v74[j].Buffer;
    if ( v57 )
      ExFreePoolWithTag(v57, 0x50444856u);
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x7A444856u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400c2700  mov     [rsp-8+arg_18], rbx
0x1400c2705  push    rbp
0x1400c2706  push    rsi
0x1400c2707  push    rdi
0x1400c2708  push    r12
0x1400c270a  push    r13
0x1400c270c  push    r14
0x1400c270e  push    r15
0x1400c2710  lea     rbp, [rsp-1A0h]
0x1400c2718  sub     rsp, 2A0h
0x1400c271f  mov     rax, cs:__security_cookie
0x1400c2726  xor     rax, rsp
0x1400c2729  mov     [rbp+1D0h+var_40], rax
0x1400c2730  mov     r15, r8
0x1400c2733  mov     r14, rdx
0x1400c2736  mov     rbx, rcx
0x1400c2739  xor     r12d, r12d
0x1400c273c  xor     edx, edx; Val
0x1400c273e  mov     [rsp+2D0h+var_288], r12
0x1400c2743  mov     r8d, 80h; Size
0x1400c2749  lea     rcx, [rbp+1D0h+var_1C0]; void *
0x1400c274d  mov     r13d, r12d
0x1400c2750  call    memset
0x1400c2755  mov     esi, 100h
0x1400c275a  lea     rcx, [rbp+1D0h+var_140]; void *
0x1400c2761  mov     r8d, esi; Size
0x1400c2764  xor     edx, edx; Val
0x1400c2766  call    memset
0x1400c276b  cmp     [r14], r12w
0x1400c276f  jbe     short loc_1400C2799
0x1400c2771  mov     r9d, 756B3257h; unsigned int
0x1400c2777  mov     [rsp+2D0h+var_2B0], r14; struct _UNICODE_STRING *
0x1400c277c  lea     r8, [rbp+1D0h+var_1C0]; struct _UNICODE_STRING *
0x1400c2780  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c2783  lea     rdx, [rbp+1D0h+var_140]; struct _LOCATOR_OPERATION *
0x1400c278a  call    ?VhdmpiPrepareNewLocator@@YAJPEAU_VHD1_BACKING_STORE@@QEAU_LOCATOR_OPERATION@@QEAU_UNICODE_STRING@@KPEAU3@@Z; VhdmpiPrepareNewLocator(_VHD1_BACKING_STORE *,_LOCATOR_OPERATION * const,_UNICODE_STRING * const,ulong,_UNICODE_STRING *)
0x1400c278f  mov     edi, eax
0x1400c2791  test    eax, eax
0x1400c2793  js      loc_1400C2C51
0x1400c2799  cmp     [r15], r12w
0x1400c279d  jbe     short loc_1400C27C7
0x1400c279f  mov     r9d, 75723257h; unsigned int
0x1400c27a5  mov     [rsp+2D0h+var_2B0], r15; struct _UNICODE_STRING *
0x1400c27aa  lea     r8, [rbp+1D0h+var_1C0]; struct _UNICODE_STRING *
0x1400c27ae  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c27b1  lea     rdx, [rbp+1D0h+var_140]; struct _LOCATOR_OPERATION *
0x1400c27b8  call    ?VhdmpiPrepareNewLocator@@YAJPEAU_VHD1_BACKING_STORE@@QEAU_LOCATOR_OPERATION@@QEAU_UNICODE_STRING@@KPEAU3@@Z; VhdmpiPrepareNewLocator(_VHD1_BACKING_STORE *,_LOCATOR_OPERATION * const,_UNICODE_STRING * const,ulong,_UNICODE_STRING *)
0x1400c27bd  mov     edi, eax
0x1400c27bf  test    eax, eax
0x1400c27c1  js      loc_1400C2C51
0x1400c27c7  mov     edx, 10000h
0x1400c27cc  mov     r8d, 7A444856h
0x1400c27d2  mov     rcx, rsi
0x1400c27d5  call    cs:__imp_ExAllocatePool2
0x1400c27dc  nop     dword ptr [rax+rax+00h]
0x1400c27e1  mov     [rsp+2D0h+var_290], rax
0x1400c27e6  mov     r13, rax
0x1400c27e9  test    rax, rax
0x1400c27ec  jnz     short loc_1400C27F8
0x1400c27ee  mov     edi, 0C000009Ah
0x1400c27f3  jmp     loc_1400C2C51
0x1400c27f8  lea     rax, aOnecoreVmDvSto_13; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400c27ff  mov     dword ptr [rsp+2D0h+var_2A8], 176h
0x1400c2807  mov     r9b, 2
0x1400c280a  mov     [rsp+2D0h+var_2B0], rax
0x1400c280f  mov     r8b, 1
0x1400c2812  lea     rdx, [rsp+2D0h+var_288]
0x1400c2817  mov     rcx, rbx
0x1400c281a  call    VhdmpiLockUnlockVhdFile
0x1400c281f  movups  xmm0, xmmword ptr [rbx+0BC8h]
0x1400c2826  mov     r15d, r12d
0x1400c2829  movups  xmm1, xmmword ptr [rbx+0BD8h]
0x1400c2830  movups  [rsp+2D0h+var_280], xmm0
0x1400c2835  movups  xmm0, xmmword ptr [rbx+0BE8h]
0x1400c283c  movups  [rsp+2D0h+var_270], xmm1
0x1400c2841  movups  xmm1, xmmword ptr [rbx+0BF8h]
0x1400c2848  movups  [rsp+2D0h+var_260], xmm0
0x1400c284d  movups  xmm0, xmmword ptr [rbx+0C08h]
0x1400c2854  movups  [rbp+1D0h+var_250], xmm1
0x1400c2858  movups  xmm1, xmmword ptr [rbx+0C18h]
0x1400c285f  movups  [rbp+1D0h+var_240], xmm0
0x1400c2863  movups  xmm0, xmmword ptr [rbx+0C28h]
0x1400c286a  movups  [rbp+1D0h+var_230], xmm1
0x1400c286e  movups  xmm1, xmmword ptr [rbx+0C38h]
0x1400c2875  movups  [rbp+1D0h+var_220], xmm0
0x1400c2879  movups  xmm0, xmmword ptr [rbx+0C48h]
0x1400c2880  movups  [rbp+1D0h+var_210], xmm1
0x1400c2884  movups  xmm1, xmmword ptr [rbx+0C58h]
0x1400c288b  movups  [rbp+1D0h+var_200], xmm0
0x1400c288f  movups  xmm0, xmmword ptr [rbx+0C68h]
0x1400c2896  movups  [rbp+1D0h+var_1F0], xmm1
0x1400c289a  movups  xmm1, xmmword ptr [rbx+0C78h]
0x1400c28a1  movups  [rbp+1D0h+var_1E0], xmm0
0x1400c28a5  movups  [rbp+1D0h+var_1D0], xmm1
0x1400c28a9  mov     ecx, r15d
0x1400c28ac  shl     rcx, 5
0x1400c28b0  mov     eax, r15d
0x1400c28b3  mov     r13, [rbp+rcx+1D0h+var_140]
0x1400c28bb  lea     rdx, [rax+rax*2]
0x1400c28bf  test    r13, r13
0x1400c28c2  jnz     short loc_1400C28D8
0x1400c28c4  mov     r13, [rsp+2D0h+var_290]
0x1400c28c9  mov     dword ptr [rsp+rdx*8+2D0h+var_280], r12d
0x1400c28ce  mov     dword ptr [rsp+rdx*8+2D0h+var_280+8], r12d
0x1400c28d3  jmp     loc_1400C2973
0x1400c28d8  cmp     [rbp+rcx+1D0h+var_134], 0
0x1400c28e0  lea     rdi, [rsp+2D0h+var_280+4]
0x1400c28e5  mov     eax, [rbp+rcx+1D0h+var_138]
0x1400c28ec  lea     r12, [rsp+2D0h+var_270]
0x1400c28f1  mov     dword ptr [rsp+rdx*8+2D0h+var_280], eax
0x1400c28f5  lea     rdi, [rdi+rdx*8]
0x1400c28f9  movzx   eax, word ptr [r13+0]
0x1400c28fe  lea     r12, [r12+rdx*8]
0x1400c2902  mov     dword ptr [rsp+rdx*8+2D0h+var_280+8], eax
0x1400c2906  jz      short loc_1400C291D
0x1400c2908  mov     eax, [rbp+rcx+1D0h+var_128]
0x1400c290f  mov     [rdi], eax
0x1400c2911  mov     rax, [rbp+rcx+1D0h+var_130]
0x1400c2919  mov     [r12], rax
0x1400c291d  mov     rcx, [rsp+2D0h+var_290]; void *
0x1400c2922  xor     edx, edx; Val
0x1400c2924  mov     r8d, 10000h; Size
0x1400c292a  call    memset
0x1400c292f  movzx   r8d, word ptr [r13+0]; Size
0x1400c2934  mov     rdx, [r13+8]; Src
0x1400c2938  mov     r13, [rsp+2D0h+var_290]
0x1400c293d  mov     rcx, r13; void *
0x1400c2940  call    memmove
0x1400c2945  mov     eax, [rdi]
0x1400c2947  lea     rcx, [rbx+48h]; struct _VHD_FILE_WRAPPER *
0x1400c294b  mov     r12, [r12]
0x1400c294f  mov     r9, r13; void *
0x1400c2952  mov     qword ptr [rsp+2D0h+var_2A8], r12; unsigned __int64
0x1400c2957  mov     r8b, 4; unsigned __int8
0x1400c295a  mov     rdx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400c295d  mov     dword ptr [rsp+2D0h+var_2B0], eax; unsigned int
0x1400c2961  call    ?VhdmpiMetadataSynchronousIo@@YAJPEAU_VHD_FILE_WRAPPER@@PEAU_VHD_BACKING_STORE_HEADER@@EPEAXK_K@Z; VhdmpiMetadataSynchronousIo(_VHD_FILE_WRAPPER *,_VHD_BACKING_STORE_HEADER *,uchar,void *,ulong,unsigned __int64)
0x1400c2966  mov     edi, eax
0x1400c2968  test    eax, eax
0x1400c296a  js      loc_1400C2BFE
0x1400c2970  xor     r12d, r12d
0x1400c2973  inc     r15d
0x1400c2976  cmp     r15d, 8
0x1400c297a  jl      loc_1400C28A9
0x1400c2980  movaps  xmm0, [rsp+2D0h+var_280]
0x1400c2985  movaps  xmm1, [rsp+2D0h+var_270]
0x1400c298a  mov     rax, [rbp+1D0h+arg_20]
0x1400c2991  movups  xmmword ptr [rbx+0BC8h], xmm0
0x1400c2998  movaps  xmm0, [rsp+2D0h+var_260]
0x1400c299d  movups  xmmword ptr [rbx+0BD8h], xmm1
0x1400c29a4  movaps  xmm1, [rbp+1D0h+var_250]
0x1400c29a8  movups  xmmword ptr [rbx+0BE8h], xmm0
0x1400c29af  movaps  xmm0, [rbp+1D0h+var_240]
0x1400c29b3  movups  xmmword ptr [rbx+0BF8h], xmm1
0x1400c29ba  movaps  xmm1, [rbp+1D0h+var_230]
0x1400c29be  movups  xmmword ptr [rbx+0C08h], xmm0
0x1400c29c5  movaps  xmm0, [rbp+1D0h+var_220]
0x1400c29c9  movups  xmmword ptr [rbx+0C18h], xmm1
0x1400c29d0  movaps  xmm1, [rbp+1D0h+var_210]
0x1400c29d4  movups  xmmword ptr [rbx+0C28h], xmm0
0x1400c29db  movaps  xmm0, [rbp+1D0h+var_200]
0x1400c29df  movups  xmmword ptr [rbx+0C38h], xmm1
0x1400c29e6  movaps  xmm1, [rbp+1D0h+var_1F0]
0x1400c29ea  movups  xmmword ptr [rbx+0C48h], xmm0
0x1400c29f1  movaps  xmm0, [rbp+1D0h+var_1E0]
0x1400c29f5  movups  xmmword ptr [rbx+0C58h], xmm1
0x1400c29fc  movaps  xmm1, [rbp+1D0h+var_1D0]
0x1400c2a00  movups  xmmword ptr [rbx+0C68h], xmm0
0x1400c2a07  movups  xmmword ptr [rbx+0C78h], xmm1
0x1400c2a0e  movups  xmm0, xmmword ptr [rax]
0x1400c2a11  mov     rax, [rbp+1D0h+arg_30]
0x1400c2a18  movdqu  xmmword ptr [rbx+9B0h], xmm0
0x1400c2a20  test    rax, rax
0x1400c2a23  jz      short loc_1400C2A2D
0x1400c2a25  mov     eax, [rax]
0x1400c2a27  mov     [rbx+9C0h], eax
0x1400c2a2d  movzx   ecx, word ptr [r14]
0x1400c2a31  lea     rdx, [rbx+9C8h]
0x1400c2a38  test    cl, 1
0x1400c2a3b  jnz     loc_1400C2BA0
0x1400c2a41  movzx   eax, word ptr [r14+2]
0x1400c2a46  test    al, 1
0x1400c2a48  jnz     loc_1400C2BA0
0x1400c2a4e  cmp     cx, ax
0x1400c2a51  ja      loc_1400C2BA0
0x1400c2a57  mov     r8d, 0FFFEh
0x1400c2a5d  cmp     ax, r8w
0x1400c2a61  ja      loc_1400C2BA0
0x1400c2a67  mov     r8, [r14+8]
0x1400c2a6b  test    r8, r8
0x1400c2a6e  jnz     short loc_1400C2A82
0x1400c2a70  test    cx, cx
0x1400c2a73  jnz     loc_1400C2BA0
0x1400c2a79  test    ax, ax
0x1400c2a7c  jnz     loc_1400C2BA0
0x1400c2a82  shr     rcx, 1
0x1400c2a85  test    rcx, rcx
0x1400c2a88  jz      short loc_1400C2AA2
0x1400c2a8a  movzx   eax, word ptr [r8]
0x1400c2a8e  dec     rcx
0x1400c2a91  mov     [rdx], ax
0x1400c2a94  add     r8, 2
0x1400c2a98  add     rdx, 2
0x1400c2a9c  sub     rsi, 1
0x1400c2aa0  jnz     short loc_1400C2A85
0x1400c2aa2  test    rsi, rsi
0x1400c2aa5  lea     rcx, [rdx-2]
0x1400c2aa9  mov     rax, rsi
0x1400c2aac  cmovnz  rcx, rdx
0x1400c2ab0  neg     rax
0x1400c2ab3  mov     [rcx], r12w
0x1400c2ab7  sbb     ecx, ecx
0x1400c2ab9  not     ecx
0x1400c2abb  and     ecx, 80000005h
0x1400c2ac1  neg     rsi
0x1400c2ac4  sbb     edi, edi
0x1400c2ac6  and     edi, ecx
0x1400c2ac8  jl      loc_1400C2BA9
0x1400c2ace  movzx   eax, word ptr [r14]
0x1400c2ad2  mov     r8d, 200h
0x1400c2ad8  cmp     ax, r8w
0x1400c2adc  jnb     short loc_1400C2AF2
0x1400c2ade  lea     rcx, [rbx+9C8h]
0x1400c2ae5  sub     r8, rax; Size
0x1400c2ae8  add     rcx, rax; void *
0x1400c2aeb  xor     edx, edx; Val
0x1400c2aed  call    memset
0x1400c2af2  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c2af5  call    ?VhdmpiFlushDynamicHeader@@YAJPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiFlushDynamicHeader(_VHD1_BACKING_STORE *)
0x1400c2afa  mov     edi, eax
0x1400c2afc  test    eax, eax
0x1400c2afe  jns     short loc_1400C2B39
0x1400c2b00  mov     eax, cs:dword_140087708
0x1400c2b06  cmp     eax, 2
0x1400c2b09  jbe     loc_1400C2C51
0x1400c2b0f  mov     edx, 8
0x1400c2b14  lea     rcx, dword_140087708
0x1400c2b1b  call    _tlgKeywordOn
0x1400c2b20  test    al, al
0x1400c2b22  jz      loc_1400C2C51
0x1400c2b28  mov     edx, 201h
0x1400c2b2d  lea     rax, aVhdmpisetparen_3; "VhdmpiSetParentFilename: failed to flus"...
0x1400c2b34  jmp     loc_1400C2BDD
0x1400c2b39  mov     rsi, r12
0x1400c2b3c  lea     rax, [rsi+0D9h]
0x1400c2b43  add     rax, rax
0x1400c2b46  mov     rcx, [rbx+rax*8]; P
0x1400c2b4a  test    rcx, rcx
0x1400c2b4d  jz      short loc_1400C2B60
0x1400c2b4f  mov     edx, 50444856h; Tag
0x1400c2b54  call    cs:__imp_ExFreePoolWithTag
0x1400c2b5b  nop     dword ptr [rax+rax+00h]
0x1400c2b60  mov     rax, rsi
0x1400c2b63  lea     rcx, [rbp+1D0h+var_1C0]
0x1400c2b67  shl     rax, 4
0x1400c2b6b  xor     edx, edx; SourceString
0x1400c2b6d  add     rcx, rax; DestinationString
0x1400c2b70  movups  xmm0, xmmword ptr [rcx]
0x1400c2b73  movdqu  xmmword ptr [rax+rbx+0D88h], xmm0
0x1400c2b7c  call    cs:__imp_RtlInitUnicodeStringEx
0x1400c2b83  nop     dword ptr [rax+rax+00h]
0x1400c2b88  inc     rsi
0x1400c2b8b  cmp     rsi, 8
0x1400c2b8f  jnz     short loc_1400C2B3C
0x1400c2b91  mov     dword ptr [rbx+48Ch], 3
0x1400c2b9b  jmp     loc_1400C2C51
0x1400c2ba0  mov     [rdx], r12w
0x1400c2ba4  mov     edi, 0C000000Dh
0x1400c2ba9  mov     eax, cs:dword_140087708
0x1400c2baf  cmp     eax, 2
0x1400c2bb2  jbe     loc_1400C2C51
0x1400c2bb8  mov     edx, 8
0x1400c2bbd  lea     rcx, dword_140087708
0x1400c2bc4  call    _tlgKeywordOn
0x1400c2bc9  test    al, al
0x1400c2bcb  jz      loc_1400C2C51
0x1400c2bd1  mov     edx, 1E4h; int
0x1400c2bd6  lea     rax, aVhdmpisetparen; "VhdmpiSetParentFilename: failed to copy"...
0x1400c2bdd  mov     r9d, 8; int
0x1400c2be3  mov     dword ptr [rsp+2D0h+var_2A8], edi; char
0x1400c2be7  lea     rcx, aVhdmpivhd1writ; "VhdmpiVhd1WriteParentLinkageInfo"
0x1400c2bee  mov     [rsp+2D0h+var_2B0], rax; char *
0x1400c2bf3  lea     r8d, [r9-6]; int
0x1400c2bf7  call    TraceEvents
0x1400c2bfc  jmp     short loc_1400C2C51
0x1400c2bfe  mov     eax, cs:dword_140087708
0x1400c2c04  cmp     eax, 2
0x1400c2c07  jbe     short loc_1400C2C4E
0x1400c2c09  mov     edx, 8
0x1400c2c0e  lea     rcx, dword_140087708
0x1400c2c15  call    _tlgKeywordOn
0x1400c2c1a  test    al, al
0x1400c2c1c  jz      short loc_1400C2C4E
0x1400c2c1e  mov     r9d, 8; int
0x1400c2c24  mov     [rsp+2D0h+var_2A0], edi
0x1400c2c28  lea     rax, aVhdmpiwritepar; "VhdmpiWriteParentLocators: failed to wr"...
0x1400c2c2f  mov     qword ptr [rsp+2D0h+var_2A8], r12; char
0x1400c2c34  mov     edx, 1B3h; int
0x1400c2c39  mov     [rsp+2D0h+var_2B0], rax; char *
0x1400c2c3e  lea     rcx, aVhdmpivhd1writ; "VhdmpiVhd1WriteParentLinkageInfo"
  ... truncated ...
```

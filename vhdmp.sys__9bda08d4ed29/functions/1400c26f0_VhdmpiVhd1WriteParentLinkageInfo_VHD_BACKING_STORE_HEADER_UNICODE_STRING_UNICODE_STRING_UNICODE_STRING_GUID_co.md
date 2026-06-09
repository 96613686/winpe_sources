# VhdmpiVhd1WriteParentLinkageInfo(_VHD_BACKING_STORE_HEADER *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_GUID const *,_GUID const *,ulong *)

- ea: `0x1400c26f0`
- end: `0x1400c2cdb`
- name: `?VhdmpiVhd1WriteParentLinkageInfo@@YAJPEAU_VHD_BACKING_STORE_HEADER@@PEAU_UNICODE_STRING@@11PEBU_GUID@@2PEAK@Z`
- size: `1515`
- prototype: `__int64 __usercall@<rax>(struct _VHD_BACKING_STORE_HEADER *@<rcx>, struct _UNICODE_STRING *@<rdx>, struct _UNICODE_STRING *@<r8>, struct _UNICODE_STRING *@<r9>, const struct _GUID *, const struct _GUID *, unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140023980`
- `0x140036284`
- `0x14003f50c`
- `0x14005dbb0`
- `0x14005de00`
- `0x14005e100`
- `0x1400c1f88`
- `0x1400c26f0`
- `0x1400e25fc`
- `0x1400e7cf8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400c2b6c`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x1400c2b6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2b44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2ca2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2b44`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2c80`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c2ca2`
- `ntoskrnl!ExAllocatePool2` at `0x1400c27c5`
- `ntoskrnl!ExAllocatePool2` at `0x1400c27c5`

## string_xrefs

- `0x1400c2bd7`: `VhdmpiVhd1WriteParentLinkageInfo`
- `0x1400c2c2e`: `VhdmpiVhd1WriteParentLinkageInfo`
- `0x1400c2c18`: `VhdmpiWriteParentLocators: failed to write parent locator to offset 0x%I64x(0x%08x).`
- `0x1400c2bc6`: `VhdmpiSetParentFilename: failed to copy absolute locator to header (0x%08x)`

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
          if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
            goto LABEL_48;
          v52 = 513;
          v53 = "VhdmpiSetParentFilename: failed to flush dynamic header (0x%08x)";
LABEL_44:
          *(_DWORD *)v59 = v12;
          TraceEvents("VhdmpiVhd1WriteParentLinkageInfo", v52, 2u, 8u, v53, *(_QWORD *)v59);
          goto LABEL_48;
        }
      }
      if ( (unsigned int)dword_1400876D0 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
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
  if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 8) )
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
0x1400c26f0  mov     [rsp-8+arg_18], rbx
0x1400c26f5  push    rbp
0x1400c26f6  push    rsi
0x1400c26f7  push    rdi
0x1400c26f8  push    r12
0x1400c26fa  push    r13
0x1400c26fc  push    r14
0x1400c26fe  push    r15
0x1400c2700  lea     rbp, [rsp-1A0h]
0x1400c2708  sub     rsp, 2A0h
0x1400c270f  mov     rax, cs:__security_cookie
0x1400c2716  xor     rax, rsp
0x1400c2719  mov     [rbp+1D0h+var_40], rax
0x1400c2720  mov     r15, r8
0x1400c2723  mov     r14, rdx
0x1400c2726  mov     rbx, rcx
0x1400c2729  xor     r12d, r12d
0x1400c272c  xor     edx, edx; Val
0x1400c272e  mov     [rsp+2D0h+var_288], r12
0x1400c2733  mov     r8d, 80h; Size
0x1400c2739  lea     rcx, [rbp+1D0h+var_1C0]; void *
0x1400c273d  mov     r13d, r12d
0x1400c2740  call    memset
0x1400c2745  mov     esi, 100h
0x1400c274a  lea     rcx, [rbp+1D0h+var_140]; void *
0x1400c2751  mov     r8d, esi; Size
0x1400c2754  xor     edx, edx; Val
0x1400c2756  call    memset
0x1400c275b  cmp     [r14], r12w
0x1400c275f  jbe     short loc_1400C2789
0x1400c2761  mov     r9d, 756B3257h; unsigned int
0x1400c2767  mov     [rsp+2D0h+var_2B0], r14; struct _UNICODE_STRING *
0x1400c276c  lea     r8, [rbp+1D0h+var_1C0]; struct _UNICODE_STRING *
0x1400c2770  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c2773  lea     rdx, [rbp+1D0h+var_140]; struct _LOCATOR_OPERATION *
0x1400c277a  call    ?VhdmpiPrepareNewLocator@@YAJPEAU_VHD1_BACKING_STORE@@QEAU_LOCATOR_OPERATION@@QEAU_UNICODE_STRING@@KPEAU3@@Z; VhdmpiPrepareNewLocator(_VHD1_BACKING_STORE *,_LOCATOR_OPERATION * const,_UNICODE_STRING * const,ulong,_UNICODE_STRING *)
0x1400c277f  mov     edi, eax
0x1400c2781  test    eax, eax
0x1400c2783  js      loc_1400C2C41
0x1400c2789  cmp     [r15], r12w
0x1400c278d  jbe     short loc_1400C27B7
0x1400c278f  mov     r9d, 75723257h; unsigned int
0x1400c2795  mov     [rsp+2D0h+var_2B0], r15; struct _UNICODE_STRING *
0x1400c279a  lea     r8, [rbp+1D0h+var_1C0]; struct _UNICODE_STRING *
0x1400c279e  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c27a1  lea     rdx, [rbp+1D0h+var_140]; struct _LOCATOR_OPERATION *
0x1400c27a8  call    ?VhdmpiPrepareNewLocator@@YAJPEAU_VHD1_BACKING_STORE@@QEAU_LOCATOR_OPERATION@@QEAU_UNICODE_STRING@@KPEAU3@@Z; VhdmpiPrepareNewLocator(_VHD1_BACKING_STORE *,_LOCATOR_OPERATION * const,_UNICODE_STRING * const,ulong,_UNICODE_STRING *)
0x1400c27ad  mov     edi, eax
0x1400c27af  test    eax, eax
0x1400c27b1  js      loc_1400C2C41
0x1400c27b7  mov     edx, 10000h
0x1400c27bc  mov     r8d, 7A444856h
0x1400c27c2  mov     rcx, rsi
0x1400c27c5  call    cs:__imp_ExAllocatePool2
0x1400c27cc  nop     dword ptr [rax+rax+00h]
0x1400c27d1  mov     [rsp+2D0h+var_290], rax
0x1400c27d6  mov     r13, rax
0x1400c27d9  test    rax, rax
0x1400c27dc  jnz     short loc_1400C27E8
0x1400c27de  mov     edi, 0C000009Ah
0x1400c27e3  jmp     loc_1400C2C41
0x1400c27e8  lea     rax, aOnecoreVmDvSto_13; "onecore\\vm\\dv\\storage\\vhd\\vhdmp\\v"...
0x1400c27ef  mov     dword ptr [rsp+2D0h+var_2A8], 176h
0x1400c27f7  mov     r9b, 2
0x1400c27fa  mov     [rsp+2D0h+var_2B0], rax
0x1400c27ff  mov     r8b, 1
0x1400c2802  lea     rdx, [rsp+2D0h+var_288]
0x1400c2807  mov     rcx, rbx
0x1400c280a  call    VhdmpiLockUnlockVhdFile
0x1400c280f  movups  xmm0, xmmword ptr [rbx+0BC8h]
0x1400c2816  mov     r15d, r12d
0x1400c2819  movups  xmm1, xmmword ptr [rbx+0BD8h]
0x1400c2820  movups  [rsp+2D0h+var_280], xmm0
0x1400c2825  movups  xmm0, xmmword ptr [rbx+0BE8h]
0x1400c282c  movups  [rsp+2D0h+var_270], xmm1
0x1400c2831  movups  xmm1, xmmword ptr [rbx+0BF8h]
0x1400c2838  movups  [rsp+2D0h+var_260], xmm0
0x1400c283d  movups  xmm0, xmmword ptr [rbx+0C08h]
0x1400c2844  movups  [rbp+1D0h+var_250], xmm1
0x1400c2848  movups  xmm1, xmmword ptr [rbx+0C18h]
0x1400c284f  movups  [rbp+1D0h+var_240], xmm0
0x1400c2853  movups  xmm0, xmmword ptr [rbx+0C28h]
0x1400c285a  movups  [rbp+1D0h+var_230], xmm1
0x1400c285e  movups  xmm1, xmmword ptr [rbx+0C38h]
0x1400c2865  movups  [rbp+1D0h+var_220], xmm0
0x1400c2869  movups  xmm0, xmmword ptr [rbx+0C48h]
0x1400c2870  movups  [rbp+1D0h+var_210], xmm1
0x1400c2874  movups  xmm1, xmmword ptr [rbx+0C58h]
0x1400c287b  movups  [rbp+1D0h+var_200], xmm0
0x1400c287f  movups  xmm0, xmmword ptr [rbx+0C68h]
0x1400c2886  movups  [rbp+1D0h+var_1F0], xmm1
0x1400c288a  movups  xmm1, xmmword ptr [rbx+0C78h]
0x1400c2891  movups  [rbp+1D0h+var_1E0], xmm0
0x1400c2895  movups  [rbp+1D0h+var_1D0], xmm1
0x1400c2899  mov     ecx, r15d
0x1400c289c  shl     rcx, 5
0x1400c28a0  mov     eax, r15d
0x1400c28a3  mov     r13, [rbp+rcx+1D0h+var_140]
0x1400c28ab  lea     rdx, [rax+rax*2]
0x1400c28af  test    r13, r13
0x1400c28b2  jnz     short loc_1400C28C8
0x1400c28b4  mov     r13, [rsp+2D0h+var_290]
0x1400c28b9  mov     dword ptr [rsp+rdx*8+2D0h+var_280], r12d
0x1400c28be  mov     dword ptr [rsp+rdx*8+2D0h+var_280+8], r12d
0x1400c28c3  jmp     loc_1400C2963
0x1400c28c8  cmp     [rbp+rcx+1D0h+var_134], 0
0x1400c28d0  lea     rdi, [rsp+2D0h+var_280+4]
0x1400c28d5  mov     eax, [rbp+rcx+1D0h+var_138]
0x1400c28dc  lea     r12, [rsp+2D0h+var_270]
0x1400c28e1  mov     dword ptr [rsp+rdx*8+2D0h+var_280], eax
0x1400c28e5  lea     rdi, [rdi+rdx*8]
0x1400c28e9  movzx   eax, word ptr [r13+0]
0x1400c28ee  lea     r12, [r12+rdx*8]
0x1400c28f2  mov     dword ptr [rsp+rdx*8+2D0h+var_280+8], eax
0x1400c28f6  jz      short loc_1400C290D
0x1400c28f8  mov     eax, [rbp+rcx+1D0h+var_128]
0x1400c28ff  mov     [rdi], eax
0x1400c2901  mov     rax, [rbp+rcx+1D0h+var_130]
0x1400c2909  mov     [r12], rax
0x1400c290d  mov     rcx, [rsp+2D0h+var_290]; void *
0x1400c2912  xor     edx, edx; Val
0x1400c2914  mov     r8d, 10000h; Size
0x1400c291a  call    memset
0x1400c291f  movzx   r8d, word ptr [r13+0]; Size
0x1400c2924  mov     rdx, [r13+8]; Src
0x1400c2928  mov     r13, [rsp+2D0h+var_290]
0x1400c292d  mov     rcx, r13; void *
0x1400c2930  call    memmove
0x1400c2935  mov     eax, [rdi]
0x1400c2937  lea     rcx, [rbx+48h]; struct _VHD_FILE_WRAPPER *
0x1400c293b  mov     r12, [r12]
0x1400c293f  mov     r9, r13; void *
0x1400c2942  mov     qword ptr [rsp+2D0h+var_2A8], r12; unsigned __int64
0x1400c2947  mov     r8b, 4; unsigned __int8
0x1400c294a  mov     rdx, rbx; struct _VHD_BACKING_STORE_HEADER *
0x1400c294d  mov     dword ptr [rsp+2D0h+var_2B0], eax; unsigned int
0x1400c2951  call    ?VhdmpiMetadataSynchronousIo@@YAJPEAU_VHD_FILE_WRAPPER@@PEAU_VHD_BACKING_STORE_HEADER@@EPEAXK_K@Z; VhdmpiMetadataSynchronousIo(_VHD_FILE_WRAPPER *,_VHD_BACKING_STORE_HEADER *,uchar,void *,ulong,unsigned __int64)
0x1400c2956  mov     edi, eax
0x1400c2958  test    eax, eax
0x1400c295a  js      loc_1400C2BEE
0x1400c2960  xor     r12d, r12d
0x1400c2963  inc     r15d
0x1400c2966  cmp     r15d, 8
0x1400c296a  jl      loc_1400C2899
0x1400c2970  movaps  xmm0, [rsp+2D0h+var_280]
0x1400c2975  movaps  xmm1, [rsp+2D0h+var_270]
0x1400c297a  mov     rax, [rbp+1D0h+arg_20]
0x1400c2981  movups  xmmword ptr [rbx+0BC8h], xmm0
0x1400c2988  movaps  xmm0, [rsp+2D0h+var_260]
0x1400c298d  movups  xmmword ptr [rbx+0BD8h], xmm1
0x1400c2994  movaps  xmm1, [rbp+1D0h+var_250]
0x1400c2998  movups  xmmword ptr [rbx+0BE8h], xmm0
0x1400c299f  movaps  xmm0, [rbp+1D0h+var_240]
0x1400c29a3  movups  xmmword ptr [rbx+0BF8h], xmm1
0x1400c29aa  movaps  xmm1, [rbp+1D0h+var_230]
0x1400c29ae  movups  xmmword ptr [rbx+0C08h], xmm0
0x1400c29b5  movaps  xmm0, [rbp+1D0h+var_220]
0x1400c29b9  movups  xmmword ptr [rbx+0C18h], xmm1
0x1400c29c0  movaps  xmm1, [rbp+1D0h+var_210]
0x1400c29c4  movups  xmmword ptr [rbx+0C28h], xmm0
0x1400c29cb  movaps  xmm0, [rbp+1D0h+var_200]
0x1400c29cf  movups  xmmword ptr [rbx+0C38h], xmm1
0x1400c29d6  movaps  xmm1, [rbp+1D0h+var_1F0]
0x1400c29da  movups  xmmword ptr [rbx+0C48h], xmm0
0x1400c29e1  movaps  xmm0, [rbp+1D0h+var_1E0]
0x1400c29e5  movups  xmmword ptr [rbx+0C58h], xmm1
0x1400c29ec  movaps  xmm1, [rbp+1D0h+var_1D0]
0x1400c29f0  movups  xmmword ptr [rbx+0C68h], xmm0
0x1400c29f7  movups  xmmword ptr [rbx+0C78h], xmm1
0x1400c29fe  movups  xmm0, xmmword ptr [rax]
0x1400c2a01  mov     rax, [rbp+1D0h+arg_30]
0x1400c2a08  movdqu  xmmword ptr [rbx+9B0h], xmm0
0x1400c2a10  test    rax, rax
0x1400c2a13  jz      short loc_1400C2A1D
0x1400c2a15  mov     eax, [rax]
0x1400c2a17  mov     [rbx+9C0h], eax
0x1400c2a1d  movzx   ecx, word ptr [r14]
0x1400c2a21  lea     rdx, [rbx+9C8h]
0x1400c2a28  test    cl, 1
0x1400c2a2b  jnz     loc_1400C2B90
0x1400c2a31  movzx   eax, word ptr [r14+2]
0x1400c2a36  test    al, 1
0x1400c2a38  jnz     loc_1400C2B90
0x1400c2a3e  cmp     cx, ax
0x1400c2a41  ja      loc_1400C2B90
0x1400c2a47  mov     r8d, 0FFFEh
0x1400c2a4d  cmp     ax, r8w
0x1400c2a51  ja      loc_1400C2B90
0x1400c2a57  mov     r8, [r14+8]
0x1400c2a5b  test    r8, r8
0x1400c2a5e  jnz     short loc_1400C2A72
0x1400c2a60  test    cx, cx
0x1400c2a63  jnz     loc_1400C2B90
0x1400c2a69  test    ax, ax
0x1400c2a6c  jnz     loc_1400C2B90
0x1400c2a72  shr     rcx, 1
0x1400c2a75  test    rcx, rcx
0x1400c2a78  jz      short loc_1400C2A92
0x1400c2a7a  movzx   eax, word ptr [r8]
0x1400c2a7e  dec     rcx
0x1400c2a81  mov     [rdx], ax
0x1400c2a84  add     r8, 2
0x1400c2a88  add     rdx, 2
0x1400c2a8c  sub     rsi, 1
0x1400c2a90  jnz     short loc_1400C2A75
0x1400c2a92  test    rsi, rsi
0x1400c2a95  lea     rcx, [rdx-2]
0x1400c2a99  mov     rax, rsi
0x1400c2a9c  cmovnz  rcx, rdx
0x1400c2aa0  neg     rax
0x1400c2aa3  mov     [rcx], r12w
0x1400c2aa7  sbb     ecx, ecx
0x1400c2aa9  not     ecx
0x1400c2aab  and     ecx, 80000005h
0x1400c2ab1  neg     rsi
0x1400c2ab4  sbb     edi, edi
0x1400c2ab6  and     edi, ecx
0x1400c2ab8  jl      loc_1400C2B99
0x1400c2abe  movzx   eax, word ptr [r14]
0x1400c2ac2  mov     r8d, 200h
0x1400c2ac8  cmp     ax, r8w
0x1400c2acc  jnb     short loc_1400C2AE2
0x1400c2ace  lea     rcx, [rbx+9C8h]
0x1400c2ad5  sub     r8, rax; Size
0x1400c2ad8  add     rcx, rax; void *
0x1400c2adb  xor     edx, edx; Val
0x1400c2add  call    memset
0x1400c2ae2  mov     rcx, rbx; struct _VHD1_BACKING_STORE *
0x1400c2ae5  call    ?VhdmpiFlushDynamicHeader@@YAJPEAU_VHD1_BACKING_STORE@@@Z; VhdmpiFlushDynamicHeader(_VHD1_BACKING_STORE *)
0x1400c2aea  mov     edi, eax
0x1400c2aec  test    eax, eax
0x1400c2aee  jns     short loc_1400C2B29
0x1400c2af0  mov     eax, cs:dword_1400876D0
0x1400c2af6  cmp     eax, 2
0x1400c2af9  jbe     loc_1400C2C41
0x1400c2aff  mov     edx, 8
0x1400c2b04  lea     rcx, dword_1400876D0
0x1400c2b0b  call    _tlgKeywordOn
0x1400c2b10  test    al, al
0x1400c2b12  jz      loc_1400C2C41
0x1400c2b18  mov     edx, 201h
0x1400c2b1d  lea     rax, aVhdmpisetparen_3; "VhdmpiSetParentFilename: failed to flus"...
0x1400c2b24  jmp     loc_1400C2BCD
0x1400c2b29  mov     rsi, r12
0x1400c2b2c  lea     rax, [rsi+0D9h]
0x1400c2b33  add     rax, rax
0x1400c2b36  mov     rcx, [rbx+rax*8]; P
0x1400c2b3a  test    rcx, rcx
0x1400c2b3d  jz      short loc_1400C2B50
0x1400c2b3f  mov     edx, 50444856h; Tag
0x1400c2b44  call    cs:__imp_ExFreePoolWithTag
0x1400c2b4b  nop     dword ptr [rax+rax+00h]
0x1400c2b50  mov     rax, rsi
0x1400c2b53  lea     rcx, [rbp+1D0h+var_1C0]
0x1400c2b57  shl     rax, 4
0x1400c2b5b  xor     edx, edx; SourceString
0x1400c2b5d  add     rcx, rax; DestinationString
0x1400c2b60  movups  xmm0, xmmword ptr [rcx]
0x1400c2b63  movdqu  xmmword ptr [rax+rbx+0D88h], xmm0
0x1400c2b6c  call    cs:__imp_RtlInitUnicodeStringEx
0x1400c2b73  nop     dword ptr [rax+rax+00h]
0x1400c2b78  inc     rsi
0x1400c2b7b  cmp     rsi, 8
0x1400c2b7f  jnz     short loc_1400C2B2C
0x1400c2b81  mov     dword ptr [rbx+48Ch], 3
0x1400c2b8b  jmp     loc_1400C2C41
0x1400c2b90  mov     [rdx], r12w
0x1400c2b94  mov     edi, 0C000000Dh
0x1400c2b99  mov     eax, cs:dword_1400876D0
0x1400c2b9f  cmp     eax, 2
0x1400c2ba2  jbe     loc_1400C2C41
0x1400c2ba8  mov     edx, 8
0x1400c2bad  lea     rcx, dword_1400876D0
0x1400c2bb4  call    _tlgKeywordOn
0x1400c2bb9  test    al, al
0x1400c2bbb  jz      loc_1400C2C41
0x1400c2bc1  mov     edx, 1E4h; int
0x1400c2bc6  lea     rax, aVhdmpisetparen; "VhdmpiSetParentFilename: failed to copy"...
0x1400c2bcd  mov     r9d, 8; int
0x1400c2bd3  mov     dword ptr [rsp+2D0h+var_2A8], edi; char
0x1400c2bd7  lea     rcx, aVhdmpivhd1writ; "VhdmpiVhd1WriteParentLinkageInfo"
0x1400c2bde  mov     [rsp+2D0h+var_2B0], rax; char *
0x1400c2be3  lea     r8d, [r9-6]; int
0x1400c2be7  call    TraceEvents
0x1400c2bec  jmp     short loc_1400C2C41
0x1400c2bee  mov     eax, cs:dword_1400876D0
0x1400c2bf4  cmp     eax, 2
0x1400c2bf7  jbe     short loc_1400C2C3E
0x1400c2bf9  mov     edx, 8
0x1400c2bfe  lea     rcx, dword_1400876D0
0x1400c2c05  call    _tlgKeywordOn
0x1400c2c0a  test    al, al
0x1400c2c0c  jz      short loc_1400C2C3E
0x1400c2c0e  mov     r9d, 8; int
0x1400c2c14  mov     [rsp+2D0h+var_2A0], edi
0x1400c2c18  lea     rax, aVhdmpiwritepar; "VhdmpiWriteParentLocators: failed to wr"...
0x1400c2c1f  mov     qword ptr [rsp+2D0h+var_2A8], r12; char
0x1400c2c24  mov     edx, 1B3h; int
0x1400c2c29  mov     [rsp+2D0h+var_2B0], rax; char *
0x1400c2c2e  lea     rcx, aVhdmpivhd1writ; "VhdmpiVhd1WriteParentLinkageInfo"
  ... truncated ...
```

# UdfFindVolumeDescriptors

- ea: `0x1400483a8`
- end: `0x140048c1e`
- name: `UdfFindVolumeDescriptors`
- size: `2166`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *, __int64 *, __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14000c490`
- `0x14000ca10`
- `0x14000cad4`
- `0x14000cb04`
- `0x14000cb34`
- `0x14001093c`
- `0x1400130cc`
- `0x140013494`
- `0x14001c080`
- `0x14002d424`
- `0x140030034`
- `0x1400483a8`
- `0x140049020`
- `0x140049bb0`
- `0x140057ec8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140048b7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048b7e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048472`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140048472`

## pseudocode

```c
__int64 __fastcall UdfFindVolumeDescriptors(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 *a6)
{
  unsigned int v8; // r13d
  __int64 v9; // r9
  int v10; // ebx
  SIZE_T v11; // r14
  _DWORD *PoolWithTag; // r12
  unsigned int v13; // r14d
  unsigned __int64 v14; // r14
  unsigned int i; // ecx
  unsigned int v16; // r9d
  __int16 v17; // r8
  int v18; // edx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  __int64 v21; // r9
  __int64 *v22; // rdx
  unsigned __int16 v23; // dx
  int v24; // r8d
  int v25; // r14d
  __int64 *v26; // r12
  __int64 v27; // r14
  __int64 v28; // rbx
  __int16 v29; // ax
  unsigned int v30; // r12d
  unsigned int v31; // r14d
  unsigned int v32; // r12d
  int v34; // [rsp+30h] [rbp-78h]
  int v35; // [rsp+44h] [rbp-64h]
  int v36; // [rsp+4Ch] [rbp-5Ch]
  _DWORD *P; // [rsp+60h] [rbp-48h]
  unsigned int v39; // [rsp+B8h] [rbp+10h]
  unsigned __int16 v40; // [rsp+B8h] [rbp+10h]

  v8 = -*(_DWORD *)(a2 + 68) & (*(_DWORD *)(a2 + 68) + 511);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_qDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      71,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      a2,
      a3[1],
      *a3);
  }
  v9 = *a3;
  if ( (unsigned int)v9 < v8 || (unsigned int)v9 % v8 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        72,
        WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
        v9,
        v8);
    }
    return 3221225522LL;
  }
  v10 = 0;
  v11 = ((-*(_DWORD *)(a2 + 68) & (*(_DWORD *)(a2 + 68) + 511)) + 4095) & 0xFFFFF000;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, v11, 0x33666455u);
  P = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported && PoolWithTag )
    memset(PoolWithTag, 0, v11);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 73, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  v13 = 1;
  v35 = 1;
  while ( 2 )
  {
    if ( v13 > 2 )
      goto LABEL_105;
    v36 = 16;
    v14 = (unsigned __int64)a3[1] << *(_DWORD *)(a2 + 72);
    for ( i = *a3; ; i = v20 - v8 )
    {
      v39 = i;
      if ( !i )
        break;
      LOBYTE(v34) = 0;
      v10 = UdfReadWriteSectors(a1, v14, v8, 1, PoolWithTag, *(_QWORD *)(a2 + 24), v34);
      if ( v10 < 0 )
        break;
      v16 = 512;
      v17 = *(_WORD *)PoolWithTag;
      if ( *(_WORD *)PoolWithTag == 6 && *(_DWORD *)(a2 + 68) >= 0x400u )
        v16 = 640;
      if ( (unsigned __int16)v17 > 9u
        || !UdfVerifyDescriptor(a1, (__int64)PoolWithTag, v17, v16, v14 >> *(_DWORD *)(a2 + 72), 1) )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            74,
            WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
        }
        goto LABEL_32;
      }
      v18 = *(unsigned __int16 *)PoolWithTag;
      if ( (_WORD)v18 == 8 )
        break;
      if ( v18 != 3 )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            76,
            WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
        }
        if ( v35 == 1 )
        {
          if ( *(_WORD *)PoolWithTag == 1 )
          {
            v21 = a2 + 1404;
            v22 = a5;
LABEL_41:
            UdfStoreVolumeDescriptorIfPrevailing(a2, v22, PoolWithTag, v21, (unsigned int)(v14 >> *(_DWORD *)(a2 + 72)));
          }
          else if ( *(_WORD *)PoolWithTag == 6 )
          {
            v21 = a2 + 1408;
            v22 = a6;
            goto LABEL_41;
          }
        }
        else if ( *(_WORD *)PoolWithTag == 5 )
        {
          if ( (unsigned __int8)UdfEqualEntityId(PoolWithTag + 6, UdfNSR02Identifier) )
          {
            v23 = 8;
          }
          else if ( (unsigned __int8)UdfEqualEntityId(PoolWithTag + 6, UdfNSR03Identifier) )
          {
            v23 = 10;
          }
          else
          {
            v23 = 0;
          }
          v24 = *(unsigned __int16 *)(a2 + 2136);
          if ( v23 != (_WORD)v24 )
          {
            if ( (_WORD)v24 != 0xFFFF )
            {
              if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
              {
                WPP_SF_dd(
                  *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                  77,
                  WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
                  v23,
                  v24);
              }
              v10 = -1073741489;
              goto LABEL_105;
            }
            *(_WORD *)(a2 + 2136) = v23;
          }
          UdfAddToPcb(a2, *a4, (__int64)PoolWithTag);
        }
        v20 = v39;
        goto LABEL_53;
      }
      if ( !--v36 )
      {
        v10 = -1073741774;
        goto LABEL_105;
      }
      v14 = ((unsigned __int64)(unsigned int)PoolWithTag[6] << *(_DWORD *)(a2 + 72)) - v8;
      v19 = PoolWithTag[5];
      if ( v19 < v8 || v19 % v8 )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
        {
          WPP_SF_dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            75,
            WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
            *a3,
            v8);
        }
LABEL_32:
        v10 = -1073741774;
        goto LABEL_105;
      }
      v20 = v8 + v19;
LABEL_53:
      v14 += v8;
    }
    v25 = v35;
    if ( v35 != 1 )
      goto LABEL_101;
    v26 = a5;
    v27 = *a5;
    if ( !*a5 || (v28 = *a6) == 0 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 78, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
      }
      v10 = -1073741489;
      goto LABEL_106;
    }
    *(_WORD *)(a2 + 2138) = *(_WORD *)(v28 + 240);
    if ( (*(_BYTE *)(v28 + 242) & 3) != 0 )
      *(_DWORD *)(a2 + 48) |= 0x10u;
    v40 = *(_WORD *)(a2 + 2136) < 0xAu ? 336 : 608;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 79, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
    }
    if ( *(_WORD *)(v27 + 56) > 1u
      || *(_WORD *)(v27 + 58) > 1u && (v29 = *(_WORD *)(v27 + 8), v29 != 7429) && v29 != 21326 )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          80,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
          *(unsigned __int16 *)(v27 + 56),
          *(unsigned __int16 *)(v27 + 58));
      }
      v10 = -1073741489;
      goto LABEL_106;
    }
    v30 = *(_DWORD *)(v27 + 64);
    if ( *(_QWORD *)(v27 + 64) != 0x100000001LL
      || !(unsigned __int8)UdfEqualCharspec(v27 + 200)
      || !(unsigned __int8)UdfEqualCharspec(v27 + 264) )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          81,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
          v30,
          *(_DWORD *)(v27 + 68));
      }
      goto LABEL_88;
    }
    v31 = *(_DWORD *)(a2 + 68);
    v32 = *(_DWORD *)(v28 + 264) + 440;
    if ( v32 > v31
      || !(unsigned __int8)UdfEqualCharspec(v28 + 20)
      || *(_DWORD *)(v28 + 212) != v31
      || !(unsigned __int8)UdfDomainIdentifierContained(v28 + 216, &UdfDomainIdentifier, 256, v40)
      || *(_DWORD *)(v28 + 268) > 2u )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_DDDD(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          82,
          WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
          v32,
          *(_DWORD *)(v28 + 212),
          v31,
          *(_DWORD *)(v28 + 268));
      }
LABEL_88:
      v10 = -1073741489;
      goto LABEL_105;
    }
    v10 = UdfInitializePcb(a1, a2, (PVOID *)a4, v28);
    if ( v10 >= 0 )
    {
      PoolWithTag = P;
      v25 = 1;
LABEL_101:
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 84, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
      }
      v13 = v25 + 1;
      v35 = v13;
      continue;
    }
    break;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 83, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
LABEL_105:
  v26 = a5;
LABEL_106:
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 85, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
  }
  if ( !*v26 || !*a6 )
    v10 = -1073741489;
  if ( v10 < 0 )
  {
    UdfFreePool(v26);
    UdfFreePool(a6);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400483a8  mov     [rsp+arg_18], r9
0x1400483ad  mov     [rsp+arg_10], r8
0x1400483b2  mov     [rsp+arg_0], rcx
0x1400483b7  push    rbx
0x1400483b8  push    rsi
0x1400483b9  push    rdi
0x1400483ba  push    r12
0x1400483bc  push    r13
0x1400483be  push    r14
0x1400483c0  push    r15
0x1400483c2  sub     rsp, 70h
0x1400483c6  mov     rbx, r8
0x1400483c9  mov     r15, rdx
0x1400483cc  mov     eax, [rdx+44h]
0x1400483cf  lea     r13d, [rax+1FFh]
0x1400483d6  neg     eax
0x1400483d8  and     r13d, eax
0x1400483db  lea     r8, WPP_GLOBAL_Control
0x1400483e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483e9  mov     edi, 800h
0x1400483ee  lea     rsi, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x1400483f5  cmp     rcx, r8
0x1400483f8  jz      short loc_140048427
0x1400483fa  test    [rcx+2Ch], edi
0x1400483fd  jz      short loc_140048427
0x1400483ff  mov     edx, 47h ; 'G'
0x140048404  mov     eax, [rbx]
0x140048406  mov     dword ptr [rsp+0A8h+var_80], eax
0x14004840a  mov     eax, [rbx+4]
0x14004840d  mov     dword ptr [rsp+0A8h+var_88], eax
0x140048411  mov     r9, r15
0x140048414  mov     r8, rsi
0x140048417  mov     rcx, [rcx+18h]
0x14004841b  call    WPP_SF_qDD
0x140048420  lea     r8, WPP_GLOBAL_Control
0x140048427  mov     r9d, [rbx]
0x14004842a  cmp     r9d, r13d
0x14004842d  jb      loc_140048BE1
0x140048433  xor     edx, edx
0x140048435  mov     eax, r9d
0x140048438  div     r13d
0x14004843b  test    edx, edx
0x14004843d  jnz     loc_140048BE1
0x140048443  xor     ebx, ebx
0x140048445  mov     ecx, [r15+44h]
0x140048449  lea     r14d, [rcx+1FFh]
0x140048450  neg     ecx
0x140048452  and     r14d, ecx
0x140048455  add     r14d, 0FFFh
0x14004845c  mov     eax, 0FFFFF000h
0x140048461  and     r14, rax
0x140048464  mov     r8d, 33666455h; Tag
0x14004846a  mov     rdx, r14; NumberOfBytes
0x14004846d  mov     ecx, 610h; PoolType
0x140048472  call    cs:__imp_ExAllocatePoolWithTag
0x140048479  nop     dword ptr [rax+rax+00h]
0x14004847e  mov     r12, rax
0x140048481  mov     [rsp+0A8h+P], rax
0x140048486  mov     al, cs:ExPoolZeroingNativelySupported
0x14004848c  test    al, al
0x14004848e  jnz     short loc_1400484A2
0x140048490  test    r12, r12
0x140048493  jz      short loc_1400484A2
0x140048495  mov     r8, r14; Size
0x140048498  xor     edx, edx; Val
0x14004849a  mov     rcx, r12; void *
0x14004849d  call    memset
0x1400484a2  mov     [rsp+0A8h+var_40], r12
0x1400484a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400484ae  lea     rax, WPP_GLOBAL_Control
0x1400484b5  cmp     rcx, rax
0x1400484b8  jz      short loc_1400484D2
0x1400484ba  mov     eax, [rcx+2Ch]
0x1400484bd  test    edi, eax
0x1400484bf  jz      short loc_1400484D2
0x1400484c1  mov     edx, 49h ; 'I'
0x1400484c6  mov     r8, rsi
0x1400484c9  mov     rcx, [rcx+18h]
0x1400484cd  call    WPP_SF_
0x1400484d2  mov     r9d, 1
0x1400484d8  mov     r14d, r9d
0x1400484db  mov     [rsp+0A8h+var_64], r9d
0x1400484e0  cmp     r14d, 2
0x1400484e4  ja      loc_140048B63
0x1400484ea  mov     [rsp+0A8h+var_5C], 10h
0x1400484f2  mov     rax, [rsp+0A8h+arg_10]
0x1400484fa  mov     r14d, [rax+4]
0x1400484fe  mov     ecx, [r15+48h]
0x140048502  shl     r14, cl
0x140048505  mov     [rsp+0A8h+var_50], r14
0x14004850a  mov     ecx, [rax]
0x14004850c  mov     [rsp+0A8h+var_60], ecx
0x140048510  mov     [rsp+0A8h+arg_8], ecx
0x140048517  test    ecx, ecx
0x140048519  jz      loc_140048825
0x14004851f  mov     byte ptr [rsp+0A8h+var_78], 0
0x140048524  mov     rax, [r15+18h]
0x140048528  mov     [rsp+0A8h+var_80], rax
0x14004852d  mov     [rsp+0A8h+var_88], r12
0x140048532  mov     r8d, r13d
0x140048535  mov     rdx, r14
0x140048538  mov     rcx, [rsp+0A8h+arg_0]
0x140048540  call    UdfReadWriteSectors
0x140048545  mov     ebx, eax
0x140048547  mov     [rsp+0A8h+var_68], eax
0x14004854b  test    eax, eax
0x14004854d  js      loc_14004881F
0x140048553  mov     r9d, 200h
0x140048559  mov     [rsp+0A8h+var_58], r9d
0x14004855e  movzx   r8d, word ptr [r12]
0x140048563  mov     eax, 6
0x140048568  cmp     ax, r8w
0x14004856c  jnz     short loc_140048584
0x14004856e  mov     eax, 280h
0x140048573  cmp     dword ptr [r15+44h], 400h
0x14004857b  cmovnb  r9d, eax
0x14004857f  mov     [rsp+0A8h+var_58], r9d
0x140048584  cmp     r8w, 9
0x140048589  ja      loc_1400487E7
0x14004858f  mov     rax, r14
0x140048592  mov     ecx, [r15+48h]
0x140048596  shr     rax, cl
0x140048599  mov     dword ptr [rsp+0A8h+var_80], 1
0x1400485a1  mov     dword ptr [rsp+0A8h+var_88], eax
0x1400485a5  mov     rdx, r12
0x1400485a8  mov     rcx, [rsp+0A8h+arg_0]
0x1400485b0  call    UdfVerifyDescriptor
0x1400485b5  test    al, al
0x1400485b7  jz      loc_1400487E7
0x1400485bd  movzx   edx, word ptr [r12]
0x1400485c2  mov     eax, 8
0x1400485c7  cmp     dx, ax
0x1400485ca  jz      loc_14004881F
0x1400485d0  cmp     edx, 3
0x1400485d3  jnz     loc_14004867C
0x1400485d9  mov     r8d, [rsp+0A8h+var_5C]
0x1400485de  add     r8d, 0FFFFFFFFh
0x1400485e2  mov     [rsp+0A8h+var_5C], r8d
0x1400485e7  jnz     short loc_1400485F7
0x1400485e9  mov     ebx, 0C0000032h
0x1400485ee  mov     [rsp+0A8h+var_68], ebx
0x1400485f2  jmp     loc_140048B63
0x1400485f7  mov     r14d, [r12+18h]
0x1400485fc  mov     ecx, [r15+48h]
0x140048600  shl     r14, cl
0x140048603  mov     eax, r13d
0x140048606  sub     r14, rax
0x140048609  mov     [rsp+0A8h+var_50], r14
0x14004860e  mov     ecx, [r12+14h]
0x140048613  mov     [rsp+0A8h+var_60], ecx
0x140048617  cmp     ecx, r13d
0x14004861a  jb      short loc_140048633
0x14004861c  xor     edx, edx
0x14004861e  mov     eax, ecx
0x140048620  div     r13d
0x140048623  test    edx, edx
0x140048625  jnz     short loc_140048633
0x140048627  add     ecx, r13d
0x14004862a  mov     [rsp+0A8h+var_60], ecx
0x14004862e  jmp     loc_14004878E
0x140048633  mov     rcx, cs:WPP_GLOBAL_Control
0x14004863a  lea     r14, WPP_GLOBAL_Control
0x140048641  cmp     rcx, r14
0x140048644  jz      short loc_14004866E
0x140048646  mov     eax, [rcx+2Ch]
0x140048649  test    edi, eax
0x14004864b  jz      short loc_14004866E
0x14004864d  mov     edx, 4Bh ; 'K'
0x140048652  mov     dword ptr [rsp+0A8h+var_88], r13d
0x140048657  mov     r9, [rsp+0A8h+arg_10]
0x14004865f  mov     r9d, [r9]
0x140048662  mov     r8, rsi
0x140048665  mov     rcx, [rcx+18h]
0x140048669  call    WPP_SF_dd
0x14004866e  mov     ebx, 0C0000032h
0x140048673  mov     [rsp+0A8h+var_68], ebx
0x140048677  jmp     loc_140048B6A
0x14004867c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048683  lea     rax, WPP_GLOBAL_Control
0x14004868a  cmp     rcx, rax
0x14004868d  jz      short loc_1400486AA
0x14004868f  mov     eax, [rcx+2Ch]
0x140048692  test    edi, eax
0x140048694  jz      short loc_1400486AA
0x140048696  mov     r9d, edx
0x140048699  mov     edx, 4Ch ; 'L'
0x14004869e  mov     r8, rsi
0x1400486a1  mov     rcx, [rcx+18h]
0x1400486a5  call    WPP_SF_d
0x1400486aa  cmp     [rsp+0A8h+var_64], 1
0x1400486af  jnz     short loc_140048705
0x1400486b1  movzx   ecx, word ptr [r12]
0x1400486b6  sub     ecx, 1
0x1400486b9  jz      short loc_1400486D5
0x1400486bb  cmp     ecx, 5
0x1400486be  jnz     loc_140048787
0x1400486c4  lea     r9, [r15+580h]
0x1400486cb  mov     rdx, [rsp+0A8h+arg_28]
0x1400486d3  jmp     short loc_1400486E4
0x1400486d5  lea     r9, [r15+57Ch]
0x1400486dc  mov     rdx, [rsp+0A8h+arg_20]
0x1400486e4  mov     ecx, [r15+48h]
0x1400486e8  mov     rax, r14
0x1400486eb  shr     rax, cl
0x1400486ee  mov     eax, eax
0x1400486f0  mov     r8, r12
0x1400486f3  mov     [rsp+0A8h+var_88], rax
0x1400486f8  mov     rcx, r15
0x1400486fb  call    UdfStoreVolumeDescriptorIfPrevailing
0x140048700  jmp     loc_140048787
0x140048705  mov     eax, 5
0x14004870a  cmp     [r12], ax
0x14004870f  jz      short loc_140048713
0x140048711  jmp     short loc_140048787
0x140048713  lea     rcx, [r12+18h]
0x140048718  lea     rdx, UdfNSR02Identifier; "\a\a"
0x14004871f  call    UdfEqualEntityId
0x140048724  test    al, al
0x140048726  jz      short loc_14004872F
0x140048728  mov     edx, 8
0x14004872d  jmp     short loc_140048750
0x14004872f  lea     rdx, UdfNSR03Identifier; "\a\a"
0x140048736  lea     rcx, [r12+18h]
0x14004873b  call    UdfEqualEntityId
0x140048740  test    al, al
0x140048742  jz      short loc_14004874B
0x140048744  mov     edx, 0Ah
0x140048749  jmp     short loc_140048750
0x14004874b  xor     eax, eax
0x14004874d  movzx   edx, ax
0x140048750  movzx   r8d, word ptr [r15+858h]
0x140048758  cmp     dx, r8w
0x14004875c  jz      short loc_140048771
0x14004875e  mov     eax, 0FFFFh
0x140048763  cmp     r8w, ax
0x140048767  jnz     short loc_1400487A7
0x140048769  mov     [r15+858h], dx
0x140048771  mov     r8, r12
0x140048774  mov     rax, [rsp+0A8h+arg_18]
0x14004877c  mov     rdx, [rax]
0x14004877f  mov     rcx, r15
0x140048782  call    UdfAddToPcb
0x140048787  mov     ecx, [rsp+0A8h+arg_8]
0x14004878e  mov     eax, r13d
0x140048791  add     r14, rax
0x140048794  mov     [rsp+0A8h+var_50], r14
0x140048799  sub     ecx, r13d
0x14004879c  mov     r9d, 1
0x1400487a2  jmp     loc_14004850C
0x1400487a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487ae  lea     r14, WPP_GLOBAL_Control
0x1400487b5  cmp     rcx, r14
0x1400487b8  jz      short loc_1400487DD
0x1400487ba  mov     eax, [rcx+2Ch]
0x1400487bd  test    edi, eax
0x1400487bf  jz      short loc_1400487DD
0x1400487c1  mov     eax, r8d
0x1400487c4  movzx   r9d, dx
0x1400487c8  mov     edx, 4Dh ; 'M'
0x1400487cd  mov     dword ptr [rsp+0A8h+var_88], eax
0x1400487d1  mov     r8, rsi
0x1400487d4  mov     rcx, [rcx+18h]
0x1400487d8  call    WPP_SF_dd
0x1400487dd  mov     ebx, 0C000014Fh
0x1400487e2  jmp     loc_140048673
0x1400487e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487ee  lea     r14, WPP_GLOBAL_Control
0x1400487f5  cmp     rcx, r14
0x1400487f8  jz      loc_14004866E
0x1400487fe  mov     eax, [rcx+2Ch]
0x140048801  test    edi, eax
0x140048803  jz      loc_14004866E
0x140048809  mov     edx, 4Ah ; 'J'
0x14004880e  mov     r8, rsi
0x140048811  mov     rcx, [rcx+18h]
0x140048815  call    WPP_SF_
0x14004881a  jmp     loc_14004866E
0x14004881f  mov     r9d, 1
0x140048825  mov     r14d, [rsp+0A8h+var_64]
0x14004882a  cmp     r14d, r9d
0x14004882d  jnz     loc_140048B25
0x140048833  mov     r12, [rsp+0A8h+arg_20]
0x14004883b  mov     r14, [r12]
0x14004883f  test    r14, r14
0x140048842  jz      loc_140048AE5
0x140048848  mov     rax, [rsp+0A8h+arg_28]
0x140048850  mov     rbx, [rax]
0x140048853  test    rbx, rbx
0x140048856  jz      loc_140048AE5
0x14004885c  movzx   eax, word ptr [rbx+0F0h]
0x140048863  mov     [r15+85Ah], ax
0x14004886b  test    byte ptr [rbx+0F2h], 3
0x140048872  jz      short loc_140048879
0x140048874  or      dword ptr [r15+30h], 10h
0x140048879  mov     eax, 0Ah
0x14004887e  cmp     [r15+858h], ax
0x140048886  sbb     ax, ax
0x140048889  and     ax, 0FEF0h
0x14004888d  add     ax, 260h
0x140048891  mov     word ptr [rsp+0A8h+arg_8], ax
  ... truncated ...
```

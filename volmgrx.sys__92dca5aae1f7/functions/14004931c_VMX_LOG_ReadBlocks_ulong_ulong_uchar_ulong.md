# VMX_LOG::ReadBlocks(ulong,ulong,uchar * *,ulong *)

- ea: `0x14004931c`
- end: `0x1400496fe`
- name: `?ReadBlocks@VMX_LOG@@QEAAJKKPEAPEAEPEAK@Z`
- size: `994`
- prototype: `__int64 __fastcall(VMX_LOG *this, unsigned int, __int64, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140056b38`

## callees

- `0x1400099d8`
- `0x14001a0a0`
- `0x14001b960`
- `0x14001be80`
- `0x140049090`
- `0x14004931c`
- `0x140049704`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400493b8`
- `ntoskrnl!ExAllocatePool2` at `0x14004941b`
- `ntoskrnl!ExAllocatePool2` at `0x1400493b8`
- `ntoskrnl!ExAllocatePool2` at `0x14004941b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049434`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049527`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004953f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400495ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400495c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049660`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004967b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400496bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049434`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049527`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004953f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400495ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400495c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049660`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004967b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400496bb`

## pseudocode

```c
__int64 __fastcall VMX_LOG::ReadBlocks(
        VMX_LOG *this,
        unsigned int a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned int *a5)
{
  unsigned int v7; // edi
  unsigned int v8; // ecx
  unsigned int v9; // ebx
  unsigned int v10; // ecx
  PVOID v11; // r12
  VMX_NOTIFICATION_QUEUE *v12; // rcx
  __int64 v13; // rdx
  unsigned __int8 *Pool2; // rsi
  VMX_LOG_COPY *v15; // rcx
  VMX_LOG_COPY *v16; // rax
  int v17; // eax
  VMX_LOG *v18; // rcx
  int v20; // r13d
  VMX_NOTIFICATION_QUEUE *v21; // rcx
  __int64 v22; // rdx
  unsigned int v23; // ecx
  VMX_LOG_COPY **v24; // rax
  unsigned int v25; // [rsp+30h] [rbp-41h] BYREF
  PVOID P; // [rsp+38h] [rbp-39h] BYREF
  VMX_LOG_COPY **v27; // [rsp+40h] [rbp-31h]
  unsigned __int8 **v28; // [rsp+48h] [rbp-29h]
  VMX_LOG_COPY *v29; // [rsp+50h] [rbp-21h]
  VMX_LOG *v30; // [rsp+58h] [rbp-19h]
  unsigned int *v31; // [rsp+60h] [rbp-11h]
  __int128 v32; // [rsp+68h] [rbp-9h] BYREF
  __int64 v33; // [rsp+78h] [rbp+7h]

  v30 = this;
  v31 = a5;
  v33 = 0;
  *a5 = 0;
  v7 = a2;
  v8 = *((_DWORD *)this + 10);
  v28 = a4;
  v9 = 64;
  v25 = 0;
  v32 = 0;
  if ( a2 + 64 > v8 )
    v9 = v8 - a2;
  if ( a2 )
  {
    v10 = *((_DWORD *)this + 11);
    if ( v9 + a2 > v10 )
      v9 = v10 - a2;
  }
  if ( !v9 )
    return 0;
  P = (PVOID)ExAllocatePool2(258, v9 << 9, 1967287638);
  v11 = P;
  if ( !P )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
      || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
    {
      return 3221225626LL;
    }
    v13 = 23;
    goto LABEL_34;
  }
  Pool2 = *a4;
  if ( !*a4 )
  {
    Pool2 = (unsigned __int8 *)ExAllocatePool2(258, v9 << 9, 1967287638);
    if ( !Pool2 )
    {
      ExFreePoolWithTag(P, 0);
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
        || *((_BYTE *)WPP_GLOBAL_Control + 41) < 2u )
      {
        return 3221225626LL;
      }
      v13 = 24;
LABEL_34:
      WPP_SF_d(*((_QWORD *)v12 + 3), v13, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, 3221225626LL);
      return 3221225626LL;
    }
  }
  memset(Pool2, 0, v9 << 9);
  v15 = (VMX_LOG *)((char *)this + 16);
  v16 = (VMX_LOG_COPY *)*((_QWORD *)this + 2);
  v29 = (VMX_LOG *)((char *)this + 16);
  while ( 1 )
  {
    v27 = (VMX_LOG_COPY **)v16;
    if ( v16 == v15 )
    {
      if ( !v7 )
      {
        P = Pool2;
        v20 = VMX_LOG_BLOCK_HEADER::Unformat((VMX_LOG_BLOCK_HEADER *)&v32, (unsigned __int8 **)&P);
        if ( v20 < 0 )
        {
          ExFreePoolWithTag(v11, 0);
          if ( !*v28 )
            ExFreePoolWithTag(Pool2, 0);
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
            && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
            && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
          {
            v22 = 27;
LABEL_44:
            WPP_SF_d(*((_QWORD *)v21 + 3), v22, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids, (unsigned int)v20);
          }
          return (unsigned int)v20;
        }
        if ( v9 > HIDWORD(v32) )
          v9 = HIDWORD(v32);
        *((_DWORD *)v30 + 11) = HIDWORD(v32);
      }
      v23 = v9 + v7;
      v24 = (VMX_LOG_COPY **)Pool2;
      v25 = v9 + v7;
      while ( 1 )
      {
        v27 = v24;
        if ( v7 >= v23 )
        {
          ExFreePoolWithTag(v11, 0);
          *v28 = Pool2;
          *v31 = v9;
          return 0;
        }
        P = v24;
        v20 = VMX_LOG_BLOCK_HEADER::Unformat((VMX_LOG_BLOCK_HEADER *)&v32, (unsigned __int8 **)&P);
        if ( v20 < 0 )
          break;
        ++v7;
        v23 = v25;
        v24 = v27 + 64;
      }
      ExFreePoolWithTag(v11, 0);
      if ( !*v28 )
        ExFreePoolWithTag(Pool2, 0);
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v22 = 28;
        goto LABEL_44;
      }
      return (unsigned int)v20;
    }
    v17 = VMX_LOG_COPY::ReadBlocks(v16, v7, v9, (char **)&P, &v25);
    v11 = P;
    if ( v17 >= 0 )
    {
      VMX_LOG::MergeBlocks(v18, Pool2, (unsigned __int8 *)P, v7, v25);
      goto LABEL_27;
    }
    if ( v17 == -1073741670 )
      break;
    if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
      && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        26,
        WPP_4b219bab5c283f1089a222952cd3541f_Traceguids,
        (unsigned int)v17);
    }
LABEL_27:
    v15 = v29;
    v16 = *v27;
  }
  ExFreePoolWithTag(P, 0);
  if ( !*a4 )
    ExFreePoolWithTag(Pool2, 0);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xBu)
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    v13 = 25;
    goto LABEL_34;
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x14004931c  mov     [rsp-8+arg_10], rbx
0x140049321  push    rbp
0x140049322  push    rsi
0x140049323  push    rdi
0x140049324  push    r12
0x140049326  push    r13
0x140049328  push    r14
0x14004932a  push    r15
0x14004932c  lea     rbp, [rsp-1Fh]
0x140049331  sub     rsp, 90h
0x140049338  mov     rax, cs:__security_cookie
0x14004933f  xor     rax, rsp
0x140049342  mov     [rbp+4Fh+var_40], rax
0x140049346  mov     rax, [rbp+4Fh+arg_20]
0x14004934a  mov     r15, rcx
0x14004934d  mov     [rbp+4Fh+var_68], rcx
0x140049351  xorps   xmm0, xmm0
0x140049354  xor     ecx, ecx
0x140049356  mov     [rbp+4Fh+var_60], rax
0x14004935a  mov     [rbp+4Fh+var_48], rcx
0x14004935e  mov     r13, r9
0x140049361  mov     [rax], ecx
0x140049363  mov     edi, edx
0x140049365  mov     ecx, [r15+28h]
0x140049369  lea     eax, [rdx+40h]
0x14004936c  mov     [rbp+4Fh+var_78], r9
0x140049370  mov     ebx, 40h ; '@'
0x140049375  mov     [rbp+4Fh+var_90], 0
0x14004937c  movups  [rbp+4Fh+var_58], xmm0
0x140049380  cmp     eax, ecx
0x140049382  jbe     short loc_140049388
0x140049384  mov     ebx, ecx
0x140049386  sub     ebx, edx
0x140049388  test    edi, edi
0x14004938a  jz      short loc_14004939B
0x14004938c  mov     ecx, [r15+2Ch]
0x140049390  lea     eax, [rbx+rdx]
0x140049393  cmp     eax, ecx
0x140049395  jbe     short loc_14004939B
0x140049397  mov     ebx, ecx
0x140049399  sub     ebx, edi
0x14004939b  test    ebx, ebx
0x14004939d  jz      loc_1400496D4
0x1400493a3  mov     eax, ebx
0x1400493a5  mov     r8d, 75426D56h
0x1400493ab  shl     eax, 9
0x1400493ae  mov     ecx, 102h
0x1400493b3  mov     edx, eax
0x1400493b5  mov     r14d, eax
0x1400493b8  call    cs:__imp_ExAllocatePool2
0x1400493bf  nop     dword ptr [rax+rax+00h]
0x1400493c4  mov     [rbp+4Fh+P], rax
0x1400493c8  mov     r12, rax
0x1400493cb  test    rax, rax
0x1400493ce  jnz     short loc_140049404
0x1400493d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400493d7  lea     r15, WPP_GLOBAL_Control
0x1400493de  cmp     rcx, r15
0x1400493e1  jz      loc_14004957F
0x1400493e7  bt      dword ptr [rcx+2Ch], 0Bh
0x1400493ec  jnb     loc_14004957F
0x1400493f2  cmp     byte ptr [rcx+29h], 2
0x1400493f6  jb      loc_14004957F
0x1400493fc  lea     edx, [rax+17h]
0x1400493ff  jmp     loc_140049569
0x140049404  mov     rsi, [r13+0]
0x140049408  test    rsi, rsi
0x14004940b  jnz     short loc_140049474
0x14004940d  mov     r8d, 75426D56h
0x140049413  mov     rdx, r14
0x140049416  mov     ecx, 102h
0x14004941b  call    cs:__imp_ExAllocatePool2
0x140049422  nop     dword ptr [rax+rax+00h]
0x140049427  mov     rsi, rax
0x14004942a  test    rax, rax
0x14004942d  jnz     short loc_140049474
0x14004942f  xor     edx, edx; Tag
0x140049431  mov     rcx, r12; P
0x140049434  call    cs:__imp_ExFreePoolWithTag
0x14004943b  nop     dword ptr [rax+rax+00h]
0x140049440  mov     rcx, cs:WPP_GLOBAL_Control
0x140049447  lea     r15, WPP_GLOBAL_Control
0x14004944e  cmp     rcx, r15
0x140049451  jz      loc_14004957F
0x140049457  bt      dword ptr [rcx+2Ch], 0Bh
0x14004945c  jnb     loc_14004957F
0x140049462  cmp     byte ptr [rcx+29h], 2
0x140049466  jb      loc_14004957F
0x14004946c  lea     edx, [rsi+18h]
0x14004946f  jmp     loc_140049569
0x140049474  mov     r8, r14; Size
0x140049477  xor     edx, edx; Val
0x140049479  mov     rcx, rsi; void *
0x14004947c  call    memset
0x140049481  lea     rcx, [r15+10h]
0x140049485  mov     rax, [rcx]
0x140049488  lea     r15, WPP_GLOBAL_Control
0x14004948f  mov     [rbp+4Fh+var_70], rcx
0x140049493  mov     [rbp+4Fh+var_80], rax
0x140049497  cmp     rax, rcx
0x14004949a  jz      loc_140049589
0x1400494a0  lea     rcx, [rbp+4Fh+var_90]
0x1400494a4  mov     r8d, ebx; unsigned int
0x1400494a7  mov     [rsp+0C0h+var_A0], rcx; unsigned int *
0x1400494ac  lea     r9, [rbp+4Fh+P]; unsigned __int8 **
0x1400494b0  mov     rcx, rax; this
0x1400494b3  mov     edx, edi; unsigned int
0x1400494b5  call    ?ReadBlocks@VMX_LOG_COPY@@QEAAJKKPEAPEAEPEAK@Z; VMX_LOG_COPY::ReadBlocks(ulong,ulong,uchar * *,ulong *)
0x1400494ba  mov     r12, [rbp+4Fh+P]
0x1400494be  mov     r9d, eax
0x1400494c1  test    eax, eax
0x1400494c3  jns     short loc_1400494FC
0x1400494c5  cmp     eax, 0C000009Ah
0x1400494ca  jz      short loc_140049521
0x1400494cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400494d3  cmp     rcx, r15
0x1400494d6  jz      short loc_140049511
0x1400494d8  bt      dword ptr [rcx+2Ch], 0Bh
0x1400494dd  jnb     short loc_140049511
0x1400494df  cmp     byte ptr [rcx+29h], 3
0x1400494e3  jb      short loc_140049511
0x1400494e5  mov     rcx, [rcx+18h]
0x1400494e9  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x1400494f0  mov     edx, 1Ah
0x1400494f5  call    WPP_SF_d
0x1400494fa  jmp     short loc_140049511
0x1400494fc  mov     eax, [rbp+4Fh+var_90]
0x1400494ff  mov     r9d, edi; unsigned int
0x140049502  mov     r8, r12; unsigned __int8 *
0x140049505  mov     dword ptr [rsp+0C0h+var_A0], eax; unsigned int
0x140049509  mov     rdx, rsi; unsigned __int8 *
0x14004950c  call    ?MergeBlocks@VMX_LOG@@AEAAXPEAE0KK@Z; VMX_LOG::MergeBlocks(uchar *,uchar *,ulong,ulong)
0x140049511  mov     rax, [rbp+4Fh+var_80]
0x140049515  mov     rcx, [rbp+4Fh+var_70]
0x140049519  mov     rax, [rax]
0x14004951c  jmp     loc_140049493
0x140049521  mov     rcx, [rbp+4Fh+P]; P
0x140049525  xor     edx, edx; Tag
0x140049527  call    cs:__imp_ExFreePoolWithTag
0x14004952e  nop     dword ptr [rax+rax+00h]
0x140049533  cmp     qword ptr [r13+0], 0
0x140049538  jnz     short loc_14004954B
0x14004953a  xor     edx, edx; Tag
0x14004953c  mov     rcx, rsi; P
0x14004953f  call    cs:__imp_ExFreePoolWithTag
0x140049546  nop     dword ptr [rax+rax+00h]
0x14004954b  mov     rcx, cs:WPP_GLOBAL_Control
0x140049552  cmp     rcx, r15
0x140049555  jz      short loc_14004957F
0x140049557  bt      dword ptr [rcx+2Ch], 0Bh
0x14004955c  jnb     short loc_14004957F
0x14004955e  cmp     byte ptr [rcx+29h], 2
0x140049562  jb      short loc_14004957F
0x140049564  mov     edx, 19h
0x140049569  mov     rcx, [rcx+18h]
0x14004956d  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x140049574  mov     r9d, 0C000009Ah
0x14004957a  call    WPP_SF_d
0x14004957f  mov     eax, 0C000009Ah
0x140049584  jmp     loc_1400496D6
0x140049589  test    edi, edi
0x14004958b  jnz     loc_14004961D
0x140049591  lea     rdx, [rbp+4Fh+P]; unsigned __int8 **
0x140049595  mov     [rbp+4Fh+P], rsi
0x140049599  lea     rcx, [rbp+4Fh+var_58]; this
0x14004959d  call    ?Unformat@VMX_LOG_BLOCK_HEADER@@QEAAJPEAPEAEK@Z; VMX_LOG_BLOCK_HEADER::Unformat(uchar * *,ulong)
0x1400495a2  mov     r13d, eax
0x1400495a5  test    eax, eax
0x1400495a7  jns     short loc_14004960E
0x1400495a9  xor     edx, edx; Tag
0x1400495ab  mov     rcx, r12; P
0x1400495ae  call    cs:__imp_ExFreePoolWithTag
0x1400495b5  nop     dword ptr [rax+rax+00h]
0x1400495ba  mov     rax, [rbp+4Fh+var_78]
0x1400495be  cmp     qword ptr [rax], 0
0x1400495c2  jnz     short loc_1400495D5
0x1400495c4  xor     edx, edx; Tag
0x1400495c6  mov     rcx, rsi; P
0x1400495c9  call    cs:__imp_ExFreePoolWithTag
0x1400495d0  nop     dword ptr [rax+rax+00h]
0x1400495d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400495dc  cmp     rcx, r15
0x1400495df  jz      short loc_140049606
0x1400495e1  bt      dword ptr [rcx+2Ch], 0Bh
0x1400495e6  jnb     short loc_140049606
0x1400495e8  cmp     byte ptr [rcx+29h], 2
0x1400495ec  jb      short loc_140049606
0x1400495ee  mov     edx, 1Bh
0x1400495f3  mov     rcx, [rcx+18h]
0x1400495f7  lea     r8, WPP_4b219bab5c283f1089a222952cd3541f_Traceguids
0x1400495fe  mov     r9d, r13d
0x140049601  call    WPP_SF_d
0x140049606  mov     eax, r13d
0x140049609  jmp     loc_1400496D6
0x14004960e  mov     eax, dword ptr [rbp+4Fh+var_58+0Ch]
0x140049611  cmp     ebx, eax
0x140049613  mov     rcx, [rbp+4Fh+var_68]
0x140049617  cmova   ebx, eax
0x14004961a  mov     [rcx+2Ch], eax
0x14004961d  lea     ecx, [rbx+rdi]
0x140049620  mov     rax, rsi
0x140049623  mov     [rbp+4Fh+var_90], ecx
0x140049626  mov     [rbp+4Fh+var_80], rax
0x14004962a  cmp     edi, ecx
0x14004962c  jnb     loc_1400496B6
0x140049632  lea     rdx, [rbp+4Fh+P]; unsigned __int8 **
0x140049636  mov     [rbp+4Fh+P], rax
0x14004963a  lea     rcx, [rbp+4Fh+var_58]; this
0x14004963e  call    ?Unformat@VMX_LOG_BLOCK_HEADER@@QEAAJPEAPEAEK@Z; VMX_LOG_BLOCK_HEADER::Unformat(uchar * *,ulong)
0x140049643  mov     r13d, eax
0x140049646  test    eax, eax
0x140049648  js      short loc_14004965B
0x14004964a  mov     rax, [rbp+4Fh+var_80]
0x14004964e  inc     edi
0x140049650  mov     ecx, [rbp+4Fh+var_90]
0x140049653  add     rax, 200h
0x140049659  jmp     short loc_140049626
0x14004965b  xor     edx, edx; Tag
0x14004965d  mov     rcx, r12; P
0x140049660  call    cs:__imp_ExFreePoolWithTag
0x140049667  nop     dword ptr [rax+rax+00h]
0x14004966c  mov     rax, [rbp+4Fh+var_78]
0x140049670  cmp     qword ptr [rax], 0
0x140049674  jnz     short loc_140049687
0x140049676  xor     edx, edx; Tag
0x140049678  mov     rcx, rsi; P
0x14004967b  call    cs:__imp_ExFreePoolWithTag
0x140049682  nop     dword ptr [rax+rax+00h]
0x140049687  mov     rcx, cs:WPP_GLOBAL_Control
0x14004968e  cmp     rcx, r15
0x140049691  jz      loc_140049606
0x140049697  bt      dword ptr [rcx+2Ch], 0Bh
0x14004969c  jnb     loc_140049606
0x1400496a2  cmp     byte ptr [rcx+29h], 2
0x1400496a6  jb      loc_140049606
0x1400496ac  mov     edx, 1Ch
0x1400496b1  jmp     loc_1400495F3
0x1400496b6  xor     edx, edx; Tag
0x1400496b8  mov     rcx, r12; P
0x1400496bb  call    cs:__imp_ExFreePoolWithTag
0x1400496c2  nop     dword ptr [rax+rax+00h]
0x1400496c7  mov     rax, [rbp+4Fh+var_78]
0x1400496cb  mov     [rax], rsi
0x1400496ce  mov     rax, [rbp+4Fh+var_60]
0x1400496d2  mov     [rax], ebx
0x1400496d4  xor     eax, eax
0x1400496d6  mov     rcx, [rbp+4Fh+var_40]
0x1400496da  xor     rcx, rsp; StackCookie
0x1400496dd  call    __security_check_cookie
0x1400496e2  mov     rbx, [rsp+0C0h+arg_10]
0x1400496ea  add     rsp, 90h
0x1400496f1  pop     r15
0x1400496f3  pop     r14
0x1400496f5  pop     r13
0x1400496f7  pop     r12
0x1400496f9  pop     rdi
0x1400496fa  pop     rsi
0x1400496fb  pop     rbp
0x1400496fc  retn
```

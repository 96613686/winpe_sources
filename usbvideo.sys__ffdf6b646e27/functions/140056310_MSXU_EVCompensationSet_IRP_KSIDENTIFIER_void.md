# MSXU_EVCompensationSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x140056310`
- end: `0x140056777`
- name: `?MSXU_EVCompensationSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1127`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x1400053fc`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b364`
- `0x14003b85c`
- `0x140040a30`
- `0x140056310`
- `0x14005bd18`

## pseudocode

```c
__int64 __fastcall MSXU_EVCompensationSet(struct _IRP *a1, struct KSIDENTIFIER *a2, _DWORD *a3)
{
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  int v8; // r8d
  __int64 v9; // r14
  __int64 v10; // rsi
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r10
  __int64 v16; // r9
  int v17; // ecx
  int v18; // r8d
  char v19; // dl
  unsigned __int8 v20; // cl
  unsigned __int8 v21; // dl
  unsigned __int8 v22; // cl
  __int64 v23; // r9
  unsigned __int8 v24; // dl
  unsigned __int8 v25; // r9
  int v26; // eax
  int v28; // [rsp+20h] [rbp-60h]
  size_t Size; // [rsp+30h] [rbp-50h]
  struct _TOPOLOGY_NODE_INFO *v30; // [rsp+38h] [rbp-48h]
  unsigned __int8 v31; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int8 v32[7]; // [rsp+51h] [rbp-2Fh] BYREF
  struct _KSFILTER *v33; // [rsp+58h] [rbp-28h] BYREF
  struct _TOPOLOGY_NODE_INFO *v34; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v35[11]; // [rsp+68h] [rbp-18h] BYREF

  v32[0] = 0;
  v31 = 0;
  v34 = 0;
  *(_QWORD *)v35 = 0;
  v33 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 145, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, a1);
  v5 = MSXUGetInfo(a1, &v33, v32, &v31, &v34, (struct _HW_DEVICE_EXTENSION **)v35);
  if ( (v5 & 0x80000000) == 0 )
  {
    v5 = ValidateExtendedPropertyDataBufferLength(a1, a3, 56);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_73;
      v7 = (unsigned int)(v8 + 91);
      goto LABEL_72;
    }
    v9 = *(_QWORD *)v35;
    v5 = -1073741811;
    v10 = *(_QWORD *)(*(_QWORD *)v35 + 976LL);
    v11 = *(unsigned __int8 *)(v10 + 33);
    v12 = v11 & 1 | 2;
    if ( (v11 & 2) == 0 )
      v12 = *(_BYTE *)(v10 + 33) & 1;
    v13 = v12 | 4;
    if ( (v11 & 4) == 0 )
      v13 = v12;
    v14 = v13 | 8;
    if ( (v11 & 8) == 0 )
      v14 = v13;
    v15 = v14 | 0x10;
    if ( (v11 & 0x10) == 0 )
      v15 = v14;
    if ( *a3 != 1 || a3[2] < 0x38u || a3[1] != -1 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_73;
      v7 = 153;
      goto LABEL_72;
    }
    v16 = *((_QWORD *)a3 + 2);
    if ( v16 == 1 )
    {
      v17 = 6;
    }
    else
    {
      switch ( *((_QWORD *)a3 + 2) )
      {
        case 2LL:
          v17 = 4;
          break;
        case 4LL:
          v17 = 3;
          break;
        case 8LL:
          v17 = 2;
          break;
        case 0x10LL:
          v17 = 1;
          break;
        default:
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return v5;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 148, v11, v16);
          goto LABEL_73;
      }
    }
    if ( (v16 & v15) == v16 )
    {
      v18 = a3[11];
      if ( v18 > v17 * *(_DWORD *)(v10 + 18) || v18 < *(_DWORD *)(v10 + 7) * v17 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return v5;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_DDDD(
            WPP_GLOBAL_Control->AttachedDevice,
            151,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            (unsigned int)v18,
            *(_DWORD *)(v10 + 7),
            *(_DWORD *)(v10 + 18),
            v17);
      }
      else
      {
        *(_WORD *)&v35[8] = 0;
        v35[10] = 0;
        v19 = v16 & 1;
        *(_QWORD *)v35 = (v16 & 1) != 0;
        if ( (v16 & 2) != 0 )
          v35[0] = v19 | 2;
        v20 = v19 | 2;
        if ( (v16 & 2) == 0 )
          v20 = v16 & 1;
        if ( (v16 & 4) != 0 )
          v35[0] = v20 | 4;
        v21 = v20 | 4;
        if ( (v16 & 4) == 0 )
          v21 = v20;
        if ( (v16 & 8) != 0 )
          v35[0] = v21 | 8;
        v22 = v21 | 8;
        if ( (v16 & 8) == 0 )
          v22 = v21;
        v23 = v16 & 0x10;
        if ( v23 )
          v35[0] = v22 | 0x10;
        *(_DWORD *)&v35[7] = v18;
        v24 = v22 | 0x10;
        if ( !v23 )
          v24 = v22;
        *(_DWORD *)&v35[7] = v18;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            149,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            (unsigned int)v18,
            v24);
        v25 = v32[0];
        *(_QWORD *)(v9 + 1112) = v33;
        v30 = v34;
        LODWORD(Size) = 11;
        LOBYTE(v28) = v31;
        *(_DWORD *)(v9 + 1288) = 1;
        v26 = SubmitControlRequest(0x21u, 1u, 0x300u, v25, v28, v35, Size, (__int64)v30, v9);
        v5 = v26;
        if ( v26 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              150,
              WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
              (unsigned int)v26);
          *(_QWORD *)(v9 + 1112) = 0;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 152);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v5;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 146;
LABEL_72:
      WPP_SF_(v6->AttachedDevice, v7, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    }
  }
LABEL_73:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 154, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x140056310  mov     [rsp-28h+arg_8], rbx
0x140056315  mov     [rsp-28h+arg_18], rsi
0x14005631a  push    rbp
0x14005631b  push    rdi
0x14005631c  push    r12
0x14005631e  push    r13
0x140056320  push    r14
0x140056322  mov     rbp, rsp
0x140056325  sub     rsp, 80h
0x14005632c  mov     rax, cs:__security_cookie
0x140056333  xor     rax, rsp
0x140056336  mov     [rbp+var_8], rax
0x14005633a  mov     rdi, r8
0x14005633d  mov     [rbp+var_2F], 0
0x140056341  mov     rsi, rcx
0x140056344  mov     [rbp+var_30], 0
0x140056348  mov     [rbp+var_20], 0
0x140056350  mov     [rbp+var_18], 0
0x140056358  mov     [rbp+var_28], 0
0x140056360  mov     rcx, cs:WPP_GLOBAL_Control
0x140056367  lea     r12, WPP_GLOBAL_Control
0x14005636e  lea     r13, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x140056375  cmp     rcx, r12
0x140056378  jz      short loc_140056394
0x14005637a  cmp     byte ptr [rcx+29h], 4
0x14005637e  jb      short loc_140056394
0x140056380  mov     rcx, [rcx+18h]
0x140056384  mov     edx, 91h
0x140056389  mov     r9, rsi
0x14005638c  mov     r8, r13
0x14005638f  call    WPP_SF_q
0x140056394  lea     rax, [rbp+var_18]
0x140056398  mov     rcx, rsi; struct _IRP *
0x14005639b  mov     [rsp+80h+var_58], rax; struct _HW_DEVICE_EXTENSION **
0x1400563a0  lea     r9, [rbp+var_30]; unsigned __int8 *
0x1400563a4  lea     rax, [rbp+var_20]
0x1400563a8  lea     r8, [rbp+var_2F]; unsigned __int8 *
0x1400563ac  mov     [rsp+80h+var_60], rax; struct _TOPOLOGY_NODE_INFO **
0x1400563b1  lea     rdx, [rbp+var_28]; struct _KSFILTER **
0x1400563b5  call    ?MSXUGetInfo@@YAJPEAU_IRP@@PEAPEAU_KSFILTER@@PEAE2PEAPEAU_TOPOLOGY_NODE_INFO@@PEAPEAU_HW_DEVICE_EXTENSION@@@Z; MSXUGetInfo(_IRP *,_KSFILTER * *,uchar *,uchar *,_TOPOLOGY_NODE_INFO * *,_HW_DEVICE_EXTENSION * *)
0x1400563ba  mov     ebx, eax
0x1400563bc  test    eax, eax
0x1400563be  jns     short loc_1400563E4
0x1400563c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400563c7  cmp     rcx, r12
0x1400563ca  jz      loc_14005674C
0x1400563d0  cmp     byte ptr [rcx+29h], 2
0x1400563d4  jb      loc_140056726
0x1400563da  mov     edx, 92h
0x1400563df  jmp     loc_14005671A
0x1400563e4  xor     r9d, r9d
0x1400563e7  mov     rdx, rdi
0x1400563ea  mov     rcx, rsi
0x1400563ed  lea     r8d, [r9+38h]
0x1400563f1  call    ValidateExtendedPropertyDataBufferLength
0x1400563f6  mov     ebx, eax
0x1400563f8  test    eax, eax
0x1400563fa  jns     short loc_14005641F
0x1400563fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140056403  cmp     rcx, r12
0x140056406  jz      loc_14005674C
0x14005640c  cmp     byte ptr [rcx+29h], 2
0x140056410  jb      loc_140056726
0x140056416  lea     edx, [r8+5Bh]
0x14005641a  jmp     loc_14005671A
0x14005641f  mov     r14, [rbp+var_18]
0x140056423  mov     r11d, 1
0x140056429  mov     ebx, 0C000000Dh
0x14005642e  mov     rsi, [r14+3D0h]
0x140056435  movzx   r8d, byte ptr [rsi+21h]
0x14005643a  mov     ecx, r8d
0x14005643d  and     rcx, r11
0x140056440  mov     rdx, rcx
0x140056443  or      rdx, 2
0x140056447  test    r8b, 2
0x14005644b  cmovz   rdx, rcx
0x14005644f  mov     rcx, rdx
0x140056452  or      rcx, 4
0x140056456  test    r8b, 4
0x14005645a  cmovz   rcx, rdx
0x14005645e  mov     rdx, rcx
0x140056461  or      rdx, 8
0x140056465  test    r8b, 8
0x140056469  cmovz   rdx, rcx
0x14005646d  mov     r10, rdx
0x140056470  or      r10, 10h
0x140056474  test    r8b, 10h
0x140056478  cmovz   r10, rdx
0x14005647c  cmp     [rdi], r11d
0x14005647f  jnz     loc_140056703
0x140056485  cmp     dword ptr [rdi+8], 38h ; '8'
0x140056489  jb      loc_140056703
0x14005648f  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x140056493  jnz     loc_140056703
0x140056499  mov     r9, [rdi+10h]
0x14005649d  mov     rax, r9
0x1400564a0  sub     rax, r11
0x1400564a3  jz      short loc_140056503
0x1400564a5  sub     rax, r11
0x1400564a8  jz      short loc_1400564FC
0x1400564aa  sub     rax, 2
0x1400564ae  jz      short loc_1400564F5
0x1400564b0  sub     rax, 4
0x1400564b4  jz      short loc_1400564EE
0x1400564b6  cmp     rax, 8
0x1400564ba  jz      short loc_1400564E9
0x1400564bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400564c3  cmp     rcx, r12
0x1400564c6  jz      loc_14005674C
0x1400564cc  cmp     byte ptr [rcx+29h], 2
0x1400564d0  jb      loc_140056726
0x1400564d6  mov     rcx, [rcx+18h]
0x1400564da  mov     edx, 94h
0x1400564df  call    WPP_SF_i
0x1400564e4  jmp     loc_140056726
0x1400564e9  mov     ecx, r11d
0x1400564ec  jmp     short loc_140056508
0x1400564ee  mov     ecx, 2
0x1400564f3  jmp     short loc_140056508
0x1400564f5  mov     ecx, 3
0x1400564fa  jmp     short loc_140056508
0x1400564fc  mov     ecx, 4
0x140056501  jmp     short loc_140056508
0x140056503  mov     ecx, 6
0x140056508  mov     rax, r10
0x14005650b  and     rax, r9
0x14005650e  cmp     rax, r9
0x140056511  jnz     loc_1400566DC
0x140056517  mov     r11d, [rsi+12h]
0x14005651b  mov     eax, r11d
0x14005651e  mov     r8d, [rdi+2Ch]
0x140056522  imul    eax, ecx
0x140056525  cmp     r8d, eax
0x140056528  jg      loc_14005669F
0x14005652e  mov     eax, ecx
0x140056530  imul    eax, [rsi+7]
0x140056534  cmp     r8d, eax
0x140056537  jl      loc_14005669F
0x14005653d  xor     eax, eax
0x14005653f  mov     r10, r9
0x140056542  mov     [rbp+var_18], rax
0x140056546  mov     rdx, r9
0x140056549  mov     [rbp+var_10], ax
0x14005654d  mov     [rbp+var_E], al
0x140056550  lea     ebx, [rax+1]
0x140056553  movzx   eax, al
0x140056556  and     rdx, rbx
0x140056559  cmovnz  eax, ebx
0x14005655c  and     r10d, 2
0x140056560  mov     byte ptr [rbp+var_18], al
0x140056563  mov     al, dl
0x140056565  or      al, 2
0x140056567  test    r10, r10
0x14005656a  jz      short loc_14005656F
0x14005656c  mov     byte ptr [rbp+var_18], al
0x14005656f  movzx   ecx, al
0x140056572  test    r10, r10
0x140056575  movzx   eax, dl
0x140056578  mov     r10, r9
0x14005657b  cmovz   ecx, eax
0x14005657e  and     r10d, 4
0x140056582  mov     al, cl
0x140056584  or      al, 4
0x140056586  test    r10, r10
0x140056589  jz      short loc_14005658E
0x14005658b  mov     byte ptr [rbp+var_18], al
0x14005658e  movzx   edx, al
0x140056591  test    r10, r10
0x140056594  movzx   eax, cl
0x140056597  mov     r10, r9
0x14005659a  cmovz   edx, eax
0x14005659d  and     r10d, 8
0x1400565a1  mov     al, dl
0x1400565a3  or      al, 8
0x1400565a5  test    r10, r10
0x1400565a8  jz      short loc_1400565AD
0x1400565aa  mov     byte ptr [rbp+var_18], al
0x1400565ad  movzx   ecx, al
0x1400565b0  test    r10, r10
0x1400565b3  movzx   eax, dl
0x1400565b6  cmovz   ecx, eax
0x1400565b9  and     r9d, 10h
0x1400565bd  mov     al, cl
0x1400565bf  or      al, 10h
0x1400565c1  test    r9, r9
0x1400565c4  jz      short loc_1400565C9
0x1400565c6  mov     byte ptr [rbp+var_18], al
0x1400565c9  mov     dword ptr [rbp+var_18+7], r8d
0x1400565cd  test    r9, r9
0x1400565d0  movsd   xmm0, [rbp+var_18]
0x1400565d5  movzx   edx, al
0x1400565d8  movzx   eax, cl
0x1400565db  movsd   [rbp+var_18], xmm0
0x1400565e0  cmovz   edx, eax
0x1400565e3  mov     dword ptr [rbp+var_18+7], r8d
0x1400565e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400565ee  cmp     rcx, r12
0x1400565f1  jz      short loc_140056614
0x1400565f3  cmp     byte ptr [rcx+29h], 4
0x1400565f7  jb      short loc_140056614
0x1400565f9  mov     rcx, [rcx+18h]
0x1400565fd  mov     r9d, r8d
0x140056600  movzx   eax, dl
0x140056603  mov     r8, r13
0x140056606  mov     edx, 95h
0x14005660b  mov     dword ptr [rsp+80h+var_60], eax
0x14005660f  call    WPP_SF_dd
0x140056614  mov     rax, [rbp+var_28]
0x140056618  mov     r8d, 300h; int
0x14005661e  mov     r9b, [rbp+var_2F]; int
0x140056622  mov     dl, bl; int
0x140056624  mov     [r14+458h], rax
0x14005662b  mov     cl, 21h ; '!'; int
0x14005662d  mov     rax, [rbp+var_20]
0x140056631  mov     [rsp+80h+var_40], r14; __int64
0x140056636  mov     [rsp+80h+var_48], rax; __int64
0x14005663b  lea     rax, [rbp+var_18]
0x14005663f  mov     dword ptr [rsp+80h+Size], 0Bh; Size
0x140056647  mov     [rsp+80h+var_58], rax; void *
0x14005664c  mov     al, [rbp+var_30]
0x14005664f  mov     byte ptr [rsp+80h+var_60], al; int
0x140056653  mov     [r14+508h], ebx
0x14005665a  call    SubmitControlRequest
0x14005665f  mov     ebx, eax
0x140056661  test    eax, eax
0x140056663  jns     loc_140056726
0x140056669  mov     rcx, cs:WPP_GLOBAL_Control
0x140056670  cmp     rcx, r12
0x140056673  jz      short loc_14005668F
0x140056675  cmp     byte ptr [rcx+29h], 2
0x140056679  jb      short loc_14005668F
0x14005667b  mov     rcx, [rcx+18h]
0x14005667f  mov     edx, 96h
0x140056684  mov     r9d, eax
0x140056687  mov     r8, r13
0x14005668a  call    WPP_SF_d
0x14005668f  mov     qword ptr [r14+458h], 0
0x14005669a  jmp     loc_140056726
0x14005669f  mov     r10, cs:WPP_GLOBAL_Control
0x1400566a6  cmp     r10, r12
0x1400566a9  jz      loc_14005674C
0x1400566af  cmp     byte ptr [r10+29h], 2
0x1400566b4  jb      short loc_140056726
0x1400566b6  mov     eax, [rsi+7]
0x1400566b9  mov     r9d, r8d
0x1400566bc  mov     dword ptr [rsp+80h+Size], ecx
0x1400566c0  mov     r8, r13
0x1400566c3  mov     rcx, [r10+18h]
0x1400566c7  mov     edx, 97h
0x1400566cc  mov     dword ptr [rsp+80h+var_58], r11d
0x1400566d1  mov     dword ptr [rsp+80h+var_60], eax
0x1400566d5  call    WPP_SF_DDDD
0x1400566da  jmp     short loc_140056726
0x1400566dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400566e3  cmp     rcx, r12
0x1400566e6  jz      short loc_14005674C
0x1400566e8  cmp     byte ptr [rcx+29h], 2
0x1400566ec  jb      short loc_140056726
0x1400566ee  mov     rcx, [rcx+18h]
0x1400566f2  mov     edx, 98h
0x1400566f7  mov     [rsp+80h+var_60], r10
0x1400566fc  call    WPP_SF_ii
0x140056701  jmp     short loc_140056726
0x140056703  mov     rcx, cs:WPP_GLOBAL_Control
0x14005670a  cmp     rcx, r12
0x14005670d  jz      short loc_14005674C
0x14005670f  cmp     byte ptr [rcx+29h], 2
0x140056713  jb      short loc_140056726
0x140056715  mov     edx, 99h
0x14005671a  mov     rcx, [rcx+18h]
0x14005671e  mov     r8, r13
0x140056721  call    WPP_SF_
0x140056726  mov     rcx, cs:WPP_GLOBAL_Control
0x14005672d  cmp     rcx, r12
0x140056730  jz      short loc_14005674C
0x140056732  cmp     byte ptr [rcx+29h], 4
0x140056736  jb      short loc_14005674C
0x140056738  mov     rcx, [rcx+18h]
0x14005673c  mov     edx, 9Ah
0x140056741  mov     r9d, ebx
0x140056744  mov     r8, r13
0x140056747  call    WPP_SF_d
0x14005674c  mov     eax, ebx
0x14005674e  mov     rcx, [rbp+var_8]
0x140056752  xor     rcx, rsp; StackCookie
0x140056755  call    __security_check_cookie
0x14005675a  lea     r11, [rsp+80h+var_s0]
0x140056762  mov     rbx, [r11+38h]
0x140056766  mov     rsi, [r11+48h]
0x14005676a  mov     rsp, r11
0x14005676d  pop     r14
0x14005676f  pop     r13
0x140056771  pop     r12
0x140056773  pop     rdi
0x140056774  pop     rbp
0x140056775  retn
```

# MSXU_ExposureSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14005b300`
- end: `0x14005b891`
- name: `?MSXU_ExposureSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1425`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14000ef88`
- `0x140019cd4`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b364`
- `0x14003b798`
- `0x14003ba48`
- `0x14003bb60`
- `0x140040a30`
- `0x14005b300`
- `0x14005bc78`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14005b354`
- `ks!KsGetFilterFromIrp` at `0x14005b354`

## pseudocode

```c
__int64 __fastcall MSXU_ExposureSet(PIRP Irp, struct KSIDENTIFIER *a2, _QWORD *a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // r8
  PKSFILTER v7; // r13
  __int64 v8; // r15
  __int64 v9; // r12
  __int64 v10; // rcx
  __int64 v11; // rdx
  NTSTATUS v12; // ebx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // r8
  unsigned __int64 v17; // r14
  __int64 v18; // rcx
  unsigned __int64 v19; // r9
  unsigned __int64 v20; // r11
  unsigned __int64 v21; // r10
  unsigned __int64 v22; // r8
  unsigned __int64 v23; // r10
  unsigned __int8 v24; // dl
  __int64 v25; // r8
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  int v32; // [rsp+20h] [rbp-49h]
  size_t Size; // [rsp+30h] [rbp-39h]
  char v34; // [rsp+50h] [rbp-19h]
  unsigned __int8 v35; // [rsp+51h] [rbp-18h]
  __int64 v36; // [rsp+58h] [rbp-11h]
  __int64 v38; // [rsp+70h] [rbp+7h] BYREF
  int v39; // [rsp+78h] [rbp+Fh]
  __int16 v40; // [rsp+7Ch] [rbp+13h]
  char v41; // [rsp+7Eh] [rbp+15h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  v7 = FilterFromIrp;
  if ( !FilterFromIrp )
  {
    v12 = -1073741823;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_40;
    v31 = 81;
    goto LABEL_48;
  }
  v8 = *(_QWORD *)FilterFromIrp->Context;
  v9 = *(_QWORD *)(v8 + 880);
  v10 = *(_QWORD *)(v9 + 32);
  v34 = *(_BYTE *)(v9 + 40);
  v35 = *(_BYTE *)(v10 + 3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDDqq(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int8 *)(v10 + 3),
      v6,
      FilterFromIrp,
      *(unsigned __int8 *)(v10 + 3),
      *(unsigned __int8 *)(v9 + 40),
      v9,
      v8);
  v12 = ValidateExtendedPropertyDataBufferLength(Irp, a3, 64);
  if ( v12 < 0 )
  {
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_40;
    v31 = 82;
    goto LABEL_48;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_iiiDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      v11,
      v13,
      a3[6],
      a3[2],
      a3[3],
      *((_DWORD *)a3 + 9),
      *((_DWORD *)a3 + 10),
      *((_DWORD *)a3 + 11));
  v14 = a3[2];
  if ( v14 != 5 && v14 != 1 && v14 != 2 && v14 != 4 && v14 != 0x8000000000000000uLL )
  {
    v12 = -1073741811;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_40;
    v31 = 84;
    goto LABEL_48;
  }
  if ( (__int64)a3[3] >= 0
    || !CExtendedVidProcSetting::isValid((CExtendedVidProcSetting *)a3)
    || *((_DWORD *)a3 + 1) != -1 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    goto LABEL_40;
  }
  v15 = *(_QWORD *)(v8 + 968);
  v17 = GetExtPropFlags(*(unsigned __int8 *)(v15 + 15)) | 0xC000000000000000uLL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 85, v16, v17);
  v18 = a3[2];
  if ( (v17 & v18) == v18 )
  {
    if ( v18 == 2 )
    {
      v19 = *(_QWORD *)(v15 + 52);
      v20 = *(_QWORD *)(v15 + 22);
      v21 = *(_QWORD *)(v15 + 7);
      if ( !v19 && v21 != v20 || (v22 = a3[6], v19) && (v22 - v21) % v19 || v22 > v20 || (v12 = 0, v22 < v21) )
        v12 = -1073741811;
      if ( v12 < 0 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_41;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          goto LABEL_40;
        v31 = 89;
        goto LABEL_48;
      }
    }
    else
    {
      v12 = 0;
    }
    if ( v18 >= 0 )
    {
      v23 = a3[6];
      v24 = v18 & 1;
      v36 = (v18 & 1) != 0;
      if ( (v18 & 2) != 0 )
        LOBYTE(v36) = v24 | 2;
      v25 = v24 | 2u;
      if ( (v18 & 2) == 0 )
        v25 = v24;
      v26 = v18 & 4;
      if ( v26 )
        LOBYTE(v36) = v25 | 4;
      v27 = (unsigned __int8)v25 | 4u;
      if ( !v26 )
        v27 = (unsigned __int8)v25;
      v38 = v36;
      v39 = v23 >> 8;
      v40 = HIDWORD(v23) >> 8;
      v41 = HIBYTE(v23);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_iD(WPP_GLOBAL_Control->AttachedDevice, v27, v25, v23, (unsigned __int8)v27);
      LODWORD(Size) = 15;
      LOBYTE(v32) = v34;
      *(_QWORD *)(v8 + 1104) = v7;
      *(_DWORD *)(v8 + 1284) = 1;
      v28 = SubmitControlRequest(0x21u, 1u, 0x200u, v35, v32, (unsigned __int8 *)&v38, Size, v9, v8);
      v12 = v28;
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            88,
            WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
            (unsigned int)v28);
        *(_QWORD *)(v8 + 1104) = 0;
      }
      goto LABEL_40;
    }
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_41;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_40;
    v31 = 86;
    goto LABEL_48;
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_41;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v31 = 90;
LABEL_48:
    WPP_SF_(v30->AttachedDevice, v31, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_40:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v12);
LABEL_41:
  Irp->IoStatus.Status = v12;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005b300  mov     [rsp-8+arg_8], rbx
0x14005b305  push    rbp
0x14005b306  push    rsi
0x14005b307  push    rdi
0x14005b308  push    r12
0x14005b30a  push    r13
0x14005b30c  push    r14
0x14005b30e  push    r15
0x14005b310  lea     rbp, [rsp-27h]
0x14005b315  sub     rsp, 90h
0x14005b31c  mov     rax, cs:__security_cookie
0x14005b323  xor     rax, rsp
0x14005b326  mov     [rbp+57h+var_40], rax
0x14005b32a  mov     rdi, r8
0x14005b32d  mov     [rbp+57h+var_58], rcx
0x14005b331  mov     rbx, rcx
0x14005b334  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b33b  lea     rax, WPP_GLOBAL_Control
0x14005b342  cmp     rcx, rax
0x14005b345  jz      short loc_14005B351
0x14005b347  cmp     byte ptr [rcx+29h], 4
0x14005b34b  jnb     loc_14005B64A
0x14005b351  mov     rcx, rbx; Irp
0x14005b354  call    cs:__imp_KsGetFilterFromIrp
0x14005b35b  nop     dword ptr [rax+rax+00h]
0x14005b360  mov     r13, rax
0x14005b363  test    rax, rax
0x14005b366  jz      loc_14005B612
0x14005b36c  mov     rcx, [rax+10h]
0x14005b370  mov     r15, [rcx]
0x14005b373  mov     r12, [r15+370h]
0x14005b37a  mov     rcx, [r12+20h]
0x14005b37f  movzx   eax, byte ptr [r12+28h]
0x14005b385  mov     [rbp+57h+var_70], al
0x14005b388  movzx   edx, byte ptr [rcx+3]
0x14005b38c  mov     [rbp+57h+var_70+1], dl
0x14005b38f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b396  lea     rsi, WPP_GLOBAL_Control
0x14005b39d  cmp     rcx, rsi
0x14005b3a0  jz      short loc_14005B3AC
0x14005b3a2  cmp     byte ptr [rcx+29h], 5
0x14005b3a6  jnb     loc_14005B667
0x14005b3ac  xor     r9d, r9d
0x14005b3af  mov     rdx, rdi
0x14005b3b2  mov     rcx, rbx
0x14005b3b5  lea     r8d, [r9+40h]
0x14005b3b9  call    ValidateExtendedPropertyDataBufferLength
0x14005b3be  mov     ebx, eax
0x14005b3c0  test    eax, eax
0x14005b3c2  js      loc_14005B68A
0x14005b3c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b3cf  cmp     rcx, rsi
0x14005b3d2  jz      short loc_14005B3DE
0x14005b3d4  cmp     byte ptr [rcx+29h], 4
0x14005b3d8  jnb     loc_14005B6AB
0x14005b3de  mov     rax, [rdi+10h]
0x14005b3e2  cmp     rax, 5
0x14005b3e6  jnz     loc_14005B6E4
0x14005b3ec  cmp     qword ptr [rdi+18h], 0
0x14005b3f1  jge     loc_14005B825
0x14005b3f7  mov     rcx, rdi; this
0x14005b3fa  call    ?isValid@CExtendedVidProcSetting@@QEAA_NXZ; CExtendedVidProcSetting::isValid(void)
0x14005b3ff  test    al, al
0x14005b401  jz      loc_14005B825
0x14005b407  cmp     dword ptr [rdi+4], 0FFFFFFFFh
0x14005b40b  jnz     loc_14005B825
0x14005b411  mov     rsi, [r15+3C8h]
0x14005b418  movzx   ecx, byte ptr [rsi+0Fh]; unsigned int
0x14005b41c  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x14005b421  mov     r14, rax
0x14005b424  mov     rax, 0C000000000000000h
0x14005b42e  or      r14, rax
0x14005b431  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b438  lea     rax, WPP_GLOBAL_Control
0x14005b43f  cmp     rcx, rax
0x14005b442  jz      short loc_14005B44E
0x14005b444  cmp     byte ptr [rcx+29h], 2
0x14005b448  jnb     loc_14005B73E
0x14005b44e  mov     rcx, [rdi+10h]
0x14005b452  mov     rax, rcx
0x14005b455  and     rax, r14
0x14005b458  cmp     rax, rcx
0x14005b45b  jnz     loc_14005B5F2
0x14005b461  cmp     rcx, 2
0x14005b465  jnz     loc_14005B792
0x14005b46b  mov     r9, [rsi+34h]
0x14005b46f  mov     r11, [rsi+16h]
0x14005b473  mov     r10, [rsi+7]
0x14005b477  test    r9, r9
0x14005b47a  jz      loc_14005B754
0x14005b480  mov     r8, [rdi+30h]
0x14005b484  test    r9, r9
0x14005b487  jz      short loc_14005B49D
0x14005b489  xor     edx, edx
0x14005b48b  mov     rax, r8
0x14005b48e  sub     rax, r10
0x14005b491  div     r9
0x14005b494  test    rdx, rdx
0x14005b497  jnz     loc_14005B75D
0x14005b49d  cmp     r8, r11
0x14005b4a0  ja      loc_14005B75D
0x14005b4a6  xor     ebx, ebx
0x14005b4a8  cmp     r8, r10
0x14005b4ab  jb      loc_14005B75D
0x14005b4b1  test    ebx, ebx
0x14005b4b3  js      loc_14005B767
0x14005b4b9  test    rcx, rcx
0x14005b4bc  js      loc_14005B799
0x14005b4c2  mov     r10, [rdi+30h]
0x14005b4c6  xor     eax, eax
0x14005b4c8  mov     [rbp+57h+var_68], rax
0x14005b4cc  mov     r9, rcx
0x14005b4cf  mov     rdx, rcx
0x14005b4d2  mov     [rbp+57h+var_68+7], r10
0x14005b4d6  lea     ebx, [rax+1]
0x14005b4d9  movzx   eax, byte ptr [rbp+57h+var_68]
0x14005b4dd  and     rdx, rbx
0x14005b4e0  cmovnz  eax, ebx
0x14005b4e3  and     r9d, 2
0x14005b4e7  mov     byte ptr [rbp+57h+var_68], al
0x14005b4ea  mov     al, dl
0x14005b4ec  or      al, 2
0x14005b4ee  test    r9, r9
0x14005b4f1  jz      short loc_14005B4F6
0x14005b4f3  mov     byte ptr [rbp+57h+var_68], al
0x14005b4f6  movzx   r8d, al
0x14005b4fa  test    r9, r9
0x14005b4fd  movzx   eax, dl
0x14005b500  cmovz   r8d, eax
0x14005b504  and     ecx, 4
0x14005b507  mov     al, r8b
0x14005b50a  or      al, 4
0x14005b50c  test    rcx, rcx
0x14005b50f  jnz     loc_14005B7C4
0x14005b515  movsd   xmm0, [rbp+57h+var_68]
0x14005b51a  test    rcx, rcx
0x14005b51d  movzx   edx, al
0x14005b520  movzx   eax, r8b
0x14005b524  cmovz   edx, eax
0x14005b527  movsd   [rbp+57h+var_50], xmm0
0x14005b52c  mov     eax, [rbp+57h+var_60]
0x14005b52f  mov     [rbp+57h+var_48], eax
0x14005b532  movzx   eax, [rbp+57h+var_5C]
0x14005b536  mov     [rbp+57h+var_44], ax
0x14005b53a  mov     al, [rbp+57h+var_5A]
0x14005b53d  mov     [rbp+57h+var_42], al
0x14005b540  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b547  lea     rax, WPP_GLOBAL_Control
0x14005b54e  cmp     rcx, rax
0x14005b551  jz      short loc_14005B55D
0x14005b553  cmp     byte ptr [rcx+29h], 4
0x14005b557  jnb     loc_14005B7CC
0x14005b55d  mov     r9b, [rbp+57h+var_70+1]; int
0x14005b561  lea     rax, [rbp+57h+var_50]
0x14005b565  mov     [rsp+0C0h+var_80], r15; __int64
0x14005b56a  mov     r8d, 200h; int
0x14005b570  mov     [rsp+0C0h+var_88], r12; __int64
0x14005b575  mov     dl, bl; int
0x14005b577  mov     dword ptr [rsp+0C0h+Size], 0Fh; Size
0x14005b57f  mov     cl, 21h ; '!'; int
0x14005b581  mov     [rsp+0C0h+var_98], rax; void *
0x14005b586  mov     al, [rbp+57h+var_70]
0x14005b589  mov     byte ptr [rsp+0C0h+var_A0], al; int
0x14005b58d  mov     [r15+450h], r13
0x14005b594  mov     [r15+504h], ebx
0x14005b59b  call    SubmitControlRequest
0x14005b5a0  mov     ebx, eax
0x14005b5a2  test    eax, eax
0x14005b5a4  js      loc_14005B7E4
0x14005b5aa  lea     rsi, WPP_GLOBAL_Control
0x14005b5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b5b8  cmp     rcx, rsi
0x14005b5bb  jnz     loc_14005B86A
0x14005b5c1  mov     rax, [rbp+57h+var_58]
0x14005b5c5  mov     [rax+30h], ebx
0x14005b5c8  mov     eax, ebx
0x14005b5ca  mov     rcx, [rbp+57h+var_40]
0x14005b5ce  xor     rcx, rsp; StackCookie
0x14005b5d1  call    __security_check_cookie
0x14005b5d6  mov     rbx, [rsp+0C0h+arg_8]
0x14005b5de  add     rsp, 90h
0x14005b5e5  pop     r15
0x14005b5e7  pop     r14
0x14005b5e9  pop     r13
0x14005b5eb  pop     r12
0x14005b5ed  pop     rdi
0x14005b5ee  pop     rsi
0x14005b5ef  pop     rbp
0x14005b5f0  retn
0x14005b5f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b5f9  lea     rsi, WPP_GLOBAL_Control
0x14005b600  cmp     rcx, rsi
0x14005b603  jz      short loc_14005B5C1
0x14005b605  cmp     byte ptr [rcx+29h], 2
0x14005b609  jb      short loc_14005B5B1
0x14005b60b  mov     edx, 5Ah ; 'Z'
0x14005b610  jmp     short loc_14005B635
0x14005b612  mov     ebx, 0C0000001h
0x14005b617  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b61e  lea     rsi, WPP_GLOBAL_Control
0x14005b625  cmp     rcx, rsi
0x14005b628  jz      short loc_14005B5C1
0x14005b62a  cmp     byte ptr [rcx+29h], 2
0x14005b62e  jb      short loc_14005B5B1
0x14005b630  mov     edx, 51h ; 'Q'
0x14005b635  mov     rcx, [rcx+18h]
0x14005b639  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b640  call    WPP_SF_
0x14005b645  jmp     loc_14005B5B1
0x14005b64a  mov     rcx, [rcx+18h]
0x14005b64e  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005b655  mov     edx, 50h ; 'P'
0x14005b65a  mov     r9, rbx
0x14005b65d  call    WPP_SF_q
0x14005b662  jmp     loc_14005B351
0x14005b667  mov     rcx, [rcx+18h]
0x14005b66b  mov     r9, r13
0x14005b66e  mov     [rsp+0C0h+var_88], r15
0x14005b673  mov     [rsp+0C0h+Size], r12
0x14005b678  mov     dword ptr [rsp+0C0h+var_98], eax
0x14005b67c  mov     [rsp+0C0h+var_A0], edx
0x14005b680  call    WPP_SF_qDDqq
0x14005b685  jmp     loc_14005B3AC
0x14005b68a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b691  cmp     rcx, rsi
0x14005b694  jz      loc_14005B5C1
0x14005b69a  cmp     byte ptr [rcx+29h], 2
0x14005b69e  jb      loc_14005B5B1
0x14005b6a4  mov     edx, 52h ; 'R'
0x14005b6a9  jmp     short loc_14005B635
0x14005b6ab  mov     eax, [rdi+2Ch]
0x14005b6ae  mov     r9, [rdi+30h]
0x14005b6b2  mov     rcx, [rcx+18h]
0x14005b6b6  mov     dword ptr [rsp+0C0h+var_80], eax
0x14005b6ba  mov     eax, [rdi+28h]
0x14005b6bd  mov     dword ptr [rsp+0C0h+var_88], eax
0x14005b6c1  mov     eax, [rdi+24h]
0x14005b6c4  mov     dword ptr [rsp+0C0h+Size], eax
0x14005b6c8  mov     rax, [rdi+18h]
0x14005b6cc  mov     [rsp+0C0h+var_98], rax
0x14005b6d1  mov     rax, [rdi+10h]
0x14005b6d5  mov     qword ptr [rsp+0C0h+var_A0], rax
0x14005b6da  call    WPP_SF_iiiDDD
0x14005b6df  jmp     loc_14005B3DE
0x14005b6e4  cmp     rax, 1
0x14005b6e8  jz      loc_14005B3EC
0x14005b6ee  cmp     rax, 2
0x14005b6f2  jz      loc_14005B3EC
0x14005b6f8  cmp     rax, 4
0x14005b6fc  jz      loc_14005B3EC
0x14005b702  mov     rcx, 8000000000000000h
0x14005b70c  cmp     rax, rcx
0x14005b70f  jz      loc_14005B3EC
0x14005b715  mov     ebx, 0C000000Dh
0x14005b71a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b721  cmp     rcx, rsi
0x14005b724  jz      loc_14005B5C1
0x14005b72a  cmp     byte ptr [rcx+29h], 2
0x14005b72e  jb      loc_14005B5B1
0x14005b734  mov     edx, 54h ; 'T'
0x14005b739  jmp     loc_14005B635
0x14005b73e  mov     rcx, [rcx+18h]
0x14005b742  mov     edx, 55h ; 'U'
0x14005b747  mov     r9, r14
0x14005b74a  call    WPP_SF_i
0x14005b74f  jmp     loc_14005B44E
0x14005b754  cmp     r10, r11
0x14005b757  jz      loc_14005B480
0x14005b75d  mov     ebx, 0C000000Dh
0x14005b762  jmp     loc_14005B4B1
0x14005b767  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b76e  lea     rsi, WPP_GLOBAL_Control
0x14005b775  cmp     rcx, rsi
0x14005b778  jz      loc_14005B5C1
0x14005b77e  cmp     byte ptr [rcx+29h], 2
0x14005b782  jb      loc_14005B5B1
0x14005b788  mov     edx, 59h ; 'Y'
0x14005b78d  jmp     loc_14005B635
0x14005b792  xor     ebx, ebx
0x14005b794  jmp     loc_14005B4B9
0x14005b799  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b7a0  lea     rsi, WPP_GLOBAL_Control
0x14005b7a7  cmp     rcx, rsi
0x14005b7aa  jz      loc_14005B5C1
0x14005b7b0  cmp     byte ptr [rcx+29h], 2
0x14005b7b4  jb      loc_14005B5B1
0x14005b7ba  mov     edx, 56h ; 'V'
0x14005b7bf  jmp     loc_14005B635
0x14005b7c4  mov     byte ptr [rbp+57h+var_68], al
0x14005b7c7  jmp     loc_14005B515
0x14005b7cc  mov     rcx, [rcx+18h]
0x14005b7d0  mov     r9, r10
0x14005b7d3  movzx   eax, dl
0x14005b7d6  mov     [rsp+0C0h+var_A0], eax
0x14005b7da  call    WPP_SF_iD
0x14005b7df  jmp     loc_14005B55D
0x14005b7e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b7eb  lea     rsi, WPP_GLOBAL_Control
0x14005b7f2  cmp     rcx, rsi
0x14005b7f5  jz      short loc_14005B815
  ... truncated ...
```

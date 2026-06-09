# MSXU_FaceAuthSet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14005c860`
- end: `0x14005ccb0`
- name: `?MSXU_FaceAuthSet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `1104`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b85c`
- `0x14003b8b8`
- `0x14003bb60`
- `0x140040a30`
- `0x14005c594`
- `0x14005c69c`
- `0x14005c860`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14005c8bf`
- `ks!KsGetFilterFromIrp` at `0x14005c8bf`

## pseudocode

```c
__int64 __fastcall MSXU_FaceAuthSet(PIRP Irp, struct KSIDENTIFIER *a2, char *a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // r8
  PKSFILTER v7; // r14
  __int64 v8; // rsi
  __int64 v9; // r13
  __int64 v10; // rcx
  NTSTATUS FaceAuthFlags; // ebx
  __int64 v12; // r8
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  _DWORD *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int8 v20; // r12
  unsigned __int64 v21; // r8
  struct _MSXU_PAYLOAD_FACEAUTH *v22; // rdx
  char v23; // r9
  char v24; // dl
  unsigned __int8 v25; // cl
  __int64 v26; // r9
  unsigned __int8 v27; // dl
  int v28; // eax
  PDEVICE_OBJECT v29; // rcx
  __int64 v30; // rdx
  int v32; // [rsp+20h] [rbp-50h]
  size_t Size; // [rsp+30h] [rbp-40h]
  char v34; // [rsp+50h] [rbp-20h]
  unsigned __int8 v35; // [rsp+51h] [rbp-1Fh]
  unsigned __int64 v36; // [rsp+58h] [rbp-18h] BYREF
  char v37; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  v7 = FilterFromIrp;
  if ( !FilterFromIrp )
  {
    FaceAuthFlags = -1073741823;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_59;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_56;
    v14 = 170;
    goto LABEL_55;
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
  FaceAuthFlags = ValidateExtendedPropertyDataBufferLength(Irp, a3, 40);
  if ( FaceAuthFlags >= 0 )
  {
    v15 = a3 + 8;
    FaceAuthFlags = -1073741811;
    if ( *(_DWORD *)a3 != 1
      || *v15 < (unsigned int)v12
      || (v16 = *((unsigned int *)a3 + 1), (unsigned int)v16 >= v7->Descriptor->PinDescriptorsCount) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_59;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          177,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          (unsigned int)*v15,
          *((_DWORD *)a3 + 1));
      goto LABEL_49;
    }
    v17 = *(_QWORD *)(v8 + 744);
    v18 = 136 * v16;
    if ( *(_DWORD *)(v18 + v17 + 120) || (v19 = *(_QWORD *)(v18 + v17 + 128)) == 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_59;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_49;
      v30 = 176;
    }
    else
    {
      v20 = *(_BYTE *)(v19 + 2);
      v21 = *(unsigned __int16 *)(v8 + 1236);
      v22 = (struct _MSXU_PAYLOAD_FACEAUTH *)(v21 + *(_QWORD *)(v8 + 1000));
      v36 = 0;
      FaceAuthFlags = GetFaceAuthFlags((struct _HW_DEVICE_EXTENSION *)v8, v22, v21, v20, &v36);
      if ( FaceAuthFlags >= 0 )
      {
        FaceAuthFlags = ValidateFlagsFaceAuth(*((_QWORD *)a3 + 2), v36);
        if ( FaceAuthFlags < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            goto LABEL_59;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 174);
        }
        else
        {
          v36 = 1;
          BYTE1(v36) = v20;
          v24 = v23 & 1;
          BYTE2(v36) = (v23 & 1) != 0;
          if ( (v23 & 2) != 0 )
            BYTE2(v36) = v24 | 2;
          v25 = v24 | 2;
          if ( (v23 & 2) == 0 )
            v25 = v23 & 1;
          v26 = v23 & 4;
          if ( v26 )
            BYTE2(v36) = v25 | 4;
          v27 = v25 | 4;
          if ( !v26 )
            v27 = v25;
          v37 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 172, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v27);
          LODWORD(Size) = 9;
          LOBYTE(v32) = v34;
          *(_QWORD *)(v8 + 1136) = v7;
          *(_DWORD *)(v8 + 1300) = 1;
          v28 = SubmitControlRequest(0x21u, 1u, 0x600u, v35, v32, (unsigned __int8 *)&v36, Size, v9, v8);
          FaceAuthFlags = v28;
          if ( v28 >= 0 )
          {
            Irp->IoStatus.Information = 40;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                173,
                WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
                (unsigned int)v28);
            *(_QWORD *)(v8 + 1136) = 0;
          }
        }
        goto LABEL_49;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_59;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_49:
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          goto LABEL_59;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_iiD(
            WPP_GLOBAL_Control->AttachedDevice,
            178,
            v12,
            *((_QWORD *)a3 + 2),
            *((_QWORD *)a3 + 3),
            FaceAuthFlags);
        goto LABEL_56;
      }
      v30 = 175;
    }
    WPP_SF_(v29->AttachedDevice, v30, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
    goto LABEL_49;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_59;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v14 = 171;
LABEL_55:
    WPP_SF_(v13->AttachedDevice, v14, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_56:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      179,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      (unsigned int)FaceAuthFlags);
LABEL_59:
  Irp->IoStatus.Status = FaceAuthFlags;
  return (unsigned int)FaceAuthFlags;
}

```

## disassembly

```asm
0x14005c860  mov     [rsp-38h+arg_8], rbx
0x14005c865  push    rbp
0x14005c866  push    rsi
0x14005c867  push    rdi
0x14005c868  push    r12
0x14005c86a  push    r13
0x14005c86c  push    r14
0x14005c86e  push    r15
0x14005c870  mov     rbp, rsp
0x14005c873  sub     rsp, 70h
0x14005c877  mov     rax, cs:__security_cookie
0x14005c87e  xor     rax, rsp
0x14005c881  mov     [rbp+var_8], rax
0x14005c885  mov     rdi, r8
0x14005c888  mov     r15, rcx
0x14005c88b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c892  lea     r12, WPP_GLOBAL_Control
0x14005c899  cmp     rcx, r12
0x14005c89c  jz      short loc_14005C8BC
0x14005c89e  cmp     byte ptr [rcx+29h], 4
0x14005c8a2  jb      short loc_14005C8BC
0x14005c8a4  mov     rcx, [rcx+18h]
0x14005c8a8  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c8af  mov     edx, 0A9h
0x14005c8b4  mov     r9, r15
0x14005c8b7  call    WPP_SF_q
0x14005c8bc  mov     rcx, r15; Irp
0x14005c8bf  call    cs:__imp_KsGetFilterFromIrp
0x14005c8c6  nop     dword ptr [rax+rax+00h]
0x14005c8cb  mov     r14, rax
0x14005c8ce  test    rax, rax
0x14005c8d1  jz      loc_14005CC2F
0x14005c8d7  mov     rcx, [rax+10h]
0x14005c8db  mov     rsi, [rcx]
0x14005c8de  mov     r13, [rsi+370h]
0x14005c8e5  mov     rcx, [r13+20h]
0x14005c8e9  movzx   eax, byte ptr [r13+28h]
0x14005c8ee  mov     [rbp+var_20], al
0x14005c8f1  movzx   edx, byte ptr [rcx+3]
0x14005c8f5  mov     [rbp+var_20+1], dl
0x14005c8f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c8ff  cmp     rcx, r12
0x14005c902  jz      short loc_14005C928
0x14005c904  cmp     byte ptr [rcx+29h], 5
0x14005c908  jb      short loc_14005C928
0x14005c90a  mov     rcx, [rcx+18h]
0x14005c90e  mov     r9, r14
0x14005c911  mov     [rsp+70h+var_38], rsi
0x14005c916  mov     [rsp+70h+Size], r13
0x14005c91b  mov     dword ptr [rsp+70h+var_48], eax
0x14005c91f  mov     dword ptr [rsp+70h+var_50], edx
0x14005c923  call    WPP_SF_qDDqq
0x14005c928  xor     r9d, r9d
0x14005c92b  mov     rdx, rdi
0x14005c92e  mov     rcx, r15
0x14005c931  lea     r8d, [r9+28h]
0x14005c935  call    ValidateExtendedPropertyDataBufferLength
0x14005c93a  mov     ebx, eax
0x14005c93c  test    eax, eax
0x14005c93e  jns     short loc_14005C964
0x14005c940  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c947  cmp     rcx, r12
0x14005c94a  jz      loc_14005CC85
0x14005c950  cmp     byte ptr [rcx+29h], 2
0x14005c954  jb      loc_14005CC5B
0x14005c95a  mov     edx, 0ABh
0x14005c95f  jmp     loc_14005CC4B
0x14005c964  cmp     dword ptr [rdi], 1
0x14005c967  lea     r9, [rdi+8]
0x14005c96b  mov     ebx, 0C000000Dh
0x14005c970  jnz     loc_14005CBC7
0x14005c976  cmp     [r9], r8d
0x14005c979  jb      loc_14005CBC7
0x14005c97f  mov     rax, [r14]
0x14005c982  mov     ecx, [rdi+4]
0x14005c985  cmp     ecx, [rax+20h]
0x14005c988  jnb     loc_14005CBC7
0x14005c98e  mov     rax, [rsi+2E8h]
0x14005c995  imul    rcx, 88h
0x14005c99c  cmp     dword ptr [rcx+rax+78h], 0
0x14005c9a1  jnz     loc_14005CB9A
0x14005c9a7  mov     rdx, [rcx+rax+80h]
0x14005c9af  test    rdx, rdx
0x14005c9b2  jz      loc_14005CB9A
0x14005c9b8  mov     r12b, [rdx+2]
0x14005c9bc  lea     rax, [rbp+var_18]
0x14005c9c0  mov     rdx, [rsi+3E8h]
0x14005c9c7  mov     r9b, r12b; unsigned __int8
0x14005c9ca  movzx   r8d, word ptr [rsi+4D4h]; unsigned __int64
0x14005c9d2  mov     rcx, rsi; struct _HW_DEVICE_EXTENSION *
0x14005c9d5  add     rdx, r8; struct _MSXU_PAYLOAD_FACEAUTH *
0x14005c9d8  mov     [rbp+var_18], 0
0x14005c9e0  mov     [rsp+70h+var_50], rax; unsigned __int64 *
0x14005c9e5  call    ?GetFaceAuthFlags@@YAJPEAU_HW_DEVICE_EXTENSION@@PEAU_MSXU_PAYLOAD_FACEAUTH@@_KEPEA_K@Z; GetFaceAuthFlags(_HW_DEVICE_EXTENSION *,_MSXU_PAYLOAD_FACEAUTH *,unsigned __int64,uchar,unsigned __int64 *)
0x14005c9ea  mov     ebx, eax
0x14005c9ec  test    eax, eax
0x14005c9ee  js      loc_14005CB76
0x14005c9f4  mov     r9, [rdi+10h]
0x14005c9f8  mov     r10, [rbp+var_18]
0x14005c9fc  mov     rcx, r9; unsigned __int64
0x14005c9ff  mov     rdx, r10; unsigned __int64
0x14005ca02  call    ?ValidateFlagsFaceAuth@@YAJ_K0@Z; ValidateFlagsFaceAuth(unsigned __int64,unsigned __int64)
0x14005ca07  mov     ebx, eax
0x14005ca09  test    eax, eax
0x14005ca0b  js      loc_14005CB3D
0x14005ca11  xor     r10d, r10d
0x14005ca14  mov     r8, r9
0x14005ca17  mov     [rbp+var_18], r10
0x14005ca1b  mov     rdx, r9
0x14005ca1e  movzx   eax, byte ptr [rbp+var_18+2]
0x14005ca22  mov     byte ptr [rbp+var_18+1], r12b
0x14005ca26  lea     ebx, [r10+1]
0x14005ca2a  and     rdx, rbx
0x14005ca2d  mov     byte ptr [rbp+var_18], bl
0x14005ca30  cmovnz  eax, ebx
0x14005ca33  and     r8d, 2
0x14005ca37  mov     byte ptr [rbp+var_18+2], al
0x14005ca3a  mov     al, dl
0x14005ca3c  or      al, 2
0x14005ca3e  test    r8, r8
0x14005ca41  jz      short loc_14005CA46
0x14005ca43  mov     byte ptr [rbp+var_18+2], al
0x14005ca46  movzx   ecx, al
0x14005ca49  test    r8, r8
0x14005ca4c  movzx   eax, dl
0x14005ca4f  cmovz   ecx, eax
0x14005ca52  and     r9d, 4
0x14005ca56  mov     al, cl
0x14005ca58  or      al, 4
0x14005ca5a  test    r9, r9
0x14005ca5d  jz      short loc_14005CA62
0x14005ca5f  mov     byte ptr [rbp+var_18+2], al
0x14005ca62  movsd   xmm0, [rbp+var_18]
0x14005ca67  test    r9, r9
0x14005ca6a  movzx   edx, al
0x14005ca6d  movzx   eax, cl
0x14005ca70  cmovz   edx, eax
0x14005ca73  movsd   [rbp+var_18], xmm0
0x14005ca78  mov     [rbp+var_10], r10b
0x14005ca7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ca83  lea     r12, WPP_GLOBAL_Control
0x14005ca8a  cmp     rcx, r12
0x14005ca8d  jz      short loc_14005CAAE
0x14005ca8f  cmp     byte ptr [rcx+29h], 4
0x14005ca93  jb      short loc_14005CAAE
0x14005ca95  mov     rcx, [rcx+18h]
0x14005ca99  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005caa0  movzx   r9d, dl
0x14005caa4  mov     edx, 0ACh
0x14005caa9  call    WPP_SF_d
0x14005caae  mov     r9b, [rbp+var_20+1]; int
0x14005cab2  lea     rax, [rbp+var_18]
0x14005cab6  mov     [rsp+70h+var_30], rsi; __int64
0x14005cabb  mov     r8d, 600h; int
0x14005cac1  mov     [rsp+70h+var_38], r13; __int64
0x14005cac6  mov     dl, bl; int
0x14005cac8  mov     dword ptr [rsp+70h+Size], 9; Size
0x14005cad0  mov     cl, 21h ; '!'; int
0x14005cad2  mov     [rsp+70h+var_48], rax; void *
0x14005cad7  mov     al, [rbp+var_20]
0x14005cada  mov     byte ptr [rsp+70h+var_50], al; int
0x14005cade  mov     [rsi+470h], r14
0x14005cae5  mov     [rsi+514h], ebx
0x14005caeb  call    SubmitControlRequest
0x14005caf0  mov     ebx, eax
0x14005caf2  test    eax, eax
0x14005caf4  jns     short loc_14005CB30
0x14005caf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cafd  cmp     rcx, r12
0x14005cb00  jz      short loc_14005CB20
0x14005cb02  cmp     byte ptr [rcx+29h], 2
0x14005cb06  jb      short loc_14005CB20
0x14005cb08  mov     rcx, [rcx+18h]
0x14005cb0c  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005cb13  mov     edx, 0ADh
0x14005cb18  mov     r9d, eax
0x14005cb1b  call    WPP_SF_d
0x14005cb20  mov     qword ptr [rsi+470h], 0
0x14005cb2b  jmp     loc_14005CBFC
0x14005cb30  mov     qword ptr [r15+38h], 28h ; '('
0x14005cb38  jmp     loc_14005CBFC
0x14005cb3d  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb44  lea     r12, WPP_GLOBAL_Control
0x14005cb4b  cmp     rcx, r12
0x14005cb4e  jz      loc_14005CC85
0x14005cb54  cmp     byte ptr [rcx+29h], 2
0x14005cb58  jb      loc_14005CBFC
0x14005cb5e  mov     rcx, [rcx+18h]
0x14005cb62  mov     edx, 0AEh
0x14005cb67  mov     [rsp+70h+var_50], r10
0x14005cb6c  call    WPP_SF_ii
0x14005cb71  jmp     loc_14005CBFC
0x14005cb76  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb7d  lea     r12, WPP_GLOBAL_Control
0x14005cb84  cmp     rcx, r12
0x14005cb87  jz      loc_14005CC85
0x14005cb8d  cmp     byte ptr [rcx+29h], 2
0x14005cb91  jb      short loc_14005CBFC
0x14005cb93  mov     edx, 0AFh
0x14005cb98  jmp     short loc_14005CBB5
0x14005cb9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cba1  cmp     rcx, r12
0x14005cba4  jz      loc_14005CC85
0x14005cbaa  cmp     byte ptr [rcx+29h], 2
0x14005cbae  jb      short loc_14005CBFC
0x14005cbb0  mov     edx, 0B0h
0x14005cbb5  mov     rcx, [rcx+18h]
0x14005cbb9  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005cbc0  call    WPP_SF_
0x14005cbc5  jmp     short loc_14005CBFC
0x14005cbc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cbce  cmp     rcx, r12
0x14005cbd1  jz      loc_14005CC85
0x14005cbd7  cmp     byte ptr [rcx+29h], 2
0x14005cbdb  jb      short loc_14005CBFC
0x14005cbdd  mov     eax, [rdi+4]
0x14005cbe0  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005cbe7  mov     r9d, [r9]
0x14005cbea  mov     edx, 0B1h
0x14005cbef  mov     rcx, [rcx+18h]
0x14005cbf3  mov     dword ptr [rsp+70h+var_50], eax
0x14005cbf7  call    WPP_SF_dd
0x14005cbfc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc03  cmp     rcx, r12
0x14005cc06  jz      short loc_14005CC85
0x14005cc08  cmp     byte ptr [rcx+29h], 4
0x14005cc0c  jb      short loc_14005CC5B
0x14005cc0e  mov     rax, [rdi+18h]
0x14005cc12  mov     edx, 0B2h
0x14005cc17  mov     r9, [rdi+10h]
0x14005cc1b  mov     rcx, [rcx+18h]
0x14005cc1f  mov     dword ptr [rsp+70h+var_48], ebx
0x14005cc23  mov     [rsp+70h+var_50], rax
0x14005cc28  call    WPP_SF_iiD
0x14005cc2d  jmp     short loc_14005CC5B
0x14005cc2f  mov     ebx, 0C0000001h
0x14005cc34  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc3b  cmp     rcx, r12
0x14005cc3e  jz      short loc_14005CC85
0x14005cc40  cmp     byte ptr [rcx+29h], 2
0x14005cc44  jb      short loc_14005CC5B
0x14005cc46  mov     edx, 0AAh
0x14005cc4b  mov     rcx, [rcx+18h]
0x14005cc4f  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005cc56  call    WPP_SF_
0x14005cc5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cc62  cmp     rcx, r12
0x14005cc65  jz      short loc_14005CC85
0x14005cc67  cmp     byte ptr [rcx+29h], 4
0x14005cc6b  jb      short loc_14005CC85
0x14005cc6d  mov     rcx, [rcx+18h]
0x14005cc71  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005cc78  mov     edx, 0B3h
0x14005cc7d  mov     r9d, ebx
0x14005cc80  call    WPP_SF_d
0x14005cc85  mov     [r15+30h], ebx
0x14005cc89  mov     eax, ebx
0x14005cc8b  mov     rcx, [rbp+var_8]
0x14005cc8f  xor     rcx, rsp; StackCookie
0x14005cc92  call    __security_check_cookie
0x14005cc97  mov     rbx, [rsp+70h+arg_8]
0x14005cc9f  add     rsp, 70h
0x14005cca3  pop     r15
0x14005cca5  pop     r14
0x14005cca7  pop     r13
0x14005cca9  pop     r12
0x14005ccab  pop     rdi
0x14005ccac  pop     rsi
0x14005ccad  pop     rbp
0x14005ccae  retn
```

# MSXU_FaceAuthGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14005c1d0`
- end: `0x14005c58b`
- name: `?MSXU_FaceAuthGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `955`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140004bac`
- `0x1400051e4`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003b85c`
- `0x14003bb60`
- `0x140040e40`
- `0x14005c1d0`
- `0x14005c594`
- `0x14005c69c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005c4ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005c4ab`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005c34e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005c34e`
- `ks!KsGetFilterFromIrp` at `0x14005c21e`
- `ks!KsGetFilterFromIrp` at `0x14005c21e`

## pseudocode

```c
__int64 __fastcall MSXU_FaceAuthGet(PIRP Irp, struct KSIDENTIFIER *a2, char *a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  PKSFILTER v8; // r14
  __int64 v9; // rsi
  __int64 v10; // r13
  int v11; // r12d
  NTSTATUS FaceAuthFlags; // ebx
  unsigned int v13; // r8d
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  unsigned int *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  SIZE_T v20; // r14
  unsigned __int8 *PoolWithTag; // rax
  unsigned __int8 *v22; // r15
  int v24; // [rsp+20h] [rbp-68h]
  size_t Size; // [rsp+30h] [rbp-58h]
  unsigned __int8 v26; // [rsp+90h] [rbp+8h]
  unsigned __int8 v27; // [rsp+90h] [rbp+8h]
  __int64 v28; // [rsp+A8h] [rbp+20h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  v8 = FilterFromIrp;
  if ( !FilterFromIrp )
  {
    FaceAuthFlags = -1073741823;
    goto LABEL_43;
  }
  v9 = *(_QWORD *)FilterFromIrp->Context;
  v10 = *(_QWORD *)(v9 + 880);
  v26 = *(_BYTE *)(v10 + 40);
  v11 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 32) + 3LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDDqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      FilterFromIrp,
      v11,
      *(unsigned __int8 *)(v10 + 40),
      v10,
      v9);
  FaceAuthFlags = ValidateExtendedPropertyDataBufferLength(Irp, a3, 40);
  if ( FaceAuthFlags >= 0 )
  {
    v16 = (unsigned int *)(a3 + 8);
    FaceAuthFlags = -1073741811;
    if ( *(_DWORD *)a3 != 1
      || *v16 < v13
      || (v17 = *((unsigned int *)a3 + 1), (unsigned int)v17 >= v8->Descriptor->PinDescriptorsCount) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          167,
          WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
          *v16,
          *((_DWORD *)a3 + 1));
      goto LABEL_43;
    }
    v18 = *(_QWORD *)(v9 + 744);
    v19 = 136 * v17;
    if ( *(_DWORD *)(v19 + v18 + 120) || !*(_QWORD *)(v19 + v18 + 128) )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_43;
      v15 = 166;
    }
    else
    {
      v20 = *(unsigned __int16 *)(v9 + 1236);
      v28 = *(_QWORD *)(v9 + 1000);
      PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)1536, v20, 0x56425355u);
      v22 = PoolWithTag;
      if ( PoolWithTag )
      {
        if ( !ExPoolZeroingNativelySupported )
          memset(PoolWithTag, 0, (unsigned int)v20);
        LODWORD(Size) = v20;
        LOBYTE(v24) = v26;
        FaceAuthFlags = SubmitControlRequest(0xA1u, 0x81u, 0x600u, v11, v24, v22, Size, v10, v9);
        if ( FaceAuthFlags < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
        }
        else
        {
          v27 = *(_BYTE *)(*(_QWORD *)(136LL * *((unsigned int *)a3 + 1) + *(_QWORD *)(v9 + 744) + 128) + 2LL);
          FaceAuthFlags = GetFaceAuthFlags(
                            (struct _HW_DEVICE_EXTENSION *)v9,
                            (struct _MSXU_PAYLOAD_FACEAUTH *)v22,
                            v20,
                            v27,
                            (unsigned __int64 *)a3 + 2);
          if ( FaceAuthFlags >= 0 )
          {
            FaceAuthFlags = GetFaceAuthFlags(
                              (struct _HW_DEVICE_EXTENSION *)v9,
                              (struct _MSXU_PAYLOAD_FACEAUTH *)(v20 + v28),
                              v20,
                              v27,
                              (unsigned __int64 *)a3 + 3);
            if ( FaceAuthFlags >= 0 )
            {
              FaceAuthFlags = ValidateFlagsFaceAuth(*((_QWORD *)a3 + 2), *((_QWORD *)a3 + 3));
              if ( FaceAuthFlags >= 0 )
                Irp->IoStatus.Information = 40;
            }
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 163);
        }
        ExFreePoolWithTag(v22, 0x56425355u);
        goto LABEL_43;
      }
      FaceAuthFlags = -1073741670;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_46;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_43;
      v15 = 165;
    }
    goto LABEL_12;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_46;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v15 = v13 + 122;
LABEL_12:
    WPP_SF_(v14->AttachedDevice, v15, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_43:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      168,
      WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids,
      (unsigned int)FaceAuthFlags);
LABEL_46:
  Irp->IoStatus.Status = FaceAuthFlags;
  return (unsigned int)FaceAuthFlags;
}

```

## disassembly

```asm
0x14005c1d0  mov     [rsp+arg_8], rbx
0x14005c1d5  push    rbp
0x14005c1d6  push    rsi
0x14005c1d7  push    rdi
0x14005c1d8  push    r12
0x14005c1da  push    r13
0x14005c1dc  push    r14
0x14005c1de  push    r15
0x14005c1e0  sub     rsp, 50h
0x14005c1e4  mov     rdi, r8
0x14005c1e7  mov     rbp, rcx
0x14005c1ea  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c1f1  lea     r15, WPP_GLOBAL_Control
0x14005c1f8  cmp     rcx, r15
0x14005c1fb  jz      short loc_14005C21B
0x14005c1fd  cmp     byte ptr [rcx+29h], 2
0x14005c201  jb      short loc_14005C21B
0x14005c203  mov     rcx, [rcx+18h]
0x14005c207  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c20e  mov     edx, 0A1h
0x14005c213  mov     r9, rbp
0x14005c216  call    WPP_SF_q
0x14005c21b  mov     rcx, rbp; Irp
0x14005c21e  call    cs:__imp_KsGetFilterFromIrp
0x14005c225  nop     dword ptr [rax+rax+00h]
0x14005c22a  mov     r14, rax
0x14005c22d  test    rax, rax
0x14005c230  jz      loc_14005C53E
0x14005c236  mov     rcx, [rax+10h]
0x14005c23a  mov     rsi, [rcx]
0x14005c23d  mov     r13, [rsi+370h]
0x14005c244  mov     rcx, [r13+20h]
0x14005c248  movzx   eax, byte ptr [r13+28h]
0x14005c24d  mov     [rsp+88h+arg_0], al
0x14005c254  movzx   r12d, byte ptr [rcx+3]
0x14005c259  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c260  cmp     rcx, r15
0x14005c263  jz      short loc_14005C28A
0x14005c265  cmp     byte ptr [rcx+29h], 5
0x14005c269  jb      short loc_14005C28A
0x14005c26b  mov     rcx, [rcx+18h]
0x14005c26f  mov     r9, r14
0x14005c272  mov     [rsp+88h+var_50], rsi
0x14005c277  mov     [rsp+88h+Size], r13
0x14005c27c  mov     dword ptr [rsp+88h+var_60], eax
0x14005c280  mov     dword ptr [rsp+88h+var_68], r12d
0x14005c285  call    WPP_SF_qDDqq
0x14005c28a  xor     r9d, r9d
0x14005c28d  mov     rdx, rdi
0x14005c290  mov     rcx, rbp
0x14005c293  lea     r8d, [r9+28h]
0x14005c297  call    ValidateExtendedPropertyDataBufferLength
0x14005c29c  mov     ebx, eax
0x14005c29e  test    eax, eax
0x14005c2a0  jns     short loc_14005C2D5
0x14005c2a2  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c2a9  cmp     rcx, r15
0x14005c2ac  jz      loc_14005C56D
0x14005c2b2  cmp     byte ptr [rcx+29h], 2
0x14005c2b6  jb      loc_14005C543
0x14005c2bc  lea     edx, [r8+7Ah]
0x14005c2c0  mov     rcx, [rcx+18h]
0x14005c2c4  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c2cb  call    WPP_SF_
0x14005c2d0  jmp     loc_14005C543
0x14005c2d5  cmp     dword ptr [rdi], 1
0x14005c2d8  lea     r9, [rdi+8]
0x14005c2dc  mov     ebx, 0C000000Dh
0x14005c2e1  jnz     loc_14005C50B
0x14005c2e7  cmp     [r9], r8d
0x14005c2ea  jb      loc_14005C50B
0x14005c2f0  mov     rax, [r14]
0x14005c2f3  mov     ecx, [rdi+4]
0x14005c2f6  cmp     ecx, [rax+20h]
0x14005c2f9  jnb     loc_14005C50B
0x14005c2ff  mov     rax, [rsi+2E8h]
0x14005c306  imul    rcx, 88h
0x14005c30d  cmp     dword ptr [rcx+rax+78h], 0
0x14005c312  jnz     loc_14005C4EF
0x14005c318  cmp     qword ptr [rcx+rax+80h], 0
0x14005c321  jz      loc_14005C4EF
0x14005c327  movzx   r14d, word ptr [rsi+4D4h]
0x14005c32f  mov     ebx, 600h
0x14005c334  mov     rax, [rsi+3E8h]
0x14005c33b  mov     edx, r14d; NumberOfBytes
0x14005c33e  mov     ecx, ebx; PoolType
0x14005c340  mov     [rsp+88h+arg_18], rax
0x14005c348  mov     r8d, 56425355h; Tag
0x14005c34e  call    cs:__imp_ExAllocatePoolWithTag
0x14005c355  nop     dword ptr [rax+rax+00h]
0x14005c35a  mov     r15, rax
0x14005c35d  test    rax, rax
0x14005c360  jz      loc_14005C4C3
0x14005c366  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14005c36d  jnz     short loc_14005C37C
0x14005c36f  mov     r8d, r14d; Size
0x14005c372  xor     edx, edx; Val
0x14005c374  mov     rcx, rax; void *
0x14005c377  call    memset
0x14005c37c  mov     al, [rsp+88h+arg_0]
0x14005c383  mov     r8d, ebx; int
0x14005c386  mov     [rsp+88h+var_48], rsi; __int64
0x14005c38b  mov     r9b, r12b; int
0x14005c38e  mov     [rsp+88h+var_50], r13; __int64
0x14005c393  mov     dl, 81h; int
0x14005c395  mov     dword ptr [rsp+88h+Size], r14d; Size
0x14005c39a  mov     cl, 0A1h; int
0x14005c39c  mov     [rsp+88h+var_60], r15; void *
0x14005c3a1  mov     byte ptr [rsp+88h+var_68], al; int
0x14005c3a5  call    SubmitControlRequest
0x14005c3aa  mov     ebx, eax
0x14005c3ac  test    eax, eax
0x14005c3ae  js      loc_14005C475
0x14005c3b4  mov     eax, [rdi+4]
0x14005c3b7  lea     r12, [rdi+10h]
0x14005c3bb  imul    rcx, rax, 88h
0x14005c3c2  mov     rax, [rsi+2E8h]
0x14005c3c9  mov     r8, r14; unsigned __int64
0x14005c3cc  mov     rdx, r15; struct _MSXU_PAYLOAD_FACEAUTH *
0x14005c3cf  mov     [rsp+88h+var_68], r12; unsigned __int64 *
0x14005c3d4  mov     rcx, [rcx+rax+80h]
0x14005c3dc  mov     al, [rcx+2]
0x14005c3df  mov     rcx, rsi; struct _HW_DEVICE_EXTENSION *
0x14005c3e2  mov     r9b, al; unsigned __int8
0x14005c3e5  mov     [rsp+88h+arg_0], al
0x14005c3ec  call    ?GetFaceAuthFlags@@YAJPEAU_HW_DEVICE_EXTENSION@@PEAU_MSXU_PAYLOAD_FACEAUTH@@_KEPEA_K@Z; GetFaceAuthFlags(_HW_DEVICE_EXTENSION *,_MSXU_PAYLOAD_FACEAUTH *,unsigned __int64,uchar,unsigned __int64 *)
0x14005c3f1  mov     ebx, eax
0x14005c3f3  test    eax, eax
0x14005c3f5  js      short loc_14005C43F
0x14005c3f7  mov     rdx, [rsp+88h+arg_18]
0x14005c3ff  lea     r13, [rdi+18h]
0x14005c403  mov     r9b, [rsp+88h+arg_0]; unsigned __int8
0x14005c40b  add     rdx, r14; struct _MSXU_PAYLOAD_FACEAUTH *
0x14005c40e  mov     r8, r14; unsigned __int64
0x14005c411  mov     [rsp+88h+var_68], r13; unsigned __int64 *
0x14005c416  mov     rcx, rsi; struct _HW_DEVICE_EXTENSION *
0x14005c419  call    ?GetFaceAuthFlags@@YAJPEAU_HW_DEVICE_EXTENSION@@PEAU_MSXU_PAYLOAD_FACEAUTH@@_KEPEA_K@Z; GetFaceAuthFlags(_HW_DEVICE_EXTENSION *,_MSXU_PAYLOAD_FACEAUTH *,unsigned __int64,uchar,unsigned __int64 *)
0x14005c41e  mov     ebx, eax
0x14005c420  test    eax, eax
0x14005c422  js      short loc_14005C43F
0x14005c424  mov     rdx, [r13+0]; unsigned __int64
0x14005c428  mov     rcx, [r12]; unsigned __int64
0x14005c42c  call    ?ValidateFlagsFaceAuth@@YAJ_K0@Z; ValidateFlagsFaceAuth(unsigned __int64,unsigned __int64)
0x14005c431  mov     ebx, eax
0x14005c433  test    eax, eax
0x14005c435  js      short loc_14005C43F
0x14005c437  mov     qword ptr [rbp+38h], 28h ; '('
0x14005c43f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c446  lea     rax, WPP_GLOBAL_Control
0x14005c44d  cmp     rcx, rax
0x14005c450  jz      short loc_14005C4A3
0x14005c452  cmp     byte ptr [rcx+29h], 4
0x14005c456  jb      short loc_14005C4A3
0x14005c458  mov     rax, [rdi+18h]
0x14005c45c  mov     edx, 0A3h
0x14005c461  mov     r9, [r12]
0x14005c465  mov     rcx, [rcx+18h]
0x14005c469  mov     [rsp+88h+var_68], rax
0x14005c46e  call    WPP_SF_ii
0x14005c473  jmp     short loc_14005C4A3
0x14005c475  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c47c  lea     rax, WPP_GLOBAL_Control
0x14005c483  cmp     rcx, rax
0x14005c486  jz      short loc_14005C4A3
0x14005c488  cmp     byte ptr [rcx+29h], 2
0x14005c48c  jb      short loc_14005C4A3
0x14005c48e  mov     rcx, [rcx+18h]
0x14005c492  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c499  mov     edx, 0A4h
0x14005c49e  call    WPP_SF_
0x14005c4a3  mov     edx, 56425355h; Tag
0x14005c4a8  mov     rcx, r15; P
0x14005c4ab  call    cs:__imp_ExFreePoolWithTag
0x14005c4b2  nop     dword ptr [rax+rax+00h]
0x14005c4b7  lea     r15, WPP_GLOBAL_Control
0x14005c4be  jmp     loc_14005C543
0x14005c4c3  mov     ebx, 0C000009Ah
0x14005c4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c4cf  lea     r15, WPP_GLOBAL_Control
0x14005c4d6  cmp     rcx, r15
0x14005c4d9  jz      loc_14005C56D
0x14005c4df  cmp     byte ptr [rcx+29h], 2
0x14005c4e3  jb      short loc_14005C543
0x14005c4e5  mov     edx, 0A5h
0x14005c4ea  jmp     loc_14005C2C0
0x14005c4ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c4f6  cmp     rcx, r15
0x14005c4f9  jz      short loc_14005C56D
0x14005c4fb  cmp     byte ptr [rcx+29h], 2
0x14005c4ff  jb      short loc_14005C543
0x14005c501  mov     edx, 0A6h
0x14005c506  jmp     loc_14005C2C0
0x14005c50b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c512  cmp     rcx, r15
0x14005c515  jz      short loc_14005C56D
0x14005c517  cmp     byte ptr [rcx+29h], 2
0x14005c51b  jb      short loc_14005C543
0x14005c51d  mov     eax, [rdi+4]
0x14005c520  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c527  mov     r9d, [r9]
0x14005c52a  mov     edx, 0A7h
0x14005c52f  mov     rcx, [rcx+18h]
0x14005c533  mov     dword ptr [rsp+88h+var_68], eax
0x14005c537  call    WPP_SF_dd
0x14005c53c  jmp     short loc_14005C543
0x14005c53e  mov     ebx, 0C0000001h
0x14005c543  mov     rcx, cs:WPP_GLOBAL_Control
0x14005c54a  cmp     rcx, r15
0x14005c54d  jz      short loc_14005C56D
0x14005c54f  cmp     byte ptr [rcx+29h], 4
0x14005c553  jb      short loc_14005C56D
0x14005c555  mov     rcx, [rcx+18h]
0x14005c559  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005c560  mov     edx, 0A8h
0x14005c565  mov     r9d, ebx
0x14005c568  call    WPP_SF_d
0x14005c56d  mov     [rbp+30h], ebx
0x14005c570  mov     eax, ebx
0x14005c572  mov     rbx, [rsp+88h+arg_8]
0x14005c57a  add     rsp, 50h
0x14005c57e  pop     r15
0x14005c580  pop     r14
0x14005c582  pop     r13
0x14005c584  pop     r12
0x14005c586  pop     rdi
0x14005c587  pop     rsi
0x14005c588  pop     rbp
0x14005c589  retn
```

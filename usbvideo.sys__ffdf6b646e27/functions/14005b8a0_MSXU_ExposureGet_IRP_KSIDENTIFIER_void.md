# MSXU_ExposureGet(_IRP *,KSIDENTIFIER *,void *)

- ea: `0x14005b8a0`
- end: `0x14005bc72`
- name: `?MSXU_ExposureGet@@YAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAX@Z`
- size: `978`
- prototype: `__int64 __fastcall(PIRP Irp, struct KSIDENTIFIER *, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation`

## callees

- `0x140004bac`
- `0x140008640`
- `0x14000de14`
- `0x14001b118`
- `0x14001b15c`
- `0x14003bb60`
- `0x14003bc58`
- `0x140040a30`
- `0x14005b8a0`
- `0x14005bc78`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x14005b8f2`
- `ks!KsGetFilterFromIrp` at `0x14005b8f2`

## pseudocode

```c
__int64 __fastcall MSXU_ExposureGet(PIRP Irp, struct KSIDENTIFIER *a2, char *a3)
{
  PKSFILTER FilterFromIrp; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r14
  __int64 v9; // rbp
  int v10; // r13d
  int v11; // r12d
  NTSTATUS v12; // ebx
  unsigned int v13; // r8d
  __int64 v14; // r15
  PDEVICE_OBJECT v15; // rcx
  __int64 v17; // rdx
  unsigned __int8 v18; // dl
  unsigned __int64 ExtPropFlags; // rax
  __int64 v20; // r10
  __int64 v21; // r11
  ULONG_PTR v22; // r12
  unsigned __int64 v23; // rbp
  unsigned __int64 v24; // rax
  __int64 v25; // r10
  __int64 v26; // rdx
  __int64 v27; // r8
  int v28; // r9d
  int v29; // [rsp+20h] [rbp-C8h]
  size_t Size; // [rsp+30h] [rbp-B8h]
  _OWORD v31[2]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v32[15]; // [rsp+90h] [rbp-58h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, Irp);
  FilterFromIrp = KsGetFilterFromIrp(Irp);
  if ( !FilterFromIrp )
  {
    v12 = -1073741823;
    goto LABEL_25;
  }
  v8 = *(_QWORD *)FilterFromIrp->Context;
  v9 = *(_QWORD *)(v8 + 880);
  v10 = *(unsigned __int8 *)(v9 + 40);
  v11 = *(unsigned __int8 *)(*(_QWORD *)(v9 + 32) + 3LL);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_qDDqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      FilterFromIrp,
      v11,
      v10,
      v9,
      *(_QWORD *)FilterFromIrp->Context);
  v12 = ValidateExtendedPropertyDataBufferLength(Irp, a3, 64);
  if ( v12 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_14;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_25;
    v17 = 74;
    goto LABEL_18;
  }
  if ( *(_DWORD *)a3 != 1 || *((_DWORD *)a3 + 2) < v13 || *((_DWORD *)a3 + 1) != -1 )
  {
    v15 = WPP_GLOBAL_Control;
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_14;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      goto LABEL_25;
    v17 = 78;
    goto LABEL_18;
  }
  v14 = *(_QWORD *)(v8 + 968);
  LODWORD(Size) = 15;
  *(_QWORD *)v32 = *(_QWORD *)(v14 + 30);
  *(_DWORD *)&v32[8] = *(_DWORD *)(v14 + 38);
  *(_WORD *)&v32[12] = *(_WORD *)(v14 + 42);
  v32[14] = *(_BYTE *)(v14 + 44);
  LOBYTE(v29) = v10;
  v12 = SubmitControlRequest(0xA1u, 0x81u, 0x200u, v11, v29, v32, Size, v9, v8);
  if ( v12 >= 0 )
  {
    v18 = v32[0];
    if ( (v32[0] & 7) != v32[0] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, v32[0]);
        v18 = v32[0];
      }
      v12 = -1073741436;
    }
    if ( v12 >= 0 )
    {
      ExtPropFlags = GetExtPropFlags(v18);
      v20 = *(_QWORD *)&v32[7];
      v22 = (unsigned int)(v21 + 64);
      *((_QWORD *)a3 + 2) = ExtPropFlags;
      memset(v31, 0, 24);
      v23 = ExtPropFlags;
      *(_DWORD *)a3 = 1;
      *((_QWORD *)a3 + 4) = 0;
      *(_OWORD *)(a3 + 40) = *(_OWORD *)((char *)v31 + 8);
      *((_DWORD *)a3 + 1) = -1;
      *((_QWORD *)a3 + 7) = *(_OWORD *)&_mm_unpackhi_pd((__m128d)0LL, (__m128d)0LL);
      *((_QWORD *)a3 + 6) = v20;
      *((_QWORD *)a3 + 1) = v22;
      *((_QWORD *)a3 + 3) = v21;
      v24 = GetExtPropFlags(*(unsigned __int8 *)(v14 + 15)) | 0x8000000000000000uLL;
      *((_QWORD *)a3 + 3) = v24;
      v26 = *(unsigned int *)(v14 + 7);
      *((_DWORD *)a3 + 9) = v26;
      v27 = *(unsigned int *)(v14 + 22);
      *((_DWORD *)a3 + 10) = v27;
      v28 = *(_DWORD *)(v14 + 52);
      *((_DWORD *)a3 + 11) = v28;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_qiiiDDD(WPP_GLOBAL_Control->AttachedDevice, v26, v27, Irp, v25, v23, v24, v26, v27, v28);
      Irp->IoStatus.Information = v22;
      goto LABEL_25;
    }
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_14;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v17 = 77;
LABEL_18:
    WPP_SF_(v15->AttachedDevice, v17, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids);
  }
LABEL_25:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids, (unsigned int)v12);
LABEL_14:
  Irp->IoStatus.Status = v12;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005b8a0  mov     [rsp+arg_8], rbx
0x14005b8a5  push    rbp
0x14005b8a6  push    rsi
0x14005b8a7  push    rdi
0x14005b8a8  push    r12
0x14005b8aa  push    r13
0x14005b8ac  push    r14
0x14005b8ae  push    r15
0x14005b8b0  sub     rsp, 0B0h
0x14005b8b7  mov     rax, cs:__security_cookie
0x14005b8be  xor     rax, rsp
0x14005b8c1  mov     [rsp+0E8h+var_48], rax
0x14005b8c9  mov     rsi, r8
0x14005b8cc  mov     rdi, rcx
0x14005b8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b8d6  lea     rbx, WPP_GLOBAL_Control
0x14005b8dd  mov     r15b, 2
0x14005b8e0  cmp     rcx, rbx
0x14005b8e3  jz      short loc_14005B8EF
0x14005b8e5  cmp     [rcx+29h], r15b
0x14005b8e9  jnb     loc_14005BB84
0x14005b8ef  mov     rcx, rdi; Irp
0x14005b8f2  call    cs:__imp_KsGetFilterFromIrp
0x14005b8f9  nop     dword ptr [rax+rax+00h]
0x14005b8fe  mov     r9, rax
0x14005b901  test    rax, rax
0x14005b904  jz      loc_14005BB76
0x14005b90a  mov     rcx, [rax+10h]
0x14005b90e  mov     r14, [rcx]
0x14005b911  mov     rbp, [r14+370h]
0x14005b918  mov     rcx, [rbp+20h]
0x14005b91c  movzx   r13d, byte ptr [rbp+28h]
0x14005b921  movzx   r12d, byte ptr [rcx+3]
0x14005b926  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b92d  cmp     rcx, rbx
0x14005b930  jz      short loc_14005B93C
0x14005b932  cmp     byte ptr [rcx+29h], 5
0x14005b936  jnb     loc_14005BBA1
0x14005b93c  xor     r9d, r9d
0x14005b93f  mov     rdx, rsi
0x14005b942  mov     rcx, rdi
0x14005b945  lea     r8d, [r9+40h]
0x14005b949  call    ValidateExtendedPropertyDataBufferLength
0x14005b94e  mov     ebx, eax
0x14005b950  test    eax, eax
0x14005b952  js      loc_14005BBC3
0x14005b958  cmp     dword ptr [rsi], 1
0x14005b95b  jnz     loc_14005BA36
0x14005b961  cmp     [rsi+8], r8d
0x14005b965  jb      loc_14005BA36
0x14005b96b  cmp     dword ptr [rsi+4], 0FFFFFFFFh
0x14005b96f  jnz     loc_14005BA36
0x14005b975  mov     r15, [r14+3C8h]
0x14005b97c  mov     r8d, 200h; int
0x14005b982  mov     [rsp+0E8h+var_A8], r14; __int64
0x14005b987  mov     r9b, r12b; int
0x14005b98a  mov     [rsp+0E8h+var_B0], rbp; __int64
0x14005b98f  mov     dl, 81h; int
0x14005b991  mov     dword ptr [rsp+0E8h+Size], 0Fh; Size
0x14005b999  mov     cl, 0A1h; int
0x14005b99b  movsd   xmm0, qword ptr [r15+1Eh]
0x14005b9a1  movsd   [rsp+0E8h+var_58], xmm0
0x14005b9aa  mov     eax, [r15+26h]
0x14005b9ae  mov     [rsp+0E8h+var_50], eax
0x14005b9b5  movzx   eax, word ptr [r15+2Ah]
0x14005b9ba  mov     [rsp+0E8h+var_4C], ax
0x14005b9c2  mov     al, [r15+2Ch]
0x14005b9c6  mov     [rsp+0E8h+var_4A], al
0x14005b9cd  lea     rax, [rsp+0E8h+var_58]
0x14005b9d5  mov     [rsp+0E8h+var_C0], rax; void *
0x14005b9da  mov     byte ptr [rsp+0E8h+var_C8], r13b; int
0x14005b9df  call    SubmitControlRequest
0x14005b9e4  mov     ebx, eax
0x14005b9e6  test    eax, eax
0x14005b9e8  jns     loc_14005BA72
0x14005b9ee  lea     r14, WPP_GLOBAL_Control
0x14005b9f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b9fc  cmp     rcx, r14
0x14005b9ff  jnz     loc_14005BC5E
0x14005ba05  mov     [rdi+30h], ebx
0x14005ba08  mov     eax, ebx
0x14005ba0a  mov     rcx, [rsp+0E8h+var_48]
0x14005ba12  xor     rcx, rsp; StackCookie
0x14005ba15  call    __security_check_cookie
0x14005ba1a  mov     rbx, [rsp+0E8h+arg_8]
0x14005ba22  add     rsp, 0B0h
0x14005ba29  pop     r15
0x14005ba2b  pop     r14
0x14005ba2d  pop     r13
0x14005ba2f  pop     r12
0x14005ba31  pop     rdi
0x14005ba32  pop     rsi
0x14005ba33  pop     rbp
0x14005ba34  retn
0x14005ba36  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ba3d  lea     r14, WPP_GLOBAL_Control
0x14005ba44  mov     ebx, 0C000000Dh
0x14005ba49  cmp     rcx, r14
0x14005ba4c  jz      short loc_14005BA05
0x14005ba4e  cmp     [rcx+29h], r15b
0x14005ba52  jb      loc_14005BB3F
0x14005ba58  mov     edx, 4Eh ; 'N'
0x14005ba5d  mov     rcx, [rcx+18h]
0x14005ba61  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005ba68  call    WPP_SF_
0x14005ba6d  jmp     loc_14005BB3F
0x14005ba72  movzx   edx, byte ptr [rsp+0E8h+var_58]
0x14005ba7a  mov     al, dl
0x14005ba7c  and     al, 7
0x14005ba7e  cmp     al, dl
0x14005ba80  jnz     loc_14005BBEE
0x14005ba86  lea     r14, WPP_GLOBAL_Control
0x14005ba8d  test    ebx, ebx
0x14005ba8f  js      loc_14005B9F5
0x14005ba95  movzx   ecx, dl; unsigned int
0x14005ba98  xor     r11d, r11d
0x14005ba9b  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x14005baa0  mov     r10, [rsp+0E8h+var_58+7]
0x14005baa8  lea     r12d, [r11+40h]
0x14005baac  xorps   xmm1, xmm1
0x14005baaf  mov     [rsi+10h], rax
0x14005bab3  movaps  [rsp+0E8h+var_78], xmm1
0x14005bab8  mov     rbp, rax
0x14005babb  movaps  [rsp+0E8h+var_68], xmm1
0x14005bac3  movups  xmm0, [rsp+0E8h+var_78+8]
0x14005bac8  mov     dword ptr [rsi], 1
0x14005bace  movsd   qword ptr [rsi+20h], xmm1
0x14005bad3  movups  xmmword ptr [rsi+28h], xmm0
0x14005bad7  mov     dword ptr [rsi+4], 0FFFFFFFFh
0x14005bade  unpckhpd xmm1, xmm1
0x14005bae2  movsd   qword ptr [rsi+38h], xmm1
0x14005bae7  mov     [rsi+30h], r10
0x14005baeb  mov     [rsi+8], r12
0x14005baef  mov     [rsi+18h], r11
0x14005baf3  movzx   ecx, byte ptr [r15+0Fh]; unsigned int
0x14005baf8  call    ?GetExtPropFlags@@YA_KK@Z; GetExtPropFlags(ulong)
0x14005bafd  mov     rcx, 8000000000000000h
0x14005bb07  or      rax, rcx
0x14005bb0a  mov     [rsi+18h], rax
0x14005bb0e  mov     edx, [r15+7]
0x14005bb12  mov     [rsi+24h], edx
0x14005bb15  mov     r8d, [r15+16h]
0x14005bb19  mov     [rsi+28h], r8d
0x14005bb1d  mov     r9d, [r15+34h]
0x14005bb21  mov     [rsi+2Ch], r9d
0x14005bb25  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb2c  cmp     rcx, r14
0x14005bb2f  jz      short loc_14005BB3B
0x14005bb31  cmp     byte ptr [rcx+29h], 4
0x14005bb35  jnb     loc_14005BC30
0x14005bb3b  mov     [rdi+38h], r12
0x14005bb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bb46  cmp     rcx, r14
0x14005bb49  jz      loc_14005BA05
0x14005bb4f  cmp     byte ptr [rcx+29h], 4
0x14005bb53  jb      loc_14005BA05
0x14005bb59  mov     rcx, [rcx+18h]
0x14005bb5d  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005bb64  mov     edx, 4Fh ; 'O'
0x14005bb69  mov     r9d, ebx
0x14005bb6c  call    WPP_SF_d
0x14005bb71  jmp     loc_14005BA05
0x14005bb76  mov     ebx, 0C0000001h
0x14005bb7b  lea     r14, WPP_GLOBAL_Control
0x14005bb82  jmp     short loc_14005BB3F
0x14005bb84  mov     rcx, [rcx+18h]
0x14005bb88  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005bb8f  mov     edx, 49h ; 'I'
0x14005bb94  mov     r9, rdi
0x14005bb97  call    WPP_SF_q
0x14005bb9c  jmp     loc_14005B8EF
0x14005bba1  mov     rcx, [rcx+18h]
0x14005bba5  mov     [rsp+0E8h+var_B0], r14
0x14005bbaa  mov     [rsp+0E8h+Size], rbp
0x14005bbaf  mov     dword ptr [rsp+0E8h+var_C0], r13d
0x14005bbb4  mov     [rsp+0E8h+var_C8], r12d
0x14005bbb9  call    WPP_SF_qDDqq
0x14005bbbe  jmp     loc_14005B93C
0x14005bbc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bbca  lea     r14, WPP_GLOBAL_Control
0x14005bbd1  cmp     rcx, r14
0x14005bbd4  jz      loc_14005BA05
0x14005bbda  cmp     [rcx+29h], r15b
0x14005bbde  jb      loc_14005BB3F
0x14005bbe4  mov     edx, 4Ah ; 'J'
0x14005bbe9  jmp     loc_14005BA5D
0x14005bbee  mov     rcx, cs:WPP_GLOBAL_Control
0x14005bbf5  lea     r14, WPP_GLOBAL_Control
0x14005bbfc  cmp     rcx, r14
0x14005bbff  jz      short loc_14005BC26
0x14005bc01  cmp     byte ptr [rcx+29h], 2
0x14005bc05  jb      short loc_14005BC26
0x14005bc07  mov     rcx, [rcx+18h]
0x14005bc0b  lea     r8, WPP_d1b3f081bb3735146c257614f5c02eb2_Traceguids
0x14005bc12  mov     r9d, edx
0x14005bc15  mov     edx, 4Bh ; 'K'
0x14005bc1a  call    WPP_SF_d
0x14005bc1f  mov     dl, byte ptr [rsp+0E8h+var_58]
0x14005bc26  mov     ebx, 0C0000184h
0x14005bc2b  jmp     loc_14005BA8D
0x14005bc30  mov     rcx, [rcx+18h]
0x14005bc34  mov     [rsp+0E8h+var_A0], r9d
0x14005bc39  mov     r9, rdi
0x14005bc3c  mov     dword ptr [rsp+0E8h+var_A8], r8d
0x14005bc41  mov     dword ptr [rsp+0E8h+var_B0], edx
0x14005bc45  mov     [rsp+0E8h+Size], rax
0x14005bc4a  mov     [rsp+0E8h+var_C0], rbp
0x14005bc4f  mov     qword ptr [rsp+0E8h+var_C8], r10
0x14005bc54  call    WPP_SF_qiiiDDD
0x14005bc59  jmp     loc_14005BB3B
0x14005bc5e  cmp     byte ptr [rcx+29h], 2
0x14005bc62  jb      loc_14005BB3F
0x14005bc68  mov     edx, 4Dh ; 'M'
0x14005bc6d  jmp     loc_14005BA5D
```

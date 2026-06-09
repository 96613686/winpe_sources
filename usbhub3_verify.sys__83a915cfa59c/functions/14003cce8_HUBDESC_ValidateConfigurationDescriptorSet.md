# HUBDESC_ValidateConfigurationDescriptorSet

- ea: `0x14003cce8`
- end: `0x14003d157`
- name: `HUBDESC_ValidateConfigurationDescriptorSet`
- size: `1135`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400063b4`
- `0x14001b804`
- `0x14002c2dc`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x14000c578`
- `0x140035e1c`
- `0x1400360bc`
- `0x140036c84`
- `0x140038124`
- `0x140038450`
- `0x140038894`
- `0x140038fac`
- `0x14003a27c`
- `0x14003b5fc`
- `0x14003cce8`
- `0x140045530`
- `0x140045570`
- `0x140045940`

## import_xrefs

- `ntoskrnl!RtlClearAllBits` at `0x14003cd75`
- `ntoskrnl!RtlClearAllBits` at `0x14003cd85`
- `ntoskrnl!RtlClearAllBits` at `0x14003cd95`
- `ntoskrnl!RtlClearAllBits` at `0x14003cd75`
- `ntoskrnl!RtlClearAllBits` at `0x14003cd85`
- `ntoskrnl!RtlClearAllBits` at `0x14003cd95`

## pseudocode

```c
char __fastcall HUBDESC_ValidateConfigurationDescriptorSet(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  __int64 v6; // rdi
  __int64 v9; // xmm0_8
  __int128 v10; // xmm1
  __int16 v11; // ax
  __int128 v12; // xmm0
  __int64 *v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rdx
  char v16; // bl
  unsigned __int64 v17; // rbx
  char v18; // di
  __int64 v19; // rcx
  int v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v22[3]; // [rsp+44h] [rbp-BCh] BYREF
  struct _RTL_BITMAP v23[17]; // [rsp+50h] [rbp-B0h] BYREF

  v6 = a2;
  v21 = 0;
  v22[0] = 0;
  if ( a5 )
    *a5 = 0;
  memset(v23, 0, 0x108u);
  v23[13].Buffer = &v23[14].SizeOfBitMap;
  *(_QWORD *)&v23[6].SizeOfBitMap = &v23[6].Buffer;
  v23[13].SizeOfBitMap = 256;
  LODWORD(v23[5].Buffer) = 256;
  LODWORD(v23[8].Buffer) = 256;
  *(_QWORD *)&v23[9].SizeOfBitMap = &v23[9].Buffer;
  RtlClearAllBits(&v23[13]);
  RtlClearAllBits((PRTL_BITMAP)&v23[5].Buffer);
  RtlClearAllBits((PRTL_BITMAP)&v23[8].Buffer);
  v9 = *(_QWORD *)(a3 + 2);
  v10 = *(_OWORD *)(a3 + 30);
  *(_QWORD *)&v23[4].SizeOfBitMap = a1 + v6;
  LOWORD(v23[0].SizeOfBitMap) = *(_WORD *)a3;
  *(_DWORD *)((char *)&v23[0].Buffer + 2) = *(_DWORD *)(a3 + 10);
  HIWORD(v23[2].Buffer) = *(_WORD *)(a3 + 46);
  LOBYTE(v23[3].SizeOfBitMap) = *(_BYTE *)(a3 + 48);
  *(unsigned int *)((char *)&v23[3].SizeOfBitMap + 1) = *(_DWORD *)(a3 + 49);
  v11 = *(_WORD *)(a3 + 53);
  *(_QWORD *)((char *)&v23[0].SizeOfBitMap + 2) = v9;
  v12 = *(_OWORD *)(a3 + 14);
  *(_WORD *)((char *)&v23[3].SizeOfBitMap + 5) = v11;
  *((_BYTE *)&v23[3].SizeOfBitMap + 7) = *(_BYTE *)(a3 + 55);
  v23[3].Buffer = (unsigned int *)a1;
  LODWORD(v23[4].Buffer) = v6;
  *(_OWORD *)((char *)&v23[0].Buffer + 6) = v12;
  *(_OWORD *)((char *)&v23[1].Buffer + 6) = v10;
  v13 = WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids;
  if ( !a1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_(a4, (_DWORD)v13, 5, 135, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    v14 = 60;
LABEL_7:
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), v14);
    goto LABEL_8;
  }
  if ( (unsigned int)v6 < 9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_dD(a4, (_DWORD)v13, 5, 136, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v6, 9);
    }
    v14 = 56;
    goto LABEL_7;
  }
  v21 = 0;
  HUBDESC_InternalValidateConfigDescriptor(a1, (unsigned int)v23, (unsigned int)v22, (unsigned int)&v21, a4);
  if ( v21 == 1 )
    goto LABEL_8;
  v17 = a1 + 9;
  v18 = v21 != 2;
  while ( v17 < *(_QWORD *)&v23[4].SizeOfBitMap )
  {
    v22[0] = 0;
    v21 = 0;
    HUBDESC_InternalValidateCommonDescriptorHeader(v17, (unsigned int)v23, (unsigned int)v22, (unsigned int)&v21, a4);
    if ( v21 == 1 )
      goto LABEL_8;
    if ( v21 == 2 )
      v18 = LOBYTE(v23[3].SizeOfBitMap) != 0 ? v18 : 0;
    v21 = 0;
    if ( *(_BYTE *)(v17 + 1) == 4 )
    {
      v23[16].SizeOfBitMap &= ~4u;
      HUBDESC_InternalValidateInterfaceDescriptor(v17, (unsigned int)v23, (unsigned int)v22, (unsigned int)&v21, a4);
      if ( v21 == 1 )
        goto LABEL_8;
      if ( v21 == 2 )
        v18 = 0;
    }
    else
    {
      switch ( *(_BYTE *)(v17 + 1) )
      {
        case 5:
          HUBDESC_InternalValidateEndpointDescriptor((char *)v17, (__int64)v23, v22, &v21, a4);
          break;
        case 0xB:
          v23[16].SizeOfBitMap &= 0xFFFFFFF3;
          HUBDESC_InternalValidateIADescriptor(v17, (unsigned int)v23, (unsigned int)v22, (unsigned int)&v21, a4);
          break;
        case 0x12:
          if ( !(unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(
                                (unsigned int)*(unsigned __int8 *)(v17 + 1) - 18,
                                v15) )
          {
            v23[16].SizeOfBitMap &= 0xFFFFFFF3;
            goto LABEL_39;
          }
          v23[16].SizeOfBitMap &= ~0x80u;
          HUBDESC_InternalValidateHighSpeedIsochEndpointCompanionDescriptor(
            v17,
            (unsigned int)v23,
            (unsigned int)v22,
            (unsigned int)&v21,
            a4);
          break;
        default:
          v19 = (unsigned int)*(unsigned __int8 *)(v17 + 1) - 48;
          if ( *(_BYTE *)(v17 + 1) == 48 )
          {
            v23[16].SizeOfBitMap &= ~8u;
            HUBDESC_InternalValidateSuperSpeedEndpointCompanionDescriptor((char *)v17, (__int64)v23, v22, &v21, a4, a5);
          }
          else
          {
            if ( *(_BYTE *)(v17 + 1) != 49 )
            {
              v23[16].SizeOfBitMap &= 0xFFFFFFF3;
              if ( (unsigned int)Feature_EUSB2__private_IsEnabledDeviceUsageNoInline(v19, v15) )
                v23[16].SizeOfBitMap &= ~0x10u;
              goto LABEL_39;
            }
            HUBDESC_InternalValidateSuperSpeedPlusIsochEndpointCompanionDescriptor(
              v17,
              (unsigned int)v23,
              (unsigned int)v22,
              (unsigned int)&v21,
              a4);
          }
          break;
      }
      if ( v21 == 1 )
        goto LABEL_8;
      if ( v21 == 2 )
        v18 = 0;
    }
LABEL_39:
    if ( !*(_BYTE *)v17 )
      break;
    v17 += v22[0];
  }
  v21 = 0;
  HUBDESC_InternalValidateLastInterface(v23, &v21, a4);
  if ( v21 != 1 )
  {
    v16 = v18;
    if ( v21 == 2 )
      v16 = 0;
    if ( WORD1(v23[12].Buffer) == *(unsigned __int8 *)(a1 + 4)
      || LOWORD(v23[0].SizeOfBitMap) <= 0x200u && !WORD2(v23[0].Buffer) )
    {
      if ( !v16 )
        goto LABEL_49;
      return v16;
    }
  }
LABEL_8:
  v16 = 0;
LABEL_49:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_(a4, v15, 5, 137, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v16;
}

```

## disassembly

```asm
0x14003cce8  mov     [rsp-8+arg_8], rbx
0x14003cced  push    rbp
0x14003ccee  push    rsi
0x14003ccef  push    rdi
0x14003ccf0  push    r14
0x14003ccf2  push    r15
0x14003ccf4  lea     rbp, [rsp-70h]
0x14003ccf9  sub     rsp, 170h
0x14003cd00  mov     rax, cs:__security_cookie
0x14003cd07  xor     rax, rsp
0x14003cd0a  mov     [rbp+90h+var_30], rax
0x14003cd0e  mov     r15, [rbp+90h+arg_20]
0x14003cd15  mov     rsi, r9
0x14003cd18  mov     edi, edx
0x14003cd1a  mov     rbx, r8
0x14003cd1d  mov     [rsp+190h+var_150], 0
0x14003cd25  mov     r14, rcx
0x14003cd28  mov     [rsp+190h+var_14C], 0
0x14003cd30  test    r15, r15
0x14003cd33  jz      short loc_14003CD39
0x14003cd35  mov     byte ptr [r15], 0
0x14003cd39  xor     edx, edx; Val
0x14003cd3b  lea     rcx, [rsp+190h+var_140]; void *
0x14003cd40  mov     r8d, 108h; Size
0x14003cd46  call    memset
0x14003cd4b  mov     ecx, 100h
0x14003cd50  lea     rax, [rbp+90h+var_60]
0x14003cd54  mov     [rbp+90h+BitMapHeader.Buffer], rax
0x14003cd58  lea     rax, [rbp+90h+var_D8]
0x14003cd5c  mov     [rbp+90h+var_E8.Buffer], rax
0x14003cd60  lea     rax, [rbp+90h+var_A8]
0x14003cd64  mov     [rbp+90h+BitMapHeader.SizeOfBitMap], ecx
0x14003cd67  mov     [rbp+90h+var_E8.SizeOfBitMap], ecx
0x14003cd6a  mov     [rbp+90h+var_B8.SizeOfBitMap], ecx
0x14003cd6d  lea     rcx, [rbp+90h+BitMapHeader]; BitMapHeader
0x14003cd71  mov     [rbp+90h+var_B8.Buffer], rax
0x14003cd75  call    cs:__imp_RtlClearAllBits
0x14003cd7c  nop     dword ptr [rax+rax+00h]
0x14003cd81  lea     rcx, [rbp+90h+var_E8]; BitMapHeader
0x14003cd85  call    cs:__imp_RtlClearAllBits
0x14003cd8c  nop     dword ptr [rax+rax+00h]
0x14003cd91  lea     rcx, [rbp+90h+var_B8]; BitMapHeader
0x14003cd95  call    cs:__imp_RtlClearAllBits
0x14003cd9c  nop     dword ptr [rax+rax+00h]
0x14003cda1  movsd   xmm0, qword ptr [rbx+2]
0x14003cda6  lea     rax, [r14+rdi]
0x14003cdaa  movups  xmm1, xmmword ptr [rbx+1Eh]
0x14003cdae  mov     [rbp+90h+var_100], rax
0x14003cdb2  movzx   eax, word ptr [rbx]
0x14003cdb5  mov     [rsp+190h+var_140], ax
0x14003cdba  movzx   eax, word ptr [rbx+0Ah]
0x14003cdbe  mov     [rsp+190h+var_136], ax
0x14003cdc3  mov     al, [rbx+0Ch]
0x14003cdc6  mov     [rsp+190h+var_134], al
0x14003cdca  mov     al, [rbx+0Dh]
0x14003cdcd  mov     [rsp+190h+var_133], al
0x14003cdd1  movzx   eax, word ptr [rbx+2Eh]
0x14003cdd5  mov     [rsp+190h+var_112], ax
0x14003cdda  mov     al, [rbx+30h]
0x14003cddd  mov     [rbp+90h+var_110], al
0x14003cde0  mov     eax, [rbx+31h]
0x14003cde3  mov     [rbp+90h+var_10F], eax
0x14003cde6  movzx   eax, word ptr [rbx+35h]
0x14003cdea  movsd   [rsp+190h+var_13E], xmm0
0x14003cdf0  movups  xmm0, xmmword ptr [rbx+0Eh]
0x14003cdf4  mov     [rbp+90h+var_10B], ax
0x14003cdf8  mov     al, [rbx+37h]
0x14003cdfb  mov     [rbp+90h+var_109], al
0x14003cdfe  mov     [rbp+90h+var_108], r14
0x14003ce02  mov     [rbp+90h+var_F8], edi
0x14003ce05  movups  [rsp+190h+var_132], xmm0
0x14003ce0a  movups  [rsp+190h+var_122], xmm1
0x14003ce0f  lea     rax, WPP_RECORDER_INITIALIZED
0x14003ce16  mov     ecx, 5
0x14003ce1b  lea     rdx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ce22  test    r14, r14
0x14003ce25  jnz     short loc_14003CE61
0x14003ce27  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14003ce2e  jz      short loc_14003CE48
0x14003ce30  mov     [rsp+190h+var_170], rdx
0x14003ce35  mov     r8d, ecx
0x14003ce38  mov     dl, 2
0x14003ce3a  mov     rcx, rsi
0x14003ce3d  mov     r9d, 87h
0x14003ce43  call    WPP_RECORDER_SF_
0x14003ce48  mov     edx, 3Ch ; '<'
0x14003ce4d  mov     rax, [rbx+18h]
0x14003ce51  mov     rcx, [rbx+28h]
0x14003ce55  call    _guard_dispatch_icall
0x14003ce5a  xor     bl, bl
0x14003ce5c  jmp     loc_14003D0FF
0x14003ce61  cmp     edi, 9
0x14003ce64  jnb     short loc_14003CE9A
0x14003ce66  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14003ce6d  jz      short loc_14003CE93
0x14003ce6f  mov     [rsp+190h+var_160], 9
0x14003ce77  mov     r8d, ecx
0x14003ce7a  mov     dword ptr [rsp+190h+var_168], edi
0x14003ce7e  mov     r9d, 88h
0x14003ce84  mov     [rsp+190h+var_170], rdx
0x14003ce89  mov     rcx, rsi
0x14003ce8c  mov     dl, 2
0x14003ce8e  call    WPP_RECORDER_SF_dD
0x14003ce93  mov     edx, 38h ; '8'
0x14003ce98  jmp     short loc_14003CE4D
0x14003ce9a  lea     r9, [rsp+190h+var_150]
0x14003ce9f  mov     [rsp+190h+var_150], 0
0x14003cea7  lea     r8, [rsp+190h+var_14C]
0x14003ceac  mov     [rsp+190h+var_170], rsi
0x14003ceb1  lea     rdx, [rsp+190h+var_140]
0x14003ceb6  mov     rcx, r14
0x14003ceb9  call    HUBDESC_InternalValidateConfigDescriptor
0x14003cebe  mov     eax, 1
0x14003cec3  cmp     [rsp+190h+var_150], eax
0x14003cec7  jz      short loc_14003CE5A
0x14003cec9  mov     edi, eax
0x14003cecb  lea     rbx, [r14+9]
0x14003cecf  xor     eax, eax
0x14003ced1  cmp     [rsp+190h+var_150], 2
0x14003ced6  cmovz   edi, eax
0x14003ced9  jmp     loc_14003D08D
0x14003cede  lea     r9, [rsp+190h+var_150]
0x14003cee3  mov     [rsp+190h+var_14C], 0
0x14003ceeb  lea     r8, [rsp+190h+var_14C]
0x14003cef0  mov     [rsp+190h+var_150], 0
0x14003cef8  lea     rdx, [rsp+190h+var_140]
0x14003cefd  mov     [rsp+190h+var_170], rsi
0x14003cf02  mov     rcx, rbx
0x14003cf05  call    HUBDESC_InternalValidateCommonDescriptorHeader
0x14003cf0a  cmp     [rsp+190h+var_150], 1
0x14003cf0f  jz      loc_14003CE5A
0x14003cf15  cmp     [rsp+190h+var_150], 2
0x14003cf1a  jnz     short loc_14003CF26
0x14003cf1c  mov     al, [rbp+90h+var_110]
0x14003cf1f  neg     al
0x14003cf21  sbb     cl, cl
0x14003cf23  and     dil, cl
0x14003cf26  mov     [rsp+190h+var_150], 0
0x14003cf2e  movzx   ecx, byte ptr [rbx+1]
0x14003cf32  sub     ecx, 4
0x14003cf35  jz      loc_14003D048
0x14003cf3b  sub     ecx, 1
0x14003cf3e  jz      loc_14003D015
0x14003cf44  sub     ecx, 6
0x14003cf47  jz      loc_14003CFF3
0x14003cf4d  sub     ecx, 7
0x14003cf50  jz      short loc_14003CFBE
0x14003cf52  sub     ecx, 1Eh
0x14003cf55  jz      short loc_14003CF97
0x14003cf57  cmp     ecx, 1
0x14003cf5a  jz      short loc_14003CF76
0x14003cf5c  and     [rbp+90h+var_40], 0FFFFFFF3h
0x14003cf60  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14003cf65  test    eax, eax
0x14003cf67  jz      loc_14003D081
0x14003cf6d  and     [rbp+90h+var_40], 0FFFFFFEFh
0x14003cf71  jmp     loc_14003D081
0x14003cf76  lea     r9, [rsp+190h+var_150]
0x14003cf7b  mov     [rsp+190h+var_170], rsi
0x14003cf80  lea     r8, [rsp+190h+var_14C]
0x14003cf85  mov     rcx, rbx
0x14003cf88  lea     rdx, [rsp+190h+var_140]
0x14003cf8d  call    HUBDESC_InternalValidateSuperSpeedPlusIsochEndpointCompanionDescriptor
0x14003cf92  jmp     loc_14003D031
0x14003cf97  and     [rbp+90h+var_40], 0FFFFFFF7h
0x14003cf9b  lea     r9, [rsp+190h+var_150]
0x14003cfa0  mov     [rsp+190h+var_168], r15
0x14003cfa5  lea     r8, [rsp+190h+var_14C]
0x14003cfaa  lea     rdx, [rsp+190h+var_140]
0x14003cfaf  mov     [rsp+190h+var_170], rsi
0x14003cfb4  mov     rcx, rbx
0x14003cfb7  call    HUBDESC_InternalValidateSuperSpeedEndpointCompanionDescriptor
0x14003cfbc  jmp     short loc_14003D031
0x14003cfbe  call    Feature_EUSB2__private_IsEnabledDeviceUsageNoInline
0x14003cfc3  test    eax, eax
0x14003cfc5  jnz     short loc_14003CFD0
0x14003cfc7  and     [rbp+90h+var_40], 0FFFFFFF3h
0x14003cfcb  jmp     loc_14003D081
0x14003cfd0  btr     [rbp+90h+var_40], 7
0x14003cfd5  lea     r9, [rsp+190h+var_150]
0x14003cfda  lea     r8, [rsp+190h+var_14C]
0x14003cfdf  mov     [rsp+190h+var_170], rsi
0x14003cfe4  lea     rdx, [rsp+190h+var_140]
0x14003cfe9  mov     rcx, rbx
0x14003cfec  call    HUBDESC_InternalValidateHighSpeedIsochEndpointCompanionDescriptor
0x14003cff1  jmp     short loc_14003D031
0x14003cff3  and     [rbp+90h+var_40], 0FFFFFFF3h
0x14003cff7  lea     r9, [rsp+190h+var_150]
0x14003cffc  lea     r8, [rsp+190h+var_14C]
0x14003d001  mov     [rsp+190h+var_170], rsi
0x14003d006  lea     rdx, [rsp+190h+var_140]
0x14003d00b  mov     rcx, rbx
0x14003d00e  call    HUBDESC_InternalValidateIADescriptor
0x14003d013  jmp     short loc_14003D031
0x14003d015  lea     r9, [rsp+190h+var_150]
0x14003d01a  mov     [rsp+190h+var_170], rsi
0x14003d01f  lea     r8, [rsp+190h+var_14C]
0x14003d024  mov     rcx, rbx
0x14003d027  lea     rdx, [rsp+190h+var_140]
0x14003d02c  call    HUBDESC_InternalValidateEndpointDescriptor
0x14003d031  cmp     [rsp+190h+var_150], 1
0x14003d036  jz      loc_14003CE5A
0x14003d03c  cmp     [rsp+190h+var_150], 2
0x14003d041  jnz     short loc_14003D081
0x14003d043  xor     dil, dil
0x14003d046  jmp     short loc_14003D081
0x14003d048  and     [rbp+90h+var_40], 0FFFFFFFBh
0x14003d04c  lea     r9, [rsp+190h+var_150]
0x14003d051  lea     r8, [rsp+190h+var_14C]
0x14003d056  mov     [rsp+190h+var_170], rsi
0x14003d05b  lea     rdx, [rsp+190h+var_140]
0x14003d060  mov     rcx, rbx
0x14003d063  call    HUBDESC_InternalValidateInterfaceDescriptor
0x14003d068  cmp     [rsp+190h+var_150], 1
0x14003d06d  jz      loc_14003CE5A
0x14003d073  xor     eax, eax
0x14003d075  movzx   edi, dil
0x14003d079  cmp     [rsp+190h+var_150], 2
0x14003d07e  cmovz   edi, eax
0x14003d081  cmp     byte ptr [rbx], 0
0x14003d084  jz      short loc_14003D097
0x14003d086  mov     eax, [rsp+190h+var_14C]
0x14003d08a  add     rbx, rax
0x14003d08d  cmp     rbx, [rbp+90h+var_100]
0x14003d091  jb      loc_14003CEDE
0x14003d097  mov     r8, rsi
0x14003d09a  mov     [rsp+190h+var_150], 0
0x14003d0a2  lea     rdx, [rsp+190h+var_150]
0x14003d0a7  lea     rcx, [rsp+190h+var_140]
0x14003d0ac  call    HUBDESC_InternalValidateLastInterface
0x14003d0b1  cmp     [rsp+190h+var_150], 1
0x14003d0b6  jz      loc_14003CE5A
0x14003d0bc  xor     eax, eax
0x14003d0be  movzx   ebx, dil
0x14003d0c2  cmp     [rsp+190h+var_150], 2
0x14003d0c7  cmovz   ebx, eax
0x14003d0ca  movzx   eax, byte ptr [r14+4]
0x14003d0cf  cmp     [rbp+90h+var_76], ax
0x14003d0d3  jz      short loc_14003D0FB
0x14003d0d5  mov     eax, 200h
0x14003d0da  cmp     [rsp+190h+var_140], ax
0x14003d0df  ja      loc_14003CE5A
0x14003d0e5  cmp     [rsp+190h+var_134], 0
0x14003d0ea  jnz     loc_14003CE5A
0x14003d0f0  cmp     [rsp+190h+var_133], 0
0x14003d0f5  jnz     loc_14003CE5A
0x14003d0fb  test    bl, bl
0x14003d0fd  jnz     short loc_14003D131
0x14003d0ff  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003d106  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003d10d  jz      short loc_14003D131
0x14003d10f  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003d116  mov     r9d, 89h
0x14003d11c  mov     r8d, 5
0x14003d122  mov     [rsp+190h+var_170], rax
0x14003d127  mov     dl, 2
0x14003d129  mov     rcx, rsi
0x14003d12c  call    WPP_RECORDER_SF_
0x14003d131  mov     al, bl
0x14003d133  mov     rcx, [rbp+90h+var_30]
0x14003d137  xor     rcx, rsp; StackCookie
0x14003d13a  call    __security_check_cookie
0x14003d13f  mov     rbx, [rsp+190h+arg_8]
0x14003d147  add     rsp, 170h
0x14003d14e  pop     r15
0x14003d150  pop     r14
0x14003d152  pop     rdi
0x14003d153  pop     rsi
0x14003d154  pop     rbp
0x14003d155  retn
```

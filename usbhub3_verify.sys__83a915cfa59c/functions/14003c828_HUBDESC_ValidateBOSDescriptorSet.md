# HUBDESC_ValidateBOSDescriptorSet

- ea: `0x14003c828`
- end: `0x14003cce1`
- name: `HUBDESC_ValidateBOSDescriptorSet`
- size: `1209`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14002bc18`

## callees

- `0x1400025a4`
- `0x1400067ac`
- `0x1400305e8`
- `0x1400357e0`
- `0x140035e1c`
- `0x14003676c`
- `0x14003c828`
- `0x14003f208`
- `0x140045570`
- `0x140045940`

## pseudocode

```c
bool __fastcall HUBDESC_ValidateBOSDescriptorSet(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        _BYTE *a6,
        _WORD *a7,
        _WORD *a8,
        __int64 a9,
        __int64 a10,
        _DWORD *a11,
        _BYTE *a12,
        _BYTE *a13,
        __int64 a14)
{
  __int64 v14; // r15
  __int64 v17; // rsi
  _BYTE *v18; // rbx
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  int v22; // edx
  __int64 v23; // r14
  int v24; // edx
  bool v25; // di
  _WORD *v26; // rbx
  int v27; // r8d
  _WORD *v28; // r12
  int v29; // r15d
  unsigned __int8 *v30; // rbx
  __int64 v31; // r12
  bool v32; // cl
  bool v33; // zf
  char v34; // al
  int v35; // eax
  _DWORD *v36; // rbx
  __int64 v37; // rax
  int v39; // [rsp+20h] [rbp-D9h]
  _BYTE v40[96]; // [rsp+60h] [rbp-99h] BYREF
  _BYTE v41[112]; // [rsp+C0h] [rbp-39h] BYREF
  unsigned int v43; // [rsp+148h] [rbp+4Fh] BYREF
  int v44; // [rsp+158h] [rbp+5Fh] BYREF

  v14 = a4;
  v44 = 0;
  v43 = 0;
  memset(v40, 0, 0x5Eu);
  memset(v41, 0, 0x40u);
  v17 = a5;
  *(_QWORD *)&v40[64] = v14 + a2;
  *(_QWORD *)&v40[88] = a3;
  v18 = v41;
  v19 = *(_OWORD *)(a5 + 8);
  *(_DWORD *)v40 = *(_DWORD *)a5;
  v20 = *(_OWORD *)(a5 + 24);
  *(_DWORD *)&v40[4] = *(_DWORD *)(a5 + 4);
  *(_DWORD *)&v40[72] = v14;
  *(_OWORD *)&v40[8] = v19;
  if ( a6 )
    v18 = a6;
  *(_QWORD *)&v40[56] = a2;
  v21 = *(_OWORD *)(a5 + 40);
  *(_OWORD *)&v40[24] = v20;
  *(_OWORD *)&v40[40] = v21;
  if ( a7 )
    *a7 = 0;
  if ( a8 )
    *a8 = 0;
  if ( a12 )
    *a12 = 0;
  if ( a13 )
    *a13 = 0;
  memset(v18, 0, 0x40u);
  *(_QWORD *)&v40[80] = v18;
  if ( (unsigned int)v14 < 5 )
  {
    LODWORD(v23) = a14;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v22) = 2;
      WPP_RECORDER_SF_dD(a14, v22, 5, 245, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v14, 5);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v17 + 24))(*(_QWORD *)(v17 + 40), 23);
    goto LABEL_15;
  }
  v23 = a14;
  HUBDESC_InternalValidateBOSDescriptor(a2, (unsigned int)v40, (unsigned int)&v43, (unsigned int)&v44, a14);
  if ( v44 == 1 )
  {
LABEL_15:
    v25 = 0;
    goto LABEL_56;
  }
  v26 = (_WORD *)(a2 + 2);
  v25 = v44 != 2;
  if ( (unsigned int)v14 >= *(unsigned __int16 *)(a2 + 2) )
  {
    v28 = (_WORD *)(a2 + 2);
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64))(v17 + 24))(*(_QWORD *)(v17 + 40), 23);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Ddd(v23, v24, v27, 246, v39, v14, *v26, v14);
    v28 = (_WORD *)(a2 + 2);
    v25 = 0;
  }
  if ( (unsigned int)v14 > (unsigned __int16)*v26 )
  {
    (*(void (__fastcall **)(_QWORD, __int64))(v17 + 32))(*(_QWORD *)(v17 + 40), 22);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_dD(v23, v24, 5, 247, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v14, *v28);
    }
  }
  v29 = 0;
  v30 = (unsigned __int8 *)(a2 + v43);
  if ( (unsigned __int64)v30 < *(_QWORD *)&v40[64] )
  {
    v31 = (__int64)a12;
    while ( 1 )
    {
      v44 = 0;
      HUBDESC_InternalValidateCommonDescriptorHeader(
        (_DWORD)v30,
        (unsigned int)v40,
        (unsigned int)&v43,
        (unsigned int)&v44,
        v23);
      if ( v44 == 1 )
        break;
      v32 = v25;
      v33 = v44 == 2;
      v44 = 0;
      if ( v33 )
        v32 = 0;
      v34 = v30[1];
      v25 = v32;
      if ( v34 == 16 )
      {
        HUBDESC_InternalValidateDeviceCapabilityDescriptor(
          v30,
          (__int64)v40,
          &v43,
          &v44,
          a7,
          a8,
          a9,
          a10,
          v31,
          (__int64)a13,
          v23);
        if ( v44 == 1 )
          break;
        if ( v44 == 2 )
          v25 = 0;
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v24) = 2;
          WPP_RECORDER_SF_dD(
            v23,
            v24,
            5,
            248,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            (_BYTE)v30 - a2,
            v34);
        }
        (*(void (__fastcall **)(_QWORD, __int64))(v17 + 32))(*(_QWORD *)(v17 + 40), 28);
      }
      ++v29;
      v30 += v43;
      if ( (unsigned __int64)v30 >= *(_QWORD *)&v40[64] )
        goto LABEL_38;
    }
    v25 = 0;
    goto LABEL_56;
  }
LABEL_38:
  v35 = *(unsigned __int8 *)(a2 + 4);
  if ( v35 != v29 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_dD(v23, v24, 5, 249, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v29, v35);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v17 + 24))(*(_QWORD *)(v17 + 40), 25);
    v25 = 0;
  }
  v36 = a11;
  if ( *(_QWORD *)(*(_QWORD *)&v40[80] + 8LL) )
  {
    if ( a11 )
      *a11 |= 0x800u;
  }
  else if ( *(_DWORD *)&v40[4] == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_(v23, v24, 5, 250, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(v17 + 24))(*(_QWORD *)(v17 + 40), 26);
    v25 = 0;
  }
  HUBMISC_LogTelemetryIfSuperSpeedDeviceWorkingInHighSpeedMode(a1);
  if ( v36 )
  {
    v37 = *(_QWORD *)&v40[80];
    if ( *(_QWORD *)(*(_QWORD *)&v40[80] + 16LL) )
      *v36 |= 0x1000u;
    if ( *(_BYTE *)(v37 + 42) )
      *v36 |= 0x10000u;
  }
  if ( !v25 )
  {
LABEL_56:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v24) = 2;
      WPP_RECORDER_SF_(v23, v24, 5, 251, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
  }
  return v25;
}

```

## disassembly

```asm
0x14003c828  mov     [rsp-8+arg_10], rbx
0x14003c82d  mov     [rsp-8+arg_0], rcx
0x14003c832  push    rbp
0x14003c833  push    rsi
0x14003c834  push    rdi
0x14003c835  push    r12
0x14003c837  push    r13
0x14003c839  push    r14
0x14003c83b  push    r15
0x14003c83d  lea     rbp, [rsp-7]
0x14003c842  sub     rsp, 100h
0x14003c849  xor     r12d, r12d
0x14003c84c  mov     r15d, r9d
0x14003c84f  mov     rbx, r8
0x14003c852  mov     [rbp+37h+arg_18], r12d
0x14003c856  mov     r13, rdx
0x14003c859  mov     [rbp+37h+arg_8], r12d
0x14003c85d  xor     edx, edx; Val
0x14003c85f  lea     rcx, [rsp+130h+var_D0]; void *
0x14003c864  lea     r8d, [r12+5Eh]; Size
0x14003c869  call    memset
0x14003c86e  lea     edi, [r12+40h]
0x14003c873  xor     edx, edx; Val
0x14003c875  mov     r8d, edi; Size
0x14003c878  lea     rcx, [rbp+37h+var_70]; void *
0x14003c87c  call    memset
0x14003c881  mov     rsi, [rbp+37h+arg_20]
0x14003c885  lea     rax, [r15+r13]
0x14003c889  mov     rcx, [rbp+37h+arg_30]
0x14003c88d  mov     [rbp+37h+var_90], rax
0x14003c891  mov     [rbp+37h+var_78], rbx
0x14003c895  lea     rbx, [rbp+37h+var_70]
0x14003c899  mov     eax, [rsi]
0x14003c89b  movups  xmm0, xmmword ptr [rsi+8]
0x14003c89f  mov     [rsp+130h+var_D0], eax
0x14003c8a3  mov     eax, [rsi+4]
0x14003c8a6  movups  xmm1, xmmword ptr [rsi+18h]
0x14003c8aa  mov     [rsp+130h+var_CC], eax
0x14003c8ae  mov     rax, [rbp+37h+arg_28]
0x14003c8b2  test    rax, rax
0x14003c8b5  mov     [rbp+37h+var_88], r15d
0x14003c8b9  movups  [rsp+130h+var_C8], xmm0
0x14003c8be  cmovnz  rbx, rax
0x14003c8c2  mov     [rbp+37h+var_98], r13
0x14003c8c6  movups  xmm0, xmmword ptr [rsi+28h]
0x14003c8ca  movups  [rsp+130h+var_B8], xmm1
0x14003c8cf  movups  [rbp+37h+var_A8], xmm0
0x14003c8d3  test    rcx, rcx
0x14003c8d6  jz      short loc_14003C8DC
0x14003c8d8  mov     [rcx], r12w
0x14003c8dc  mov     rcx, [rbp+37h+arg_38]
0x14003c8e0  test    rcx, rcx
0x14003c8e3  jz      short loc_14003C8E9
0x14003c8e5  mov     [rcx], r12w
0x14003c8e9  mov     rax, [rbp+37h+arg_58]
0x14003c8f0  test    rax, rax
0x14003c8f3  jz      short loc_14003C8F8
0x14003c8f5  mov     [rax], r12b
0x14003c8f8  mov     rax, [rbp+37h+arg_60]
0x14003c8ff  test    rax, rax
0x14003c902  jz      short loc_14003C907
0x14003c904  mov     [rax], r12b
0x14003c907  mov     r8, rdi; Size
0x14003c90a  xor     edx, edx; Val
0x14003c90c  mov     rcx, rbx; void *
0x14003c90f  call    memset
0x14003c914  mov     [rbp+37h+var_80], rbx
0x14003c918  lea     rax, WPP_RECORDER_INITIALIZED
0x14003c91f  lea     rbx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003c926  cmp     r15d, 5
0x14003c92a  jnb     short loc_14003C97E
0x14003c92c  cmp     cs:WPP_RECORDER_INITIALIZED, rax; __annotation("TMF:",
0x14003c933  mov     r14, [rbp+37h+arg_68]
0x14003c93a  jz      short loc_14003C964
0x14003c93c  mov     dword ptr [rsp+130h+var_100], 5
0x14003c944  mov     r9d, 0F5h
0x14003c94a  mov     dword ptr [rsp+130h+var_108], r15d
0x14003c94f  mov     r8d, 5
0x14003c955  mov     dl, 2
0x14003c957  mov     [rsp+130h+var_110], rbx
0x14003c95c  mov     rcx, r14
0x14003c95f  call    WPP_RECORDER_SF_dD
0x14003c964  mov     rax, [rsi+18h]
0x14003c968  mov     edx, 17h
0x14003c96d  mov     rcx, [rsi+28h]
0x14003c971  call    _guard_dispatch_icall
0x14003c976  mov     dil, r12b
0x14003c979  jmp     loc_14003CC97
0x14003c97e  mov     r14, [rbp+37h+arg_68]
0x14003c985  lea     r9, [rbp+37h+arg_18]
0x14003c989  lea     r8, [rbp+37h+arg_8]
0x14003c98d  mov     [rsp+130h+var_110], r14
0x14003c992  lea     rdx, [rsp+130h+var_D0]
0x14003c997  mov     rcx, r13
0x14003c99a  call    HUBDESC_InternalValidateBOSDescriptor
0x14003c99f  mov     eax, 1
0x14003c9a4  cmp     [rbp+37h+arg_18], eax
0x14003c9a7  jz      short loc_14003C976
0x14003c9a9  cmp     [rbp+37h+arg_18], 2
0x14003c9ad  lea     rbx, [r13+2]
0x14003c9b1  mov     edi, eax
0x14003c9b3  movzx   eax, word ptr [rbx]
0x14003c9b6  cmovz   edi, r12d
0x14003c9ba  cmp     r15d, eax
0x14003c9bd  jnb     short loc_14003CA0E
0x14003c9bf  mov     rax, [rsi+18h]
0x14003c9c3  mov     edx, 17h
0x14003c9c8  mov     rcx, [rsi+28h]
0x14003c9cc  call    _guard_dispatch_icall
0x14003c9d1  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003c9d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003c9df  jz      short loc_14003CA06
0x14003c9e1  movzx   eax, word ptr [rbx]
0x14003c9e4  mov     r9d, 0F6h
0x14003c9ea  mov     dword ptr [rsp+130h+var_F8], r15d
0x14003c9ef  mov     rcx, r14
0x14003c9f2  mov     dword ptr [rsp+130h+var_100], eax
0x14003c9f6  mov     dword ptr [rsp+130h+var_108], r15d
0x14003c9fb  call    WPP_RECORDER_SF_Ddd
0x14003ca00  lea     r12, [r13+2]
0x14003ca04  jmp     short loc_14003CA09
0x14003ca06  mov     r12, rbx
0x14003ca09  xor     dil, dil
0x14003ca0c  jmp     short loc_14003CA11
0x14003ca0e  mov     r12, rbx
0x14003ca11  movzx   eax, word ptr [rbx]
0x14003ca14  cmp     r15d, eax
0x14003ca17  jbe     short loc_14003CA6B
0x14003ca19  mov     rax, [rsi+20h]
0x14003ca1d  mov     edx, 16h
0x14003ca22  mov     rcx, [rsi+28h]
0x14003ca26  call    _guard_dispatch_icall
0x14003ca2b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003ca32  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003ca39  jz      short loc_14003CA6B
0x14003ca3b  movzx   eax, word ptr [r12]
0x14003ca40  mov     r9d, 0F7h
0x14003ca46  mov     dword ptr [rsp+130h+var_100], eax
0x14003ca4a  mov     r8d, 5
0x14003ca50  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003ca57  mov     dword ptr [rsp+130h+var_108], r15d
0x14003ca5c  mov     dl, 2
0x14003ca5e  mov     [rsp+130h+var_110], rax
0x14003ca63  mov     rcx, r14
0x14003ca66  call    WPP_RECORDER_SF_dD
0x14003ca6b  mov     ebx, [rbp+37h+arg_8]
0x14003ca6e  xor     r15d, r15d
0x14003ca71  add     rbx, r13
0x14003ca74  cmp     rbx, [rbp+37h+var_90]
0x14003ca78  jnb     loc_14003CB95
0x14003ca7e  mov     r12, [rbp+37h+arg_58]
0x14003ca85  lea     r9, [rbp+37h+arg_18]
0x14003ca89  mov     [rbp+37h+arg_18], 0
0x14003ca90  lea     r8, [rbp+37h+arg_8]
0x14003ca94  mov     [rsp+130h+var_110], r14
0x14003ca99  lea     rdx, [rsp+130h+var_D0]
0x14003ca9e  mov     rcx, rbx
0x14003caa1  call    HUBDESC_InternalValidateCommonDescriptorHeader
0x14003caa6  cmp     [rbp+37h+arg_18], 1
0x14003caaa  jz      loc_14003CBF1
0x14003cab0  xor     eax, eax
0x14003cab2  movzx   ecx, dil
0x14003cab6  cmp     [rbp+37h+arg_18], 2
0x14003caba  mov     [rbp+37h+arg_18], eax
0x14003cabd  cmovz   ecx, eax
0x14003cac0  movzx   eax, byte ptr [rbx+1]
0x14003cac4  movzx   edi, cl
0x14003cac7  cmp     al, 10h
0x14003cac9  jz      short loc_14003CB1E
0x14003cacb  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003cad2  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14003cad9  jz      short loc_14003CB0A
0x14003cadb  mov     dword ptr [rsp+130h+var_100], eax
0x14003cadf  mov     ecx, ebx
0x14003cae1  sub     ecx, r13d
0x14003cae4  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003caeb  mov     dword ptr [rsp+130h+var_108], ecx
0x14003caef  mov     r9d, 0F8h
0x14003caf5  mov     rcx, r14
0x14003caf8  mov     [rsp+130h+var_110], rax
0x14003cafd  mov     r8d, 5
0x14003cb03  mov     dl, 2
0x14003cb05  call    WPP_RECORDER_SF_dD
0x14003cb0a  mov     rax, [rsi+20h]
0x14003cb0e  mov     edx, 1Ch
0x14003cb13  mov     rcx, [rsi+28h]
0x14003cb17  call    _guard_dispatch_icall
0x14003cb1c  jmp     short loc_14003CB82
0x14003cb1e  mov     rax, [rbp+37h+arg_60]
0x14003cb25  lea     r9, [rbp+37h+arg_18]
0x14003cb29  mov     [rsp+130h+var_E0], r14
0x14003cb2e  lea     r8, [rbp+37h+arg_8]
0x14003cb32  mov     [rsp+130h+var_E8], rax
0x14003cb37  lea     rdx, [rsp+130h+var_D0]
0x14003cb3c  mov     rax, [rbp+37h+arg_48]
0x14003cb43  mov     rcx, rbx
0x14003cb46  mov     [rsp+130h+var_F0], r12
0x14003cb4b  mov     [rsp+130h+var_F8], rax
0x14003cb50  mov     rax, [rbp+37h+arg_40]
0x14003cb57  mov     [rsp+130h+var_100], rax
0x14003cb5c  mov     rax, [rbp+37h+arg_38]
0x14003cb60  mov     [rsp+130h+var_108], rax
0x14003cb65  mov     rax, [rbp+37h+arg_30]
0x14003cb69  mov     [rsp+130h+var_110], rax
0x14003cb6e  call    HUBDESC_InternalValidateDeviceCapabilityDescriptor
0x14003cb73  cmp     [rbp+37h+arg_18], 1
0x14003cb77  jz      short loc_14003CBF1
0x14003cb79  xor     eax, eax
0x14003cb7b  cmp     [rbp+37h+arg_18], 2
0x14003cb7f  cmovz   edi, eax
0x14003cb82  mov     eax, [rbp+37h+arg_8]
0x14003cb85  inc     r15d
0x14003cb88  add     rbx, rax
0x14003cb8b  cmp     rbx, [rbp+37h+var_90]
0x14003cb8f  jb      loc_14003CA85
0x14003cb95  movzx   eax, byte ptr [r13+4]
0x14003cb9a  cmp     eax, r15d
0x14003cb9d  jz      short loc_14003CBF9
0x14003cb9f  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003cba6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14003cbad  jz      short loc_14003CBDA
0x14003cbaf  mov     dword ptr [rsp+130h+var_100], eax
0x14003cbb3  mov     r9d, 0F9h
0x14003cbb9  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003cbc0  mov     dword ptr [rsp+130h+var_108], r15d
0x14003cbc5  mov     r8d, 5
0x14003cbcb  mov     [rsp+130h+var_110], rax
0x14003cbd0  mov     dl, 2
0x14003cbd2  mov     rcx, r14
0x14003cbd5  call    WPP_RECORDER_SF_dD
0x14003cbda  mov     rax, [rsi+18h]
0x14003cbde  mov     edx, 19h
0x14003cbe3  mov     rcx, [rsi+28h]
0x14003cbe7  call    _guard_dispatch_icall
0x14003cbec  xor     dil, dil
0x14003cbef  jmp     short loc_14003CC00
0x14003cbf1  xor     dil, dil
0x14003cbf4  jmp     loc_14003CC90
0x14003cbf9  lea     r12, WPP_RECORDER_INITIALIZED
0x14003cc00  mov     rax, [rbp+37h+var_80]
0x14003cc04  mov     rbx, [rbp+37h+arg_50]
0x14003cc0b  cmp     qword ptr [rax+8], 0
0x14003cc10  jz      short loc_14003CC1D
0x14003cc12  test    rbx, rbx
0x14003cc15  jz      short loc_14003CC64
0x14003cc17  bts     dword ptr [rbx], 0Bh
0x14003cc1b  jmp     short loc_14003CC64
0x14003cc1d  cmp     [rsp+130h+var_CC], 3
0x14003cc22  jnz     short loc_14003CC64
0x14003cc24  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14003cc2b  jz      short loc_14003CC4F
0x14003cc2d  lea     rax, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003cc34  mov     r9d, 0FAh
0x14003cc3a  mov     r8d, 5
0x14003cc40  mov     [rsp+130h+var_110], rax
0x14003cc45  mov     dl, 2
0x14003cc47  mov     rcx, r14
0x14003cc4a  call    WPP_RECORDER_SF_
0x14003cc4f  mov     rax, [rsi+18h]
0x14003cc53  mov     edx, 1Ah
0x14003cc58  mov     rcx, [rsi+28h]
0x14003cc5c  call    _guard_dispatch_icall
0x14003cc61  xor     dil, dil
0x14003cc64  mov     rcx, [rbp+37h+arg_0]
0x14003cc68  call    HUBMISC_LogTelemetryIfSuperSpeedDeviceWorkingInHighSpeedMode
0x14003cc6d  test    rbx, rbx
0x14003cc70  jz      short loc_14003CC8B
0x14003cc72  mov     rax, [rbp+37h+var_80]
0x14003cc76  cmp     qword ptr [rax+10h], 0
0x14003cc7b  jz      short loc_14003CC81
0x14003cc7d  bts     dword ptr [rbx], 0Ch
0x14003cc81  cmp     byte ptr [rax+2Ah], 0
0x14003cc85  jz      short loc_14003CC8B
0x14003cc87  bts     dword ptr [rbx], 10h
0x14003cc8b  test    dil, dil
0x14003cc8e  jnz     short loc_14003CCC2
0x14003cc90  lea     rbx, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003cc97  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003cc9e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003cca5  jz      short loc_14003CCC2
0x14003cca7  mov     r9d, 0FBh
0x14003ccad  mov     [rsp+130h+var_110], rbx
0x14003ccb2  mov     r8d, 5
0x14003ccb8  mov     dl, 2
0x14003ccba  mov     rcx, r14
0x14003ccbd  call    WPP_RECORDER_SF_
0x14003ccc2  mov     rbx, [rsp+130h+arg_10]
0x14003ccca  mov     al, dil
0x14003cccd  add     rsp, 100h
0x14003ccd4  pop     r15
0x14003ccd6  pop     r14
0x14003ccd8  pop     r13
0x14003ccda  pop     r12
0x14003ccdc  pop     rdi
0x14003ccdd  pop     rsi
0x14003ccde  pop     rbp
0x14003ccdf  retn
```

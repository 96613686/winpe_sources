# OncRpcSepEncryptMessage

- ea: `0x14000aac4`
- end: `0x14000aee6`
- name: `OncRpcSepEncryptMessage`
- size: `1058`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140009700`
- `0x14000993c`

## callees

- `0x140001100`
- `0x140001cac`
- `0x140001d60`
- `0x140001ef0`
- `0x1400020c0`
- `0x140002230`
- `0x140008968`
- `0x14000a1ec`
- `0x14000aac4`
- `0x140012838`
- `0x140015640`
- `0x140015840`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae65`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ae8b`
- `ksecdd!SealMessage` at `0x14000ac71`
- `ksecdd!SealMessage` at `0x14000ac71`
- `ksecdd!MapSecurityError` at `0x14000ac8a`
- `ksecdd!MapSecurityError` at `0x14000ac8a`

## pseudocode

```c
__int64 __fastcall OncRpcSepEncryptMessage(
        __int64 a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7,
        unsigned int a8,
        _DWORD *a9)
{
  _BYTE *v9; // r14
  PVOID v11; // r13
  int v12; // eax
  int v13; // r15d
  __int64 v14; // rcx
  PVOID v15; // rdi
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // eax
  SECURITY_STATUS v24; // ecx
  char *v25; // rsi
  __int64 DescriptorFromPtr; // rdi
  const void *v27; // rdx
  size_t v28; // r8
  __int64 v29; // rbx
  char *v30; // rsi
  bool v31; // zf
  __int64 v32; // rax
  __int64 v33; // rbx
  __int64 v34; // rdi
  _BYTE *v35; // rdx
  unsigned int v36; // r12d
  __int64 v37; // rcx
  __int64 v38; // rbx
  __int64 LastBufferDescriptor; // rax
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rbx
  PVOID v43; // r8
  _BYTE *v44; // rcx
  int v45; // eax
  __int64 v46; // r8
  unsigned int v47; // r8d
  unsigned int v48; // ecx
  __int64 v49; // rax
  PVOID P; // [rsp+30h] [rbp-C1h] BYREF
  PVOID v52; // [rsp+38h] [rbp-B9h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-B1h]
  PVOID v54; // [rsp+48h] [rbp-A9h]
  __int64 v55; // [rsp+50h] [rbp-A1h]
  __int64 v56; // [rsp+58h] [rbp-99h]
  PVOID v57; // [rsp+60h] [rbp-91h]
  __int64 v58; // [rsp+68h] [rbp-89h]
  __int64 v59; // [rsp+70h] [rbp-81h]
  __int128 v60; // [rsp+78h] [rbp-79h] BYREF
  __int64 v61; // [rsp+88h] [rbp-69h]
  _DWORD *v62; // [rsp+90h] [rbp-61h]
  _DWORD *v63; // [rsp+98h] [rbp-59h]
  _BYTE v64[64]; // [rsp+A0h] [rbp-51h] BYREF

  v9 = v64;
  v61 = a1;
  v11 = 0;
  v63 = a9;
  v55 = a4;
  v62 = a2;
  v58 = a3;
  v56 = a6;
  v60 = 0;
  v52 = v64;
  P = 0;
  v53 = OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(a3, a6, a7, 0);
  if ( v53 + 2 > 4 )
  {
    v12 = NfsMemMgrBufferAllocate(1, 1347241300, 16 * (v53 + 2), &v52);
    v9 = v52;
    v13 = v12;
    if ( v12 < 0 )
      goto LABEL_33;
  }
  v14 = *(_QWORD *)(a3 + 40);
  if ( v14 )
    v15 = *(PVOID *)(v14 + 64);
  else
    v15 = 0;
  v54 = v15;
  if ( (unsigned int)OncRpcBufMgrGetDescriptorAllocationLengthRemaining() >= a8 )
  {
    LODWORD(v52) = 0;
  }
  else
  {
    v16 = a8;
    if ( a8 <= 4 )
      v16 = 4;
    LODWORD(v52) = v16 + 4;
    v17 = NfsMemMgrBufferAllocate(512, 1885685586, (unsigned int)(v16 + 4), &P);
    v11 = P;
    v13 = v17;
    if ( v17 < 0 )
      goto LABEL_31;
    v15 = P;
    v54 = P;
  }
  v18 = v53;
  v57 = v11;
  LODWORD(v60) = 0;
  DWORD1(v60) = v53 + 2;
  *((_QWORD *)&v60 + 1) = v9;
  OncRpcBufMgrpContextConfigureSecBufsFromPtr(a3, v56, a7, (_DWORD)v9);
  v19 = v55;
  v20 = 16LL * v18;
  P = (PVOID)v20;
  *(_DWORD *)&v9[v20 + 4] = 2;
  *(_QWORD *)&v9[v20 + 8] = v19;
  *(_DWORD *)&v9[v20] = a5;
  v21 = v61;
  v22 = 16LL * (v18 + 1);
  v59 = v22;
  *(_DWORD *)&v9[v22 + 4] = 9;
  *(_QWORD *)&v9[v22 + 8] = v15;
  *(_DWORD *)&v9[v22] = a8;
  v23 = SealMessage(v21, 0, &v60, 0);
  *v62 = OncRpcSeSecStatusToGssMajor(v23);
  v13 = MapSecurityError(v24);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        24,
        WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids,
        (unsigned int)v13);
LABEL_31:
    if ( v11 )
      ExFreePoolWithTag(v11, 0x70654752u);
    goto LABEL_33;
  }
  v25 = (char *)(v55 + *(unsigned int *)&v9[(_QWORD)P]);
  DescriptorFromPtr = OncRpcBufMgrpContextGetDescriptorFromPtr(a3, v56, 0);
  v28 = (unsigned int)(*(_DWORD *)(DescriptorFromPtr + 64) - (_DWORD)v27);
  v29 = (unsigned int)v28;
  memmove(v25, v27, v28);
  v30 = &v25[v29];
  v31 = v57 == 0;
  *(_QWORD *)(DescriptorFromPtr + 64) = v30;
  if ( v31 )
  {
    v32 = OncRpcBufMgrpContextGetDescriptorFromPtr(v58, v54, 0);
    v33 = v59;
    v34 = v32;
    memmove(v30, *(const void **)&v9[v59 + 8], *(unsigned int *)&v9[v59]);
    *(_QWORD *)(v34 + 64) += *(unsigned int *)&v9[v33];
    v35 = *(_BYTE **)(v34 + 64);
    if ( ((*(_DWORD *)&v9[v33] + a7 + *(_DWORD *)&v9[(_QWORD)P]) & 3) != 0 )
    {
      v36 = 4 - ((*(_DWORD *)&v9[v33] + a7 + *(_DWORD *)&v9[(_QWORD)P]) & 3);
      v37 = v36;
      *(_QWORD *)(v34 + 64) = &v35[v36];
      if ( v36 )
      {
        do
        {
          *v35++ = 0;
          --v37;
        }
        while ( v37 );
      }
    }
  }
  else
  {
    v38 = v58;
    v13 = OncRpcBufMgrChainUserSuppliedBuffer(v58, (__int64)v11);
    if ( v13 >= 0 )
    {
      LastBufferDescriptor = OncRpcBufMgrGetLastBufferDescriptor(v38);
      *(_QWORD *)(v38 + 40) = LastBufferDescriptor;
      v40 = LastBufferDescriptor;
      v41 = LastBufferDescriptor ? *(_QWORD *)(LastBufferDescriptor + 56) : 0LL;
      v42 = v59;
      v43 = P;
      v44 = (_BYTE *)(*(unsigned int *)&v9[v59] + v41);
      *(_QWORD *)(LastBufferDescriptor + 64) = v44;
      v45 = ((_BYTE)a7 + v9[(_QWORD)v43] + v9[v42]) & 3;
      if ( (((_BYTE)a7 + v9[(_QWORD)v43] + v9[v42]) & 3) != 0 )
      {
        v46 = (unsigned int)(4 - v45);
        *(_QWORD *)(v40 + 64) = &v44[v46];
        if ( 4 != v45 )
        {
          do
          {
            *v44++ = 0;
            --v46;
          }
          while ( v46 );
        }
      }
    }
  }
  v47 = 0;
  v48 = 0;
  if ( v53 != -2 )
  {
    do
    {
      v49 = v48++;
      v47 += *(_DWORD *)&v9[16 * v49];
    }
    while ( v48 < v53 + 2 );
  }
  *v63 = _byteswap_ulong(v47);
  if ( v13 < 0 )
    goto LABEL_31;
LABEL_33:
  if ( v9 != v64 )
    ExFreePoolWithTag(v9, 0x504D4554u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14000aac4  push    rbp
0x14000aac6  push    rbx
0x14000aac7  push    rsi
0x14000aac8  push    rdi
0x14000aac9  push    r12
0x14000aacb  push    r13
0x14000aacd  push    r14
0x14000aacf  push    r15
0x14000aad1  lea     rbp, [rsp-7]
0x14000aad6  sub     rsp, 0F8h
0x14000aadd  mov     rax, cs:__security_cookie
0x14000aae4  xor     rax, rsp
0x14000aae7  mov     [rbp+3Fh+var_50], rax
0x14000aaeb  mov     rax, [rbp+3Fh+arg_28]
0x14000aaef  lea     r14, [rbp+3Fh+var_90]
0x14000aaf3  mov     rbx, r8
0x14000aaf6  mov     [rbp+3Fh+var_A8], rcx
0x14000aafa  mov     rcx, [rbp+3Fh+arg_40]
0x14000ab01  xorps   xmm0, xmm0
0x14000ab04  mov     r8d, [rbp+3Fh+arg_30]
0x14000ab08  xor     r13d, r13d
0x14000ab0b  mov     [rbp+3Fh+var_98], rcx
0x14000ab0f  mov     rcx, rbx
0x14000ab12  mov     [rsp+130h+var_E0], r9
0x14000ab17  xor     r9d, r9d
0x14000ab1a  mov     [rbp+3Fh+var_A0], rdx
0x14000ab1e  mov     rdx, rax
0x14000ab21  mov     [rsp+130h+var_C8], rbx
0x14000ab26  mov     [rsp+130h+var_D8], rax
0x14000ab2b  movups  [rbp+3Fh+var_B8], xmm0
0x14000ab2f  mov     [rsp+130h+var_F8], r14
0x14000ab34  mov     [rsp+130h+P], r13
0x14000ab39  call    OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr
0x14000ab3e  mov     [rsp+130h+var_F0], eax
0x14000ab42  lea     r12d, [r13+4]
0x14000ab46  add     eax, 2
0x14000ab49  lea     rdi, WPP_GLOBAL_Control
0x14000ab50  cmp     eax, r12d
0x14000ab53  jbe     short loc_14000AB7F
0x14000ab55  mov     r8d, eax
0x14000ab58  lea     r9, [rsp+130h+var_F8]
0x14000ab5d  shl     r8d, 4
0x14000ab61  lea     ecx, [r13+1]
0x14000ab65  mov     edx, 504D4554h
0x14000ab6a  call    NfsMemMgrBufferAllocate
0x14000ab6f  mov     r14, [rsp+130h+var_F8]
0x14000ab74  mov     r15d, eax
0x14000ab77  test    eax, eax
0x14000ab79  js      loc_14000AE7A
0x14000ab7f  mov     rcx, [rbx+28h]
0x14000ab83  test    rcx, rcx
0x14000ab86  jnz     short loc_14000AB8C
0x14000ab88  xor     edi, edi
0x14000ab8a  jmp     short loc_14000AB90
0x14000ab8c  mov     rdi, [rcx+40h]
0x14000ab90  mov     [rsp+130h+var_E8], rdi
0x14000ab95  call    OncRpcBufMgrGetDescriptorAllocationLengthRemaining
0x14000ab9a  mov     esi, [rbp+3Fh+arg_38]
0x14000aba0  cmp     eax, esi
0x14000aba2  jnb     short loc_14000ABE5
0x14000aba4  mov     eax, esi
0x14000aba6  lea     r9, [rsp+130h+P]
0x14000abab  cmp     esi, r12d
0x14000abae  mov     edx, 70654752h
0x14000abb3  mov     ecx, 200h
0x14000abb8  cmovbe  eax, r12d
0x14000abbc  add     eax, r12d
0x14000abbf  mov     r8d, eax
0x14000abc2  mov     dword ptr [rsp+130h+var_F8], eax
0x14000abc6  call    NfsMemMgrBufferAllocate
0x14000abcb  mov     r13, [rsp+130h+P]
0x14000abd0  mov     r15d, eax
0x14000abd3  test    eax, eax
0x14000abd5  js      loc_14000AE51
0x14000abdb  mov     rdi, r13
0x14000abde  mov     [rsp+130h+var_E8], r13
0x14000abe3  jmp     short loc_14000ABEA
0x14000abe5  mov     dword ptr [rsp+130h+var_F8], r13d
0x14000abea  mov     r15d, [rsp+130h+var_F0]
0x14000abef  mov     r9, r14
0x14000abf2  mov     r8d, [rbp+3Fh+arg_30]
0x14000abf6  mov     rcx, rbx
0x14000abf9  mov     rdx, [rsp+130h+var_D8]
0x14000abfe  mov     [rsp+130h+var_D0], r13
0x14000ac03  lea     eax, [r15+2]
0x14000ac07  mov     dword ptr [rbp+3Fh+var_B8], 0
0x14000ac0e  mov     dword ptr [rbp+3Fh+var_B8+4], eax
0x14000ac11  mov     qword ptr [rbp+3Fh+var_B8+8], r14
0x14000ac15  mov     byte ptr [rsp+130h+var_108], 0
0x14000ac1a  call    OncRpcBufMgrpContextConfigureSecBufsFromPtr
0x14000ac1f  mov     rax, [rsp+130h+var_E0]
0x14000ac24  lea     r8, [rbp+3Fh+var_B8]
0x14000ac28  mov     ecx, r15d
0x14000ac2b  xor     r9d, r9d
0x14000ac2e  shl     rcx, 4
0x14000ac32  xor     edx, edx
0x14000ac34  mov     [rsp+130h+P], rcx
0x14000ac39  mov     dword ptr [rcx+r14+4], 2
0x14000ac42  mov     [rcx+r14+8], rax
0x14000ac47  mov     eax, [rbp+3Fh+arg_20]
0x14000ac4a  mov     [rcx+r14], eax
0x14000ac4e  lea     eax, [r15+1]
0x14000ac52  mov     rcx, [rbp+3Fh+var_A8]
0x14000ac56  shl     rax, 4
0x14000ac5a  mov     [rsp+130h+var_C0], rax
0x14000ac5f  mov     dword ptr [rax+r14+4], 9
0x14000ac68  mov     [rax+r14+8], rdi
0x14000ac6d  mov     [rax+r14], esi
0x14000ac71  call    cs:__imp_SealMessage
0x14000ac78  nop     dword ptr [rax+rax+00h]
0x14000ac7d  mov     ecx, eax
0x14000ac7f  call    OncRpcSeSecStatusToGssMajor
0x14000ac84  mov     rdx, [rbp+3Fh+var_A0]
0x14000ac88  mov     [rdx], eax
0x14000ac8a  call    cs:__imp_MapSecurityError
0x14000ac91  nop     dword ptr [rax+rax+00h]
0x14000ac96  mov     r15d, eax
0x14000ac99  test    eax, eax
0x14000ac9b  jns     short loc_14000ACDC
0x14000ac9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aca4  lea     rdi, WPP_GLOBAL_Control
0x14000acab  cmp     rcx, rdi
0x14000acae  jz      loc_14000AE58
0x14000acb4  mov     eax, [rcx+2Ch]
0x14000acb7  test    al, 40h
0x14000acb9  jz      loc_14000AE58
0x14000acbf  mov     rcx, [rcx+18h]
0x14000acc3  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000acca  mov     edx, 18h
0x14000accf  mov     r9d, r15d
0x14000acd2  call    WPP_SF_d
0x14000acd7  jmp     loc_14000AE58
0x14000acdc  mov     rax, [rsp+130h+P]
0x14000ace1  xor     r8d, r8d
0x14000ace4  mov     rdx, [rsp+130h+var_D8]
0x14000ace9  mov     rcx, rbx
0x14000acec  mov     esi, [rax+r14]
0x14000acf0  add     rsi, [rsp+130h+var_E0]
0x14000acf5  call    OncRpcBufMgrpContextGetDescriptorFromPtr
0x14000acfa  mov     rcx, rsi; void *
0x14000acfd  mov     rdi, rax
0x14000ad00  mov     r8d, [rax+40h]
0x14000ad04  sub     r8d, edx; Size
0x14000ad07  mov     ebx, r8d
0x14000ad0a  call    memmove
0x14000ad0f  add     rsi, rbx
0x14000ad12  cmp     [rsp+130h+var_D0], 0
0x14000ad18  mov     [rdi+40h], rsi
0x14000ad1c  jnz     short loc_14000AD93
0x14000ad1e  mov     rdx, [rsp+130h+var_E8]
0x14000ad23  xor     r8d, r8d
0x14000ad26  mov     rcx, [rsp+130h+var_C8]
0x14000ad2b  call    OncRpcBufMgrpContextGetDescriptorFromPtr
0x14000ad30  mov     rbx, [rsp+130h+var_C0]
0x14000ad35  mov     rcx, rsi; void *
0x14000ad38  mov     rdi, rax
0x14000ad3b  mov     r8d, [rbx+r14]; Size
0x14000ad3f  mov     rdx, [rbx+r14+8]; Src
0x14000ad44  call    memmove
0x14000ad49  mov     ecx, [rbx+r14]
0x14000ad4d  add     [rdi+40h], rcx
0x14000ad51  mov     rax, [rsp+130h+P]
0x14000ad56  mov     rdx, [rdi+40h]
0x14000ad5a  mov     ecx, [rax+r14]
0x14000ad5e  add     ecx, [rbp+3Fh+arg_30]
0x14000ad61  add     ecx, [rbx+r14]
0x14000ad65  and     ecx, 3
0x14000ad68  jz      loc_14000AE24
0x14000ad6e  sub     r12d, ecx
0x14000ad71  mov     ecx, r12d
0x14000ad74  lea     rax, [rdx+r12]
0x14000ad78  mov     [rdi+40h], rax
0x14000ad7c  jz      loc_14000AE24
0x14000ad82  mov     byte ptr [rdx], 0
0x14000ad85  inc     rdx
0x14000ad88  sub     rcx, 1
0x14000ad8c  jnz     short loc_14000AD82
0x14000ad8e  jmp     loc_14000AE24
0x14000ad93  mov     rbx, [rsp+130h+var_C8]
0x14000ad98  lea     rax, OncRpcSepFreePaddingBufferCallbackRoutine
0x14000ad9f  mov     r8d, dword ptr [rsp+130h+var_F8]
0x14000ada4  mov     rcx, rbx
0x14000ada7  mov     [rsp+130h+var_108], 0
0x14000adb0  xor     r9d, r9d
0x14000adb3  mov     rdx, r13
0x14000adb6  mov     [rsp+130h+var_110], rax
0x14000adbb  call    OncRpcBufMgrChainUserSuppliedBuffer
0x14000adc0  mov     r15d, eax
0x14000adc3  test    eax, eax
0x14000adc5  js      short loc_14000AE24
0x14000adc7  mov     rcx, rbx
0x14000adca  call    OncRpcBufMgrGetLastBufferDescriptor
0x14000adcf  mov     [rbx+28h], rax
0x14000add3  mov     rdx, rax
0x14000add6  test    rax, rax
0x14000add9  jnz     short loc_14000ADDF
0x14000addb  xor     ecx, ecx
0x14000addd  jmp     short loc_14000ADE3
0x14000addf  mov     rcx, [rax+38h]
0x14000ade3  mov     rbx, [rsp+130h+var_C0]
0x14000ade8  mov     r8, [rsp+130h+P]
0x14000aded  mov     eax, [rbx+r14]
0x14000adf1  add     rcx, rax
0x14000adf4  mov     [rdx+40h], rcx
0x14000adf8  mov     eax, [rbx+r14]
0x14000adfc  add     eax, [r8+r14]
0x14000ae00  add     eax, [rbp+3Fh+arg_30]
0x14000ae03  and     eax, 3
0x14000ae06  jz      short loc_14000AE24
0x14000ae08  sub     r12d, eax
0x14000ae0b  mov     r8d, r12d
0x14000ae0e  lea     rax, [rcx+r12]
0x14000ae12  mov     [rdx+40h], rax
0x14000ae16  jz      short loc_14000AE24
0x14000ae18  mov     byte ptr [rcx], 0
0x14000ae1b  inc     rcx
0x14000ae1e  sub     r8, 1
0x14000ae22  jnz     short loc_14000AE18
0x14000ae24  mov     edx, [rsp+130h+var_F0]
0x14000ae28  xor     r8d, r8d
0x14000ae2b  xor     ecx, ecx
0x14000ae2d  add     edx, 2
0x14000ae30  jz      short loc_14000AE42
0x14000ae32  mov     eax, ecx
0x14000ae34  inc     ecx
0x14000ae36  shl     rax, 4
0x14000ae3a  add     r8d, [rax+r14]
0x14000ae3e  cmp     ecx, edx
0x14000ae40  jb      short loc_14000AE32
0x14000ae42  mov     rax, [rbp+3Fh+var_98]
0x14000ae46  bswap   r8d
0x14000ae49  mov     [rax], r8d
0x14000ae4c  test    r15d, r15d
0x14000ae4f  jns     short loc_14000AE73
0x14000ae51  lea     rdi, WPP_GLOBAL_Control
0x14000ae58  test    r13, r13
0x14000ae5b  jz      short loc_14000AE7A
0x14000ae5d  mov     edx, 70654752h; Tag
0x14000ae62  mov     rcx, r13; P
0x14000ae65  call    cs:__imp_ExFreePoolWithTag
0x14000ae6c  nop     dword ptr [rax+rax+00h]
0x14000ae71  jmp     short loc_14000AE7A
0x14000ae73  lea     rdi, WPP_GLOBAL_Control
0x14000ae7a  lea     rax, [rbp+3Fh+var_90]
0x14000ae7e  cmp     r14, rax
0x14000ae81  jz      short loc_14000AE97
0x14000ae83  mov     edx, 504D4554h; Tag
0x14000ae88  mov     rcx, r14; P
0x14000ae8b  call    cs:__imp_ExFreePoolWithTag
0x14000ae92  nop     dword ptr [rax+rax+00h]
0x14000ae97  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae9e  cmp     rcx, rdi
0x14000aea1  jz      short loc_14000AEC2
0x14000aea3  mov     eax, [rcx+2Ch]
0x14000aea6  test    al, 1
0x14000aea8  jz      short loc_14000AEC2
0x14000aeaa  mov     rcx, [rcx+18h]
0x14000aeae  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000aeb5  mov     edx, 19h
0x14000aeba  mov     r9d, r15d
0x14000aebd  call    WPP_SF_d
0x14000aec2  mov     eax, r15d
0x14000aec5  mov     rcx, [rbp+3Fh+var_50]
0x14000aec9  xor     rcx, rsp; StackCookie
0x14000aecc  call    __security_check_cookie
0x14000aed1  add     rsp, 0F8h
0x14000aed8  pop     r15
0x14000aeda  pop     r14
0x14000aedc  pop     r13
0x14000aede  pop     r12
0x14000aee0  pop     rdi
0x14000aee1  pop     rsi
0x14000aee2  pop     rbx
0x14000aee3  pop     rbp
0x14000aee4  retn
```

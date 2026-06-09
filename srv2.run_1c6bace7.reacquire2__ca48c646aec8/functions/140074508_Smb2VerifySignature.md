# Smb2VerifySignature

- ea: `0x140074508`
- end: `0x14007489d`
- name: `Smb2VerifySignature`
- size: `917`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140073ab0`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x1400222ec`
- `0x140022958`
- `0x140038490`
- `0x140038560`
- `0x140074508`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140074731`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140074731`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x1400745ce`
- `srvnet!SmbCryptoSigningAlgRequireIV` at `0x1400745ce`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x1400745fb`
- `srvnet!SmbCryptoCalculateAndSetIV` at `0x1400745fb`
- `ksecdd!BCryptDuplicateHash` at `0x1400745b6`
- `ksecdd!BCryptDuplicateHash` at `0x1400745b6`
- `ksecdd!BCryptHashData` at `0x140074645`
- `ksecdd!BCryptHashData` at `0x140074645`
- `ksecdd!BCryptFinishHash` at `0x140074677`
- `ksecdd!BCryptFinishHash` at `0x140074677`
- `ksecdd!BCryptDestroyHash` at `0x1400746da`
- `ksecdd!BCryptDestroyHash` at `0x1400746da`

## pseudocode

```c
__int64 __fastcall Smb2VerifySignature(__int64 a1, void *a2)
{
  __int64 v2; // rax
  __int64 v3; // r8
  ULONG v5; // r14d
  __int64 v6; // r13
  struct _MDL *v7; // rdi
  void *v8; // r12
  unsigned int v9; // ebp
  ULONG v10; // ebx
  UCHAR *SigningHashObject; // rax
  UCHAR *v12; // r15
  NTSTATUS v13; // ebx
  __int64 v14; // r9
  UCHAR *MappedSystemVa; // rax
  ULONG ByteCount; // ebp
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  __int64 v19; // rdx
  PDEVICE_OBJECT v20; // r10
  BCRYPT_HASH_HANDLE phNewHash; // [rsp+30h] [rbp-88h] BYREF
  ULONG cbOutput; // [rsp+38h] [rbp-80h]
  void *Buf1; // [rsp+40h] [rbp-78h]
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-70h] BYREF
  __int128 v25; // [rsp+58h] [rbp-60h]

  v2 = *(_QWORD *)(a1 + 304);
  v3 = *(_QWORD *)(a1 + 560);
  v5 = *(_DWORD *)(a1 + 404);
  Buf1 = a2;
  v6 = *(_QWORD *)(v2 + 24);
  v7 = *(struct _MDL **)(v2 + 56);
  v8 = *(void **)(v3 + 112);
  v9 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL) + 140LL);
  phNewHash = 0;
  *(_OWORD *)pbOutput = 0;
  v25 = 0;
  v10 = *(_DWORD *)(v3 + 120);
  cbOutput = *(_DWORD *)(v3 + 124);
  if ( !v8 )
    __int2c();
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(v10);
  v12 = SigningHashObject;
  if ( !SigningHashObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1);
    }
LABEL_23:
    v13 = -1073741670;
    goto LABEL_17;
  }
  v13 = BCryptDuplicateHash(v8, &phNewHash, SigningHashObject, v10, 0);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v19 = 17;
LABEL_49:
      WPP_SF_qD(AttachedDevice, v19, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1, v13);
    }
  }
  else
  {
    if ( !(unsigned __int8)SmbCryptoSigningAlgRequireIV(v9)
      || (LOBYTE(v14) = *(_WORD *)(v6 + 12) == 12,
          v13 = SmbCryptoCalculateAndSetIV(v9, *(_QWORD *)(v6 + 24), 0, v14, phNewHash),
          v13 >= 0) )
    {
      while ( 1 )
      {
        if ( (v7->MdlFlags & 5) != 0 )
          MappedSystemVa = (UCHAR *)v7->MappedSystemVa;
        else
          MappedSystemVa = (UCHAR *)MmMapLockedPagesSpecifyCache(v7, 0, MmCached, 0, 0, 0x40000010u);
        ByteCount = v5;
        if ( v5 >= v7->ByteCount )
          ByteCount = v7->ByteCount;
        if ( !MappedSystemVa )
          goto LABEL_23;
        v7 = v7->Next;
        v13 = BCryptHashData(phNewHash, MappedSystemVa, ByteCount, 0);
        if ( v13 < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 19;
            goto LABEL_48;
          }
          goto LABEL_17;
        }
        if ( v7 )
        {
          v5 -= ByteCount;
          if ( v5 )
            continue;
        }
        v13 = BCryptFinishHash(phNewHash, pbOutput, cbOutput, 0);
        if ( v13 < 0 )
        {
          v20 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v19 = 20;
            goto LABEL_48;
          }
        }
        else if ( memcmp(Buf1, pbOutput, 0x10u) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids, a1);
          }
          v13 = -1073741790;
        }
        goto LABEL_17;
      }
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v19 = 18;
LABEL_48:
      AttachedDevice = v20->AttachedDevice;
      goto LABEL_49;
    }
  }
LABEL_17:
  if ( phNewHash )
  {
    BCryptDestroyHash(phNewHash);
    phNewHash = 0;
  }
  if ( v12 )
    Smb2DeallocateSigningHashObject(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140074508  push    rbx
0x14007450a  push    rbp
0x14007450b  push    rsi
0x14007450c  push    rdi
0x14007450d  push    r12
0x14007450f  push    r13
0x140074511  push    r14
0x140074513  push    r15
0x140074515  sub     rsp, 78h
0x140074519  mov     rax, cs:__security_cookie
0x140074520  xor     rax, rsp
0x140074523  mov     [rsp+0B8h+var_50], rax
0x140074528  mov     rax, [rcx+130h]
0x14007452f  xorps   xmm0, xmm0
0x140074532  mov     r8, [rcx+230h]
0x140074539  mov     rsi, rcx
0x14007453c  mov     r14d, [rcx+194h]
0x140074543  mov     [rsp+0B8h+Buf1], rdx
0x140074548  mov     r13, [rax+18h]
0x14007454c  mov     rdi, [rax+38h]
0x140074550  mov     r12, [r8+70h]
0x140074554  mov     rax, [rcx+60h]
0x140074558  mov     rcx, [rax+1F0h]
0x14007455f  mov     ebp, [rcx+8Ch]
0x140074565  mov     [rsp+0B8h+phNewHash], 0
0x14007456e  movups  xmmword ptr [rsp+0B8h+pbOutput], xmm0
0x140074573  movups  [rsp+0B8h+var_60], xmm0
0x140074578  mov     eax, [r8+7Ch]
0x14007457c  mov     ebx, [r8+78h]
0x140074580  mov     [rsp+0B8h+cbOutput], eax
0x140074584  test    r12, r12
0x140074587  jz      loc_140074742
0x14007458d  mov     ecx, ebx
0x14007458f  call    Smb2AllocateSigningHashObject
0x140074594  mov     r15, rax
0x140074597  test    rax, rax
0x14007459a  jz      loc_1400746FB
0x1400745a0  mov     r9d, ebx; cbHashObject
0x1400745a3  mov     [rsp+0B8h+dwFlags], 0; dwFlags
0x1400745ab  mov     r8, rax; pbHashObject
0x1400745ae  lea     rdx, [rsp+0B8h+phNewHash]; phNewHash
0x1400745b3  mov     rcx, r12; hHash
0x1400745b6  call    cs:__imp_BCryptDuplicateHash
0x1400745bd  nop     dword ptr [rax+rax+00h]
0x1400745c2  mov     ebx, eax
0x1400745c4  test    eax, eax
0x1400745c6  js      loc_140074773
0x1400745cc  mov     ecx, ebp
0x1400745ce  call    cs:__imp_SmbCryptoSigningAlgRequireIV
0x1400745d5  nop     dword ptr [rax+rax+00h]
0x1400745da  test    al, al
0x1400745dc  jz      short loc_140074611
0x1400745de  cmp     word ptr [r13+0Ch], 0Ch
0x1400745e4  mov     ecx, ebp
0x1400745e6  mov     rax, [rsp+0B8h+phNewHash]
0x1400745eb  mov     rdx, [r13+18h]
0x1400745ef  setz    r9b
0x1400745f3  xor     r8d, r8d
0x1400745f6  mov     qword ptr [rsp+0B8h+dwFlags], rax
0x1400745fb  call    cs:__imp_SmbCryptoCalculateAndSetIV
0x140074602  nop     dword ptr [rax+rax+00h]
0x140074607  mov     ebx, eax
0x140074609  test    eax, eax
0x14007460b  js      loc_1400747AE
0x140074611  test    byte ptr [rdi+0Ah], 5
0x140074615  jz      loc_140074715
0x14007461b  mov     rax, [rdi+18h]
0x14007461f  mov     ecx, [rdi+28h]
0x140074622  mov     ebp, r14d
0x140074625  cmp     r14d, ecx
0x140074628  cmovnb  ebp, ecx
0x14007462b  test    rax, rax
0x14007462e  jz      loc_14007470E
0x140074634  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x140074639  xor     r9d, r9d; dwFlags
0x14007463c  mov     rdi, [rdi]
0x14007463f  mov     r8d, ebp; cbInput
0x140074642  mov     rdx, rax; pbInput
0x140074645  call    cs:__imp_BCryptHashData
0x14007464c  nop     dword ptr [rax+rax+00h]
0x140074651  mov     ebx, eax
0x140074653  test    eax, eax
0x140074655  js      loc_140074865
0x14007465b  test    rdi, rdi
0x14007465e  jz      short loc_140074665
0x140074660  sub     r14d, ebp
0x140074663  jnz     short loc_140074611
0x140074665  mov     r8d, [rsp+0B8h+cbOutput]; cbOutput
0x14007466a  lea     rdx, [rsp+0B8h+pbOutput]; pbOutput
0x14007466f  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x140074674  xor     r9d, r9d; dwFlags
0x140074677  call    cs:__imp_BCryptFinishHash
0x14007467e  nop     dword ptr [rax+rax+00h]
0x140074683  mov     ebx, eax
0x140074685  test    eax, eax
0x140074687  js      loc_1400747E1
0x14007468d  mov     rcx, [rsp+0B8h+Buf1]; Buf1
0x140074692  lea     rdx, [rsp+0B8h+pbOutput]; Buf2
0x140074697  mov     r8d, 10h; Size
0x14007469d  call    memcmp
0x1400746a2  test    eax, eax
0x1400746a4  jnz     loc_140074819
0x1400746aa  mov     rcx, [rsp+0B8h+phNewHash]; hHash
0x1400746af  test    rcx, rcx
0x1400746b2  jnz     short loc_1400746DA
0x1400746b4  test    r15, r15
0x1400746b7  jnz     short loc_1400746F1
0x1400746b9  mov     eax, ebx
0x1400746bb  mov     rcx, [rsp+0B8h+var_50]
0x1400746c0  xor     rcx, rsp; StackCookie
0x1400746c3  call    __security_check_cookie
0x1400746c8  add     rsp, 78h
0x1400746cc  pop     r15
0x1400746ce  pop     r14
0x1400746d0  pop     r13
0x1400746d2  pop     r12
0x1400746d4  pop     rdi
0x1400746d5  pop     rsi
0x1400746d6  pop     rbp
0x1400746d7  pop     rbx
0x1400746d8  retn
0x1400746da  call    cs:__imp_BCryptDestroyHash
0x1400746e1  nop     dword ptr [rax+rax+00h]
0x1400746e6  mov     [rsp+0B8h+phNewHash], 0
0x1400746ef  jmp     short loc_1400746B4
0x1400746f1  mov     rcx, r15
0x1400746f4  call    Smb2DeallocateSigningHashObject
0x1400746f9  jmp     short loc_1400746B9
0x1400746fb  mov     r10, cs:WPP_GLOBAL_Control
0x140074702  lea     rcx, WPP_GLOBAL_Control
0x140074709  cmp     r10, rcx
0x14007470c  jnz     short loc_140074749
0x14007470e  mov     ebx, 0C000009Ah
0x140074713  jmp     short loc_1400746AA
0x140074715  xor     r9d, r9d; RequestedAddress
0x140074718  mov     [rsp+0B8h+Priority], 40000010h; Priority
0x140074720  xor     edx, edx; AccessMode
0x140074722  mov     [rsp+0B8h+dwFlags], 0; BugCheckOnFailure
0x14007472a  mov     rcx, rdi; MemoryDescriptorList
0x14007472d  lea     r8d, [r9+1]; CacheType
0x140074731  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140074738  nop     dword ptr [rax+rax+00h]
0x14007473d  jmp     loc_14007461F
0x140074742  int     2Ch; Windows NT - assertion failure
0x140074744  jmp     loc_14007458D
0x140074749  mov     ecx, [r10+2Ch]
0x14007474d  test    cl, 1
0x140074750  jz      short loc_14007470E
0x140074752  cmp     byte ptr [r10+29h], 1
0x140074757  jb      short loc_14007470E
0x140074759  mov     rcx, [r10+18h]
0x14007475d  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140074764  mov     edx, 10h
0x140074769  mov     r9, rsi
0x14007476c  call    WPP_SF_q
0x140074771  jmp     short loc_14007470E
0x140074773  mov     rax, cs:WPP_GLOBAL_Control
0x14007477a  lea     rcx, WPP_GLOBAL_Control
0x140074781  cmp     rax, rcx
0x140074784  jz      loc_1400746AA
0x14007478a  mov     edx, [rax+2Ch]
0x14007478d  test    dl, 1
0x140074790  jz      loc_1400746AA
0x140074796  cmp     byte ptr [rax+29h], 1
0x14007479a  jb      loc_1400746AA
0x1400747a0  mov     rcx, [rax+18h]
0x1400747a4  mov     edx, 11h
0x1400747a9  jmp     loc_140096A2B
0x1400747ae  mov     r10, cs:WPP_GLOBAL_Control
0x1400747b5  lea     rcx, WPP_GLOBAL_Control
0x1400747bc  cmp     r10, rcx
0x1400747bf  jz      loc_1400746AA
0x1400747c5  mov     eax, [r10+2Ch]
0x1400747c9  test    al, 1
0x1400747cb  jz      loc_1400746AA
0x1400747d1  cmp     byte ptr [r10+29h], 1
0x1400747d6  jb      loc_1400746AA
0x1400747dc  jmp     loc_140096A22
0x1400747e1  mov     r10, cs:WPP_GLOBAL_Control
0x1400747e8  lea     rcx, WPP_GLOBAL_Control
0x1400747ef  cmp     r10, rcx
0x1400747f2  jz      loc_1400746AA
0x1400747f8  mov     eax, [r10+2Ch]
0x1400747fc  test    al, 1
0x1400747fe  jz      loc_1400746AA
0x140074804  cmp     byte ptr [r10+29h], 1
0x140074809  jb      loc_1400746AA
0x14007480f  mov     edx, 14h
0x140074814  jmp     loc_140096A27
0x140074819  mov     r10, cs:WPP_GLOBAL_Control
0x140074820  lea     rcx, WPP_GLOBAL_Control
0x140074827  cmp     r10, rcx
0x14007482a  jz      loc_140096A44
0x140074830  mov     eax, [r10+2Ch]
0x140074834  test    al, 1
0x140074836  jz      loc_140096A44
0x14007483c  cmp     byte ptr [r10+29h], 1
0x140074841  jb      loc_140096A44
0x140074847  mov     rcx, [r10+18h]
0x14007484b  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140074852  mov     edx, 15h
0x140074857  mov     r9, rsi
0x14007485a  call    WPP_SF_q
0x14007485f  nop
0x140074860  jmp     loc_140096A44
0x140074865  mov     r10, cs:WPP_GLOBAL_Control
0x14007486c  lea     rcx, WPP_GLOBAL_Control
0x140074873  cmp     r10, rcx
0x140074876  jz      loc_1400746AA
0x14007487c  mov     eax, [r10+2Ch]
0x140074880  test    al, 1
0x140074882  jz      loc_1400746AA
0x140074888  cmp     byte ptr [r10+29h], 1
0x14007488d  jb      loc_1400746AA
0x140074893  mov     edx, 13h
0x140074898  jmp     loc_140096A27
0x140096a22  mov     edx, 12h
0x140096a27  mov     rcx, [r10+18h]
0x140096a2b  lea     r8, WPP_6d4e5bfc4720373e45ea9239f13f904a_Traceguids
0x140096a32  mov     [rsp+0B8h+dwFlags], ebx
0x140096a36  mov     r9, rsi
0x140096a39  call    WPP_SF_qD
0x140096a3e  nop
0x140096a3f  jmp     loc_1400746AA
0x140096a44  mov     ebx, 0C0000022h
0x140096a49  jmp     loc_1400746AA
```

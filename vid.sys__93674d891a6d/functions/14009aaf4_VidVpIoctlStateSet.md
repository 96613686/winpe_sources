# VidVpIoctlStateSet

- ea: `0x14009aaf4`
- end: `0x14009aed8`
- name: `VidVpIoctlStateSet`
- size: `996`
- prototype: `__int64 __fastcall(int, int, int, int, char, volatile void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1400321a4`

## callees

- `0x140011518`
- `0x140012bc0`
- `0x140021c60`
- `0x14002f724`
- `0x1400347a4`
- `0x1400347d4`
- `0x14007a110`
- `0x14007a908`
- `0x14007a960`
- `0x14009aaf4`
- `0x14009cc7c`
- `0x1400ceb0c`
- `0x1400f0730`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14009abbf`
- `ntoskrnl!ProbeForRead` at `0x14009abdb`
- `ntoskrnl!ProbeForRead` at `0x14009abbf`
- `ntoskrnl!ProbeForRead` at `0x14009abdb`
- `winhvr!WinHvSetVpRegisters` at `0x14009ad82`
- `winhvr!WinHvSetVpRegisters` at `0x14009ad82`

## pseudocode

```c
__int64 __fastcall VidVpIoctlStateSet(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        volatile void *a4,
        unsigned __int8 a5,
        volatile void *a6)
{
  char v9; // r12
  unsigned __int8 v10; // r14
  int v11; // edi
  char *v12; // r15
  unsigned __int8 v13; // r13
  __int64 v14; // r8
  __int64 i; // rcx
  int v16; // edx
  __int64 j; // rax
  _QWORD *v18; // r9
  __int64 v21; // [rsp+48h] [rbp-310h] BYREF
  volatile void *Address; // [rsp+50h] [rbp-308h]
  void *Src; // [rsp+58h] [rbp-300h]
  __int64 v24[2]; // [rsp+60h] [rbp-2F8h] BYREF
  size_t v25; // [rsp+70h] [rbp-2E8h] BYREF
  __int64 v26; // [rsp+78h] [rbp-2E0h] BYREF
  size_t v27; // [rsp+80h] [rbp-2D8h]
  _DWORD v28[32]; // [rsp+90h] [rbp-2C8h] BYREF
  _OWORD v29[32]; // [rsp+110h] [rbp-248h] BYREF

  Address = a4;
  v24[1] = a1;
  Src = (void *)a6;
  v21 = 0;
  v24[0] = -1;
  v26 = 0;
  v9 = 0;
  v10 = a5;
  if ( (unsigned __int8)(a5 - 1) > 0x7Fu )
  {
    v11 = -1073741811;
    goto LABEL_35;
  }
  if ( a3 < 0x800 )
  {
    VidObjectLockAcquireShared(a1);
    v9 = 1;
    v11 = VidVpLookup(a1, a2, &v25);
    if ( v11 >= 0 )
    {
      v12 = (char *)Address;
      ProbeForRead(Address, 4LL * a5, 1u);
      ProbeForRead(a6, 16LL * a5, 1u);
      do
      {
        v13 = 32;
        if ( v10 < 0x20u )
          v13 = v10;
        v27 = 4LL * v13;
        RtlCopyFromUser(v28, v12, v27);
        v25 = 16LL * v13;
        RtlCopyFromUser(v29, Src, v25);
        for ( i = 0; (unsigned int)i < v13; i = (unsigned int)(i + 1) )
        {
          v16 = v28[i];
          if ( (v16 & 0xFFFFFFFC) == 0 && v16 != 2 )
            goto LABEL_3;
        }
        if ( (a3 & 0x700) != 0 && (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0 )
          goto LABEL_3;
        if ( (a3 & 0x700) != 0 && (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0x20 )
        {
          if ( (a3 & 0x700) != 0x100 )
            goto LABEL_3;
          v11 = VsmmSvcImportVpState(a1, a2, a3, (unsigned int)v28, (__int64)v29, v13);
          if ( v11 < 0 )
            break;
        }
        else
        {
          if ( (*(_DWORD *)(a1 + 32) & 0x1E0LL) == 0x40 )
          {
            for ( j = 0; (unsigned int)j < v13; j = (unsigned int)(j + 1) )
            {
              if ( v28[j] == 589888 )
              {
                v18 = &v29[(unsigned int)j];
                if ( *v18 )
                {
                  v11 = VidSnpHandleSevControlRegisterSet(a1, a2, a3, (_DWORD)v18, 3, (__int64)&v21, (__int64)v24);
                  if ( v11 < 0 )
                    goto LABEL_35;
                  break;
                }
                if ( v10 != 1 )
                  goto LABEL_3;
                v11 = VidSnpPartitionReset(a1, 480);
                goto LABEL_35;
              }
            }
          }
          LOBYTE(v14) = a3;
          v11 = WinHvSetVpRegisters(*(_QWORD *)(a1 + 648), a2, v14, v13, v28, v29, &v26);
          if ( v11 < 0 )
            break;
          if ( v21 )
          {
            VidSnpSevControlUpdateVpState(a1, a2, a3, 589888, v21, v24[0]);
            v21 = 0;
          }
        }
        v12 = (char *)Address + v27;
        Address = (char *)Address + v27;
        Src = (char *)Src + v25;
        v10 -= v13;
      }
      while ( v10 );
    }
LABEL_35:
    if ( v11 >= 0 )
      goto LABEL_38;
    goto LABEL_36;
  }
LABEL_3:
  v11 = -1073741811;
LABEL_36:
  if ( v21 )
    VsmmGpaRangeUnlockMbpByGpa(a1, v24[0], v21);
LABEL_38:
  if ( v9 )
    VidObjectLockRelease(a1);
  if ( v11 < 0 )
    VidTraceErrorStatusInternal0(
      "VidVpIoctlStateSet",
      "onecore\\vm\\vid\\sys\\driver\\vidvpioctl.c",
      783,
      (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14009aaf4  push    rbx
0x14009aaf6  push    rsi
0x14009aaf7  push    rdi
0x14009aaf8  push    r12
0x14009aafa  push    r13
0x14009aafc  push    r14
0x14009aafe  push    r15
0x14009ab00  sub     rsp, 320h
0x14009ab07  mov     rax, cs:__security_cookie
0x14009ab0e  xor     rax, rsp
0x14009ab11  mov     [rsp+358h+var_48], rax
0x14009ab19  mov     [rsp+358h+Address], r9
0x14009ab1e  mov     ebx, r8d
0x14009ab21  mov     r15d, edx
0x14009ab24  mov     [rsp+358h+var_314], edx
0x14009ab28  mov     rsi, rcx
0x14009ab2b  mov     [rsp+358h+var_2F0], rcx
0x14009ab30  mov     r13, [rsp+358h+arg_28]
0x14009ab38  mov     [rsp+358h+Src], r13
0x14009ab3d  mov     [rsp+358h+var_310], 0
0x14009ab46  mov     [rsp+358h+var_2F8], 0FFFFFFFFFFFFFFFFh
0x14009ab4f  mov     [rsp+358h+var_2E0], 0
0x14009ab58  xor     r12b, r12b
0x14009ab5b  movzx   r14d, [rsp+358h+arg_20]
0x14009ab64  lea     eax, [r14-1]
0x14009ab68  cmp     al, 7Fh
0x14009ab6a  ja      loc_14009AE27
0x14009ab70  cmp     ebx, 800h
0x14009ab76  jb      short loc_14009AB84
0x14009ab78  mov     edi, 0C000000Dh
0x14009ab7d  xor     bl, bl
0x14009ab7f  jmp     loc_14009AE32
0x14009ab84  call    VidObjectLockAcquireShared
0x14009ab89  mov     r12b, 1
0x14009ab8c  lea     r8, [rsp+358h+var_2E8]
0x14009ab91  mov     edx, r15d
0x14009ab94  mov     rcx, rsi
0x14009ab97  call    VidVpLookup
0x14009ab9c  mov     edi, eax
0x14009ab9e  test    eax, eax
0x14009aba0  js      loc_14009AE2C
0x14009aba6  mov     rdi, r14
0x14009aba9  lea     rdx, ds:0[r14*4]; Length
0x14009abb1  mov     r8d, 1; Alignment
0x14009abb7  mov     r15, [rsp+358h+Address]
0x14009abbc  mov     rcx, r15; Address
0x14009abbf  call    cs:__imp_ProbeForRead
0x14009abc6  nop     dword ptr [rax+rax+00h]
0x14009abcb  shl     rdi, 4
0x14009abcf  mov     r8d, 1; Alignment
0x14009abd5  mov     rdx, rdi; Length
0x14009abd8  mov     rcx, r13; Address
0x14009abdb  call    cs:__imp_ProbeForRead
0x14009abe2  nop     dword ptr [rax+rax+00h]
0x14009abe7  nop
0x14009abe8  mov     r13d, 20h ; ' '
0x14009abee  movzx   eax, r14b
0x14009abf2  cmp     r14b, r13b
0x14009abf5  cmovb   r13d, eax
0x14009abf9  movzx   edi, r13b
0x14009abfd  lea     rax, ds:0[rdi*4]
0x14009ac05  mov     [rsp+358h+var_2D8], rax
0x14009ac0d  mov     r8, rax; Size
0x14009ac10  mov     rdx, r15; Src
0x14009ac13  lea     rcx, [rsp+358h+var_2C8]; void *
0x14009ac1b  call    RtlCopyFromUser
0x14009ac20  shl     rdi, 4
0x14009ac24  mov     [rsp+358h+var_2E8], rdi
0x14009ac29  mov     r8, rdi; Size
0x14009ac2c  mov     rdx, [rsp+358h+Src]; Src
0x14009ac31  lea     rcx, [rsp+358h+var_248]; void *
0x14009ac39  call    RtlCopyFromUser
0x14009ac3e  nop
0x14009ac3f  xor     ecx, ecx
0x14009ac41  movzx   r15d, r13b
0x14009ac45  cmp     ecx, r15d
0x14009ac48  jnb     short loc_14009AC66
0x14009ac4a  mov     edx, [rsp+rcx*4+358h+var_2C8]
0x14009ac51  test    edx, 0FFFFFFFCh
0x14009ac57  jnz     short loc_14009AC62
0x14009ac59  cmp     edx, 2
0x14009ac5c  jnz     loc_14009AB78
0x14009ac62  inc     ecx
0x14009ac64  jmp     short loc_14009AC45
0x14009ac66  mov     ecx, ebx
0x14009ac68  and     ecx, 700h
0x14009ac6e  mov     edx, 1E0h
0x14009ac73  jz      short loc_14009AC81
0x14009ac75  mov     eax, [rsi+20h]
0x14009ac78  test    rdx, rax
0x14009ac7b  jz      loc_14009AB78
0x14009ac81  test    ecx, ecx
0x14009ac83  jz      short loc_14009ACD5
0x14009ac85  mov     eax, [rsi+20h]
0x14009ac88  and     rax, rdx
0x14009ac8b  cmp     rax, 20h ; ' '
0x14009ac8f  jnz     short loc_14009ACD5
0x14009ac91  cmp     ecx, 100h
0x14009ac97  jnz     loc_14009AB78
0x14009ac9d  mov     dword ptr [rsp+358h+var_330], r15d
0x14009aca2  lea     rax, [rsp+358h+var_248]
0x14009acaa  mov     [rsp+358h+var_338], rax
0x14009acaf  lea     r9, [rsp+358h+var_2C8]
0x14009acb7  mov     r8d, ebx
0x14009acba  mov     edx, [rsp+358h+var_314]
0x14009acbe  mov     rcx, rsi
0x14009acc1  call    VsmmSvcImportVpState
0x14009acc6  mov     edi, eax
0x14009acc8  test    eax, eax
0x14009acca  js      loc_14009AE2C
0x14009acd0  jmp     loc_14009ADCE
0x14009acd5  mov     eax, [rsi+20h]
0x14009acd8  and     rax, rdx
0x14009acdb  cmp     rax, 40h ; '@'
0x14009acdf  jnz     short loc_14009AD49
0x14009ace1  xor     eax, eax
0x14009ace3  cmp     eax, r15d
0x14009ace6  jnb     short loc_14009AD49
0x14009ace8  mov     ecx, eax
0x14009acea  cmp     [rsp+rax*4+358h+var_2C8], 90040h
0x14009acf5  jz      short loc_14009ACFB
0x14009acf7  inc     eax
0x14009acf9  jmp     short loc_14009ACE3
0x14009acfb  shl     rcx, 4
0x14009acff  lea     r9, [rsp+358h+var_248]
0x14009ad07  add     r9, rcx
0x14009ad0a  cmp     qword ptr [r9], 0
0x14009ad0e  jz      loc_14009ADF5
0x14009ad14  lea     rax, [rsp+358h+var_2F8]
0x14009ad19  mov     [rsp+358h+var_328], rax
0x14009ad1e  lea     rax, [rsp+358h+var_310]
0x14009ad23  mov     [rsp+358h+var_330], rax
0x14009ad28  mov     dword ptr [rsp+358h+var_338], 3
0x14009ad30  mov     r8d, ebx
0x14009ad33  mov     edx, [rsp+358h+var_314]
0x14009ad37  mov     rcx, rsi
0x14009ad3a  call    VidSnpHandleSevControlRegisterSet
0x14009ad3f  mov     edi, eax
0x14009ad41  test    eax, eax
0x14009ad43  js      loc_14009AE2C
0x14009ad49  lea     rax, [rsp+358h+var_2E0]
0x14009ad4e  mov     [rsp+358h+var_328], rax
0x14009ad53  lea     rax, [rsp+358h+var_248]
0x14009ad5b  mov     [rsp+358h+var_330], rax
0x14009ad60  lea     rax, [rsp+358h+var_2C8]
0x14009ad68  mov     [rsp+358h+var_338], rax
0x14009ad6d  mov     r9d, r15d
0x14009ad70  mov     r8b, bl
0x14009ad73  mov     r15d, [rsp+358h+var_314]
0x14009ad78  mov     edx, r15d
0x14009ad7b  mov     rcx, [rsi+288h]
0x14009ad82  call    cs:__imp_WinHvSetVpRegisters
0x14009ad89  nop     dword ptr [rax+rax+00h]
0x14009ad8e  mov     edi, eax
0x14009ad90  test    eax, eax
0x14009ad92  js      loc_14009AE2C
0x14009ad98  mov     r8, [rsp+358h+var_310]
0x14009ad9d  test    r8, r8
0x14009ada0  jz      short loc_14009ADCE
0x14009ada2  mov     rax, [rsp+358h+var_2F8]
0x14009ada7  mov     [rsp+358h+var_330], rax
0x14009adac  mov     [rsp+358h+var_338], r8
0x14009adb1  mov     r9d, 90040h
0x14009adb7  mov     r8d, ebx
0x14009adba  mov     edx, r15d
0x14009adbd  mov     rcx, rsi
0x14009adc0  call    VidSnpSevControlUpdateVpState
0x14009adc5  mov     [rsp+358h+var_310], 0
0x14009adce  mov     r15, [rsp+358h+Address]
0x14009add3  add     r15, [rsp+358h+var_2D8]
0x14009addb  mov     [rsp+358h+Address], r15
0x14009ade0  mov     rax, [rsp+358h+var_2E8]
0x14009ade5  add     [rsp+358h+Src], rax
0x14009adea  sub     r14b, r13b
0x14009aded  jnz     loc_14009ABE8
0x14009adf3  jmp     short loc_14009AE2C
0x14009adf5  cmp     r14b, 1
0x14009adf9  jnz     loc_14009AB78
0x14009adff  mov     rcx, rsi
0x14009ae02  call    VidSnpPartitionReset
0x14009ae07  mov     edi, eax
0x14009ae09  jmp     short loc_14009AE2C
0x14009ae0b  mov     edi, eax
0x14009ae0d  mov     bl, 1
0x14009ae0f  mov     r12b, bl
0x14009ae12  mov     rsi, [rsp+358h+var_2F0]
0x14009ae17  jmp     short loc_14009AE2E
0x14009ae19  mov     edi, eax
0x14009ae1b  mov     bl, 1
0x14009ae1d  mov     r12b, bl
0x14009ae20  mov     rsi, [rsp+358h+var_2F0]
0x14009ae25  jmp     short loc_14009AE2E
0x14009ae27  mov     edi, 0C000000Dh
0x14009ae2c  xor     bl, bl
0x14009ae2e  test    edi, edi
0x14009ae30  jns     short loc_14009AE49
0x14009ae32  mov     r8, [rsp+358h+var_310]
0x14009ae37  test    r8, r8
0x14009ae3a  jz      short loc_14009AE49
0x14009ae3c  mov     rdx, [rsp+358h+var_2F8]
0x14009ae41  mov     rcx, rsi
0x14009ae44  call    VsmmGpaRangeUnlockMbpByGpa
0x14009ae49  test    r12b, r12b
0x14009ae4c  jz      short loc_14009AE56
0x14009ae4e  mov     rcx, rsi
0x14009ae51  call    VidObjectLockRelease
0x14009ae56  test    bl, bl
0x14009ae58  jz      short loc_14009AE92
0x14009ae5a  lea     rax, WPP_GLOBAL_Control
0x14009ae61  mov     rcx, cs:WPP_GLOBAL_Control
0x14009ae68  cmp     rcx, rax
0x14009ae6b  jz      short loc_14009AE92
0x14009ae6d  mov     eax, [rcx+2Ch]
0x14009ae70  test    al, 2
0x14009ae72  jz      short loc_14009AE92
0x14009ae74  cmp     byte ptr [rcx+29h], 2
0x14009ae78  jb      short loc_14009AE92
0x14009ae7a  mov     edx, 0Eh
0x14009ae7f  mov     r9d, edi
0x14009ae82  lea     r8, WPP_f3c8146851b33f019037d8521c1ed030_Traceguids
0x14009ae89  mov     rcx, [rcx+18h]
0x14009ae8d  call    WPP_SF_d
0x14009ae92  test    edi, edi
0x14009ae94  jns     short loc_14009AEB2
0x14009ae96  mov     r9d, edi
0x14009ae99  mov     r8d, 30Fh
0x14009ae9f  lea     rdx, aOnecoreVmVidSy_13; "onecore\\vm\\vid\\sys\\driver\\vidvpioc"...
0x14009aea6  lea     rcx, aVidvpioctlstat; "VidVpIoctlStateSet"
0x14009aead  call    VidTraceErrorStatusInternal0
0x14009aeb2  mov     eax, edi
0x14009aeb4  mov     rcx, [rsp+358h+var_48]
0x14009aebc  xor     rcx, rsp; StackCookie
0x14009aebf  call    __security_check_cookie
0x14009aec4  add     rsp, 320h
0x14009aecb  pop     r15
0x14009aecd  pop     r14
0x14009aecf  pop     r13
0x14009aed1  pop     r12
0x14009aed3  pop     rdi
0x14009aed4  pop     rsi
0x14009aed5  pop     rbx
0x14009aed6  retn
```

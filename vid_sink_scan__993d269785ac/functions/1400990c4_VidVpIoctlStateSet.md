# VidVpIoctlStateSet

- ea: `0x1400990c4`
- end: `0x1400994a8`
- name: `VidVpIoctlStateSet`
- size: `996`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, volatile void *, unsigned __int8, volatile void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x140031fa4`

## callees

- `0x1400116c8`
- `0x140012b3c`
- `0x140021650`
- `0x14002f524`
- `0x140034554`
- `0x140034584`
- `0x140079234`
- `0x140079a2c`
- `0x140079a84`
- `0x1400990c4`
- `0x14009b24c`
- `0x1400cc350`
- `0x1400eda50`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x14009918f`
- `ntoskrnl!ProbeForRead` at `0x1400991ab`
- `ntoskrnl!ProbeForRead` at `0x14009918f`
- `ntoskrnl!ProbeForRead` at `0x1400991ab`
- `winhvr!WinHvSetVpRegisters` at `0x140099352`
- `winhvr!WinHvSetVpRegisters` at `0x140099352`

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
    VidObjectLockAcquireShared();
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
    VsmmGpaRangeUnlockMbpByGpa(a1, v24[0]);
LABEL_38:
  if ( v9 )
    VidObjectLockRelease(a1);
  if ( v11 < 0 )
    VidTraceErrorStatusInternal0("VidVpIoctlStateSet", "onecore\\vm\\vid\\sys\\driver\\vidvpioctl.c", 783);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400990c4  push    rbx
0x1400990c6  push    rsi
0x1400990c7  push    rdi
0x1400990c8  push    r12
0x1400990ca  push    r13
0x1400990cc  push    r14
0x1400990ce  push    r15
0x1400990d0  sub     rsp, 320h
0x1400990d7  mov     rax, cs:__security_cookie
0x1400990de  xor     rax, rsp
0x1400990e1  mov     [rsp+358h+var_48], rax
0x1400990e9  mov     [rsp+358h+Address], r9
0x1400990ee  mov     ebx, r8d
0x1400990f1  mov     r15d, edx
0x1400990f4  mov     [rsp+358h+var_314], edx
0x1400990f8  mov     rsi, rcx
0x1400990fb  mov     [rsp+358h+var_2F0], rcx
0x140099100  mov     r13, [rsp+358h+arg_28]
0x140099108  mov     [rsp+358h+Src], r13
0x14009910d  mov     [rsp+358h+var_310], 0
0x140099116  mov     [rsp+358h+var_2F8], 0FFFFFFFFFFFFFFFFh
0x14009911f  mov     [rsp+358h+var_2E0], 0
0x140099128  xor     r12b, r12b
0x14009912b  movzx   r14d, [rsp+358h+arg_20]
0x140099134  lea     eax, [r14-1]
0x140099138  cmp     al, 7Fh
0x14009913a  ja      loc_1400993F7
0x140099140  cmp     ebx, 800h
0x140099146  jb      short loc_140099154
0x140099148  mov     edi, 0C000000Dh
0x14009914d  xor     bl, bl
0x14009914f  jmp     loc_140099402
0x140099154  call    VidObjectLockAcquireShared
0x140099159  mov     r12b, 1
0x14009915c  lea     r8, [rsp+358h+var_2E8]
0x140099161  mov     edx, r15d
0x140099164  mov     rcx, rsi
0x140099167  call    VidVpLookup
0x14009916c  mov     edi, eax
0x14009916e  test    eax, eax
0x140099170  js      loc_1400993FC
0x140099176  mov     rdi, r14
0x140099179  lea     rdx, ds:0[r14*4]; Length
0x140099181  mov     r8d, 1; Alignment
0x140099187  mov     r15, [rsp+358h+Address]
0x14009918c  mov     rcx, r15; Address
0x14009918f  call    cs:__imp_ProbeForRead
0x140099196  nop     dword ptr [rax+rax+00h]
0x14009919b  shl     rdi, 4
0x14009919f  mov     r8d, 1; Alignment
0x1400991a5  mov     rdx, rdi; Length
0x1400991a8  mov     rcx, r13; Address
0x1400991ab  call    cs:__imp_ProbeForRead
0x1400991b2  nop     dword ptr [rax+rax+00h]
0x1400991b7  nop
0x1400991b8  mov     r13d, 20h ; ' '
0x1400991be  movzx   eax, r14b
0x1400991c2  cmp     r14b, r13b
0x1400991c5  cmovb   r13d, eax
0x1400991c9  movzx   edi, r13b
0x1400991cd  lea     rax, ds:0[rdi*4]
0x1400991d5  mov     [rsp+358h+var_2D8], rax
0x1400991dd  mov     r8, rax; Size
0x1400991e0  mov     rdx, r15; Src
0x1400991e3  lea     rcx, [rsp+358h+var_2C8]; void *
0x1400991eb  call    RtlCopyFromUser
0x1400991f0  shl     rdi, 4
0x1400991f4  mov     [rsp+358h+var_2E8], rdi
0x1400991f9  mov     r8, rdi; Size
0x1400991fc  mov     rdx, [rsp+358h+Src]; Src
0x140099201  lea     rcx, [rsp+358h+var_248]; void *
0x140099209  call    RtlCopyFromUser
0x14009920e  nop
0x14009920f  xor     ecx, ecx
0x140099211  movzx   r15d, r13b
0x140099215  cmp     ecx, r15d
0x140099218  jnb     short loc_140099236
0x14009921a  mov     edx, [rsp+rcx*4+358h+var_2C8]
0x140099221  test    edx, 0FFFFFFFCh
0x140099227  jnz     short loc_140099232
0x140099229  cmp     edx, 2
0x14009922c  jnz     loc_140099148
0x140099232  inc     ecx
0x140099234  jmp     short loc_140099215
0x140099236  mov     ecx, ebx
0x140099238  and     ecx, 700h
0x14009923e  mov     edx, 1E0h
0x140099243  jz      short loc_140099251
0x140099245  mov     eax, [rsi+20h]
0x140099248  test    rdx, rax
0x14009924b  jz      loc_140099148
0x140099251  test    ecx, ecx
0x140099253  jz      short loc_1400992A5
0x140099255  mov     eax, [rsi+20h]
0x140099258  and     rax, rdx
0x14009925b  cmp     rax, 20h ; ' '
0x14009925f  jnz     short loc_1400992A5
0x140099261  cmp     ecx, 100h
0x140099267  jnz     loc_140099148
0x14009926d  mov     dword ptr [rsp+358h+var_330], r15d
0x140099272  lea     rax, [rsp+358h+var_248]
0x14009927a  mov     [rsp+358h+var_338], rax
0x14009927f  lea     r9, [rsp+358h+var_2C8]
0x140099287  mov     r8d, ebx
0x14009928a  mov     edx, [rsp+358h+var_314]
0x14009928e  mov     rcx, rsi
0x140099291  call    VsmmSvcImportVpState
0x140099296  mov     edi, eax
0x140099298  test    eax, eax
0x14009929a  js      loc_1400993FC
0x1400992a0  jmp     loc_14009939E
0x1400992a5  mov     eax, [rsi+20h]
0x1400992a8  and     rax, rdx
0x1400992ab  cmp     rax, 40h ; '@'
0x1400992af  jnz     short loc_140099319
0x1400992b1  xor     eax, eax
0x1400992b3  cmp     eax, r15d
0x1400992b6  jnb     short loc_140099319
0x1400992b8  mov     ecx, eax
0x1400992ba  cmp     [rsp+rax*4+358h+var_2C8], 90040h
0x1400992c5  jz      short loc_1400992CB
0x1400992c7  inc     eax
0x1400992c9  jmp     short loc_1400992B3
0x1400992cb  shl     rcx, 4
0x1400992cf  lea     r9, [rsp+358h+var_248]
0x1400992d7  add     r9, rcx
0x1400992da  cmp     qword ptr [r9], 0
0x1400992de  jz      loc_1400993C5
0x1400992e4  lea     rax, [rsp+358h+var_2F8]
0x1400992e9  mov     [rsp+358h+var_328], rax
0x1400992ee  lea     rax, [rsp+358h+var_310]
0x1400992f3  mov     [rsp+358h+var_330], rax
0x1400992f8  mov     dword ptr [rsp+358h+var_338], 3
0x140099300  mov     r8d, ebx
0x140099303  mov     edx, [rsp+358h+var_314]
0x140099307  mov     rcx, rsi
0x14009930a  call    VidSnpHandleSevControlRegisterSet
0x14009930f  mov     edi, eax
0x140099311  test    eax, eax
0x140099313  js      loc_1400993FC
0x140099319  lea     rax, [rsp+358h+var_2E0]
0x14009931e  mov     [rsp+358h+var_328], rax
0x140099323  lea     rax, [rsp+358h+var_248]
0x14009932b  mov     [rsp+358h+var_330], rax
0x140099330  lea     rax, [rsp+358h+var_2C8]
0x140099338  mov     [rsp+358h+var_338], rax
0x14009933d  mov     r9d, r15d
0x140099340  mov     r8b, bl
0x140099343  mov     r15d, [rsp+358h+var_314]
0x140099348  mov     edx, r15d
0x14009934b  mov     rcx, [rsi+288h]
0x140099352  call    cs:__imp_WinHvSetVpRegisters
0x140099359  nop     dword ptr [rax+rax+00h]
0x14009935e  mov     edi, eax
0x140099360  test    eax, eax
0x140099362  js      loc_1400993FC
0x140099368  mov     r8, [rsp+358h+var_310]
0x14009936d  test    r8, r8
0x140099370  jz      short loc_14009939E
0x140099372  mov     rax, [rsp+358h+var_2F8]
0x140099377  mov     [rsp+358h+var_330], rax
0x14009937c  mov     [rsp+358h+var_338], r8
0x140099381  mov     r9d, 90040h
0x140099387  mov     r8d, ebx
0x14009938a  mov     edx, r15d
0x14009938d  mov     rcx, rsi
0x140099390  call    VidSnpSevControlUpdateVpState
0x140099395  mov     [rsp+358h+var_310], 0
0x14009939e  mov     r15, [rsp+358h+Address]
0x1400993a3  add     r15, [rsp+358h+var_2D8]
0x1400993ab  mov     [rsp+358h+Address], r15
0x1400993b0  mov     rax, [rsp+358h+var_2E8]
0x1400993b5  add     [rsp+358h+Src], rax
0x1400993ba  sub     r14b, r13b
0x1400993bd  jnz     loc_1400991B8
0x1400993c3  jmp     short loc_1400993FC
0x1400993c5  cmp     r14b, 1
0x1400993c9  jnz     loc_140099148
0x1400993cf  mov     rcx, rsi
0x1400993d2  call    VidSnpPartitionReset
0x1400993d7  mov     edi, eax
0x1400993d9  jmp     short loc_1400993FC
0x1400993db  mov     edi, eax
0x1400993dd  mov     bl, 1
0x1400993df  mov     r12b, bl
0x1400993e2  mov     rsi, [rsp+358h+var_2F0]
0x1400993e7  jmp     short loc_1400993FE
0x1400993e9  mov     edi, eax
0x1400993eb  mov     bl, 1
0x1400993ed  mov     r12b, bl
0x1400993f0  mov     rsi, [rsp+358h+var_2F0]
0x1400993f5  jmp     short loc_1400993FE
0x1400993f7  mov     edi, 0C000000Dh
0x1400993fc  xor     bl, bl
0x1400993fe  test    edi, edi
0x140099400  jns     short loc_140099419
0x140099402  mov     r8, [rsp+358h+var_310]
0x140099407  test    r8, r8
0x14009940a  jz      short loc_140099419
0x14009940c  mov     rdx, [rsp+358h+var_2F8]
0x140099411  mov     rcx, rsi
0x140099414  call    VsmmGpaRangeUnlockMbpByGpa
0x140099419  test    r12b, r12b
0x14009941c  jz      short loc_140099426
0x14009941e  mov     rcx, rsi
0x140099421  call    VidObjectLockRelease
0x140099426  test    bl, bl
0x140099428  jz      short loc_140099462
0x14009942a  lea     rax, WPP_GLOBAL_Control
0x140099431  mov     rcx, cs:WPP_GLOBAL_Control
0x140099438  cmp     rcx, rax
0x14009943b  jz      short loc_140099462
0x14009943d  mov     eax, [rcx+2Ch]
0x140099440  test    al, 2
0x140099442  jz      short loc_140099462
0x140099444  cmp     byte ptr [rcx+29h], 2
0x140099448  jb      short loc_140099462
0x14009944a  mov     edx, 0Eh
0x14009944f  mov     r9d, edi
0x140099452  lea     r8, WPP_d1d52df2f618343a97df75412feab325_Traceguids
0x140099459  mov     rcx, [rcx+18h]
0x14009945d  call    WPP_SF_d
0x140099462  test    edi, edi
0x140099464  jns     short loc_140099482
0x140099466  mov     r9d, edi
0x140099469  mov     r8d, 30Fh
0x14009946f  lea     rdx, aOnecoreVmVidSy_13; "onecore\\vm\\vid\\sys\\driver\\vidvpioc"...
0x140099476  lea     rcx, aVidvpioctlstat; "VidVpIoctlStateSet"
0x14009947d  call    VidTraceErrorStatusInternal0
0x140099482  mov     eax, edi
0x140099484  mov     rcx, [rsp+358h+var_48]
0x14009948c  xor     rcx, rsp; StackCookie
0x14009948f  call    __security_check_cookie
0x140099494  add     rsp, 320h
0x14009949b  pop     r15
0x14009949d  pop     r14
0x14009949f  pop     r13
0x1400994a1  pop     r12
0x1400994a3  pop     rdi
0x1400994a4  pop     rsi
0x1400994a5  pop     rbx
0x1400994a6  retn
```

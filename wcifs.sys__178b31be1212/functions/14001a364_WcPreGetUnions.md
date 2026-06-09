# WcPreGetUnions

- ea: `0x14001a364`
- end: `0x14001a624`
- name: `WcPreGetUnions`
- size: `704`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400231a0`

## callees

- `0x140004058`
- `0x140004198`
- `0x140004d7c`
- `0x140007c90`
- `0x140007cb0`
- `0x14001443c`
- `0x14001a364`
- `0x14001f488`

## import_xrefs

- `ntoskrnl!PsIsHostSilo` at `0x14001a3b1`
- `ntoskrnl!PsIsHostSilo` at `0x14001a3b1`
- `ntoskrnl!ProbeForRead` at `0x14001a536`
- `ntoskrnl!ProbeForRead` at `0x14001a536`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001a3a2`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14001a3a2`
- `ntoskrnl!ProbeForWrite` at `0x14001a54e`
- `ntoskrnl!ProbeForWrite` at `0x14001a54e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a602`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001a602`
- `ntoskrnl!ExAllocatePool2` at `0x14001a4d3`
- `ntoskrnl!ExAllocatePool2` at `0x14001a4d3`

## pseudocode

```c
__int64 __fastcall WcPreGetUnions(__int64 a1)
{
  void *Pool2; // rdi
  unsigned int v3; // r14d
  __int64 v4; // rax
  SIZE_T v5; // r13
  SIZE_T v6; // r12
  unsigned int *v7; // r15
  __int64 CurrentServerSilo; // rax
  int v9; // ebx
  _UNKNOWN **v10; // rdx
  _UNKNOWN **v11; // rdx
  int v12; // r9d
  _UNKNOWN **v13; // rdx
  char v14; // r14
  __int64 v15; // rdx
  __int64 v16; // rax
  char v18; // [rsp+30h] [rbp-68h]
  char v19; // [rsp+38h] [rbp-60h]
  unsigned int v20; // [rsp+A8h] [rbp+10h] BYREF
  volatile void *Address; // [rsp+B0h] [rbp+18h]
  void *v22; // [rsp+B8h] [rbp+20h]

  Pool2 = 0;
  v3 = 0;
  v20 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  v5 = *(unsigned int *)(v4 + 32);
  v6 = *(unsigned int *)(v4 + 24);
  Address = *(volatile void **)(v4 + 48);
  v7 = *(unsigned int **)(v4 + 56);
  CurrentServerSilo = PsGetCurrentServerSilo();
  if ( (unsigned __int8)PsIsHostSilo(CurrentServerSilo) )
  {
    v9 = -1073741637;
    v10 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_sD(
        wil_details_featureDescriptors_a->DeviceExtension,
        (_DWORD)v10,
        14,
        10,
        (__int64)WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\fsctrl.c",
        55);
    }
    goto LABEL_24;
  }
  if ( (unsigned int)v5 < 0x18 )
  {
    v9 = -1073741811;
    v11 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
    v12 = 11;
    v19 = v5;
    v18 = 61;
    goto LABEL_8;
  }
  if ( (unsigned int)v6 < 0xC )
  {
    v9 = -1073741811;
    v11 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_24;
    v12 = 12;
    v19 = v6;
    v18 = 67;
LABEL_8:
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_sDdd(
      wil_details_featureDescriptors_a->DeviceExtension,
      (_DWORD)v11,
      14,
      v12,
      (__int64)WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\wcifs\\fsctrl.c",
      v18,
      v19,
      12);
    goto LABEL_24;
  }
  v9 = 0;
  Pool2 = (void *)ExAllocatePool2(256, v5, 1953317719);
  v22 = Pool2;
  if ( Pool2 )
  {
    v14 = *(_BYTE *)(a1 + 80);
    if ( v14 == 1 )
    {
      ProbeForRead(Address, v5, 1u);
      ProbeForWrite(v7, v6, 1u);
    }
    if ( v14 )
      RtlCopyFromUser(Pool2, (void *)Address, v5);
    else
      RtlCopyVolatileMemory(Pool2, (const void *)Address, v5);
    if ( v14 )
      RtlSetUserMemory(v7);
    else
      RtlSetVolatileMemory(v7, 0, v6);
    LOBYTE(v15) = v14;
    v7[1] = WcProcessGetUnions((__int64)Pool2 + 8, v15, v6, (__int64)v7, &v20);
    v3 = v20;
    *v7 = v20;
  }
  else
  {
    v9 = -1073741670;
    v13 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 2;
      WPP_RECORDER_SF_sD(
        wil_details_featureDescriptors_a->DeviceExtension,
        (_DWORD)v13,
        14,
        13,
        (__int64)WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\fsctrl.c",
        75);
    }
  }
LABEL_24:
  *(_DWORD *)(a1 + 24) = v9;
  if ( v9 >= 0 )
    v16 = v3;
  else
    v16 = 0;
  *(_QWORD *)(a1 + 32) = v16;
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x746D4357u);
  return 4;
}

```

## disassembly

```asm
0x14001a364  mov     rax, rsp
0x14001a367  mov     [rax+8], rcx
0x14001a36b  push    rbx
0x14001a36c  push    rsi
0x14001a36d  push    rdi
0x14001a36e  push    r12
0x14001a370  push    r13
0x14001a372  push    r14
0x14001a374  push    r15
0x14001a376  sub     rsp, 60h
0x14001a37a  mov     rsi, rcx
0x14001a37d  xor     edi, edi
0x14001a37f  xor     r14d, r14d
0x14001a382  mov     [rax+10h], r14d
0x14001a386  mov     rax, [rcx+10h]
0x14001a38a  mov     r13d, [rax+20h]
0x14001a38e  mov     r12d, [rax+18h]
0x14001a392  mov     rcx, [rax+30h]
0x14001a396  mov     [rsp+98h+Address], rcx
0x14001a39e  mov     r15, [rax+38h]
0x14001a3a2  call    cs:__imp_PsGetCurrentServerSilo
0x14001a3a9  nop     dword ptr [rax+rax+00h]
0x14001a3ae  mov     rcx, rax
0x14001a3b1  call    cs:__imp_PsIsHostSilo
0x14001a3b8  nop     dword ptr [rax+rax+00h]
0x14001a3bd  test    al, al
0x14001a3bf  jz      short loc_14001A41B
0x14001a3c1  mov     ebx, 0C00000BBh
0x14001a3c6  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001a3cd  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001a3d4  jz      loc_14001A5E3
0x14001a3da  lea     r9d, [rdi+0Ah]
0x14001a3de  mov     dword ptr [rsp+98h+var_68], 37h ; '7'
0x14001a3e6  mov     dl, 3
0x14001a3e8  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\wcifs\\fsctrl.c"
0x14001a3ef  mov     [rsp+98h+var_70], rax
0x14001a3f4  lea     rax, WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids
0x14001a3fb  mov     r8d, 0Eh
0x14001a401  mov     [rsp+98h+var_78], rax
0x14001a406  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001a40d  mov     rcx, [rcx+40h]
0x14001a411  call    WPP_RECORDER_SF_sD
0x14001a416  jmp     loc_14001A5E3
0x14001a41b  cmp     r13d, 18h
0x14001a41f  jnb     short loc_14001A48A
0x14001a421  mov     ebx, 0C000000Dh
0x14001a426  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001a42d  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001a434  jz      loc_14001A5E3
0x14001a43a  mov     r9d, 0Bh
0x14001a440  mov     [rsp+98h+var_58], 0Ch
0x14001a448  mov     dword ptr [rsp+98h+var_60], r13d
0x14001a44d  mov     dword ptr [rsp+98h+var_68], 3Dh ; '='
0x14001a455  lea     rax, aOnecoreBaseFsW_2; "onecore\\base\\fs\\wci\\wcifs\\fsctrl.c"
0x14001a45c  mov     [rsp+98h+var_70], rax
0x14001a461  lea     rax, WPP_c070de6cd2643f4183d5a0f659a39519_Traceguids
0x14001a468  mov     [rsp+98h+var_78], rax
0x14001a46d  mov     r8d, 0Eh
0x14001a473  mov     dl, 2
0x14001a475  mov     rcx, cs:wil_details_featureDescriptors_a
0x14001a47c  mov     rcx, [rcx+40h]
0x14001a480  call    WPP_RECORDER_SF_sDdd
0x14001a485  jmp     loc_14001A5E3
0x14001a48a  cmp     r12d, 0Ch
0x14001a48e  jnb     short loc_14001A4C3
0x14001a490  mov     ebx, 0C000000Dh
0x14001a495  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001a49c  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001a4a3  jz      loc_14001A5E3
0x14001a4a9  mov     r9d, 0Ch
0x14001a4af  mov     [rsp+98h+var_58], r9d
0x14001a4b4  mov     dword ptr [rsp+98h+var_60], r12d
0x14001a4b9  mov     dword ptr [rsp+98h+var_68], 43h ; 'C'
0x14001a4c1  jmp     short loc_14001A455
0x14001a4c3  xor     ebx, ebx
0x14001a4c5  mov     r8d, 746D4357h
0x14001a4cb  mov     rdx, r13
0x14001a4ce  mov     ecx, 100h
0x14001a4d3  call    cs:__imp_ExAllocatePool2
0x14001a4da  nop     dword ptr [rax+rax+00h]
0x14001a4df  mov     rdi, rax
0x14001a4e2  mov     [rsp+98h+arg_18], rax
0x14001a4ea  test    rax, rax
0x14001a4ed  jnz     short loc_14001A51B
0x14001a4ef  mov     ebx, 0C000009Ah
0x14001a4f4  lea     rdx, WPP_RECORDER_INITIALIZED
0x14001a4fb  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14001a502  jz      loc_14001A5E3
0x14001a508  lea     r9d, [rax+0Dh]
0x14001a50c  mov     dword ptr [rsp+98h+var_68], 4Bh ; 'K'
0x14001a514  mov     dl, 2
0x14001a516  jmp     loc_14001A3E8
0x14001a51b  mov     r14b, [rsi+50h]
0x14001a51f  cmp     r14b, 1
0x14001a523  jnz     short loc_14001A55A
0x14001a525  mov     r8d, 1; Alignment
0x14001a52b  mov     rdx, r13; Length
0x14001a52e  mov     rcx, [rsp+98h+Address]; Address
0x14001a536  call    cs:__imp_ProbeForRead
0x14001a53d  nop     dword ptr [rax+rax+00h]
0x14001a542  mov     rdx, r12; Length
0x14001a545  mov     r8d, 1; Alignment
0x14001a54b  mov     rcx, r15; Address
0x14001a54e  call    cs:__imp_ProbeForWrite
0x14001a555  nop     dword ptr [rax+rax+00h]
0x14001a55a  mov     r8, r13; Size
0x14001a55d  mov     rdx, [rsp+98h+Address]; Src
0x14001a565  mov     rcx, rdi; void *
0x14001a568  test    r14b, r14b
0x14001a56b  jz      short loc_14001A574
0x14001a56d  call    RtlCopyFromUser
0x14001a572  jmp     short loc_14001A579
0x14001a574  call    RtlCopyVolatileMemory
0x14001a579  mov     r8, r12; Size
0x14001a57c  xor     edx, edx; Val
0x14001a57e  mov     rcx, r15; void *
0x14001a581  test    r14b, r14b
0x14001a584  jz      short loc_14001A58D
0x14001a586  call    RtlSetUserMemory
0x14001a58b  jmp     short loc_14001A592
0x14001a58d  call    RtlSetVolatileMemory
0x14001a592  lea     rcx, [rdi+8]
0x14001a596  lea     rax, [rsp+98h+arg_8]
0x14001a59e  mov     [rsp+98h+var_78], rax
0x14001a5a3  mov     r9, r15
0x14001a5a6  mov     r8d, r12d
0x14001a5a9  mov     dl, r14b
0x14001a5ac  call    WcProcessGetUnions
0x14001a5b1  mov     [r15+4], eax
0x14001a5b5  mov     r14d, [rsp+98h+arg_8]
0x14001a5bd  mov     [r15], r14d
0x14001a5c0  jmp     short loc_14001A5E3
0x14001a5c2  mov     ebx, 0C0000005h
0x14001a5c7  mov     [rsp+98h+var_48], ebx
0x14001a5cb  mov     rsi, [rsp+98h+arg_0]
0x14001a5d3  mov     rdi, [rsp+98h+arg_18]
0x14001a5db  mov     r14d, [rsp+98h+arg_8]
0x14001a5e3  mov     [rsi+18h], ebx
0x14001a5e6  test    ebx, ebx
0x14001a5e8  jns     short loc_14001A5EE
0x14001a5ea  xor     eax, eax
0x14001a5ec  jmp     short loc_14001A5F1
0x14001a5ee  mov     eax, r14d
0x14001a5f1  mov     [rsi+20h], rax
0x14001a5f5  test    rdi, rdi
0x14001a5f8  jz      short loc_14001A60E
0x14001a5fa  mov     edx, 746D4357h; Tag
0x14001a5ff  mov     rcx, rdi; P
0x14001a602  call    cs:__imp_ExFreePoolWithTag
0x14001a609  nop     dword ptr [rax+rax+00h]
0x14001a60e  mov     eax, 4
0x14001a613  add     rsp, 60h
0x14001a617  pop     r15
0x14001a619  pop     r14
0x14001a61b  pop     r13
0x14001a61d  pop     r12
0x14001a61f  pop     rdi
0x14001a620  pop     rsi
0x14001a621  pop     rbx
0x14001a622  retn
```

# VidPartitionCreate

- ea: `0x140009988`
- end: `0x140009d17`
- name: `VidPartitionCreate`
- size: `911`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, void *Buf2, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x140009664`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x140008178`
- `0x140009988`
- `0x14000a4e0`
- `0x14000a510`
- `0x140011f20`
- `0x1400124a4`
- `0x140012554`
- `0x140021650`
- `0x1400217a0`
- `0x140030760`
- `0x140030790`
- `0x1400307d0`
- `0x140038630`
- `0x140083878`
- `0x14009a1a8`
- `0x14009a238`
- `0x1400f5860`
- `0x1400f7510`
- `0x1400f795c`
- `0x1400f8c40`
- `0x1400faca0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009c3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009c3c`
- `ntoskrnl!ExAllocatePool2` at `0x140009acc`
- `ntoskrnl!ExAllocatePool2` at `0x140009acc`

## string_xrefs

- `0x140009a4a`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140009aec`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140009c80`: `onecore\vm\vid\sys\driver\vidcreateclose.c`
- `0x140009a51`: `VidPartitionCreate`
- `0x140009af3`: `VidPartitionCreate`
- `0x140009c70`: `VidPartitionCreate`

## pseudocode

```c
__int64 __fastcall VidPartitionCreate(PCUNICODE_STRING SourceString, _OWORD *Buf2, __int64 a3, __int64 a4, char a5)
{
  PVOID v6; // rsi
  int v9; // edx
  int v10; // r8d
  __int64 v11; // r12
  __int64 v12; // rsi
  int v13; // r8d
  int v14; // r14d
  char *Pool2; // rax
  int v16; // r8d
  _QWORD *v18; // [rsp+30h] [rbp-81h] BYREF
  int v19; // [rsp+38h] [rbp-79h] BYREF
  _BYTE v20[32]; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v21[16]; // [rsp+60h] [rbp-51h] BYREF
  _BYTE v22[16]; // [rsp+70h] [rbp-41h] BYREF
  int *v23; // [rsp+80h] [rbp-31h]
  __int64 v24; // [rsp+88h] [rbp-29h]
  PVOID *v25; // [rsp+90h] [rbp-21h]
  __int64 v26; // [rsp+98h] [rbp-19h]
  _OWORD *v27; // [rsp+A0h] [rbp-11h]
  __int64 v28; // [rsp+A8h] [rbp-9h]

  v6 = VidDeviceExtension;
  v18 = VidDeviceExtension;
  v11 = *(char *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01015 + 2280))(
                    WdfDriverGlobals,
                    a4)
                + 64);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qSd(WPP_GLOBAL_Control->AttachedDevice, v9, v10, a3, (__int64)SourceString->Buffer, v11);
  }
  if ( !(_BYTE)v11 )
  {
    v12 = VidPartitionTableLookupAndReference(v6, Buf2, 1);
    if ( !v12 )
    {
      v14 = -1070137335;
      VidTraceErrorInternal0("VidPartitionCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 675);
      goto LABEL_28;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qSq(WPP_GLOBAL_Control->AttachedDevice, 14, v13, a3, (__int64)SourceString->Buffer, v12);
    }
    v14 = 0;
LABEL_25:
    *(_QWORD *)(a3 + 24) = v12 | v11;
    return (unsigned int)v14;
  }
  if ( a5 || (v14 = VidSidPartitionCheck(Buf2), v14 >= 0) )
  {
    Pool2 = (char *)ExAllocatePool2(64, 12816, 1917084758);
    v12 = (__int64)Pool2;
    if ( !Pool2 )
    {
      v14 = -1073741670;
      VidTraceErrorInternal0("VidPartitionCreate", "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c", 714);
      goto LABEL_28;
    }
    v14 = VidPartitionInitialize(Pool2, SourceString, Buf2);
    if ( v14 >= 0 )
    {
      if ( !a5 || (v14 = VidExoPartitionInitialize(v12), v14 >= 0) )
      {
        v14 = VidPartitionTableInsert(v18, v12);
        if ( v14 >= 0 )
        {
          VidBamReferencePowerPolicy();
          *(_QWORD *)(v12 + 808) = 1;
          *(_QWORD *)(v12 + 816) = 1;
          *(_QWORD *)(v12 + 800) = 1;
          VidOpCtrlUnblock(v12 + 704);
          VidReferencePartition(v12);
          VidOpCtrlStart((volatile signed __int32 *)VidDeviceExtension + 2);
          _InterlockedAdd64((volatile signed __int64 *)(v18[45] + 8LL), 1u);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_qSq(WPP_GLOBAL_Control->AttachedDevice, 15, v16, a3, (__int64)SourceString->Buffer, v12);
          }
          goto LABEL_25;
        }
      }
      VidThreadPoolDrain(v12 + 3488);
      VidThreadPoolTeardown(v12 + 3488);
      VidLockAcquireExclusive(v12 + 8);
      VidLockAcquireExclusive(v12 + 3744);
      VidPartitionUninitialize(v12);
      VidLockRelease(v12 + 3744);
      VidLockRelease(v12 + 8);
    }
    ExFreePoolWithTag((PVOID)v12, 0x72446456u);
  }
LABEL_28:
  if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
  {
    tlgCreate1Sz_char(v21, "VidPartitionCreate");
    tlgCreate1Sz_char(v22, "onecore\\vm\\vid\\sys\\driver\\vidcreateclose.c");
    v19 = 831;
    v23 = &v19;
    v24 = 4;
    v25 = (PVOID *)&v18;
    LODWORD(v18) = v14;
    v26 = 4;
    v27 = Buf2;
    v28 = 16;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, word_14004632A, 0, 0, 7, v20);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140009988  push    rbp
0x14000998a  push    rbx
0x14000998b  push    rsi
0x14000998c  push    rdi
0x14000998d  push    r12
0x14000998f  push    r13
0x140009991  push    r14
0x140009993  push    r15
0x140009995  lea     rbp, [rsp-17h]
0x14000999a  sub     rsp, 0C8h
0x1400099a1  mov     rax, cs:__security_cookie
0x1400099a8  xor     rax, rsp
0x1400099ab  mov     [rbp+4Fh+var_50], rax
0x1400099af  mov     rax, cs:WdfFunctions_01015
0x1400099b6  mov     r13, rdx
0x1400099b9  mov     rsi, cs:VidDeviceExtension
0x1400099c0  mov     r15, rcx
0x1400099c3  mov     rcx, cs:WdfDriverGlobals
0x1400099ca  mov     rdx, r9
0x1400099cd  mov     rdi, r8
0x1400099d0  mov     [rsp+100h+var_D0], rsi
0x1400099d5  mov     rax, [rax+8E8h]
0x1400099dc  call    _guard_dispatch_icall
0x1400099e1  movsx   r12, byte ptr [rax+40h]
0x1400099e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099ed  lea     r14, WPP_GLOBAL_Control
0x1400099f4  cmp     rcx, r14
0x1400099f7  jz      short loc_140009A20
0x1400099f9  mov     eax, [rcx+2Ch]
0x1400099fc  test    al, 2
0x1400099fe  jz      short loc_140009A20
0x140009a00  cmp     byte ptr [rcx+29h], 4
0x140009a04  jb      short loc_140009A20
0x140009a06  mov     rax, [r15+8]
0x140009a0a  mov     r9, rdi
0x140009a0d  mov     rcx, [rcx+18h]
0x140009a11  mov     dword ptr [rsp+100h+var_D8], r12d
0x140009a16  mov     [rsp+100h+var_E0], rax
0x140009a1b  call    WPP_SF_qSd
0x140009a20  test    r12b, r12b
0x140009a23  jnz     short loc_140009AA2
0x140009a25  mov     r8d, 1
0x140009a2b  mov     rdx, r13
0x140009a2e  mov     rcx, rsi
0x140009a31  call    VidPartitionTableLookupAndReference
0x140009a36  mov     rsi, rax
0x140009a39  test    rax, rax
0x140009a3c  jnz     short loc_140009A62
0x140009a3e  mov     r14d, 0C0370009h
0x140009a44  mov     r8d, 2A3h
0x140009a4a  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009a51  lea     rcx, aVidpartitioncr; "VidPartitionCreate"
0x140009a58  call    VidTraceErrorInternal0
0x140009a5d  jmp     loc_140009C48
0x140009a62  mov     rcx, cs:WPP_GLOBAL_Control
0x140009a69  cmp     rcx, r14
0x140009a6c  jz      short loc_140009A9A
0x140009a6e  mov     eax, [rcx+2Ch]
0x140009a71  test    al, 2
0x140009a73  jz      short loc_140009A9A
0x140009a75  cmp     byte ptr [rcx+29h], 4
0x140009a79  jb      short loc_140009A9A
0x140009a7b  mov     rax, [r15+8]
0x140009a7f  mov     edx, 0Eh
0x140009a84  mov     rcx, [rcx+18h]
0x140009a88  mov     r9, rdi
0x140009a8b  mov     [rsp+100h+var_D8], rsi
0x140009a90  mov     [rsp+100h+var_E0], rax
0x140009a95  call    WPP_SF_qSq
0x140009a9a  xor     r14d, r14d
0x140009a9d  jmp     loc_140009BDD
0x140009aa2  mov     bl, [rbp+4Fh+arg_20]
0x140009aa5  test    bl, bl
0x140009aa7  jnz     short loc_140009ABC
0x140009aa9  mov     rcx, r13; Buf2
0x140009aac  call    VidSidPartitionCheck
0x140009ab1  mov     r14d, eax
0x140009ab4  test    eax, eax
0x140009ab6  js      loc_140009C48
0x140009abc  mov     edx, 3210h
0x140009ac1  mov     ecx, 40h ; '@'
0x140009ac6  mov     r8d, 72446456h
0x140009acc  call    cs:__imp_ExAllocatePool2
0x140009ad3  nop     dword ptr [rax+rax+00h]
0x140009ad8  mov     rsi, rax
0x140009adb  test    rax, rax
0x140009ade  jnz     short loc_140009B04
0x140009ae0  mov     r14d, 0C000009Ah
0x140009ae6  mov     r8d, 2CAh
0x140009aec  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009af3  lea     rcx, aVidpartitioncr; "VidPartitionCreate"
0x140009afa  call    VidTraceErrorInternal0
0x140009aff  jmp     loc_140009C48
0x140009b04  mov     r8, r13
0x140009b07  mov     rdx, r15; SourceString
0x140009b0a  mov     rcx, rsi; DeferredContext
0x140009b0d  call    VidPartitionInitialize
0x140009b12  mov     r14d, eax
0x140009b15  test    eax, eax
0x140009b17  js      loc_140009C34
0x140009b1d  test    bl, bl
0x140009b1f  jz      short loc_140009B34
0x140009b21  mov     rcx, rsi
0x140009b24  call    VidExoPartitionInitialize
0x140009b29  mov     r14d, eax
0x140009b2c  test    eax, eax
0x140009b2e  js      loc_140009BEC
0x140009b34  mov     rcx, [rsp+100h+var_D0]
0x140009b39  mov     rdx, rsi
0x140009b3c  call    VidPartitionTableInsert
0x140009b41  mov     r14d, eax
0x140009b44  test    eax, eax
0x140009b46  js      loc_140009BEC
0x140009b4c  call    VidBamReferencePowerPolicy
0x140009b51  mov     ebx, 1
0x140009b56  lea     rcx, [rsi+2C0h]
0x140009b5d  mov     [rsi+328h], rbx
0x140009b64  mov     [rsi+330h], rbx
0x140009b6b  mov     [rsi+320h], rbx
0x140009b72  call    VidOpCtrlUnblock
0x140009b77  mov     rcx, rsi
0x140009b7a  call    VidReferencePartition
0x140009b7f  mov     rcx, cs:VidDeviceExtension
0x140009b86  add     rcx, 8
0x140009b8a  call    VidOpCtrlStart
0x140009b8f  mov     rax, [rsp+100h+var_D0]
0x140009b94  mov     rcx, [rax+168h]
0x140009b9b  lock add [rcx+8], rbx
0x140009ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ba7  lea     rax, WPP_GLOBAL_Control
0x140009bae  cmp     rcx, rax
0x140009bb1  jz      short loc_140009BDD
0x140009bb3  mov     eax, [rcx+2Ch]
0x140009bb6  test    al, 2
0x140009bb8  jz      short loc_140009BDD
0x140009bba  cmp     byte ptr [rcx+29h], 4
0x140009bbe  jb      short loc_140009BDD
0x140009bc0  mov     rax, [r15+8]
0x140009bc4  lea     edx, [rbx+0Eh]
0x140009bc7  mov     rcx, [rcx+18h]
0x140009bcb  mov     r9, rdi
0x140009bce  mov     [rsp+100h+var_D8], rsi
0x140009bd3  mov     [rsp+100h+var_E0], rax
0x140009bd8  call    WPP_SF_qSq
0x140009bdd  mov     rax, r12
0x140009be0  or      rax, rsi
0x140009be3  mov     [rdi+18h], rax
0x140009be7  jmp     loc_140009CF3
0x140009bec  lea     rbx, [rsi+0DA0h]
0x140009bf3  mov     rcx, rbx
0x140009bf6  call    VidThreadPoolDrain
0x140009bfb  mov     rcx, rbx
0x140009bfe  call    VidThreadPoolTeardown
0x140009c03  lea     rcx, [rsi+8]
0x140009c07  call    VidLockAcquireExclusive
0x140009c0c  lea     rbx, [rsi+0EA0h]
0x140009c13  mov     rcx, rbx
0x140009c16  call    VidLockAcquireExclusive
0x140009c1b  mov     rcx, rsi
0x140009c1e  call    VidPartitionUninitialize
0x140009c23  mov     rcx, rbx
0x140009c26  call    VidLockRelease
0x140009c2b  lea     rcx, [rsi+8]
0x140009c2f  call    VidLockRelease
0x140009c34  mov     edx, 72446456h; Tag
0x140009c39  mov     rcx, rsi; P
0x140009c3c  call    cs:__imp_ExFreePoolWithTag
0x140009c43  nop     dword ptr [rax+rax+00h]
0x140009c48  mov     eax, cs:dword_140064110
0x140009c4e  cmp     eax, 2
0x140009c51  jbe     loc_140009CF3
0x140009c57  mov     edx, 100h
0x140009c5c  lea     rcx, dword_140064110
0x140009c63  call    _tlgKeywordOn
0x140009c68  test    al, al
0x140009c6a  jz      loc_140009CF3
0x140009c70  lea     rdx, aVidpartitioncr; "VidPartitionCreate"
0x140009c77  lea     rcx, [rbp+4Fh+var_A0]
0x140009c7b  call    _tlgCreate1Sz_char
0x140009c80  lea     rdx, aOnecoreVmVidSy_40; "onecore\\vm\\vid\\sys\\driver\\vidcreat"...
0x140009c87  lea     rcx, [rbp+4Fh+var_90]
0x140009c8b  call    _tlgCreate1Sz_char
0x140009c90  lea     rax, [rbp+4Fh+var_C8]
0x140009c94  mov     [rbp+4Fh+var_C8], 33Fh
0x140009c9b  mov     [rbp+4Fh+var_80], rax
0x140009c9f  lea     rdx, word_14004632A
0x140009ca6  lea     rax, [rsp+100h+var_D0]
0x140009cab  mov     [rbp+4Fh+var_78], 4
0x140009cb3  mov     [rbp+4Fh+var_70], rax
0x140009cb7  lea     rcx, dword_140064110
0x140009cbe  lea     rax, [rbp+4Fh+var_C0]
0x140009cc2  mov     dword ptr [rsp+100h+var_D0], r14d
0x140009cc7  mov     [rsp+100h+var_D8], rax
0x140009ccc  xor     r9d, r9d
0x140009ccf  xor     r8d, r8d
0x140009cd2  mov     dword ptr [rsp+100h+var_E0], 7
0x140009cda  mov     [rbp+4Fh+var_68], 4
0x140009ce2  mov     [rbp+4Fh+var_60], r13
0x140009ce6  mov     [rbp+4Fh+var_58], 10h
0x140009cee  call    _tlgWriteTransfer_EtwWriteTransfer
0x140009cf3  mov     eax, r14d
0x140009cf6  mov     rcx, [rbp+4Fh+var_50]
0x140009cfa  xor     rcx, rsp; StackCookie
0x140009cfd  call    __security_check_cookie
0x140009d02  add     rsp, 0C8h
0x140009d09  pop     r15
0x140009d0b  pop     r14
0x140009d0d  pop     r13
0x140009d0f  pop     r12
0x140009d11  pop     rdi
0x140009d12  pop     rsi
0x140009d13  pop     rbx
0x140009d14  pop     rbp
0x140009d15  retn
```

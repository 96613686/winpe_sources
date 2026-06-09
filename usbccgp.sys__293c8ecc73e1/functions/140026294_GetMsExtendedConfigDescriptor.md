# GetMsExtendedConfigDescriptor

- ea: `0x140026294`
- end: `0x1400265c5`
- name: `GetMsExtendedConfigDescriptor`
- size: `817`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x14000a6cc`
- `0x14000ba3c`
- `0x14000f338`
- `0x140026294`
- `0x14002b99c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002656f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026593`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002656f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026593`
- `ntoskrnl!RtlCompareMemory` at `0x1400264cb`
- `ntoskrnl!RtlCompareMemory` at `0x1400264cb`
- `ntoskrnl!ExAllocatePool2` at `0x1400262d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400263f2`
- `ntoskrnl!ExAllocatePool2` at `0x1400262d1`
- `ntoskrnl!ExAllocatePool2` at `0x1400263f2`

## pseudocode

```c
__int64 __fastcall GetMsExtendedConfigDescriptor(_QWORD *a1)
{
  bool v1; // zf
  int v4; // edx
  unsigned int *Pool2; // rsi
  int MsOsFeatureDescriptor; // ebx
  void *v7; // rbp
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r9
  int v11; // edx
  int v12; // r9d
  unsigned int v13; // ebx
  int v14; // r9d
  unsigned int v15; // [rsp+80h] [rbp+8h] BYREF

  v1 = a1[141] == 0;
  v15 = 0;
  if ( !v1 )
    return 0;
  Pool2 = (unsigned int *)ExAllocatePool2(64, 16, 1130525525);
  if ( !Pool2 )
  {
    MsOsFeatureDescriptor = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_(a1[171], v4, 8, 20, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
    }
LABEL_36:
    a1[140] = 0;
    if ( MsOsFeatureDescriptor == -1073741637 )
      return 0;
    return (unsigned int)MsOsFeatureDescriptor;
  }
  v7 = 0;
  MsOsFeatureDescriptor = GetMsOsFeatureDescriptor((_DWORD)a1, 0, 0, 4, (__int64)Pool2, 16, (__int64)&v15);
  if ( MsOsFeatureDescriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_d(
        a1[171],
        v8,
        1,
        21,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        MsOsFeatureDescriptor);
    }
    goto LABEL_32;
  }
  if ( v15 != 16
    || *((_WORD *)Pool2 + 2) != 256
    || *((_WORD *)Pool2 + 3) != 4
    || (v9 = *((unsigned __int8 *)Pool2 + 8), !(_BYTE)v9)
    || (v10 = *Pool2, v8 = 24 * v9 + 16, v10 != v8) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 22;
      goto LABEL_30;
    }
LABEL_31:
    MsOsFeatureDescriptor = -1073741811;
    goto LABEL_32;
  }
  v7 = (void *)ExAllocatePool2(64, (unsigned int)v10, 1130525525);
  if ( !v7 )
  {
    MsOsFeatureDescriptor = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_32;
    v12 = 23;
    goto LABEL_17;
  }
  MsOsFeatureDescriptor = GetMsOsFeatureDescriptor((_DWORD)a1, 0, 0, 4, (__int64)v7, *Pool2, (__int64)&v15);
  if ( MsOsFeatureDescriptor >= 0 )
  {
    v13 = v15;
    if ( v15 == *Pool2 && RtlCompareMemory(Pool2, v7, 0x10u) == 16 )
    {
      MsOsFeatureDescriptor = USBD_ValidateExtendedConfigurationDescriptor(
                                v7,
                                v13,
                                a1[7],
                                *(unsigned __int16 *)(a1[7] + 2LL));
      if ( MsOsFeatureDescriptor >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v12 = 26;
LABEL_17:
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_(a1[171], v11, 8, v12, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      goto LABEL_32;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = 25;
LABEL_30:
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_(a1[171], v8, 8, v14, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 2;
    WPP_RECORDER_SF_D(
      a1[171],
      v8,
      8,
      24,
      (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
      MsOsFeatureDescriptor);
  }
LABEL_32:
  ExFreePoolWithTag(Pool2, 0x43627355u);
  if ( MsOsFeatureDescriptor < 0 )
  {
    if ( v7 )
      ExFreePoolWithTag(v7, 0x43627355u);
    goto LABEL_36;
  }
  a1[140] = v7;
  return (unsigned int)MsOsFeatureDescriptor;
}

```

## disassembly

```asm
0x140026294  mov     rax, rsp
0x140026297  push    rbx
0x140026298  push    rbp
0x140026299  push    rsi
0x14002629a  push    rdi
0x14002629b  push    r12
0x14002629d  push    r15
0x14002629f  sub     rsp, 48h
0x1400262a3  cmp     qword ptr [rcx+468h], 0
0x1400262ab  mov     rdi, rcx
0x1400262ae  mov     dword ptr [rax+8], 0
0x1400262b5  jz      short loc_1400262BE
0x1400262b7  xor     eax, eax
0x1400262b9  jmp     loc_1400265B7
0x1400262be  mov     r15d, 10h
0x1400262c4  mov     r8d, 43627355h
0x1400262ca  mov     edx, r15d
0x1400262cd  lea     ecx, [r15+30h]
0x1400262d1  call    cs:__imp_ExAllocatePool2
0x1400262d8  nop     dword ptr [rax+rax+00h]
0x1400262dd  mov     rsi, rax
0x1400262e0  test    rax, rax
0x1400262e3  jnz     short loc_140026325
0x1400262e5  mov     ebx, 0C000009Ah
0x1400262ea  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400262f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400262f8  jz      loc_14002659F
0x1400262fe  mov     rcx, [rdi+558h]
0x140026305  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14002630c  lea     r9d, [r15+4]
0x140026310  mov     [rsp+78h+var_58], rax
0x140026315  lea     r8d, [r15-8]
0x140026319  mov     dl, 2
0x14002631b  call    WPP_RECORDER_SF_
0x140026320  jmp     loc_14002659F
0x140026325  lea     rax, [rsp+78h+arg_0]
0x14002632d  xor     ebp, ebp
0x14002632f  mov     [rsp+78h+var_48], rax
0x140026334  xor     r8d, r8d
0x140026337  mov     [rsp+78h+var_50], r15d
0x14002633c  xor     edx, edx
0x14002633e  mov     rcx, rdi
0x140026341  mov     [rsp+78h+var_58], rsi
0x140026346  lea     r12d, [rbp+4]
0x14002634a  mov     r9d, r12d
0x14002634d  call    GetMsOsFeatureDescriptor
0x140026352  mov     ebx, eax
0x140026354  test    eax, eax
0x140026356  jns     short loc_140026398
0x140026358  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002635f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026366  jz      loc_140026563
0x14002636c  mov     rcx, [rdi+558h]
0x140026373  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14002637a  lea     r9d, [rbp+15h]
0x14002637e  mov     [rsp+78h+var_50], ebx
0x140026382  lea     r8d, [rbp+1]
0x140026386  mov     [rsp+78h+var_58], rax
0x14002638b  mov     dl, r12b
0x14002638e  call    WPP_RECORDER_SF_d
0x140026393  jmp     loc_140026563
0x140026398  cmp     [rsp+78h+arg_0], r15d
0x1400263a0  jnz     loc_140026528
0x1400263a6  mov     eax, 100h
0x1400263ab  cmp     [rsi+4], ax
0x1400263af  jnz     loc_140026528
0x1400263b5  cmp     [rsi+6], r12w
0x1400263ba  jnz     loc_140026528
0x1400263c0  movzx   eax, byte ptr [rsi+8]
0x1400263c4  test    al, al
0x1400263c6  jz      loc_140026528
0x1400263cc  mov     r9d, [rsi]
0x1400263cf  lea     rdx, [rax+rax*2]
0x1400263d3  lea     rdx, ds:10h[rdx*8]
0x1400263db  cmp     r9, rdx
0x1400263de  jnz     loc_140026528
0x1400263e4  mov     r8d, 43627355h
0x1400263ea  mov     edx, r9d
0x1400263ed  mov     ecx, 40h ; '@'
0x1400263f2  call    cs:__imp_ExAllocatePool2
0x1400263f9  nop     dword ptr [rax+rax+00h]
0x1400263fe  mov     rbp, rax
0x140026401  test    rax, rax
0x140026404  jnz     short loc_140026448
0x140026406  mov     ebx, 0C000009Ah
0x14002640b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026412  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026419  jz      loc_140026563
0x14002641f  lea     r9d, [rbp+17h]
0x140026423  mov     rcx, [rdi+558h]
0x14002642a  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140026431  mov     r8d, 8
0x140026437  mov     [rsp+78h+var_58], rax
0x14002643c  mov     dl, 2
0x14002643e  call    WPP_RECORDER_SF_
0x140026443  jmp     loc_140026563
0x140026448  lea     rax, [rsp+78h+arg_0]
0x140026450  mov     r9d, r12d
0x140026453  mov     [rsp+78h+var_48], rax
0x140026458  xor     r8d, r8d
0x14002645b  mov     eax, [rsi]
0x14002645d  xor     edx, edx
0x14002645f  mov     [rsp+78h+var_50], eax
0x140026463  mov     rcx, rdi
0x140026466  mov     [rsp+78h+var_58], rbp
0x14002646b  call    GetMsOsFeatureDescriptor
0x140026470  mov     ebx, eax
0x140026472  test    eax, eax
0x140026474  jns     short loc_1400264B7
0x140026476  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002647d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026484  jz      loc_140026563
0x14002648a  mov     rcx, [rdi+558h]
0x140026491  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140026498  mov     r9d, 18h
0x14002649e  mov     [rsp+78h+var_50], ebx
0x1400264a2  mov     dl, 2
0x1400264a4  mov     [rsp+78h+var_58], rax
0x1400264a9  lea     r8d, [r9-10h]
0x1400264ad  call    WPP_RECORDER_SF_D
0x1400264b2  jmp     loc_140026563
0x1400264b7  mov     ebx, [rsp+78h+arg_0]
0x1400264be  cmp     ebx, [rsi]
0x1400264c0  jnz     short loc_140026510
0x1400264c2  mov     r8, r15; Length
0x1400264c5  mov     rdx, rbp; Source2
0x1400264c8  mov     rcx, rsi; Source1
0x1400264cb  call    cs:__imp_RtlCompareMemory
0x1400264d2  nop     dword ptr [rax+rax+00h]
0x1400264d7  cmp     rax, r15
0x1400264da  jnz     short loc_140026510
0x1400264dc  mov     r8, [rdi+38h]
0x1400264e0  mov     edx, ebx
0x1400264e2  mov     rcx, rbp
0x1400264e5  movzx   r9d, word ptr [r8+2]
0x1400264ea  call    USBD_ValidateExtendedConfigurationDescriptor
0x1400264ef  mov     ebx, eax
0x1400264f1  test    eax, eax
0x1400264f3  jns     short loc_140026563
0x1400264f5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400264fc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026503  jz      short loc_140026563
0x140026505  mov     r9d, 1Ah
0x14002650b  jmp     loc_140026423
0x140026510  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026517  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002651e  jz      short loc_14002655E
0x140026520  mov     r9d, 19h
0x140026526  jmp     short loc_14002653E
0x140026528  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002652f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026536  jz      short loc_14002655E
0x140026538  mov     r9d, 16h
0x14002653e  mov     rcx, [rdi+558h]
0x140026545  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14002654c  mov     r8d, 8
0x140026552  mov     [rsp+78h+var_58], rax
0x140026557  mov     dl, 2
0x140026559  call    WPP_RECORDER_SF_
0x14002655e  mov     ebx, 0C000000Dh
0x140026563  mov     r15d, 43627355h
0x140026569  mov     rcx, rsi; P
0x14002656c  mov     edx, r15d; Tag
0x14002656f  call    cs:__imp_ExFreePoolWithTag
0x140026576  nop     dword ptr [rax+rax+00h]
0x14002657b  test    ebx, ebx
0x14002657d  js      short loc_140026588
0x14002657f  mov     [rdi+460h], rbp
0x140026586  jmp     short loc_1400265B5
0x140026588  test    rbp, rbp
0x14002658b  jz      short loc_14002659F
0x14002658d  mov     edx, r15d; Tag
0x140026590  mov     rcx, rbp; P
0x140026593  call    cs:__imp_ExFreePoolWithTag
0x14002659a  nop     dword ptr [rax+rax+00h]
0x14002659f  xor     eax, eax
0x1400265a1  mov     qword ptr [rdi+460h], 0
0x1400265ac  cmp     ebx, 0C00000BBh
0x1400265b2  cmovz   ebx, eax
0x1400265b5  mov     eax, ebx
0x1400265b7  add     rsp, 48h
0x1400265bb  pop     r15
0x1400265bd  pop     r12
0x1400265bf  pop     rdi
0x1400265c0  pop     rsi
0x1400265c1  pop     rbp
0x1400265c2  pop     rbx
0x1400265c3  retn
```

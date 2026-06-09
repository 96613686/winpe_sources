# GetMsOs20DescriptorSet

- ea: `0x1400265cc`
- end: `0x140026886`
- name: `GetMsOs20DescriptorSet`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140028f7c`

## callees

- `0x1400088b4`
- `0x14000a6cc`
- `0x14000ba3c`
- `0x140015100`
- `0x1400265cc`
- `0x14002b99c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026833`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026859`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026833`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026859`
- `ntoskrnl!ExAllocatePool2` at `0x1400265f6`
- `ntoskrnl!ExAllocatePool2` at `0x1400266f7`
- `ntoskrnl!ExAllocatePool2` at `0x1400265f6`
- `ntoskrnl!ExAllocatePool2` at `0x1400266f7`

## pseudocode

```c
__int64 __fastcall GetMsOs20DescriptorSet(__int64 a1)
{
  __int64 Pool2; // rax
  int v3; // edx
  _WORD *v4; // rdi
  int MsOsFeatureDescriptor; // ebx
  void *v6; // rbp
  int v7; // edx
  void *v8; // rax
  int v9; // edx
  int v10; // r9d
  int v12; // [rsp+88h] [rbp+10h] BYREF

  v12 = 0;
  Pool2 = ExAllocatePool2(64, 10, 1130525525);
  v4 = (_WORD *)Pool2;
  if ( !Pool2 )
  {
    MsOsFeatureDescriptor = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v3, 8, 27, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
    }
    goto LABEL_27;
  }
  *(_QWORD *)Pool2 = 0;
  *(_WORD *)(Pool2 + 8) = 0;
  v6 = 0;
  MsOsFeatureDescriptor = GetMsOsFeatureDescriptor(a1, 0, 0, 7, Pool2, 10, (__int64)&v12);
  if ( MsOsFeatureDescriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v7,
        1,
        28,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        MsOsFeatureDescriptor);
    }
    goto LABEL_23;
  }
  if ( v12 != 10 || *v4 != 10 || v4[1] )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 29;
      goto LABEL_21;
    }
LABEL_22:
    MsOsFeatureDescriptor = -1073741668;
    goto LABEL_23;
  }
  v8 = (void *)ExAllocatePool2(64, (unsigned __int16)v4[4], 1130525525);
  v6 = v8;
  if ( !v8 )
  {
    MsOsFeatureDescriptor = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v9, 8, 30, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
    }
    goto LABEL_23;
  }
  memset(v8, 0, (unsigned __int16)v4[4]);
  MsOsFeatureDescriptor = GetMsOsFeatureDescriptor(a1, 0, 0, 7, (__int64)v6, (unsigned __int16)v4[4], (__int64)&v12);
  if ( MsOsFeatureDescriptor < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_D(
        *(_QWORD *)(a1 + 1368),
        v7,
        8,
        31,
        (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids,
        MsOsFeatureDescriptor);
    }
    goto LABEL_23;
  }
  if ( v12 != (unsigned __int16)v4[4] )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = 32;
LABEL_21:
      LOBYTE(v7) = 4;
      WPP_RECORDER_SF_(*(_QWORD *)(a1 + 1368), v7, 1, v10, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids);
      goto LABEL_22;
    }
    goto LABEL_22;
  }
LABEL_23:
  ExFreePoolWithTag(v4, 0x43627355u);
  if ( MsOsFeatureDescriptor >= 0 )
  {
    *(_QWORD *)(a1 + 1128) = v6;
    return (unsigned int)MsOsFeatureDescriptor;
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0x43627355u);
LABEL_27:
  *(_QWORD *)(a1 + 1128) = 0;
  if ( MsOsFeatureDescriptor == -1073741637 )
    return 0;
  return (unsigned int)MsOsFeatureDescriptor;
}

```

## disassembly

```asm
0x1400265cc  mov     rax, rsp
0x1400265cf  push    rbx
0x1400265d0  push    rbp
0x1400265d1  push    rsi
0x1400265d2  push    rdi
0x1400265d3  push    r14
0x1400265d5  push    r15
0x1400265d7  sub     rsp, 48h
0x1400265db  xor     r14d, r14d
0x1400265de  mov     rsi, rcx
0x1400265e1  mov     r8d, 43627355h
0x1400265e7  mov     [rax+10h], r14d
0x1400265eb  lea     r15d, [r14+0Ah]
0x1400265ef  mov     edx, r15d
0x1400265f2  lea     ecx, [r14+40h]
0x1400265f6  call    cs:__imp_ExAllocatePool2
0x1400265fd  nop     dword ptr [rax+rax+00h]
0x140026602  mov     rdi, rax
0x140026605  test    rax, rax
0x140026608  jnz     short loc_14002664A
0x14002660a  mov     ebx, 0C000009Ah
0x14002660f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026616  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002661d  jz      loc_140026865
0x140026623  mov     rcx, [rsi+558h]
0x14002662a  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140026631  lea     r9d, [r14+1Bh]
0x140026635  mov     [rsp+78h+var_58], rax
0x14002663a  lea     r8d, [r14+8]
0x14002663e  mov     dl, 2
0x140026640  call    WPP_RECORDER_SF_
0x140026645  jmp     loc_140026865
0x14002664a  xor     eax, eax
0x14002664c  xor     r8d, r8d
0x14002664f  mov     [rdi], rax
0x140026652  xor     edx, edx
0x140026654  mov     [rdi+8], ax
0x140026658  mov     rcx, rsi
0x14002665b  mov     rbp, r14
0x14002665e  lea     r9d, [rax+7]
0x140026662  lea     rax, [rsp+78h+arg_8]
0x14002666a  mov     [rsp+78h+var_48], rax
0x14002666f  mov     [rsp+78h+var_50], r15d
0x140026674  mov     [rsp+78h+var_58], rdi
0x140026679  call    GetMsOsFeatureDescriptor
0x14002667e  mov     ebx, eax
0x140026680  test    eax, eax
0x140026682  jns     short loc_1400266C5
0x140026684  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002668b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140026692  jz      loc_14002682B
0x140026698  mov     rcx, [rsi+558h]
0x14002669f  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x1400266a6  mov     r9d, 1Ch
0x1400266ac  mov     [rsp+78h+var_50], ebx
0x1400266b0  mov     dl, 4
0x1400266b2  mov     [rsp+78h+var_58], rax
0x1400266b7  lea     r8d, [r9-1Bh]
0x1400266bb  call    WPP_RECORDER_SF_d
0x1400266c0  jmp     loc_14002682B
0x1400266c5  cmp     [rsp+78h+arg_8], r15d
0x1400266cd  jnz     loc_1400267F0
0x1400266d3  cmp     [rdi], r15w
0x1400266d7  jnz     loc_1400267F0
0x1400266dd  cmp     [rdi+2], r14w
0x1400266e2  jnz     loc_1400267F0
0x1400266e8  movzx   edx, word ptr [rdi+8]
0x1400266ec  mov     ecx, 40h ; '@'
0x1400266f1  mov     r8d, 43627355h
0x1400266f7  call    cs:__imp_ExAllocatePool2
0x1400266fe  nop     dword ptr [rax+rax+00h]
0x140026703  mov     rbp, rax
0x140026706  test    rax, rax
0x140026709  jnz     short loc_14002674B
0x14002670b  mov     ebx, 0C000009Ah
0x140026710  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026717  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002671e  jz      loc_14002682B
0x140026724  mov     rcx, [rsi+558h]
0x14002672b  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140026732  lea     r9d, [rbp+1Eh]
0x140026736  mov     [rsp+78h+var_58], rax
0x14002673b  lea     r8d, [rbp+8]
0x14002673f  mov     dl, 2
0x140026741  call    WPP_RECORDER_SF_
0x140026746  jmp     loc_14002682B
0x14002674b  movzx   r8d, word ptr [rdi+8]; Size
0x140026750  xor     edx, edx; Val
0x140026752  mov     rcx, rbp; void *
0x140026755  call    memset
0x14002675a  movzx   eax, word ptr [rdi+8]
0x14002675e  lea     rcx, [rsp+78h+arg_8]
0x140026766  mov     [rsp+78h+var_48], rcx
0x14002676b  mov     r9d, 7
0x140026771  mov     [rsp+78h+var_50], eax
0x140026775  mov     rcx, rsi
0x140026778  xor     r8d, r8d
0x14002677b  mov     [rsp+78h+var_58], rbp
0x140026780  xor     edx, edx
0x140026782  call    GetMsOsFeatureDescriptor
0x140026787  mov     ebx, eax
0x140026789  test    eax, eax
0x14002678b  jns     short loc_1400267CB
0x14002678d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026794  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002679b  jz      loc_14002682B
0x1400267a1  mov     rcx, [rsi+558h]
0x1400267a8  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x1400267af  mov     r9d, 1Fh
0x1400267b5  mov     [rsp+78h+var_50], ebx
0x1400267b9  mov     dl, 2
0x1400267bb  mov     [rsp+78h+var_58], rax
0x1400267c0  lea     r8d, [r9-17h]
0x1400267c4  call    WPP_RECORDER_SF_D
0x1400267c9  jmp     short loc_14002682B
0x1400267cb  movzx   eax, word ptr [rdi+8]
0x1400267cf  cmp     [rsp+78h+arg_8], eax
0x1400267d6  jz      short loc_14002682B
0x1400267d8  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400267df  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400267e6  jz      short loc_140026826
0x1400267e8  mov     r9d, 20h ; ' '
0x1400267ee  jmp     short loc_140026806
0x1400267f0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400267f7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400267fe  jz      short loc_140026826
0x140026800  mov     r9d, 1Dh
0x140026806  mov     rcx, [rsi+558h]
0x14002680d  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x140026814  mov     r8d, 1
0x14002681a  mov     [rsp+78h+var_58], rax
0x14002681f  mov     dl, 4
0x140026821  call    WPP_RECORDER_SF_
0x140026826  mov     ebx, 0C000009Ch
0x14002682b  mov     edx, 43627355h; Tag
0x140026830  mov     rcx, rdi; P
0x140026833  call    cs:__imp_ExFreePoolWithTag
0x14002683a  nop     dword ptr [rax+rax+00h]
0x14002683f  test    ebx, ebx
0x140026841  js      short loc_14002684C
0x140026843  mov     [rsi+468h], rbp
0x14002684a  jmp     short loc_140026876
0x14002684c  test    rbp, rbp
0x14002684f  jz      short loc_140026865
0x140026851  mov     edx, 43627355h; Tag
0x140026856  mov     rcx, rbp; P
0x140026859  call    cs:__imp_ExFreePoolWithTag
0x140026860  nop     dword ptr [rax+rax+00h]
0x140026865  cmp     ebx, 0C00000BBh
0x14002686b  mov     [rsi+468h], r14
0x140026872  cmovz   ebx, r14d
0x140026876  mov     eax, ebx
0x140026878  add     rsp, 48h
0x14002687c  pop     r15
0x14002687e  pop     r14
0x140026880  pop     rdi
0x140026881  pop     rsi
0x140026882  pop     rbp
0x140026883  pop     rbx
0x140026884  retn
```

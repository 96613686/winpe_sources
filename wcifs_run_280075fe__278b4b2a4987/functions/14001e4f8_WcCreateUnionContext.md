# WcCreateUnionContext

- ea: `0x14001e4f8`
- end: `0x14001e6ae`
- name: `WcCreateUnionContext`
- size: `438`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING SourceString@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000696c`
- `0x140020e60`

## callees

- `0x140004198`
- `0x14001e4f8`

## import_xrefs

- `ntoskrnl!RtlRandomEx` at `0x14001e609`
- `ntoskrnl!RtlRandomEx` at `0x14001e609`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14001e5bd`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x14001e5bd`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e645`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001e645`
- `ntoskrnl!KeInitializeEvent` at `0x14001e679`
- `ntoskrnl!KeInitializeEvent` at `0x14001e679`
- `ntoskrnl!ExAllocatePool2` at `0x14001e52f`
- `ntoskrnl!ExAllocatePool2` at `0x14001e52f`

## pseudocode

```c
__int64 __fastcall WcCreateUnionContext(PCUNICODE_STRING SourceString, int a2, int a3, int a4, __int64 *a5)
{
  __int64 Pool2; // rax
  int v10; // edx
  __int64 v11; // rbx
  unsigned int v12; // edi
  ULONG v13; // eax
  ULONG Seed; // [rsp+80h] [rbp+8h] BYREF

  Seed = 0;
  Pool2 = ExAllocatePool2(64, SourceString->Length + 256LL, 1668629335);
  v11 = Pool2;
  if ( Pool2 )
  {
    v12 = 0;
    RtlInitializeGenericTableAvl(
      (PRTL_AVL_TABLE)(Pool2 + 64),
      WcCompareLayerTableEntry,
      WcAllocateLayerTableEntry,
      WcFreeLayerTableEntry,
      0);
    *(_QWORD *)(v11 + 176) = v11 + 168;
    *(_QWORD *)(v11 + 168) = v11 + 168;
    Seed = MEMORY[0xFFFFF78000000320] ^ v11 ^ MEMORY[0xFFFFF78000000324] ^ (unsigned int)KeGetCurrentThread();
    v13 = RtlRandomEx(&Seed);
    *(_DWORD *)(v11 + 24) = a2;
    *(_DWORD *)(v11 + 56) = v13;
    *(_QWORD *)(v11 + 48) = 0;
    *(_WORD *)(v11 + 8) = 0;
    *(_WORD *)(v11 + 10) = SourceString->Length;
    *(_QWORD *)(v11 + 16) = v11 + 256;
    *(_DWORD *)(v11 + 36) = a3;
    *(_DWORD *)(v11 + 40) = a4;
    RtlCopyUnicodeString((PUNICODE_STRING)(v11 + 8), SourceString);
    *(_DWORD *)(v11 + 32) = 0;
    *(_DWORD *)v11 = 0;
    _InterlockedAdd((volatile signed __int32 *)v11, 1u);
    *(_DWORD *)(v11 + 200) = 1;
    *(_QWORD *)(v11 + 208) = 0;
    *(_DWORD *)(v11 + 216) = 0;
    KeInitializeEvent((PRKEVENT)(v11 + 224), SynchronizationEvent, 0);
    *(_QWORD *)(v11 + 192) = v11 + 184;
    *(_QWORD *)(v11 + 184) = v11 + 184;
    *a5 = v11;
  }
  else
  {
    v12 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v10,
        9,
        176,
        (__int64)WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\wcifs\\utils.c",
        9);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x14001e4f8  mov     rax, rsp
0x14001e4fb  push    rbx
0x14001e4fc  push    rbp
0x14001e4fd  push    rsi
0x14001e4fe  push    rdi
0x14001e4ff  push    r14
0x14001e501  push    r15
0x14001e503  sub     rsp, 48h
0x14001e507  mov     r15d, edx
0x14001e50a  mov     dword ptr [rax+8], 0
0x14001e511  movzx   edx, word ptr [rcx]
0x14001e514  mov     r14d, r8d
0x14001e517  mov     rsi, rcx
0x14001e51a  add     rdx, 100h
0x14001e521  mov     ecx, 40h ; '@'
0x14001e526  mov     r8d, 63754357h
0x14001e52c  mov     ebp, r9d
0x14001e52f  call    cs:__imp_ExAllocatePool2
0x14001e536  nop     dword ptr [rax+rax+00h]
0x14001e53b  mov     rbx, rax
0x14001e53e  test    rax, rax
0x14001e541  jnz     short loc_14001E59D
0x14001e543  mov     edi, 0C000009Ah
0x14001e548  lea     rax, WPP_RECORDER_INITIALIZED
0x14001e54f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001e556  jz      loc_14001E69E
0x14001e55c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e563  lea     rax, aOnecoreBaseFsW_1; "onecore\\base\\fs\\wci\\wcifs\\utils.c"
0x14001e56a  mov     [rsp+78h+var_48], 1E09h
0x14001e572  lea     r8d, [rbx+9]
0x14001e576  mov     [rsp+78h+var_50], rax
0x14001e57b  mov     r9d, 0B0h
0x14001e581  lea     rax, WPP_7fe91d13bb4232a4ef347966c958c4d1_Traceguids
0x14001e588  mov     dl, 2
0x14001e58a  mov     rcx, [rcx+40h]
0x14001e58e  mov     [rsp+78h+TableContext], rax
0x14001e593  call    WPP_RECORDER_SF_sD
0x14001e598  jmp     loc_14001E69E
0x14001e59d  xor     edi, edi
0x14001e59f  lea     rcx, [rax+40h]; Table
0x14001e5a3  lea     r9, WcFreeLayerTableEntry; FreeRoutine
0x14001e5aa  mov     [rsp+78h+TableContext], rdi; TableContext
0x14001e5af  lea     r8, WcAllocateLayerTableEntry; AllocateRoutine
0x14001e5b6  lea     rdx, WcCompareLayerTableEntry; CompareRoutine
0x14001e5bd  call    cs:__imp_RtlInitializeGenericTableAvl
0x14001e5c4  nop     dword ptr [rax+rax+00h]
0x14001e5c9  lea     rax, [rbx+0A8h]
0x14001e5d0  mov     [rax+8], rax
0x14001e5d4  mov     [rax], rax
0x14001e5d7  mov     rax, 0FFFFF78000000320h
0x14001e5e1  mov     rax, [rax]
0x14001e5e4  mov     rdx, gs:188h
0x14001e5ed  mov     rcx, rax
0x14001e5f0  shr     rcx, 20h
0x14001e5f4  xor     edx, ecx
0x14001e5f6  lea     rcx, [rsp+78h+Seed]; Seed
0x14001e5fe  xor     edx, ebx
0x14001e600  xor     edx, eax
0x14001e602  mov     [rsp+78h+Seed], edx
0x14001e609  call    cs:__imp_RtlRandomEx
0x14001e610  nop     dword ptr [rax+rax+00h]
0x14001e615  lea     rcx, [rbx+8]; DestinationString
0x14001e619  mov     [rbx+18h], r15d
0x14001e61d  mov     [rbx+38h], eax
0x14001e620  mov     rdx, rsi; SourceString
0x14001e623  xor     eax, eax
0x14001e625  mov     [rbx+30h], rdi
0x14001e629  mov     [rcx], ax
0x14001e62c  movzx   eax, word ptr [rsi]
0x14001e62f  mov     [rbx+0Ah], ax
0x14001e633  lea     rax, [rbx+100h]
0x14001e63a  mov     [rbx+10h], rax
0x14001e63e  mov     [rbx+24h], r14d
0x14001e642  mov     [rbx+28h], ebp
0x14001e645  call    cs:__imp_RtlCopyUnicodeString
0x14001e64c  nop     dword ptr [rax+rax+00h]
0x14001e651  mov     [rbx+20h], edi
0x14001e654  lea     edx, [rdi+1]; Type
0x14001e657  mov     [rbx], edi
0x14001e659  lock add [rbx], edx
0x14001e65c  lea     rcx, [rbx+0E0h]; Event
0x14001e663  mov     [rbx+0C8h], edx
0x14001e669  xor     r8d, r8d; State
0x14001e66c  mov     [rbx+0D0h], rdi
0x14001e673  mov     [rbx+0D8h], edi
0x14001e679  call    cs:__imp_KeInitializeEvent
0x14001e680  nop     dword ptr [rax+rax+00h]
0x14001e685  lea     rcx, [rbx+0B8h]
0x14001e68c  mov     [rcx+8], rcx
0x14001e690  mov     [rcx], rcx
0x14001e693  mov     rcx, [rsp+78h+arg_20]
0x14001e69b  mov     [rcx], rbx
0x14001e69e  mov     eax, edi
0x14001e6a0  add     rsp, 48h
0x14001e6a4  pop     r15
0x14001e6a6  pop     r14
0x14001e6a8  pop     rdi
0x14001e6a9  pop     rsi
0x14001e6aa  pop     rbp
0x14001e6ab  pop     rbx
0x14001e6ac  retn
```

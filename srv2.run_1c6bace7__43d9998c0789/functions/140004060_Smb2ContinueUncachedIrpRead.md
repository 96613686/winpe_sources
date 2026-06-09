# Smb2ContinueUncachedIrpRead

- ea: `0x140004060`
- end: `0x140004192`
- name: `Smb2ContinueUncachedIrpRead`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140004060`
- `0x1400041a0`
- `0x1400051dc`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14003a404`
- `ntoskrnl!IoFreeMdl` at `0x14003a404`
- `ntoskrnl!RtlInitAnsiString` at `0x140004120`
- `ntoskrnl!RtlInitAnsiString` at `0x140004120`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004167`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004167`
- `ntoskrnl!MmUnlockPages` at `0x14003a3f5`
- `ntoskrnl!MmUnlockPages` at `0x14003a3f5`
- `HAL!KeQueryPerformanceCounter` at `0x1400040c9`
- `HAL!KeQueryPerformanceCounter` at `0x1400040c9`

## string_xrefs

- `0x140004106`: `Smb2ContinueUncachedIrpRead`

## pseudocode

```c
PSLIST_ENTRY __fastcall Smb2ContinueUncachedIrpRead(__int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // rdi
  bool v3; // zf
  __int64 v5; // rdi
  __int64 *v6; // rbp
  void *v7; // rcx
  struct _MDL *v8; // rsi
  LARGE_INTEGER PerformanceCounter; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // edx
  int v14; // ecx
  struct _MDL *v15; // rbp
  CSHORT MdlFlags; // ax
  struct _STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF

  v1 = *(_QWORD *)(a1 + 560);
  v2 = a1 + 584;
  v3 = *(_BYTE *)(a1 + 600) == 0;
  DestinationString = 0;
  if ( !v3 )
  {
    PerformanceCounter = KeQueryPerformanceCounter(0);
    v11 = *(unsigned __int8 *)(v2 + 128);
    if ( (unsigned __int8)(v11 - 1) <= 0xFDu )
    {
      v12 = *(_QWORD *)(v2 + 136);
      if ( PerformanceCounter.QuadPart > v12 )
        *(_QWORD *)(v2 + 8 * v11 + 40) += PerformanceCounter.QuadPart - v12;
      ++*(_WORD *)(v2 + 2 * v11 + 18);
    }
    *(_BYTE *)(v2 + 128) = 0;
    *(LARGE_INTEGER *)(v2 + 136) = PerformanceCounter;
    RtlInitAnsiString(&DestinationString, "Smb2ContinueUncachedIrpRead");
    if ( (Microsoft_Windows_SMBServerEnableBits & 4) != 0 )
      McTemplateK0qqhsr2_EtwWriteTransfer(
        v14,
        v13,
        v2,
        0,
        61,
        DestinationString.Length,
        (__int64)DestinationString.Buffer);
  }
  v5 = *(_QWORD *)(a1 + 120);
  v6 = *(__int64 **)(v1 + 200);
  v7 = *(void **)(v5 + 160);
  if ( v7 )
  {
    ExFreePoolWithTag(v7, 0);
    *(_QWORD *)(v5 + 160) = 0;
  }
  v8 = *(struct _MDL **)(v5 + 8);
  if ( v8 && v8 != (struct _MDL *)v6 && (v8->MdlFlags & 4) == 0 )
  {
    do
    {
      v15 = v8;
      v8 = v8->Next;
      MdlFlags = v15->MdlFlags;
      if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
        MmUnlockPages(v15);
      IoFreeMdl(v15);
    }
    while ( v8 );
    *(_QWORD *)(v5 + 8) = 0;
  }
  return Smb2ContinueUncachedRead(a1);
}

```

## disassembly

```asm
0x140004060  push    rbx
0x140004062  push    rbp
0x140004063  push    rsi
0x140004064  push    rdi
0x140004065  sub     rsp, 58h
0x140004069  mov     rsi, [rcx+230h]
0x140004070  lea     rdi, [rcx+248h]
0x140004077  cmp     byte ptr [rdi+10h], 0
0x14000407b  xorps   xmm0, xmm0
0x14000407e  mov     rbx, rcx
0x140004081  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x140004086  jnz     short loc_1400040C7
0x140004088  mov     rdi, [rbx+78h]
0x14000408c  mov     rbp, [rsi+0C8h]
0x140004093  mov     rcx, [rdi+0A0h]; P
0x14000409a  test    rcx, rcx
0x14000409d  jnz     loc_140004165
0x1400040a3  mov     rsi, [rdi+8]
0x1400040a7  test    rsi, rsi
0x1400040aa  jz      short loc_1400040B5
0x1400040ac  cmp     rsi, rbp
0x1400040af  jnz     loc_140004183
0x1400040b5  mov     rcx, rbx
0x1400040b8  call    Smb2ContinueUncachedRead
0x1400040bd  add     rsp, 58h
0x1400040c1  pop     rdi
0x1400040c2  pop     rsi
0x1400040c3  pop     rbp
0x1400040c4  pop     rbx
0x1400040c5  retn
0x1400040c7  xor     ecx, ecx; PerformanceFrequency
0x1400040c9  call    cs:__imp_KeQueryPerformanceCounter
0x1400040d0  nop     dword ptr [rax+rax+00h]
0x1400040d5  movzx   r8d, byte ptr [rdi+80h]
0x1400040dd  lea     ecx, [r8-1]
0x1400040e1  cmp     cl, 0FDh
0x1400040e4  ja      short loc_140004106
0x1400040e6  mov     r9, [rdi+88h]
0x1400040ed  cmp     rax, r9
0x1400040f0  jle     short loc_140004100
0x1400040f2  mov     rcx, rax
0x1400040f5  lea     rdx, [rdi+r8*8]
0x1400040f9  sub     rcx, r9
0x1400040fc  add     [rdx+28h], rcx
0x140004100  inc     word ptr [rdi+r8*2+12h]
0x140004106  lea     rdx, aSmb2continueun; "Smb2ContinueUncachedIrpRead"
0x14000410d  mov     byte ptr [rdi+80h], 0
0x140004114  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x140004119  mov     [rdi+88h], rax
0x140004120  call    cs:__imp_RtlInitAnsiString
0x140004127  nop     dword ptr [rax+rax+00h]
0x14000412c  test    cs:Microsoft_Windows_SMBServerEnableBits, 4
0x140004133  jz      loc_140004088
0x140004139  mov     rax, [rsp+78h+DestinationString.Buffer]
0x14000413e  xor     r9d, r9d
0x140004141  mov     [rsp+78h+var_48], rax
0x140004146  mov     r8, rdi
0x140004149  movzx   eax, [rsp+78h+DestinationString.Length]
0x14000414e  mov     [rsp+78h+var_50], ax
0x140004153  mov     [rsp+78h+var_58], 63Dh
0x14000415b  call    McTemplateK0qqhsr2_EtwWriteTransfer
0x140004160  jmp     loc_140004088
0x140004165  xor     edx, edx; Tag
0x140004167  call    cs:__imp_ExFreePoolWithTag
0x14000416e  nop     dword ptr [rax+rax+00h]
0x140004173  mov     qword ptr [rdi+0A0h], 0
0x14000417e  jmp     loc_1400040A3
0x140004183  test    byte ptr [rsi+0Ah], 4
0x140004187  jnz     loc_1400040B5
0x14000418d  jmp     loc_14003A3E0
0x14003a3e0  mov     rbp, rsi
0x14003a3e3  mov     rsi, [rsi]
0x14003a3e6  movzx   eax, word ptr [rbp+0Ah]
0x14003a3ea  test    al, 2
0x14003a3ec  jnz     short loc_14003A3F2
0x14003a3ee  test    al, 20h
0x14003a3f0  jz      short loc_14003A401
0x14003a3f2  mov     rcx, rbp; MemoryDescriptorList
0x14003a3f5  call    cs:__imp_MmUnlockPages
0x14003a3fc  nop     dword ptr [rax+rax+00h]
0x14003a401  mov     rcx, rbp; Mdl
0x14003a404  call    cs:__imp_IoFreeMdl
0x14003a40b  nop     dword ptr [rax+rax+00h]
0x14003a410  test    rsi, rsi
0x14003a413  jnz     short loc_14003A3E0
0x14003a415  mov     [rdi+8], rsi
0x14003a419  jmp     loc_1400040B5
```

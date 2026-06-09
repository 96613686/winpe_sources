# SafeAllocaInitialize

- ea: `0x180047a5c`
- end: `0x180047b18`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180025c38`

## callees

- `0x180047a5c`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x180047a6d`
- `ntdll!RtlImageNtHeader` at `0x180047a6d`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())(_QWORD)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(_QWORD); // rax
  __int64 SizeOfStackCommit; // rax

  v0 = RtlImageNtHeader(NtCurrentPeb()->ImageBaseAddress);
  v1 = v0;
  if ( NtCurrentPeb()->BeingDebugged || !v0 )
  {
    SizeOfStackCommit = 0;
  }
  else
  {
    if ( v0->OptionalHeader.SizeOfStackReserve - v0->OptionalHeader.SizeOfStackCommit < 0x3000 )
    {
      g_ulMaxStackAllocSize = 0;
      goto LABEL_5;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_5:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_8;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_8;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_8:
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  result = SchannelFree;
  g_pfnFree = (__int64)SchannelFree;
  return result;
}

```

## disassembly

```asm
0x180047a5c  sub     rsp, 28h
0x180047a60  mov     rcx, gs:60h
0x180047a69  mov     rcx, [rcx+10h]; BaseAddress
0x180047a6d  call    cs:__imp_RtlImageNtHeader
0x180047a73  mov     rcx, gs:60h
0x180047a7c  mov     r8d, 3000h
0x180047a82  mov     rdx, rax
0x180047a85  cmp     byte ptr [rcx+2], 0
0x180047a89  jnz     short loc_180047AF7
0x180047a8b  test    rax, rax
0x180047a8e  jz      short loc_180047AF7
0x180047a90  mov     rax, [rax+60h]
0x180047a94  sub     rax, [rdx+68h]
0x180047a98  cmp     rax, r8
0x180047a9b  jnb     short loc_180047B12
0x180047a9d  mov     cs:g_ulMaxStackAllocSize, 0
0x180047aa8  mov     rax, gs:30h
0x180047ab1  mov     eax, [rax+1748h]
0x180047ab7  mov     cs:g_ulAdditionalProbeSize, rax
0x180047abe  test    rax, rax
0x180047ac1  jnz     short loc_180047ACC
0x180047ac3  mov     cs:g_ulAdditionalProbeSize, r8
0x180047aca  jmp     short loc_180047AD6
0x180047acc  add     rax, 8
0x180047ad0  cmp     rax, 8
0x180047ad4  jb      short loc_180047B05
0x180047ad6  lea     rax, SafeAllocaAllocateFromHeap
0x180047add  mov     cs:g_pfnAllocate, rax
0x180047ae4  lea     rax, SchannelFree
0x180047aeb  mov     cs:g_pfnFree, rax
0x180047af2  add     rsp, 28h
0x180047af6  retn
0x180047af7  xor     eax, eax
0x180047af9  mov     cs:g_ulMaxStackAllocSize, rax
0x180047b00  test    rdx, rdx
0x180047b03  jnz     short loc_180047AA8
0x180047b05  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x180047b10  jmp     short loc_180047AD6
0x180047b12  mov     rax, [rdx+68h]
0x180047b16  jmp     short loc_180047AF9
```

# SafeAllocaInitialize

- ea: `0x180042790`
- end: `0x18004283e`
- name: `SafeAllocaInitialize`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800014d0`

## callees

- `0x180042790`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x1800427a1`
- `ntdll!RtlImageNtHeader` at `0x1800427a1`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax

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
      goto LABEL_8;
    }
    SizeOfStackCommit = v0->OptionalHeader.SizeOfStackCommit;
  }
  g_ulMaxStackAllocSize = SizeOfStackCommit;
  if ( !v1 )
    goto LABEL_11;
LABEL_8:
  GuaranteedStackBytes = NtCurrentTeb()->GuaranteedStackBytes;
  g_ulAdditionalProbeSize = GuaranteedStackBytes;
  if ( GuaranteedStackBytes )
  {
    if ( (unsigned __int64)(GuaranteedStackBytes + 8) >= 8 )
      goto LABEL_12;
LABEL_11:
    g_ulAdditionalProbeSize = -9;
    goto LABEL_12;
  }
  g_ulAdditionalProbeSize = 12288;
LABEL_12:
  result = SafeAllocaAllocateFromHeap;
  g_pfnAllocate = (__int64)SafeAllocaAllocateFromHeap;
  return result;
}

```

## disassembly

```asm
0x180042790  sub     rsp, 28h
0x180042794  mov     rcx, gs:60h
0x18004279d  mov     rcx, [rcx+10h]; BaseAddress
0x1800427a1  call    cs:__imp_RtlImageNtHeader
0x1800427a7  mov     rcx, gs:60h
0x1800427b0  mov     r8d, 3000h
0x1800427b6  mov     rdx, rax
0x1800427b9  cmp     byte ptr [rcx+2], 0
0x1800427bd  jnz     short loc_1800427E4
0x1800427bf  test    rax, rax
0x1800427c2  jz      short loc_1800427E4
0x1800427c4  mov     rax, [rax+60h]
0x1800427c8  sub     rax, [rdx+68h]
0x1800427cc  cmp     rax, r8
0x1800427cf  jnb     short loc_1800427DE
0x1800427d1  mov     cs:g_ulMaxStackAllocSize, 0
0x1800427dc  jmp     short loc_1800427F2
0x1800427de  mov     rax, [rdx+68h]
0x1800427e2  jmp     short loc_1800427E6
0x1800427e4  xor     eax, eax
0x1800427e6  mov     cs:g_ulMaxStackAllocSize, rax
0x1800427ed  test    rdx, rdx
0x1800427f0  jz      short loc_180042820
0x1800427f2  mov     rax, gs:30h
0x1800427fb  mov     eax, [rax+1748h]
0x180042801  mov     cs:g_ulAdditionalProbeSize, rax
0x180042808  test    rax, rax
0x18004280b  jnz     short loc_180042816
0x18004280d  mov     cs:g_ulAdditionalProbeSize, r8
0x180042814  jmp     short loc_18004282B
0x180042816  add     rax, 8
0x18004281a  cmp     rax, 8
0x18004281e  jnb     short loc_18004282B
0x180042820  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18004282b  lea     rax, SafeAllocaAllocateFromHeap
0x180042832  mov     cs:g_pfnAllocate, rax
0x180042839  add     rsp, 28h
0x18004283d  retn
```

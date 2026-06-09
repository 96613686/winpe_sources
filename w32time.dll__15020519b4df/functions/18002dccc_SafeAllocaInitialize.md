# SafeAllocaInitialize

- ea: `0x18002dccc`
- end: `0x18002dd8f`
- name: `SafeAllocaInitialize`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180039100`

## callees

- `0x18002dccc`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18002dcdd`
- `ntdll!RtlImageNtHeader` at `0x18002dcdd`

## pseudocode

```c
__int64 (__fastcall *SafeAllocaInitialize())()
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 GuaranteedStackBytes; // rax
  __int64 (__fastcall *result)(); // rax
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
  result = SafeAllocaFreeToHeap;
  g_pfnFree = (__int64)SafeAllocaFreeToHeap;
  return result;
}

```

## disassembly

```asm
0x18002dccc  sub     rsp, 28h
0x18002dcd0  mov     rcx, gs:60h
0x18002dcd9  mov     rcx, [rcx+10h]; BaseAddress
0x18002dcdd  call    cs:__imp_RtlImageNtHeader
0x18002dce4  nop     dword ptr [rax+rax+00h]
0x18002dce9  mov     rcx, gs:60h
0x18002dcf2  mov     r8d, 3000h
0x18002dcf8  mov     rdx, rax
0x18002dcfb  cmp     byte ptr [rcx+2], 0
0x18002dcff  jnz     short loc_18002DD6E
0x18002dd01  test    rax, rax
0x18002dd04  jz      short loc_18002DD6E
0x18002dd06  mov     rax, [rax+60h]
0x18002dd0a  sub     rax, [rdx+68h]
0x18002dd0e  cmp     rax, r8
0x18002dd11  jnb     short loc_18002DD89
0x18002dd13  mov     cs:g_ulMaxStackAllocSize, 0
0x18002dd1e  mov     rax, gs:30h
0x18002dd27  mov     eax, [rax+1748h]
0x18002dd2d  mov     cs:g_ulAdditionalProbeSize, rax
0x18002dd34  test    rax, rax
0x18002dd37  jnz     short loc_18002DD42
0x18002dd39  mov     cs:g_ulAdditionalProbeSize, r8
0x18002dd40  jmp     short loc_18002DD4C
0x18002dd42  add     rax, 8
0x18002dd46  cmp     rax, 8
0x18002dd4a  jb      short loc_18002DD7C
0x18002dd4c  lea     rax, SafeAllocaAllocateFromHeap
0x18002dd53  mov     cs:g_pfnAllocate, rax
0x18002dd5a  lea     rax, SafeAllocaFreeToHeap
0x18002dd61  mov     cs:g_pfnFree, rax
0x18002dd68  add     rsp, 28h
0x18002dd6c  retn
0x18002dd6e  xor     eax, eax
0x18002dd70  mov     cs:g_ulMaxStackAllocSize, rax
0x18002dd77  test    rdx, rdx
0x18002dd7a  jnz     short loc_18002DD1E
0x18002dd7c  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18002dd87  jmp     short loc_18002DD4C
0x18002dd89  mov     rax, [rdx+68h]
0x18002dd8d  jmp     short loc_18002DD70
```

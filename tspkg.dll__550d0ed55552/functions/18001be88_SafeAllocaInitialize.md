# SafeAllocaInitialize

- ea: `0x18001be88`
- end: `0x18001bf44`
- name: `SafeAllocaInitialize`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180017a40`

## callees

- `0x18001be88`

## import_xrefs

- `ntdll!RtlImageNtHeader` at `0x18001be99`
- `ntdll!RtlImageNtHeader` at `0x18001be99`

## pseudocode

```c
void (__fastcall *SafeAllocaInitialize())(void *)
{
  PIMAGE_NT_HEADERS v0; // rax
  PIMAGE_NT_HEADERS v1; // rdx
  __int64 SizeOfStackCommit; // rax
  __int64 GuaranteedStackBytes; // rax
  void (__fastcall *result)(void *); // rax

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
  g_pfnAllocate = (__int64)TSAllocate;
  result = TSFree;
  g_pfnFree = (__int64)TSFree;
  return result;
}

```

## disassembly

```asm
0x18001be88  sub     rsp, 28h
0x18001be8c  mov     rcx, gs:60h
0x18001be95  mov     rcx, [rcx+10h]; BaseAddress
0x18001be99  call    cs:__imp_RtlImageNtHeader
0x18001be9f  mov     rcx, gs:60h
0x18001bea8  mov     r8d, 3000h
0x18001beae  mov     rdx, rax
0x18001beb1  cmp     byte ptr [rcx+2], 0
0x18001beb5  jnz     short loc_18001BEDC
0x18001beb7  test    rax, rax
0x18001beba  jz      short loc_18001BEDC
0x18001bebc  mov     rax, [rax+60h]
0x18001bec0  sub     rax, [rdx+68h]
0x18001bec4  cmp     rax, r8
0x18001bec7  jnb     short loc_18001BED6
0x18001bec9  mov     cs:g_ulMaxStackAllocSize, 0
0x18001bed4  jmp     short loc_18001BEEA
0x18001bed6  mov     rax, [rdx+68h]
0x18001beda  jmp     short loc_18001BEDE
0x18001bedc  xor     eax, eax
0x18001bede  mov     cs:g_ulMaxStackAllocSize, rax
0x18001bee5  test    rdx, rdx
0x18001bee8  jz      short loc_18001BF18
0x18001beea  mov     rax, gs:30h
0x18001bef3  mov     eax, [rax+1748h]
0x18001bef9  mov     cs:g_ulAdditionalProbeSize, rax
0x18001bf00  test    rax, rax
0x18001bf03  jnz     short loc_18001BF0E
0x18001bf05  mov     cs:g_ulAdditionalProbeSize, r8
0x18001bf0c  jmp     short loc_18001BF23
0x18001bf0e  add     rax, 8
0x18001bf12  cmp     rax, 8
0x18001bf16  jnb     short loc_18001BF23
0x18001bf18  mov     cs:g_ulAdditionalProbeSize, 0FFFFFFFFFFFFFFF7h
0x18001bf23  lea     rax, ?TSAllocate@@YAPEAX_K@Z; TSAllocate(unsigned __int64)
0x18001bf2a  mov     cs:g_pfnAllocate, rax
0x18001bf31  lea     rax, ?TSFree@@YAXPEAX@Z; TSFree(void *)
0x18001bf38  mov     cs:g_pfnFree, rax
0x18001bf3f  add     rsp, 28h
0x18001bf43  retn
```

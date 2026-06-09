# SmpCheckMemoryCoolingCompatibility

- ea: `0x14000d6f8`
- end: `0x14000d7e3`
- name: `SmpCheckMemoryCoolingCompatibility`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f120`

## callees

- `0x14000d6f8`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x14000d750`
- `ntdll!NtQuerySystemInformation` at `0x14000d750`
- `ntdll!RtlAllocateHeap` at `0x14000d72e`
- `ntdll!RtlAllocateHeap` at `0x14000d72e`
- `ntdll!RtlFreeHeap` at `0x14000d775`
- `ntdll!RtlFreeHeap` at `0x14000d7d4`
- `ntdll!RtlFreeHeap` at `0x14000d775`
- `ntdll!RtlFreeHeap` at `0x14000d7d4`
- `ntdll!NtUpdateWnfStateData` at `0x14000d7b7`
- `ntdll!NtUpdateWnfStateData` at `0x14000d7b7`

## pseudocode

```c
void SmpCheckMemoryCoolingCompatibility()
{
  _DWORD *v0; // rbx
  int v1; // esi
  unsigned int v2; // edi
  unsigned int i; // ebp
  _DWORD *Heap; // rax
  NTSTATUS v5; // eax
  ULONG ReturnLength; // [rsp+70h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  v2 = (SmpMaximumNodeCount << 13) + 48;
  ReturnLength = 0;
  for ( i = 0; i < 2; ++i )
  {
    Heap = RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v2);
    v0 = Heap;
    if ( !Heap )
      return;
    v5 = NtQuerySystemInformation(SystemCallTimeInformation|0x80, Heap, v2, &ReturnLength);
    v1 = v5;
    if ( v5 < 0 )
    {
      if ( v5 != -1073741789 )
        goto LABEL_12;
      RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v0);
      v2 = ReturnLength;
      v0 = 0;
    }
  }
  if ( v1 >= 0 && v0[3] > 1u )
    NtUpdateWnfStateData(&WNF_SMSS_MEMORY_COOLING_COMPATIBLE, 0, 0, 0, 0, 0, 0);
  if ( v0 )
LABEL_12:
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v0);
}

```

## disassembly

```asm
0x14000d6f8  push    rbx
0x14000d6fa  push    rbp
0x14000d6fb  push    rsi
0x14000d6fc  push    rdi
0x14000d6fd  sub     rsp, 48h
0x14000d701  mov     edi, cs:SmpMaximumNodeCount
0x14000d707  xor     ebx, ebx
0x14000d709  shl     edi, 0Dh
0x14000d70c  xor     esi, esi
0x14000d70e  add     edi, 30h ; '0'
0x14000d711  mov     [rsp+68h+ReturnLength], ebx
0x14000d715  xor     ebp, ebp
0x14000d717  cmp     ebp, 2
0x14000d71a  jnb     short loc_14000D785
0x14000d71c  mov     rcx, gs:60h
0x14000d725  xor     edx, edx; Flags
0x14000d727  mov     r8d, edi; Size
0x14000d72a  mov     rcx, [rcx+30h]; HeapHandle
0x14000d72e  call    cs:__imp_RtlAllocateHeap
0x14000d734  mov     rbx, rax
0x14000d737  test    rax, rax
0x14000d73a  jz      loc_14000D7DA
0x14000d740  lea     r9, [rsp+68h+ReturnLength]; ReturnLength
0x14000d745  mov     r8d, edi; SystemInformationLength
0x14000d748  mov     rdx, rax; SystemInformation
0x14000d74b  mov     ecx, 8Ah; SystemInformationClass
0x14000d750  call    cs:__imp_NtQuerySystemInformation
0x14000d756  mov     esi, eax
0x14000d758  test    eax, eax
0x14000d75a  jns     short loc_14000D781
0x14000d75c  cmp     eax, 0C0000023h
0x14000d761  jnz     short loc_14000D7C2
0x14000d763  mov     rcx, gs:60h
0x14000d76c  mov     r8, rbx; BaseAddress
0x14000d76f  xor     edx, edx; Flags
0x14000d771  mov     rcx, [rcx+30h]; HeapHandle
0x14000d775  call    cs:__imp_RtlFreeHeap
0x14000d77b  mov     edi, [rsp+68h+ReturnLength]
0x14000d77f  xor     ebx, ebx
0x14000d781  inc     ebp
0x14000d783  jmp     short loc_14000D717
0x14000d785  test    esi, esi
0x14000d787  js      short loc_14000D7BD
0x14000d789  cmp     dword ptr [rbx+0Ch], 1
0x14000d78d  jbe     short loc_14000D7BD
0x14000d78f  mov     [rsp+68h+var_38], 0
0x14000d797  lea     rcx, WNF_SMSS_MEMORY_COOLING_COMPATIBLE
0x14000d79e  mov     [rsp+68h+var_40], 0
0x14000d7a6  xor     r9d, r9d
0x14000d7a9  xor     r8d, r8d
0x14000d7ac  mov     [rsp+68h+var_48], 0
0x14000d7b5  xor     edx, edx
0x14000d7b7  call    cs:__imp_NtUpdateWnfStateData
0x14000d7bd  test    rbx, rbx
0x14000d7c0  jz      short loc_14000D7DA
0x14000d7c2  mov     rcx, gs:60h
0x14000d7cb  mov     r8, rbx; BaseAddress
0x14000d7ce  xor     edx, edx; Flags
0x14000d7d0  mov     rcx, [rcx+30h]; HeapHandle
0x14000d7d4  call    cs:__imp_RtlFreeHeap
0x14000d7da  add     rsp, 48h
0x14000d7de  pop     rdi
0x14000d7df  pop     rsi
0x14000d7e0  pop     rbp
0x14000d7e1  pop     rbx
0x14000d7e2  retn
```

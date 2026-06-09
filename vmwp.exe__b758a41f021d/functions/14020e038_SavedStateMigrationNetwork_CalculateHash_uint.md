# SavedStateMigrationNetwork::CalculateHash(uint &)

- ea: `0x14020e038`
- end: `0x14020e0b0`
- name: `?CalculateHash@SavedStateMigrationNetwork@@QEAAHAEAI@Z`
- size: `120`
- prototype: `__int64 __fastcall(SavedStateMigrationNetwork *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400e96b0`
- `0x140214f00`

## callees

- `0x1400a3370`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x14020e059`
- `ntdll!RtlComputeCrc32` at `0x14020e075`
- `ntdll!RtlComputeCrc32` at `0x14020e091`
- `ntdll!RtlComputeCrc32` at `0x14020e059`
- `ntdll!RtlComputeCrc32` at `0x14020e075`
- `ntdll!RtlComputeCrc32` at `0x14020e091`

## pseudocode

```c
__int64 __fastcall SavedStateMigrationNetwork::CalculateHash(SavedStateMigrationNetwork *this, unsigned int *a2)
{
  ULONG KeyEntryTableUsedBytes; // eax
  ULONG v5; // eax
  ULONG v6; // eax

  KeyEntryTableUsedBytes = SavedStateStorage::GetKeyEntryTableUsedBytes(this);
  v5 = RtlComputeCrc32(0, *((PUCHAR *)this + 18), KeyEntryTableUsedBytes);
  v6 = RtlComputeCrc32(v5, *((PUCHAR *)this + 21), *((_DWORD *)this + 45));
  *a2 = RtlComputeCrc32(v6, *((PUCHAR *)this + 24), *((_DWORD *)this + 50));
  return 1;
}

```

## disassembly

```asm
0x14020e038  mov     [rsp+arg_0], rbx
0x14020e03d  push    rdi
0x14020e03e  sub     rsp, 20h
0x14020e042  mov     rdi, rdx
0x14020e045  mov     rbx, rcx
0x14020e048  call    ?GetKeyEntryTableUsedBytes@SavedStateStorage@@IEAAIXZ; SavedStateStorage::GetKeyEntryTableUsedBytes(void)
0x14020e04d  mov     rdx, [rbx+90h]; Buffer
0x14020e054  mov     r8d, eax; Length
0x14020e057  xor     ecx, ecx; InitialCrc
0x14020e059  call    cs:__imp_RtlComputeCrc32
0x14020e060  nop     dword ptr [rax+rax+00h]
0x14020e065  mov     r8d, [rbx+0B4h]; Length
0x14020e06c  mov     ecx, eax; InitialCrc
0x14020e06e  mov     rdx, [rbx+0A8h]; Buffer
0x14020e075  call    cs:__imp_RtlComputeCrc32
0x14020e07c  nop     dword ptr [rax+rax+00h]
0x14020e081  mov     r8d, [rbx+0C8h]; Length
0x14020e088  mov     ecx, eax; InitialCrc
0x14020e08a  mov     rdx, [rbx+0C0h]; Buffer
0x14020e091  call    cs:__imp_RtlComputeCrc32
0x14020e098  nop     dword ptr [rax+rax+00h]
0x14020e09d  mov     rbx, [rsp+28h+arg_0]
0x14020e0a2  mov     [rdi], eax
0x14020e0a4  mov     eax, 1
0x14020e0a9  add     rsp, 20h
0x14020e0ad  pop     rdi
0x14020e0ae  retn
```

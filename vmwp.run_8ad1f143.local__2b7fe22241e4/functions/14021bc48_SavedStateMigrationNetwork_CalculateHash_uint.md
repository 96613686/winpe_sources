# SavedStateMigrationNetwork::CalculateHash(uint &)

- ea: `0x14021bc48`
- end: `0x14021bcc0`
- name: `?CalculateHash@SavedStateMigrationNetwork@@QEAAHAEAI@Z`
- size: `120`
- prototype: `__int64 __fastcall(SavedStateMigrationNetwork *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a0720`
- `0x1400a0874`

## callees

- `0x1400a15b4`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x14021bc69`
- `ntdll!RtlComputeCrc32` at `0x14021bc85`
- `ntdll!RtlComputeCrc32` at `0x14021bca1`
- `ntdll!RtlComputeCrc32` at `0x14021bc69`
- `ntdll!RtlComputeCrc32` at `0x14021bc85`
- `ntdll!RtlComputeCrc32` at `0x14021bca1`

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
0x14021bc48  mov     [rsp+arg_0], rbx
0x14021bc4d  push    rdi
0x14021bc4e  sub     rsp, 20h
0x14021bc52  mov     rdi, rdx
0x14021bc55  mov     rbx, rcx
0x14021bc58  call    ?GetKeyEntryTableUsedBytes@SavedStateStorage@@IEAAIXZ; SavedStateStorage::GetKeyEntryTableUsedBytes(void)
0x14021bc5d  mov     rdx, [rbx+90h]; Buffer
0x14021bc64  mov     r8d, eax; Length
0x14021bc67  xor     ecx, ecx; InitialCrc
0x14021bc69  call    cs:__imp_RtlComputeCrc32
0x14021bc70  nop     dword ptr [rax+rax+00h]
0x14021bc75  mov     r8d, [rbx+0B4h]; Length
0x14021bc7c  mov     ecx, eax; InitialCrc
0x14021bc7e  mov     rdx, [rbx+0A8h]; Buffer
0x14021bc85  call    cs:__imp_RtlComputeCrc32
0x14021bc8c  nop     dword ptr [rax+rax+00h]
0x14021bc91  mov     r8d, [rbx+0C8h]; Length
0x14021bc98  mov     ecx, eax; InitialCrc
0x14021bc9a  mov     rdx, [rbx+0C0h]; Buffer
0x14021bca1  call    cs:__imp_RtlComputeCrc32
0x14021bca8  nop     dword ptr [rax+rax+00h]
0x14021bcad  mov     rbx, [rsp+28h+arg_0]
0x14021bcb2  mov     [rdi], eax
0x14021bcb4  mov     eax, 1
0x14021bcb9  add     rsp, 20h
0x14021bcbd  pop     rdi
0x14021bcbe  retn
```

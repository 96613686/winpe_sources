# WinSAT::CompressionWorkload::GetPerThreadWorkingSetReqs(ulong &)

- ea: `0x140078af0`
- end: `0x140078b65`
- name: `?GetPerThreadWorkingSetReqs@CompressionWorkload@WinSAT@@UEBAKAEAK@Z`
- size: `117`
- prototype: `unsigned int __fastcall(WinSAT::CompressionWorkload *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140078af0`

## import_xrefs

- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x140078b1d`
- `ntdll!RtlGetCompressionWorkSpaceSize` at `0x140078b1d`
- `ntdll!RtlNtStatusToDosError` at `0x140078b29`
- `ntdll!RtlNtStatusToDosError` at `0x140078b29`

## pseudocode

```c
ULONG __fastcall WinSAT::CompressionWorkload::GetPerThreadWorkingSetReqs(
        WinSAT::CompressionWorkload *this,
        unsigned int *a2)
{
  NTSTATUS CompressionWorkSpaceSize; // eax
  ULONG v6; // eax
  unsigned int v7; // ecx
  ULONG v8; // [rsp+40h] [rbp+18h] BYREF
  ULONG v9; // [rsp+48h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  CompressionWorkSpaceSize = RtlGetCompressionWorkSpaceSize(2u, &v8, &v9);
  if ( CompressionWorkSpaceSize )
    return RtlNtStatusToDosError(CompressionWorkSpaceSize);
  v6 = v9;
  *a2 = 0;
  v7 = *((_DWORD *)this + 252);
  *a2 = v7;
  if ( v8 > v6 )
    v6 = v8;
  *a2 = v7 + *((_DWORD *)this + 252) + v6;
  return 0;
}

```

## disassembly

```asm
0x140078af0  mov     rax, rsp
0x140078af3  mov     [rax+8], rbx
0x140078af7  push    rdi
0x140078af8  sub     rsp, 20h
0x140078afc  mov     rbx, rdx
0x140078aff  mov     dword ptr [rax+18h], 0
0x140078b06  mov     rdi, rcx
0x140078b09  mov     dword ptr [rax+20h], 0
0x140078b10  mov     ecx, 2; CompressionFormatAndEngine
0x140078b15  lea     rdx, [rax+18h]; CompressBufferWorkSpaceSize
0x140078b19  lea     r8, [rax+20h]; CompressFragmentWorkSpaceSize
0x140078b1d  call    cs:__imp_RtlGetCompressionWorkSpaceSize
0x140078b23  test    eax, eax
0x140078b25  jz      short loc_140078B31
0x140078b27  mov     ecx, eax; Status
0x140078b29  call    cs:__imp_RtlNtStatusToDosError
0x140078b2f  jmp     short loc_140078B5A
0x140078b31  mov     eax, [rsp+28h+arg_18]
0x140078b35  mov     dword ptr [rbx], 0
0x140078b3b  mov     ecx, [rdi+3F0h]
0x140078b41  mov     [rbx], ecx
0x140078b43  mov     edx, [rdi+3F0h]
0x140078b49  add     edx, ecx
0x140078b4b  cmp     [rsp+28h+arg_10], eax
0x140078b4f  cmova   eax, [rsp+28h+arg_10]
0x140078b54  add     eax, edx
0x140078b56  mov     [rbx], eax
0x140078b58  xor     eax, eax
0x140078b5a  mov     rbx, [rsp+28h+arg_0]
0x140078b5f  add     rsp, 20h
0x140078b63  pop     rdi
0x140078b64  retn
```

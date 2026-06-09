# VmsUtilComputeFlowSignature

- ea: `0x14014b3dc`
- end: `0x14014b467`
- name: `VmsUtilComputeFlowSignature`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400f4284`
- `0x1401577b8`

## import_xrefs

- `NETIO!RtlCompute37Hash` at `0x14014b3f4`
- `NETIO!RtlCompute37Hash` at `0x14014b40c`
- `NETIO!RtlCompute37Hash` at `0x14014b424`
- `NETIO!RtlCompute37Hash` at `0x14014b43c`
- `NETIO!RtlCompute37Hash` at `0x14014b454`
- `NETIO!RtlCompute37Hash` at `0x14014b3f4`
- `NETIO!RtlCompute37Hash` at `0x14014b40c`
- `NETIO!RtlCompute37Hash` at `0x14014b424`
- `NETIO!RtlCompute37Hash` at `0x14014b43c`
- `NETIO!RtlCompute37Hash` at `0x14014b454`

## pseudocode

```c
__int64 __fastcall VmsUtilComputeFlowSignature(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax

  v2 = RtlCompute37Hash((unsigned int)Vms37HashSeed, a1, 1);
  v3 = RtlCompute37Hash(v2, a1 + 4, 16);
  v4 = RtlCompute37Hash(v3, a1 + 20, 16);
  v5 = RtlCompute37Hash(v4, a1 + 36, 2);
  return RtlCompute37Hash(v5, a1 + 38, 2);
}

```

## disassembly

```asm
0x14014b3dc  push    rbx
0x14014b3de  sub     rsp, 20h
0x14014b3e2  mov     rbx, rcx
0x14014b3e5  mov     rdx, rcx
0x14014b3e8  mov     ecx, cs:Vms37HashSeed
0x14014b3ee  mov     r8d, 1
0x14014b3f4  call    cs:__imp_RtlCompute37Hash
0x14014b3fb  nop     dword ptr [rax+rax+00h]
0x14014b400  lea     rdx, [rbx+4]
0x14014b404  mov     r8d, 10h
0x14014b40a  mov     ecx, eax
0x14014b40c  call    cs:__imp_RtlCompute37Hash
0x14014b413  nop     dword ptr [rax+rax+00h]
0x14014b418  lea     rdx, [rbx+14h]
0x14014b41c  mov     r8d, 10h
0x14014b422  mov     ecx, eax
0x14014b424  call    cs:__imp_RtlCompute37Hash
0x14014b42b  nop     dword ptr [rax+rax+00h]
0x14014b430  lea     rdx, [rbx+24h]
0x14014b434  mov     r8d, 2
0x14014b43a  mov     ecx, eax
0x14014b43c  call    cs:__imp_RtlCompute37Hash
0x14014b443  nop     dword ptr [rax+rax+00h]
0x14014b448  lea     rdx, [rbx+26h]
0x14014b44c  mov     r8d, 2
0x14014b452  mov     ecx, eax
0x14014b454  call    cs:__imp_RtlCompute37Hash
0x14014b45b  nop     dword ptr [rax+rax+00h]
0x14014b460  add     rsp, 20h
0x14014b464  pop     rbx
0x14014b465  retn
```

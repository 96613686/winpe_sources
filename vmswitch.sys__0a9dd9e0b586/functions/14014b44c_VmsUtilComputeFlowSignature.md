# VmsUtilComputeFlowSignature

- ea: `0x14014b44c`
- end: `0x14014b4d7`
- name: `VmsUtilComputeFlowSignature`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400f42f4`
- `0x140157828`

## import_xrefs

- `NETIO!RtlCompute37Hash` at `0x14014b464`
- `NETIO!RtlCompute37Hash` at `0x14014b47c`
- `NETIO!RtlCompute37Hash` at `0x14014b494`
- `NETIO!RtlCompute37Hash` at `0x14014b4ac`
- `NETIO!RtlCompute37Hash` at `0x14014b4c4`
- `NETIO!RtlCompute37Hash` at `0x14014b464`
- `NETIO!RtlCompute37Hash` at `0x14014b47c`
- `NETIO!RtlCompute37Hash` at `0x14014b494`
- `NETIO!RtlCompute37Hash` at `0x14014b4ac`
- `NETIO!RtlCompute37Hash` at `0x14014b4c4`

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
0x14014b44c  push    rbx
0x14014b44e  sub     rsp, 20h
0x14014b452  mov     rbx, rcx
0x14014b455  mov     rdx, rcx
0x14014b458  mov     ecx, cs:Vms37HashSeed
0x14014b45e  mov     r8d, 1
0x14014b464  call    cs:__imp_RtlCompute37Hash
0x14014b46b  nop     dword ptr [rax+rax+00h]
0x14014b470  lea     rdx, [rbx+4]
0x14014b474  mov     r8d, 10h
0x14014b47a  mov     ecx, eax
0x14014b47c  call    cs:__imp_RtlCompute37Hash
0x14014b483  nop     dword ptr [rax+rax+00h]
0x14014b488  lea     rdx, [rbx+14h]
0x14014b48c  mov     r8d, 10h
0x14014b492  mov     ecx, eax
0x14014b494  call    cs:__imp_RtlCompute37Hash
0x14014b49b  nop     dword ptr [rax+rax+00h]
0x14014b4a0  lea     rdx, [rbx+24h]
0x14014b4a4  mov     r8d, 2
0x14014b4aa  mov     ecx, eax
0x14014b4ac  call    cs:__imp_RtlCompute37Hash
0x14014b4b3  nop     dword ptr [rax+rax+00h]
0x14014b4b8  lea     rdx, [rbx+26h]
0x14014b4bc  mov     r8d, 2
0x14014b4c2  mov     ecx, eax
0x14014b4c4  call    cs:__imp_RtlCompute37Hash
0x14014b4cb  nop     dword ptr [rax+rax+00h]
0x14014b4d0  add     rsp, 20h
0x14014b4d4  pop     rbx
0x14014b4d5  retn
```

# IoPerfCleanup

- ea: `0x1400d2e58`
- end: `0x1400d2f14`
- name: `IoPerfCleanup`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026800`

## callees

- `0x14005dd00`
- `0x1400d2e58`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400d2ea4`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400d2ea4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2ef8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2edc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2ef8`

## pseudocode

```c
void IoPerfCleanup()
{
  void *v0; // rcx
  void *v1; // rcx
  void *v2; // rcx

  byte_140090322 = 1;
  WORD1(qword_1400901C0) = 0;
  memset(&qword_1400901C8, 0, 0x80u);
  memset(&IoPerfLatencyLevels, 0, 0x80u);
  if ( byte_140090398 )
    ExDeleteResourceLite(&Resource);
  v0 = (void *)_InterlockedExchange64(&IoPerfGlobalContext, 0);
  if ( v0 )
    ExFreePoolWithTag(v0, 0);
  v1 = (void *)_InterlockedExchange64(&qword_1400902C8, 0);
  if ( v1 )
    ExFreePoolWithTag(v1, 0);
  v2 = (void *)_InterlockedExchange64((volatile __int64 *)&Src, 0);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  dword_1400903C8 = 0;
}

```

## disassembly

```asm
0x1400d2e58  sub     rsp, 28h
0x1400d2e5c  xor     eax, eax
0x1400d2e5e  mov     cs:byte_140090322, 1
0x1400d2e65  xor     edx, edx; Val
0x1400d2e67  mov     word ptr cs:qword_1400901C0+2, ax
0x1400d2e6e  mov     r8d, 80h; Size
0x1400d2e74  lea     rcx, qword_1400901C8; void *
0x1400d2e7b  call    memset
0x1400d2e80  xor     edx, edx; Val
0x1400d2e82  lea     rcx, IoPerfLatencyLevels; void *
0x1400d2e89  mov     r8d, 80h; Size
0x1400d2e8f  call    memset
0x1400d2e94  cmp     cs:byte_140090398, 0
0x1400d2e9b  jz      short loc_1400D2EB0
0x1400d2e9d  lea     rcx, Resource; Resource
0x1400d2ea4  call    cs:__imp_ExDeleteResourceLite
0x1400d2eab  nop     dword ptr [rax+rax+00h]
0x1400d2eb0  xor     ecx, ecx
0x1400d2eb2  xchg    rcx, cs:IoPerfGlobalContext; P
0x1400d2eb9  test    rcx, rcx
0x1400d2ebc  jz      short loc_1400D2ECC
0x1400d2ebe  xor     edx, edx; Tag
0x1400d2ec0  call    cs:__imp_ExFreePoolWithTag
0x1400d2ec7  nop     dword ptr [rax+rax+00h]
0x1400d2ecc  xor     ecx, ecx
0x1400d2ece  xchg    rcx, cs:qword_1400902C8; P
0x1400d2ed5  test    rcx, rcx
0x1400d2ed8  jz      short loc_1400D2EE8
0x1400d2eda  xor     edx, edx; Tag
0x1400d2edc  call    cs:__imp_ExFreePoolWithTag
0x1400d2ee3  nop     dword ptr [rax+rax+00h]
0x1400d2ee8  xor     ecx, ecx
0x1400d2eea  xchg    rcx, cs:Src; P
0x1400d2ef1  test    rcx, rcx
0x1400d2ef4  jz      short loc_1400D2F04
0x1400d2ef6  xor     edx, edx; Tag
0x1400d2ef8  call    cs:__imp_ExFreePoolWithTag
0x1400d2eff  nop     dword ptr [rax+rax+00h]
0x1400d2f04  mov     cs:dword_1400903C8, 0
0x1400d2f0e  add     rsp, 28h
0x1400d2f12  retn
```

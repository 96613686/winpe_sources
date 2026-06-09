# IoPerfCleanup

- ea: `0x1400d2de8`
- end: `0x1400d2ea4`
- name: `IoPerfCleanup`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140026c20`

## callees

- `0x14005e100`
- `0x1400d2de8`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400d2e34`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400d2e34`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e88`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e50`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d2e88`

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
0x1400d2de8  sub     rsp, 28h
0x1400d2dec  xor     eax, eax
0x1400d2dee  mov     cs:byte_140090322, 1
0x1400d2df5  xor     edx, edx; Val
0x1400d2df7  mov     word ptr cs:qword_1400901C0+2, ax
0x1400d2dfe  mov     r8d, 80h; Size
0x1400d2e04  lea     rcx, qword_1400901C8; void *
0x1400d2e0b  call    memset
0x1400d2e10  xor     edx, edx; Val
0x1400d2e12  lea     rcx, IoPerfLatencyLevels; void *
0x1400d2e19  mov     r8d, 80h; Size
0x1400d2e1f  call    memset
0x1400d2e24  cmp     cs:byte_140090398, 0
0x1400d2e2b  jz      short loc_1400D2E40
0x1400d2e2d  lea     rcx, Resource; Resource
0x1400d2e34  call    cs:__imp_ExDeleteResourceLite
0x1400d2e3b  nop     dword ptr [rax+rax+00h]
0x1400d2e40  xor     ecx, ecx
0x1400d2e42  xchg    rcx, cs:IoPerfGlobalContext; P
0x1400d2e49  test    rcx, rcx
0x1400d2e4c  jz      short loc_1400D2E5C
0x1400d2e4e  xor     edx, edx; Tag
0x1400d2e50  call    cs:__imp_ExFreePoolWithTag
0x1400d2e57  nop     dword ptr [rax+rax+00h]
0x1400d2e5c  xor     ecx, ecx
0x1400d2e5e  xchg    rcx, cs:qword_1400902C8; P
0x1400d2e65  test    rcx, rcx
0x1400d2e68  jz      short loc_1400D2E78
0x1400d2e6a  xor     edx, edx; Tag
0x1400d2e6c  call    cs:__imp_ExFreePoolWithTag
0x1400d2e73  nop     dword ptr [rax+rax+00h]
0x1400d2e78  xor     ecx, ecx
0x1400d2e7a  xchg    rcx, cs:Src; P
0x1400d2e81  test    rcx, rcx
0x1400d2e84  jz      short loc_1400D2E94
0x1400d2e86  xor     edx, edx; Tag
0x1400d2e88  call    cs:__imp_ExFreePoolWithTag
0x1400d2e8f  nop     dword ptr [rax+rax+00h]
0x1400d2e94  mov     cs:dword_1400903C8, 0
0x1400d2e9e  add     rsp, 28h
0x1400d2ea2  retn
```

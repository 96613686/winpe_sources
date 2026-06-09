# SmpDeleteTargetFile

- ea: `0x1400140c8`
- end: `0x1400140fa`
- name: `SmpDeleteTargetFile`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops, loader_planting`

## callers

- `0x140013fd8`
- `0x14001426c`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1400140ef`
- `ntdll!NtSetInformationFile` at `0x1400140ef`

## pseudocode

```c
NTSTATUS __fastcall SmpDeleteTargetFile(void *a1)
{
  struct _IO_STATUS_BLOCK v2; // [rsp+30h] [rbp-18h] BYREF
  char v3; // [rsp+58h] [rbp+10h] BYREF

  v3 = 1;
  v2 = 0;
  return NtSetInformationFile(a1, &v2, &v3, 1u, FileDispositionInformation);
}

```

## disassembly

```asm
0x1400140c8  mov     rax, rsp
0x1400140cb  sub     rsp, 48h
0x1400140cf  xorps   xmm0, xmm0
0x1400140d2  mov     byte ptr [rax+10h], 1
0x1400140d6  mov     r9d, 1; Length
0x1400140dc  mov     dword ptr [rax-28h], 0Dh
0x1400140e3  lea     r8, [rax+10h]; FileInformation
0x1400140e7  lea     rdx, [rax-18h]; IoStatusBlock
0x1400140eb  movups  xmmword ptr [rax-18h], xmm0
0x1400140ef  call    cs:__imp_NtSetInformationFile
0x1400140f5  add     rsp, 48h
0x1400140f9  retn
```

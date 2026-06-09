# SmpFinalizePathStrings

- ea: `0x14000e6c0`
- end: `0x14000e79a`
- name: `SmpFinalizePathStrings`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x14000c638`

## callees

- `0x14000e6c0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x14000e6de`
- `ntdll!RtlInitUnicodeString` at `0x14000e6de`
- `ntdll!RtlGetNtSystemRoot` at `0x14000e6ce`
- `ntdll!RtlGetNtSystemRoot` at `0x14000e6ce`
- `ntdll!RtlAllocateHeap` at `0x14000e71a`
- `ntdll!RtlAllocateHeap` at `0x14000e71a`
- `ntdll!RtlFreeHeap` at `0x14000e778`
- `ntdll!RtlFreeHeap` at `0x14000e778`
- `ntdll!RtlAppendUnicodeToString` at `0x14000e74a`
- `ntdll!RtlAppendUnicodeToString` at `0x14000e74a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000e738`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000e75c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000e738`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000e75c`

## string_xrefs

- `0x14000e73e`: `\system32;`

## pseudocode

```c
__int64 __fastcall SmpFinalizePathStrings(__int64 a1, __int64 a2)
{
  const WCHAR *NtSystemRoot; // rax
  unsigned int v3; // ebx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-18h] BYREF

  Destination = 0;
  NtSystemRoot = (const WCHAR *)RtlGetNtSystemRoot(a1, a2);
  RtlInitUnicodeString(&SmpSystemRoot, NtSystemRoot);
  Destination.Length = 0;
  Destination.MaximumLength = SmpSystemRoot.MaximumLength + SmpDefaultLibPath.MaximumLength + 20;
  Destination.Buffer = (PWSTR)RtlAllocateHeap(
                                *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                                SmBaseTag,
                                Destination.MaximumLength);
  if ( Destination.Buffer )
  {
    v3 = 0;
    RtlAppendUnicodeStringToString(&Destination, &SmpSystemRoot);
    RtlAppendUnicodeToString(&Destination, L"\\system32;");
    RtlAppendUnicodeStringToString(&Destination, &SmpDefaultLibPath);
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, SmpDefaultLibPath.Buffer);
    SmpDefaultLibPath = Destination;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
  return v3;
}

```

## disassembly

```asm
0x14000e6c0  push    rbx
0x14000e6c2  sub     rsp, 30h
0x14000e6c6  xorps   xmm0, xmm0
0x14000e6c9  movups  xmmword ptr [rsp+38h+Destination.Length], xmm0
0x14000e6ce  call    cs:__imp_RtlGetNtSystemRoot
0x14000e6d4  mov     rdx, rax; SourceString
0x14000e6d7  lea     rcx, SmpSystemRoot; DestinationString
0x14000e6de  call    cs:__imp_RtlInitUnicodeString
0x14000e6e4  xor     eax, eax
0x14000e6e6  mov     [rsp+38h+Destination.Length], ax
0x14000e6eb  movzx   eax, cs:SmpDefaultLibPath.MaximumLength
0x14000e6f2  add     ax, 14h
0x14000e6f6  add     ax, cs:SmpSystemRoot.MaximumLength
0x14000e6fd  movzx   r8d, ax; Size
0x14000e701  mov     [rsp+38h+Destination.MaximumLength], r8w
0x14000e707  mov     rcx, gs:60h
0x14000e710  mov     edx, cs:SmBaseTag; Flags
0x14000e716  mov     rcx, [rcx+30h]; HeapHandle
0x14000e71a  call    cs:__imp_RtlAllocateHeap
0x14000e720  mov     [rsp+38h+Destination.Buffer], rax
0x14000e725  test    rax, rax
0x14000e728  jz      short loc_14000E78D
0x14000e72a  lea     rdx, SmpSystemRoot; Source
0x14000e731  xor     ebx, ebx
0x14000e733  lea     rcx, [rsp+38h+Destination]; Destination
0x14000e738  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e73e  lea     rdx, aSystem32_0; "\\system32;"
0x14000e745  lea     rcx, [rsp+38h+Destination]; Destination
0x14000e74a  call    cs:__imp_RtlAppendUnicodeToString
0x14000e750  lea     rdx, SmpDefaultLibPath; Source
0x14000e757  lea     rcx, [rsp+38h+Destination]; Destination
0x14000e75c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000e762  mov     rcx, gs:60h
0x14000e76b  xor     edx, edx; Flags
0x14000e76d  mov     r8, cs:SmpDefaultLibPath.Buffer; BaseAddress
0x14000e774  mov     rcx, [rcx+30h]; HeapHandle
0x14000e778  call    cs:__imp_RtlFreeHeap
0x14000e77e  movups  xmm0, xmmword ptr [rsp+38h+Destination.Length]
0x14000e783  movdqu  xmmword ptr cs:SmpDefaultLibPath.Length, xmm0
0x14000e78b  jmp     short loc_14000E792
0x14000e78d  mov     ebx, 0C0000017h
0x14000e792  mov     eax, ebx
0x14000e794  add     rsp, 30h
0x14000e798  pop     rbx
0x14000e799  retn
```

# SmpConfigureS0InitCmd

- ea: `0x1400138c0`
- end: `0x140013944`
- name: `SmpConfigureS0InitCmd`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400138c0`
- `0x14001cc11`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140013906`
- `ntdll!RtlAllocateHeap` at `0x140013906`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400138e1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1400138e1`

## pseudocode

```c
NTSTATUS __fastcall SmpConfigureS0InitCmd(__int64 a1, __int64 a2, const WCHAR *a3)
{
  NTSTATUS result; // eax
  WCHAR *Heap; // rax

  if ( a3 )
  {
    result = RtlInitUnicodeStringEx(&SmpS0InitCmd, a3);
    if ( result < 0 )
      return result;
    Heap = (WCHAR *)RtlAllocateHeap(
                      *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                      SmBaseTag,
                      SmpS0InitCmd.MaximumLength);
    SmpS0InitCmd.Buffer = Heap;
    if ( !Heap )
      return -1073741801;
    memcpy_0(Heap, a3, SmpS0InitCmd.MaximumLength);
    SmpS0CommandOverride = 1;
  }
  else
  {
    SmpS0CommandOverride = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400138c0  push    rbx
0x1400138c2  sub     rsp, 20h
0x1400138c6  mov     rbx, r8
0x1400138c9  test    r8, r8
0x1400138cc  jnz     short loc_1400138D7
0x1400138ce  mov     cs:SmpS0CommandOverride, r8d
0x1400138d5  jmp     short loc_14001393C
0x1400138d7  mov     rdx, rbx; SourceString
0x1400138da  lea     rcx, SmpS0InitCmd; DestinationString
0x1400138e1  call    cs:__imp_RtlInitUnicodeStringEx
0x1400138e7  test    eax, eax
0x1400138e9  js      short loc_14001393E
0x1400138eb  mov     rcx, gs:60h
0x1400138f4  movzx   r8d, cs:SmpS0InitCmd.MaximumLength; Size
0x1400138fc  mov     edx, cs:SmBaseTag; Flags
0x140013902  mov     rcx, [rcx+30h]; HeapHandle
0x140013906  call    cs:__imp_RtlAllocateHeap
0x14001390c  mov     cs:SmpS0InitCmd.Buffer, rax
0x140013913  test    rax, rax
0x140013916  jnz     short loc_14001391F
0x140013918  mov     eax, 0C0000017h
0x14001391d  jmp     short loc_14001393E
0x14001391f  movzx   r8d, cs:SmpS0InitCmd.MaximumLength; MaxCount
0x140013927  mov     rdx, rbx; Src
0x14001392a  mov     rcx, rax; void *
0x14001392d  call    memcpy_0
0x140013932  mov     cs:SmpS0CommandOverride, 1
0x14001393c  xor     eax, eax
0x14001393e  add     rsp, 20h
0x140013942  pop     rbx
0x140013943  retn
```

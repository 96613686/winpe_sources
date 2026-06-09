# SmpExpandKnownDllsPath

- ea: `0x14000d83c`
- end: `0x14000d8cf`
- name: `SmpExpandKnownDllsPath`
- size: `147`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140015660`

## callees

- `0x14000d83c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000d874`
- `ntdll!RtlAllocateHeap` at `0x14000d874`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000d8a9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x14000d8a9`
- `ntdll!RtlCopyUnicodeString` at `0x14000d89d`
- `ntdll!RtlCopyUnicodeString` at `0x14000d89d`

## pseudocode

```c
__int64 __fastcall SmpExpandKnownDllsPath(PCUNICODE_STRING Source, PUNICODE_STRING Destination)
{
  USHORT v4; // si
  WCHAR *Heap; // rax
  __int64 result; // rax

  v4 = SmpSystemRoot.Length + Source->Length + 2;
  Heap = (WCHAR *)RtlAllocateHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v4);
  Destination->Buffer = Heap;
  if ( !Heap )
    return 3221225626LL;
  Destination->MaximumLength = v4;
  Destination->Length = 0;
  RtlCopyUnicodeString(Destination, &SmpSystemRoot);
  RtlAppendUnicodeStringToString(Destination, Source);
  result = 0;
  Destination->Buffer[(unsigned __int64)Destination->Length >> 1] = 0;
  return result;
}

```

## disassembly

```asm
0x14000d83c  mov     [rsp+arg_0], rbx
0x14000d841  mov     [rsp+arg_8], rsi
0x14000d846  push    rdi
0x14000d847  sub     rsp, 20h
0x14000d84b  movzx   eax, word ptr [rcx]
0x14000d84e  mov     rdi, rcx
0x14000d851  mov     rcx, gs:60h
0x14000d85a  add     ax, 2
0x14000d85e  add     ax, cs:SmpSystemRoot.Length
0x14000d865  mov     rbx, rdx
0x14000d868  movzx   esi, ax
0x14000d86b  xor     edx, edx; Flags
0x14000d86d  mov     r8d, esi; Size
0x14000d870  mov     rcx, [rcx+30h]; HeapHandle
0x14000d874  call    cs:__imp_RtlAllocateHeap
0x14000d87a  mov     [rbx+8], rax
0x14000d87e  test    rax, rax
0x14000d881  jnz     short loc_14000D88A
0x14000d883  mov     eax, 0C000009Ah
0x14000d888  jmp     short loc_14000D8BF
0x14000d88a  xor     eax, eax
0x14000d88c  mov     [rbx+2], si
0x14000d890  lea     rdx, SmpSystemRoot; SourceString
0x14000d897  mov     [rbx], ax
0x14000d89a  mov     rcx, rbx; DestinationString
0x14000d89d  call    cs:__imp_RtlCopyUnicodeString
0x14000d8a3  mov     rdx, rdi; Source
0x14000d8a6  mov     rcx, rbx; Destination
0x14000d8a9  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000d8af  movzx   edx, word ptr [rbx]
0x14000d8b2  mov     rcx, [rbx+8]
0x14000d8b6  shr     rdx, 1
0x14000d8b9  xor     eax, eax
0x14000d8bb  mov     [rcx+rdx*2], ax
0x14000d8bf  mov     rbx, [rsp+28h+arg_0]
0x14000d8c4  mov     rsi, [rsp+28h+arg_8]
0x14000d8c9  add     rsp, 20h
0x14000d8cd  pop     rdi
0x14000d8ce  retn
```

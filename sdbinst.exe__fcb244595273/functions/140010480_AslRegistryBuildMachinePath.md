# AslRegistryBuildMachinePath

- ea: `0x140010480`
- end: `0x14001055f`
- name: `AslRegistryBuildMachinePath`
- size: `223`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination, PCWSTR Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140010568`

## callees

- `0x14001008c`
- `0x140010480`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400104a3`
- `ntdll!RtlInitUnicodeString` at `0x1400104a3`
- `ntdll!RtlAllocateHeap` at `0x1400104e4`
- `ntdll!RtlAllocateHeap` at `0x1400104e4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140010525`
- `ntdll!RtlAppendUnicodeStringToString` at `0x140010525`
- `ntdll!RtlAppendUnicodeToString` at `0x140010540`
- `ntdll!RtlAppendUnicodeToString` at `0x14001054c`
- `ntdll!RtlAppendUnicodeToString` at `0x140010540`
- `ntdll!RtlAppendUnicodeToString` at `0x14001054c`

## string_xrefs

- `0x140010492`: `\Registry\Machine`
- `0x140010508`: `AslRegistryBuildMachinePath`

## pseudocode

```c
__int64 __fastcall AslRegistryBuildMachinePath(PUNICODE_STRING Destination, PCWSTR Source)
{
  __int64 v4; // rax
  USHORT v5; // ax
  WCHAR *Heap; // rax
  unsigned int v7; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF

  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine");
  Destination->Length = 0;
  v4 = -1;
  do
    ++v4;
  while ( Source[v4] );
  v5 = DestinationString.Length + 2 * (v4 + 1);
  Destination->MaximumLength = v5;
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v5);
  Destination->Buffer = Heap;
  if ( Heap )
  {
    RtlAppendUnicodeStringToString(Destination, &DestinationString);
    if ( Source && *Source != 92 )
      RtlAppendUnicodeToString(Destination, L"\\");
    RtlAppendUnicodeToString(Destination, Source);
    return 0;
  }
  else
  {
    v7 = -1073741801;
    AslLogCallPrintf(
      1,
      "AslRegistryBuildMachinePath",
      1582,
      "Failed to allocate %d bytes for user key buffer",
      Destination->MaximumLength);
  }
  return v7;
}

```

## disassembly

```asm
0x140010480  push    rbx
0x140010482  push    rbp
0x140010483  push    rsi
0x140010484  push    rdi
0x140010485  sub     rsp, 48h
0x140010489  mov     rdi, rdx
0x14001048c  mov     rbx, rcx
0x14001048f  xorps   xmm0, xmm0
0x140010492  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine"
0x140010499  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x14001049e  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400104a3  call    cs:__imp_RtlInitUnicodeString
0x1400104a9  xor     esi, esi
0x1400104ab  mov     [rbx], si
0x1400104ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400104b2  inc     rax
0x1400104b5  cmp     [rdi+rax*2], si
0x1400104b9  jnz     short loc_1400104B2
0x1400104bb  mov     ebp, 1
0x1400104c0  add     ax, bp
0x1400104c3  add     ax, ax
0x1400104c6  add     ax, [rsp+68h+DestinationString.Length]
0x1400104cb  movzx   r8d, ax; Size
0x1400104cf  lea     edx, [rbp+7]; Flags
0x1400104d2  mov     [rbx+2], r8w
0x1400104d7  mov     rcx, gs:60h
0x1400104e0  mov     rcx, [rcx+30h]; HeapHandle
0x1400104e4  call    cs:__imp_RtlAllocateHeap
0x1400104ea  mov     [rbx+8], rax
0x1400104ee  test    rax, rax
0x1400104f1  jnz     short loc_14001051D
0x1400104f3  movzx   eax, word ptr [rbx+2]
0x1400104f7  lea     r9, aFailedToAlloca_11; "Failed to allocate %d bytes for user ke"...
0x1400104fe  mov     r8d, 62Eh
0x140010504  mov     [rsp+68h+var_48], eax
0x140010508  lea     rdx, aAslregistrybui_0; "AslRegistryBuildMachinePath"
0x14001050f  mov     ecx, ebp
0x140010511  mov     edi, 0C0000017h
0x140010516  call    AslLogCallPrintf
0x14001051b  jmp     short loc_140010554
0x14001051d  lea     rdx, [rsp+68h+DestinationString]; Source
0x140010522  mov     rcx, rbx; Destination
0x140010525  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001052b  test    rdi, rdi
0x14001052e  jz      short loc_140010546
0x140010530  cmp     word ptr [rdi], 5Ch ; '\'
0x140010534  jz      short loc_140010546
0x140010536  lea     rdx, asc_1400326D0; "\\"
0x14001053d  mov     rcx, rbx; Destination
0x140010540  call    cs:__imp_RtlAppendUnicodeToString
0x140010546  mov     rdx, rdi; Source
0x140010549  mov     rcx, rbx; Destination
0x14001054c  call    cs:__imp_RtlAppendUnicodeToString
0x140010552  mov     edi, esi
0x140010554  mov     eax, edi
0x140010556  add     rsp, 48h
0x14001055a  pop     rdi
0x14001055b  pop     rsi
0x14001055c  pop     rbp
0x14001055d  pop     rbx
0x14001055e  retn
```

# RemovePerThreadEntry

- ea: `0x1800266b0`
- end: `0x180026726`
- name: `RemovePerThreadEntry`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025cc8`

## callees

- `0x1800037a8`
- `0x1800266b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800266be`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800266be`

## string_xrefs

- `0x180026713`: `Marking thread data entry for thread 0x%0lx as deleted\n`

## pseudocode

```c
__int64 __fastcall RemovePerThreadEntry(int a1)
{
  _QWORD *Value; // rax
  __int64 v4; // rcx
  bool v5; // zf

  Value = TlsGetValue(GlobalTlsLastErrorIndex);
  if ( !Value )
    return 0;
  v4 = Value[1];
  if ( !v4 )
    return 0;
  v5 = g_fTracingOn == 0;
  *(_BYTE *)(v4 + 40) = 1;
  if ( !v5 && g_fProviderEnabled && (g_ulTraceFlags & 0x200000) != 0 )
    LDAPClientPrint(0x200000, "Marking thread data entry for thread 0x%0lx as deleted\n", a1);
  return 1;
}

```

## disassembly

```asm
0x1800266b0  push    rbx
0x1800266b2  sub     rsp, 20h
0x1800266b6  mov     ebx, ecx
0x1800266b8  mov     ecx, cs:GlobalTlsLastErrorIndex; dwTlsIndex
0x1800266be  call    cs:__imp_TlsGetValue
0x1800266c5  nop     dword ptr [rax+rax+00h]
0x1800266ca  test    rax, rax
0x1800266cd  jnz     short loc_1800266D8
0x1800266cf  xor     eax, eax
0x1800266d1  add     rsp, 20h
0x1800266d5  pop     rbx
0x1800266d6  retn
0x1800266d8  mov     rcx, [rax+8]
0x1800266dc  test    rcx, rcx
0x1800266df  jz      short loc_1800266CF
0x1800266e1  cmp     cs:g_fTracingOn, 0
0x1800266e8  mov     byte ptr [rcx+28h], 1
0x1800266ec  jnz     short loc_1800266FA
0x1800266ee  mov     eax, 1
0x1800266f3  add     rsp, 20h
0x1800266f7  pop     rbx
0x1800266f8  retn
0x1800266fa  cmp     cs:g_fProviderEnabled, 0
0x180026701  jz      short loc_1800266EE
0x180026703  test    cs:g_ulTraceFlags, 200000h
0x18002670e  jz      short loc_1800266EE
0x180026710  mov     r8d, ebx
0x180026713  lea     rdx, aMarkingThreadD; "Marking thread data entry for thread 0x"...
0x18002671a  mov     ecx, 200000h
0x18002671f  call    LDAPClientPrint
0x180026724  jmp     short loc_1800266EE
```

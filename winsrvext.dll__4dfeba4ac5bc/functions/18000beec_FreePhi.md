# FreePhi

- ea: `0x18000beec`
- end: `0x18000bf2f`
- name: `FreePhi`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000da7c`
- `0x18000dda0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000befc`
- `ntdll!RtlFreeUnicodeString` at `0x18000bf0f`
- `ntdll!RtlFreeUnicodeString` at `0x18000befc`
- `ntdll!RtlFreeUnicodeString` at `0x18000bf0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bf23`

## pseudocode

```c
HLOCAL __fastcall FreePhi(struct _UNICODE_STRING *a1)
{
  RtlFreeUnicodeString(a1 + 9);
  RtlFreeUnicodeString(a1 + 10);
  return LocalFree(a1);
}

```

## disassembly

```asm
0x18000beec  push    rbx
0x18000beee  sub     rsp, 20h
0x18000bef2  mov     rbx, rcx
0x18000bef5  add     rcx, 90h; UnicodeString
0x18000befc  call    cs:__imp_RtlFreeUnicodeString
0x18000bf03  nop     dword ptr [rax+rax+00h]
0x18000bf08  lea     rcx, [rbx+0A0h]; UnicodeString
0x18000bf0f  call    cs:__imp_RtlFreeUnicodeString
0x18000bf16  nop     dword ptr [rax+rax+00h]
0x18000bf1b  mov     rcx, rbx
0x18000bf1e  add     rsp, 20h
0x18000bf22  pop     rbx
0x18000bf23  jmp     cs:__imp_LocalFree
```

# SICimDBFreeCachedCtxFields

- ea: `0x180020bd4`
- end: `0x180020c30`
- name: `SICimDBFreeCachedCtxFields`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020c38`

## callees

- `0x1800187d4`
- `0x180019a4c`
- `0x180020bd4`

## import_xrefs

- `securekernel!RtlFreeUnicodeString` at `0x180020c05`
- `securekernel!RtlFreeUnicodeString` at `0x180020c15`
- `securekernel!RtlFreeUnicodeString` at `0x180020c05`
- `securekernel!RtlFreeUnicodeString` at `0x180020c15`

## pseudocode

```c
void __fastcall SICimDBFreeCachedCtxFields(__int64 a1)
{
  if ( a1 )
  {
    SIPolicyFree(*(_QWORD *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    SIPolicyFreeSIChainInfo(a1 + 16);
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 72));
    RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 88));
    *(_QWORD *)(a1 + 104) = 0;
  }
}

```

## disassembly

```asm
0x180020bd4  test    rcx, rcx
0x180020bd7  jz      short locret_180020C2E
0x180020bd9  push    rbx
0x180020bda  sub     rsp, 20h
0x180020bde  mov     rbx, rcx
0x180020be1  mov     rcx, [rcx]
0x180020be4  call    SIPolicyFree
0x180020be9  lea     rcx, [rbx+10h]
0x180020bed  mov     qword ptr [rbx], 0
0x180020bf4  mov     qword ptr [rbx+8], 0
0x180020bfc  call    SIPolicyFreeSIChainInfo
0x180020c01  lea     rcx, [rbx+48h]; UnicodeString
0x180020c05  call    cs:__imp_RtlFreeUnicodeString
0x180020c0c  nop     dword ptr [rax+rax+00h]
0x180020c11  lea     rcx, [rbx+58h]; UnicodeString
0x180020c15  call    cs:__imp_RtlFreeUnicodeString
0x180020c1c  nop     dword ptr [rax+rax+00h]
0x180020c21  mov     qword ptr [rbx+68h], 0
0x180020c29  add     rsp, 20h
0x180020c2d  pop     rbx
0x180020c2e  retn
```

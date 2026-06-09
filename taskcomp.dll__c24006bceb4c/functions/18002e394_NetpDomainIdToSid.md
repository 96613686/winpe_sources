# NetpDomainIdToSid

- ea: `0x18002e394`
- end: `0x18002e41d`
- name: `NetpDomainIdToSid`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002e28c`

## callees

- `0x18002e394`
- `0x18002e4bc`
- `0x18002e4d4`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18002e407`
- `ntdll!RtlSubAuthoritySid` at `0x18002e407`
- `ntdll!RtlLengthRequiredSid` at `0x18002e3bb`
- `ntdll!RtlLengthRequiredSid` at `0x18002e3bb`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002e3af`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002e3fa`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002e3af`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002e3fa`
- `ntdll!RtlCopySid` at `0x18002e3e1`
- `ntdll!RtlCopySid` at `0x18002e3e1`

## pseudocode

```c
__int64 __fastcall NetpDomainIdToSid(__int64 a1, ULONG a2, PSID *a3)
{
  PSID v3; // rsi
  ULONG v6; // edi
  ULONG v7; // ebp
  void *v8; // rax
  NTSTATUS v10; // eax
  PSID v11; // rcx
  PUCHAR v12; // rax

  v3 = BuiltinDomainSid;
  v6 = *RtlSubAuthorityCountSid(BuiltinDomainSid);
  v7 = RtlLengthRequiredSid(v6 + 1);
  v8 = (void *)NetpMemoryAllocate(v7);
  *a3 = v8;
  if ( !v8 )
    return 8;
  v10 = RtlCopySid(v7, v8, v3);
  v11 = *a3;
  if ( v10 >= 0 )
  {
    v12 = RtlSubAuthorityCountSid(v11);
    ++*v12;
    *RtlSubAuthoritySid(*a3, v6) = a2;
    return 0;
  }
  else
  {
    NetpMemoryFree(v11);
    return 2140;
  }
}

```

## disassembly

```asm
0x18002e394  push    rbx
0x18002e396  push    rbp
0x18002e397  push    rsi
0x18002e398  push    rdi
0x18002e399  push    r14
0x18002e39b  sub     rsp, 20h
0x18002e39f  mov     rsi, cs:BuiltinDomainSid
0x18002e3a6  mov     rbx, r8
0x18002e3a9  mov     rcx, rsi; Sid
0x18002e3ac  mov     r14d, edx
0x18002e3af  call    cs:__imp_RtlSubAuthorityCountSid
0x18002e3b5  movzx   edi, byte ptr [rax]
0x18002e3b8  lea     ecx, [rdi+1]; SubAuthorityCount
0x18002e3bb  call    cs:__imp_RtlLengthRequiredSid
0x18002e3c1  mov     ecx, eax
0x18002e3c3  mov     ebp, eax
0x18002e3c5  call    NetpMemoryAllocate
0x18002e3ca  mov     [rbx], rax
0x18002e3cd  test    rax, rax
0x18002e3d0  jnz     short loc_18002E3D9
0x18002e3d2  mov     eax, 8
0x18002e3d7  jmp     short loc_18002E412
0x18002e3d9  mov     r8, rsi; SourceSid
0x18002e3dc  mov     rdx, rax; DestinationSid
0x18002e3df  mov     ecx, ebp; DestinationSidLength
0x18002e3e1  call    cs:__imp_RtlCopySid
0x18002e3e7  mov     rcx, [rbx]; Sid
0x18002e3ea  test    eax, eax
0x18002e3ec  jns     short loc_18002E3FA
0x18002e3ee  call    NetpMemoryFree
0x18002e3f3  mov     eax, 85Ch
0x18002e3f8  jmp     short loc_18002E412
0x18002e3fa  call    cs:__imp_RtlSubAuthorityCountSid
0x18002e400  mov     edx, edi; SubAuthority
0x18002e402  inc     byte ptr [rax]
0x18002e404  mov     rcx, [rbx]; Sid
0x18002e407  call    cs:__imp_RtlSubAuthoritySid
0x18002e40d  mov     [rax], r14d
0x18002e410  xor     eax, eax
0x18002e412  add     rsp, 20h
0x18002e416  pop     r14
0x18002e418  pop     rdi
0x18002e419  pop     rsi
0x18002e41a  pop     rbp
0x18002e41b  pop     rbx
0x18002e41c  retn
```

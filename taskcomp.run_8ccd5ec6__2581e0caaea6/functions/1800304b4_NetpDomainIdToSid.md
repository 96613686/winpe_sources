# NetpDomainIdToSid

- ea: `0x1800304b4`
- end: `0x18003055c`
- name: `NetpDomainIdToSid`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180030394`

## callees

- `0x1800304b4`
- `0x1800305fc`
- `0x18003061c`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18003053f`
- `ntdll!RtlSubAuthoritySid` at `0x18003053f`
- `ntdll!RtlLengthRequiredSid` at `0x1800304e1`
- `ntdll!RtlLengthRequiredSid` at `0x1800304e1`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800304cf`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003052c`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800304cf`
- `ntdll!RtlSubAuthorityCountSid` at `0x18003052c`
- `ntdll!RtlCopySid` at `0x18003050d`
- `ntdll!RtlCopySid` at `0x18003050d`

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
0x1800304b4  push    rbx
0x1800304b6  push    rbp
0x1800304b7  push    rsi
0x1800304b8  push    rdi
0x1800304b9  push    r14
0x1800304bb  sub     rsp, 20h
0x1800304bf  mov     rsi, cs:BuiltinDomainSid
0x1800304c6  mov     rbx, r8
0x1800304c9  mov     rcx, rsi; Sid
0x1800304cc  mov     r14d, edx
0x1800304cf  call    cs:__imp_RtlSubAuthorityCountSid
0x1800304d6  nop     dword ptr [rax+rax+00h]
0x1800304db  movzx   edi, byte ptr [rax]
0x1800304de  lea     ecx, [rdi+1]; SubAuthorityCount
0x1800304e1  call    cs:__imp_RtlLengthRequiredSid
0x1800304e8  nop     dword ptr [rax+rax+00h]
0x1800304ed  mov     ecx, eax
0x1800304ef  mov     ebp, eax
0x1800304f1  call    NetpMemoryAllocate
0x1800304f6  mov     [rbx], rax
0x1800304f9  test    rax, rax
0x1800304fc  jnz     short loc_180030505
0x1800304fe  mov     eax, 8
0x180030503  jmp     short loc_180030550
0x180030505  mov     r8, rsi; SourceSid
0x180030508  mov     rdx, rax; DestinationSid
0x18003050b  mov     ecx, ebp; DestinationSidLength
0x18003050d  call    cs:__imp_RtlCopySid
0x180030514  nop     dword ptr [rax+rax+00h]
0x180030519  mov     rcx, [rbx]; Sid
0x18003051c  test    eax, eax
0x18003051e  jns     short loc_18003052C
0x180030520  call    NetpMemoryFree
0x180030525  mov     eax, 85Ch
0x18003052a  jmp     short loc_180030550
0x18003052c  call    cs:__imp_RtlSubAuthorityCountSid
0x180030533  nop     dword ptr [rax+rax+00h]
0x180030538  mov     edx, edi; SubAuthority
0x18003053a  inc     byte ptr [rax]
0x18003053c  mov     rcx, [rbx]; Sid
0x18003053f  call    cs:__imp_RtlSubAuthoritySid
0x180030546  nop     dword ptr [rax+rax+00h]
0x18003054b  mov     [rax], r14d
0x18003054e  xor     eax, eax
0x180030550  add     rsp, 20h
0x180030554  pop     r14
0x180030556  pop     rdi
0x180030557  pop     rsi
0x180030558  pop     rbp
0x180030559  pop     rbx
0x18003055a  retn
```

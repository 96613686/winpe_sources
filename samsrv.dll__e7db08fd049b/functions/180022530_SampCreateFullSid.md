# SampCreateFullSid

- ea: `0x180022530`
- end: `0x1800225df`
- name: `SampCreateFullSid`
- size: `175`
- prototype: `__int64 __fastcall(PSID SourceSid)`
- caller_count: `12`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180001760`
- `0x1800263d8`
- `0x180053f9c`
- `0x180054644`
- `0x18006c858`
- `0x18007b910`
- `0x18008db68`
- `0x1800985f0`
- `0x1800a05c0`
- `0x1800a85bc`
- `0x1800a8b50`
- `0x1800a8cd0`

## callees

- `0x180022530`
- `0x180027e24`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180022544`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002258c`
- `ntdll!RtlSubAuthorityCountSid` at `0x180022544`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002258c`
- `ntdll!RtlSubAuthoritySid` at `0x18002259b`
- `ntdll!RtlSubAuthoritySid` at `0x18002259b`
- `ntdll!RtlLengthRequiredSid` at `0x180022557`
- `ntdll!RtlLengthRequiredSid` at `0x180022557`
- `ntdll!RtlCopySid` at `0x180022583`
- `ntdll!RtlCopySid` at `0x180022583`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022566`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022566`

## pseudocode

```c
__int64 __fastcall SampCreateFullSid(PSID SourceSid, ULONG a2, PSID *a3)
{
  ULONG v6; // edi
  ULONG v7; // ebp
  HLOCAL v8; // rax
  unsigned int v9; // ebx
  PULONG v10; // rax

  v6 = (unsigned __int8)(*RtlSubAuthorityCountSid(SourceSid) + 1);
  v7 = RtlLengthRequiredSid(v6);
  v8 = LocalAlloc(0x40u, v7);
  *a3 = v8;
  if ( v8 )
  {
    RtlCopySid(v7, v8, SourceSid);
    *RtlSubAuthorityCountSid(*a3) = v6;
    v10 = RtlSubAuthoritySid(*a3, v6 - 1);
    v9 = 0;
    *v10 = a2;
  }
  else
  {
    v9 = -1073741670;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 126, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v9, v9);
  return v9;
}

```

## disassembly

```asm
0x180022530  push    rbx
0x180022532  push    rbp
0x180022533  push    rsi
0x180022534  push    rdi
0x180022535  push    r14
0x180022537  sub     rsp, 30h
0x18002253b  mov     rbx, r8
0x18002253e  mov     r14d, edx
0x180022541  mov     rsi, rcx
0x180022544  call    cs:__imp_RtlSubAuthorityCountSid
0x18002254a  movzx   r9d, byte ptr [rax]
0x18002254e  inc     r9b
0x180022551  movzx   edi, r9b
0x180022555  mov     ecx, edi; SubAuthorityCount
0x180022557  call    cs:__imp_RtlLengthRequiredSid
0x18002255d  mov     edx, eax; uBytes
0x18002255f  mov     ecx, 40h ; '@'; uFlags
0x180022564  mov     ebp, eax
0x180022566  call    cs:__imp_LocalAlloc
0x18002256c  mov     [rbx], rax
0x18002256f  test    rax, rax
0x180022572  jnz     short loc_18002257B
0x180022574  mov     ebx, 0C000009Ah
0x180022579  jmp     short loc_1800225A6
0x18002257b  mov     r8, rsi; SourceSid
0x18002257e  mov     rdx, rax; DestinationSid
0x180022581  mov     ecx, ebp; DestinationSidLength
0x180022583  call    cs:__imp_RtlCopySid
0x180022589  mov     rcx, [rbx]; Sid
0x18002258c  call    cs:__imp_RtlSubAuthorityCountSid
0x180022592  lea     edx, [rdi-1]; SubAuthority
0x180022595  mov     [rax], dil
0x180022598  mov     rcx, [rbx]; Sid
0x18002259b  call    cs:__imp_RtlSubAuthoritySid
0x1800225a1  xor     ebx, ebx
0x1800225a3  mov     [rax], r14d
0x1800225a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800225ad  test    dword ptr [rcx+44h], 20000h
0x1800225b4  jz      short loc_1800225D2
0x1800225b6  mov     rcx, [rcx+38h]
0x1800225ba  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x1800225c1  mov     edx, 7Eh ; '~'
0x1800225c6  mov     [rsp+58h+var_38], ebx
0x1800225ca  mov     r9d, ebx
0x1800225cd  call    WPP_SF_Dd
0x1800225d2  mov     eax, ebx
0x1800225d4  add     rsp, 30h
0x1800225d8  pop     r14
0x1800225da  pop     rdi
0x1800225db  pop     rsi
0x1800225dc  pop     rbp
0x1800225dd  pop     rbx
0x1800225de  retn
```

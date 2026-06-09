# SampSplitSid

- ea: `0x180021460`
- end: `0x180021541`
- name: `SampSplitSid`
- size: `225`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `18`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009030`
- `0x180033efc`
- `0x180034b6c`
- `0x180035610`
- `0x180037548`
- `0x1800386c8`
- `0x1800388c0`
- `0x180058f40`
- `0x1800902b4`
- `0x1800908f0`
- `0x1800930f8`
- `0x180093454`
- `0x180093818`
- `0x18009d630`
- `0x1800a3940`
- `0x1800aa648`
- `0x1800aee00`
- `0x1800aff40`

## callees

- `0x180021460`
- `0x180027e24`
- `0x1800bb794`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18002147e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800214de`
- `ntdll!RtlSubAuthorityCountSid` at `0x18002147e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800214de`
- `ntdll!RtlSubAuthoritySid` at `0x1800214ec`
- `ntdll!RtlSubAuthoritySid` at `0x1800214ec`
- `ntdll!RtlLengthSid` at `0x18002149c`
- `ntdll!RtlLengthSid` at `0x18002149c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800214b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800214b8`

## pseudocode

```c
__int64 __fastcall SampSplitSid(void *Src, PSID *a2, ULONG *a3)
{
  int v6; // esi
  unsigned int v7; // ebx
  ULONG v8; // eax
  PSID v9; // rcx
  size_t v10; // rbp
  HLOCAL v11; // rax
  PUCHAR v12; // rax
  PULONG v13; // rax

  v6 = *RtlSubAuthorityCountSid(Src);
  if ( !(_BYTE)v6 )
  {
    v7 = -1073741704;
    goto LABEL_9;
  }
  v8 = RtlLengthSid(Src);
  if ( a2 )
  {
    v9 = *a2;
    v10 = v8;
    if ( !*a2 )
    {
      v11 = LocalAlloc(0x40u, v8);
      *a2 = v11;
      v9 = v11;
      if ( !v11 )
      {
        v7 = -1073741670;
        goto LABEL_9;
      }
    }
    memmove_0(v9, Src, v10);
    v12 = RtlSubAuthorityCountSid(*a2);
    --*v12;
  }
  v13 = RtlSubAuthoritySid(Src, v6 - 1);
  v7 = 0;
  *a3 = *v13;
LABEL_9:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 128, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v7, v7);
  return v7;
}

```

## disassembly

```asm
0x180021460  push    rbx
0x180021462  sub     rsp, 30h
0x180021466  mov     [rsp+38h+arg_8], rsi
0x18002146b  mov     rbx, rcx
0x18002146e  mov     [rsp+38h+arg_10], rdi
0x180021473  mov     rdi, rdx
0x180021476  mov     [rsp+38h+arg_18], r14
0x18002147b  mov     r14, r8
0x18002147e  call    cs:__imp_RtlSubAuthorityCountSid
0x180021484  movzx   esi, byte ptr [rax]
0x180021487  cmp     sil, 1
0x18002148b  jnb     short loc_180021494
0x18002148d  mov     ebx, 0C0000078h
0x180021492  jmp     short loc_1800214FE
0x180021494  mov     rcx, rbx; Sid
0x180021497  mov     [rsp+38h+arg_0], rbp
0x18002149c  call    cs:__imp_RtlLengthSid
0x1800214a2  test    rdi, rdi
0x1800214a5  jz      short loc_1800214E6
0x1800214a7  mov     rcx, [rdi]; void *
0x1800214aa  mov     ebp, eax
0x1800214ac  test    rcx, rcx
0x1800214af  jnz     short loc_1800214D0
0x1800214b1  mov     edx, ebp; uBytes
0x1800214b3  mov     ecx, 40h ; '@'; uFlags
0x1800214b8  call    cs:__imp_LocalAlloc
0x1800214be  mov     [rdi], rax
0x1800214c1  mov     rcx, rax
0x1800214c4  test    rax, rax
0x1800214c7  jnz     short loc_1800214D0
0x1800214c9  mov     ebx, 0C000009Ah
0x1800214ce  jmp     short loc_1800214F9
0x1800214d0  mov     r8, rbp; Size
0x1800214d3  mov     rdx, rbx; Src
0x1800214d6  call    memmove_0
0x1800214db  mov     rcx, [rdi]; Sid
0x1800214de  call    cs:__imp_RtlSubAuthorityCountSid
0x1800214e4  dec     byte ptr [rax]
0x1800214e6  lea     edx, [rsi-1]; SubAuthority
0x1800214e9  mov     rcx, rbx; Sid
0x1800214ec  call    cs:__imp_RtlSubAuthoritySid
0x1800214f2  xor     ebx, ebx
0x1800214f4  mov     ecx, [rax]
0x1800214f6  mov     [r14], ecx
0x1800214f9  mov     rbp, [rsp+38h+arg_0]
0x1800214fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180021505  mov     r14, [rsp+38h+arg_18]
0x18002150a  mov     rdi, [rsp+38h+arg_10]
0x18002150f  mov     rsi, [rsp+38h+arg_8]
0x180021514  test    dword ptr [rcx+44h], 20000h
0x18002151b  jz      short loc_180021539
0x18002151d  mov     rcx, [rcx+38h]
0x180021521  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180021528  mov     edx, 80h
0x18002152d  mov     [rsp+38h+var_18], ebx
0x180021531  mov     r9d, ebx
0x180021534  call    WPP_SF_Dd
0x180021539  mov     eax, ebx
0x18002153b  add     rsp, 30h
0x18002153f  pop     rbx
0x180021540  retn
```

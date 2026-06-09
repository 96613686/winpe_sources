# SampExtractInternetDomainSidFromSid(void *,void * *)

- ea: `0x180053544`
- end: `0x1800535e4`
- name: `?SampExtractInternetDomainSidFromSid@@YAJPEAXPEAPEAX@Z`
- size: `160`
- prototype: `__int64 __fastcall(void *Src, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180053f9c`
- `0x180054644`

## callees

- `0x180027e24`
- `0x180053544`
- `0x1800bb794`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180053554`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800535a1`
- `ntdll!RtlSubAuthorityCountSid` at `0x180053554`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800535a1`
- `ntdll!RtlLengthSid` at `0x180053569`
- `ntdll!RtlLengthSid` at `0x180053569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053578`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053578`

## pseudocode

```c
__int64 __fastcall SampExtractInternetDomainSidFromSid(void *Src, void **a2)
{
  unsigned int v4; // ebx
  SIZE_T v5; // rsi
  HLOCAL v6; // rax
  void *v7; // rdi
  PUCHAR v8; // rax

  if ( *RtlSubAuthorityCountSid(Src) )
  {
    v5 = RtlLengthSid(Src);
    v6 = LocalAlloc(0x40u, v5);
    *a2 = v6;
    v7 = v6;
    if ( v6 )
    {
      memmove_0(v6, Src, v5);
      v8 = RtlSubAuthorityCountSid(v7);
      *v8 -= 5;
      v4 = 0;
    }
    else
    {
      v4 = -1073741670;
    }
  }
  else
  {
    v4 = -1073741704;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 127, &WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids, v4, v4);
  return v4;
}

```

## disassembly

```asm
0x180053544  push    rbx
0x180053546  push    rsi
0x180053547  push    rdi
0x180053548  push    r14
0x18005354a  sub     rsp, 38h
0x18005354e  mov     r14, rdx
0x180053551  mov     rbx, rcx
0x180053554  call    cs:__imp_RtlSubAuthorityCountSid
0x18005355a  cmp     byte ptr [rax], 1
0x18005355d  jnb     short loc_180053566
0x18005355f  mov     ebx, 0C0000078h
0x180053564  jmp     short loc_1800535AC
0x180053566  mov     rcx, rbx; Sid
0x180053569  call    cs:__imp_RtlLengthSid
0x18005356f  mov     edx, eax; uBytes
0x180053571  mov     ecx, 40h ; '@'; uFlags
0x180053576  mov     esi, eax
0x180053578  call    cs:__imp_LocalAlloc
0x18005357e  mov     [r14], rax
0x180053581  mov     rdi, rax
0x180053584  test    rax, rax
0x180053587  jnz     short loc_180053590
0x180053589  mov     ebx, 0C000009Ah
0x18005358e  jmp     short loc_1800535AC
0x180053590  mov     r8, rsi; Size
0x180053593  mov     rdx, rbx; Src
0x180053596  mov     rcx, rdi; void *
0x180053599  call    memmove_0
0x18005359e  mov     rcx, rdi; Sid
0x1800535a1  call    cs:__imp_RtlSubAuthorityCountSid
0x1800535a7  add     byte ptr [rax], 0FBh
0x1800535aa  xor     ebx, ebx
0x1800535ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800535b3  test    dword ptr [rcx+44h], 20000h
0x1800535ba  jz      short loc_1800535D8
0x1800535bc  mov     rcx, [rcx+38h]
0x1800535c0  lea     r8, WPP_24d3cb53f35333e5462bba9dfbf11e25_Traceguids
0x1800535c7  mov     edx, 7Fh
0x1800535cc  mov     [rsp+58h+var_38], ebx
0x1800535d0  mov     r9d, ebx
0x1800535d3  call    WPP_SF_Dd
0x1800535d8  mov     eax, ebx
0x1800535da  add     rsp, 38h
0x1800535de  pop     r14
0x1800535e0  pop     rdi
0x1800535e1  pop     rsi
0x1800535e2  pop     rbx
0x1800535e3  retn
```

# SampCreateAccountSid(_SAMP_OBJECT *,void * *)

- ea: `0x180022678`
- end: `0x180022781`
- name: `?SampCreateAccountSid@@YAJPEAU_SAMP_OBJECT@@PEAPEAX@Z`
- size: `265`
- prototype: `__int64 __fastcall(struct _SAMP_OBJECT *, void **)`
- caller_count: `10`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800291c0`
- `0x180056510`
- `0x180056c30`
- `0x1800573f0`
- `0x180064380`
- `0x18008cd00`
- `0x180091598`
- `0x1800a56d0`
- `0x1800a6810`
- `0x1800ac198`

## callees

- `0x180022678`
- `0x180027e24`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x1800226c0`
- `ntdll!RtlSubAuthorityCountSid` at `0x180022706`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800226c0`
- `ntdll!RtlSubAuthorityCountSid` at `0x180022706`
- `ntdll!RtlSubAuthoritySid` at `0x180022715`
- `ntdll!RtlSubAuthoritySid` at `0x180022715`
- `ntdll!RtlLengthRequiredSid` at `0x1800226cf`
- `ntdll!RtlLengthRequiredSid` at `0x1800226cf`
- `ntdll!RtlCopySid` at `0x1800226fd`
- `ntdll!RtlCopySid` at `0x1800226fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800226df`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800226df`

## pseudocode

```c
__int64 __fastcall SampCreateAccountSid(struct _SAMP_OBJECT *a1, void **a2)
{
  ULONG v2; // ebx
  void *v4; // rbp
  ULONG v5; // esi
  ULONG v6; // r14d
  HLOCAL v7; // rax
  unsigned int v8; // ebx

  v2 = 0;
  v4 = (void *)*((_QWORD *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1);
  if ( *((_DWORD *)a1 + 4) == 2 || (unsigned int)(*((_DWORD *)a1 + 4) - 3) <= 1 )
    v2 = *((_DWORD *)a1 + 62);
  v5 = (unsigned __int8)(*RtlSubAuthorityCountSid(*((PSID *)SampDefinedDomains + 170 * *((unsigned int *)a1 + 50) + 1))
                       + 1);
  v6 = RtlLengthRequiredSid(v5);
  v7 = LocalAlloc(0x40u, v6);
  *a2 = v7;
  if ( v7 )
  {
    RtlCopySid(v6, v7, v4);
    *RtlSubAuthorityCountSid(*a2) = v5;
    *RtlSubAuthoritySid(*a2, v5 - 1) = v2;
    v8 = 0;
  }
  else
  {
    v8 = -1073741670;
  }
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 126, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v8, v8);
    if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 127, WPP_48bf36016493398285a8dbc678e80a21_Traceguids, v8, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180022678  push    rbx
0x18002267a  push    rbp
0x18002267b  push    rsi
0x18002267c  push    rdi
0x18002267d  push    r14
0x18002267f  sub     rsp, 30h
0x180022683  mov     eax, [rcx+0C8h]
0x180022689  xor     ebx, ebx
0x18002268b  imul    r8, rax, 550h
0x180022692  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x180022699  mov     rdi, rdx
0x18002269c  mov     rbp, [r8+rax+8]
0x1800226a1  mov     r8d, [rcx+10h]
0x1800226a5  sub     r8d, 2
0x1800226a9  jz      short loc_1800226B7
0x1800226ab  sub     r8d, 1
0x1800226af  jz      short loc_1800226B7
0x1800226b1  cmp     r8d, 1
0x1800226b5  jnz     short loc_1800226BD
0x1800226b7  mov     ebx, [rcx+0F8h]
0x1800226bd  mov     rcx, rbp; Sid
0x1800226c0  call    cs:__imp_RtlSubAuthorityCountSid
0x1800226c6  mov     cl, [rax]
0x1800226c8  inc     cl
0x1800226ca  movzx   esi, cl
0x1800226cd  mov     ecx, esi; SubAuthorityCount
0x1800226cf  call    cs:__imp_RtlLengthRequiredSid
0x1800226d5  mov     edx, eax; uBytes
0x1800226d7  mov     ecx, 40h ; '@'; uFlags
0x1800226dc  mov     r14d, eax
0x1800226df  call    cs:__imp_LocalAlloc
0x1800226e5  mov     [rdi], rax
0x1800226e8  test    rax, rax
0x1800226eb  jnz     short loc_1800226F4
0x1800226ed  mov     ebx, 0C000009Ah
0x1800226f2  jmp     short loc_18002271F
0x1800226f4  mov     r8, rbp; SourceSid
0x1800226f7  mov     rdx, rax; DestinationSid
0x1800226fa  mov     ecx, r14d; DestinationSidLength
0x1800226fd  call    cs:__imp_RtlCopySid
0x180022703  mov     rcx, [rdi]; Sid
0x180022706  call    cs:__imp_RtlSubAuthorityCountSid
0x18002270c  lea     edx, [rsi-1]; SubAuthority
0x18002270f  mov     [rax], sil
0x180022712  mov     rcx, [rdi]; Sid
0x180022715  call    cs:__imp_RtlSubAuthoritySid
0x18002271b  mov     [rax], ebx
0x18002271d  xor     ebx, ebx
0x18002271f  mov     rcx, cs:WPP_GLOBAL_Control
0x180022726  mov     edi, 20000h
0x18002272b  test    [rcx+44h], edi
0x18002272e  jz      short loc_180022774
0x180022730  mov     rcx, [rcx+38h]
0x180022734  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x18002273b  mov     edx, 7Eh ; '~'
0x180022740  mov     [rsp+58h+var_38], ebx
0x180022744  mov     r9d, ebx
0x180022747  call    WPP_SF_Dd
0x18002274c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022753  test    [rcx+44h], edi
0x180022756  jz      short loc_180022774
0x180022758  mov     rcx, [rcx+38h]
0x18002275c  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x180022763  mov     edx, 7Fh
0x180022768  mov     [rsp+58h+var_38], ebx
0x18002276c  mov     r9d, ebx
0x18002276f  call    WPP_SF_Dd
0x180022774  mov     eax, ebx
0x180022776  add     rsp, 30h
0x18002277a  pop     r14
0x18002277c  pop     rdi
0x18002277d  pop     rsi
0x18002277e  pop     rbp
0x18002277f  pop     rbx
0x180022780  retn
```

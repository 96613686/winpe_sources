# PacValidateInfo3(_NETLOGON_VALIDATION_SAM_INFO3 * const)

- ea: `0x18008856c`
- end: `0x180088657`
- name: `?PacValidateInfo3@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800884f0`

## callees

- `0x18008856c`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1800885c0`
- `ntdll!RtlValidSid` at `0x1800885f8`
- `ntdll!RtlValidSid` at `0x18008862e`
- `ntdll!RtlValidSid` at `0x1800885c0`
- `ntdll!RtlValidSid` at `0x1800885f8`
- `ntdll!RtlValidSid` at `0x18008862e`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800885d1`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088609`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800885d1`
- `ntdll!RtlSubAuthorityCountSid` at `0x180088609`

## pseudocode

```c
__int64 __fastcall PacValidateInfo3(struct _NETLOGON_VALIDATION_SAM_INFO3 *const a1)
{
  unsigned int v2; // ecx
  unsigned int v3; // eax
  unsigned int v4; // edx
  unsigned int i; // edi

  v2 = *((_DWORD *)a1 + 39);
  if ( v2 > 0x4000 )
    return 3221225818LL;
  v3 = *((_DWORD *)a1 + 74);
  if ( v3 > 0x4000 )
    return 3221225818LL;
  v4 = *((_DWORD *)a1 + 68);
  if ( v4 > 0x4000 || v2 + v4 + v3 > 0x4000 )
    return 3221225818LL;
  if ( !RtlValidSid(*((PSID *)a1 + 28))
    || *RtlSubAuthorityCountSid(*((PSID *)a1 + 28)) == 15
    || (*((_DWORD *)a1 + 42) & 0x200) != 0
    && *((_DWORD *)a1 + 74)
    && (!RtlValidSid(*((PSID *)a1 + 36)) || *RtlSubAuthorityCountSid(*((PSID *)a1 + 36)) == 15) )
  {
    return 3221225592LL;
  }
  for ( i = 0; i < *((_DWORD *)a1 + 68); ++i )
  {
    if ( !RtlValidSid(*(PSID *)(*((_QWORD *)a1 + 35) + 16LL * i)) )
      return 3221225592LL;
  }
  return 0;
}

```

## disassembly

```asm
0x18008856c  mov     [rsp+arg_0], rbx
0x180088571  push    rdi
0x180088572  sub     rsp, 20h
0x180088576  mov     rbx, rcx
0x180088579  mov     r8d, 4000h
0x18008857f  mov     ecx, [rcx+9Ch]
0x180088585  cmp     ecx, r8d
0x180088588  ja      loc_180088647
0x18008858e  mov     eax, [rbx+128h]
0x180088594  cmp     eax, r8d
0x180088597  ja      loc_180088647
0x18008859d  mov     edx, [rbx+110h]
0x1800885a3  cmp     edx, r8d
0x1800885a6  ja      loc_180088647
0x1800885ac  add     eax, edx
0x1800885ae  add     eax, ecx
0x1800885b0  cmp     eax, r8d
0x1800885b3  ja      loc_180088647
0x1800885b9  mov     rcx, [rbx+0E0h]; Sid
0x1800885c0  call    cs:__imp_RtlValidSid
0x1800885c6  test    al, al
0x1800885c8  jz      short loc_180088640
0x1800885ca  mov     rcx, [rbx+0E0h]; Sid
0x1800885d1  call    cs:__imp_RtlSubAuthorityCountSid
0x1800885d7  cmp     byte ptr [rax], 0Fh
0x1800885da  jz      short loc_180088640
0x1800885dc  test    dword ptr [rbx+0A8h], 200h
0x1800885e6  jz      short loc_180088614
0x1800885e8  cmp     dword ptr [rbx+128h], 0
0x1800885ef  jz      short loc_180088614
0x1800885f1  mov     rcx, [rbx+120h]; Sid
0x1800885f8  call    cs:__imp_RtlValidSid
0x1800885fe  test    al, al
0x180088600  jz      short loc_180088640
0x180088602  mov     rcx, [rbx+120h]; Sid
0x180088609  call    cs:__imp_RtlSubAuthorityCountSid
0x18008860f  cmp     byte ptr [rax], 0Fh
0x180088612  jz      short loc_180088640
0x180088614  xor     edi, edi
0x180088616  cmp     edi, [rbx+110h]
0x18008861c  jnb     short loc_18008863C
0x18008861e  mov     rcx, [rbx+118h]
0x180088625  mov     eax, edi
0x180088627  add     rax, rax
0x18008862a  mov     rcx, [rcx+rax*8]; Sid
0x18008862e  call    cs:__imp_RtlValidSid
0x180088634  test    al, al
0x180088636  jz      short loc_180088640
0x180088638  inc     edi
0x18008863a  jmp     short loc_180088616
0x18008863c  xor     eax, eax
0x18008863e  jmp     short loc_18008864C
0x180088640  mov     eax, 0C0000078h
0x180088645  jmp     short loc_18008864C
0x180088647  mov     eax, 0C000015Ah
0x18008864c  mov     rbx, [rsp+28h+arg_0]
0x180088651  add     rsp, 20h
0x180088655  pop     rdi
0x180088656  retn
```

# PacValidateInfo3(_NETLOGON_VALIDATION_SAM_INFO3 * const)

- ea: `0x1800375ac`
- end: `0x180037697`
- name: `?PacValidateInfo3@@YAJQEAU_NETLOGON_VALIDATION_SAM_INFO3@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(struct _NETLOGON_VALIDATION_SAM_INFO3 *const)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180037534`

## callees

- `0x1800375ac`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x180037611`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037649`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037611`
- `ntdll!RtlSubAuthorityCountSid` at `0x180037649`
- `ntdll!RtlValidSid` at `0x180037600`
- `ntdll!RtlValidSid` at `0x180037638`
- `ntdll!RtlValidSid` at `0x18003766e`
- `ntdll!RtlValidSid` at `0x180037600`
- `ntdll!RtlValidSid` at `0x180037638`
- `ntdll!RtlValidSid` at `0x18003766e`

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
0x1800375ac  mov     [rsp+arg_0], rbx
0x1800375b1  push    rdi
0x1800375b2  sub     rsp, 20h
0x1800375b6  mov     rbx, rcx
0x1800375b9  mov     r8d, 4000h
0x1800375bf  mov     ecx, [rcx+9Ch]
0x1800375c5  cmp     ecx, r8d
0x1800375c8  ja      loc_180037687
0x1800375ce  mov     eax, [rbx+128h]
0x1800375d4  cmp     eax, r8d
0x1800375d7  ja      loc_180037687
0x1800375dd  mov     edx, [rbx+110h]
0x1800375e3  cmp     edx, r8d
0x1800375e6  ja      loc_180037687
0x1800375ec  add     eax, edx
0x1800375ee  add     eax, ecx
0x1800375f0  cmp     eax, r8d
0x1800375f3  ja      loc_180037687
0x1800375f9  mov     rcx, [rbx+0E0h]; Sid
0x180037600  call    cs:__imp_RtlValidSid
0x180037606  test    al, al
0x180037608  jz      short loc_180037680
0x18003760a  mov     rcx, [rbx+0E0h]; Sid
0x180037611  call    cs:__imp_RtlSubAuthorityCountSid
0x180037617  cmp     byte ptr [rax], 0Fh
0x18003761a  jz      short loc_180037680
0x18003761c  test    dword ptr [rbx+0A8h], 200h
0x180037626  jz      short loc_180037654
0x180037628  cmp     dword ptr [rbx+128h], 0
0x18003762f  jz      short loc_180037654
0x180037631  mov     rcx, [rbx+120h]; Sid
0x180037638  call    cs:__imp_RtlValidSid
0x18003763e  test    al, al
0x180037640  jz      short loc_180037680
0x180037642  mov     rcx, [rbx+120h]; Sid
0x180037649  call    cs:__imp_RtlSubAuthorityCountSid
0x18003764f  cmp     byte ptr [rax], 0Fh
0x180037652  jz      short loc_180037680
0x180037654  xor     edi, edi
0x180037656  cmp     edi, [rbx+110h]
0x18003765c  jnb     short loc_18003767C
0x18003765e  mov     rcx, [rbx+118h]
0x180037665  mov     eax, edi
0x180037667  add     rax, rax
0x18003766a  mov     rcx, [rcx+rax*8]; Sid
0x18003766e  call    cs:__imp_RtlValidSid
0x180037674  test    al, al
0x180037676  jz      short loc_180037680
0x180037678  inc     edi
0x18003767a  jmp     short loc_180037656
0x18003767c  xor     eax, eax
0x18003767e  jmp     short loc_18003768C
0x180037680  mov     eax, 0C0000078h
0x180037685  jmp     short loc_18003768C
0x180037687  mov     eax, 0C000015Ah
0x18003768c  mov     rbx, [rsp+28h+arg_0]
0x180037691  add     rsp, 20h
0x180037695  pop     rdi
0x180037696  retn
```

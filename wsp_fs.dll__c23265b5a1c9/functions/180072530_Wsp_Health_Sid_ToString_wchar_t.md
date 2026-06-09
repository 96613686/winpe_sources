# Wsp::Health::Sid::ToString(wchar_t * *)

- ea: `0x180072530`
- end: `0x180072587`
- name: `?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z`
- size: `87`
- prototype: `unsigned int(Wsp::Health::Sid *__hidden this, wchar_t **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800721dc`

## callees

- `0x180019198`
- `0x180072530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007256b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007256b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007255b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18007255b`

## pseudocode

```c
DWORD __fastcall Wsp::Health::Sid::ToString(struct _SID **this, wchar_t **a2)
{
  if ( !Wsp::Health::Sid::IsValidSid(this[1]) )
    return 1337;
  if ( ConvertSidToStringSidW(this[1], a2) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x180072530  mov     [rsp+arg_0], rbx
0x180072535  push    rdi
0x180072536  sub     rsp, 20h
0x18007253a  mov     rbx, rcx
0x18007253d  mov     rdi, rdx
0x180072540  mov     rcx, [rcx+8]; struct _SID *
0x180072544  call    ?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z; Wsp::Health::Sid::IsValidSid(_SID const *)
0x180072549  test    al, al
0x18007254b  jnz     short loc_180072554
0x18007254d  mov     eax, 539h
0x180072552  jmp     short loc_18007257B
0x180072554  mov     rcx, [rbx+8]; Sid
0x180072558  mov     rdx, rdi; StringSid
0x18007255b  call    cs:__imp_ConvertSidToStringSidW
0x180072562  nop     dword ptr [rax+rax+00h]
0x180072567  test    eax, eax
0x180072569  jnz     short loc_180072579
0x18007256b  call    cs:__imp_GetLastError
0x180072572  nop     dword ptr [rax+rax+00h]
0x180072577  jmp     short loc_18007257B
0x180072579  xor     eax, eax
0x18007257b  mov     rbx, [rsp+28h+arg_0]
0x180072580  add     rsp, 20h
0x180072584  pop     rdi
0x180072585  retn
```

# Wsp::Health::Sid::IsValidSid(_SID const *)

- ea: `0x180019198`
- end: `0x1800191b3`
- name: `?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z`
- size: `27`
- prototype: `bool __fastcall(const struct _SID *)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800195c0`
- `0x180019740`
- `0x180071150`
- `0x180072530`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001919c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001919c`

## pseudocode

```c
bool __fastcall Wsp::Health::Sid::IsValidSid(struct _SID *a1)
{
  return IsValidSid(a1);
}

```

## disassembly

```asm
0x180019198  sub     rsp, 28h
0x18001919c  call    cs:__imp_IsValidSid
0x1800191a3  nop     dword ptr [rax+rax+00h]
0x1800191a8  test    eax, eax
0x1800191aa  setnz   al
0x1800191ad  add     rsp, 28h
0x1800191b1  retn
```

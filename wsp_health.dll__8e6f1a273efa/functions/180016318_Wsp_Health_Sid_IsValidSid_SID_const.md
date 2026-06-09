# Wsp::Health::Sid::IsValidSid(_SID const *)

- ea: `0x180016318`
- end: `0x180016333`
- name: `?IsValidSid@Sid@Health@Wsp@@SA_NPEBU_SID@@@Z`
- size: `27`
- prototype: `bool __fastcall(const struct _SID *)`
- caller_count: `4`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016450`
- `0x1800165d0`
- `0x18007a770`
- `0x18007bf20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001631c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18001631c`

## pseudocode

```c
bool __fastcall Wsp::Health::Sid::IsValidSid(struct _SID *a1)
{
  return IsValidSid(a1);
}

```

## disassembly

```asm
0x180016318  sub     rsp, 28h
0x18001631c  call    cs:__imp_IsValidSid
0x180016323  nop     dword ptr [rax+rax+00h]
0x180016328  test    eax, eax
0x18001632a  setnz   al
0x18001632d  add     rsp, 28h
0x180016331  retn
```

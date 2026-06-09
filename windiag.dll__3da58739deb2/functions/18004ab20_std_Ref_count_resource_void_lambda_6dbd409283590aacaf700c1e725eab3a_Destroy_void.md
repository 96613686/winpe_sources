# std::_Ref_count_resource<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>::_Destroy(void)

- ea: `0x18004ab20`
- end: `0x18004ab4e`
- name: `?_Destroy@?$_Ref_count_resource@PEAXV_lambda_6dbd409283590aacaf700c1e725eab3a_@@@std@@EEAAXXZ`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004ab43`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004ab43`

## pseudocode

```c
BOOL __fastcall std::_Ref_count_resource<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>::_Destroy(__int64 a1)
{
  return AdjustTokenPrivileges(*(HANDLE *)(a1 + 16), 0, (PTOKEN_PRIVILEGES)(a1 + 24), 0, 0, 0);
}

```

## disassembly

```asm
0x18004ab20  sub     rsp, 38h
0x18004ab24  lea     r8, [rcx+18h]; NewState
0x18004ab28  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x18004ab31  mov     rcx, [rcx+10h]; TokenHandle
0x18004ab35  xor     r9d, r9d; BufferLength
0x18004ab38  xor     edx, edx; DisableAllPrivileges
0x18004ab3a  mov     [rsp+38h+PreviousState], 0; PreviousState
0x18004ab43  call    cs:__imp_AdjustTokenPrivileges
0x18004ab49  add     rsp, 38h
0x18004ab4d  retn
```

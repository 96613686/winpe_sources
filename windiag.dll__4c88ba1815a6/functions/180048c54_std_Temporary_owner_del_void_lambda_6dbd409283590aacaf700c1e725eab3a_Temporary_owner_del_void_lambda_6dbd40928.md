# std::_Temporary_owner_del<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>::~_Temporary_owner_del<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>(void)

- ea: `0x180048c54`
- end: `0x180048c84`
- name: `??1?$_Temporary_owner_del@PEAXV_lambda_6dbd409283590aacaf700c1e725eab3a_@@@std@@QEAA@XZ`
- size: `48`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800973d2`

## callees

- `0x180048c54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180048c79`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180048c79`

## pseudocode

```c
BOOL __fastcall std::_Temporary_owner_del<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>::~_Temporary_owner_del<void *,_lambda_6dbd409283590aacaf700c1e725eab3a_>(
        __int64 a1)
{
  BOOL result; // eax

  result = 0;
  if ( *(_BYTE *)(a1 + 16) )
    return AdjustTokenPrivileges(**(HANDLE **)(a1 + 8), 0, (PTOKEN_PRIVILEGES)(*(_QWORD *)(a1 + 8) + 8LL), 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x180048c54  sub     rsp, 38h
0x180048c58  xor     eax, eax
0x180048c5a  cmp     [rcx+10h], al
0x180048c5d  jz      short loc_180048C7F
0x180048c5f  mov     rcx, [rcx+8]
0x180048c63  xor     r9d, r9d; BufferLength
0x180048c66  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180048c6b  xor     edx, edx; DisableAllPrivileges
0x180048c6d  mov     [rsp+38h+PreviousState], rax; PreviousState
0x180048c72  lea     r8, [rcx+8]; NewState
0x180048c76  mov     rcx, [rcx]; TokenHandle
0x180048c79  call    cs:__imp_AdjustTokenPrivileges
0x180048c7f  add     rsp, 38h
0x180048c83  retn
```

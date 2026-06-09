# CSecDescriptor::AddAce(CSecDescriptor::enumAclType,CSecDescriptor::enumAccessType,ulong,void * const)

- ea: `0x18000d594`
- end: `0x18000d5dd`
- name: `?AddAce@CSecDescriptor@@QEAAXW4enumAclType@1@W4enumAccessType@1@KQEAX@Z`
- size: `73`
- prototype: `BOOL __fastcall(__int64, __int64, __int64, __int64, PSID pSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000af5c`
- `0x180010638`

## callees

- `0x18000d038`
- `0x18000d594`
- `0x18000fdc8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d5c9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000d5bf`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000d5bf`

## pseudocode

```c
BOOL __fastcall CSecDescriptor::AddAce(__int64 a1, __int64 a2, __int64 a3, __int64 a4, PSID pSid)
{
  PACL *v5; // rbx
  BOOL result; // eax
  DWORD LastError; // eax

  v5 = (PACL *)(a1 + 16);
  if ( (*(_BYTE *)(a1 + 28) & 1) == 0 )
    CACL::Initialize((CACL *)(a1 + 16));
  result = AddAccessAllowedAce(*v5, 2u, 0x1F01FFu, pSid);
  if ( !result )
  {
    LastError = GetLastError();
    TrkRaiseWin32Error(LastError);
  }
  return result;
}

```

## disassembly

```asm
0x18000d594  push    rbx
0x18000d596  sub     rsp, 20h
0x18000d59a  lea     rbx, [rcx+10h]
0x18000d59e  test    byte ptr [rbx+0Ch], 1
0x18000d5a2  jnz     short loc_18000D5AC
0x18000d5a4  mov     rcx, rbx; this
0x18000d5a7  call    ?Initialize@CACL@@QEAAXXZ; CACL::Initialize(void)
0x18000d5ac  mov     r9, [rsp+28h+pSid]; pSid
0x18000d5b1  mov     edx, 2; dwAceRevision
0x18000d5b6  mov     rcx, [rbx]; pAcl
0x18000d5b9  mov     r8d, 1F01FFh; AccessMask
0x18000d5bf  call    cs:__imp_AddAccessAllowedAce
0x18000d5c5  test    eax, eax
0x18000d5c7  jnz     short loc_18000D5D7
0x18000d5c9  call    cs:__imp_GetLastError
0x18000d5cf  mov     ecx, eax; int
0x18000d5d1  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000d5d7  add     rsp, 20h
0x18000d5db  pop     rbx
0x18000d5dc  retn
```

# ATL::CSid::Copy(_SID const &)

- ea: `0x140006c10`
- end: `0x140006c79`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void __fastcall(ATL::CSid *this, struct _SID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400097f8`

## callees

- `0x140006c10`
- `0x1400072bc`
- `0x140007468`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140006c23`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140006c23`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140006c30`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140006c30`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140006c48`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140006c48`

## pseudocode

```c
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  signed int Error; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::PrivateAtlThrow(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::PrivateAtlThrow(Error);
  }
}

```

## disassembly

```asm
0x140006c10  mov     [rsp+arg_0], rbx
0x140006c15  push    rdi
0x140006c16  sub     rsp, 20h
0x140006c1a  mov     rdi, rcx
0x140006c1d  mov     rbx, rdx
0x140006c20  mov     rcx, rdx; pSid
0x140006c23  call    cs:__imp_IsValidSid
0x140006c29  test    eax, eax
0x140006c2b  jz      short loc_140006C5D
0x140006c2d  mov     rcx, rbx; pSid
0x140006c30  call    cs:__imp_GetLengthSid
0x140006c36  cmp     eax, 44h ; 'D'
0x140006c39  ja      short loc_140006C5D
0x140006c3b  lea     rdx, [rdi+8]; pDestinationSid
0x140006c3f  mov     byte ptr [rdi+4Ch], 1
0x140006c43  mov     r8, rbx; pSourceSid
0x140006c46  mov     ecx, eax; nDestinationSidLength
0x140006c48  call    cs:__imp_CopySid
0x140006c4e  test    eax, eax
0x140006c50  jz      short loc_140006C68
0x140006c52  mov     rbx, [rsp+28h+arg_0]
0x140006c57  add     rsp, 20h
0x140006c5b  pop     rdi
0x140006c5c  retn
0x140006c5d  mov     ecx, 80070057h; int
0x140006c62  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140006c68  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140006c6d  mov     ecx, eax; int
0x140006c6f  mov     byte ptr [rdi+4Ch], 0
0x140006c73  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```

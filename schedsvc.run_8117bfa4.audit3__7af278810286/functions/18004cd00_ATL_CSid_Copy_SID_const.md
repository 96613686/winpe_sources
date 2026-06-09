# ATL::CSid::Copy(_SID const &)

- ea: `0x18004cd00`
- end: `0x18004cd7c`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `124`
- prototype: `void(ATL::CSid *__hidden this, const struct _SID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002177c`

## callees

- `0x18004cd00`
- `0x1800529a0`
- `0x180055004`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004cd26`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18004cd26`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004cd13`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004cd13`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004cd44`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18004cd44`

## pseudocode

```c
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  unsigned int Error; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::PrivateAtlThrow(0x80070057);
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
0x18004cd00  mov     [rsp+arg_0], rbx
0x18004cd05  push    rdi
0x18004cd06  sub     rsp, 20h
0x18004cd0a  mov     rdi, rcx
0x18004cd0d  mov     rbx, rdx
0x18004cd10  mov     rcx, rdx; pSid
0x18004cd13  call    cs:__imp_IsValidSid
0x18004cd1a  nop     dword ptr [rax+rax+00h]
0x18004cd1f  test    eax, eax
0x18004cd21  jz      short loc_18004CD65
0x18004cd23  mov     rcx, rbx; pSid
0x18004cd26  call    cs:__imp_GetLengthSid
0x18004cd2d  nop     dword ptr [rax+rax+00h]
0x18004cd32  cmp     eax, 44h ; 'D'
0x18004cd35  ja      short loc_18004CD65
0x18004cd37  lea     rdx, [rdi+8]; pDestinationSid
0x18004cd3b  mov     byte ptr [rdi+4Ch], 1
0x18004cd3f  mov     r8, rbx; pSourceSid
0x18004cd42  mov     ecx, eax; nDestinationSidLength
0x18004cd44  call    cs:__imp_CopySid
0x18004cd4b  nop     dword ptr [rax+rax+00h]
0x18004cd50  test    eax, eax
0x18004cd52  jnz     short loc_18004CD70
0x18004cd54  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004cd59  mov     ecx, eax; unsigned int
0x18004cd5b  mov     byte ptr [rdi+4Ch], 0
0x18004cd5f  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004cd65  mov     ecx, 80070057h; unsigned int
0x18004cd6a  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18004cd70  mov     rbx, [rsp+28h+arg_0]
0x18004cd75  add     rsp, 20h
0x18004cd79  pop     rdi
0x18004cd7a  retn
```

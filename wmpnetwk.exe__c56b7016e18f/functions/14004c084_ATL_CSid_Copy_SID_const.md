# ATL::CSid::Copy(_SID const &)

- ea: `0x14004c084`
- end: `0x14004c0ed`
- name: `?Copy@CSid@ATL@@AEAAXAEBU_SID@@@Z`
- size: `105`
- prototype: `void(ATL::CSid *__hidden this, const struct _SID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x140044834`
- `0x140092014`

## callees

- `0x1400396dc`
- `0x14004bb5c`
- `0x14004c084`

## import_xrefs

- `ADVAPI32!CopySid` at `0x14004c0bc`
- `ADVAPI32!CopySid` at `0x14004c0bc`
- `ADVAPI32!GetLengthSid` at `0x14004c0a4`
- `ADVAPI32!GetLengthSid` at `0x14004c0a4`
- `ADVAPI32!IsValidSid` at `0x14004c097`
- `ADVAPI32!IsValidSid` at `0x14004c097`

## pseudocode

```c
void __fastcall ATL::CSid::Copy(ATL::CSid *this, struct _SID *a2)
{
  DWORD LengthSid; // eax
  int Error; // eax

  if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
    ATL::AtlThrowImpl(-2147024809);
  *((_BYTE *)this + 76) = 1;
  if ( !CopySid(LengthSid, (char *)this + 8, a2) )
  {
    Error = ATL::AtlHresultFromLastError();
    *((_BYTE *)this + 76) = 0;
    ATL::AtlThrowImpl(Error);
  }
}

```

## disassembly

```asm
0x14004c084  mov     [rsp+arg_0], rbx
0x14004c089  push    rdi
0x14004c08a  sub     rsp, 20h
0x14004c08e  mov     rdi, rcx
0x14004c091  mov     rbx, rdx
0x14004c094  mov     rcx, rdx; pSid
0x14004c097  call    cs:__imp_IsValidSid
0x14004c09d  test    eax, eax
0x14004c09f  jz      short loc_14004C0D7
0x14004c0a1  mov     rcx, rbx; pSid
0x14004c0a4  call    cs:__imp_GetLengthSid
0x14004c0aa  cmp     eax, 44h ; 'D'
0x14004c0ad  ja      short loc_14004C0D7
0x14004c0af  lea     rdx, [rdi+8]; pDestinationSid
0x14004c0b3  mov     byte ptr [rdi+4Ch], 1
0x14004c0b7  mov     r8, rbx; pSourceSid
0x14004c0ba  mov     ecx, eax; nDestinationSidLength
0x14004c0bc  call    cs:__imp_CopySid
0x14004c0c2  test    eax, eax
0x14004c0c4  jnz     short loc_14004C0E2
0x14004c0c6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14004c0cb  mov     ecx, eax; int
0x14004c0cd  mov     byte ptr [rdi+4Ch], 0
0x14004c0d1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004c0d7  mov     ecx, 80070057h; int
0x14004c0dc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14004c0e2  mov     rbx, [rsp+28h+arg_0]
0x14004c0e7  add     rsp, 20h
0x14004c0eb  pop     rdi
0x14004c0ec  retn
```

# ATL::CSid::LoadAccount(_SID const *,ushort const *)

- ea: `0x180022b44`
- end: `0x180022bd9`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z`
- size: `149`
- prototype: `bool(ATL::CSid *__hidden this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022d44`

## callees

- `0x180022b44`
- `0x180022be0`
- `0x180022dc0`
- `0x180039524`
- `0x18003c1f0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022b74`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180022b74`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022ba3`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180022ba3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022b8b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180022b8b`

## pseudocode

```c
bool __fastcall ATL::CSid::LoadAccount(ATL::CSid *this, struct _SID *a2, const unsigned __int16 *a3)
{
  DWORD LengthSid; // eax
  bool result; // al
  int Error; // eax

  ATL::CSid::Clear(this);
  if ( !a2 )
    return 0;
  try
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString();
    if ( !IsValidSid(a2) )
      ATL::PrivateAtlThrow(-2147024809);
    LengthSid = GetLengthSid(a2);
    if ( LengthSid > 0x44 )
      ATL::PrivateAtlThrow(-2147024809);
    *((_BYTE *)this + 76) = 1;
    if ( !CopySid(LengthSid, (char *)this + 8, a2) )
    {
      Error = ATL::AtlHresultFromLastError();
      *((_BYTE *)this + 76) = 0;
      ATL::PrivateAtlThrow(Error);
    }
    result = 1;
  }
  catch ( ... )
  {
    ATL::CSid::Clear(this);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180022b44  mov     [rsp+arg_8], rbx
0x180022b49  mov     [rsp+arg_0], rcx
0x180022b4e  push    rdi
0x180022b4f  sub     rsp, 20h
0x180022b53  mov     rdi, rdx
0x180022b56  mov     rbx, rcx
0x180022b59  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x180022b5e  test    rdi, rdi
0x180022b61  jz      short loc_180022BD5
0x180022b63  lea     rcx, [rbx+70h]
0x180022b67  xor     r8d, r8d
0x180022b6a  xor     edx, edx
0x180022b6c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180022b71  mov     rcx, rdi; pSid
0x180022b74  call    cs:__imp_IsValidSid
0x180022b7a  test    eax, eax
0x180022b7c  jnz     short loc_180022B88
0x180022b7e  mov     ecx, 80070057h; int
0x180022b83  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180022b88  mov     rcx, rdi; pSid
0x180022b8b  call    cs:__imp_GetLengthSid
0x180022b91  cmp     eax, 44h ; 'D'
0x180022b94  ja      short loc_180022BBA
0x180022b96  mov     byte ptr [rbx+4Ch], 1
0x180022b9a  lea     rdx, [rbx+8]; pDestinationSid
0x180022b9e  mov     r8, rdi; pSourceSid
0x180022ba1  mov     ecx, eax; nDestinationSidLength
0x180022ba3  call    cs:__imp_CopySid
0x180022ba9  test    eax, eax
0x180022bab  jz      short loc_180022BC4
0x180022bad  mov     al, 1
0x180022baf  mov     rbx, [rsp+28h+arg_8]
0x180022bb4  add     rsp, 20h
0x180022bb8  pop     rdi
0x180022bb9  retn
0x180022bba  mov     ecx, 80070057h; int
0x180022bbf  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180022bc4  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180022bc9  mov     byte ptr [rbx+4Ch], 0
0x180022bcd  mov     ecx, eax; int
0x180022bcf  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180022bd5  xor     al, al
0x180022bd7  jmp     short loc_180022BAF
```

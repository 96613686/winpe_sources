# ATL::CSid::LoadAccount(_SID const *,ushort const *)

- ea: `0x1800247b4`
- end: `0x180024860`
- name: `?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z`
- size: `172`
- prototype: `bool(ATL::CSid *__hidden this, const struct _SID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800249e4`

## callees

- `0x1800247b4`
- `0x180024868`
- `0x180024a60`
- `0x18003c664`
- `0x18003f580`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800247e8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800247e8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024823`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180024823`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024805`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180024805`

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
0x1800247b4  mov     [rsp+arg_8], rbx
0x1800247b9  mov     [rsp+arg_0], rcx
0x1800247be  push    rdi
0x1800247bf  sub     rsp, 20h
0x1800247c3  mov     rdi, rdx
0x1800247c6  mov     rbx, rcx
0x1800247c9  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x1800247ce  test    rdi, rdi
0x1800247d1  jz      loc_18002485C
0x1800247d7  lea     rcx, [rbx+70h]
0x1800247db  xor     r8d, r8d
0x1800247de  xor     edx, edx
0x1800247e0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800247e5  mov     rcx, rdi; pSid
0x1800247e8  call    cs:__imp_IsValidSid
0x1800247ef  nop     dword ptr [rax+rax+00h]
0x1800247f4  test    eax, eax
0x1800247f6  jnz     short loc_180024802
0x1800247f8  mov     ecx, 80070057h; int
0x1800247fd  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180024802  mov     rcx, rdi; pSid
0x180024805  call    cs:__imp_GetLengthSid
0x18002480c  nop     dword ptr [rax+rax+00h]
0x180024811  cmp     eax, 44h ; 'D'
0x180024814  ja      short loc_180024841
0x180024816  mov     byte ptr [rbx+4Ch], 1
0x18002481a  lea     rdx, [rbx+8]; pDestinationSid
0x18002481e  mov     r8, rdi; pSourceSid
0x180024821  mov     ecx, eax; nDestinationSidLength
0x180024823  call    cs:__imp_CopySid
0x18002482a  nop     dword ptr [rax+rax+00h]
0x18002482f  test    eax, eax
0x180024831  jz      short loc_18002484B
0x180024833  mov     al, 1
0x180024835  mov     rbx, [rsp+28h+arg_8]
0x18002483a  add     rsp, 20h
0x18002483e  pop     rdi
0x18002483f  retn
0x180024841  mov     ecx, 80070057h; int
0x180024846  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002484b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180024850  mov     byte ptr [rbx+4Ch], 0
0x180024854  mov     ecx, eax; int
0x180024856  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x18002485c  xor     al, al
0x18002485e  jmp     short loc_180024835
```

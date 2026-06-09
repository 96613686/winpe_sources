# ATL::CSid::operator=(_SID const &)

- ea: `0x180028bc4`
- end: `0x180028c7e`
- name: `??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027838`

## callees

- `0x180028bc4`
- `0x180028c84`
- `0x1800504b4`
- `0x1800528ac`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c27`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180028c27`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028c1a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180028c1a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028c3e`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180028c3e`

## pseudocode

```c
__int64 __fastcall ATL::CSid::operator=(__int64 a1, void *a2)
{
  void *v2; // rsi
  DWORD LengthSid; // eax
  unsigned int Error; // eax

  v2 = (void *)(a1 + 8);
  if ( !*(_BYTE *)(a1 + 76) || v2 != a2 )
  {
    *(_DWORD *)(a1 + 80) = 7;
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 88);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 96);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 104);
    ATL::CSimpleStringT<unsigned short,0>::Empty(a1 + 112);
    *(_BYTE *)(a1 + 76) = 0;
    if ( !IsValidSid(a2) || (LengthSid = GetLengthSid(a2), LengthSid > 0x44) )
      ATL::PrivateAtlThrow(0x80070057);
    *(_BYTE *)(a1 + 76) = 1;
    if ( !CopySid(LengthSid, v2, a2) )
    {
      Error = ATL::AtlHresultFromLastError();
      *(_BYTE *)(a1 + 76) = 0;
      ATL::PrivateAtlThrow(Error);
    }
    *(_DWORD *)(a1 + 80) = 8;
  }
  return a1;
}

```

## disassembly

```asm
0x180028bc4  mov     [rsp+arg_0], rbx
0x180028bc9  mov     [rsp+arg_8], rsi
0x180028bce  push    rdi
0x180028bcf  sub     rsp, 20h
0x180028bd3  cmp     byte ptr [rcx+4Ch], 0
0x180028bd7  lea     rsi, [rcx+8]
0x180028bdb  mov     rdi, rdx
0x180028bde  mov     rbx, rcx
0x180028be1  jz      short loc_180028BE8
0x180028be3  cmp     rsi, rdx
0x180028be6  jz      short loc_180028C60
0x180028be8  mov     dword ptr [rcx+50h], 7
0x180028bef  add     rcx, 58h ; 'X'
0x180028bf3  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180028bf8  lea     rcx, [rbx+60h]
0x180028bfc  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180028c01  lea     rcx, [rbx+68h]
0x180028c05  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180028c0a  lea     rcx, [rbx+70h]
0x180028c0e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180028c13  mov     rcx, rdi; pSid
0x180028c16  mov     byte ptr [rbx+4Ch], 0
0x180028c1a  call    cs:__imp_IsValidSid
0x180028c20  test    eax, eax
0x180028c22  jz      short loc_180028C73
0x180028c24  mov     rcx, rdi; pSid
0x180028c27  call    cs:__imp_GetLengthSid
0x180028c2d  cmp     eax, 44h ; 'D'
0x180028c30  ja      short loc_180028C73
0x180028c32  mov     r8, rdi; pSourceSid
0x180028c35  mov     byte ptr [rbx+4Ch], 1
0x180028c39  mov     rdx, rsi; pDestinationSid
0x180028c3c  mov     ecx, eax; nDestinationSidLength
0x180028c3e  call    cs:__imp_CopySid
0x180028c44  test    eax, eax
0x180028c46  jnz     short loc_180028C59
0x180028c48  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180028c4d  mov     ecx, eax; unsigned int
0x180028c4f  mov     byte ptr [rbx+4Ch], 0
0x180028c53  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180028c59  mov     dword ptr [rbx+50h], 8
0x180028c60  mov     rsi, [rsp+28h+arg_8]
0x180028c65  mov     rax, rbx
0x180028c68  mov     rbx, [rsp+28h+arg_0]
0x180028c6d  add     rsp, 20h
0x180028c71  pop     rdi
0x180028c72  retn
0x180028c73  mov     ecx, 80070057h; unsigned int
0x180028c78  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```

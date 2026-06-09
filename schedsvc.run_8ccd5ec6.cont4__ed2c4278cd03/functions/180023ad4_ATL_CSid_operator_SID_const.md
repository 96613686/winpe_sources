# ATL::CSid::operator=(_SID const &)

- ea: `0x180023ad4`
- end: `0x180023b77`
- name: `??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021844`

## callees

- `0x180023ad4`
- `0x180023b80`
- `0x1800529a0`
- `0x180055004`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023b13`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180023b13`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023b00`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180023b00`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023b30`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180023b30`

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
    ATL::CSid::Clear((ATL::CSid *)a1);
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
0x180023ad4  mov     [rsp+arg_0], rbx
0x180023ad9  mov     [rsp+arg_8], rsi
0x180023ade  push    rdi
0x180023adf  sub     rsp, 20h
0x180023ae3  cmp     byte ptr [rcx+4Ch], 0
0x180023ae7  lea     rsi, [rcx+8]
0x180023aeb  mov     rdi, rdx
0x180023aee  mov     rbx, rcx
0x180023af1  jz      short loc_180023AF8
0x180023af3  cmp     rsi, rdx
0x180023af6  jz      short loc_180023B58
0x180023af8  call    ?Clear@CSid@ATL@@AEAAXXZ; ATL::CSid::Clear(void)
0x180023afd  mov     rcx, rdi; pSid
0x180023b00  call    cs:__imp_IsValidSid
0x180023b07  nop     dword ptr [rax+rax+00h]
0x180023b0c  test    eax, eax
0x180023b0e  jz      short loc_180023B6C
0x180023b10  mov     rcx, rdi; pSid
0x180023b13  call    cs:__imp_GetLengthSid
0x180023b1a  nop     dword ptr [rax+rax+00h]
0x180023b1f  cmp     eax, 44h ; 'D'
0x180023b22  ja      short loc_180023B6C
0x180023b24  mov     r8, rdi; pSourceSid
0x180023b27  mov     byte ptr [rbx+4Ch], 1
0x180023b2b  mov     rdx, rsi; pDestinationSid
0x180023b2e  mov     ecx, eax; nDestinationSidLength
0x180023b30  call    cs:__imp_CopySid
0x180023b37  nop     dword ptr [rax+rax+00h]
0x180023b3c  test    eax, eax
0x180023b3e  jnz     short loc_180023B51
0x180023b40  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180023b45  mov     ecx, eax; unsigned int
0x180023b47  mov     byte ptr [rbx+4Ch], 0
0x180023b4b  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x180023b51  mov     dword ptr [rbx+50h], 8
0x180023b58  mov     rsi, [rsp+28h+arg_8]
0x180023b5d  mov     rax, rbx
0x180023b60  mov     rbx, [rsp+28h+arg_0]
0x180023b65  add     rsp, 20h
0x180023b69  pop     rdi
0x180023b6a  retn
0x180023b6c  mov     ecx, 80070057h; unsigned int
0x180023b71  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
```

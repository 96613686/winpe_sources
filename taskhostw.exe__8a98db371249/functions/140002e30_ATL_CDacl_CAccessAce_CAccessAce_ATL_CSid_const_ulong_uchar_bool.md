# ATL::CDacl::CAccessAce::CAccessAce(ATL::CSid const &,ulong,uchar,bool)

- ea: `0x140002e30`
- end: `0x140002f45`
- name: `??0CAccessAce@CDacl@ATL@@QEAA@AEBVCSid@2@KE_N@Z`
- size: `277`
- prototype: `ATL::CDacl::CAccessAce *__fastcall(ATL::CDacl::CAccessAce *this, const struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002b40`

## callees

- `0x140002e30`
- `0x140002f50`
- `0x140002ff0`
- `0x140003030`
- `0x1400072bc`
- `0x140007468`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ede`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140002ede`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002eee`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140002eee`

## pseudocode

```c
ATL::CDacl::CAccessAce *__fastcall ATL::CDacl::CAccessAce::CAccessAce(
        ATL::CDacl::CAccessAce *this,
        const struct ATL::CSid *a2)
{
  _QWORD *v4; // rsi
  DWORD LengthSid; // eax
  int Error; // eax

  *(_QWORD *)this = &ATL::CAcl::CAce::`vftable';
  v4 = (_QWORD *)((char *)this + 8);
  *((_QWORD *)this + 1) = &ATL::CSid::`vftable';
  *((_BYTE *)this + 84) = *((_BYTE *)a2 + 76);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 20);
  *((_QWORD *)this + 12) = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 11) - 24LL) + 24;
  v4[12] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 12) - 24LL) + 24;
  v4[13] = ATL::CSimpleStringT<unsigned short,0>::CloneData(*((_QWORD *)a2 + 13) - 24LL) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v4 + 14);
  if ( *((_BYTE *)a2 + 76) )
  {
    if ( !ATL::CSid::IsValid(a2) )
      ATL::PrivateAtlThrow(-2147024809);
    LengthSid = GetLengthSid((char *)a2 + 8);
    if ( !CopySid(LengthSid, v4 + 1, (char *)a2 + 8) )
    {
      Error = ATL::AtlHresultFromLastError();
      ATL::PrivateAtlThrow(Error);
    }
  }
  *((_DWORD *)this + 32) = 33619967;
  *((_BYTE *)this + 132) = 0;
  *((_QWORD *)this + 17) = 0;
  *(_QWORD *)this = &ATL::CDacl::CAccessAce::`vftable';
  *((_BYTE *)this + 144) = 1;
  return this;
}

```

## disassembly

```asm
0x140002e30  mov     [rsp+arg_8], rbx
0x140002e35  mov     [rsp+arg_10], rsi
0x140002e3a  mov     [rsp+arg_0], rcx
0x140002e3f  push    rdi
0x140002e40  sub     rsp, 20h
0x140002e44  mov     rdi, rdx
0x140002e47  mov     rbx, rcx
0x140002e4a  lea     rax, ??_7CAce@CAcl@ATL@@6B@; const ATL::CAcl::CAce::`vftable'
0x140002e51  mov     [rcx], rax
0x140002e54  lea     rsi, [rcx+8]
0x140002e58  mov     [rsp+28h+arg_0], rsi
0x140002e5d  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140002e64  mov     [rsi], rax
0x140002e67  movzx   eax, byte ptr [rdx+4Ch]
0x140002e6b  mov     [rsi+4Ch], al
0x140002e6e  mov     eax, [rdx+50h]
0x140002e71  mov     [rsi+50h], eax
0x140002e74  mov     rcx, [rdx+58h]
0x140002e78  sub     rcx, 18h
0x140002e7c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140002e81  add     rax, 18h
0x140002e85  mov     [rsi+58h], rax
0x140002e89  mov     rcx, [rdi+60h]
0x140002e8d  sub     rcx, 18h
0x140002e91  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140002e96  add     rax, 18h
0x140002e9a  mov     [rsi+60h], rax
0x140002e9e  mov     rcx, [rdi+68h]
0x140002ea2  sub     rcx, 18h
0x140002ea6  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x140002eab  add     rax, 18h
0x140002eaf  mov     [rsi+68h], rax
0x140002eb3  lea     rcx, [rsi+70h]
0x140002eb7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x140002ebc  nop
0x140002ebd  cmp     byte ptr [rdi+4Ch], 0
0x140002ec1  jz      short loc_140002F05
0x140002ec3  mov     rcx, rdi; this
0x140002ec6  call    ?IsValid@CSid@ATL@@QEBA_NXZ; ATL::CSid::IsValid(void)
0x140002ecb  test    al, al
0x140002ecd  jnz     short loc_140002EDA
0x140002ecf  mov     ecx, 80070057h; int
0x140002ed4  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002eda  lea     rcx, [rdi+8]; pSid
0x140002ede  call    cs:__imp_GetLengthSid
0x140002ee4  lea     rdx, [rsi+8]; pDestinationSid
0x140002ee8  lea     r8, [rdi+8]; pSourceSid
0x140002eec  mov     ecx, eax; nDestinationSidLength
0x140002eee  call    cs:__imp_CopySid
0x140002ef4  test    eax, eax
0x140002ef6  jnz     short loc_140002F05
0x140002ef8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140002efd  mov     ecx, eax; int
0x140002eff  call    ?PrivateAtlThrow@ATL@@YAXJ@Z; ATL::PrivateAtlThrow(long)
0x140002f05  mov     dword ptr [rbx+80h], 200FFFFh
0x140002f0f  mov     byte ptr [rbx+84h], 0
0x140002f16  mov     qword ptr [rbx+88h], 0
0x140002f21  lea     rax, ??_7CAccessAce@CDacl@ATL@@6B@; const ATL::CDacl::CAccessAce::`vftable'
0x140002f28  mov     [rbx], rax
0x140002f2b  mov     byte ptr [rbx+90h], 1
0x140002f32  mov     rax, rbx
0x140002f35  mov     rbx, [rsp+28h+arg_8]
0x140002f3a  mov     rsi, [rsp+28h+arg_10]
0x140002f3f  add     rsp, 20h
0x140002f43  pop     rdi
0x140002f44  retn
```

# ClusterADObject::GetObjectSid(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18009774c`
- end: `0x1800977f2`
- name: `?GetObjectSid@ClusterADObject@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `166`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800977f8`
- `0x180097a40`

## callees

- `0x18001072c`
- `0x180031428`
- `0x18009774c`
- `0x180098888`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800977a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009779b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009779b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ClusterADObject::GetObjectSid(__int64 a1, __int64 a2, const wchar_t *a3)
{
  int BinaryAttribute; // ebx
  signed int LastError; // eax
  LPWSTR v6; // rbx
  LPWSTR v8; // [rsp+40h] [rbp+8h] BYREF
  PSID Sid; // [rsp+50h] [rbp+18h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp+20h] BYREF

  Sid = 0;
  BinaryAttribute = CLdapWrapper::GetBinaryAttribute(
                      *(LDAP ***)(a1 + 256),
                      *(LDAPMessage ***)(a1 + 264),
                      a3,
                      (unsigned __int8 **)&Sid,
                      (unsigned int *)&v8);
  if ( BinaryAttribute >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v6 = StringSid;
      v8 = StringSid;
      std::wstring::assign(a2);
      CTSmartPtr_PolicyLocalMem::DestroyMem(v6);
      BinaryAttribute = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      BinaryAttribute = LastError;
    }
  }
  CTSmartPtr_PolicyLocalMem::DestroyMem(Sid);
  return (unsigned int)BinaryAttribute;
}

```

## disassembly

```asm
0x18009774c  mov     r11, rsp
0x18009774f  mov     [r11+10h], rbx
0x180097753  push    rdi
0x180097754  sub     rsp, 30h
0x180097758  mov     rdi, rdx
0x18009775b  mov     qword ptr [r11+18h], 0
0x180097763  lea     rax, [r11+8]
0x180097767  mov     [r11-18h], rax
0x18009776b  lea     r9, [r11+18h]; unsigned __int8 **
0x18009776f  mov     rdx, [rcx+108h]; struct CLdapSearchResult *
0x180097776  mov     rcx, [rcx+100h]; this
0x18009777d  call    ?GetBinaryAttribute@CLdapWrapper@@QEAAJPEAVCLdapSearchResult@@PEB_WPEAPEAEPEAK@Z; CLdapWrapper::GetBinaryAttribute(CLdapSearchResult *,wchar_t const *,uchar * *,ulong *)
0x180097782  mov     ebx, eax
0x180097784  test    eax, eax
0x180097786  js      short loc_1800977DB
0x180097788  mov     [rsp+38h+StringSid], 0
0x180097791  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180097796  mov     rcx, [rsp+38h+Sid]; Sid
0x18009779b  call    cs:__imp_ConvertSidToStringSidW
0x1800977a1  test    eax, eax
0x1800977a3  jnz     short loc_1800977BB
0x1800977a5  call    cs:__imp_GetLastError
0x1800977ab  test    eax, eax
0x1800977ad  jle     short loc_1800977B7
0x1800977af  movzx   eax, ax
0x1800977b2  or      eax, 80070000h
0x1800977b7  mov     ebx, eax
0x1800977b9  jmp     short loc_1800977DB
0x1800977bb  mov     rbx, [rsp+38h+StringSid]
0x1800977c0  mov     [rsp+38h+arg_0], rbx
0x1800977c5  mov     rdx, rbx
0x1800977c8  mov     rcx, rdi
0x1800977cb  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x1800977d0  nop
0x1800977d1  mov     rcx, rbx; void *
0x1800977d4  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800977d9  xor     ebx, ebx
0x1800977db  mov     rcx, [rsp+38h+Sid]; void *
0x1800977e0  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x1800977e5  mov     eax, ebx
0x1800977e7  mov     rbx, [rsp+38h+arg_8]
0x1800977ec  add     rsp, 30h
0x1800977f0  pop     rdi
0x1800977f1  retn
```

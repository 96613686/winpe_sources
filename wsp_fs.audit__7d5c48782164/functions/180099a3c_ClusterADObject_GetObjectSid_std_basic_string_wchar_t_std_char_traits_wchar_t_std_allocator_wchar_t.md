# ClusterADObject::GetObjectSid(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180099a3c`
- end: `0x180099aef`
- name: `?GetObjectSid@ClusterADObject@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180099af8`
- `0x180099d70`

## callees

- `0x180010b90`
- `0x18003245c`
- `0x180099a3c`
- `0x18009ac54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099a9b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180099a8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180099a8b`

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
                      *(CLdapWrapper **)(a1 + 256),
                      *(struct CLdapSearchResult **)(a1 + 264),
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
      std::wstring::assign(a2, StringSid);
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
0x180099a3c  mov     r11, rsp
0x180099a3f  mov     [r11+10h], rbx
0x180099a43  push    rdi
0x180099a44  sub     rsp, 30h
0x180099a48  mov     rdi, rdx
0x180099a4b  mov     qword ptr [r11+18h], 0
0x180099a53  lea     rax, [r11+8]
0x180099a57  mov     [r11-18h], rax
0x180099a5b  lea     r9, [r11+18h]; unsigned __int8 **
0x180099a5f  mov     rdx, [rcx+108h]; struct CLdapSearchResult *
0x180099a66  mov     rcx, [rcx+100h]; this
0x180099a6d  call    ?GetBinaryAttribute@CLdapWrapper@@QEAAJPEAVCLdapSearchResult@@PEB_WPEAPEAEPEAK@Z; CLdapWrapper::GetBinaryAttribute(CLdapSearchResult *,wchar_t const *,uchar * *,ulong *)
0x180099a72  mov     ebx, eax
0x180099a74  test    eax, eax
0x180099a76  js      short loc_180099AD7
0x180099a78  mov     [rsp+38h+StringSid], 0
0x180099a81  lea     rdx, [rsp+38h+StringSid]; StringSid
0x180099a86  mov     rcx, [rsp+38h+Sid]; Sid
0x180099a8b  call    cs:__imp_ConvertSidToStringSidW
0x180099a92  nop     dword ptr [rax+rax+00h]
0x180099a97  test    eax, eax
0x180099a99  jnz     short loc_180099AB7
0x180099a9b  call    cs:__imp_GetLastError
0x180099aa2  nop     dword ptr [rax+rax+00h]
0x180099aa7  test    eax, eax
0x180099aa9  jle     short loc_180099AB3
0x180099aab  movzx   eax, ax
0x180099aae  or      eax, 80070000h
0x180099ab3  mov     ebx, eax
0x180099ab5  jmp     short loc_180099AD7
0x180099ab7  mov     rbx, [rsp+38h+StringSid]
0x180099abc  mov     [rsp+38h+arg_0], rbx
0x180099ac1  mov     rdx, rbx
0x180099ac4  mov     rcx, rdi
0x180099ac7  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180099acc  nop
0x180099acd  mov     rcx, rbx; void *
0x180099ad0  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x180099ad5  xor     ebx, ebx
0x180099ad7  mov     rcx, [rsp+38h+Sid]; void *
0x180099adc  call    ?DestroyMem@CTSmartPtr_PolicyLocalMem@@SAHPEAX@Z; CTSmartPtr_PolicyLocalMem::DestroyMem(void *)
0x180099ae1  mov     eax, ebx
0x180099ae3  mov     rbx, [rsp+38h+arg_8]
0x180099ae8  add     rsp, 30h
0x180099aec  pop     rdi
0x180099aed  retn
```

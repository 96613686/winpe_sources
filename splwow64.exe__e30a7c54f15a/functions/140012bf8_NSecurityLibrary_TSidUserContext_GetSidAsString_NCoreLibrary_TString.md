# NSecurityLibrary::TSidUserContext::GetSidAsString(NCoreLibrary::TString &)

- ea: `0x140012bf8`
- end: `0x140012c78`
- name: `?GetSidAsString@TSidUserContext@NSecurityLibrary@@QEBAJAEAVTString@NCoreLibrary@@@Z`
- size: `128`
- prototype: `int(NSecurityLibrary::TSidUserContext *__hidden this, struct NCoreLibrary::TString *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000805c`
- `0x14000fae0`

## callees

- `0x140012bd4`
- `0x140012bf8`
- `0x140012d4c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140012c65`
- `KERNEL32!LocalFree` at `0x140012c65`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140012c37`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140012c37`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::TSidUserContext::GetSidAsString(
        NSecurityLibrary::TSidUserContext *this,
        struct NCoreLibrary::TString *a2)
{
  int LastErrorAsHResult; // ebx
  PSID *v4; // rcx
  NCoreLibrary *v5; // rcx
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF

  LastErrorAsHResult = *((_DWORD *)this + 14);
  if ( LastErrorAsHResult >= 0 )
  {
    if ( *(__int16 **)a2 == word_14002174A )
    {
      return (unsigned int)-2147024882;
    }
    else
    {
      v4 = (PSID *)*((_QWORD *)this + 6);
      StringSid = 0;
      if ( ConvertSidToStringSidW(*v4, &StringSid)
        || (LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v5), LastErrorAsHResult >= 0) )
      {
        LastErrorAsHResult = NCoreLibrary::TString::Update(a2, StringSid);
      }
      if ( StringSid )
        LocalFree(StringSid);
    }
  }
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140012bf8  mov     [rsp+arg_8], rbx
0x140012bfd  push    rdi
0x140012bfe  sub     rsp, 20h
0x140012c02  mov     ebx, [rcx+38h]
0x140012c05  mov     rdi, rdx
0x140012c08  test    ebx, ebx
0x140012c0a  js      short loc_140012C6B
0x140012c0c  xor     ebx, ebx
0x140012c0e  lea     rdx, word_14002174A
0x140012c15  cmp     [rdi], rdx
0x140012c18  mov     eax, 8007000Eh
0x140012c1d  cmovz   ebx, eax
0x140012c20  jz      short loc_140012C6B
0x140012c22  mov     rcx, [rcx+30h]
0x140012c26  lea     rdx, [rsp+28h+StringSid]; StringSid
0x140012c2b  mov     [rsp+28h+StringSid], 0
0x140012c34  mov     rcx, [rcx]; Sid
0x140012c37  call    cs:__imp_ConvertSidToStringSidW
0x140012c3d  test    eax, eax
0x140012c3f  jnz     short loc_140012C4C
0x140012c41  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140012c46  mov     ebx, eax
0x140012c48  test    eax, eax
0x140012c4a  js      short loc_140012C5B
0x140012c4c  mov     rdx, [rsp+28h+StringSid]; unsigned __int16 *
0x140012c51  mov     rcx, rdi; this
0x140012c54  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x140012c59  mov     ebx, eax
0x140012c5b  mov     rcx, [rsp+28h+StringSid]; hMem
0x140012c60  test    rcx, rcx
0x140012c63  jz      short loc_140012C6B
0x140012c65  call    cs:__imp_LocalFree
0x140012c6b  mov     eax, ebx
0x140012c6d  mov     rbx, [rsp+28h+arg_8]
0x140012c72  add     rsp, 20h
0x140012c76  pop     rdi
0x140012c77  retn
```

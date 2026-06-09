# ATL::CSid::Sid(void)

- ea: `0x18004ab30`
- end: `0x18004ab85`
- name: `?Sid@CSid@ATL@@QEBAPEBGXZ`
- size: `85`
- prototype: `const unsigned __int16 *__fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f730`

## callees

- `0x1800233e4`
- `0x18004ab30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ab75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004ab75`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ab59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004ab59`

## pseudocode

```c
const unsigned __int16 *__fastcall ATL::CSid::Sid(ATL::CSid *this)
{
  char *v1; // rbx
  LPWSTR StringSid; // [rsp+38h] [rbp+10h] BYREF

  v1 = (char *)this + 104;
  if ( !*(_DWORD *)(*((_QWORD *)this + 13) - 16LL) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW((char *)this + 8, &StringSid) )
    {
      try
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v1, StringSid);
        LocalFree(StringSid);
      }
      catch ( ... )
      {
        ATL::CSimpleStringT<unsigned short,0>::Empty((char *)this + 104);
        throw;
      }
    }
  }
  return *(const unsigned __int16 **)v1;
}

```

## disassembly

```asm
0x18004ab30  mov     [rsp+arg_0], rcx
0x18004ab35  push    rbx
0x18004ab36  sub     rsp, 20h
0x18004ab3a  lea     rbx, [rcx+68h]
0x18004ab3e  mov     rax, [rbx]
0x18004ab41  cmp     dword ptr [rax-10h], 0
0x18004ab45  jnz     short loc_18004AB7B
0x18004ab47  mov     [rsp+28h+StringSid], 0
0x18004ab50  add     rcx, 8; Sid
0x18004ab54  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18004ab59  call    cs:__imp_ConvertSidToStringSidW
0x18004ab5f  test    eax, eax
0x18004ab61  jz      short loc_18004AB7B
0x18004ab63  mov     rdx, [rsp+28h+StringSid]
0x18004ab68  mov     rcx, rbx
0x18004ab6b  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004ab70  mov     rcx, [rsp+28h+StringSid]; hMem
0x18004ab75  call    cs:__imp_LocalFree
0x18004ab7b  mov     rax, [rbx]
0x18004ab7e  add     rsp, 20h
0x18004ab82  pop     rbx
0x18004ab83  retn
```

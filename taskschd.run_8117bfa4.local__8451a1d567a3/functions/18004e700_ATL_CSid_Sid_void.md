# ATL::CSid::Sid(void)

- ea: `0x18004e700`
- end: `0x18004e761`
- name: `?Sid@CSid@ATL@@QEBAPEBGXZ`
- size: `97`
- prototype: `const unsigned __int16 *__fastcall(ATL::CSid *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fa5c`

## callees

- `0x180025100`
- `0x18004e700`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e74b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e74b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e729`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004e729`

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
0x18004e700  mov     [rsp+arg_0], rcx
0x18004e705  push    rbx
0x18004e706  sub     rsp, 20h
0x18004e70a  lea     rbx, [rcx+68h]
0x18004e70e  mov     rax, [rbx]
0x18004e711  cmp     dword ptr [rax-10h], 0
0x18004e715  jnz     short loc_18004E757
0x18004e717  mov     [rsp+28h+StringSid], 0
0x18004e720  add     rcx, 8; Sid
0x18004e724  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18004e729  call    cs:__imp_ConvertSidToStringSidW
0x18004e730  nop     dword ptr [rax+rax+00h]
0x18004e735  test    eax, eax
0x18004e737  jz      short loc_18004E757
0x18004e739  mov     rdx, [rsp+28h+StringSid]
0x18004e73e  mov     rcx, rbx
0x18004e741  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18004e746  mov     rcx, [rsp+28h+StringSid]; hMem
0x18004e74b  call    cs:__imp_LocalFree
0x18004e752  nop     dword ptr [rax+rax+00h]
0x18004e757  mov     rax, [rbx]
0x18004e75a  add     rsp, 20h
0x18004e75e  pop     rbx
0x18004e75f  retn
```

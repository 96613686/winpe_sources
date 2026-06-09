# CHANNEL_LIST::ValidateEntry(CHANNEL_ENTRY *,ETW_PROVIDER_ENTRY &,bool)

- ea: `0x18001b378`
- end: `0x18001b4b3`
- name: `?ValidateEntry@CHANNEL_LIST@@AEAAXPEAVCHANNEL_ENTRY@@AEAVETW_PROVIDER_ENTRY@@_N@Z`
- size: `315`
- prototype: `void __fastcall(CHANNEL_LIST *this, struct CHANNEL_ENTRY *, struct ETW_PROVIDER_ENTRY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018eb8`

## callees

- `0x180019354`
- `0x18001a594`
- `0x18001b340`
- `0x18001b378`
- `0x18001e09c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b460`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001b460`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b451`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001b451`

## pseudocode

```c
void __fastcall CHANNEL_LIST::ValidateEntry(
        CHANNEL_LIST *this,
        struct CHANNEL_ENTRY *a2,
        struct ETW_PROVIDER_ENTRY *a3)
{
  struct CHANNEL_ENTRY *v3; // rbx
  __int64 v5; // rdx
  char *v7; // rcx
  const WCHAR **v8; // rdi
  const WCHAR *v9; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-18h] BYREF

  v3 = a2;
  v5 = *((unsigned __int16 *)a2 + 52);
  if ( (unsigned int)v5 <= 0xF || (unsigned __int16)(v5 - 256) <= 0xFEFEu )
  {
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(struct CHANNEL_ENTRY **)v3;
    ThrowWithFormatMessage(-1073221865, v5, v3);
  }
  v7 = (char *)v3 + 64;
  if ( !*((_QWORD *)v3 + 10) )
    std::wstring::operator=(v7, v3);
  CHANNEL_LIST::ValidateChannelName(v7, v3);
  if ( *((_QWORD *)v3 + 17) )
  {
    STRING_LIST::AddRef(
      *(_QWORD *)this,
      (_QWORD *)v3 + 15,
      4u,
      *((unsigned __int16 *)v3 + 52),
      (__int64)L"channel",
      0,
      (__int64)a3,
      (_QWORD *)v3 + 23);
    *((_BYTE *)a3 + 278) = 1;
  }
  if ( *((_QWORD *)v3 + 21) )
  {
    v8 = (const WCHAR **)((char *)v3 + 152);
    SecurityDescriptor = 0;
    if ( *((_QWORD *)v3 + 22) <= 7u )
      v9 = (const WCHAR *)((char *)v3 + 152);
    else
      v9 = *v8;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, &SecurityDescriptor, 0) )
    {
      if ( *((_QWORD *)v3 + 22) > 7u )
        v8 = (const WCHAR **)*v8;
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(struct CHANNEL_ENTRY **)v3;
      ThrowWithFormatMessage(-1073221804, v3, v8);
    }
    LocalFree(SecurityDescriptor);
  }
}

```

## disassembly

```asm
0x18001b378  mov     [rsp+arg_0], rbx
0x18001b37d  mov     [rsp+arg_8], rsi
0x18001b382  push    rdi
0x18001b383  sub     rsp, 50h
0x18001b387  mov     rbx, rdx
0x18001b38a  mov     rdi, r8
0x18001b38d  movzx   edx, word ptr [rdx+68h]
0x18001b391  mov     rsi, rcx
0x18001b394  cmp     edx, 0Fh
0x18001b397  jbe     loc_18001B49B
0x18001b39d  mov     ecx, 100h
0x18001b3a2  movzx   eax, dx
0x18001b3a5  sub     ax, cx
0x18001b3a8  mov     ecx, 0FEFEh
0x18001b3ad  cmp     ax, cx
0x18001b3b0  jbe     loc_18001B49B
0x18001b3b6  lea     rcx, [rbx+40h]
0x18001b3ba  cmp     qword ptr [rcx+10h], 0
0x18001b3bf  jnz     short loc_18001B3C9
0x18001b3c1  mov     rdx, rbx
0x18001b3c4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001b3c9  mov     rdx, rbx
0x18001b3cc  call    ?ValidateChannelName@CHANNEL_LIST@@AEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; CHANNEL_LIST::ValidateChannelName(std::wstring const &)
0x18001b3d1  lea     rdx, [rbx+78h]
0x18001b3d5  cmp     qword ptr [rdx+10h], 0
0x18001b3da  jz      short loc_18001B41C
0x18001b3dc  movzx   r9d, word ptr [rbx+68h]
0x18001b3e1  lea     rax, [rbx+0B8h]
0x18001b3e8  mov     rcx, [rsi]
0x18001b3eb  mov     r8d, 4
0x18001b3f1  mov     [rsp+58h+var_20], rax
0x18001b3f6  lea     rax, aChannel; "channel"
0x18001b3fd  mov     [rsp+58h+var_28], rdi
0x18001b402  mov     [rsp+58h+var_30], 0
0x18001b40b  mov     [rsp+58h+var_38], rax
0x18001b410  call    ?AddRef@STRING_LIST@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4TableType@@_KPEB_WPEAKAEAVETW_PROVIDER_ENTRY@@PEAPEAVSTRING_ENTRY@@@Z; STRING_LIST::AddRef(std::wstring const &,TableType,unsigned __int64,wchar_t const *,ulong *,ETW_PROVIDER_ENTRY &,STRING_ENTRY * *)
0x18001b415  mov     byte ptr [rdi+116h], 1
0x18001b41c  cmp     qword ptr [rbx+0A8h], 0
0x18001b424  jz      short loc_18001B466
0x18001b426  lea     rdi, [rbx+98h]
0x18001b42d  mov     [rsp+58h+SecurityDescriptor], 0
0x18001b436  cmp     qword ptr [rdi+18h], 7
0x18001b43b  jbe     short loc_18001B442
0x18001b43d  mov     rcx, [rdi]
0x18001b440  jmp     short loc_18001B445
0x18001b442  mov     rcx, rdi; StringSecurityDescriptor
0x18001b445  xor     r9d, r9d; SecurityDescriptorSize
0x18001b448  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x18001b44d  lea     edx, [r9+1]; StringSDRevision
0x18001b451  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001b457  test    eax, eax
0x18001b459  jz      short loc_18001B476
0x18001b45b  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x18001b460  call    cs:__imp_LocalFree
0x18001b466  mov     rbx, [rsp+58h+arg_0]
0x18001b46b  mov     rsi, [rsp+58h+arg_8]
0x18001b470  add     rsp, 50h
0x18001b474  pop     rdi
0x18001b475  retn
0x18001b476  cmp     qword ptr [rdi+18h], 7
0x18001b47b  jbe     short loc_18001B480
0x18001b47d  mov     rdi, [rdi]
0x18001b480  cmp     qword ptr [rbx+18h], 7
0x18001b485  jbe     short loc_18001B48A
0x18001b487  mov     rbx, [rbx]
0x18001b48a  mov     r8, rdi
0x18001b48d  mov     rdx, rbx
0x18001b490  mov     ecx, 0C007EF54h; int
0x18001b495  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
0x18001b49b  cmp     qword ptr [rbx+18h], 7
0x18001b4a0  jbe     short loc_18001B4A5
0x18001b4a2  mov     rbx, [rbx]
0x18001b4a5  mov     r8, rbx
0x18001b4a8  mov     ecx, 0C007EF17h; int
0x18001b4ad  call    ?ThrowWithFormatMessage@@YAXJZZ; ThrowWithFormatMessage(long,...)
```

# Capability::SidString(void)

- ea: `0x18001a590`
- end: `0x18001a6d0`
- name: `?SidString@Capability@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `320`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001a2a8`

## callees

- `0x18000e110`
- `0x180011a78`
- `0x180013cfc`
- `0x180016a88`
- `0x1800192a8`
- `0x180019ec8`
- `0x18001a590`
- `0x180048290`
- `0x18004fa50`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18001a626`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001a626`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18001a63c`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18001a63c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a686`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a686`

## pseudocode

```c
__int64 __fastcall Capability::SidString(const WCHAR *SourceString, __int64 a2)
{
  PCWSTR v3; // rdi
  __int64 v4; // rdx
  bool v5; // cf
  LPWSTR v6; // rdi
  __int64 v7; // r8
  LPWSTR StringSid; // [rsp+20h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-51h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v12; // [rsp+48h] [rbp-31h]
  _BYTE Sid[48]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v14[48]; // [rsp+88h] [rbp+Fh] BYREF

  v3 = SourceString;
  if ( !*((_QWORD *)SourceString + 6) )
  {
    if ( !*((_QWORD *)SourceString + 2) )
    {
      std::wstring::wstring(a2, &Options);
      return a2;
    }
    DeviceCapabilitySids::Lookup(v11, SourceString);
    if ( !v12 )
    {
      v5 = *((_QWORD *)v3 + 3) < 8u;
      DestinationString = 0;
      if ( !v5 )
        v3 = *(PCWSTR *)v3;
      if ( RtlInitUnicodeStringEx(&DestinationString, v3) < 0
        || (int)RtlDeriveCapabilitySidsFromName(&DestinationString, v14, Sid) < 0
        || (StringSid = 0, !ConvertSidToStringSidW(Sid, &StringSid)) )
      {
        std::wstring::wstring(a2, &Options);
        goto LABEL_18;
      }
      v6 = StringSid;
      if ( *StringSid )
      {
        v7 = -1;
        do
          ++v7;
        while ( StringSid[v7] );
      }
      else
      {
        v7 = 0;
      }
      std::wstring::assign(v11, StringSid, v7);
      LocalFree(v6);
    }
    std::wstring::wstring(a2, v11);
LABEL_18:
    LOBYTE(v4) = 1;
    std::wstring::_Tidy(v11, v4, 0);
    return a2;
  }
  std::wstring::wstring(a2);
  return a2;
}

```

## disassembly

```asm
0x18001a590  mov     [rsp-8+arg_10], rbx
0x18001a595  push    rbp
0x18001a596  push    rsi
0x18001a597  push    rdi
0x18001a598  lea     rbp, [rsp-47h]
0x18001a59d  sub     rsp, 0C0h
0x18001a5a4  mov     rax, cs:__security_cookie
0x18001a5ab  xor     rax, rsp
0x18001a5ae  mov     [rbp+57h+var_18], rax
0x18001a5b2  mov     rbx, rdx
0x18001a5b5  xor     esi, esi
0x18001a5b7  lea     rdx, [rcx+20h]
0x18001a5bb  mov     rdi, rcx
0x18001a5be  cmp     [rdx+10h], rsi
0x18001a5c2  jbe     short loc_18001A5D1
0x18001a5c4  mov     rcx, rbx
0x18001a5c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001a5cc  jmp     loc_18001A6AE
0x18001a5d1  cmp     [rcx+10h], rsi
0x18001a5d5  jnz     short loc_18001A5EB
0x18001a5d7  lea     rdx, Options
0x18001a5de  mov     rcx, rbx
0x18001a5e1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001a5e6  jmp     loc_18001A6AE
0x18001a5eb  mov     rdx, rdi
0x18001a5ee  lea     rcx, [rbp+57h+var_98]
0x18001a5f2  call    ?Lookup@DeviceCapabilitySids@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; DeviceCapabilitySids::Lookup(std::wstring const &)
0x18001a5f7  cmp     [rbp+57h+var_88], rsi
0x18001a5fb  jbe     short loc_18001A60E
0x18001a5fd  lea     rdx, [rbp+57h+var_98]
0x18001a601  mov     rcx, rbx
0x18001a604  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001a609  jmp     loc_18001A6A0
0x18001a60e  cmp     qword ptr [rdi+18h], 8
0x18001a613  xorps   xmm0, xmm0
0x18001a616  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001a61a  jb      short loc_18001A61F
0x18001a61c  mov     rdi, [rdi]
0x18001a61f  mov     rdx, rdi; SourceString
0x18001a622  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001a626  call    cs:__imp_RtlInitUnicodeStringEx
0x18001a62c  test    eax, eax
0x18001a62e  js      short loc_18001A691
0x18001a630  lea     r8, [rbp+57h+Sid]
0x18001a634  lea     rdx, [rbp+57h+var_48]
0x18001a638  lea     rcx, [rbp+57h+DestinationString]
0x18001a63c  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18001a642  test    eax, eax
0x18001a644  js      short loc_18001A691
0x18001a646  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18001a64a  mov     [rbp+57h+StringSid], rsi
0x18001a64e  lea     rcx, [rbp+57h+Sid]; Sid
0x18001a652  call    ConvertSidToStringSidW
0x18001a657  test    eax, eax
0x18001a659  jz      short loc_18001A691
0x18001a65b  mov     rdi, [rbp+57h+StringSid]
0x18001a65f  cmp     [rdi], si
0x18001a662  jnz     short loc_18001A669
0x18001a664  mov     r8, rsi
0x18001a667  jmp     short loc_18001A677
0x18001a669  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001a66d  inc     r8
0x18001a670  cmp     [rdi+r8*2], si
0x18001a675  jnz     short loc_18001A66D
0x18001a677  mov     rdx, rdi
0x18001a67a  lea     rcx, [rbp+57h+var_98]
0x18001a67e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001a683  mov     rcx, rdi; hMem
0x18001a686  call    cs:__imp_LocalFree
0x18001a68c  jmp     loc_18001A5FD
0x18001a691  lea     rdx, Options
0x18001a698  mov     rcx, rbx
0x18001a69b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001a6a0  xor     r8d, r8d
0x18001a6a3  lea     rcx, [rbp+57h+var_98]
0x18001a6a7  mov     dl, 1
0x18001a6a9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001a6ae  mov     rax, rbx
0x18001a6b1  mov     rcx, [rbp+57h+var_18]
0x18001a6b5  xor     rcx, rsp; StackCookie
0x18001a6b8  call    __security_check_cookie
0x18001a6bd  mov     rbx, [rsp+0D0h+arg_10]
0x18001a6c5  add     rsp, 0C0h
0x18001a6cc  pop     rdi
0x18001a6cd  pop     rsi
0x18001a6ce  pop     rbp
0x18001a6cf  retn
```

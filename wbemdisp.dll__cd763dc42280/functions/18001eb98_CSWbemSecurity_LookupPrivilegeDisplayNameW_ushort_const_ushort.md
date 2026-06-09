# CSWbemSecurity::LookupPrivilegeDisplayNameW(ushort const *,ushort * *)

- ea: `0x18001eb98`
- end: `0x18001ec6d`
- name: `?LookupPrivilegeDisplayNameW@CSWbemSecurity@@SAXPEBGPEAPEAG@Z`
- size: `213`
- prototype: `void __fastcall(LPCWSTR lpName, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c120`

## callees

- `0x18001eb98`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ec3c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ec5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ec3c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ec5c`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ec05`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001ec05`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001ec48`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18001ec48`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeDisplayNameW` at `0x18001ebe3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeDisplayNameW` at `0x18001ec2f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeDisplayNameW` at `0x18001ebe3`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeDisplayNameW` at `0x18001ec2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSWbemSecurity::LookupPrivilegeDisplayNameW(LPCWSTR lpName, unsigned __int16 **a2)
{
  OLECHAR *v4; // rdi
  WCHAR v5; // [rsp+58h] [rbp+10h] BYREF
  DWORD cchDisplayName; // [rsp+60h] [rbp+18h] BYREF
  DWORD LanguageId; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 )
  {
    if ( CSWbemSecurity::s_bIsNT )
    {
      LanguageId = 0;
      cchDisplayName = 1;
      LookupPrivilegeDisplayNameW(0, lpName, &v5, &cchDisplayName, &LanguageId);
      v4 = (OLECHAR *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cchDisplayName + 1, 2u));
      if ( v4 )
      {
        if ( LookupPrivilegeDisplayNameW(&SystemName, lpName, v4, &cchDisplayName, &LanguageId) )
          *a2 = SysAllocString(v4);
        CWin32DefaultArena::WbemMemFree(v4);
      }
    }
    if ( !*a2 )
      *a2 = SysAllocString(&SystemName);
  }
}

```

## disassembly

```asm
0x18001eb98  test    rdx, rdx
0x18001eb9b  jz      locret_18001EC6C
0x18001eba1  mov     r11, rsp
0x18001eba4  push    rbx
0x18001eba5  push    rsi
0x18001eba6  push    rdi
0x18001eba7  sub     rsp, 30h
0x18001ebab  mov     rbx, rdx
0x18001ebae  mov     rsi, rcx
0x18001ebb1  cmp     cs:?s_bIsNT@CSWbemSecurity@@0_NA, 0; bool CSWbemSecurity::s_bIsNT
0x18001ebb8  jz      loc_18001EC4F
0x18001ebbe  mov     [rsp+48h+LanguageId], 0
0x18001ebc6  mov     [rsp+48h+cchDisplayName], 1
0x18001ebce  lea     rax, [r11+20h]
0x18001ebd2  mov     [r11-28h], rax
0x18001ebd6  lea     r9, [r11+18h]; cchDisplayName
0x18001ebda  lea     r8, [r11+10h]; lpDisplayName
0x18001ebde  mov     rdx, rcx; lpName
0x18001ebe1  xor     ecx, ecx; lpSystemName
0x18001ebe3  call    cs:__imp_LookupPrivilegeDisplayNameW
0x18001ebe9  mov     ecx, [rsp+48h+cchDisplayName]
0x18001ebed  inc     ecx
0x18001ebef  mov     eax, 2
0x18001ebf4  mul     rcx
0x18001ebf7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001ebfe  cmovb   rax, rcx
0x18001ec02  mov     rcx, rax
0x18001ec05  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001ec0b  mov     rdi, rax
0x18001ec0e  test    rax, rax
0x18001ec11  jz      short loc_18001EC4F
0x18001ec13  lea     rax, [rsp+48h+LanguageId]
0x18001ec18  mov     [rsp+48h+lpLanguageId], rax; lpLanguageId
0x18001ec1d  lea     r9, [rsp+48h+cchDisplayName]; cchDisplayName
0x18001ec22  mov     r8, rdi; lpDisplayName
0x18001ec25  mov     rdx, rsi; lpName
0x18001ec28  lea     rcx, SystemName; lpSystemName
0x18001ec2f  call    cs:__imp_LookupPrivilegeDisplayNameW
0x18001ec35  test    eax, eax
0x18001ec37  jz      short loc_18001EC45
0x18001ec39  mov     rcx, rdi; psz
0x18001ec3c  call    cs:__imp_SysAllocString
0x18001ec42  mov     [rbx], rax
0x18001ec45  mov     rcx, rdi
0x18001ec48  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18001ec4e  nop
0x18001ec4f  cmp     qword ptr [rbx], 0
0x18001ec53  jnz     short loc_18001EC65
0x18001ec55  lea     rcx, SystemName; psz
0x18001ec5c  call    cs:__imp_SysAllocString
0x18001ec62  mov     [rbx], rax
0x18001ec65  add     rsp, 30h
0x18001ec69  pop     rdi
0x18001ec6a  pop     rsi
0x18001ec6b  pop     rbx
0x18001ec6c  retn
```

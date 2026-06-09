# IsInteractiveUserLogonToken(void *)

- ea: `0x1800a7bb0`
- end: `0x1800a7d07`
- name: `?IsInteractiveUserLogonToken@@YAHPEAX@Z`
- size: `343`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18014d610`

## callees

- `0x18000aa0c`
- `0x1800a7bb0`
- `0x1800e09a0`
- `0x180106340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7c3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7caf`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a7c16`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800a7c16`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800a7c86`
- `api-ms-win-security-base-l1-2-0!CheckTokenMembershipEx` at `0x1800a7c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7c6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a7c6b`

## pseudocode

```c
__int64 __fastcall IsInteractiveUserLogonToken(void *a1)
{
  DWORD v2; // eax
  DWORD LastError; // eax
  unsigned int v5; // ebx
  unsigned int v6; // [rsp+60h] [rbp-20h] BYREF
  PSID hMem; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  hMem = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 4u, 0, 0, 0, 0, 0, 0, 0, &hMem) )
  {
    if ( (unsigned int)CheckTokenMembershipEx(a1, hMem, 1, &v6) )
    {
      v5 = v6;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, LastError);
      }
      v5 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
    return v5;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105)
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
    {
      v2 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids, v2);
    }
    if ( hMem )
      LocalFree(hMem);
    return 0;
  }
}

```

## disassembly

```asm
0x1800a7bb0  mov     [rsp-8+arg_8], rbx
0x1800a7bb5  mov     [rsp-8+arg_10], rdi
0x1800a7bba  push    rbp
0x1800a7bbb  mov     rbp, rsp
0x1800a7bbe  sub     rsp, 80h
0x1800a7bc5  mov     rax, cs:__security_cookie
0x1800a7bcc  xor     rax, rsp
0x1800a7bcf  mov     [rbp+var_8], rax
0x1800a7bd3  xor     edi, edi
0x1800a7bd5  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800a7bdb  lea     rax, [rbp+hMem]
0x1800a7bdf  mov     [rbp+var_20], edi
0x1800a7be2  mov     [rsp+80h+pSid], rax; pSid
0x1800a7be7  mov     rbx, rcx
0x1800a7bea  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x1800a7bee  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800a7bf2  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x1800a7bf6  lea     r8d, [rdi+4]; nSubAuthority0
0x1800a7bfa  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x1800a7bfe  xor     r9d, r9d; nSubAuthority1
0x1800a7c01  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x1800a7c05  mov     dl, 1; nSubAuthorityCount
0x1800a7c07  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x1800a7c0b  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x1800a7c0f  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x1800a7c12  mov     [rbp+hMem], rdi
0x1800a7c16  call    cs:__imp_AllocateAndInitializeSid
0x1800a7c1c  test    eax, eax
0x1800a7c1e  jnz     short loc_1800A7C75
0x1800a7c20  mov     rax, cs:WPP_GLOBAL_Control
0x1800a7c27  lea     rcx, WPP_GLOBAL_Control
0x1800a7c2e  cmp     rax, rcx
0x1800a7c31  jz      short loc_1800A7C62
0x1800a7c33  cmp     byte ptr [rax+69h], 1
0x1800a7c37  jb      short loc_1800A7C62
0x1800a7c39  test    byte ptr [rax+6Ch], 1
0x1800a7c3d  jz      short loc_1800A7C62
0x1800a7c3f  call    cs:__imp_GetLastError
0x1800a7c45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7c4c  lea     edx, [rdi+27h]
0x1800a7c4f  mov     r9d, eax
0x1800a7c52  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x1800a7c59  mov     rcx, [rcx+60h]
0x1800a7c5d  call    WPP_SF_d
0x1800a7c62  mov     rcx, [rbp+hMem]; hMem
0x1800a7c66  test    rcx, rcx
0x1800a7c69  jz      short loc_1800A7C71
0x1800a7c6b  call    cs:__imp_LocalFree
0x1800a7c71  xor     eax, eax
0x1800a7c73  jmp     short loc_1800A7CE6
0x1800a7c75  mov     rdx, [rbp+hMem]
0x1800a7c79  lea     r9, [rbp+var_20]
0x1800a7c7d  mov     r8d, 1
0x1800a7c83  mov     rcx, rbx
0x1800a7c86  call    cs:__imp_CheckTokenMembershipEx
0x1800a7c8c  test    eax, eax
0x1800a7c8e  jnz     short loc_1800A7CD8
0x1800a7c90  mov     rax, cs:WPP_GLOBAL_Control
0x1800a7c97  lea     rcx, WPP_GLOBAL_Control
0x1800a7c9e  cmp     rax, rcx
0x1800a7ca1  jz      short loc_1800A7CD4
0x1800a7ca3  cmp     byte ptr [rax+69h], 1
0x1800a7ca7  jb      short loc_1800A7CD4
0x1800a7ca9  test    byte ptr [rax+6Ch], 1
0x1800a7cad  jz      short loc_1800A7CD4
0x1800a7caf  call    cs:__imp_GetLastError
0x1800a7cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7cbc  lea     r8, WPP_ede209a8f13d3dc52ae0550d8960da19_Traceguids
0x1800a7cc3  mov     edx, 28h ; '('
0x1800a7cc8  mov     r9d, eax
0x1800a7ccb  mov     rcx, [rcx+60h]
0x1800a7ccf  call    WPP_SF_d
0x1800a7cd4  mov     ebx, edi
0x1800a7cd6  jmp     short loc_1800A7CDB
0x1800a7cd8  mov     ebx, [rbp+var_20]
0x1800a7cdb  lea     rcx, [rbp+hMem]
0x1800a7cdf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a7ce4  mov     eax, ebx
0x1800a7ce6  mov     rcx, [rbp+var_8]
0x1800a7cea  xor     rcx, rsp; StackCookie
0x1800a7ced  call    __security_check_cookie
0x1800a7cf2  lea     r11, [rsp+80h+var_s0]
0x1800a7cfa  mov     rbx, [r11+18h]
0x1800a7cfe  mov     rdi, [r11+20h]
0x1800a7d02  mov     rsp, r11
0x1800a7d05  pop     rbp
0x1800a7d06  retn
```

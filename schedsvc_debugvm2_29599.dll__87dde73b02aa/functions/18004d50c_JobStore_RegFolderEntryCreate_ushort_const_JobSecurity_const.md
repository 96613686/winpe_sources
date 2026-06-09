# JobStore::RegFolderEntryCreate(ushort const *,JobSecurity const &)

- ea: `0x18004d50c`
- end: `0x18004d619`
- name: `?RegFolderEntryCreate@JobStore@@QEBAJPEBGAEBVJobSecurity@@@Z`
- size: `269`
- prototype: `int(JobStore *__hidden this, const unsigned __int16 *, const struct JobSecurity *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800213f8`
- `0x180024ce0`
- `0x18002506c`

## callees

- `0x18001fca0`
- `0x180021300`
- `0x180049b74`
- `0x18004a5d8`
- `0x18004d50c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18004d601`
- `OLEAUT32!__imp_SysFreeString` at `0x18004d601`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004d5b8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004d5b8`

## string_xrefs

- `0x18004d54e`: `TaskCache\Tree\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JobStore::RegFolderEntryCreate(HKEY *this, const unsigned __int16 *a2, const struct JobSecurity *a3)
{
  const unsigned __int16 *v6; // rdx
  LSTATUS v7; // eax
  signed int v8; // ebx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-20h] BYREF
  DWORD dwDisposition; // [rsp+90h] [rbp+20h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+A8h] [rbp+38h] BYREF

  dwDisposition = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = tsched::StoreSecurity::g_pRestrictedKeySecurity;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  lpSubKey = 0;
  ATL::CComBSTR::operator=(&lpSubKey, L"TaskCache\\Tree\\");
  v6 = a2 + 1;
  if ( *a2 != 92 )
    v6 = a2;
  ATL::CComBSTR::operator+=(&lpSubKey, v6);
  phkResult = 0;
  v7 = RegCreateKeyExW(this[2], lpSubKey, 0, 0, 0, 0xF003Fu, &SecurityAttributes, &phkResult, &dwDisposition);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
  }
  else if ( dwDisposition == 2 )
  {
    v8 = -2147024713;
  }
  else
  {
    v8 = JobSecurity::StreamOut(a3, phkResult);
    if ( v8 >= 0 )
      v8 = 0;
  }
  wmi::AutoRegKey::Close((wmi::AutoRegKey *)&phkResult);
  SysFreeString((BSTR)lpSubKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004d50c  mov     [rsp-18h+arg_10], rbx
0x18004d511  push    rbp
0x18004d512  push    rsi
0x18004d513  push    rdi
0x18004d514  mov     rbp, rsp
0x18004d517  sub     rsp, 70h
0x18004d51b  mov     rsi, r8
0x18004d51e  mov     rbx, rdx
0x18004d521  mov     rdi, rcx
0x18004d524  mov     [rbp+dwDisposition], 0
0x18004d52b  mov     qword ptr [rbp+SecurityAttributes.nLength], 18h
0x18004d533  mov     rax, cs:?g_pRestrictedKeySecurity@StoreSecurity@tsched@@3PEAXEA; void * tsched::StoreSecurity::g_pRestrictedKeySecurity
0x18004d53a  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x18004d53e  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], 0
0x18004d546  mov     [rbp+lpSubKey], 0
0x18004d54e  lea     rdx, aTaskcacheTree_0; "TaskCache\\Tree\\"
0x18004d555  lea     rcx, [rbp+lpSubKey]
0x18004d559  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18004d55e  mov     eax, 5Ch ; '\'
0x18004d563  lea     rdx, [rbx+2]
0x18004d567  cmp     ax, [rbx]
0x18004d56a  cmovnz  rdx, rbx
0x18004d56e  lea     rcx, [rbp+lpSubKey]
0x18004d572  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x18004d577  mov     [rbp+arg_18], 0
0x18004d57f  lea     rax, [rbp+dwDisposition]
0x18004d583  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18004d588  lea     rax, [rbp+arg_18]
0x18004d58c  mov     [rsp+70h+phkResult], rax; phkResult
0x18004d591  lea     rax, [rbp+SecurityAttributes]
0x18004d595  mov     [rsp+70h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18004d59a  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x18004d5a2  mov     [rsp+70h+dwOptions], 0; dwOptions
0x18004d5aa  xor     r9d, r9d; lpClass
0x18004d5ad  xor     r8d, r8d; Reserved
0x18004d5b0  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18004d5b4  mov     rcx, [rdi+10h]; hKey
0x18004d5b8  call    cs:__imp_RegCreateKeyExW
0x18004d5be  mov     ebx, eax
0x18004d5c0  test    eax, eax
0x18004d5c2  jz      short loc_18004D5D1
0x18004d5c4  jle     short loc_18004D5F3
0x18004d5c6  movzx   ebx, ax
0x18004d5c9  or      ebx, 80070000h
0x18004d5cf  jmp     short loc_18004D5F3
0x18004d5d1  cmp     [rbp+dwDisposition], 2
0x18004d5d5  jnz     short loc_18004D5DE
0x18004d5d7  mov     ebx, 800700B7h
0x18004d5dc  jmp     short loc_18004D5F3
0x18004d5de  mov     rdx, [rbp+arg_18]; HKEY
0x18004d5e2  mov     rcx, rsi; this
0x18004d5e5  call    ?StreamOut@JobSecurity@@QEBAJPEAUHKEY__@@@Z; JobSecurity::StreamOut(HKEY__ *)
0x18004d5ea  mov     ebx, eax
0x18004d5ec  xor     ecx, ecx
0x18004d5ee  test    eax, eax
0x18004d5f0  cmovns  ebx, ecx
0x18004d5f3  lea     rcx, [rbp+arg_18]; this
0x18004d5f7  call    ?Close@AutoRegKey@wmi@@QEAAXXZ; wmi::AutoRegKey::Close(void)
0x18004d5fc  nop
0x18004d5fd  mov     rcx, [rbp+lpSubKey]; bstrString
0x18004d601  call    cs:__imp_SysFreeString
0x18004d607  mov     eax, ebx
0x18004d609  mov     rbx, [rsp+70h+arg_10]
0x18004d611  add     rsp, 70h
0x18004d615  pop     rdi
0x18004d616  pop     rsi
0x18004d617  pop     rbp
0x18004d618  retn
```

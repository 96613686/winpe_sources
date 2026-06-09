# ComputeService::Client::IsCallerHyperVAdministrator(void)

- ea: `0x18003a324`
- end: `0x18003a434`
- name: `?IsCallerHyperVAdministrator@Client@ComputeService@@YA_NXZ`
- size: `272`
- prototype: `bool __fastcall(ComputeService::Client *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18007c7f8`
- `0x18007c8a6`
- `0x18007c94b`
- `0x18007c9f0`

## callees

- `0x180002f50`
- `0x180006660`
- `0x180039e80`
- `0x18003a324`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a3eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a38f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003a3eb`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a366`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a3ca`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a366`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003a3ca`

## pseudocode

```c
bool __fastcall ComputeService::Client::IsCallerHyperVAdministrator(ComputeService::Client *this, __int64 a2, void *a3)
{
  char v3; // bl
  bool v4; // di
  void *v5; // r8
  PSID SidToCheck[2]; // [rsp+20h] [rbp-60h] BYREF
  _BYTE v8[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v9[32]; // [rsp+50h] [rbp-30h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp-10h] BYREF

  IsMember = 0;
  Vml::VmSid::VmSid((Vml::VmSid *)SidToCheck, WinBuiltinAdministratorsSid, a3);
  v3 = 1;
  v4 = CheckTokenMembership(0, SidToCheck[0], &IsMember) && IsMember;
  if ( SidToCheck[0] )
    LocalFree(SidToCheck[0]);
  std::wstring::~wstring(v9);
  std::wstring::~wstring(v8);
  if ( v4 )
    return 1;
  Vml::VmSid::VmSid((Vml::VmSid *)SidToCheck, WinBuiltinHyperVAdminsSid, v5);
  if ( !CheckTokenMembership(0, SidToCheck[0], &IsMember) || !IsMember )
    v3 = 0;
  if ( SidToCheck[0] )
    LocalFree(SidToCheck[0]);
  std::wstring::~wstring(v9);
  std::wstring::~wstring(v8);
  return v3 != 0;
}

```

## disassembly

```asm
0x18003a324  mov     [rsp-8+arg_0], rbx
0x18003a329  mov     [rsp-8+arg_8], rdi
0x18003a32e  push    rbp
0x18003a32f  mov     rbp, rsp
0x18003a332  sub     rsp, 80h
0x18003a339  mov     rax, cs:__security_cookie
0x18003a340  xor     rax, rsp
0x18003a343  mov     [rbp+var_8], rax
0x18003a347  mov     edx, 1Ah; enum WELL_KNOWN_SID_TYPE
0x18003a34c  mov     [rbp+IsMember], 0
0x18003a353  lea     rcx, [rbp+SidToCheck]; this
0x18003a357  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x18003a35c  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18003a360  lea     r8, [rbp+IsMember]; IsMember
0x18003a364  xor     ecx, ecx; TokenHandle
0x18003a366  call    cs:__imp_CheckTokenMembership
0x18003a36d  nop     dword ptr [rax+rax+00h]
0x18003a372  mov     bl, 1
0x18003a374  test    eax, eax
0x18003a376  jz      short loc_18003A383
0x18003a378  cmp     [rbp+IsMember], 0
0x18003a37c  jz      short loc_18003A383
0x18003a37e  mov     dil, bl
0x18003a381  jmp     short loc_18003A386
0x18003a383  xor     dil, dil
0x18003a386  mov     rcx, [rbp+SidToCheck]; hMem
0x18003a38a  test    rcx, rcx
0x18003a38d  jz      short loc_18003A39B
0x18003a38f  call    cs:__imp_LocalFree
0x18003a396  nop     dword ptr [rax+rax+00h]
0x18003a39b  lea     rcx, [rbp+var_30]
0x18003a39f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a3a4  lea     rcx, [rbp+var_50]
0x18003a3a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a3ad  test    dil, dil
0x18003a3b0  jnz     short loc_18003A410
0x18003a3b2  mov     edx, 63h ; 'c'; enum WELL_KNOWN_SID_TYPE
0x18003a3b7  lea     rcx, [rbp+SidToCheck]; this
0x18003a3bb  call    ??0VmSid@Vml@@QEAA@W4WELL_KNOWN_SID_TYPE@@PEAX@Z; Vml::VmSid::VmSid(WELL_KNOWN_SID_TYPE,void *)
0x18003a3c0  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x18003a3c4  lea     r8, [rbp+IsMember]; IsMember
0x18003a3c8  xor     ecx, ecx; TokenHandle
0x18003a3ca  call    cs:__imp_CheckTokenMembership
0x18003a3d1  nop     dword ptr [rax+rax+00h]
0x18003a3d6  test    eax, eax
0x18003a3d8  jz      short loc_18003A3E0
0x18003a3da  cmp     [rbp+IsMember], 0
0x18003a3de  jnz     short loc_18003A3E2
0x18003a3e0  xor     bl, bl
0x18003a3e2  mov     rcx, [rbp+SidToCheck]; hMem
0x18003a3e6  test    rcx, rcx
0x18003a3e9  jz      short loc_18003A3F7
0x18003a3eb  call    cs:__imp_LocalFree
0x18003a3f2  nop     dword ptr [rax+rax+00h]
0x18003a3f7  lea     rcx, [rbp+var_30]
0x18003a3fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a400  lea     rcx, [rbp+var_50]
0x18003a404  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003a409  test    bl, bl
0x18003a40b  setnz   al
0x18003a40e  jmp     short loc_18003A412
0x18003a410  mov     al, bl
0x18003a412  mov     rcx, [rbp+var_8]
0x18003a416  xor     rcx, rsp; StackCookie
0x18003a419  call    __security_check_cookie
0x18003a41e  lea     r11, [rsp+80h+var_s0]
0x18003a426  mov     rbx, [r11+10h]
0x18003a42a  mov     rdi, [r11+18h]
0x18003a42e  mov     rsp, r11
0x18003a431  pop     rbp
0x18003a432  retn
```

# CSecurityAttribute::GetAdminSid(void)

- ea: `0x1400121f0`
- end: `0x140012319`
- name: `?GetAdminSid@CSecurityAttribute@@AEAAJXZ`
- size: `297`
- prototype: `__int64 __fastcall(CSecurityAttribute *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140012818`

## callees

- `0x14000e280`
- `0x1400121f0`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x140012260`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140012260`
- `ADVAPI32!FreeSid` at `0x1400122a8`
- `ADVAPI32!FreeSid` at `0x1400122a8`
- `KERNEL32!LocalFree` at `0x1400122ef`
- `KERNEL32!LocalFree` at `0x1400122ef`
- `KERNEL32!GetLastError` at `0x14001226e`
- `KERNEL32!GetLastError` at `0x14001226e`

## string_xrefs

- `0x140012285`: `Failed to get administrator's SID`
- `0x140012291`: `CSecurityAttribute::GetAdminSid`
- `0x1400122db`: `CSecurityAttribute::GetAdminSid`

## pseudocode

```c
__int64 __fastcall CSecurityAttribute::GetAdminSid(CSecurityAttribute *this)
{
  PSID *v1; // rdi
  signed int v3; // ebx
  signed int LastError; // eax
  HLOCAL v5; // rdi
  HLOCAL hMem; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-20h] BYREF

  v1 = (PSID *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    return 0;
  v3 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, (PSID *)this + 1) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
      v3 = -2147467259;
    WusaLogDebugEventA(L"CSecurityAttribute::GetAdminSid", 113, "Failed to get administrator's SID");
    FreeSid(*v1);
    *v1 = 0;
    hMem = 0;
    WusaGetErrorMessage(v3, (unsigned __int16 **)&hMem);
    v5 = hMem;
    WusaLogDebugEventA(
      L"CSecurityAttribute::GetAdminSid",
      124,
      "Exit with error code 0X%x (%ls)",
      v3,
      (const wchar_t *)hMem);
    if ( v5 )
      LocalFree(v5);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400121f0  mov     [rsp+arg_8], rbx
0x1400121f5  mov     [rsp+arg_10], rsi
0x1400121fa  push    rdi
0x1400121fb  sub     rsp, 80h
0x140012202  mov     rax, cs:__security_cookie
0x140012209  xor     rax, rsp
0x14001220c  mov     [rsp+88h+var_18], rax
0x140012211  lea     rdi, [rcx+8]
0x140012215  xor     esi, esi
0x140012217  cmp     [rdi], rsi
0x14001221a  jz      short loc_140012223
0x14001221c  xor     eax, eax
0x14001221e  jmp     loc_1400122F7
0x140012223  mov     [rsp+88h+pSid], rdi; pSid
0x140012228  lea     rcx, [rsp+88h+pIdentifierAuthority]; pIdentifierAuthority
0x14001222d  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x140012231  mov     r9d, 220h; nSubAuthority1
0x140012237  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x14001223b  mov     r8d, 20h ; ' '; nSubAuthority0
0x140012241  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x140012245  mov     dl, 2; nSubAuthorityCount
0x140012247  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x14001224b  mov     ebx, esi
0x14001224d  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x140012251  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x140012255  mov     dword ptr [rsp+88h+pIdentifierAuthority.Value], esi
0x140012259  mov     word ptr [rsp+88h+pIdentifierAuthority.Value+4], 500h
0x140012260  call    cs:__imp_AllocateAndInitializeSid
0x140012266  test    eax, eax
0x140012268  jnz     loc_1400122F5
0x14001226e  call    cs:__imp_GetLastError
0x140012274  mov     ebx, eax
0x140012276  test    eax, eax
0x140012278  jle     short loc_140012283
0x14001227a  movzx   ebx, ax
0x14001227d  or      ebx, 80070000h
0x140012283  test    ebx, ebx
0x140012285  lea     r8, aFailedToGetAdm_0; "Failed to get administrator's SID"
0x14001228c  mov     eax, 80004005h
0x140012291  lea     rcx, aCsecurityattri_1; "CSecurityAttribute::GetAdminSid"
0x140012298  mov     edx, 71h ; 'q'
0x14001229d  cmovns  ebx, eax
0x1400122a0  call    WusaLogDebugEventA
0x1400122a5  mov     rcx, [rdi]; pSid
0x1400122a8  call    cs:__imp_FreeSid
0x1400122ae  lea     rdx, [rsp+88h+hMem]; unsigned __int16 **
0x1400122b3  mov     [rdi], rsi
0x1400122b6  mov     ecx, ebx; dwMessageId
0x1400122b8  mov     [rsp+88h+hMem], rsi
0x1400122bd  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x1400122c2  mov     rdi, [rsp+88h+hMem]
0x1400122c7  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x1400122ce  mov     r9d, ebx
0x1400122d1  mov     qword ptr [rsp+88h+nSubAuthority2], rdi
0x1400122d6  mov     edx, 7Ch ; '|'
0x1400122db  lea     rcx, aCsecurityattri_1; "CSecurityAttribute::GetAdminSid"
0x1400122e2  call    WusaLogDebugEventA
0x1400122e7  test    rdi, rdi
0x1400122ea  jz      short loc_1400122F5
0x1400122ec  mov     rcx, rdi; hMem
0x1400122ef  call    cs:__imp_LocalFree
0x1400122f5  mov     eax, ebx
0x1400122f7  mov     rcx, [rsp+88h+var_18]
0x1400122fc  xor     rcx, rsp; StackCookie
0x1400122ff  call    __security_check_cookie
0x140012304  lea     r11, [rsp+88h+var_8]
0x14001230c  mov     rbx, [r11+18h]
0x140012310  mov     rsi, [r11+20h]
0x140012314  mov     rsp, r11
0x140012317  pop     rdi
0x140012318  retn
```

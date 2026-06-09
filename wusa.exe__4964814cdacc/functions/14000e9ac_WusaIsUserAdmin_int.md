# WusaIsUserAdmin(int *)

- ea: `0x14000e9ac`
- end: `0x14000eb04`
- name: `?WusaIsUserAdmin@@YAJPEAH@Z`
- size: `344`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14000f8f0`

## callees

- `0x14000e280`
- `0x14000e9ac`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x14000ea11`
- `ADVAPI32!AllocateAndInitializeSid` at `0x14000ea11`
- `ADVAPI32!CheckTokenMembership` at `0x14000ea62`
- `ADVAPI32!CheckTokenMembership` at `0x14000ea62`
- `ADVAPI32!FreeSid` at `0x14000ea9f`
- `ADVAPI32!FreeSid` at `0x14000ea9f`
- `KERNEL32!LocalFree` at `0x14000eae4`
- `KERNEL32!LocalFree` at `0x14000eae4`
- `KERNEL32!GetLastError` at `0x14000ea1f`
- `KERNEL32!GetLastError` at `0x14000ea6c`
- `KERNEL32!GetLastError` at `0x14000ea1f`
- `KERNEL32!GetLastError` at `0x14000ea6c`

## string_xrefs

- `0x14000ea34`: `Failed to allocate and initialize Administrators group SID.`
- `0x14000ea81`: `Failed to check token membership.`

## pseudocode

```c
__int64 __fastcall WusaIsUserAdmin(int *a1)
{
  signed int v2; // eax
  signed int v3; // ebx
  const char *v4; // r8
  __int64 v5; // rdx
  signed int LastError; // eax
  HLOCAL v7; // rdi
  WINBOOL IsMember; // [rsp+60h] [rbp+7h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+Fh] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+17h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+1Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
    {
      v3 = 0;
      *a1 = IsMember;
      goto LABEL_13;
    }
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = "Failed to check token membership.";
    v5 = 99;
  }
  else
  {
    SidToCheck = 0;
    v2 = GetLastError();
    v3 = v2;
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    v4 = "Failed to allocate and initialize Administrators group SID.";
    v5 = 94;
  }
  if ( v3 >= 0 )
    v3 = -2147467259;
  WusaLogDebugEventA(L"WusaIsUserAdmin", v5, v4);
LABEL_13:
  if ( SidToCheck )
    FreeSid(SidToCheck);
  if ( v3 < 0 )
  {
    hMem = 0;
    WusaGetErrorMessage(v3, (unsigned __int16 **)&hMem);
    v7 = hMem;
    WusaLogDebugEventA(L"WusaIsUserAdmin", 111, "Exit with error code 0X%x (%ls)", v3, (const wchar_t *)hMem);
    if ( v7 )
      LocalFree(v7);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000e9ac  push    rbp
0x14000e9ae  push    rbx
0x14000e9af  push    rsi
0x14000e9b0  push    rdi
0x14000e9b1  lea     rbp, [rsp-3Fh]
0x14000e9b6  sub     rsp, 98h
0x14000e9bd  mov     rax, cs:__security_cookie
0x14000e9c4  xor     rax, rsp
0x14000e9c7  mov     [rbp+57h+var_30], rax
0x14000e9cb  xor     esi, esi
0x14000e9cd  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x14000e9d3  lea     rax, [rbp+57h+SidToCheck]
0x14000e9d7  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x14000e9da  mov     [rsp+0B0h+pSid], rax; pSid
0x14000e9df  mov     rdi, rcx
0x14000e9e2  mov     [rsp+0B0h+nSubAuthority7], esi; nSubAuthority7
0x14000e9e6  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x14000e9ea  mov     [rsp+0B0h+nSubAuthority6], esi; nSubAuthority6
0x14000e9ee  lea     r8d, [rsi+20h]; nSubAuthority0
0x14000e9f2  mov     [rsp+0B0h+nSubAuthority5], esi; nSubAuthority5
0x14000e9f6  mov     r9d, 220h; nSubAuthority1
0x14000e9fc  mov     [rsp+0B0h+nSubAuthority4], esi; nSubAuthority4
0x14000ea00  mov     dl, 2; nSubAuthorityCount
0x14000ea02  mov     [rsp+0B0h+nSubAuthority3], esi; nSubAuthority3
0x14000ea06  mov     [rsp+0B0h+nSubAuthority2], esi; nSubAuthority2
0x14000ea0a  mov     [rbp+57h+SidToCheck], rsi
0x14000ea0e  mov     [rbp+57h+IsMember], esi
0x14000ea11  call    cs:__imp_AllocateAndInitializeSid
0x14000ea17  test    eax, eax
0x14000ea19  jnz     short loc_14000EA58
0x14000ea1b  mov     [rbp+57h+SidToCheck], rsi
0x14000ea1f  call    cs:__imp_GetLastError
0x14000ea25  mov     ebx, eax
0x14000ea27  test    eax, eax
0x14000ea29  jle     short loc_14000EA34
0x14000ea2b  movzx   ebx, ax
0x14000ea2e  or      ebx, 80070000h
0x14000ea34  lea     r8, aFailedToAlloca_17; "Failed to allocate and initialize Admin"...
0x14000ea3b  mov     edx, 5Eh ; '^'
0x14000ea40  test    ebx, ebx
0x14000ea42  lea     rcx, aWusaisuseradmi; "WusaIsUserAdmin"
0x14000ea49  mov     eax, 80004005h
0x14000ea4e  cmovns  ebx, eax
0x14000ea51  call    WusaLogDebugEventA
0x14000ea56  jmp     short loc_14000EA96
0x14000ea58  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x14000ea5c  lea     r8, [rbp+57h+IsMember]; IsMember
0x14000ea60  xor     ecx, ecx; TokenHandle
0x14000ea62  call    cs:__imp_CheckTokenMembership
0x14000ea68  test    eax, eax
0x14000ea6a  jnz     short loc_14000EA8F
0x14000ea6c  call    cs:__imp_GetLastError
0x14000ea72  mov     ebx, eax
0x14000ea74  test    eax, eax
0x14000ea76  jle     short loc_14000EA81
0x14000ea78  movzx   ebx, ax
0x14000ea7b  or      ebx, 80070000h
0x14000ea81  lea     r8, aFailedToCheckT; "Failed to check token membership."
0x14000ea88  mov     edx, 63h ; 'c'
0x14000ea8d  jmp     short loc_14000EA40
0x14000ea8f  mov     eax, [rbp+57h+IsMember]
0x14000ea92  mov     ebx, esi
0x14000ea94  mov     [rdi], eax
0x14000ea96  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x14000ea9a  test    rcx, rcx
0x14000ea9d  jz      short loc_14000EAA5
0x14000ea9f  call    cs:__imp_FreeSid
0x14000eaa5  test    ebx, ebx
0x14000eaa7  jns     short loc_14000EAEA
0x14000eaa9  lea     rdx, [rbp+57h+hMem]; unsigned __int16 **
0x14000eaad  mov     [rbp+57h+hMem], rsi
0x14000eab1  mov     ecx, ebx; dwMessageId
0x14000eab3  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x14000eab8  mov     rdi, [rbp+57h+hMem]
0x14000eabc  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x14000eac3  mov     r9d, ebx
0x14000eac6  mov     qword ptr [rsp+0B0h+nSubAuthority2], rdi
0x14000eacb  mov     edx, 6Fh ; 'o'
0x14000ead0  lea     rcx, aWusaisuseradmi; "WusaIsUserAdmin"
0x14000ead7  call    WusaLogDebugEventA
0x14000eadc  test    rdi, rdi
0x14000eadf  jz      short loc_14000EAEA
0x14000eae1  mov     rcx, rdi; hMem
0x14000eae4  call    cs:__imp_LocalFree
0x14000eaea  mov     eax, ebx
0x14000eaec  mov     rcx, [rbp+57h+var_30]
0x14000eaf0  xor     rcx, rsp; StackCookie
0x14000eaf3  call    __security_check_cookie
0x14000eaf8  add     rsp, 98h
0x14000eaff  pop     rdi
0x14000eb00  pop     rsi
0x14000eb01  pop     rbx
0x14000eb02  pop     rbp
0x14000eb03  retn
```

# CUserName::IsAdmin(int *)

- ea: `0x1800bf2e0`
- end: `0x1800bf42f`
- name: `?IsAdmin@CUserName@@UEAAJPEAH@Z`
- size: `335`
- prototype: `__int64 __fastcall(CUserName *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180009940`
- `0x180015020`
- `0x1800a0ae0`
- `0x1800bf2e0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800bf40c`
- `ntdll!RtlFreeSid` at `0x1800bf40c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bf3bf`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bf370`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800bf370`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800bf3af`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800bf3af`

## string_xrefs

- `0x1800bf314`: `No token`
- `0x1800bf346`: `CUtil::CreateAdminSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUserName::IsAdmin(CUserName *this, int *a2)
{
  PSID v2; // rsi
  bool v4; // zf
  unsigned int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  signed int v9; // eax
  WINBOOL IsMember; // [rsp+50h] [rbp+30h] BYREF
  PSID SidToCheck; // [rsp+60h] [rbp+40h] BYREF
  void *DuplicateTokenHandle; // [rsp+68h] [rbp+48h] BYREF

  v2 = 0;
  v4 = (*((_BYTE *)this + 1600) & 4) == 0;
  SidToCheck = 0;
  DuplicateTokenHandle = 0;
  if ( v4 )
  {
    if ( !*((_QWORD *)this + 199) )
    {
      _DbgPrintMessage(8, "No token");
      v6 = -2147023888;
      goto LABEL_17;
    }
    v7 = CUtils::CreateAdminSid(&SidToCheck);
    v6 = v7;
    if ( v7 < 0 )
    {
      _DbgPrintMessage(8, "CUtil::CreateAdminSid failed: 0x%x in %s", v7, "CUserName::IsAdmin");
LABEL_6:
      v2 = SidToCheck;
      goto LABEL_15;
    }
    if ( !DuplicateToken(*((HANDLE *)this + 199), SecurityIdentification, &DuplicateTokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_6;
    }
    IsMember = 0;
    v2 = SidToCheck;
    if ( !CheckTokenMembership(DuplicateTokenHandle, SidToCheck, &IsMember) )
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      goto LABEL_15;
    }
    *((_DWORD *)this + 670) &= ~1u;
    *((_DWORD *)this + 670) |= IsMember & 1;
    *((_DWORD *)this + 400) |= 4u;
  }
  *a2 = *((_DWORD *)this + 670) & 1;
  v6 = 0;
LABEL_15:
  if ( v2 )
    RtlFreeSid(v2);
LABEL_17:
  SmartHANDLE::~SmartHANDLE((SmartHANDLE *)&DuplicateTokenHandle);
  return v6;
}

```

## disassembly

```asm
0x1800bf2e0  push    rbp
0x1800bf2e2  push    rbx
0x1800bf2e3  push    rsi
0x1800bf2e4  push    rdi
0x1800bf2e5  push    r14
0x1800bf2e7  mov     rbp, rsp
0x1800bf2ea  sub     rsp, 20h
0x1800bf2ee  xor     esi, esi
0x1800bf2f0  mov     r14, rdx
0x1800bf2f3  test    byte ptr [rcx+640h], 4
0x1800bf2fa  mov     rdi, rcx
0x1800bf2fd  mov     [rbp+SidToCheck], rsi
0x1800bf301  mov     [rbp+DuplicateTokenHandle], rsi
0x1800bf305  jnz     loc_1800BF3F6
0x1800bf30b  cmp     [rcx+638h], rsi
0x1800bf312  jnz     short loc_1800BF32D
0x1800bf314  lea     rdx, aNoToken; "No token"
0x1800bf31b  lea     ecx, [rsi+8]; int
0x1800bf31e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bf323  mov     ebx, 800703F0h
0x1800bf328  jmp     loc_1800BF418
0x1800bf32d  lea     rcx, [rbp+SidToCheck]; void **
0x1800bf331  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x1800bf336  mov     ebx, eax
0x1800bf338  test    eax, eax
0x1800bf33a  jns     short loc_1800BF360
0x1800bf33c  lea     r9, aCusernameIsadm; "CUserName::IsAdmin"
0x1800bf343  mov     r8d, eax
0x1800bf346  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x1800bf34d  mov     ecx, 8; int
0x1800bf352  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800bf357  mov     rsi, [rbp+SidToCheck]
0x1800bf35b  jmp     loc_1800BF404
0x1800bf360  mov     rcx, [rdi+638h]; ExistingTokenHandle
0x1800bf367  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800bf36b  mov     edx, 1; ImpersonationLevel
0x1800bf370  call    cs:__imp_DuplicateToken
0x1800bf377  nop     dword ptr [rax+rax+00h]
0x1800bf37c  test    eax, eax
0x1800bf37e  jnz     short loc_1800BF39D
0x1800bf380  call    cs:__imp_GetLastError
0x1800bf387  nop     dword ptr [rax+rax+00h]
0x1800bf38c  mov     ebx, eax
0x1800bf38e  test    eax, eax
0x1800bf390  jle     short loc_1800BF357
0x1800bf392  movzx   ebx, ax
0x1800bf395  or      ebx, 80070000h
0x1800bf39b  jmp     short loc_1800BF357
0x1800bf39d  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x1800bf3a1  lea     r8, [rbp+IsMember]; IsMember
0x1800bf3a5  mov     [rbp+IsMember], esi
0x1800bf3a8  mov     rsi, [rbp+SidToCheck]
0x1800bf3ac  mov     rdx, rsi; SidToCheck
0x1800bf3af  call    cs:__imp_CheckTokenMembership
0x1800bf3b6  nop     dword ptr [rax+rax+00h]
0x1800bf3bb  test    eax, eax
0x1800bf3bd  jnz     short loc_1800BF3DC
0x1800bf3bf  call    cs:__imp_GetLastError
0x1800bf3c6  nop     dword ptr [rax+rax+00h]
0x1800bf3cb  mov     ebx, eax
0x1800bf3cd  test    eax, eax
0x1800bf3cf  jle     short loc_1800BF404
0x1800bf3d1  movzx   ebx, ax
0x1800bf3d4  or      ebx, 80070000h
0x1800bf3da  jmp     short loc_1800BF404
0x1800bf3dc  and     dword ptr [rdi+0A78h], 0FFFFFFFEh
0x1800bf3e3  mov     eax, [rbp+IsMember]
0x1800bf3e6  and     eax, 1
0x1800bf3e9  or      [rdi+0A78h], eax
0x1800bf3ef  or      dword ptr [rdi+640h], 4
0x1800bf3f6  mov     eax, [rdi+0A78h]
0x1800bf3fc  and     eax, 1
0x1800bf3ff  mov     [r14], eax
0x1800bf402  xor     ebx, ebx
0x1800bf404  test    rsi, rsi
0x1800bf407  jz      short loc_1800BF418
0x1800bf409  mov     rcx, rsi; Sid
0x1800bf40c  call    cs:__imp_RtlFreeSid
0x1800bf413  nop     dword ptr [rax+rax+00h]
0x1800bf418  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x1800bf41c  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800bf421  mov     eax, ebx
0x1800bf423  add     rsp, 20h
0x1800bf427  pop     r14
0x1800bf429  pop     rdi
0x1800bf42a  pop     rsi
0x1800bf42b  pop     rbx
0x1800bf42c  pop     rbp
0x1800bf42d  retn
```

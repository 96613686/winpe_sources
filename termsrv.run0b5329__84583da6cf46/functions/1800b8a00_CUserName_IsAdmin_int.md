# CUserName::IsAdmin(int *)

- ea: `0x1800b8a00`
- end: `0x1800b8b30`
- name: `?IsAdmin@CUserName@@UEAAJPEAH@Z`
- size: `304`
- prototype: `__int64 __fastcall(CUserName *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000a210`
- `0x1800148d0`
- `0x18009c828`
- `0x1800b8a00`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x1800b8b14`
- `ntdll!RtlFreeSid` at `0x1800b8b14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8acd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8a9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b8acd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800b8a90`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800b8a90`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b8ac3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800b8ac3`

## string_xrefs

- `0x1800b8a34`: `No token`
- `0x1800b8a66`: `CUtil::CreateAdminSid failed: 0x%x in %s`

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
0x1800b8a00  push    rbp
0x1800b8a02  push    rbx
0x1800b8a03  push    rsi
0x1800b8a04  push    rdi
0x1800b8a05  push    r14
0x1800b8a07  mov     rbp, rsp
0x1800b8a0a  sub     rsp, 20h
0x1800b8a0e  xor     esi, esi
0x1800b8a10  mov     r14, rdx
0x1800b8a13  test    byte ptr [rcx+640h], 4
0x1800b8a1a  mov     rdi, rcx
0x1800b8a1d  mov     [rbp+SidToCheck], rsi
0x1800b8a21  mov     [rbp+DuplicateTokenHandle], rsi
0x1800b8a25  jnz     loc_1800B8AFE
0x1800b8a2b  cmp     [rcx+638h], rsi
0x1800b8a32  jnz     short loc_1800B8A4D
0x1800b8a34  lea     rdx, aNoToken; "No token"
0x1800b8a3b  lea     ecx, [rsi+8]; int
0x1800b8a3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b8a43  mov     ebx, 800703F0h
0x1800b8a48  jmp     loc_1800B8B1A
0x1800b8a4d  lea     rcx, [rbp+SidToCheck]; void **
0x1800b8a51  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x1800b8a56  mov     ebx, eax
0x1800b8a58  test    eax, eax
0x1800b8a5a  jns     short loc_1800B8A80
0x1800b8a5c  lea     r9, aCusernameIsadm; "CUserName::IsAdmin"
0x1800b8a63  mov     r8d, eax
0x1800b8a66  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x1800b8a6d  mov     ecx, 8; int
0x1800b8a72  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800b8a77  mov     rsi, [rbp+SidToCheck]
0x1800b8a7b  jmp     loc_1800B8B0C
0x1800b8a80  mov     rcx, [rdi+638h]; ExistingTokenHandle
0x1800b8a87  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x1800b8a8b  mov     edx, 1; ImpersonationLevel
0x1800b8a90  call    cs:__imp_DuplicateToken
0x1800b8a96  test    eax, eax
0x1800b8a98  jnz     short loc_1800B8AB1
0x1800b8a9a  call    cs:__imp_GetLastError
0x1800b8aa0  mov     ebx, eax
0x1800b8aa2  test    eax, eax
0x1800b8aa4  jle     short loc_1800B8A77
0x1800b8aa6  movzx   ebx, ax
0x1800b8aa9  or      ebx, 80070000h
0x1800b8aaf  jmp     short loc_1800B8A77
0x1800b8ab1  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x1800b8ab5  lea     r8, [rbp+IsMember]; IsMember
0x1800b8ab9  mov     [rbp+IsMember], esi
0x1800b8abc  mov     rsi, [rbp+SidToCheck]
0x1800b8ac0  mov     rdx, rsi; SidToCheck
0x1800b8ac3  call    cs:__imp_CheckTokenMembership
0x1800b8ac9  test    eax, eax
0x1800b8acb  jnz     short loc_1800B8AE4
0x1800b8acd  call    cs:__imp_GetLastError
0x1800b8ad3  mov     ebx, eax
0x1800b8ad5  test    eax, eax
0x1800b8ad7  jle     short loc_1800B8B0C
0x1800b8ad9  movzx   ebx, ax
0x1800b8adc  or      ebx, 80070000h
0x1800b8ae2  jmp     short loc_1800B8B0C
0x1800b8ae4  and     dword ptr [rdi+0A78h], 0FFFFFFFEh
0x1800b8aeb  mov     eax, [rbp+IsMember]
0x1800b8aee  and     eax, 1
0x1800b8af1  or      [rdi+0A78h], eax
0x1800b8af7  or      dword ptr [rdi+640h], 4
0x1800b8afe  mov     eax, [rdi+0A78h]
0x1800b8b04  and     eax, 1
0x1800b8b07  mov     [r14], eax
0x1800b8b0a  xor     ebx, ebx
0x1800b8b0c  test    rsi, rsi
0x1800b8b0f  jz      short loc_1800B8B1A
0x1800b8b11  mov     rcx, rsi; Sid
0x1800b8b14  call    cs:__imp_RtlFreeSid
0x1800b8b1a  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x1800b8b1e  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x1800b8b23  mov     eax, ebx
0x1800b8b25  add     rsp, 20h
0x1800b8b29  pop     r14
0x1800b8b2b  pop     rdi
0x1800b8b2c  pop     rsi
0x1800b8b2d  pop     rbx
0x1800b8b2e  pop     rbp
0x1800b8b2f  retn
```

# CUserName::IsAdmin(int *)

- ea: `0x18005aff0`
- end: `0x18005b120`
- name: `?IsAdmin@CUserName@@UEAAJPEAH@Z`
- size: `304`
- prototype: `__int64 __fastcall(CUserName *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003f30`
- `0x1800130a8`
- `0x18001f948`
- `0x18005aff0`

## import_xrefs

- `ntdll!RtlFreeSid` at `0x18005b104`
- `ntdll!RtlFreeSid` at `0x18005b104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b0bd`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005b080`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18005b080`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005b0b3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18005b0b3`

## string_xrefs

- `0x18005b024`: `No token`
- `0x18005b056`: `CUtil::CreateAdminSid failed: 0x%x in %s`

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
0x18005aff0  push    rbp
0x18005aff2  push    rbx
0x18005aff3  push    rsi
0x18005aff4  push    rdi
0x18005aff5  push    r14
0x18005aff7  mov     rbp, rsp
0x18005affa  sub     rsp, 20h
0x18005affe  xor     esi, esi
0x18005b000  mov     r14, rdx
0x18005b003  test    byte ptr [rcx+640h], 4
0x18005b00a  mov     rdi, rcx
0x18005b00d  mov     [rbp+SidToCheck], rsi
0x18005b011  mov     [rbp+DuplicateTokenHandle], rsi
0x18005b015  jnz     loc_18005B0EE
0x18005b01b  cmp     [rcx+638h], rsi
0x18005b022  jnz     short loc_18005B03D
0x18005b024  lea     rdx, aNoToken; "No token"
0x18005b02b  lea     ecx, [rsi+8]; int
0x18005b02e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b033  mov     ebx, 800703F0h
0x18005b038  jmp     loc_18005B10A
0x18005b03d  lea     rcx, [rbp+SidToCheck]; void **
0x18005b041  call    ?CreateAdminSid@CUtils@@SAJPEAPEAX@Z; CUtils::CreateAdminSid(void * *)
0x18005b046  mov     ebx, eax
0x18005b048  test    eax, eax
0x18005b04a  jns     short loc_18005B070
0x18005b04c  lea     r9, aCusernameIsadm; "CUserName::IsAdmin"
0x18005b053  mov     r8d, eax
0x18005b056  lea     rdx, aCutilCreateadm; "CUtil::CreateAdminSid failed: 0x%x in %"...
0x18005b05d  mov     ecx, 8; int
0x18005b062  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005b067  mov     rsi, [rbp+SidToCheck]
0x18005b06b  jmp     loc_18005B0FC
0x18005b070  mov     rcx, [rdi+638h]; ExistingTokenHandle
0x18005b077  lea     r8, [rbp+DuplicateTokenHandle]; DuplicateTokenHandle
0x18005b07b  mov     edx, 1; ImpersonationLevel
0x18005b080  call    cs:__imp_DuplicateToken
0x18005b086  test    eax, eax
0x18005b088  jnz     short loc_18005B0A1
0x18005b08a  call    cs:__imp_GetLastError
0x18005b090  mov     ebx, eax
0x18005b092  test    eax, eax
0x18005b094  jle     short loc_18005B067
0x18005b096  movzx   ebx, ax
0x18005b099  or      ebx, 80070000h
0x18005b09f  jmp     short loc_18005B067
0x18005b0a1  mov     rcx, [rbp+DuplicateTokenHandle]; TokenHandle
0x18005b0a5  lea     r8, [rbp+IsMember]; IsMember
0x18005b0a9  mov     [rbp+IsMember], esi
0x18005b0ac  mov     rsi, [rbp+SidToCheck]
0x18005b0b0  mov     rdx, rsi; SidToCheck
0x18005b0b3  call    cs:__imp_CheckTokenMembership
0x18005b0b9  test    eax, eax
0x18005b0bb  jnz     short loc_18005B0D4
0x18005b0bd  call    cs:__imp_GetLastError
0x18005b0c3  mov     ebx, eax
0x18005b0c5  test    eax, eax
0x18005b0c7  jle     short loc_18005B0FC
0x18005b0c9  movzx   ebx, ax
0x18005b0cc  or      ebx, 80070000h
0x18005b0d2  jmp     short loc_18005B0FC
0x18005b0d4  and     dword ptr [rdi+0A78h], 0FFFFFFFEh
0x18005b0db  mov     eax, [rbp+IsMember]
0x18005b0de  and     eax, 1
0x18005b0e1  or      [rdi+0A78h], eax
0x18005b0e7  or      dword ptr [rdi+640h], 4
0x18005b0ee  mov     eax, [rdi+0A78h]
0x18005b0f4  and     eax, 1
0x18005b0f7  mov     [r14], eax
0x18005b0fa  xor     ebx, ebx
0x18005b0fc  test    rsi, rsi
0x18005b0ff  jz      short loc_18005B10A
0x18005b101  mov     rcx, rsi; Sid
0x18005b104  call    cs:__imp_RtlFreeSid
0x18005b10a  lea     rcx, [rbp+DuplicateTokenHandle]; this
0x18005b10e  call    ??1SmartHANDLE@@QEAA@XZ; SmartHANDLE::~SmartHANDLE(void)
0x18005b113  mov     eax, ebx
0x18005b115  add     rsp, 20h
0x18005b119  pop     r14
0x18005b11b  pop     rdi
0x18005b11c  pop     rsi
0x18005b11d  pop     rbx
0x18005b11e  pop     rbp
0x18005b11f  retn
```

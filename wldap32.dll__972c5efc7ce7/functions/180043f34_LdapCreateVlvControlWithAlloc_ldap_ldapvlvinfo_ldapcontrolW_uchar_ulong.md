# LdapCreateVlvControlWithAlloc(ldap *,ldapvlvinfo *,ldapcontrolW * *,uchar,ulong)

- ea: `0x180043f34`
- end: `0x180044043`
- name: `?LdapCreateVlvControlWithAlloc@@YAKPEAUldap@@PEAUldapvlvinfo@@PEAPEAUldapcontrolW@@EK@Z`
- size: `271`
- prototype: `unsigned int(struct ldap *, struct ldapvlvinfo *, struct ldapcontrolW **, unsigned __int8, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180044b60`
- `0x180044b90`

## callees

- `0x1800037a8`
- `0x18000adb0`
- `0x18000cda0`
- `0x18001ce90`
- `0x1800201e0`
- `0x180043f34`
- `0x18004404c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043fc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180043fc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004400e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044029`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004400e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044029`

## pseudocode

```c
__int64 __fastcall LdapCreateVlvControlWithAlloc(
        struct ldap *a1,
        struct ldapvlvinfo *a2,
        struct ldapcontrolW **a3,
        char a4,
        unsigned int a5)
{
  unsigned __int8 v7; // bp
  __int64 ConnectionPointer; // rax
  _DWORD *v9; // rbx
  struct ldapcontrolW *v10; // rdi
  unsigned int v11; // esi
  struct _RTL_CRITICAL_SECTION *v12; // rcx

  v7 = a4 != 0;
  ConnectionPointer = GetConnectionPointer(a1, a2, a3);
  v9 = (_DWORD *)ConnectionPointer;
  if ( ConnectionPointer && a3 && a2 )
  {
    v10 = (struct ldapcontrolW *)ldapMalloc(32, 1953383244);
    if ( v10 )
    {
      v11 = LdapEncodeVlvControl((struct ldap_connection *)v9, v10, a2, v7, a5);
      if ( v11 )
      {
        ldap_control_freeW(v10);
        v10 = 0;
      }
      *a3 = v10;
    }
    else
    {
      *a3 = 0;
      v11 = 90;
    }
  }
  else
  {
    v11 = 89;
    if ( !ConnectionPointer )
      return v11;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 128));
  --*v9;
  if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 4) != 0 )
    LDAPClientPrint(4, "LDAP deref conn 0x%x, new count = 0x%x\n", (_DWORD)v9, *v9);
  v12 = (struct _RTL_CRITICAL_SECTION *)(v9 + 128);
  if ( *v9 )
  {
    LeaveCriticalSection(v12);
  }
  else
  {
    LeaveCriticalSection(v12);
    DereferenceLdapConnection2((__int64)v9, 1);
  }
  return v11;
}

```

## disassembly

```asm
0x180043f34  push    rbx
0x180043f36  push    rbp
0x180043f37  push    rsi
0x180043f38  push    rdi
0x180043f39  push    r14
0x180043f3b  sub     rsp, 30h
0x180043f3f  test    r9b, r9b
0x180043f42  mov     r14, r8
0x180043f45  mov     rsi, rdx
0x180043f48  setnz   bpl
0x180043f4c  call    GetConnectionPointer
0x180043f51  mov     rbx, rax
0x180043f54  test    rax, rax
0x180043f57  jz      short loc_180043FB3
0x180043f59  test    r14, r14
0x180043f5c  jz      short loc_180043FB3
0x180043f5e  test    rsi, rsi
0x180043f61  jz      short loc_180043FB3
0x180043f63  mov     edx, 746E434Ch
0x180043f68  mov     ecx, 20h ; ' '
0x180043f6d  call    ldapMalloc
0x180043f72  mov     rdi, rax
0x180043f75  test    rax, rax
0x180043f78  jnz     short loc_180043F82
0x180043f7a  mov     [r14], rax
0x180043f7d  lea     esi, [rax+5Ah]
0x180043f80  jmp     short loc_180043FBD
0x180043f82  mov     eax, [rsp+58h+arg_20]
0x180043f89  mov     r9b, bpl; unsigned __int8
0x180043f8c  mov     r8, rsi; struct ldapvlvinfo *
0x180043f8f  mov     [rsp+58h+var_38], eax; unsigned int
0x180043f93  mov     rdx, rdi; struct ldapcontrolW *
0x180043f96  mov     rcx, rbx; struct ldap_connection *
0x180043f99  call    ?LdapEncodeVlvControl@@YAKPEAUldap_connection@@PEAUldapcontrolW@@PEAUldapvlvinfo@@EK@Z; LdapEncodeVlvControl(ldap_connection *,ldapcontrolW *,ldapvlvinfo *,uchar,ulong)
0x180043f9e  mov     esi, eax
0x180043fa0  test    eax, eax
0x180043fa2  jz      short loc_180043FAE
0x180043fa4  mov     rcx, rdi; Control
0x180043fa7  call    ldap_control_freeW
0x180043fac  xor     edi, edi
0x180043fae  mov     [r14], rdi
0x180043fb1  jmp     short loc_180043FBD
0x180043fb3  mov     esi, 59h ; 'Y'
0x180043fb8  test    rbx, rbx
0x180043fbb  jz      short loc_180044035
0x180043fbd  lea     rdi, [rbx+200h]
0x180043fc4  mov     rcx, rdi; lpCriticalSection
0x180043fc7  call    cs:__imp_EnterCriticalSection
0x180043fce  nop     dword ptr [rax+rax+00h]
0x180043fd3  dec     dword ptr [rbx]
0x180043fd5  cmp     cs:g_fTracingOn, 0
0x180043fdc  jz      short loc_180044006
0x180043fde  cmp     cs:g_fProviderEnabled, 0
0x180043fe5  jz      short loc_180044006
0x180043fe7  mov     ecx, 4
0x180043fec  test    byte ptr cs:g_ulTraceFlags, cl
0x180043ff2  jz      short loc_180044006
0x180043ff4  mov     r9d, [rbx]
0x180043ff7  lea     rdx, aLdapDerefConn0; "LDAP deref conn 0x%x, new count = 0x%x"...
0x180043ffe  mov     r8, rbx
0x180044001  call    LDAPClientPrint
0x180044006  cmp     dword ptr [rbx], 0
0x180044009  mov     rcx, rdi; lpCriticalSection
0x18004400c  jnz     short loc_180044029
0x18004400e  call    cs:__imp_LeaveCriticalSection
0x180044015  nop     dword ptr [rax+rax+00h]
0x18004401a  mov     edx, 1
0x18004401f  mov     rcx, rbx
0x180044022  call    DereferenceLdapConnection2
0x180044027  jmp     short loc_180044035
0x180044029  call    cs:__imp_LeaveCriticalSection
0x180044030  nop     dword ptr [rax+rax+00h]
0x180044035  mov     eax, esi
0x180044037  add     rsp, 30h
0x18004403b  pop     r14
0x18004403d  pop     rdi
0x18004403e  pop     rsi
0x18004403f  pop     rbp
0x180044040  pop     rbx
0x180044041  retn
```

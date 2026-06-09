# CRegAccount::SetAccessToRegKey(void *,HKEY__ *,ulong,int)

- ea: `0x180026634`
- end: `0x180026802`
- name: `?SetAccessToRegKey@CRegAccount@@SAJPEAXPEAUHKEY__@@KH@Z`
- size: `462`
- prototype: `static int(void *, HKEY, unsigned int, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180021a70`
- `0x180022c1c`
- `0x18002656c`
- `0x1800395b4`
- `0x180040650`

## callees

- `0x180021730`
- `0x180023a58`
- `0x180026634`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002678b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002678b`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800267a7`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800267a7`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180026705`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180026705`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800266dd`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1800266dd`
- `ADVAPI32!RegGetKeySecurity` at `0x18002669a`
- `ADVAPI32!RegGetKeySecurity` at `0x1800266cc`
- `ADVAPI32!RegGetKeySecurity` at `0x18002669a`
- `ADVAPI32!RegGetKeySecurity` at `0x1800266cc`
- `ADVAPI32!RegSetKeySecurity` at `0x1800267bf`
- `ADVAPI32!RegSetKeySecurity` at `0x1800267bf`

## pseudocode

```c
__int64 __fastcall CRegAccount::SetAccessToRegKey(void *a1, HKEY a2, unsigned int a3, int a4)
{
  void *v4; // rdi
  void *v7; // rax
  unsigned int LastWin32Error; // ebx
  LSTATUS KeySecurity; // eax
  void *v10; // rax
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-40h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+44h] [rbp-3Ch] BYREF
  PACL pDacl; // [rsp+48h] [rbp-38h] BYREF
  PACL v15; // [rsp+50h] [rbp-30h] BYREF
  _BYTE pSecurityDescriptor[40]; // [rsp+58h] [rbp-28h] BYREF
  void *v17; // [rsp+A0h] [rbp+20h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+B8h] [rbp+38h] BYREF

  v17 = a1;
  v15 = 0;
  v4 = 0;
  pDacl = 0;
  if ( !a4 )
    goto LABEL_16;
  cbSecurityDescriptor = 1000;
  v7 = MemAllocClear(0x3E8u);
  v4 = v7;
  if ( !v7 )
  {
LABEL_3:
    LastWin32Error = -2147024882;
    goto LABEL_22;
  }
  KeySecurity = RegGetKeySecurity(a2, 4u, v7, &cbSecurityDescriptor);
  if ( KeySecurity == 122 )
  {
    MemFree(v4);
    v10 = MemAllocClear(cbSecurityDescriptor);
    v4 = v10;
    if ( !v10 )
      goto LABEL_3;
    KeySecurity = RegGetKeySecurity(a2, 4u, v10, &cbSecurityDescriptor);
  }
  if ( KeySecurity )
    goto LABEL_20;
  cbSecurityDescriptor = GetSecurityDescriptorLength(v4);
  if ( !cbSecurityDescriptor || !GetSecurityDescriptorDacl(v4, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
LABEL_9:
    LastWin32Error = GetLastWin32Error();
    goto LABEL_22;
  }
  if ( bDaclPresent && !pDacl )
  {
    LastWin32Error = cbSecurityDescriptor;
    goto LABEL_22;
  }
  LastWin32Error = CRegAccount::DoesAccessExist(pDacl, &v17, 1, a3, &bDaclPresent);
  if ( !LastWin32Error && !bDaclPresent )
  {
LABEL_16:
    LastWin32Error = CRegAccount::AddAccess(&pDacl, &v17, 1, a3, 0, 3, &v15);
    if ( LastWin32Error )
      goto LABEL_22;
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v15, 0) )
    {
      KeySecurity = RegSetKeySecurity(a2, 4u, pSecurityDescriptor);
      if ( !KeySecurity )
        goto LABEL_22;
LABEL_20:
      LastWin32Error = (unsigned __int16)KeySecurity | 0x80070000;
      if ( KeySecurity <= 0 )
        LastWin32Error = KeySecurity;
      goto LABEL_22;
    }
    goto LABEL_9;
  }
LABEL_22:
  MemFree(v15);
  MemFree(v4);
  return LastWin32Error;
}

```

## disassembly

```asm
0x180026634  mov     [rsp-18h+arg_8], rbx
0x180026639  mov     [rsp-18h+arg_10], rsi
0x18002663e  mov     [rsp-18h+arg_0], rcx
0x180026643  push    rbp
0x180026644  push    rdi
0x180026645  push    r14
0x180026647  mov     rbp, rsp
0x18002664a  sub     rsp, 80h
0x180026651  and     [rbp+var_30], 0
0x180026656  xor     edi, edi
0x180026658  and     [rbp+pDacl], 0
0x18002665d  mov     r14d, r8d
0x180026660  mov     rsi, rdx
0x180026663  test    r9d, r9d
0x180026666  jz      loc_180026754
0x18002666c  mov     ecx, 3E8h; unsigned __int64
0x180026671  mov     [rbp+cbSecurityDescriptor], ecx
0x180026674  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180026679  mov     rdi, rax
0x18002667c  test    rax, rax
0x18002667f  jnz     short loc_18002668B
0x180026681  mov     ebx, 8007000Eh
0x180026686  jmp     loc_1800267D7
0x18002668b  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x18002668f  mov     r8, rdi; pSecurityDescriptor
0x180026692  mov     edx, 4; SecurityInformation
0x180026697  mov     rcx, rsi; hKey
0x18002669a  call    cs:__imp_RegGetKeySecurity
0x1800266a0  cmp     eax, 7Ah ; 'z'
0x1800266a3  jnz     short loc_1800266D2
0x1800266a5  mov     rcx, rdi; lpMem
0x1800266a8  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800266ad  mov     ecx, [rbp+cbSecurityDescriptor]; unsigned __int64
0x1800266b0  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x1800266b5  mov     rdi, rax
0x1800266b8  test    rax, rax
0x1800266bb  jz      short loc_180026681
0x1800266bd  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x1800266c1  mov     r8, rax; pSecurityDescriptor
0x1800266c4  mov     edx, 4; SecurityInformation
0x1800266c9  mov     rcx, rsi; hKey
0x1800266cc  call    cs:__imp_RegGetKeySecurity
0x1800266d2  test    eax, eax
0x1800266d4  jnz     loc_1800267C9
0x1800266da  mov     rcx, rdi; pSecurityDescriptor
0x1800266dd  call    cs:__imp_GetSecurityDescriptorLength
0x1800266e3  mov     [rbp+cbSecurityDescriptor], eax
0x1800266e6  test    eax, eax
0x1800266e8  jnz     short loc_1800266F6
0x1800266ea  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x1800266ef  mov     ebx, eax
0x1800266f1  jmp     loc_1800267D7
0x1800266f6  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800266fa  mov     rcx, rdi; pSecurityDescriptor
0x1800266fd  lea     r8, [rbp+pDacl]; pDacl
0x180026701  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180026705  call    cs:__imp_GetSecurityDescriptorDacl
0x18002670b  test    eax, eax
0x18002670d  jz      short loc_1800266EA
0x18002670f  cmp     [rbp+bDaclPresent], 0
0x180026713  mov     rcx, [rbp+pDacl]; pAcl
0x180026717  jz      short loc_180026726
0x180026719  test    rcx, rcx
0x18002671c  jnz     short loc_180026726
0x18002671e  mov     ebx, [rbp+cbSecurityDescriptor]
0x180026721  jmp     loc_1800267D7
0x180026726  lea     rax, [rbp+bDaclPresent]
0x18002672a  mov     r9d, r14d; unsigned int
0x18002672d  mov     r8d, 1; int
0x180026733  mov     [rsp+80h+var_60], rax; int *
0x180026738  lea     rdx, [rbp+arg_0]; void **
0x18002673c  call    ?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z; CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)
0x180026741  mov     ebx, eax
0x180026743  test    eax, eax
0x180026745  jnz     loc_1800267D7
0x18002674b  cmp     [rbp+bDaclPresent], eax
0x18002674e  jnz     loc_1800267D7
0x180026754  lea     rax, [rbp+var_30]
0x180026758  mov     r9d, r14d; unsigned int
0x18002675b  mov     [rsp+80h+var_50], rax; struct _ACL **
0x180026760  lea     rdx, [rbp+arg_0]; void **
0x180026764  mov     [rsp+80h+var_58], 3; char
0x180026769  lea     rcx, [rbp+pDacl]; struct _ACL **
0x18002676d  and     [rsp+80h+var_60], 0
0x180026773  mov     r8d, 1; int
0x180026779  call    ?AddAccess@CRegAccount@@CAJPEAPEAU_ACL@@PEAPEAXHKPEAHE0@Z; CRegAccount::AddAccess(_ACL * *,void * *,int,ulong,int *,uchar,_ACL * *)
0x18002677e  mov     ebx, eax
0x180026780  test    eax, eax
0x180026782  jnz     short loc_1800267D7
0x180026784  lea     edx, [rax+1]; dwRevision
0x180026787  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18002678b  call    cs:__imp_InitializeSecurityDescriptor
0x180026791  test    eax, eax
0x180026793  jz      loc_1800266EA
0x180026799  mov     r8, [rbp+var_30]; pDacl
0x18002679d  lea     edx, [rbx+1]; bDaclPresent
0x1800267a0  xor     r9d, r9d; bDaclDefaulted
0x1800267a3  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800267a7  call    cs:__imp_SetSecurityDescriptorDacl
0x1800267ad  test    eax, eax
0x1800267af  jz      loc_1800266EA
0x1800267b5  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800267b9  mov     rcx, rsi; hKey
0x1800267bc  lea     edx, [rbx+4]; SecurityInformation
0x1800267bf  call    cs:__imp_RegSetKeySecurity
0x1800267c5  test    eax, eax
0x1800267c7  jz      short loc_1800267D7
0x1800267c9  movzx   ebx, ax
0x1800267cc  or      ebx, 80070000h
0x1800267d2  test    eax, eax
0x1800267d4  cmovle  ebx, eax
0x1800267d7  mov     rcx, [rbp+var_30]; lpMem
0x1800267db  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800267e0  mov     rcx, rdi; lpMem
0x1800267e3  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x1800267e8  lea     r11, [rsp+80h+var_s0]
0x1800267f0  mov     eax, ebx
0x1800267f2  mov     rbx, [r11+28h]
0x1800267f6  mov     rsi, [r11+30h]
0x1800267fa  mov     rsp, r11
0x1800267fd  pop     r14
0x1800267ff  pop     rdi
0x180026800  pop     rbp
0x180026801  retn
```

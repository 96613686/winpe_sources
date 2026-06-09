# CNtSecurityDescriptor::DeleteSacl(void)

- ea: `0x18003c7b0`
- end: `0x18003c96a`
- name: `?DeleteSacl@CNtSecurityDescriptor@@QEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(CNtSecurityDescriptor *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180009fd0`
- `0x180013564`
- `0x180014120`
- `0x180023b40`
- `0x1800269d4`
- `0x18003a700`
- `0x18003c7b0`
- `0x180043f2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c849`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtSecurityDescriptor::DeleteSacl(CNtSecurityDescriptor *this)
{
  struct SNtAbsoluteSD *AbsoluteCopy; // rax
  __int64 v3; // rdx
  struct SNtAbsoluteSD *v4; // rdi
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // r9d
  signed int LastError; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _BYTE v15[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( *((_DWORD *)this + 2) || !*(_QWORD *)this )
  {
    v5 = -2147217407;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217407);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 10;
    v8 = 2147749889LL;
LABEL_29:
    WPP_SF_D(v6[2], v7, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v8);
    return v5;
  }
  AbsoluteCopy = CNtSecurityDescriptor::GetAbsoluteCopy(this);
  v4 = AbsoluteCopy;
  if ( !AbsoluteCopy )
  {
    v5 = -2147217402;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217402);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return v5;
    }
    v7 = 11;
    v8 = 2147749894LL;
    goto LABEL_29;
  }
  MakeGuard<void (*)(SNtAbsoluteSD const *),SNtAbsoluteSD *>(v15, v3, AbsoluteCopy);
  if ( (unsigned int)DLSetSecurityDescriptorSacl(*(void **)v4, 0, 0, v9) )
  {
    if ( (unsigned int)CNtSecurityDescriptor::SetFromAbsoluteCopy(this, v4) )
    {
      ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v15);
      return 0;
    }
    v5 = -2147217407;
    CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, -2147217407);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v12 = 13;
    v13 = 2147749889LL;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v5);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    v12 = 12;
    v13 = v5;
  }
  WPP_SF_D(v11[2], v12, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids, v13);
LABEL_23:
  ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>((__int64)v15);
  return v5;
}

```

## disassembly

```asm
0x18003c7b0  mov     [rsp+arg_0], rbx
0x18003c7b5  push    rdi
0x18003c7b6  sub     rsp, 40h
0x18003c7ba  mov     rbx, rcx
0x18003c7bd  cmp     dword ptr [rcx+8], 0
0x18003c7c1  jnz     loc_18003C910
0x18003c7c7  cmp     qword ptr [rcx], 0
0x18003c7cb  jz      loc_18003C910
0x18003c7d1  call    ?GetAbsoluteCopy@CNtSecurityDescriptor@@QEAAPEAUSNtAbsoluteSD@@XZ; CNtSecurityDescriptor::GetAbsoluteCopy(void)
0x18003c7d6  mov     rdi, rax
0x18003c7d9  test    rax, rax
0x18003c7dc  jnz     short loc_18003C82A
0x18003c7de  mov     ebx, 80041006h
0x18003c7e3  mov     edx, ebx; int
0x18003c7e5  lea     rcx, qword_18006A9C0; this
0x18003c7ec  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c7f1  lea     rax, WPP_GLOBAL_Control
0x18003c7f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c7ff  cmp     rcx, rax
0x18003c802  jz      loc_18003C95D
0x18003c808  test    byte ptr [rcx+1Ch], 1
0x18003c80c  jz      loc_18003C95D
0x18003c812  cmp     byte ptr [rcx+19h], 2
0x18003c816  jb      loc_18003C95D
0x18003c81c  lea     edx, [rdi+0Bh]
0x18003c81f  mov     r9d, 80041006h
0x18003c825  jmp     loc_18003C94D
0x18003c82a  mov     r8, rdi
0x18003c82d  lea     rcx, [rsp+48h+var_20]
0x18003c832  call    ??$MakeGuard@P6AXPEBUSNtAbsoluteSD@@@ZPEAU1@@@YA?AV?$ScopeGuardImpl1@P6AXPEBUSNtAbsoluteSD@@@ZPEAU1@@@P6AXPEBUSNtAbsoluteSD@@@ZPEAU1@@Z; MakeGuard<void (*)(SNtAbsoluteSD const *),SNtAbsoluteSD *>(void (*)(SNtAbsoluteSD const *),SNtAbsoluteSD *)
0x18003c837  nop
0x18003c838  xor     r8d, r8d; struct _ACL *
0x18003c83b  xor     edx, edx; int
0x18003c83d  mov     rcx, [rdi]; void *
0x18003c840  call    ?DLSetSecurityDescriptorSacl@@YAHPEAXHPEAU_ACL@@H@Z; DLSetSecurityDescriptorSacl(void *,int,_ACL *,int)
0x18003c845  test    eax, eax
0x18003c847  jnz     short loc_18003C899
0x18003c849  call    cs:__imp_GetLastError
0x18003c84f  mov     ebx, eax
0x18003c851  test    eax, eax
0x18003c853  jle     short loc_18003C85E
0x18003c855  movzx   ebx, ax
0x18003c858  or      ebx, 80070000h
0x18003c85e  test    ebx, ebx
0x18003c860  jns     short loc_18003C870
0x18003c862  mov     edx, ebx; int
0x18003c864  lea     rcx, qword_18006A9C0; this
0x18003c86b  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c870  lea     rax, WPP_GLOBAL_Control
0x18003c877  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c87e  cmp     rcx, rax
0x18003c881  jz      short loc_18003C8F6
0x18003c883  test    byte ptr [rcx+1Ch], 1
0x18003c887  jz      short loc_18003C8F6
0x18003c889  cmp     byte ptr [rcx+19h], 2
0x18003c88d  jb      short loc_18003C8F6
0x18003c88f  mov     edx, 0Ch
0x18003c894  mov     r9d, ebx
0x18003c897  jmp     short loc_18003C8E5
0x18003c899  mov     rdx, rdi; struct SNtAbsoluteSD *
0x18003c89c  mov     rcx, rbx; this
0x18003c89f  call    ?SetFromAbsoluteCopy@CNtSecurityDescriptor@@QEAAHPEAUSNtAbsoluteSD@@@Z; CNtSecurityDescriptor::SetFromAbsoluteCopy(SNtAbsoluteSD *)
0x18003c8a4  test    eax, eax
0x18003c8a6  jnz     short loc_18003C902
0x18003c8a8  mov     ebx, 80041001h
0x18003c8ad  mov     edx, ebx; int
0x18003c8af  lea     rcx, qword_18006A9C0; this
0x18003c8b6  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c8bb  lea     rax, WPP_GLOBAL_Control
0x18003c8c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8c9  cmp     rcx, rax
0x18003c8cc  jz      short loc_18003C8F6
0x18003c8ce  test    byte ptr [rcx+1Ch], 1
0x18003c8d2  jz      short loc_18003C8F6
0x18003c8d4  cmp     byte ptr [rcx+19h], 2
0x18003c8d8  jb      short loc_18003C8F6
0x18003c8da  mov     edx, 0Dh
0x18003c8df  mov     r9d, 80041001h
0x18003c8e5  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003c8ec  mov     rcx, [rcx+10h]
0x18003c8f0  call    WPP_SF_D
0x18003c8f5  nop
0x18003c8f6  lea     rcx, [rsp+48h+var_20]
0x18003c8fb  call    ??1?$ScopeGuardImpl1@P6AXPEBUtagVARIANT@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(void)
0x18003c900  jmp     short loc_18003C95D
0x18003c902  lea     rcx, [rsp+48h+var_20]
0x18003c907  call    ??1?$ScopeGuardImpl1@P6AXPEBUtagVARIANT@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>::~ScopeGuardImpl1<void (*)(tagVARIANT const *),tagVARIANT *>(void)
0x18003c90c  xor     eax, eax
0x18003c90e  jmp     short loc_18003C95F
0x18003c910  mov     ebx, 80041001h
0x18003c915  mov     edx, ebx; int
0x18003c917  lea     rcx, qword_18006A9C0; this
0x18003c91e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003c923  lea     rax, WPP_GLOBAL_Control
0x18003c92a  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c931  cmp     rcx, rax
0x18003c934  jz      short loc_18003C95D
0x18003c936  test    byte ptr [rcx+1Ch], 1
0x18003c93a  jz      short loc_18003C95D
0x18003c93c  cmp     byte ptr [rcx+19h], 2
0x18003c940  jb      short loc_18003C95D
0x18003c942  mov     edx, 0Ah
0x18003c947  mov     r9d, 80041001h
0x18003c94d  lea     r8, WPP_d46c2ce2a264379614ce1d5e696f8ef1_Traceguids
0x18003c954  mov     rcx, [rcx+10h]
0x18003c958  call    WPP_SF_D
0x18003c95d  mov     eax, ebx
0x18003c95f  mov     rbx, [rsp+48h+arg_0]
0x18003c964  add     rsp, 40h
0x18003c968  pop     rdi
0x18003c969  retn
```

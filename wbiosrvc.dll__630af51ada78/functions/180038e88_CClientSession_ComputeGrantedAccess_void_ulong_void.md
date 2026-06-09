# CClientSession::ComputeGrantedAccess(void *,ulong,void *)

- ea: `0x180038e88`
- end: `0x18003900f`
- name: `?ComputeGrantedAccess@CClientSession@@AEAAXPEAXK0@Z`
- size: `391`
- prototype: `void __fastcall(CClientSession *this, void *, char, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ff5c`

## callees

- `0x180038e88`
- `0x1800530c4`
- `0x180069cd4`
- `0x1800702a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f09`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038ef2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038f64`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038ef2`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180038f64`

## pseudocode

```c
void __fastcall CClientSession::ComputeGrantedAccess(CClientSession *this, void *a2, char a3, void *a4)
{
  PPRIVILEGE_SET v8; // rbx
  DWORD v9; // eax
  _BYTE v10[4]; // [rsp+40h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-15h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-11h] BYREF
  WINBOOL AccessStatus; // [rsp+4Ch] [rbp-Dh] BYREF
  void **pExceptionObject; // [rsp+50h] [rbp-9h] BYREF
  const char *v15; // [rsp+58h] [rbp-1h]
  __int64 v16; // [rsp+60h] [rbp+7h]
  PPRIVILEGE_SET PrivilegeSet[9]; // [rsp+68h] [rbp+Fh] BYREF

  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  AccessStatus = 0;
  if ( AccessCheck(
         a4,
         a2,
         0x2000000u,
         (PGENERIC_MAPPING)&GenericMapping,
         0,
         &PrivilegeSetLength,
         &GrantedAccess,
         &AccessStatus)
    || !PrivilegeSetLength
    || GetLastError() != 122 )
  {
    v16 = 0;
    v15 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v10[0] = 0;
  std::vector<unsigned char>::vector<unsigned char>(PrivilegeSet, PrivilegeSetLength, v10);
  v8 = PrivilegeSet[0];
  if ( !AccessCheck(
          a4,
          a2,
          0x2000000u,
          (PGENERIC_MAPPING)&GenericMapping,
          PrivilegeSet[0],
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
  {
    v16 = 0;
    v15 = "bad allocation";
    pExceptionObject = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  v9 = GrantedAccess;
  if ( (a3 & 1) == 0 )
  {
    v9 = GrantedAccess & 0xFFFFFFFE;
    GrantedAccess &= ~1u;
  }
  if ( (a3 & 2) == 0 )
  {
    v9 &= ~2u;
    GrantedAccess = v9;
  }
  *((_DWORD *)this + 40) = v9;
  if ( v8 )
    std::_Deallocate<16>(v8, (char *)PrivilegeSet[2] - (char *)v8);
}

```

## disassembly

```asm
0x180038e88  push    rbp
0x180038e8a  push    rbx
0x180038e8b  push    rsi
0x180038e8c  push    rdi
0x180038e8d  push    r14
0x180038e8f  push    r15
0x180038e91  lea     rbp, [rsp-2Fh]
0x180038e96  sub     rsp, 88h
0x180038e9d  mov     r14, r9
0x180038ea0  mov     edi, r8d
0x180038ea3  mov     r15, rdx
0x180038ea6  mov     rsi, rcx
0x180038ea9  mov     [rbp+57h+var_68], 0
0x180038eb0  mov     [rbp+57h+var_6C], 0
0x180038eb7  mov     [rbp+57h+var_64], 0
0x180038ebe  lea     rax, [rbp+57h+var_64]
0x180038ec2  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x180038ec7  lea     rax, [rbp+57h+var_6C]
0x180038ecb  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180038ed0  lea     rax, [rbp+57h+var_68]
0x180038ed4  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180038ed9  mov     [rsp+0B0h+PrivilegeSet], 0; PrivilegeSet
0x180038ee2  lea     r9, GenericMapping; GenericMapping
0x180038ee9  mov     r8d, 2000000h; DesiredAccess
0x180038eef  mov     rcx, r14; pSecurityDescriptor
0x180038ef2  call    cs:__imp_AccessCheck
0x180038ef8  test    eax, eax
0x180038efa  jnz     loc_180038FE1
0x180038f00  cmp     [rbp+57h+var_68], eax
0x180038f03  jz      loc_180038FE1
0x180038f09  call    cs:__imp_GetLastError
0x180038f0f  cmp     eax, 7Ah ; 'z'
0x180038f12  jnz     loc_180038FE1
0x180038f18  mov     [rbp+57h+var_70], 0
0x180038f1c  mov     edx, [rbp+57h+var_68]
0x180038f1f  lea     r8, [rbp+57h+var_70]
0x180038f23  lea     rcx, [rbp+57h+var_48]
0x180038f27  call    ??$?0V?$allocator@E@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBEAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,uchar const &,std::allocator<uchar> const &)
0x180038f2c  nop
0x180038f2d  lea     rax, [rbp+57h+var_64]
0x180038f31  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x180038f36  lea     rax, [rbp+57h+var_6C]
0x180038f3a  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x180038f3f  lea     rax, [rbp+57h+var_68]
0x180038f43  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x180038f48  mov     rbx, [rbp+57h+var_48]
0x180038f4c  mov     [rsp+0B0h+PrivilegeSet], rbx; PrivilegeSet
0x180038f51  lea     r9, GenericMapping; GenericMapping
0x180038f58  mov     r8d, 2000000h; DesiredAccess
0x180038f5e  mov     rdx, r15; ClientToken
0x180038f61  mov     rcx, r14; pSecurityDescriptor
0x180038f64  call    cs:__imp_AccessCheck
0x180038f6a  test    eax, eax
0x180038f6c  jnz     short loc_180038F9C
0x180038f6e  xorps   xmm0, xmm0
0x180038f71  movups  [rbp+57h+var_58], xmm0
0x180038f75  lea     rax, aBadAllocation; "bad allocation"
0x180038f7c  mov     qword ptr [rbp+57h+var_58], rax
0x180038f80  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180038f87  mov     [rbp+57h+pExceptionObject], rax
0x180038f8b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180038f92  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180038f96  call    _CxxThrowException_0
0x180038f9c  mov     eax, [rbp+57h+var_6C]
0x180038f9f  test    dil, 1
0x180038fa3  jnz     short loc_180038FAB
0x180038fa5  and     eax, 0FFFFFFFEh
0x180038fa8  mov     [rbp+57h+var_6C], eax
0x180038fab  test    dil, 2
0x180038faf  jnz     short loc_180038FB7
0x180038fb1  and     eax, 0FFFFFFFDh
0x180038fb4  mov     [rbp+57h+var_6C], eax
0x180038fb7  mov     [rsi+0A0h], eax
0x180038fbd  test    rbx, rbx
0x180038fc0  jz      short loc_180038FD1
0x180038fc2  mov     rdx, [rbp+57h+var_38]
0x180038fc6  sub     rdx, rbx
0x180038fc9  mov     rcx, rbx
0x180038fcc  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180038fd1  add     rsp, 88h
0x180038fd8  pop     r15
0x180038fda  pop     r14
0x180038fdc  pop     rdi
0x180038fdd  pop     rsi
0x180038fde  pop     rbx
0x180038fdf  pop     rbp
0x180038fe0  retn
0x180038fe1  xorps   xmm0, xmm0
0x180038fe4  movups  [rbp+57h+var_58], xmm0
0x180038fe8  lea     rax, aBadAllocation; "bad allocation"
0x180038fef  mov     qword ptr [rbp+57h+var_58], rax
0x180038ff3  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180038ffa  mov     [rbp+57h+pExceptionObject], rax
0x180038ffe  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180039005  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180039009  call    _CxxThrowException_0
```

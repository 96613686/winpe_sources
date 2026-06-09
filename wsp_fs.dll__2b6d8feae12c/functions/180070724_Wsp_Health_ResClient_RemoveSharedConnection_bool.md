# Wsp::Health::ResClient::RemoveSharedConnection(bool)

- ea: `0x180070724`
- end: `0x180070866`
- name: `?RemoveSharedConnection@ResClient@Health@Wsp@@QEAAX_N@Z`
- size: `322`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006ff60`

## callees

- `0x18006f6e0`
- `0x18006f70c`
- `0x18006f8a8`
- `0x18006fe74`
- `0x180070584`
- `0x180070648`
- `0x18007067c`
- `0x180070724`
- `0x180070a40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800707fd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800707fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800707aa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800707aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070820`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070820`

## string_xrefs

- `0x1800707b0`: `RemoveSharedConnection::Grabbed the Lock`
- `0x180070803`: `RemoveSharedConnection::Released the Lock`

## pseudocode

```c
void __fastcall Wsp::Health::ResClient::RemoveSharedConnection(RTL_SRWLOCK *this)
{
  bool v1; // zf
  PSID v3[2]; // [rsp+20h] [rbp-20h] BYREF
  void *v4[2]; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  wchar_t *v6; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *v7; // [rsp+88h] [rbp+48h] BYREF

  v1 = this[43].Ptr == 0;
  v4[0] = &Wsp::Health::Token::`vftable';
  v3[0] = &Wsp::Health::Sid::`vftable';
  v4[1] = 0;
  v3[1] = 0;
  hMem = 0;
  v6 = 0;
  if ( !v1 )
  {
    if ( Wsp::Health::ResClient::GetUserSid((struct _SID **)this, (struct Wsp::Health::Sid *)v3, v4)
      && !Wsp::Health::Sid::ToString(v3, (wchar_t **)&hMem) )
    {
      AcquireSRWLockExclusive(this + 41);
      v7 = L"RemoveSharedConnection::Grabbed the Lock";
      Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v7);
      if ( (unsigned int)CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Find(&this[22], hMem, &v6) && v6 )
      {
        Wsp::Health::RefBase::Release((Wsp::Health::RefBase *)v6);
        CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove((__int64)&this[22], (__int64)hMem);
      }
      ReleaseSRWLockExclusive(this + 41);
      v6 = L"RemoveSharedConnection::Released the Lock";
      Wsp::Health::ResClient::LogComment((const wchar_t *const *)&v6);
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
  }
  Wsp::Health::Sid::Clear((Wsp::Health::Sid *)v3);
  Wsp::Health::Token::Clear((Wsp::Health::Token *)v4);
  v3[0] = &Wsp::Health::Sid::`vftable';
  Wsp::Health::Sid::Clear((Wsp::Health::Sid *)v3);
  v4[0] = &Wsp::Health::Token::`vftable';
  Wsp::Health::Token::Clear((Wsp::Health::Token *)v4);
}

```

## disassembly

```asm
0x180070724  push    rbp
0x180070726  push    rbx
0x180070727  push    rdi
0x180070728  push    r14
0x18007072a  push    r15
0x18007072c  mov     rbp, rsp
0x18007072f  sub     rsp, 40h
0x180070733  cmp     qword ptr [rcx+158h], 0
0x18007073b  lea     r14, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180070742  lea     r15, ??_7Sid@Health@Wsp@@6B@; const Wsp::Health::Sid::`vftable'
0x180070749  mov     [rbp+var_10], r14
0x18007074d  mov     [rbp+var_20], r15
0x180070751  mov     rbx, rcx
0x180070754  mov     [rbp+var_8], 0
0x18007075c  mov     [rbp+var_18], 0
0x180070764  mov     [rbp+hMem], 0
0x18007076c  mov     [rbp+arg_10], 0
0x180070774  jz      loc_18007082E
0x18007077a  lea     r8, [rbp+var_10]; struct Wsp::Health::Token *
0x18007077e  lea     rdx, [rbp+var_20]; struct Wsp::Health::Sid *
0x180070782  call    ?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z; Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)
0x180070787  test    al, al
0x180070789  jz      loc_180070817
0x18007078f  lea     rdx, [rbp+hMem]; wchar_t **
0x180070793  lea     rcx, [rbp+var_20]; this
0x180070797  call    ?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z; Wsp::Health::Sid::ToString(wchar_t * *)
0x18007079c  test    eax, eax
0x18007079e  jnz     short loc_180070817
0x1800707a0  lea     rdi, [rbx+148h]
0x1800707a7  mov     rcx, rdi; SRWLock
0x1800707aa  call    cs:__imp_AcquireSRWLockExclusive
0x1800707b0  lea     rax, aRemovesharedco_0; "RemoveSharedConnection::Grabbed the Loc"...
0x1800707b7  lea     rcx, [rbp+arg_18]; wchar_t **
0x1800707bb  mov     [rbp+arg_18], rax
0x1800707bf  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x1800707c4  mov     rdx, [rbp+hMem]
0x1800707c8  lea     r8, [rbp+arg_10]
0x1800707cc  lea     rcx, [rbx+0B0h]
0x1800707d3  call    ?Find@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_WPEAPEAVCHealthConnection@Health@Wsp@@@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Find(wchar_t *,Wsp::Health::CHealthConnection * *)
0x1800707d8  test    eax, eax
0x1800707da  jz      short loc_1800707FA
0x1800707dc  mov     rcx, [rbp+arg_10]; this
0x1800707e0  test    rcx, rcx
0x1800707e3  jz      short loc_1800707FA
0x1800707e5  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x1800707ea  mov     rdx, [rbp+hMem]
0x1800707ee  lea     rcx, [rbx+0B0h]
0x1800707f5  call    ?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)
0x1800707fa  mov     rcx, rdi; SRWLock
0x1800707fd  call    cs:__imp_ReleaseSRWLockExclusive
0x180070803  lea     rax, aRemovesharedco; "RemoveSharedConnection::Released the Lo"...
0x18007080a  lea     rcx, [rbp+arg_10]; wchar_t **
0x18007080e  mov     [rbp+arg_10], rax
0x180070812  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180070817  mov     rcx, [rbp+hMem]; hMem
0x18007081b  test    rcx, rcx
0x18007081e  jz      short loc_18007082E
0x180070820  call    cs:__imp_LocalFree
0x180070826  mov     [rbp+hMem], 0
0x18007082e  lea     rcx, [rbp+var_20]; this
0x180070832  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x180070837  lea     rcx, [rbp+var_10]; this
0x18007083b  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180070840  lea     rcx, [rbp+var_20]; this
0x180070844  mov     [rbp+var_20], r15
0x180070848  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x18007084d  lea     rcx, [rbp+var_10]; this
0x180070851  mov     [rbp+var_10], r14
0x180070855  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007085a  add     rsp, 40h
0x18007085e  pop     r15
0x180070860  pop     r14
0x180070862  pop     rdi
0x180070863  pop     rbx
0x180070864  pop     rbp
0x180070865  retn
```

# Wsp::Health::ResClient::RemoveSharedConnection(bool)

- ea: `0x180079abc`
- end: `0x180079bfe`
- name: `?RemoveSharedConnection@ResClient@Health@Wsp@@QEAAX_N@Z`
- size: `322`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800792a0`
- `0x180079c90`

## callees

- `0x180077864`
- `0x180078700`
- `0x18007872c`
- `0x1800788c8`
- `0x1800791b8`
- `0x1800798c4`
- `0x180079924`
- `0x180079abc`
- `0x180079e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180079b42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180079b42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180079b95`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180079b95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079bb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180079bb8`

## string_xrefs

- `0x180079b48`: `RemoveSharedConnection::Grabbed the Lock`
- `0x180079b9b`: `RemoveSharedConnection::Released the Lock`

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
0x180079abc  push    rbp
0x180079abe  push    rbx
0x180079abf  push    rdi
0x180079ac0  push    r14
0x180079ac2  push    r15
0x180079ac4  mov     rbp, rsp
0x180079ac7  sub     rsp, 40h
0x180079acb  cmp     qword ptr [rcx+158h], 0
0x180079ad3  lea     r14, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x180079ada  lea     r15, ??_7Sid@Health@Wsp@@6B@; const Wsp::Health::Sid::`vftable'
0x180079ae1  mov     [rbp+var_10], r14
0x180079ae5  mov     [rbp+var_20], r15
0x180079ae9  mov     rbx, rcx
0x180079aec  mov     [rbp+var_8], 0
0x180079af4  mov     [rbp+var_18], 0
0x180079afc  mov     [rbp+hMem], 0
0x180079b04  mov     [rbp+arg_10], 0
0x180079b0c  jz      loc_180079BC6
0x180079b12  lea     r8, [rbp+var_10]; struct Wsp::Health::Token *
0x180079b16  lea     rdx, [rbp+var_20]; struct Wsp::Health::Sid *
0x180079b1a  call    ?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z; Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)
0x180079b1f  test    al, al
0x180079b21  jz      loc_180079BAF
0x180079b27  lea     rdx, [rbp+hMem]; wchar_t **
0x180079b2b  lea     rcx, [rbp+var_20]; this
0x180079b2f  call    ?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z; Wsp::Health::Sid::ToString(wchar_t * *)
0x180079b34  test    eax, eax
0x180079b36  jnz     short loc_180079BAF
0x180079b38  lea     rdi, [rbx+148h]
0x180079b3f  mov     rcx, rdi; SRWLock
0x180079b42  call    cs:__imp_AcquireSRWLockExclusive
0x180079b48  lea     rax, aRemovesharedco_0; "RemoveSharedConnection::Grabbed the Loc"...
0x180079b4f  lea     rcx, [rbp+arg_18]; wchar_t **
0x180079b53  mov     [rbp+arg_18], rax
0x180079b57  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180079b5c  mov     rdx, [rbp+hMem]
0x180079b60  lea     r8, [rbp+arg_10]
0x180079b64  lea     rcx, [rbx+0B0h]
0x180079b6b  call    ?Find@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_WPEAPEAVCHealthConnection@Health@Wsp@@@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Find(wchar_t *,Wsp::Health::CHealthConnection * *)
0x180079b70  test    eax, eax
0x180079b72  jz      short loc_180079B92
0x180079b74  mov     rcx, [rbp+arg_10]; this
0x180079b78  test    rcx, rcx
0x180079b7b  jz      short loc_180079B92
0x180079b7d  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x180079b82  mov     rdx, [rbp+hMem]
0x180079b86  lea     rcx, [rbx+0B0h]
0x180079b8d  call    ?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)
0x180079b92  mov     rcx, rdi; SRWLock
0x180079b95  call    cs:__imp_ReleaseSRWLockExclusive
0x180079b9b  lea     rax, aRemovesharedco; "RemoveSharedConnection::Released the Lo"...
0x180079ba2  lea     rcx, [rbp+arg_10]; wchar_t **
0x180079ba6  mov     [rbp+arg_10], rax
0x180079baa  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180079baf  mov     rcx, [rbp+hMem]; hMem
0x180079bb3  test    rcx, rcx
0x180079bb6  jz      short loc_180079BC6
0x180079bb8  call    cs:__imp_LocalFree
0x180079bbe  mov     [rbp+hMem], 0
0x180079bc6  lea     rcx, [rbp+var_20]; this
0x180079bca  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x180079bcf  lea     rcx, [rbp+var_10]; this
0x180079bd3  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079bd8  lea     rcx, [rbp+var_20]; this
0x180079bdc  mov     [rbp+var_20], r15
0x180079be0  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x180079be5  lea     rcx, [rbp+var_10]; this
0x180079be9  mov     [rbp+var_10], r14
0x180079bed  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180079bf2  add     rsp, 40h
0x180079bf6  pop     r15
0x180079bf8  pop     r14
0x180079bfa  pop     rdi
0x180079bfb  pop     rbx
0x180079bfc  pop     rbp
0x180079bfd  retn
```

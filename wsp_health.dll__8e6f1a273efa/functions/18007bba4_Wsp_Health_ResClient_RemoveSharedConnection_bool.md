# Wsp::Health::ResClient::RemoveSharedConnection(bool)

- ea: `0x18007bba4`
- end: `0x18007bcfd`
- name: `?RemoveSharedConnection@ResClient@Health@Wsp@@QEAAX_N@Z`
- size: `345`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this, bool)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007b2a0`
- `0x18007bda4`

## callees

- `0x180079720`
- `0x18007a650`
- `0x18007a67c`
- `0x18007a828`
- `0x18007b1a8`
- `0x18007b990`
- `0x18007b9f4`
- `0x18007bba4`
- `0x18007bf20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bc2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bc2e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bc87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bc87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bcb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007bcb0`

## string_xrefs

- `0x18007bc3a`: `RemoveSharedConnection::Grabbed the Lock`
- `0x18007bc93`: `RemoveSharedConnection::Released the Lock`

## pseudocode

```c
void __fastcall Wsp::Health::ResClient::RemoveSharedConnection(RTL_SRWLOCK *this)
{
  bool v1; // zf
  struct _SID *v3[2]; // [rsp+20h] [rbp-20h] BYREF
  void *v4[2]; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  wchar_t *v6; // [rsp+80h] [rbp+40h] BYREF
  wchar_t *v7; // [rsp+88h] [rbp+48h] BYREF

  v1 = this[43].Ptr == 0;
  v4[0] = &Wsp::Health::Token::`vftable';
  v3[0] = (struct _SID *)&Wsp::Health::Sid::`vftable';
  v4[1] = 0;
  v3[1] = 0;
  hMem = 0;
  v6 = 0;
  if ( !v1 )
  {
    if ( Wsp::Health::ResClient::GetUserSid((const struct _SID **)this, (struct Wsp::Health::Sid *)v3, v4)
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
  v3[0] = (struct _SID *)&Wsp::Health::Sid::`vftable';
  Wsp::Health::Sid::Clear((Wsp::Health::Sid *)v3);
  v4[0] = &Wsp::Health::Token::`vftable';
  Wsp::Health::Token::Clear((Wsp::Health::Token *)v4);
}

```

## disassembly

```asm
0x18007bba4  push    rbp
0x18007bba6  push    rbx
0x18007bba7  push    rdi
0x18007bba8  push    r14
0x18007bbaa  push    r15
0x18007bbac  mov     rbp, rsp
0x18007bbaf  sub     rsp, 40h
0x18007bbb3  cmp     qword ptr [rcx+158h], 0
0x18007bbbb  lea     r14, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x18007bbc2  lea     r15, ??_7Sid@Health@Wsp@@6B@; const Wsp::Health::Sid::`vftable'
0x18007bbc9  mov     [rbp+var_10], r14
0x18007bbcd  mov     [rbp+var_20], r15
0x18007bbd1  mov     rbx, rcx
0x18007bbd4  mov     [rbp+var_8], 0
0x18007bbdc  mov     [rbp+var_18], 0
0x18007bbe4  mov     [rbp+hMem], 0
0x18007bbec  mov     [rbp+arg_10], 0
0x18007bbf4  jz      loc_18007BCC4
0x18007bbfa  lea     r8, [rbp+var_10]; struct Wsp::Health::Token *
0x18007bbfe  lea     rdx, [rbp+var_20]; struct Wsp::Health::Sid *
0x18007bc02  call    ?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z; Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)
0x18007bc07  test    al, al
0x18007bc09  jz      loc_18007BCA7
0x18007bc0f  lea     rdx, [rbp+hMem]; wchar_t **
0x18007bc13  lea     rcx, [rbp+var_20]; this
0x18007bc17  call    ?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z; Wsp::Health::Sid::ToString(wchar_t * *)
0x18007bc1c  test    eax, eax
0x18007bc1e  jnz     loc_18007BCA7
0x18007bc24  lea     rdi, [rbx+148h]
0x18007bc2b  mov     rcx, rdi; SRWLock
0x18007bc2e  call    cs:__imp_AcquireSRWLockExclusive
0x18007bc35  nop     dword ptr [rax+rax+00h]
0x18007bc3a  lea     rax, aRemovesharedco_0; "RemoveSharedConnection::Grabbed the Loc"...
0x18007bc41  lea     rcx, [rbp+arg_18]; wchar_t **
0x18007bc45  mov     [rbp+arg_18], rax
0x18007bc49  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x18007bc4e  mov     rdx, [rbp+hMem]
0x18007bc52  lea     r8, [rbp+arg_10]
0x18007bc56  lea     rcx, [rbx+0B0h]
0x18007bc5d  call    ?Find@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_WPEAPEAVCHealthConnection@Health@Wsp@@@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Find(wchar_t *,Wsp::Health::CHealthConnection * *)
0x18007bc62  test    eax, eax
0x18007bc64  jz      short loc_18007BC84
0x18007bc66  mov     rcx, [rbp+arg_10]; this
0x18007bc6a  test    rcx, rcx
0x18007bc6d  jz      short loc_18007BC84
0x18007bc6f  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x18007bc74  mov     rdx, [rbp+hMem]
0x18007bc78  lea     rcx, [rbx+0B0h]
0x18007bc7f  call    ?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)
0x18007bc84  mov     rcx, rdi; SRWLock
0x18007bc87  call    cs:__imp_ReleaseSRWLockExclusive
0x18007bc8e  nop     dword ptr [rax+rax+00h]
0x18007bc93  lea     rax, aRemovesharedco; "RemoveSharedConnection::Released the Lo"...
0x18007bc9a  lea     rcx, [rbp+arg_10]; wchar_t **
0x18007bc9e  mov     [rbp+arg_10], rax
0x18007bca2  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x18007bca7  mov     rcx, [rbp+hMem]; hMem
0x18007bcab  test    rcx, rcx
0x18007bcae  jz      short loc_18007BCC4
0x18007bcb0  call    cs:__imp_LocalFree
0x18007bcb7  nop     dword ptr [rax+rax+00h]
0x18007bcbc  mov     [rbp+hMem], 0
0x18007bcc4  lea     rcx, [rbp+var_20]; this
0x18007bcc8  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x18007bccd  lea     rcx, [rbp+var_10]; this
0x18007bcd1  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007bcd6  lea     rcx, [rbp+var_20]; this
0x18007bcda  mov     [rbp+var_20], r15
0x18007bcde  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x18007bce3  lea     rcx, [rbp+var_10]; this
0x18007bce7  mov     [rbp+var_10], r14
0x18007bceb  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007bcf0  add     rsp, 40h
0x18007bcf4  pop     r15
0x18007bcf6  pop     r14
0x18007bcf8  pop     rdi
0x18007bcf9  pop     rbx
0x18007bcfa  pop     rbp
0x18007bcfb  retn
```

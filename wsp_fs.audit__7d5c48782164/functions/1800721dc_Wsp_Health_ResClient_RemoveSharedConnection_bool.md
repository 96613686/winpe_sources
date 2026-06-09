# Wsp::Health::ResClient::RemoveSharedConnection(bool)

- ea: `0x1800721dc`
- end: `0x180072335`
- name: `?RemoveSharedConnection@ResClient@Health@Wsp@@QEAAX_N@Z`
- size: `345`
- prototype: `void __fastcall(Wsp::Health::ResClient *__hidden this, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180071930`

## callees

- `0x180071030`
- `0x18007105c`
- `0x180071208`
- `0x180071830`
- `0x180072020`
- `0x1800720e4`
- `0x18007211c`
- `0x1800721dc`
- `0x180072530`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800722bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800722bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072266`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180072266`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800722e8`

## string_xrefs

- `0x180072272`: `RemoveSharedConnection::Grabbed the Lock`
- `0x1800722cb`: `RemoveSharedConnection::Released the Lock`

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
0x1800721dc  push    rbp
0x1800721de  push    rbx
0x1800721df  push    rdi
0x1800721e0  push    r14
0x1800721e2  push    r15
0x1800721e4  mov     rbp, rsp
0x1800721e7  sub     rsp, 40h
0x1800721eb  cmp     qword ptr [rcx+158h], 0
0x1800721f3  lea     r14, ??_7Token@Health@Wsp@@6B@; const Wsp::Health::Token::`vftable'
0x1800721fa  lea     r15, ??_7Sid@Health@Wsp@@6B@; const Wsp::Health::Sid::`vftable'
0x180072201  mov     [rbp+var_10], r14
0x180072205  mov     [rbp+var_20], r15
0x180072209  mov     rbx, rcx
0x18007220c  mov     [rbp+var_8], 0
0x180072214  mov     [rbp+var_18], 0
0x18007221c  mov     [rbp+hMem], 0
0x180072224  mov     [rbp+arg_10], 0
0x18007222c  jz      loc_1800722FC
0x180072232  lea     r8, [rbp+var_10]; struct Wsp::Health::Token *
0x180072236  lea     rdx, [rbp+var_20]; struct Wsp::Health::Sid *
0x18007223a  call    ?GetUserSid@ResClient@Health@Wsp@@AEBA_NPEAVSid@23@PEAVToken@23@@Z; Wsp::Health::ResClient::GetUserSid(Wsp::Health::Sid *,Wsp::Health::Token *)
0x18007223f  test    al, al
0x180072241  jz      loc_1800722DF
0x180072247  lea     rdx, [rbp+hMem]; wchar_t **
0x18007224b  lea     rcx, [rbp+var_20]; this
0x18007224f  call    ?ToString@Sid@Health@Wsp@@QEAAKPEAPEA_W@Z; Wsp::Health::Sid::ToString(wchar_t * *)
0x180072254  test    eax, eax
0x180072256  jnz     loc_1800722DF
0x18007225c  lea     rdi, [rbx+148h]
0x180072263  mov     rcx, rdi; SRWLock
0x180072266  call    cs:__imp_AcquireSRWLockExclusive
0x18007226d  nop     dword ptr [rax+rax+00h]
0x180072272  lea     rax, aRemovesharedco_0; "RemoveSharedConnection::Grabbed the Loc"...
0x180072279  lea     rcx, [rbp+arg_18]; wchar_t **
0x18007227d  mov     [rbp+arg_18], rax
0x180072281  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x180072286  mov     rdx, [rbp+hMem]
0x18007228a  lea     r8, [rbp+arg_10]
0x18007228e  lea     rcx, [rbx+0B0h]
0x180072295  call    ?Find@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_WPEAPEAVCHealthConnection@Health@Wsp@@@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Find(wchar_t *,Wsp::Health::CHealthConnection * *)
0x18007229a  test    eax, eax
0x18007229c  jz      short loc_1800722BC
0x18007229e  mov     rcx, [rbp+arg_10]; this
0x1800722a2  test    rcx, rcx
0x1800722a5  jz      short loc_1800722BC
0x1800722a7  call    ?Release@RefBase@Health@Wsp@@QEAAKXZ; Wsp::Health::RefBase::Release(void)
0x1800722ac  mov     rdx, [rbp+hMem]
0x1800722b0  lea     rcx, [rbx+0B0h]
0x1800722b7  call    ?Remove@?$CMapBase@PEA_WPEAVCHealthConnection@Health@Wsp@@@@QEAAHPEA_W@Z; CMapBase<wchar_t *,Wsp::Health::CHealthConnection *>::Remove(wchar_t *)
0x1800722bc  mov     rcx, rdi; SRWLock
0x1800722bf  call    cs:__imp_ReleaseSRWLockExclusive
0x1800722c6  nop     dword ptr [rax+rax+00h]
0x1800722cb  lea     rax, aRemovesharedco; "RemoveSharedConnection::Released the Lo"...
0x1800722d2  lea     rcx, [rbp+arg_10]; wchar_t **
0x1800722d6  mov     [rbp+arg_10], rax
0x1800722da  call    ?LogComment@ResClient@Health@Wsp@@SAXAEBQEB_W@Z; Wsp::Health::ResClient::LogComment(wchar_t const * const &)
0x1800722df  mov     rcx, [rbp+hMem]; hMem
0x1800722e3  test    rcx, rcx
0x1800722e6  jz      short loc_1800722FC
0x1800722e8  call    cs:__imp_LocalFree
0x1800722ef  nop     dword ptr [rax+rax+00h]
0x1800722f4  mov     [rbp+hMem], 0
0x1800722fc  lea     rcx, [rbp+var_20]; this
0x180072300  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x180072305  lea     rcx, [rbp+var_10]; this
0x180072309  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x18007230e  lea     rcx, [rbp+var_20]; this
0x180072312  mov     [rbp+var_20], r15
0x180072316  call    ?Clear@Sid@Health@Wsp@@UEAAXXZ; Wsp::Health::Sid::Clear(void)
0x18007231b  lea     rcx, [rbp+var_10]; this
0x18007231f  mov     [rbp+var_10], r14
0x180072323  call    ?Clear@Token@Health@Wsp@@QEAAXXZ; Wsp::Health::Token::Clear(void)
0x180072328  add     rsp, 40h
0x18007232c  pop     r15
0x18007232e  pop     r14
0x180072330  pop     rdi
0x180072331  pop     rbx
0x180072332  pop     rbp
0x180072333  retn
```

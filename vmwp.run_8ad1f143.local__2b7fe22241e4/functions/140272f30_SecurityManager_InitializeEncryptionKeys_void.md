# SecurityManager::InitializeEncryptionKeys(void)

- ea: `0x140272f30`
- end: `0x140273240`
- name: `?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ`
- size: `784`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1402740a0`

## callees

- `0x140034f18`
- `0x1400544a8`
- `0x1400545d0`
- `0x14005e804`
- `0x140081798`
- `0x1400b42d0`
- `0x1400d6a94`
- `0x140132960`
- `0x140271d20`
- `0x140272580`
- `0x140272f30`
- `0x1402c2010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x140273196`
- `bcrypt!BCryptGenRandom` at `0x140273196`
- `vid!VidInitEncryptionKeys` at `0x140272f89`
- `vid!VidInitEncryptionKeys` at `0x140272f89`

## string_xrefs

- `0x14027305d`: `/configuration/security/keys/encrypted_static_key`
- `0x1402730ae`: `/configuration/security/keys/encrypted_static_key`
- `0x140272f6d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140272fa1`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140273009`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402730cf`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027313e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402731b3`: `onecore\vm\worker\security\securitymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall SecurityManager::InitializeEncryptionKeys(SecurityManager *this)
{
  const char *v3; // r9
  PUCHAR *v4; // rdi
  unsigned int v5; // esi
  int v6; // eax
  int v7; // eax
  unsigned int v8; // esi
  int v9; // eax
  unsigned int v10; // ebx
  NTSTATUS v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // [rsp+20h] [rbp-68h]
  unsigned int v14; // [rsp+20h] [rbp-68h]
  char *v15[2]; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-48h] BYREF
  PUCHAR pbBuffer[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v18; // [rsp+58h] [rbp-30h]
  void *v19[2]; // [rsp+60h] [rbp-28h] BYREF
  __int64 v20; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( *((_BYTE *)this + 192) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6BE,
      (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
      (const char *)0x8007139FLL,
      v13);
    return 2147947423LL;
  }
  if ( !(unsigned int)VidInitEncryptionKeys(*((_QWORD *)this + 12)) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6C1,
             (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
             v3);
  *((_BYTE *)this + 192) = 1;
  if ( *((_DWORD *)this + 31) )
  {
    v4 = (PUCHAR *)((char *)this + 320);
    if ( *((_QWORD *)this + 41) == *((_QWORD *)this + 40) )
    {
      *(_OWORD *)v15 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v15, *((_QWORD *)this + 2), 0);
      v5 = (unsigned int)v15[1];
      if ( SLODWORD(v15[1]) < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6CC,
          (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
          (const char *)LODWORD(v15[1]),
          v13);
        VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
        return v5;
      }
      *(_OWORD *)pbBuffer = 0;
      v18 = 0;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(pbBuffer, 32);
      v16 = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, unsigned int *))(**((_QWORD **)this + 2) + 80LL))(
             *((_QWORD *)this + 2),
             L"/configuration/security/keys/encrypted_static_key",
             &v16);
      if ( (unsigned int)RepositoryKeyFound(v6) )
      {
        *(_OWORD *)v19 = 0;
        v20 = 0;
        std::vector<enum gsl::byte>::vector<enum gsl::byte>(v19, v16);
        v7 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void *, _QWORD))(**((_QWORD **)this + 2) + 88LL))(
               *((_QWORD *)this + 2),
               L"/configuration/security/keys/encrypted_static_key",
               v19[0],
               (unsigned int)(LODWORD(v19[1]) - LODWORD(v19[0])));
        v8 = v7;
        if ( v7 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6D9,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v7,
            v13);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v8;
        }
        v9 = SecurityManager::DecryptData(
               this,
               v19[0],
               LODWORD(v19[1]) - LODWORD(v19[0]),
               pbBuffer[0],
               LODWORD(pbBuffer[1]) - LODWORD(pbBuffer[0]));
        v10 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6DF,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v9,
            v14);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v10;
        }
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v19);
      }
      else
      {
        v11 = BCryptGenRandom(0, pbBuffer[0], LODWORD(pbBuffer[1]) - LODWORD(pbBuffer[0]), 2u);
        v12 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6EA,
            (unsigned int)"onecore\\vm\\worker\\security\\securitymanager.cpp",
            (const char *)(unsigned int)v11,
            v13);
          std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
          VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
          return v12;
        }
      }
      if ( v4 != pbBuffer )
        std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(v4, pbBuffer[0], pbBuffer[1] - pbBuffer[0]);
      std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(pbBuffer);
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v15);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140272f30  mov     [rsp+arg_8], rbx
0x140272f35  mov     [rsp+arg_10], rsi
0x140272f3a  push    rdi
0x140272f3b  sub     rsp, 80h
0x140272f42  mov     rax, cs:__security_cookie
0x140272f49  xor     rax, rsp
0x140272f4c  mov     [rsp+88h+var_10], rax
0x140272f51  mov     rbx, rcx
0x140272f54  cmp     byte ptr [rcx+0C0h], 0
0x140272f5b  jz      short loc_140272F85
0x140272f5d  mov     rcx, [rsp+88h]; this
0x140272f65  mov     ebx, 8007139Fh
0x140272f6a  mov     r9d, ebx; char *
0x140272f6d  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140272f74  mov     edx, 6BEh; void *
0x140272f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140272f7e  mov     eax, ebx
0x140272f80  jmp     loc_14027321D
0x140272f85  mov     rcx, [rcx+60h]
0x140272f89  call    cs:__imp_VidInitEncryptionKeys
0x140272f90  nop     dword ptr [rax+rax+00h]
0x140272f95  test    eax, eax
0x140272f97  jnz     short loc_140272FB7
0x140272f99  mov     rcx, [rsp+88h]; this
0x140272fa1  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140272fa8  mov     edx, 6C1h; void *
0x140272fad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140272fb2  jmp     loc_14027321D
0x140272fb7  mov     byte ptr [rbx+0C0h], 1
0x140272fbe  cmp     dword ptr [rbx+7Ch], 0
0x140272fc2  jz      loc_14027321B
0x140272fc8  lea     rdi, [rbx+140h]
0x140272fcf  mov     rax, [rdi+8]
0x140272fd3  cmp     rax, [rdi]
0x140272fd6  jnz     loc_140273213
0x140272fdc  xorps   xmm0, xmm0
0x140272fdf  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x140272fe4  xor     r8d, r8d
0x140272fe7  mov     rdx, [rbx+10h]
0x140272feb  lea     rcx, [rsp+88h+var_58]
0x140272ff0  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140272ff5  nop
0x140272ff6  mov     esi, dword ptr [rsp+88h+var_58+8]
0x140272ffa  test    esi, esi
0x140272ffc  jns     short loc_14027302C
0x140272ffe  mov     rcx, [rsp+88h]; this
0x140273006  mov     r9d, esi; char *
0x140273009  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273010  mov     edx, 6CCh; void *
0x140273015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027301a  nop
0x14027301b  lea     rcx, [rsp+88h+var_58]; this
0x140273020  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273025  mov     eax, esi
0x140273027  jmp     loc_14027321D
0x14027302c  xorps   xmm0, xmm0
0x14027302f  xor     eax, eax
0x140273031  movups  xmmword ptr [rsp+88h+pbBuffer], xmm0
0x140273036  mov     [rsp+88h+var_30], rax
0x14027303b  lea     edx, [rax+20h]
0x14027303e  lea     rcx, [rsp+88h+pbBuffer]
0x140273043  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140273048  nop
0x140273049  mov     [rsp+88h+var_48], 0
0x140273051  mov     rcx, [rbx+10h]
0x140273055  mov     rax, [rcx]
0x140273058  lea     r8, [rsp+88h+var_48]
0x14027305d  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x140273064  mov     rax, [rax+50h]
0x140273068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027306d  mov     ecx, eax; int
0x14027306f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x140273074  test    eax, eax
0x140273076  jz      loc_140273183
0x14027307c  xorps   xmm0, xmm0
0x14027307f  xor     eax, eax
0x140273081  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x140273086  mov     [rsp+88h+var_18], rax
0x14027308b  mov     edx, [rsp+88h+var_48]
0x14027308f  lea     rcx, [rsp+88h+var_28]
0x140273094  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140273099  nop
0x14027309a  mov     rcx, [rbx+10h]
0x14027309e  mov     r8, [rsp+88h+var_28]
0x1402730a3  mov     rax, [rcx]
0x1402730a6  mov     r9d, dword ptr [rsp+88h+var_28+8]
0x1402730ab  sub     r9d, r8d
0x1402730ae  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x1402730b5  mov     rax, [rax+58h]
0x1402730b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402730be  mov     esi, eax
0x1402730c0  test    eax, eax
0x1402730c2  jns     short loc_140273108
0x1402730c4  mov     rcx, [rsp+88h]; this
0x1402730cc  mov     r9d, eax; char *
0x1402730cf  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402730d6  mov     edx, 6D9h; void *
0x1402730db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402730e0  nop
0x1402730e1  lea     rcx, [rsp+88h+var_28]
0x1402730e6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402730eb  nop
0x1402730ec  lea     rcx, [rsp+88h+pbBuffer]
0x1402730f1  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402730f6  nop
0x1402730f7  lea     rcx, [rsp+88h+var_58]; this
0x1402730fc  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273101  mov     eax, esi
0x140273103  jmp     loc_14027321D
0x140273108  mov     r9, [rsp+88h+pbBuffer]; void *
0x14027310d  mov     rdx, [rsp+88h+var_28]; void *
0x140273112  mov     eax, dword ptr [rsp+88h+pbBuffer+8]
0x140273116  sub     eax, r9d
0x140273119  mov     r8d, dword ptr [rsp+88h+var_28+8]
0x14027311e  sub     r8d, edx; unsigned int
0x140273121  mov     [rsp+88h+var_68], eax; int
0x140273125  mov     rcx, rbx; this
0x140273128  call    ?DecryptData@SecurityManager@@UEAAJPEAXI0I@Z; SecurityManager::DecryptData(void *,uint,void *,uint)
0x14027312d  mov     ebx, eax
0x14027312f  test    eax, eax
0x140273131  jns     short loc_140273177
0x140273133  mov     rcx, [rsp+88h]; this
0x14027313b  mov     r9d, eax; char *
0x14027313e  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x140273145  mov     edx, 6DFh; void *
0x14027314a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027314f  nop
0x140273150  lea     rcx, [rsp+88h+var_28]
0x140273155  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027315a  nop
0x14027315b  lea     rcx, [rsp+88h+pbBuffer]
0x140273160  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273165  nop
0x140273166  lea     rcx, [rsp+88h+var_58]; this
0x14027316b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273170  mov     eax, ebx
0x140273172  jmp     loc_14027321D
0x140273177  lea     rcx, [rsp+88h+var_28]
0x14027317c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273181  jmp     short loc_1402731DE
0x140273183  mov     rdx, [rsp+88h+pbBuffer]; pbBuffer
0x140273188  mov     r8d, dword ptr [rsp+88h+pbBuffer+8]
0x14027318d  sub     r8d, edx; cbBuffer
0x140273190  xor     ecx, ecx; hAlgorithm
0x140273192  lea     r9d, [rcx+2]; dwFlags
0x140273196  call    cs:__imp_BCryptGenRandom
0x14027319d  nop     dword ptr [rax+rax+00h]
0x1402731a2  mov     ebx, eax
0x1402731a4  test    eax, eax
0x1402731a6  jns     short loc_1402731DE
0x1402731a8  mov     rcx, [rsp+88h]; this
0x1402731b0  mov     r9d, eax; char *
0x1402731b3  lea     r8, aOnecoreVmWorke_116; "onecore\\vm\\worker\\security\\security"...
0x1402731ba  mov     edx, 6EAh; void *
0x1402731bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402731c4  nop
0x1402731c5  lea     rcx, [rsp+88h+pbBuffer]
0x1402731ca  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402731cf  nop
0x1402731d0  lea     rcx, [rsp+88h+var_58]; this
0x1402731d5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402731da  mov     eax, ebx
0x1402731dc  jmp     short loc_14027321D
0x1402731de  lea     rax, [rsp+88h+pbBuffer]
0x1402731e3  cmp     rdi, rax
0x1402731e6  jz      short loc_1402731FE
0x1402731e8  mov     rdx, [rsp+88h+pbBuffer]
0x1402731ed  mov     r8, [rsp+88h+pbBuffer+8]
0x1402731f2  sub     r8, rdx
0x1402731f5  mov     rcx, rdi
0x1402731f8  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1402731fd  nop
0x1402731fe  lea     rcx, [rsp+88h+pbBuffer]
0x140273203  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140273208  nop
0x140273209  lea     rcx, [rsp+88h+var_58]; this
0x14027320e  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140273213  jmp     short loc_14027321B
0x140273215  mov     eax, [rsp+88h+var_48]
0x140273219  jmp     short loc_14027321D
0x14027321b  xor     eax, eax
0x14027321d  mov     rcx, [rsp+88h+var_10]
0x140273222  xor     rcx, rsp; StackCookie
0x140273225  call    __security_check_cookie
0x14027322a  lea     r11, [rsp+88h+var_8]
0x140273232  mov     rbx, [r11+18h]
0x140273236  mov     rsi, [r11+20h]
0x14027323a  mov     rsp, r11
0x14027323d  pop     rdi
0x14027323e  retn
```

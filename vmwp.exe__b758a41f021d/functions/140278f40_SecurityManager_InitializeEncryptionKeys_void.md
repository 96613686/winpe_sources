# SecurityManager::InitializeEncryptionKeys(void)

- ea: `0x140278f40`
- end: `0x140279250`
- name: `?InitializeEncryptionKeys@SecurityManager@@UEAAJXZ`
- size: `784`
- prototype: `__int64 __fastcall(SecurityManager *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14027a0b0`

## callees

- `0x14004b838`
- `0x140053de8`
- `0x140053f10`
- `0x1400691b4`
- `0x14006d540`
- `0x1400927e8`
- `0x1400c5bf4`
- `0x14011ea40`
- `0x140277bd0`
- `0x140278450`
- `0x140278f40`
- `0x1402cb010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1402791a6`
- `bcrypt!BCryptGenRandom` at `0x1402791a6`
- `vid!VidInitEncryptionKeys` at `0x140278f99`
- `vid!VidInitEncryptionKeys` at `0x140278f99`

## string_xrefs

- `0x14027906d`: `/configuration/security/keys/encrypted_static_key`
- `0x1402790be`: `/configuration/security/keys/encrypted_static_key`
- `0x140278f7d`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140278fb1`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x140279019`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402790df`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x14027914e`: `onecore\vm\worker\security\securitymanager.cpp`
- `0x1402791c3`: `onecore\vm\worker\security\securitymanager.cpp`

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
0x140278f40  mov     [rsp+arg_8], rbx
0x140278f45  mov     [rsp+arg_10], rsi
0x140278f4a  push    rdi
0x140278f4b  sub     rsp, 80h
0x140278f52  mov     rax, cs:__security_cookie
0x140278f59  xor     rax, rsp
0x140278f5c  mov     [rsp+88h+var_10], rax
0x140278f61  mov     rbx, rcx
0x140278f64  cmp     byte ptr [rcx+0C0h], 0
0x140278f6b  jz      short loc_140278F95
0x140278f6d  mov     rcx, [rsp+88h]; this
0x140278f75  mov     ebx, 8007139Fh
0x140278f7a  mov     r9d, ebx; char *
0x140278f7d  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140278f84  mov     edx, 6BEh; void *
0x140278f89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140278f8e  mov     eax, ebx
0x140278f90  jmp     loc_14027922D
0x140278f95  mov     rcx, [rcx+60h]
0x140278f99  call    cs:__imp_VidInitEncryptionKeys
0x140278fa0  nop     dword ptr [rax+rax+00h]
0x140278fa5  test    eax, eax
0x140278fa7  jnz     short loc_140278FC7
0x140278fa9  mov     rcx, [rsp+88h]; this
0x140278fb1  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140278fb8  mov     edx, 6C1h; void *
0x140278fbd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140278fc2  jmp     loc_14027922D
0x140278fc7  mov     byte ptr [rbx+0C0h], 1
0x140278fce  cmp     dword ptr [rbx+7Ch], 0
0x140278fd2  jz      loc_14027922B
0x140278fd8  lea     rdi, [rbx+140h]
0x140278fdf  mov     rax, [rdi+8]
0x140278fe3  cmp     rax, [rdi]
0x140278fe6  jnz     loc_140279223
0x140278fec  xorps   xmm0, xmm0
0x140278fef  movups  xmmword ptr [rsp+88h+var_58], xmm0
0x140278ff4  xor     r8d, r8d
0x140278ff7  mov     rdx, [rbx+10h]
0x140278ffb  lea     rcx, [rsp+88h+var_58]
0x140279000  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140279005  nop
0x140279006  mov     esi, dword ptr [rsp+88h+var_58+8]
0x14027900a  test    esi, esi
0x14027900c  jns     short loc_14027903C
0x14027900e  mov     rcx, [rsp+88h]; this
0x140279016  mov     r9d, esi; char *
0x140279019  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279020  mov     edx, 6CCh; void *
0x140279025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027902a  nop
0x14027902b  lea     rcx, [rsp+88h+var_58]; this
0x140279030  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279035  mov     eax, esi
0x140279037  jmp     loc_14027922D
0x14027903c  xorps   xmm0, xmm0
0x14027903f  xor     eax, eax
0x140279041  movups  xmmword ptr [rsp+88h+pbBuffer], xmm0
0x140279046  mov     [rsp+88h+var_30], rax
0x14027904b  lea     edx, [rax+20h]
0x14027904e  lea     rcx, [rsp+88h+pbBuffer]
0x140279053  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140279058  nop
0x140279059  mov     [rsp+88h+var_48], 0
0x140279061  mov     rcx, [rbx+10h]
0x140279065  mov     rax, [rcx]
0x140279068  lea     r8, [rsp+88h+var_48]
0x14027906d  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x140279074  mov     rax, [rax+50h]
0x140279078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027907d  mov     ecx, eax; int
0x14027907f  call    ?RepositoryKeyFound@@YAHJ@Z; RepositoryKeyFound(long)
0x140279084  test    eax, eax
0x140279086  jz      loc_140279193
0x14027908c  xorps   xmm0, xmm0
0x14027908f  xor     eax, eax
0x140279091  movups  xmmword ptr [rsp+88h+var_28], xmm0
0x140279096  mov     [rsp+88h+var_18], rax
0x14027909b  mov     edx, [rsp+88h+var_48]
0x14027909f  lea     rcx, [rsp+88h+var_28]
0x1402790a4  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x1402790a9  nop
0x1402790aa  mov     rcx, [rbx+10h]
0x1402790ae  mov     r8, [rsp+88h+var_28]
0x1402790b3  mov     rax, [rcx]
0x1402790b6  mov     r9d, dword ptr [rsp+88h+var_28+8]
0x1402790bb  sub     r9d, r8d
0x1402790be  lea     rdx, ?SECURITY_SETTING_ENCRYPTED_STATIC_KEY@@3QBGB; "/configuration/security/keys/encrypted_"...
0x1402790c5  mov     rax, [rax+58h]
0x1402790c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402790ce  mov     esi, eax
0x1402790d0  test    eax, eax
0x1402790d2  jns     short loc_140279118
0x1402790d4  mov     rcx, [rsp+88h]; this
0x1402790dc  mov     r9d, eax; char *
0x1402790df  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1402790e6  mov     edx, 6D9h; void *
0x1402790eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402790f0  nop
0x1402790f1  lea     rcx, [rsp+88h+var_28]
0x1402790f6  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402790fb  nop
0x1402790fc  lea     rcx, [rsp+88h+pbBuffer]
0x140279101  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140279106  nop
0x140279107  lea     rcx, [rsp+88h+var_58]; this
0x14027910c  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279111  mov     eax, esi
0x140279113  jmp     loc_14027922D
0x140279118  mov     r9, [rsp+88h+pbBuffer]; void *
0x14027911d  mov     rdx, [rsp+88h+var_28]; void *
0x140279122  mov     eax, dword ptr [rsp+88h+pbBuffer+8]
0x140279126  sub     eax, r9d
0x140279129  mov     r8d, dword ptr [rsp+88h+var_28+8]
0x14027912e  sub     r8d, edx; unsigned int
0x140279131  mov     [rsp+88h+var_68], eax; int
0x140279135  mov     rcx, rbx; this
0x140279138  call    ?DecryptData@SecurityManager@@UEAAJPEAXI0I@Z; SecurityManager::DecryptData(void *,uint,void *,uint)
0x14027913d  mov     ebx, eax
0x14027913f  test    eax, eax
0x140279141  jns     short loc_140279187
0x140279143  mov     rcx, [rsp+88h]; this
0x14027914b  mov     r9d, eax; char *
0x14027914e  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x140279155  mov     edx, 6DFh; void *
0x14027915a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14027915f  nop
0x140279160  lea     rcx, [rsp+88h+var_28]
0x140279165  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x14027916a  nop
0x14027916b  lea     rcx, [rsp+88h+pbBuffer]
0x140279170  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140279175  nop
0x140279176  lea     rcx, [rsp+88h+var_58]; this
0x14027917b  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279180  mov     eax, ebx
0x140279182  jmp     loc_14027922D
0x140279187  lea     rcx, [rsp+88h+var_28]
0x14027918c  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140279191  jmp     short loc_1402791EE
0x140279193  mov     rdx, [rsp+88h+pbBuffer]; pbBuffer
0x140279198  mov     r8d, dword ptr [rsp+88h+pbBuffer+8]
0x14027919d  sub     r8d, edx; cbBuffer
0x1402791a0  xor     ecx, ecx; hAlgorithm
0x1402791a2  lea     r9d, [rcx+2]; dwFlags
0x1402791a6  call    cs:__imp_BCryptGenRandom
0x1402791ad  nop     dword ptr [rax+rax+00h]
0x1402791b2  mov     ebx, eax
0x1402791b4  test    eax, eax
0x1402791b6  jns     short loc_1402791EE
0x1402791b8  mov     rcx, [rsp+88h]; this
0x1402791c0  mov     r9d, eax; char *
0x1402791c3  lea     r8, aOnecoreVmWorke_117; "onecore\\vm\\worker\\security\\security"...
0x1402791ca  mov     edx, 6EAh; void *
0x1402791cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1402791d4  nop
0x1402791d5  lea     rcx, [rsp+88h+pbBuffer]
0x1402791da  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x1402791df  nop
0x1402791e0  lea     rcx, [rsp+88h+var_58]; this
0x1402791e5  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402791ea  mov     eax, ebx
0x1402791ec  jmp     short loc_14027922D
0x1402791ee  lea     rax, [rsp+88h+pbBuffer]
0x1402791f3  cmp     rdi, rax
0x1402791f6  jz      short loc_14027920E
0x1402791f8  mov     rdx, [rsp+88h+pbBuffer]
0x1402791fd  mov     r8, [rsp+88h+pbBuffer+8]
0x140279202  sub     r8, rdx
0x140279205  mov     rcx, rdi
0x140279208  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x14027920d  nop
0x14027920e  lea     rcx, [rsp+88h+pbBuffer]
0x140279213  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140279218  nop
0x140279219  lea     rcx, [rsp+88h+var_58]; this
0x14027921e  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x140279223  jmp     short loc_14027922B
0x140279225  mov     eax, [rsp+88h+var_48]
0x140279229  jmp     short loc_14027922D
0x14027922b  xor     eax, eax
0x14027922d  mov     rcx, [rsp+88h+var_10]
0x140279232  xor     rcx, rsp; StackCookie
0x140279235  call    __security_check_cookie
0x14027923a  lea     r11, [rsp+88h+var_8]
0x140279242  mov     rbx, [r11+18h]
0x140279246  mov     rsi, [r11+20h]
0x14027924a  mov     rsp, r11
0x14027924d  pop     rdi
0x14027924e  retn
```

# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x180009b1c`
- end: `0x180009d84`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `616`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007da0`
- `0x180008680`

## callees

- `0x180008d30`
- `0x180008e40`
- `0x180009b1c`
- `0x18001e240`
- `0x18001fb70`
- `0x1800269c0`
- `0x18002c9a8`
- `0x18002d3e0`
- `0x18002da34`
- `0x18002ff08`
- `0x180039680`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009bae`
- `msvcrt!_wcsicmp` at `0x180009bdc`
- `msvcrt!_wcsicmp` at `0x180009bae`
- `msvcrt!_wcsicmp` at `0x180009bdc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d67`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009d67`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b59`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009b59`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall User::UpdateEntry(
        User::UserEntry **this,
        const struct _bstr_t *a2,
        const struct _bstr_t *a3,
        const struct _bstr_t *a4,
        enum _SID_NAME_USE a5,
        void *a6)
{
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  const wchar_t **v11; // rcx
  const wchar_t **v12; // rdx
  const wchar_t **v13; // rcx
  const wchar_t **v14; // rdx
  char v15; // bl
  _QWORD *v16; // rcx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  unsigned __int64 v21; // rbp
  const unsigned __int16 *v22; // r8
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rbx
  const unsigned __int16 *v25; // r8
  bool v26; // r8
  unsigned __int16 *v27[7]; // [rsp+20h] [rbp-38h] BYREF
  char v28; // [rsp+60h] [rbp+8h] BYREF

  if ( *this )
  {
    v10 = User::s_cs;
    v27[1] = (unsigned __int16 *)User::s_cs;
    EnterCriticalSection(User::s_cs);
    if ( a6 && !*((_QWORD *)*this + 4) )
      User::UserEntry::CopySid(*this, a6);
    if ( (unsigned int)(*((_DWORD *)*this + 10) - 4) > 1
      && ((v11 = *(const wchar_t ***)a2) != 0
       && *v11
       && (v12 = (const wchar_t **)*((_QWORD *)*this + 2)) != 0
       && *v12
       && _wcsicmp(*v11, *v12)
       || (v13 = *(const wchar_t ***)a3) != 0
       && *v13
       && (v14 = (const wchar_t **)*((_QWORD *)*this + 3)) != 0
       && *v14
       && _wcsicmp(*v13, *v14)) )
    {
      _bstr_t::operator=((char *)*this + 8, 0);
      _bstr_t::operator=((char *)*this + 16, 0);
      _bstr_t::operator=((char *)*this + 24, 0);
      User::UpdateEntry((User *)this);
    }
    else
    {
      v15 = 0;
      if ( *(_QWORD *)a2 )
      {
        if ( **(_QWORD **)a2 )
        {
          v16 = (_QWORD *)((char *)*this + 16);
          if ( !*v16 || !*(_QWORD *)*v16 )
          {
            v15 = 1;
            _bstr_t::operator=(v16, a2);
          }
        }
      }
      if ( *(_QWORD *)a3 )
      {
        if ( **(_QWORD **)a3 )
        {
          v17 = (_QWORD *)((char *)*this + 24);
          if ( !*v17 || !*(_QWORD *)*v17 )
          {
            v15 = 1;
            _bstr_t::operator=(v17, a3);
          }
        }
      }
      if ( !*(_QWORD *)a4 || !**(_QWORD **)a4 || (v18 = (_QWORD *)((char *)*this + 8), *v18) && *(_QWORD *)*v18 )
      {
        if ( v15 )
        {
          v19 = _bstr_t::length(a2) + 1;
          v20 = _bstr_t::length(a3) + v19;
          ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v27, v20);
          v21 = v20 + 1LL;
          if ( *(_QWORD *)a3 )
            v22 = **(const unsigned __int16 ***)a3;
          else
            v22 = 0;
          v23 = v20 + 1LL;
          v24 = v27[0];
          StringCchCopyW(v27[0], v23, v22);
          StringCchCatW(v24, v21, L"\\");
          if ( *(_QWORD *)a2 )
            v25 = **(const unsigned __int16 ***)a2;
          else
            v25 = 0;
          StringCchCatW(v24, v21, v25);
          _bstr_t::_bstr_t((_bstr_t *)&v28, v24, v26);
          _bstr_t::operator=((char *)*this + 8, &v28);
          _bstr_t::_Free((_bstr_t *)&v28);
          SysFreeString(0);
        }
      }
      else
      {
        _bstr_t::operator=(v18, a4);
      }
      if ( a5 != SidTypeUnknown )
        *((_DWORD *)*this + 10) = a5;
    }
    LeaveCriticalSection(v10);
  }
}

```

## disassembly

```asm
0x180009b1c  mov     [rsp+arg_8], rbx
0x180009b21  mov     [rsp+arg_10], rbp
0x180009b26  push    rsi
0x180009b27  push    rdi
0x180009b28  push    r12
0x180009b2a  push    r14
0x180009b2c  push    r15
0x180009b2e  sub     rsp, 30h
0x180009b32  mov     rbp, r9
0x180009b35  mov     r15, r8
0x180009b38  mov     r14, rdx
0x180009b3b  mov     rsi, rcx
0x180009b3e  xor     r12d, r12d
0x180009b41  cmp     [rcx], r12
0x180009b44  jz      loc_180009D6D
0x180009b4a  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180009b51  mov     [rsp+58h+var_30], rdi
0x180009b56  mov     rcx, rdi; lpCriticalSection
0x180009b59  call    cs:__imp_EnterCriticalSection
0x180009b5f  nop
0x180009b60  mov     rdx, [rsp+58h+arg_28]; void *
0x180009b68  test    rdx, rdx
0x180009b6b  jz      short loc_180009B7B
0x180009b6d  mov     rcx, [rsi]; this
0x180009b70  cmp     [rcx+20h], r12
0x180009b74  jnz     short loc_180009B7B
0x180009b76  call    ?CopySid@UserEntry@User@@QEAAXPEAX@Z; User::UserEntry::CopySid(void *)
0x180009b7b  mov     rdx, [rsi]
0x180009b7e  mov     eax, [rdx+28h]
0x180009b81  sub     eax, 4
0x180009b84  cmp     eax, 1
0x180009b87  jbe     loc_180009C1D
0x180009b8d  mov     rcx, [r14]
0x180009b90  test    rcx, rcx
0x180009b93  jz      short loc_180009BB8
0x180009b95  cmp     [rcx], r12
0x180009b98  jz      short loc_180009BB8
0x180009b9a  mov     rdx, [rdx+10h]
0x180009b9e  test    rdx, rdx
0x180009ba1  jz      short loc_180009BB8
0x180009ba3  cmp     [rdx], r12
0x180009ba6  jz      short loc_180009BB8
0x180009ba8  mov     rdx, [rdx]; String2
0x180009bab  mov     rcx, [rcx]; String1
0x180009bae  call    cs:__imp__wcsicmp
0x180009bb4  test    eax, eax
0x180009bb6  jnz     short loc_180009BE6
0x180009bb8  mov     rcx, [r15]
0x180009bbb  test    rcx, rcx
0x180009bbe  jz      short loc_180009C1D
0x180009bc0  cmp     [rcx], r12
0x180009bc3  jz      short loc_180009C1D
0x180009bc5  mov     rax, [rsi]
0x180009bc8  mov     rdx, [rax+18h]
0x180009bcc  test    rdx, rdx
0x180009bcf  jz      short loc_180009C1D
0x180009bd1  cmp     [rdx], r12
0x180009bd4  jz      short loc_180009C1D
0x180009bd6  mov     rdx, [rdx]; String2
0x180009bd9  mov     rcx, [rcx]; String1
0x180009bdc  call    cs:__imp__wcsicmp
0x180009be2  test    eax, eax
0x180009be4  jz      short loc_180009C1D
0x180009be6  mov     rcx, [rsi]
0x180009be9  add     rcx, 8
0x180009bed  xor     edx, edx
0x180009bef  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180009bf4  mov     rcx, [rsi]
0x180009bf7  add     rcx, 10h
0x180009bfb  xor     edx, edx
0x180009bfd  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180009c02  mov     rcx, [rsi]
0x180009c05  add     rcx, 18h
0x180009c09  xor     edx, edx
0x180009c0b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180009c10  mov     rcx, rsi; this
0x180009c13  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180009c18  jmp     loc_180009D64
0x180009c1d  mov     bl, r12b
0x180009c20  mov     rax, [r14]
0x180009c23  test    rax, rax
0x180009c26  jz      short loc_180009C4B
0x180009c28  cmp     [rax], r12
0x180009c2b  jz      short loc_180009C4B
0x180009c2d  mov     rcx, [rsi]
0x180009c30  add     rcx, 10h
0x180009c34  mov     rax, [rcx]
0x180009c37  test    rax, rax
0x180009c3a  jz      short loc_180009C41
0x180009c3c  cmp     [rax], r12
0x180009c3f  jnz     short loc_180009C4B
0x180009c41  mov     bl, 1
0x180009c43  mov     rdx, r14
0x180009c46  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180009c4b  mov     rax, [r15]
0x180009c4e  test    rax, rax
0x180009c51  jz      short loc_180009C76
0x180009c53  cmp     [rax], r12
0x180009c56  jz      short loc_180009C76
0x180009c58  mov     rcx, [rsi]
0x180009c5b  add     rcx, 18h
0x180009c5f  mov     rax, [rcx]
0x180009c62  test    rax, rax
0x180009c65  jz      short loc_180009C6C
0x180009c67  cmp     [rax], r12
0x180009c6a  jnz     short loc_180009C76
0x180009c6c  mov     bl, 1
0x180009c6e  mov     rdx, r15
0x180009c71  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180009c76  mov     rax, [rbp+0]
0x180009c7a  test    rax, rax
0x180009c7d  jz      short loc_180009CA5
0x180009c7f  cmp     [rax], r12
0x180009c82  jz      short loc_180009CA5
0x180009c84  mov     rcx, [rsi]
0x180009c87  add     rcx, 8
0x180009c8b  mov     rax, [rcx]
0x180009c8e  test    rax, rax
0x180009c91  jz      short loc_180009C98
0x180009c93  cmp     [rax], r12
0x180009c96  jnz     short loc_180009CA5
0x180009c98  mov     rdx, rbp
0x180009c9b  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180009ca0  jmp     loc_180009D52
0x180009ca5  test    bl, bl
0x180009ca7  jz      loc_180009D52
0x180009cad  mov     rcx, r14; this
0x180009cb0  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180009cb5  lea     ebx, [rax+1]
0x180009cb8  mov     rcx, r15; this
0x180009cbb  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180009cc0  add     ebx, eax
0x180009cc2  mov     edx, ebx; int
0x180009cc4  lea     rcx, [rsp+58h+var_38]; this
0x180009cc9  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180009cce  nop
0x180009ccf  mov     ebp, ebx
0x180009cd1  inc     rbp
0x180009cd4  mov     r8, [r15]
0x180009cd7  test    r8, r8
0x180009cda  jz      short loc_180009CE1
0x180009cdc  mov     r8, [r8]
0x180009cdf  jmp     short loc_180009CE4
0x180009ce1  mov     r8, r12; unsigned __int16 *
0x180009ce4  mov     rdx, rbp; unsigned __int64
0x180009ce7  mov     rbx, [rsp+58h+var_38]
0x180009cec  mov     rcx, rbx; unsigned __int16 *
0x180009cef  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009cf4  lea     r8, asc_180077260; "\\"
0x180009cfb  mov     rdx, rbp; unsigned __int64
0x180009cfe  mov     rcx, rbx; unsigned __int16 *
0x180009d01  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009d06  mov     r8, [r14]
0x180009d09  test    r8, r8
0x180009d0c  jz      short loc_180009D13
0x180009d0e  mov     r8, [r8]
0x180009d11  jmp     short loc_180009D16
0x180009d13  mov     r8, r12; unsigned __int16 *
0x180009d16  mov     rdx, rbp; unsigned __int64
0x180009d19  mov     rcx, rbx; unsigned __int16 *
0x180009d1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009d21  mov     rdx, rbx; unsigned __int16 *
0x180009d24  lea     rcx, [rsp+58h+arg_0]; this
0x180009d29  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180009d2e  mov     rcx, [rsi]
0x180009d31  add     rcx, 8
0x180009d35  lea     rdx, [rsp+58h+arg_0]
0x180009d3a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180009d3f  lea     rcx, [rsp+58h+arg_0]; this
0x180009d44  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x180009d49  nop
0x180009d4a  xor     ecx, ecx; bstrString
0x180009d4c  call    cs:__imp_SysFreeString
0x180009d52  mov     ecx, [rsp+58h+arg_20]
0x180009d59  cmp     ecx, 8
0x180009d5c  jz      short loc_180009D64
0x180009d5e  mov     rax, [rsi]
0x180009d61  mov     [rax+28h], ecx
0x180009d64  mov     rcx, rdi; lpCriticalSection
0x180009d67  call    cs:__imp_LeaveCriticalSection
0x180009d6d  mov     rbx, [rsp+58h+arg_8]
0x180009d72  mov     rbp, [rsp+58h+arg_10]
0x180009d77  add     rsp, 30h
0x180009d7b  pop     r15
0x180009d7d  pop     r14
0x180009d7f  pop     r12
0x180009d81  pop     rdi
0x180009d82  pop     rsi
0x180009d83  retn
```

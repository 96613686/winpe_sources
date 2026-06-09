# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x180003b3c`
- end: `0x180003da4`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `616`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018d00`
- `0x180019168`
- `0x180019a10`

## callees

- `0x1800031a0`
- `0x180003af0`
- `0x180003b3c`
- `0x180003dac`
- `0x180003ec0`
- `0x180003ef0`
- `0x180004e50`
- `0x180004eec`
- `0x180004f28`
- `0x1800188e4`
- `0x18001af08`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003bce`
- `msvcrt!_wcsicmp` at `0x180003bfc`
- `msvcrt!_wcsicmp` at `0x180003bce`
- `msvcrt!_wcsicmp` at `0x180003bfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003b79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003d87`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d6c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall User::UpdateEntry(
        void ***this,
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
  _bstr_t *v16; // rcx
  _bstr_t *v17; // rcx
  _bstr_t *v18; // rcx
  unsigned int v19; // ebx
  UINT v20; // ebx
  unsigned __int64 v21; // rbp
  unsigned __int16 *v22; // r8
  unsigned __int64 v23; // rdx
  unsigned __int16 *v24; // rbx
  const unsigned __int16 *v25; // r8
  unsigned __int16 *v26[7]; // [rsp+20h] [rbp-38h] BYREF
  char v27; // [rsp+60h] [rbp+8h] BYREF

  if ( *this )
  {
    v10 = User::s_cs;
    v26[1] = (unsigned __int16 *)User::s_cs;
    EnterCriticalSection(User::s_cs);
    if ( a6 && !(*this)[4] )
      User::UserEntry::CopySid(*this, a6);
    if ( (unsigned int)(*((_DWORD *)*this + 10) - 4) > 1
      && ((v11 = *(const wchar_t ***)a2) != 0
       && *v11
       && (v12 = (const wchar_t **)(*this)[2]) != 0
       && *v12
       && _wcsicmp(*v11, *v12)
       || (v13 = *(const wchar_t ***)a3) != 0
       && *v13
       && (v14 = (const wchar_t **)(*this)[3]) != 0
       && *v14
       && _wcsicmp(*v13, *v14)) )
    {
      _bstr_t::operator=(*this + 1, 0);
      _bstr_t::operator=(*this + 2, 0);
      _bstr_t::operator=(*this + 3, 0);
      User::UpdateEntry((User *)this);
    }
    else
    {
      v15 = 0;
      if ( *(_QWORD *)a2 )
      {
        if ( **(_QWORD **)a2 )
        {
          v16 = (_bstr_t *)(*this + 2);
          if ( !*(_QWORD *)v16 || !**(_QWORD **)v16 )
          {
            v15 = 1;
            _bstr_t::operator=(v16, (__int64)a2);
          }
        }
      }
      if ( *(_QWORD *)a3 )
      {
        if ( **(_QWORD **)a3 )
        {
          v17 = (_bstr_t *)(*this + 3);
          if ( !*(_QWORD *)v17 || !**(_QWORD **)v17 )
          {
            v15 = 1;
            _bstr_t::operator=(v17, (__int64)a3);
          }
        }
      }
      if ( !*(_QWORD *)a4 || !**(_QWORD **)a4 || (v18 = (_bstr_t *)(*this + 1), *(_QWORD *)v18) && **(_QWORD **)v18 )
      {
        if ( v15 )
        {
          v19 = _bstr_t::length(a2) + 1;
          v20 = _bstr_t::length(a3) + v19;
          ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)v26, v20);
          v21 = v20 + 1LL;
          if ( *(_QWORD *)a3 )
            v22 = **(unsigned __int16 ***)a3;
          else
            v22 = 0;
          v23 = v20 + 1LL;
          v24 = v26[0];
          StringCchCopyW(v26[0], v23, v22);
          StringCchCatW(v24, v21, L"\\");
          if ( *(_QWORD *)a2 )
            v25 = **(const unsigned __int16 ***)a2;
          else
            v25 = 0;
          StringCchCatW(v24, v21, v25);
          _bstr_t::_bstr_t((_bstr_t *)&v27, v24);
          _bstr_t::operator=((_bstr_t *)(*this + 1), (__int64)&v27);
          _bstr_t::~_bstr_t((_bstr_t *)&v27);
          SysFreeString(0);
        }
      }
      else
      {
        _bstr_t::operator=(v18, (__int64)a4);
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
0x180003b3c  mov     [rsp+arg_8], rbx
0x180003b41  mov     [rsp+arg_10], rbp
0x180003b46  push    rsi
0x180003b47  push    rdi
0x180003b48  push    r12
0x180003b4a  push    r14
0x180003b4c  push    r15
0x180003b4e  sub     rsp, 30h
0x180003b52  mov     rbp, r9
0x180003b55  mov     r15, r8
0x180003b58  mov     r14, rdx
0x180003b5b  mov     rsi, rcx
0x180003b5e  xor     r12d, r12d
0x180003b61  cmp     [rcx], r12
0x180003b64  jz      loc_180003D8D
0x180003b6a  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180003b71  mov     [rsp+58h+var_30], rdi
0x180003b76  mov     rcx, rdi; lpCriticalSection
0x180003b79  call    cs:__imp_EnterCriticalSection
0x180003b7f  nop
0x180003b80  mov     rdx, [rsp+58h+arg_28]; void *
0x180003b88  test    rdx, rdx
0x180003b8b  jz      short loc_180003B9B
0x180003b8d  mov     rcx, [rsi]; this
0x180003b90  cmp     [rcx+20h], r12
0x180003b94  jnz     short loc_180003B9B
0x180003b96  call    ?CopySid@UserEntry@User@@QEAAXPEAX@Z; User::UserEntry::CopySid(void *)
0x180003b9b  mov     rdx, [rsi]
0x180003b9e  mov     eax, [rdx+28h]
0x180003ba1  sub     eax, 4
0x180003ba4  cmp     eax, 1
0x180003ba7  jbe     loc_180003C3D
0x180003bad  mov     rcx, [r14]
0x180003bb0  test    rcx, rcx
0x180003bb3  jz      short loc_180003BD8
0x180003bb5  cmp     [rcx], r12
0x180003bb8  jz      short loc_180003BD8
0x180003bba  mov     rdx, [rdx+10h]
0x180003bbe  test    rdx, rdx
0x180003bc1  jz      short loc_180003BD8
0x180003bc3  cmp     [rdx], r12
0x180003bc6  jz      short loc_180003BD8
0x180003bc8  mov     rdx, [rdx]; String2
0x180003bcb  mov     rcx, [rcx]; String1
0x180003bce  call    cs:__imp__wcsicmp
0x180003bd4  test    eax, eax
0x180003bd6  jnz     short loc_180003C06
0x180003bd8  mov     rcx, [r15]
0x180003bdb  test    rcx, rcx
0x180003bde  jz      short loc_180003C3D
0x180003be0  cmp     [rcx], r12
0x180003be3  jz      short loc_180003C3D
0x180003be5  mov     rax, [rsi]
0x180003be8  mov     rdx, [rax+18h]
0x180003bec  test    rdx, rdx
0x180003bef  jz      short loc_180003C3D
0x180003bf1  cmp     [rdx], r12
0x180003bf4  jz      short loc_180003C3D
0x180003bf6  mov     rdx, [rdx]; String2
0x180003bf9  mov     rcx, [rcx]; String1
0x180003bfc  call    cs:__imp__wcsicmp
0x180003c02  test    eax, eax
0x180003c04  jz      short loc_180003C3D
0x180003c06  mov     rcx, [rsi]
0x180003c09  add     rcx, 8
0x180003c0d  xor     edx, edx
0x180003c0f  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003c14  mov     rcx, [rsi]
0x180003c17  add     rcx, 10h
0x180003c1b  xor     edx, edx
0x180003c1d  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003c22  mov     rcx, [rsi]
0x180003c25  add     rcx, 18h
0x180003c29  xor     edx, edx
0x180003c2b  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003c30  mov     rcx, rsi; this
0x180003c33  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180003c38  jmp     loc_180003D84
0x180003c3d  mov     bl, r12b
0x180003c40  mov     rax, [r14]
0x180003c43  test    rax, rax
0x180003c46  jz      short loc_180003C6B
0x180003c48  cmp     [rax], r12
0x180003c4b  jz      short loc_180003C6B
0x180003c4d  mov     rcx, [rsi]
0x180003c50  add     rcx, 10h
0x180003c54  mov     rax, [rcx]
0x180003c57  test    rax, rax
0x180003c5a  jz      short loc_180003C61
0x180003c5c  cmp     [rax], r12
0x180003c5f  jnz     short loc_180003C6B
0x180003c61  mov     bl, 1
0x180003c63  mov     rdx, r14
0x180003c66  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003c6b  mov     rax, [r15]
0x180003c6e  test    rax, rax
0x180003c71  jz      short loc_180003C96
0x180003c73  cmp     [rax], r12
0x180003c76  jz      short loc_180003C96
0x180003c78  mov     rcx, [rsi]
0x180003c7b  add     rcx, 18h
0x180003c7f  mov     rax, [rcx]
0x180003c82  test    rax, rax
0x180003c85  jz      short loc_180003C8C
0x180003c87  cmp     [rax], r12
0x180003c8a  jnz     short loc_180003C96
0x180003c8c  mov     bl, 1
0x180003c8e  mov     rdx, r15
0x180003c91  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003c96  mov     rax, [rbp+0]
0x180003c9a  test    rax, rax
0x180003c9d  jz      short loc_180003CC5
0x180003c9f  cmp     [rax], r12
0x180003ca2  jz      short loc_180003CC5
0x180003ca4  mov     rcx, [rsi]
0x180003ca7  add     rcx, 8
0x180003cab  mov     rax, [rcx]
0x180003cae  test    rax, rax
0x180003cb1  jz      short loc_180003CB8
0x180003cb3  cmp     [rax], r12
0x180003cb6  jnz     short loc_180003CC5
0x180003cb8  mov     rdx, rbp
0x180003cbb  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003cc0  jmp     loc_180003D72
0x180003cc5  test    bl, bl
0x180003cc7  jz      loc_180003D72
0x180003ccd  mov     rcx, r14; this
0x180003cd0  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180003cd5  lea     ebx, [rax+1]
0x180003cd8  mov     rcx, r15; this
0x180003cdb  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180003ce0  add     ebx, eax
0x180003ce2  mov     edx, ebx; int
0x180003ce4  lea     rcx, [rsp+58h+var_38]; this
0x180003ce9  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180003cee  nop
0x180003cef  mov     ebp, ebx
0x180003cf1  inc     rbp
0x180003cf4  mov     r8, [r15]
0x180003cf7  test    r8, r8
0x180003cfa  jz      short loc_180003D01
0x180003cfc  mov     r8, [r8]
0x180003cff  jmp     short loc_180003D04
0x180003d01  mov     r8, r12; unsigned __int16 *
0x180003d04  mov     rdx, rbp; unsigned __int64
0x180003d07  mov     rbx, [rsp+58h+var_38]
0x180003d0c  mov     rcx, rbx; unsigned __int16 *
0x180003d0f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003d14  lea     r8, asc_18004F6BC; "\\"
0x180003d1b  mov     rdx, rbp; unsigned __int64
0x180003d1e  mov     rcx, rbx; unsigned __int16 *
0x180003d21  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003d26  mov     r8, [r14]
0x180003d29  test    r8, r8
0x180003d2c  jz      short loc_180003D33
0x180003d2e  mov     r8, [r8]
0x180003d31  jmp     short loc_180003D36
0x180003d33  mov     r8, r12; unsigned __int16 *
0x180003d36  mov     rdx, rbp; unsigned __int64
0x180003d39  mov     rcx, rbx; unsigned __int16 *
0x180003d3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003d41  mov     rdx, rbx; unsigned __int16 *
0x180003d44  lea     rcx, [rsp+58h+arg_0]; this
0x180003d49  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180003d4e  mov     rcx, [rsi]
0x180003d51  add     rcx, 8
0x180003d55  lea     rdx, [rsp+58h+arg_0]
0x180003d5a  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003d5f  lea     rcx, [rsp+58h+arg_0]; this
0x180003d64  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003d69  nop
0x180003d6a  xor     ecx, ecx; bstrString
0x180003d6c  call    cs:__imp_SysFreeString
0x180003d72  mov     ecx, [rsp+58h+arg_20]
0x180003d79  cmp     ecx, 8
0x180003d7c  jz      short loc_180003D84
0x180003d7e  mov     rax, [rsi]
0x180003d81  mov     [rax+28h], ecx
0x180003d84  mov     rcx, rdi; lpCriticalSection
0x180003d87  call    cs:__imp_LeaveCriticalSection
0x180003d8d  mov     rbx, [rsp+58h+arg_8]
0x180003d92  mov     rbp, [rsp+58h+arg_10]
0x180003d97  add     rsp, 30h
0x180003d9b  pop     r15
0x180003d9d  pop     r14
0x180003d9f  pop     r12
0x180003da1  pop     rdi
0x180003da2  pop     rsi
0x180003da3  retn
```

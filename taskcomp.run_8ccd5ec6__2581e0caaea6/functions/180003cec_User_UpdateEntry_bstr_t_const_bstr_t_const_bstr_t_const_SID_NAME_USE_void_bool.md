# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x180003cec`
- end: `0x180003f73`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `647`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180019f10`
- `0x18001a394`
- `0x18001acc4`

## callees

- `0x180003320`
- `0x180003c9c`
- `0x180003cec`
- `0x180003f7c`
- `0x180004090`
- `0x1800040c0`
- `0x1800050d0`
- `0x180005184`
- `0x1800051c4`
- `0x180019ac0`
- `0x18001c3ac`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180003d84`
- `msvcrt!_wcsicmp` at `0x180003db8`
- `msvcrt!_wcsicmp` at `0x180003d84`
- `msvcrt!_wcsicmp` at `0x180003db8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003d29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f4f`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f2e`
- `OLEAUT32!__imp_SysFreeString` at `0x180003f2e`

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
  unsigned __int16 *v22; // r8
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
            v22 = **(unsigned __int16 ***)a3;
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
          _bstr_t::~_bstr_t((_bstr_t *)&v28);
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
0x180003cec  mov     [rsp+arg_8], rbx
0x180003cf1  mov     [rsp+arg_10], rbp
0x180003cf6  push    rsi
0x180003cf7  push    rdi
0x180003cf8  push    r12
0x180003cfa  push    r14
0x180003cfc  push    r15
0x180003cfe  sub     rsp, 30h
0x180003d02  mov     rbp, r9
0x180003d05  mov     r15, r8
0x180003d08  mov     r14, rdx
0x180003d0b  mov     rsi, rcx
0x180003d0e  xor     r12d, r12d
0x180003d11  cmp     [rcx], r12
0x180003d14  jz      loc_180003F5B
0x180003d1a  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x180003d21  mov     [rsp+58h+var_30], rdi
0x180003d26  mov     rcx, rdi; lpCriticalSection
0x180003d29  call    cs:__imp_EnterCriticalSection
0x180003d30  nop     dword ptr [rax+rax+00h]
0x180003d35  nop
0x180003d36  mov     rdx, [rsp+58h+arg_28]; void *
0x180003d3e  test    rdx, rdx
0x180003d41  jz      short loc_180003D51
0x180003d43  mov     rcx, [rsi]; this
0x180003d46  cmp     [rcx+20h], r12
0x180003d4a  jnz     short loc_180003D51
0x180003d4c  call    ?CopySid@UserEntry@User@@QEAAXPEAX@Z; User::UserEntry::CopySid(void *)
0x180003d51  mov     rdx, [rsi]
0x180003d54  mov     eax, [rdx+28h]
0x180003d57  sub     eax, 4
0x180003d5a  cmp     eax, 1
0x180003d5d  jbe     loc_180003DFF
0x180003d63  mov     rcx, [r14]
0x180003d66  test    rcx, rcx
0x180003d69  jz      short loc_180003D94
0x180003d6b  cmp     [rcx], r12
0x180003d6e  jz      short loc_180003D94
0x180003d70  mov     rdx, [rdx+10h]
0x180003d74  test    rdx, rdx
0x180003d77  jz      short loc_180003D94
0x180003d79  cmp     [rdx], r12
0x180003d7c  jz      short loc_180003D94
0x180003d7e  mov     rdx, [rdx]; String2
0x180003d81  mov     rcx, [rcx]; String1
0x180003d84  call    cs:__imp__wcsicmp
0x180003d8b  nop     dword ptr [rax+rax+00h]
0x180003d90  test    eax, eax
0x180003d92  jnz     short loc_180003DC8
0x180003d94  mov     rcx, [r15]
0x180003d97  test    rcx, rcx
0x180003d9a  jz      short loc_180003DFF
0x180003d9c  cmp     [rcx], r12
0x180003d9f  jz      short loc_180003DFF
0x180003da1  mov     rax, [rsi]
0x180003da4  mov     rdx, [rax+18h]
0x180003da8  test    rdx, rdx
0x180003dab  jz      short loc_180003DFF
0x180003dad  cmp     [rdx], r12
0x180003db0  jz      short loc_180003DFF
0x180003db2  mov     rdx, [rdx]; String2
0x180003db5  mov     rcx, [rcx]; String1
0x180003db8  call    cs:__imp__wcsicmp
0x180003dbf  nop     dword ptr [rax+rax+00h]
0x180003dc4  test    eax, eax
0x180003dc6  jz      short loc_180003DFF
0x180003dc8  mov     rcx, [rsi]
0x180003dcb  add     rcx, 8
0x180003dcf  xor     edx, edx
0x180003dd1  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003dd6  mov     rcx, [rsi]
0x180003dd9  add     rcx, 10h
0x180003ddd  xor     edx, edx
0x180003ddf  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003de4  mov     rcx, [rsi]
0x180003de7  add     rcx, 18h
0x180003deb  xor     edx, edx
0x180003ded  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x180003df2  mov     rcx, rsi; this
0x180003df5  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x180003dfa  jmp     loc_180003F4C
0x180003dff  mov     bl, r12b
0x180003e02  mov     rax, [r14]
0x180003e05  test    rax, rax
0x180003e08  jz      short loc_180003E2D
0x180003e0a  cmp     [rax], r12
0x180003e0d  jz      short loc_180003E2D
0x180003e0f  mov     rcx, [rsi]
0x180003e12  add     rcx, 10h
0x180003e16  mov     rax, [rcx]
0x180003e19  test    rax, rax
0x180003e1c  jz      short loc_180003E23
0x180003e1e  cmp     [rax], r12
0x180003e21  jnz     short loc_180003E2D
0x180003e23  mov     bl, 1
0x180003e25  mov     rdx, r14
0x180003e28  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003e2d  mov     rax, [r15]
0x180003e30  test    rax, rax
0x180003e33  jz      short loc_180003E58
0x180003e35  cmp     [rax], r12
0x180003e38  jz      short loc_180003E58
0x180003e3a  mov     rcx, [rsi]
0x180003e3d  add     rcx, 18h
0x180003e41  mov     rax, [rcx]
0x180003e44  test    rax, rax
0x180003e47  jz      short loc_180003E4E
0x180003e49  cmp     [rax], r12
0x180003e4c  jnz     short loc_180003E58
0x180003e4e  mov     bl, 1
0x180003e50  mov     rdx, r15
0x180003e53  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003e58  mov     rax, [rbp+0]
0x180003e5c  test    rax, rax
0x180003e5f  jz      short loc_180003E87
0x180003e61  cmp     [rax], r12
0x180003e64  jz      short loc_180003E87
0x180003e66  mov     rcx, [rsi]
0x180003e69  add     rcx, 8
0x180003e6d  mov     rax, [rcx]
0x180003e70  test    rax, rax
0x180003e73  jz      short loc_180003E7A
0x180003e75  cmp     [rax], r12
0x180003e78  jnz     short loc_180003E87
0x180003e7a  mov     rdx, rbp
0x180003e7d  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003e82  jmp     loc_180003F3A
0x180003e87  test    bl, bl
0x180003e89  jz      loc_180003F3A
0x180003e8f  mov     rcx, r14; this
0x180003e92  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180003e97  lea     ebx, [rax+1]
0x180003e9a  mov     rcx, r15; this
0x180003e9d  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x180003ea2  add     ebx, eax
0x180003ea4  mov     edx, ebx; int
0x180003ea6  lea     rcx, [rsp+58h+var_38]; this
0x180003eab  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x180003eb0  nop
0x180003eb1  mov     ebp, ebx
0x180003eb3  inc     rbp
0x180003eb6  mov     r8, [r15]
0x180003eb9  test    r8, r8
0x180003ebc  jz      short loc_180003EC3
0x180003ebe  mov     r8, [r8]
0x180003ec1  jmp     short loc_180003EC6
0x180003ec3  mov     r8, r12; unsigned __int16 *
0x180003ec6  mov     rdx, rbp; unsigned __int64
0x180003ec9  mov     rbx, [rsp+58h+var_38]
0x180003ece  mov     rcx, rbx; unsigned __int16 *
0x180003ed1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003ed6  lea     r8, asc_1800516CC; "\\"
0x180003edd  mov     rdx, rbp; unsigned __int64
0x180003ee0  mov     rcx, rbx; unsigned __int16 *
0x180003ee3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003ee8  mov     r8, [r14]
0x180003eeb  test    r8, r8
0x180003eee  jz      short loc_180003EF5
0x180003ef0  mov     r8, [r8]
0x180003ef3  jmp     short loc_180003EF8
0x180003ef5  mov     r8, r12; unsigned __int16 *
0x180003ef8  mov     rdx, rbp; unsigned __int64
0x180003efb  mov     rcx, rbx; unsigned __int16 *
0x180003efe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003f03  mov     rdx, rbx; unsigned __int16 *
0x180003f06  lea     rcx, [rsp+58h+arg_0]; this
0x180003f0b  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x180003f10  mov     rcx, [rsi]
0x180003f13  add     rcx, 8
0x180003f17  lea     rdx, [rsp+58h+arg_0]
0x180003f1c  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x180003f21  lea     rcx, [rsp+58h+arg_0]; this
0x180003f26  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180003f2b  nop
0x180003f2c  xor     ecx, ecx; bstrString
0x180003f2e  call    cs:__imp_SysFreeString
0x180003f35  nop     dword ptr [rax+rax+00h]
0x180003f3a  mov     ecx, [rsp+58h+arg_20]
0x180003f41  cmp     ecx, 8
0x180003f44  jz      short loc_180003F4C
0x180003f46  mov     rax, [rsi]
0x180003f49  mov     [rax+28h], ecx
0x180003f4c  mov     rcx, rdi; lpCriticalSection
0x180003f4f  call    cs:__imp_LeaveCriticalSection
0x180003f56  nop     dword ptr [rax+rax+00h]
0x180003f5b  mov     rbx, [rsp+58h+arg_8]
0x180003f60  mov     rbp, [rsp+58h+arg_10]
0x180003f65  add     rsp, 30h
0x180003f69  pop     r15
0x180003f6b  pop     r14
0x180003f6d  pop     r12
0x180003f6f  pop     rdi
0x180003f70  pop     rsi
0x180003f71  retn
```

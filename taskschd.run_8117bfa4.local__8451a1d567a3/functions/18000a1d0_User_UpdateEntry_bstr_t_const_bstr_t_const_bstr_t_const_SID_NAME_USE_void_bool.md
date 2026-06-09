# User::UpdateEntry(_bstr_t const &,_bstr_t const &,_bstr_t const &,_SID_NAME_USE,void *,bool)

- ea: `0x18000a1d0`
- end: `0x18000a457`
- name: `?UpdateEntry@User@@AEBAXAEBV_bstr_t@@00W4_SID_NAME_USE@@PEAX_N@Z`
- size: `647`
- prototype: `void __usercall(User *__hidden this@<rcx>, const struct _bstr_t *@<rdx>, const struct _bstr_t *@<r8>, const struct _bstr_t *@<r9>, enum _SID_NAME_USE, void *, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180008240`
- `0x1800089e0`

## callees

- `0x180009150`
- `0x180009280`
- `0x18000a1d0`
- `0x18001f240`
- `0x180020c10`
- `0x1800287c0`
- `0x18002ed1c`
- `0x18002f170`
- `0x18002fe74`
- `0x180032638`
- `0x18003c7c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a268`
- `msvcrt!_wcsicmp` at `0x18000a29c`
- `msvcrt!_wcsicmp` at `0x18000a268`
- `msvcrt!_wcsicmp` at `0x18000a29c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a20d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a20d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a412`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a412`

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
0x18000a1d0  mov     [rsp+arg_8], rbx
0x18000a1d5  mov     [rsp+arg_10], rbp
0x18000a1da  push    rsi
0x18000a1db  push    rdi
0x18000a1dc  push    r12
0x18000a1de  push    r14
0x18000a1e0  push    r15
0x18000a1e2  sub     rsp, 30h
0x18000a1e6  mov     rbp, r9
0x18000a1e9  mov     r15, r8
0x18000a1ec  mov     r14, rdx
0x18000a1ef  mov     rsi, rcx
0x18000a1f2  xor     r12d, r12d
0x18000a1f5  cmp     [rcx], r12
0x18000a1f8  jz      loc_18000A43F
0x18000a1fe  mov     rdi, cs:?s_cs@User@@0PEAVCritSec@wmi@@EA; wmi::CritSec * User::s_cs
0x18000a205  mov     [rsp+58h+var_30], rdi
0x18000a20a  mov     rcx, rdi; lpCriticalSection
0x18000a20d  call    cs:__imp_EnterCriticalSection
0x18000a214  nop     dword ptr [rax+rax+00h]
0x18000a219  nop
0x18000a21a  mov     rdx, [rsp+58h+arg_28]; void *
0x18000a222  test    rdx, rdx
0x18000a225  jz      short loc_18000A235
0x18000a227  mov     rcx, [rsi]; this
0x18000a22a  cmp     [rcx+20h], r12
0x18000a22e  jnz     short loc_18000A235
0x18000a230  call    ?CopySid@UserEntry@User@@QEAAXPEAX@Z; User::UserEntry::CopySid(void *)
0x18000a235  mov     rdx, [rsi]
0x18000a238  mov     eax, [rdx+28h]
0x18000a23b  sub     eax, 4
0x18000a23e  cmp     eax, 1
0x18000a241  jbe     loc_18000A2E3
0x18000a247  mov     rcx, [r14]
0x18000a24a  test    rcx, rcx
0x18000a24d  jz      short loc_18000A278
0x18000a24f  cmp     [rcx], r12
0x18000a252  jz      short loc_18000A278
0x18000a254  mov     rdx, [rdx+10h]
0x18000a258  test    rdx, rdx
0x18000a25b  jz      short loc_18000A278
0x18000a25d  cmp     [rdx], r12
0x18000a260  jz      short loc_18000A278
0x18000a262  mov     rdx, [rdx]; String2
0x18000a265  mov     rcx, [rcx]; String1
0x18000a268  call    cs:__imp__wcsicmp
0x18000a26f  nop     dword ptr [rax+rax+00h]
0x18000a274  test    eax, eax
0x18000a276  jnz     short loc_18000A2AC
0x18000a278  mov     rcx, [r15]
0x18000a27b  test    rcx, rcx
0x18000a27e  jz      short loc_18000A2E3
0x18000a280  cmp     [rcx], r12
0x18000a283  jz      short loc_18000A2E3
0x18000a285  mov     rax, [rsi]
0x18000a288  mov     rdx, [rax+18h]
0x18000a28c  test    rdx, rdx
0x18000a28f  jz      short loc_18000A2E3
0x18000a291  cmp     [rdx], r12
0x18000a294  jz      short loc_18000A2E3
0x18000a296  mov     rdx, [rdx]; String2
0x18000a299  mov     rcx, [rcx]; String1
0x18000a29c  call    cs:__imp__wcsicmp
0x18000a2a3  nop     dword ptr [rax+rax+00h]
0x18000a2a8  test    eax, eax
0x18000a2aa  jz      short loc_18000A2E3
0x18000a2ac  mov     rcx, [rsi]
0x18000a2af  add     rcx, 8
0x18000a2b3  xor     edx, edx
0x18000a2b5  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000a2ba  mov     rcx, [rsi]
0x18000a2bd  add     rcx, 10h
0x18000a2c1  xor     edx, edx
0x18000a2c3  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000a2c8  mov     rcx, [rsi]
0x18000a2cb  add     rcx, 18h
0x18000a2cf  xor     edx, edx
0x18000a2d1  call    ??4_bstr_t@@QEAAAEAV0@PEBG@Z; _bstr_t::operator=(ushort const *)
0x18000a2d6  mov     rcx, rsi; this
0x18000a2d9  call    ?UpdateEntry@User@@AEBAJXZ; User::UpdateEntry(void)
0x18000a2de  jmp     loc_18000A430
0x18000a2e3  mov     bl, r12b
0x18000a2e6  mov     rax, [r14]
0x18000a2e9  test    rax, rax
0x18000a2ec  jz      short loc_18000A311
0x18000a2ee  cmp     [rax], r12
0x18000a2f1  jz      short loc_18000A311
0x18000a2f3  mov     rcx, [rsi]
0x18000a2f6  add     rcx, 10h
0x18000a2fa  mov     rax, [rcx]
0x18000a2fd  test    rax, rax
0x18000a300  jz      short loc_18000A307
0x18000a302  cmp     [rax], r12
0x18000a305  jnz     short loc_18000A311
0x18000a307  mov     bl, 1
0x18000a309  mov     rdx, r14
0x18000a30c  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18000a311  mov     rax, [r15]
0x18000a314  test    rax, rax
0x18000a317  jz      short loc_18000A33C
0x18000a319  cmp     [rax], r12
0x18000a31c  jz      short loc_18000A33C
0x18000a31e  mov     rcx, [rsi]
0x18000a321  add     rcx, 18h
0x18000a325  mov     rax, [rcx]
0x18000a328  test    rax, rax
0x18000a32b  jz      short loc_18000A332
0x18000a32d  cmp     [rax], r12
0x18000a330  jnz     short loc_18000A33C
0x18000a332  mov     bl, 1
0x18000a334  mov     rdx, r15
0x18000a337  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18000a33c  mov     rax, [rbp+0]
0x18000a340  test    rax, rax
0x18000a343  jz      short loc_18000A36B
0x18000a345  cmp     [rax], r12
0x18000a348  jz      short loc_18000A36B
0x18000a34a  mov     rcx, [rsi]
0x18000a34d  add     rcx, 8
0x18000a351  mov     rax, [rcx]
0x18000a354  test    rax, rax
0x18000a357  jz      short loc_18000A35E
0x18000a359  cmp     [rax], r12
0x18000a35c  jnz     short loc_18000A36B
0x18000a35e  mov     rdx, rbp
0x18000a361  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18000a366  jmp     loc_18000A41E
0x18000a36b  test    bl, bl
0x18000a36d  jz      loc_18000A41E
0x18000a373  mov     rcx, r14; this
0x18000a376  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000a37b  lea     ebx, [rax+1]
0x18000a37e  mov     rcx, r15; this
0x18000a381  call    ?length@_bstr_t@@QEBAIXZ; _bstr_t::length(void)
0x18000a386  add     ebx, eax
0x18000a388  mov     edx, ebx; int
0x18000a38a  lea     rcx, [rsp+58h+var_38]; this
0x18000a38f  call    ??0CComBSTR@ATL@@QEAA@H@Z; ATL::CComBSTR::CComBSTR(int)
0x18000a394  nop
0x18000a395  mov     ebp, ebx
0x18000a397  inc     rbp
0x18000a39a  mov     r8, [r15]
0x18000a39d  test    r8, r8
0x18000a3a0  jz      short loc_18000A3A7
0x18000a3a2  mov     r8, [r8]
0x18000a3a5  jmp     short loc_18000A3AA
0x18000a3a7  mov     r8, r12; unsigned __int16 *
0x18000a3aa  mov     rdx, rbp; unsigned __int64
0x18000a3ad  mov     rbx, [rsp+58h+var_38]
0x18000a3b2  mov     rcx, rbx; unsigned __int16 *
0x18000a3b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a3ba  lea     r8, asc_18007B230; "\\"
0x18000a3c1  mov     rdx, rbp; unsigned __int64
0x18000a3c4  mov     rcx, rbx; unsigned __int16 *
0x18000a3c7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3cc  mov     r8, [r14]
0x18000a3cf  test    r8, r8
0x18000a3d2  jz      short loc_18000A3D9
0x18000a3d4  mov     r8, [r8]
0x18000a3d7  jmp     short loc_18000A3DC
0x18000a3d9  mov     r8, r12; unsigned __int16 *
0x18000a3dc  mov     rdx, rbp; unsigned __int64
0x18000a3df  mov     rcx, rbx; unsigned __int16 *
0x18000a3e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a3e7  mov     rdx, rbx; unsigned __int16 *
0x18000a3ea  lea     rcx, [rsp+58h+arg_0]; this
0x18000a3ef  call    ??0_bstr_t@@QEAA@PEAG_N@Z; _bstr_t::_bstr_t(ushort *,bool)
0x18000a3f4  mov     rcx, [rsi]
0x18000a3f7  add     rcx, 8
0x18000a3fb  lea     rdx, [rsp+58h+arg_0]
0x18000a400  call    ??4_bstr_t@@QEAAAEAV0@AEBV0@@Z; _bstr_t::operator=(_bstr_t const &)
0x18000a405  lea     rcx, [rsp+58h+arg_0]; this
0x18000a40a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18000a40f  nop
0x18000a410  xor     ecx, ecx; bstrString
0x18000a412  call    cs:__imp_SysFreeString
0x18000a419  nop     dword ptr [rax+rax+00h]
0x18000a41e  mov     ecx, [rsp+58h+arg_20]
0x18000a425  cmp     ecx, 8
0x18000a428  jz      short loc_18000A430
0x18000a42a  mov     rax, [rsi]
0x18000a42d  mov     [rax+28h], ecx
0x18000a430  mov     rcx, rdi; lpCriticalSection
0x18000a433  call    cs:__imp_LeaveCriticalSection
0x18000a43a  nop     dword ptr [rax+rax+00h]
0x18000a43f  mov     rbx, [rsp+58h+arg_8]
0x18000a444  mov     rbp, [rsp+58h+arg_10]
0x18000a449  add     rsp, 30h
0x18000a44d  pop     r15
0x18000a44f  pop     r14
0x18000a451  pop     r12
0x18000a453  pop     rdi
0x18000a454  pop     rsi
0x18000a455  retn
```

# CLdapConnection::LdapOpen(ushort const *,ushort const *,int)

- ea: `0x18001f2c0`
- end: `0x18001f439`
- name: `?LdapOpen@CLdapConnection@@QEAAKPEBG0H@Z`
- size: `377`
- prototype: `unsigned int __fastcall(CLdapConnection *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180012ff0`
- `0x180014330`
- `0x180014e40`
- `0x180015830`
- `0x18001f2c0`
- `0x18001f440`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f35e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f3a7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f2f1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f35e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001f3a7`

## pseudocode

```c
__int64 __fastcall CLdapConnection::LdapOpen(
        CLdapConnection *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4)
{
  unsigned __int16 **v4; // rsi
  void *v6; // rcx
  unsigned int DSInfo; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // r9d
  unsigned int DefaultContext; // ebx
  void *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8

  v4 = (unsigned __int16 **)((char *)this + 16);
  v6 = (void *)*((_QWORD *)this + 2);
  if ( v6 )
  {
    operator delete(v6);
    *v4 = 0;
  }
  if ( a2 )
  {
    DSInfo = DuplicateStringWBom(a2, 0, v4);
    v13 = 83;
  }
  else
  {
    DSInfo = GetDSInfo(a4, a3, v4, 0);
    v13 = 77;
  }
  DefaultContext = DSInfo;
  if ( !(unsigned int)ElValidateWin32_10(DSInfo, v11, v12, v13) )
  {
    *((_DWORD *)this + 2) = a4 != 0 ? 3268 : 389;
    v15 = (void *)*((_QWORD *)this + 4);
    if ( v15 )
    {
      operator delete(v15);
      *((_QWORD *)this + 4) = 0;
    }
    DefaultContext = CLdap::GetDefaultContext(
                       (PWSTR)L"schemaNamingContext",
                       (unsigned __int16 **)this + 4,
                       *v4,
                       *((_DWORD *)this + 2));
    if ( !(unsigned int)ElValidateWin32_10(DefaultContext, v16, v17, 0x62u) )
    {
      v18 = (void *)*((_QWORD *)this + 3);
      if ( v18 )
      {
        operator delete(v18);
        *((_QWORD *)this + 3) = 0;
      }
      if ( a4
        || (DefaultContext = CLdap::GetDefaultContext(
                               (PWSTR)L"defaultNamingContext",
                               (unsigned __int16 **)this + 3,
                               *v4,
                               *((_DWORD *)this + 2)),
            !(unsigned int)ElValidateWin32_10(DefaultContext, v19, v20, 0x70u)) )
      {
        DefaultContext = CLdap::Open(this, *v4, *((_DWORD *)this + 2), &stru_18004B618, 0, 0, 0x486u);
        ElValidateWin32_10(DefaultContext, v21, v22, 0x7Bu);
      }
    }
  }
  return DefaultContext;
}

```

## disassembly

```asm
0x18001f2c0  mov     rax, rsp
0x18001f2c3  mov     [rax+8], rbx
0x18001f2c7  mov     [rax+10h], rbp
0x18001f2cb  mov     [rax+18h], rsi
0x18001f2cf  mov     [rax+20h], rdi
0x18001f2d3  push    r14
0x18001f2d5  sub     rsp, 40h
0x18001f2d9  lea     rsi, [rcx+10h]
0x18001f2dd  mov     rdi, rcx
0x18001f2e0  mov     rcx, [rsi]
0x18001f2e3  mov     ebp, r9d
0x18001f2e6  mov     r14, r8
0x18001f2e9  mov     rbx, rdx
0x18001f2ec  test    rcx, rcx
0x18001f2ef  jz      short loc_18001F301
0x18001f2f1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f2f8  nop     dword ptr [rax+rax+00h]
0x18001f2fd  and     qword ptr [rsi], 0
0x18001f301  mov     r8, rsi; unsigned __int16 **
0x18001f304  test    rbx, rbx
0x18001f307  jnz     short loc_18001F31C
0x18001f309  xor     r9d, r9d; unsigned __int16 **
0x18001f30c  mov     rdx, r14; unsigned __int16 *
0x18001f30f  mov     ecx, ebp; int
0x18001f311  call    ?GetDSInfo@@YAKHPEBGPEAPEAG1@Z; GetDSInfo(int,ushort const *,ushort * *,ushort * *)
0x18001f316  lea     r9d, [rbx+4Dh]
0x18001f31a  jmp     short loc_18001F32C
0x18001f31c  xor     edx, edx; int
0x18001f31e  mov     rcx, rbx; unsigned __int16 *
0x18001f321  call    ?DuplicateStringWBom@@YAKPEBGHPEAPEAG@Z; DuplicateStringWBom(ushort const *,int,ushort * *)
0x18001f326  mov     r9d, 53h ; 'S'
0x18001f32c  mov     ecx, eax
0x18001f32e  mov     ebx, eax
0x18001f330  call    ElValidateWin32_10
0x18001f335  test    eax, eax
0x18001f337  jnz     loc_18001F41B
0x18001f33d  mov     eax, ebp
0x18001f33f  lea     rbx, [rdi+20h]
0x18001f343  neg     eax
0x18001f345  sbb     ecx, ecx
0x18001f347  and     ecx, 0B3Fh
0x18001f34d  add     ecx, 185h
0x18001f353  mov     [rdi+8], ecx
0x18001f356  mov     rcx, [rbx]
0x18001f359  test    rcx, rcx
0x18001f35c  jz      short loc_18001F36E
0x18001f35e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f365  nop     dword ptr [rax+rax+00h]
0x18001f36a  and     qword ptr [rbx], 0
0x18001f36e  mov     r9d, [rdi+8]; unsigned int
0x18001f372  lea     rcx, attr; "schemaNamingContext"
0x18001f379  mov     r8, [rsi]; unsigned __int16 *
0x18001f37c  mov     rdx, rbx; unsigned __int16 **
0x18001f37f  call    ?GetDefaultContext@CLdap@@SAKPEBGPEAPEAG0K@Z; CLdap::GetDefaultContext(ushort const *,ushort * *,ushort const *,ulong)
0x18001f384  mov     r9d, 62h ; 'b'
0x18001f38a  mov     ecx, eax
0x18001f38c  mov     ebx, eax
0x18001f38e  call    ElValidateWin32_10
0x18001f393  test    eax, eax
0x18001f395  jnz     loc_18001F41B
0x18001f39b  lea     rbx, [rdi+18h]
0x18001f39f  mov     rcx, [rbx]
0x18001f3a2  test    rcx, rcx
0x18001f3a5  jz      short loc_18001F3B7
0x18001f3a7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001f3ae  nop     dword ptr [rax+rax+00h]
0x18001f3b3  and     qword ptr [rbx], 0
0x18001f3b7  test    ebp, ebp
0x18001f3b9  jnz     short loc_18001F3E2
0x18001f3bb  mov     r9d, [rdi+8]; unsigned int
0x18001f3bf  lea     rcx, aDefaultnamingc; "defaultNamingContext"
0x18001f3c6  mov     r8, [rsi]; unsigned __int16 *
0x18001f3c9  mov     rdx, rbx; unsigned __int16 **
0x18001f3cc  call    ?GetDefaultContext@CLdap@@SAKPEBGPEAPEAG0K@Z; CLdap::GetDefaultContext(ushort const *,ushort * *,ushort const *,ulong)
0x18001f3d1  lea     r9d, [rbp+70h]
0x18001f3d5  mov     ecx, eax
0x18001f3d7  mov     ebx, eax
0x18001f3d9  call    ElValidateWin32_10
0x18001f3de  test    eax, eax
0x18001f3e0  jnz     short loc_18001F41B
0x18001f3e2  mov     r8d, [rdi+8]; unsigned int
0x18001f3e6  lea     r9, stru_18004B618; struct l_timeval *
0x18001f3ed  mov     rdx, [rsi]; unsigned __int16 *
0x18001f3f0  mov     rcx, rdi; this
0x18001f3f3  mov     [rsp+48h+var_18], 486h; unsigned int
0x18001f3fb  and     [rsp+48h+var_20], 0
0x18001f401  and     [rsp+48h+var_28], 0
0x18001f407  call    ?Open@CLdap@@QEAAKPEBGKPEBUl_timeval@@00K@Z; CLdap::Open(ushort const *,ulong,l_timeval const *,ushort const *,ushort const *,ulong)
0x18001f40c  mov     r9d, 7Bh ; '{'
0x18001f412  mov     ecx, eax
0x18001f414  mov     ebx, eax
0x18001f416  call    ElValidateWin32_10
0x18001f41b  mov     rbp, [rsp+48h+arg_8]
0x18001f420  mov     eax, ebx
0x18001f422  mov     rbx, [rsp+48h+arg_0]
0x18001f427  mov     rsi, [rsp+48h+arg_10]
0x18001f42c  mov     rdi, [rsp+48h+arg_18]
0x18001f431  add     rsp, 40h
0x18001f435  pop     r14
0x18001f437  retn
```

# CWuaSingletonClassFactory::QueryInterface(_GUID const &,void * *)

- ea: `0x14000c340`
- end: `0x14000c422`
- name: `?QueryInterface@CWuaSingletonClassFactory@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `226`
- prototype: `int(CWuaSingletonClassFactory *__hidden this, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140018fd0`

## callees

- `0x140002ac0`
- `0x14000c340`
- `0x1400206e0`

## string_xrefs

- `0x14000c357`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x14000c40a`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaSingletonClassFactory::QueryInterface(
        CWuaSingletonClassFactory *this,
        const struct _GUID *a2,
        void **a3)
{
  __int64 result; // rax
  int v5; // edi
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
  if ( IID_IUnknown.Data1 == a2->Data1
    && *(_DWORD *)&IID_IUnknown.Data2 == *(_DWORD *)&a2->Data2
    && *(_DWORD *)IID_IUnknown.Data4 == *(_DWORD *)a2->Data4
    && *(_DWORD *)&IID_IUnknown.Data4[4] == *(_DWORD *)&a2->Data4[4]
    || IID_IClassFactory.Data1 == a2->Data1
    && *(_DWORD *)&IID_IClassFactory.Data2 == *(_DWORD *)&a2->Data2
    && *(_DWORD *)IID_IClassFactory.Data4 == *(_DWORD *)a2->Data4
    && *(_DWORD *)&IID_IClassFactory.Data4[4] == *(_DWORD *)&a2->Data4[4] )
  {
    *a3 = this;
LABEL_12:
    (*(void (__fastcall **)(CWuaSingletonClassFactory *))(*(_QWORD *)this + 8LL))(this);
    return 0;
  }
  v5 = (*(__int64 (__fastcall **)(CWuaSingletonClassFactory *))(*(_QWORD *)this + 48LL))(this);
  if ( v5 >= 0 )
    goto LABEL_12;
  result = 2147500034LL;
  if ( v5 != -2147467262 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)(unsigned int)v5,
      v6);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x14000c340  mov     [rsp+arg_0], rbx
0x14000c345  push    rdi; int
0x14000c346  sub     rsp, 20h
0x14000c34a  mov     rbx, rcx
0x14000c34d  test    r8, r8
0x14000c350  jnz     short loc_14000C374
0x14000c352  mov     rcx, [rsp+28h]; this
0x14000c357  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c35e  mov     ebx, 80004003h
0x14000c363  mov     edx, 217h; void *
0x14000c368  mov     r9d, ebx; char *
0x14000c36b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c370  mov     eax, ebx
0x14000c372  jmp     short loc_14000C3DC
0x14000c374  mov     ecx, [rdx]
0x14000c376  cmp     cs:IID_IUnknown.Data1, ecx
0x14000c37c  jnz     short loc_14000C39F
0x14000c37e  mov     eax, dword ptr cs:IID_IUnknown.Data2
0x14000c384  cmp     eax, [rdx+4]
0x14000c387  jnz     short loc_14000C39F
0x14000c389  mov     eax, dword ptr cs:IID_IUnknown.Data4
0x14000c38f  cmp     eax, [rdx+8]
0x14000c392  jnz     short loc_14000C39F
0x14000c394  mov     eax, dword ptr cs:IID_IUnknown.Data4+4
0x14000c39a  cmp     eax, [rdx+0Ch]
0x14000c39d  jz      short loc_14000C3C8
0x14000c39f  cmp     cs:IID_IClassFactory.Data1, ecx
0x14000c3a5  jnz     short loc_14000C3E7
0x14000c3a7  mov     eax, dword ptr cs:IID_IClassFactory.Data2
0x14000c3ad  cmp     eax, [rdx+4]
0x14000c3b0  jnz     short loc_14000C3E7
0x14000c3b2  mov     eax, dword ptr cs:IID_IClassFactory.Data4
0x14000c3b8  cmp     eax, [rdx+8]
0x14000c3bb  jnz     short loc_14000C3E7
0x14000c3bd  mov     eax, dword ptr cs:IID_IClassFactory.Data4+4
0x14000c3c3  cmp     eax, [rdx+0Ch]
0x14000c3c6  jnz     short loc_14000C3E7
0x14000c3c8  mov     [r8], rbx
0x14000c3cb  mov     rax, [rbx]
0x14000c3ce  mov     rcx, rbx
0x14000c3d1  mov     rax, [rax+8]
0x14000c3d5  call    _guard_dispatch_icall
0x14000c3da  xor     eax, eax
0x14000c3dc  mov     rbx, [rsp+28h+arg_0]
0x14000c3e1  add     rsp, 20h
0x14000c3e5  pop     rdi
0x14000c3e6  retn
0x14000c3e7  mov     rax, [rbx]
0x14000c3ea  mov     rcx, rbx
0x14000c3ed  mov     rax, [rax+30h]
0x14000c3f1  call    _guard_dispatch_icall
0x14000c3f6  mov     edi, eax
0x14000c3f8  test    eax, eax
0x14000c3fa  jns     short loc_14000C3CB
0x14000c3fc  mov     eax, 80004002h
0x14000c401  cmp     edi, eax
0x14000c403  jz      short loc_14000C3DC
0x14000c405  mov     rcx, [rsp+28h]; this
0x14000c40a  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c411  mov     r9d, edi; char *
0x14000c414  mov     edx, 21Fh; void *
0x14000c419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c41e  mov     eax, edi
0x14000c420  jmp     short loc_14000C3DC
```

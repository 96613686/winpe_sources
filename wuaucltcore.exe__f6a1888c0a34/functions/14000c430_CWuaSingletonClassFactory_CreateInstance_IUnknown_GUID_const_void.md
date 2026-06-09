# CWuaSingletonClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x14000c430`
- end: `0x14000c493`
- name: `?CreateInstance@CWuaSingletonClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `int(CWuaSingletonClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002ac0`
- `0x14000c430`
- `0x1400206e0`

## string_xrefs

- `0x14000c47c`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaSingletonClassFactory::CreateInstance(
        CWuaSingletonClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a4 )
  {
    v4 = -2147467261;
    v5 = 554;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v4,
      v7);
    return v4;
  }
  if ( a2 )
  {
    v4 = -2147221232;
    v5 = 555;
    goto LABEL_7;
  }
  v4 = (**(__int64 (__fastcall ***)(CWuaSingletonClassFactory *, const struct _GUID *, void **))this)(this, a3, a4);
  if ( (v4 & 0x80000000) != 0 )
  {
    v5 = 556;
    goto LABEL_7;
  }
  return v4;
}

```

## disassembly

```asm
0x14000c430  push    rbx; int
0x14000c432  sub     rsp, 20h
0x14000c436  mov     r10, r8
0x14000c439  test    r9, r9
0x14000c43c  jnz     short loc_14000C44A
0x14000c43e  mov     ebx, 80004003h
0x14000c443  mov     edx, 22Ah
0x14000c448  jmp     short loc_14000C477
0x14000c44a  test    rdx, rdx
0x14000c44d  jz      short loc_14000C45B
0x14000c44f  mov     ebx, 80040110h
0x14000c454  mov     edx, 22Bh
0x14000c459  jmp     short loc_14000C477
0x14000c45b  mov     rax, [rcx]
0x14000c45e  mov     r8, r9
0x14000c461  mov     rdx, r10
0x14000c464  mov     rax, [rax]
0x14000c467  call    _guard_dispatch_icall
0x14000c46c  mov     ebx, eax
0x14000c46e  test    eax, eax
0x14000c470  jns     short loc_14000C48B
0x14000c472  mov     edx, 22Ch; void *
0x14000c477  mov     rcx, [rsp+28h]; this
0x14000c47c  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c483  mov     r9d, ebx; char *
0x14000c486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c48b  mov     eax, ebx
0x14000c48d  add     rsp, 20h
0x14000c491  pop     rbx
0x14000c492  retn
```

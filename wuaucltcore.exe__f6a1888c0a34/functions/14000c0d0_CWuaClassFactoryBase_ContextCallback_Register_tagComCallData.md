# CWuaClassFactoryBase::ContextCallback_Register(tagComCallData *)

- ea: `0x14000c0d0`
- end: `0x14000c14e`
- name: `?ContextCallback_Register@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z`
- size: `126`
- prototype: `static int(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002ac0`
- `0x14000c0d0`
- `0x14000c21c`

## string_xrefs

- `0x14000c137`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::ContextCallback_Register(struct tagComCallData *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  void *pUserDefined; // rax
  IUnknown *v4; // rcx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v2 = 463;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v1,
      v6);
    return v1;
  }
  pUserDefined = a1->pUserDefined;
  if ( !pUserDefined )
  {
    v1 = -2147024809;
    v2 = 464;
    goto LABEL_11;
  }
  if ( *(_DWORD *)pUserDefined != 24 )
  {
    v1 = -2147024809;
    v2 = 469;
    goto LABEL_11;
  }
  v4 = (IUnknown *)*((_QWORD *)pUserDefined + 1);
  if ( !v4 )
  {
    v1 = -2147024809;
    v2 = 470;
    goto LABEL_11;
  }
  v1 = CWuaClassFactoryBase::RegisterClassFactoryImpl(v4);
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = 471;
    goto LABEL_11;
  }
  return v1;
}

```

## disassembly

```asm
0x14000c0d0  push    rbx; int
0x14000c0d2  sub     rsp, 20h
0x14000c0d6  test    rcx, rcx
0x14000c0d9  jnz     short loc_14000C0E7
0x14000c0db  mov     ebx, 80004003h
0x14000c0e0  mov     edx, 1CFh
0x14000c0e5  jmp     short loc_14000C132
0x14000c0e7  mov     rax, [rcx+8]
0x14000c0eb  test    rax, rax
0x14000c0ee  jnz     short loc_14000C0FC
0x14000c0f0  mov     ebx, 80070057h
0x14000c0f5  mov     edx, 1D0h
0x14000c0fa  jmp     short loc_14000C132
0x14000c0fc  cmp     dword ptr [rax], 18h
0x14000c0ff  jz      short loc_14000C10D
0x14000c101  mov     ebx, 80070057h
0x14000c106  mov     edx, 1D5h
0x14000c10b  jmp     short loc_14000C132
0x14000c10d  mov     rcx, [rax+8]; pUnk
0x14000c111  test    rcx, rcx
0x14000c114  jnz     short loc_14000C122
0x14000c116  mov     ebx, 80070057h
0x14000c11b  mov     edx, 1D6h
0x14000c120  jmp     short loc_14000C132
0x14000c122  call    ?RegisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::RegisterClassFactoryImpl(void)
0x14000c127  mov     ebx, eax
0x14000c129  test    eax, eax
0x14000c12b  jns     short loc_14000C146
0x14000c12d  mov     edx, 1D7h; void *
0x14000c132  mov     rcx, [rsp+28h]; this
0x14000c137  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c13e  mov     r9d, ebx; char *
0x14000c141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c146  mov     eax, ebx
0x14000c148  add     rsp, 20h
0x14000c14c  pop     rbx
0x14000c14d  retn
```

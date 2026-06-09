# CWuaClassFactoryBase::ContextCallback_Unregister(tagComCallData *)

- ea: `0x180031380`
- end: `0x180031433`
- name: `?ContextCallback_Unregister@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z`
- size: `179`
- prototype: `static int(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003950`
- `0x180031380`
- `0x180031490`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180031401`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x180031401`

## string_xrefs

- `0x1800313e6`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x180031417`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

## pseudocode

```c
__int64 __fastcall CWuaClassFactoryBase::ContextCallback_Unregister(struct tagComCallData *a1)
{
  unsigned int v1; // ebx
  __int64 v2; // rdx
  void *pUserDefined; // rbx
  IUnknown *v4; // rcx
  int v5; // eax
  unsigned int v6; // edi
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v2 = 477;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)v1,
      v8);
    return v1;
  }
  pUserDefined = a1->pUserDefined;
  if ( !pUserDefined )
  {
    v1 = -2147024809;
    v2 = 478;
    goto LABEL_13;
  }
  if ( *(_DWORD *)pUserDefined != 24 )
  {
    v1 = -2147024809;
    v2 = 483;
    goto LABEL_13;
  }
  v4 = (IUnknown *)*((_QWORD *)pUserDefined + 1);
  if ( !v4 )
  {
    v1 = -2147024809;
    v2 = 484;
    goto LABEL_13;
  }
  v5 = CWuaClassFactoryBase::UnregisterClassFactoryImpl(v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdcom.cpp",
      (const char *)(unsigned int)v5,
      v8);
    return v6;
  }
  v1 = CoDisconnectContext(*((_DWORD *)pUserDefined + 4));
  if ( (v1 & 0x80000000) != 0 )
  {
    v2 = 493;
    goto LABEL_13;
  }
  return v1;
}

```

## disassembly

```asm
0x180031380  mov     [rsp+arg_0], rbx
0x180031385  push    rdi; int
0x180031386  sub     rsp, 20h
0x18003138a  test    rcx, rcx
0x18003138d  jnz     short loc_18003139B
0x18003138f  mov     ebx, 80004003h
0x180031394  mov     edx, 1DDh
0x180031399  jmp     short loc_180031412
0x18003139b  mov     rbx, [rcx+8]
0x18003139f  test    rbx, rbx
0x1800313a2  jnz     short loc_1800313B0
0x1800313a4  mov     ebx, 80070057h
0x1800313a9  mov     edx, 1DEh
0x1800313ae  jmp     short loc_180031412
0x1800313b0  cmp     dword ptr [rbx], 18h
0x1800313b3  jz      short loc_1800313C1
0x1800313b5  mov     ebx, 80070057h
0x1800313ba  mov     edx, 1E3h
0x1800313bf  jmp     short loc_180031412
0x1800313c1  mov     rcx, [rbx+8]; pUnk
0x1800313c5  test    rcx, rcx
0x1800313c8  jnz     short loc_1800313D6
0x1800313ca  mov     ebx, 80070057h
0x1800313cf  mov     edx, 1E4h
0x1800313d4  jmp     short loc_180031412
0x1800313d6  call    ?UnregisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::UnregisterClassFactoryImpl(void)
0x1800313db  mov     edi, eax
0x1800313dd  test    eax, eax
0x1800313df  jns     short loc_1800313FE
0x1800313e1  mov     rcx, [rsp+28h]; this
0x1800313e6  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1800313ed  mov     r9d, eax; char *
0x1800313f0  mov     edx, 1E8h; void *
0x1800313f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800313fa  mov     eax, edi
0x1800313fc  jmp     short loc_180031428
0x1800313fe  mov     ecx, [rbx+10h]; dwTimeout
0x180031401  call    cs:__imp_CoDisconnectContext
0x180031407  mov     ebx, eax
0x180031409  test    eax, eax
0x18003140b  jns     short loc_180031426
0x18003140d  mov     edx, 1EDh; void *
0x180031412  mov     rcx, [rsp+28h]; this
0x180031417  lea     r8, aCW1SSrcClientL_27; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18003141e  mov     r9d, ebx; char *
0x180031421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031426  mov     eax, ebx
0x180031428  mov     rbx, [rsp+28h+arg_0]
0x18003142d  add     rsp, 20h
0x180031431  pop     rdi
0x180031432  retn
```

# CWuaClassFactoryBase::ContextCallback_Unregister(tagComCallData *)

- ea: `0x14000c160`
- end: `0x14000c213`
- name: `?ContextCallback_Unregister@CWuaClassFactoryBase@@CAJPEAUtagComCallData@@@Z`
- size: `179`
- prototype: `static int(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002ac0`
- `0x14000c160`
- `0x14000c270`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x14000c1e1`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x14000c1e1`

## string_xrefs

- `0x14000c1c6`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`
- `0x14000c1f7`: `C:\__w\1\s\src\Client\lib\util\sdcom.cpp`

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
0x14000c160  mov     [rsp+arg_0], rbx
0x14000c165  push    rdi; int
0x14000c166  sub     rsp, 20h
0x14000c16a  test    rcx, rcx
0x14000c16d  jnz     short loc_14000C17B
0x14000c16f  mov     ebx, 80004003h
0x14000c174  mov     edx, 1DDh
0x14000c179  jmp     short loc_14000C1F2
0x14000c17b  mov     rbx, [rcx+8]
0x14000c17f  test    rbx, rbx
0x14000c182  jnz     short loc_14000C190
0x14000c184  mov     ebx, 80070057h
0x14000c189  mov     edx, 1DEh
0x14000c18e  jmp     short loc_14000C1F2
0x14000c190  cmp     dword ptr [rbx], 18h
0x14000c193  jz      short loc_14000C1A1
0x14000c195  mov     ebx, 80070057h
0x14000c19a  mov     edx, 1E3h
0x14000c19f  jmp     short loc_14000C1F2
0x14000c1a1  mov     rcx, [rbx+8]; pUnk
0x14000c1a5  test    rcx, rcx
0x14000c1a8  jnz     short loc_14000C1B6
0x14000c1aa  mov     ebx, 80070057h
0x14000c1af  mov     edx, 1E4h
0x14000c1b4  jmp     short loc_14000C1F2
0x14000c1b6  call    ?UnregisterClassFactoryImpl@CWuaClassFactoryBase@@AEAAJXZ; CWuaClassFactoryBase::UnregisterClassFactoryImpl(void)
0x14000c1bb  mov     edi, eax
0x14000c1bd  test    eax, eax
0x14000c1bf  jns     short loc_14000C1DE
0x14000c1c1  mov     rcx, [rsp+28h]; this
0x14000c1c6  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c1cd  mov     r9d, eax; char *
0x14000c1d0  mov     edx, 1E8h; void *
0x14000c1d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c1da  mov     eax, edi
0x14000c1dc  jmp     short loc_14000C208
0x14000c1de  mov     ecx, [rbx+10h]; dwTimeout
0x14000c1e1  call    cs:__imp_CoDisconnectContext
0x14000c1e7  mov     ebx, eax
0x14000c1e9  test    eax, eax
0x14000c1eb  jns     short loc_14000C206
0x14000c1ed  mov     edx, 1EDh; void *
0x14000c1f2  mov     rcx, [rsp+28h]; this
0x14000c1f7  lea     r8, aCW1SSrcClientL_10; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x14000c1fe  mov     r9d, ebx; char *
0x14000c201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c206  mov     eax, ebx
0x14000c208  mov     rbx, [rsp+28h+arg_0]
0x14000c20d  add     rsp, 20h
0x14000c211  pop     rdi
0x14000c212  retn
```

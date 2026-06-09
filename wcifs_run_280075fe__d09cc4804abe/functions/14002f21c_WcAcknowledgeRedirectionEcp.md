# WcAcknowledgeRedirectionEcp

- ea: `0x14002f21c`
- end: `0x14002f3c3`
- name: `WcAcknowledgeRedirectionEcp`
- size: `423`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140025220`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140001bc8`
- `0x140001fd0`
- `0x1400024fc`
- `0x14002f21c`

## import_xrefs

- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002f269`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002f269`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f37e`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f37e`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002f29c`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002f29c`
- `FLTMGR!FltReleaseContext` at `0x14002f392`
- `FLTMGR!FltReleaseContext` at `0x14002f3a6`
- `FLTMGR!FltReleaseContext` at `0x14002f392`
- `FLTMGR!FltReleaseContext` at `0x14002f3a6`

## pseudocode

```c
void __fastcall WcAcknowledgeRedirectionEcp(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject)
{
  char ContextFileObject; // al
  PFLT_CONTEXT v6; // rdi
  char *v7; // rbx
  __int64 Source; // r8
  PVOID EcpContext; // [rsp+30h] [rbp-20h] BYREF
  PECP_LIST EcpList; // [rsp+38h] [rbp-18h] BYREF
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-10h]
  PFLT_CONTEXT v12; // [rsp+48h] [rbp-8h]
  ULONG EcpContextSize; // [rsp+78h] [rbp+28h] BYREF

  EcpList = 0;
  EcpContext = 0;
  Context = 0;
  v12 = 0;
  EcpContextSize = 0;
  if ( FltGetEcpListFromCallbackData(Globals, CallbackData, &EcpList) >= 0
    && FltFindExtraCreateParameter(Globals, EcpList, &GUID_ECP_CREATE_REDIRECTION, &EcpContext, &EcpContextSize) >= 0 )
  {
    *((_WORD *)EcpContext + 1) |= 2u;
    ContextFileObject = WcGetContextFileObject(Instance, FileObject);
    v6 = Context;
    v7 = (char *)v12;
    if ( ContextFileObject
      && ((unsigned __int8)WcIsPlaceHolderStream(Context, v12) || (unsigned __int8)WcIsPlaceHolderDirectory(v6, v7))
      && (unsigned __int8)WcIsSourcedStream(v7) )
    {
      Source = WcGetSource(v7);
      *((_WORD *)EcpContext + 1) &= ~2u;
      *((_WORD *)EcpContext + 1) |= 1u;
      if ( (*(_DWORD *)(*(_QWORD *)(Source + 32) + 16LL) & 2) != 0 )
        *((_WORD *)EcpContext + 1) |= 4u;
      if ( (*(_DWORD *)(*(_QWORD *)(Source + 32) + 16LL) & 1) != 0 )
      {
        *((_WORD *)EcpContext + 1) |= 8u;
      }
      else if ( EcpContextSize >= 0x24 )
      {
        *(_OWORD *)((char *)EcpContext + 4) = *(_OWORD *)(v7 + 84);
        *(_OWORD *)((char *)EcpContext + 20) = *(_OWORD *)(v7 + 100);
      }
    }
    FltAcknowledgeEcp(Globals, EcpContext);
    if ( v6 )
      FltReleaseContext(v6);
    if ( v7 )
      FltReleaseContext(v7);
  }
}

```

## disassembly

```asm
0x14002f21c  mov     [rsp-8+arg_0], rbx
0x14002f221  mov     [rsp-8+arg_8], rdi
0x14002f226  push    rbp
0x14002f227  mov     rbp, rsp
0x14002f22a  sub     rsp, 50h
0x14002f22e  mov     rdi, rdx
0x14002f231  mov     [rbp+EcpList], 0
0x14002f239  mov     rdx, rcx; CallbackData
0x14002f23c  mov     [rbp+EcpContext], 0
0x14002f244  mov     rcx, cs:Globals; Filter
0x14002f24b  mov     rbx, r8
0x14002f24e  lea     r8, [rbp+EcpList]; EcpList
0x14002f252  mov     [rbp+Context], 0
0x14002f25a  mov     [rbp+var_8], 0
0x14002f262  mov     [rbp+arg_18], 0
0x14002f269  call    cs:__imp_FltGetEcpListFromCallbackData
0x14002f270  nop     dword ptr [rax+rax+00h]
0x14002f275  test    eax, eax
0x14002f277  js      loc_14002F3B2
0x14002f27d  mov     rdx, [rbp+EcpList]; EcpList
0x14002f281  lea     rax, [rbp+arg_18]
0x14002f285  mov     rcx, cs:Globals; Filter
0x14002f28c  lea     r9, [rbp+EcpContext]; EcpContext
0x14002f290  lea     r8, GUID_ECP_CREATE_REDIRECTION; EcpType
0x14002f297  mov     [rsp+50h+EcpContextSize], rax; EcpContextSize
0x14002f29c  call    cs:__imp_FltFindExtraCreateParameter
0x14002f2a3  nop     dword ptr [rax+rax+00h]
0x14002f2a8  test    eax, eax
0x14002f2aa  js      loc_14002F3B2
0x14002f2b0  mov     rax, [rbp+EcpContext]
0x14002f2b4  lea     r9, [rbp+var_8]
0x14002f2b8  lea     r8, [rbp+Context]
0x14002f2bc  mov     rdx, rbx; FileObject
0x14002f2bf  mov     rcx, rdi; Instance
0x14002f2c2  or      word ptr [rax+2], 2
0x14002f2c7  call    WcGetContextFileObject
0x14002f2cc  mov     rdi, [rbp+Context]
0x14002f2d0  mov     rbx, [rbp+var_8]
0x14002f2d4  test    al, al
0x14002f2d6  jz      loc_14002F373
0x14002f2dc  mov     rdx, rbx
0x14002f2df  mov     rcx, rdi
0x14002f2e2  call    WcIsPlaceHolderStream
0x14002f2e7  test    al, al
0x14002f2e9  jnz     short loc_14002F2FA
0x14002f2eb  mov     rdx, rbx
0x14002f2ee  mov     rcx, rdi
0x14002f2f1  call    WcIsPlaceHolderDirectory
0x14002f2f6  test    al, al
0x14002f2f8  jz      short loc_14002F373
0x14002f2fa  mov     rcx, rbx
0x14002f2fd  call    WcIsSourcedStream
0x14002f302  test    al, al
0x14002f304  jz      short loc_14002F373
0x14002f306  mov     rcx, rbx
0x14002f309  call    WcGetSource
0x14002f30e  mov     rcx, [rbp+EcpContext]
0x14002f312  mov     r8, rax
0x14002f315  mov     eax, 0FFFDh
0x14002f31a  and     [rcx+2], ax
0x14002f31e  mov     rcx, [rbp+EcpContext]
0x14002f322  or      word ptr [rcx+2], 1
0x14002f327  mov     rcx, [r8+20h]
0x14002f32b  mov     edx, [rcx+10h]
0x14002f32e  test    dl, 2
0x14002f331  jz      short loc_14002F33C
0x14002f333  mov     rax, [rbp+EcpContext]
0x14002f337  or      word ptr [rax+2], 4
0x14002f33c  mov     rax, [r8+20h]
0x14002f340  mov     ecx, [rax+10h]
0x14002f343  test    cl, 1
0x14002f346  jz      short loc_14002F353
0x14002f348  mov     rax, [rbp+EcpContext]
0x14002f34c  or      word ptr [rax+2], 8
0x14002f351  jmp     short loc_14002F373
0x14002f353  cmp     [rbp+arg_18], 24h ; '$'
0x14002f357  jb      short loc_14002F373
0x14002f359  mov     rax, [rbp+EcpContext]
0x14002f35d  movups  xmm0, xmmword ptr [rbx+54h]
0x14002f361  movdqu  xmmword ptr [rax+4], xmm0
0x14002f366  mov     rax, [rbp+EcpContext]
0x14002f36a  movups  xmm1, xmmword ptr [rbx+64h]
0x14002f36e  movdqu  xmmword ptr [rax+14h], xmm1
0x14002f373  mov     rdx, [rbp+EcpContext]; EcpContext
0x14002f377  mov     rcx, cs:Globals; Filter
0x14002f37e  call    cs:__imp_FltAcknowledgeEcp
0x14002f385  nop     dword ptr [rax+rax+00h]
0x14002f38a  test    rdi, rdi
0x14002f38d  jz      short loc_14002F39E
0x14002f38f  mov     rcx, rdi; Context
0x14002f392  call    cs:__imp_FltReleaseContext
0x14002f399  nop     dword ptr [rax+rax+00h]
0x14002f39e  test    rbx, rbx
0x14002f3a1  jz      short loc_14002F3B2
0x14002f3a3  mov     rcx, rbx; Context
0x14002f3a6  call    cs:__imp_FltReleaseContext
0x14002f3ad  nop     dword ptr [rax+rax+00h]
0x14002f3b2  mov     rbx, [rsp+50h+arg_0]
0x14002f3b7  mov     rdi, [rsp+50h+arg_8]
0x14002f3bc  add     rsp, 50h
0x14002f3c0  pop     rbp
0x14002f3c1  retn
```

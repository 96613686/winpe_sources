# WcAcknowledgeRedirectionEcp

- ea: `0x14002f26c`
- end: `0x14002f413`
- name: `WcAcknowledgeRedirectionEcp`
- size: `423`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140025270`

## callees

- `0x140001500`
- `0x140001b94`
- `0x140001bc8`
- `0x140001fd0`
- `0x1400024fc`
- `0x14002f26c`

## import_xrefs

- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002f2b9`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14002f2b9`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f3ce`
- `FLTMGR!FltAcknowledgeEcp` at `0x14002f3ce`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002f2ec`
- `FLTMGR!FltFindExtraCreateParameter` at `0x14002f2ec`
- `FLTMGR!FltReleaseContext` at `0x14002f3e2`
- `FLTMGR!FltReleaseContext` at `0x14002f3f6`
- `FLTMGR!FltReleaseContext` at `0x14002f3e2`
- `FLTMGR!FltReleaseContext` at `0x14002f3f6`

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
0x14002f26c  mov     [rsp-8+arg_0], rbx
0x14002f271  mov     [rsp-8+arg_8], rdi
0x14002f276  push    rbp
0x14002f277  mov     rbp, rsp
0x14002f27a  sub     rsp, 50h
0x14002f27e  mov     rdi, rdx
0x14002f281  mov     [rbp+EcpList], 0
0x14002f289  mov     rdx, rcx; CallbackData
0x14002f28c  mov     [rbp+EcpContext], 0
0x14002f294  mov     rcx, cs:Globals; Filter
0x14002f29b  mov     rbx, r8
0x14002f29e  lea     r8, [rbp+EcpList]; EcpList
0x14002f2a2  mov     [rbp+Context], 0
0x14002f2aa  mov     [rbp+var_8], 0
0x14002f2b2  mov     [rbp+arg_18], 0
0x14002f2b9  call    cs:__imp_FltGetEcpListFromCallbackData
0x14002f2c0  nop     dword ptr [rax+rax+00h]
0x14002f2c5  test    eax, eax
0x14002f2c7  js      loc_14002F402
0x14002f2cd  mov     rdx, [rbp+EcpList]; EcpList
0x14002f2d1  lea     rax, [rbp+arg_18]
0x14002f2d5  mov     rcx, cs:Globals; Filter
0x14002f2dc  lea     r9, [rbp+EcpContext]; EcpContext
0x14002f2e0  lea     r8, GUID_ECP_CREATE_REDIRECTION; EcpType
0x14002f2e7  mov     [rsp+50h+EcpContextSize], rax; EcpContextSize
0x14002f2ec  call    cs:__imp_FltFindExtraCreateParameter
0x14002f2f3  nop     dword ptr [rax+rax+00h]
0x14002f2f8  test    eax, eax
0x14002f2fa  js      loc_14002F402
0x14002f300  mov     rax, [rbp+EcpContext]
0x14002f304  lea     r9, [rbp+var_8]
0x14002f308  lea     r8, [rbp+Context]
0x14002f30c  mov     rdx, rbx; FileObject
0x14002f30f  mov     rcx, rdi; Instance
0x14002f312  or      word ptr [rax+2], 2
0x14002f317  call    WcGetContextFileObject
0x14002f31c  mov     rdi, [rbp+Context]
0x14002f320  mov     rbx, [rbp+var_8]
0x14002f324  test    al, al
0x14002f326  jz      loc_14002F3C3
0x14002f32c  mov     rdx, rbx
0x14002f32f  mov     rcx, rdi
0x14002f332  call    WcIsPlaceHolderStream
0x14002f337  test    al, al
0x14002f339  jnz     short loc_14002F34A
0x14002f33b  mov     rdx, rbx
0x14002f33e  mov     rcx, rdi
0x14002f341  call    WcIsPlaceHolderDirectory
0x14002f346  test    al, al
0x14002f348  jz      short loc_14002F3C3
0x14002f34a  mov     rcx, rbx
0x14002f34d  call    WcIsSourcedStream
0x14002f352  test    al, al
0x14002f354  jz      short loc_14002F3C3
0x14002f356  mov     rcx, rbx
0x14002f359  call    WcGetSource
0x14002f35e  mov     rcx, [rbp+EcpContext]
0x14002f362  mov     r8, rax
0x14002f365  mov     eax, 0FFFDh
0x14002f36a  and     [rcx+2], ax
0x14002f36e  mov     rcx, [rbp+EcpContext]
0x14002f372  or      word ptr [rcx+2], 1
0x14002f377  mov     rcx, [r8+20h]
0x14002f37b  mov     edx, [rcx+10h]
0x14002f37e  test    dl, 2
0x14002f381  jz      short loc_14002F38C
0x14002f383  mov     rax, [rbp+EcpContext]
0x14002f387  or      word ptr [rax+2], 4
0x14002f38c  mov     rax, [r8+20h]
0x14002f390  mov     ecx, [rax+10h]
0x14002f393  test    cl, 1
0x14002f396  jz      short loc_14002F3A3
0x14002f398  mov     rax, [rbp+EcpContext]
0x14002f39c  or      word ptr [rax+2], 8
0x14002f3a1  jmp     short loc_14002F3C3
0x14002f3a3  cmp     [rbp+arg_18], 24h ; '$'
0x14002f3a7  jb      short loc_14002F3C3
0x14002f3a9  mov     rax, [rbp+EcpContext]
0x14002f3ad  movups  xmm0, xmmword ptr [rbx+54h]
0x14002f3b1  movdqu  xmmword ptr [rax+4], xmm0
0x14002f3b6  mov     rax, [rbp+EcpContext]
0x14002f3ba  movups  xmm1, xmmword ptr [rbx+64h]
0x14002f3be  movdqu  xmmword ptr [rax+14h], xmm1
0x14002f3c3  mov     rdx, [rbp+EcpContext]; EcpContext
0x14002f3c7  mov     rcx, cs:Globals; Filter
0x14002f3ce  call    cs:__imp_FltAcknowledgeEcp
0x14002f3d5  nop     dword ptr [rax+rax+00h]
0x14002f3da  test    rdi, rdi
0x14002f3dd  jz      short loc_14002F3EE
0x14002f3df  mov     rcx, rdi; Context
0x14002f3e2  call    cs:__imp_FltReleaseContext
0x14002f3e9  nop     dword ptr [rax+rax+00h]
0x14002f3ee  test    rbx, rbx
0x14002f3f1  jz      short loc_14002F402
0x14002f3f3  mov     rcx, rbx; Context
0x14002f3f6  call    cs:__imp_FltReleaseContext
0x14002f3fd  nop     dword ptr [rax+rax+00h]
0x14002f402  mov     rbx, [rsp+50h+arg_0]
0x14002f407  mov     rdi, [rsp+50h+arg_8]
0x14002f40c  add     rsp, 50h
0x14002f410  pop     rbp
0x14002f411  retn
```

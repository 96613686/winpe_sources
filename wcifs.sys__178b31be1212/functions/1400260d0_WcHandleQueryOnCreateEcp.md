# WcHandleQueryOnCreateEcp

- ea: `0x1400260d0`
- end: `0x140026257`
- name: `WcHandleQueryOnCreateEcp`
- size: `391`
- prototype: `void __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400149c0`
- `0x140025270`
- `0x140028ad0`

## callees

- `0x140001500`
- `0x140001580`
- `0x140001b94`
- `0x140001bc8`
- `0x1400260d0`

## import_xrefs

- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140026121`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140026121`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140026170`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140026170`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140026155`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140026155`
- `FLTMGR!FltReleaseContext` at `0x1400261e6`
- `FLTMGR!FltReleaseContext` at `0x1400261fa`
- `FLTMGR!FltReleaseContext` at `0x1400261e6`
- `FLTMGR!FltReleaseContext` at `0x1400261fa`

## pseudocode

```c
void __fastcall WcHandleQueryOnCreateEcp(
        PFLT_CALLBACK_DATA CallbackData,
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject)
{
  PFLT_CONTEXT v6; // rdi
  PFLT_CONTEXT v7; // rbx
  _DWORD *v8; // rcx
  unsigned int v9; // eax
  char ContextFileObject; // al
  ULONG EcpContextSize; // [rsp+30h] [rbp-38h] BYREF
  PVOID EcpContext; // [rsp+38h] [rbp-30h] BYREF
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-28h] BYREF
  PFLT_CONTEXT v14; // [rsp+48h] [rbp-20h] BYREF
  PECP_LIST EcpList; // [rsp+50h] [rbp-18h] BYREF
  int v16; // [rsp+B8h] [rbp+50h] BYREF

  EcpList = 0;
  EcpContext = 0;
  EcpContextSize = 0;
  v16 = 0;
  v6 = 0;
  v7 = 0;
  Context = 0;
  v14 = 0;
  if ( FltGetEcpListFromCallbackData(Globals, CallbackData, &EcpList) < 0 )
    return;
  if ( !EcpList )
    return;
  if ( FltFindExtraCreateParameter(Globals, EcpList, &GUID_ECP_QUERY_ON_CREATE, &EcpContext, &EcpContextSize) < 0 )
    return;
  if ( !FltIsEcpAcknowledged(Globals, EcpContext) )
    return;
  if ( (*((_DWORD *)EcpContext + 1) & 1) == 0 )
    return;
  if ( !(unsigned __int8)WcUnionsExistForInstance(Instance, FileObject, &v16, 0) )
    return;
  v8 = EcpContext;
  if ( *((_DWORD *)EcpContext + 19) != v16 )
    return;
  if ( CallbackData->Iopb->MajorFunction )
    goto LABEL_10;
  ContextFileObject = WcGetContextFileObject(Instance, FileObject, &Context, &v14);
  v7 = v14;
  v6 = Context;
  if ( ContextFileObject
    && ((unsigned __int8)WcIsPlaceHolderStream(Context, v14) || (unsigned __int8)WcIsPlaceHolderDirectory(v6, v7)) )
  {
    v8 = EcpContext;
LABEL_10:
    v9 = v8[18] & 0xFFFFE9FF;
    if ( !v9 )
      v9 = 128;
    v8[18] = v9;
    *((_DWORD *)EcpContext + 19) = 0;
  }
  if ( v6 )
    FltReleaseContext(v6);
  if ( v7 )
    FltReleaseContext(v7);
}

```

## disassembly

```asm
0x1400260d0  push    rbp
0x1400260d2  push    rbx
0x1400260d3  push    rsi
0x1400260d4  push    rdi
0x1400260d5  push    r14
0x1400260d7  push    r15
0x1400260d9  mov     rbp, rsp
0x1400260dc  sub     rsp, 68h
0x1400260e0  mov     r14, rdx
0x1400260e3  mov     [rbp+EcpList], 0
0x1400260eb  mov     rdx, rcx; CallbackData
0x1400260ee  mov     [rbp+EcpContext], 0
0x1400260f6  mov     rsi, r8
0x1400260f9  mov     [rbp+var_38], 0
0x140026100  mov     r15, rcx
0x140026103  mov     [rbp+arg_18], 0
0x14002610a  mov     rcx, cs:Globals; Filter
0x140026111  lea     r8, [rbp+EcpList]; EcpList
0x140026115  xor     edi, edi
0x140026117  xor     ebx, ebx
0x140026119  mov     [rbp+Context], rdi
0x14002611d  mov     [rbp+var_20], rbx
0x140026121  call    cs:__imp_FltGetEcpListFromCallbackData
0x140026128  nop     dword ptr [rax+rax+00h]
0x14002612d  test    eax, eax
0x14002612f  js      short loc_1400261AE
0x140026131  mov     rdx, [rbp+EcpList]; EcpList
0x140026135  test    rdx, rdx
0x140026138  jz      short loc_1400261AE
0x14002613a  mov     rcx, cs:Globals; Filter
0x140026141  lea     rax, [rbp+var_38]
0x140026145  lea     r9, [rbp+EcpContext]; EcpContext
0x140026149  mov     [rsp+68h+EcpContextSize], rax; EcpContextSize
0x14002614e  lea     r8, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140026155  call    cs:__imp_FltFindExtraCreateParameter
0x14002615c  nop     dword ptr [rax+rax+00h]
0x140026161  test    eax, eax
0x140026163  js      short loc_1400261AE
0x140026165  mov     rdx, [rbp+EcpContext]; EcpContext
0x140026169  mov     rcx, cs:Globals; Filter
0x140026170  call    cs:__imp_FltIsEcpAcknowledged
0x140026177  nop     dword ptr [rax+rax+00h]
0x14002617c  test    al, al
0x14002617e  jz      short loc_1400261AE
0x140026180  mov     rax, [rbp+EcpContext]
0x140026184  mov     ecx, [rax+4]
0x140026187  test    cl, 1
0x14002618a  jz      short loc_1400261AE
0x14002618c  xor     r9d, r9d
0x14002618f  lea     r8, [rbp+arg_18]
0x140026193  mov     rdx, rsi
0x140026196  mov     rcx, r14
0x140026199  call    WcUnionsExistForInstance
0x14002619e  test    al, al
0x1400261a0  jz      short loc_1400261AE
0x1400261a2  mov     rcx, [rbp+EcpContext]
0x1400261a6  mov     eax, [rbp+arg_18]
0x1400261a9  cmp     [rcx+4Ch], eax
0x1400261ac  jz      short loc_140026208
0x1400261ae  add     rsp, 68h
0x1400261b2  pop     r15
0x1400261b4  pop     r14
0x1400261b6  pop     rdi
0x1400261b7  pop     rsi
0x1400261b8  pop     rbx
0x1400261b9  pop     rbp
0x1400261ba  retn
0x1400261bc  mov     rcx, [rbp+EcpContext]
0x1400261c0  mov     eax, [rcx+48h]
0x1400261c3  mov     edx, 80h
0x1400261c8  and     eax, 0FFFFE9FFh
0x1400261cd  cmovz   eax, edx
0x1400261d0  mov     [rcx+48h], eax
0x1400261d3  mov     rax, [rbp+EcpContext]
0x1400261d7  mov     dword ptr [rax+4Ch], 0
0x1400261de  test    rdi, rdi
0x1400261e1  jz      short loc_1400261F2
0x1400261e3  mov     rcx, rdi; Context
0x1400261e6  call    cs:__imp_FltReleaseContext
0x1400261ed  nop     dword ptr [rax+rax+00h]
0x1400261f2  test    rbx, rbx
0x1400261f5  jz      short loc_1400261AE
0x1400261f7  mov     rcx, rbx; Context
0x1400261fa  call    cs:__imp_FltReleaseContext
0x140026201  nop     dword ptr [rax+rax+00h]
0x140026206  jmp     short loc_1400261AE
0x140026208  mov     rax, [r15+10h]
0x14002620c  cmp     [rax+4], bl
0x14002620f  jnz     short loc_1400261C0
0x140026211  lea     r9, [rbp+var_20]
0x140026215  mov     rdx, rsi; FileObject
0x140026218  lea     r8, [rbp+Context]
0x14002621c  mov     rcx, r14; Instance
0x14002621f  call    WcGetContextFileObject
0x140026224  mov     rbx, [rbp+var_20]
0x140026228  mov     rdi, [rbp+Context]
0x14002622c  test    al, al
0x14002622e  jz      short loc_1400261DE
0x140026230  mov     rdx, rbx
0x140026233  mov     rcx, rdi
0x140026236  call    WcIsPlaceHolderStream
0x14002623b  test    al, al
0x14002623d  jnz     loc_1400261BC
0x140026243  mov     rdx, rbx
0x140026246  mov     rcx, rdi
0x140026249  call    WcIsPlaceHolderDirectory
0x14002624e  test    al, al
0x140026250  jz      short loc_1400261DE
0x140026252  jmp     loc_1400261BC
```

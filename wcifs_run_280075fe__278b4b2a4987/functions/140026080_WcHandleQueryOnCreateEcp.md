# WcHandleQueryOnCreateEcp

- ea: `0x140026080`
- end: `0x140026207`
- name: `WcHandleQueryOnCreateEcp`
- size: `391`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400149c0`
- `0x140025220`
- `0x140028a80`

## callees

- `0x140001500`
- `0x140001580`
- `0x140001b94`
- `0x140001bc8`
- `0x140026080`

## import_xrefs

- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400260d1`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x1400260d1`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140026120`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140026120`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140026105`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140026105`
- `FLTMGR!FltReleaseContext` at `0x140026196`
- `FLTMGR!FltReleaseContext` at `0x1400261aa`
- `FLTMGR!FltReleaseContext` at `0x140026196`
- `FLTMGR!FltReleaseContext` at `0x1400261aa`

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
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-28h]
  PFLT_CONTEXT v14; // [rsp+48h] [rbp-20h]
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
  ContextFileObject = WcGetContextFileObject(Instance, FileObject);
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
0x140026080  push    rbp
0x140026082  push    rbx
0x140026083  push    rsi
0x140026084  push    rdi
0x140026085  push    r14
0x140026087  push    r15
0x140026089  mov     rbp, rsp
0x14002608c  sub     rsp, 68h
0x140026090  mov     r14, rdx
0x140026093  mov     [rbp+EcpList], 0
0x14002609b  mov     rdx, rcx; CallbackData
0x14002609e  mov     [rbp+EcpContext], 0
0x1400260a6  mov     rsi, r8
0x1400260a9  mov     [rbp+var_38], 0
0x1400260b0  mov     r15, rcx
0x1400260b3  mov     [rbp+arg_18], 0
0x1400260ba  mov     rcx, cs:Globals; Filter
0x1400260c1  lea     r8, [rbp+EcpList]; EcpList
0x1400260c5  xor     edi, edi
0x1400260c7  xor     ebx, ebx
0x1400260c9  mov     [rbp+Context], rdi
0x1400260cd  mov     [rbp+var_20], rbx
0x1400260d1  call    cs:__imp_FltGetEcpListFromCallbackData
0x1400260d8  nop     dword ptr [rax+rax+00h]
0x1400260dd  test    eax, eax
0x1400260df  js      short loc_14002615E
0x1400260e1  mov     rdx, [rbp+EcpList]; EcpList
0x1400260e5  test    rdx, rdx
0x1400260e8  jz      short loc_14002615E
0x1400260ea  mov     rcx, cs:Globals; Filter
0x1400260f1  lea     rax, [rbp+var_38]
0x1400260f5  lea     r9, [rbp+EcpContext]; EcpContext
0x1400260f9  mov     [rsp+68h+EcpContextSize], rax; EcpContextSize
0x1400260fe  lea     r8, GUID_ECP_QUERY_ON_CREATE; EcpType
0x140026105  call    cs:__imp_FltFindExtraCreateParameter
0x14002610c  nop     dword ptr [rax+rax+00h]
0x140026111  test    eax, eax
0x140026113  js      short loc_14002615E
0x140026115  mov     rdx, [rbp+EcpContext]; EcpContext
0x140026119  mov     rcx, cs:Globals; Filter
0x140026120  call    cs:__imp_FltIsEcpAcknowledged
0x140026127  nop     dword ptr [rax+rax+00h]
0x14002612c  test    al, al
0x14002612e  jz      short loc_14002615E
0x140026130  mov     rax, [rbp+EcpContext]
0x140026134  mov     ecx, [rax+4]
0x140026137  test    cl, 1
0x14002613a  jz      short loc_14002615E
0x14002613c  xor     r9d, r9d
0x14002613f  lea     r8, [rbp+arg_18]
0x140026143  mov     rdx, rsi
0x140026146  mov     rcx, r14
0x140026149  call    WcUnionsExistForInstance
0x14002614e  test    al, al
0x140026150  jz      short loc_14002615E
0x140026152  mov     rcx, [rbp+EcpContext]
0x140026156  mov     eax, [rbp+arg_18]
0x140026159  cmp     [rcx+4Ch], eax
0x14002615c  jz      short loc_1400261B8
0x14002615e  add     rsp, 68h
0x140026162  pop     r15
0x140026164  pop     r14
0x140026166  pop     rdi
0x140026167  pop     rsi
0x140026168  pop     rbx
0x140026169  pop     rbp
0x14002616a  retn
0x14002616c  mov     rcx, [rbp+EcpContext]
0x140026170  mov     eax, [rcx+48h]
0x140026173  mov     edx, 80h
0x140026178  and     eax, 0FFFFE9FFh
0x14002617d  cmovz   eax, edx
0x140026180  mov     [rcx+48h], eax
0x140026183  mov     rax, [rbp+EcpContext]
0x140026187  mov     dword ptr [rax+4Ch], 0
0x14002618e  test    rdi, rdi
0x140026191  jz      short loc_1400261A2
0x140026193  mov     rcx, rdi; Context
0x140026196  call    cs:__imp_FltReleaseContext
0x14002619d  nop     dword ptr [rax+rax+00h]
0x1400261a2  test    rbx, rbx
0x1400261a5  jz      short loc_14002615E
0x1400261a7  mov     rcx, rbx; Context
0x1400261aa  call    cs:__imp_FltReleaseContext
0x1400261b1  nop     dword ptr [rax+rax+00h]
0x1400261b6  jmp     short loc_14002615E
0x1400261b8  mov     rax, [r15+10h]
0x1400261bc  cmp     [rax+4], bl
0x1400261bf  jnz     short loc_140026170
0x1400261c1  lea     r9, [rbp+var_20]
0x1400261c5  mov     rdx, rsi; FileObject
0x1400261c8  lea     r8, [rbp+Context]
0x1400261cc  mov     rcx, r14; Instance
0x1400261cf  call    WcGetContextFileObject
0x1400261d4  mov     rbx, [rbp+var_20]
0x1400261d8  mov     rdi, [rbp+Context]
0x1400261dc  test    al, al
0x1400261de  jz      short loc_14002618E
0x1400261e0  mov     rdx, rbx
0x1400261e3  mov     rcx, rdi
0x1400261e6  call    WcIsPlaceHolderStream
0x1400261eb  test    al, al
0x1400261ed  jnz     loc_14002616C
0x1400261f3  mov     rdx, rbx
0x1400261f6  mov     rcx, rdi
0x1400261f9  call    WcIsPlaceHolderDirectory
0x1400261fe  test    al, al
0x140026200  jz      short loc_14002618E
0x140026202  jmp     loc_14002616C
```

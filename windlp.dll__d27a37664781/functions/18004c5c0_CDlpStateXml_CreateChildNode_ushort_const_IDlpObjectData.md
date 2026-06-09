# CDlpStateXml::CreateChildNode(ushort const *,IDlpObjectData * *)

- ea: `0x18004c5c0`
- end: `0x18004c7f7`
- name: `?CreateChildNode@CDlpStateXml@@UEAAJPEBGPEAPEAVIDlpObjectData@@@Z`
- size: `567`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, const unsigned __int16 *, struct IDlpObjectData **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180028640`
- `0x18004c5c0`
- `0x18004d5d4`
- `0x1800667ac`
- `0x180068488`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c7ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004c7ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c7ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004c7ba`
- `UNATTEND!UnattendFreeNode` at `0x18004c712`
- `UNATTEND!UnattendFreeNode` at `0x18004c784`
- `UNATTEND!UnattendFreeNode` at `0x18004c78e`
- `UNATTEND!UnattendFreeNode` at `0x18004c712`
- `UNATTEND!UnattendFreeNode` at `0x18004c784`
- `UNATTEND!UnattendFreeNode` at `0x18004c78e`
- `UNATTEND!UnattendCtxOpenNode` at `0x18004c68d`
- `UNATTEND!UnattendCtxOpenNode` at `0x18004c68d`
- `UNATTEND!UnattendCtxCleanup` at `0x18004c798`
- `UNATTEND!UnattendCtxCleanup` at `0x18004c798`
- `UNATTEND!UnattendCtxBeginModify` at `0x18004c6db`
- `UNATTEND!UnattendCtxBeginModify` at `0x18004c6db`
- `UNATTEND!UnattendCtxCommitModify` at `0x18004c73a`
- `UNATTEND!UnattendCtxCommitModify` at `0x18004c73a`
- `UNATTEND!UnattendCtxDeserializeString` at `0x18004c676`
- `UNATTEND!UnattendCtxDeserializeString` at `0x18004c676`
- `UNATTEND!UnattendCtxSpliceTrees` at `0x18004c6fe`
- `UNATTEND!UnattendCtxSpliceTrees` at `0x18004c6fe`
- `UNATTEND!UnattendCtxGetCountByNode` at `0x18004c6c4`
- `UNATTEND!UnattendCtxGetCountByNode` at `0x18004c6c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDlpStateXml::CreateChildNode(
        struct _UNATTEND_CONTEXT **this,
        const unsigned __int16 *a2,
        struct IDlpObjectData **a3)
{
  unsigned __int16 *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int CountByNode; // eax
  int v10; // eax
  CDlpStateXml *v11; // rax
  HANDLE ProcessHeap; // rax
  __int64 v14; // [rsp+30h] [rbp-29h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-21h] BYREF
  __int128 v16; // [rsp+40h] [rbp-19h] BYREF
  __int128 v17; // [rsp+50h] [rbp-9h]
  __int64 v18; // [rsp+60h] [rbp+7h]
  _OWORD v19[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+88h] [rbp+2Fh]
  unsigned int v21; // [rsp+D0h] [rbp+77h] BYREF
  CDlpStateXml *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  v22 = 0;
  v6 = 0;
  v15 = 0;
  v21 = 0;
  v14 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
    v8 = 2147942487LL;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_18;
  }
  CountByNode = CDlpStateXml::CreateInstance(&v22);
  v7 = CountByNode;
  if ( CountByNode < 0 )
  {
LABEL_5:
    v8 = (unsigned int)CountByNode;
    goto LABEL_3;
  }
  v10 = STRAPI_Format(&v15, &qword_18009B400, a2, a2);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v6 = v15;
    CountByNode = UnattendCtxDeserializeString(&v14, v15);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = UnattendCtxOpenNode(&v14, a2, v19);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = CDlpStateXml::OpenCurrentNode((CDlpStateXml *)this, (struct _UNATTEND_NODE *)&v16);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    v21 = 0;
    CountByNode = UnattendCtxGetCountByNode(this[16], &v16, a2, &v21);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = UnattendCtxBeginModify(this[16]);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = UnattendCtxSpliceTrees(this[16], &v16, &v14, v19);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = UnattendFreeNode(&v16);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    v16 = 0;
    v17 = 0;
    v18 = 0;
    CountByNode = UnattendCtxCommitModify(this[16]);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    CountByNode = CDlpStateXml::InitializeNode(v22, (struct CDlpStateXml *)this, this[16], a2, v21);
    v7 = CountByNode;
    if ( CountByNode < 0 )
      goto LABEL_5;
    v11 = v22;
    v22 = 0;
    *a3 = v11;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    v6 = v15;
  }
LABEL_18:
  UnattendFreeNode(&v16);
  UnattendFreeNode(v19);
  UnattendCtxCleanup(&v14);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v22 )
    (*(void (__fastcall **)(CDlpStateXml *))(*(_QWORD *)v22 + 16LL))(v22);
  return v7;
}

```

## disassembly

```asm
0x18004c5c0  mov     [rsp-8+arg_0], rbx
0x18004c5c5  push    rbp
0x18004c5c6  push    rsi
0x18004c5c7  push    rdi
0x18004c5c8  push    r14
0x18004c5ca  push    r15
0x18004c5cc  lea     rbp, [rsp-37h]
0x18004c5d1  sub     rsp, 90h
0x18004c5d8  mov     r15, r8
0x18004c5db  mov     r14, rdx
0x18004c5de  mov     rsi, rcx
0x18004c5e1  mov     [rbp+57h+arg_18], 0
0x18004c5e9  xor     ebx, ebx
0x18004c5eb  mov     [rbp+57h+var_78], rbx
0x18004c5ef  mov     [rbp+57h+arg_10], ebx
0x18004c5f2  mov     [rbp+57h+var_80], rbx
0x18004c5f6  xorps   xmm0, xmm0
0x18004c5f9  xor     eax, eax
0x18004c5fb  movups  [rbp+57h+var_70], xmm0
0x18004c5ff  movups  [rbp+57h+var_60], xmm0
0x18004c603  mov     [rbp+57h+var_50], rax
0x18004c607  xorps   xmm1, xmm1
0x18004c60a  movups  [rbp+57h+var_48], xmm1
0x18004c60e  movups  [rbp+57h+var_38], xmm1
0x18004c612  mov     [rbp+57h+var_28], rax
0x18004c616  test    r8, r8
0x18004c619  jnz     short loc_18004C62C
0x18004c61b  mov     edi, 80070057h
0x18004c620  mov     ecx, edi
0x18004c622  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004c627  jmp     loc_18004C780
0x18004c62c  lea     rcx, [rbp+57h+arg_18]; struct CDlpStateXml **
0x18004c630  call    ?CreateInstance@CDlpStateXml@@SAJPEAPEAV1@@Z; CDlpStateXml::CreateInstance(CDlpStateXml * *)
0x18004c635  mov     edi, eax
0x18004c637  test    eax, eax
0x18004c639  jns     short loc_18004C63F
0x18004c63b  mov     ecx, eax
0x18004c63d  jmp     short loc_18004C622
0x18004c63f  mov     r9, r14
0x18004c642  mov     r8, r14
0x18004c645  lea     rdx, qword_18009B400; unsigned __int16 *
0x18004c64c  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x18004c650  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18004c655  mov     edi, eax
0x18004c657  test    eax, eax
0x18004c659  jns     short loc_18004C66B
0x18004c65b  mov     ecx, eax
0x18004c65d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18004c662  mov     rbx, [rbp+57h+var_78]
0x18004c666  jmp     loc_18004C780
0x18004c66b  mov     rbx, [rbp+57h+var_78]
0x18004c66f  mov     rdx, rbx
0x18004c672  lea     rcx, [rbp+57h+var_80]
0x18004c676  call    cs:__imp_UnattendCtxDeserializeString
0x18004c67c  mov     edi, eax
0x18004c67e  test    eax, eax
0x18004c680  js      short loc_18004C63B
0x18004c682  lea     r8, [rbp+57h+var_48]
0x18004c686  mov     rdx, r14
0x18004c689  lea     rcx, [rbp+57h+var_80]
0x18004c68d  call    cs:__imp_UnattendCtxOpenNode
0x18004c693  mov     edi, eax
0x18004c695  test    eax, eax
0x18004c697  js      short loc_18004C63B
0x18004c699  lea     rdx, [rbp+57h+var_70]; struct _UNATTEND_NODE *
0x18004c69d  mov     rcx, rsi; this
0x18004c6a0  call    ?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z; CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)
0x18004c6a5  mov     edi, eax
0x18004c6a7  test    eax, eax
0x18004c6a9  js      short loc_18004C63B
0x18004c6ab  mov     [rbp+57h+arg_10], 0
0x18004c6b2  lea     r9, [rbp+57h+arg_10]
0x18004c6b6  mov     r8, r14
0x18004c6b9  lea     rdx, [rbp+57h+var_70]
0x18004c6bd  mov     rcx, [rsi+80h]
0x18004c6c4  call    cs:__imp_UnattendCtxGetCountByNode
0x18004c6ca  mov     edi, eax
0x18004c6cc  test    eax, eax
0x18004c6ce  js      loc_18004C63B
0x18004c6d4  mov     rcx, [rsi+80h]
0x18004c6db  call    cs:__imp_UnattendCtxBeginModify
0x18004c6e1  mov     edi, eax
0x18004c6e3  test    eax, eax
0x18004c6e5  js      loc_18004C63B
0x18004c6eb  lea     r9, [rbp+57h+var_48]
0x18004c6ef  lea     r8, [rbp+57h+var_80]
0x18004c6f3  lea     rdx, [rbp+57h+var_70]
0x18004c6f7  mov     rcx, [rsi+80h]
0x18004c6fe  call    cs:__imp_UnattendCtxSpliceTrees
0x18004c704  mov     edi, eax
0x18004c706  test    eax, eax
0x18004c708  js      loc_18004C63B
0x18004c70e  lea     rcx, [rbp+57h+var_70]
0x18004c712  call    cs:__imp_UnattendFreeNode
0x18004c718  mov     edi, eax
0x18004c71a  test    eax, eax
0x18004c71c  js      loc_18004C63B
0x18004c722  xorps   xmm0, xmm0
0x18004c725  xor     eax, eax
0x18004c727  movups  [rbp+57h+var_70], xmm0
0x18004c72b  movups  [rbp+57h+var_60], xmm0
0x18004c72f  mov     [rbp+57h+var_50], rax
0x18004c733  mov     rcx, [rsi+80h]
0x18004c73a  call    cs:__imp_UnattendCtxCommitModify
0x18004c740  mov     edi, eax
0x18004c742  test    eax, eax
0x18004c744  js      loc_18004C63B
0x18004c74a  mov     eax, [rbp+57h+arg_10]
0x18004c74d  mov     [rsp+0B0h+var_90], eax; unsigned int
0x18004c751  mov     r9, r14; unsigned __int16 *
0x18004c754  mov     r8, [rsi+80h]; struct _UNATTEND_CONTEXT *
0x18004c75b  mov     rdx, rsi; struct CDlpStateXml *
0x18004c75e  mov     rcx, [rbp+57h+arg_18]; this
0x18004c762  call    ?InitializeNode@CDlpStateXml@@AEAAJPEAV1@PEAU_UNATTEND_CONTEXT@@PEBGK@Z; CDlpStateXml::InitializeNode(CDlpStateXml *,_UNATTEND_CONTEXT *,ushort const *,ulong)
0x18004c767  mov     edi, eax
0x18004c769  test    eax, eax
0x18004c76b  js      loc_18004C63B
0x18004c771  mov     rax, [rbp+57h+arg_18]
0x18004c775  mov     [rbp+57h+arg_18], 0
0x18004c77d  mov     [r15], rax
0x18004c780  lea     rcx, [rbp+57h+var_70]
0x18004c784  call    cs:__imp_UnattendFreeNode
0x18004c78a  lea     rcx, [rbp+57h+var_48]
0x18004c78e  call    cs:__imp_UnattendFreeNode
0x18004c794  lea     rcx, [rbp+57h+var_80]
0x18004c798  call    cs:__imp_UnattendCtxCleanup
0x18004c79e  mov     ecx, edi
0x18004c7a0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004c7a5  nop
0x18004c7a6  test    rbx, rbx
0x18004c7a9  jz      short loc_18004C7C8
0x18004c7ab  call    cs:__imp_GetProcessHeap
0x18004c7b1  mov     rcx, rax; hHeap
0x18004c7b4  lea     r8, [rbx-4]; lpMem
0x18004c7b8  xor     edx, edx; dwFlags
0x18004c7ba  call    cs:__imp_HeapFree
0x18004c7c0  xor     ecx, ecx
0x18004c7c2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18004c7c7  nop
0x18004c7c8  mov     rcx, [rbp+57h+arg_18]
0x18004c7cc  test    rcx, rcx
0x18004c7cf  jz      short loc_18004C7DE
0x18004c7d1  mov     rax, [rcx]
0x18004c7d4  mov     rax, [rax+10h]
0x18004c7d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c7dd  nop
0x18004c7de  mov     eax, edi
0x18004c7e0  mov     rbx, [rsp+0B0h+arg_0]
0x18004c7e8  add     rsp, 90h
0x18004c7ef  pop     r15
0x18004c7f1  pop     r14
0x18004c7f3  pop     rdi
0x18004c7f4  pop     rsi
0x18004c7f5  pop     rbp
0x18004c7f6  retn
```

# CDlpStateXml::SetDwordProperty(ushort const *,ulong)

- ea: `0x180073750`
- end: `0x180073862`
- name: `?SetDwordProperty@CDlpStateXml@@UEAAJPEBGK@Z`
- size: `274`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180028640`
- `0x180068488`
- `0x180073750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007383b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007383b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007384a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007384a`
- `UNATTEND!UnattendFreeNode` at `0x1800737ec`
- `UNATTEND!UnattendFreeNode` at `0x180073824`
- `UNATTEND!UnattendFreeNode` at `0x1800737ec`
- `UNATTEND!UnattendFreeNode` at `0x180073824`
- `UNATTEND!UnattendCtxBeginModify` at `0x1800737b9`
- `UNATTEND!UnattendCtxBeginModify` at `0x1800737b9`
- `UNATTEND!UnattendCtxCommitModify` at `0x18007380d`
- `UNATTEND!UnattendCtxCommitModify` at `0x18007380d`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x1800737dc`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x1800737dc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpStateXml::SetDwordProperty(CDlpStateXml *this, const unsigned __int16 *a2)
{
  unsigned int v4; // edi
  __int64 v5; // rcx
  int v6; // eax
  unsigned __int16 *v7; // rbx
  HANDLE ProcessHeap; // rax
  __int128 v10; // [rsp+30h] [rbp-38h] BYREF
  __int128 v11; // [rsp+40h] [rbp-28h]
  __int64 v12; // [rsp+50h] [rbp-18h]
  unsigned __int16 *v13; // [rsp+98h] [rbp+30h] BYREF

  v13 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    v5 = 2147942487LL;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  v6 = STRAPI_Format(&v13, L"%X");
  v4 = v6;
  if ( v6 < 0 )
    goto LABEL_9;
  v6 = CDlpStateXml::OpenCurrentNode((CDlpStateXml *)((char *)this - 8), (struct _UNATTEND_NODE *)&v10);
  v4 = v6;
  if ( v6 < 0 )
    goto LABEL_9;
  v6 = UnattendCtxBeginModify(*((_QWORD *)this + 15));
  v4 = v6;
  if ( v6 < 0 )
    goto LABEL_9;
  v6 = UnattendCtxSetStringByNode(*((_QWORD *)this + 15), &v10, a2, 0, v13);
  v4 = v6;
  if ( v6 < 0
    || (v6 = UnattendFreeNode(&v10), v4 = v6, v6 < 0)
    || (v10 = 0, v11 = 0, v12 = 0, v6 = UnattendCtxCommitModify(*((_QWORD *)this + 15)), v4 = v6, v6 < 0) )
  {
LABEL_9:
    v5 = (unsigned int)v6;
    goto LABEL_10;
  }
LABEL_11:
  UnattendFreeNode(&v10);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  v7 = v13;
  if ( v13 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v4;
}

```

## disassembly

```asm
0x180073750  push    rbp
0x180073752  push    rbx
0x180073753  push    rsi
0x180073754  push    rdi
0x180073755  mov     rbp, rsp
0x180073758  sub     rsp, 68h
0x18007375c  mov     rsi, rdx
0x18007375f  mov     rbx, rcx
0x180073762  mov     [rbp+arg_8], 0
0x18007376a  xorps   xmm0, xmm0
0x18007376d  xor     eax, eax
0x18007376f  movups  [rbp+var_38], xmm0
0x180073773  movups  [rbp+var_28], xmm0
0x180073777  mov     [rbp+var_18], rax
0x18007377b  test    rdx, rdx
0x18007377e  jnz     short loc_18007378C
0x180073780  mov     edi, 80070057h
0x180073785  mov     ecx, edi
0x180073787  jmp     loc_18007381B
0x18007378c  lea     rdx, asc_18009B4CC; "%X"
0x180073793  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x180073797  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18007379c  mov     edi, eax
0x18007379e  test    eax, eax
0x1800737a0  js      short loc_180073819
0x1800737a2  lea     rcx, [rbx-8]; this
0x1800737a6  lea     rdx, [rbp+var_38]; struct _UNATTEND_NODE *
0x1800737aa  call    ?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z; CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)
0x1800737af  mov     edi, eax
0x1800737b1  test    eax, eax
0x1800737b3  js      short loc_180073819
0x1800737b5  mov     rcx, [rbx+78h]
0x1800737b9  call    cs:__imp_UnattendCtxBeginModify
0x1800737bf  mov     edi, eax
0x1800737c1  test    eax, eax
0x1800737c3  js      short loc_180073819
0x1800737c5  mov     rax, [rbp+arg_8]
0x1800737c9  mov     [rsp+68h+var_48], rax
0x1800737ce  xor     r9d, r9d
0x1800737d1  mov     r8, rsi
0x1800737d4  lea     rdx, [rbp+var_38]
0x1800737d8  mov     rcx, [rbx+78h]
0x1800737dc  call    cs:__imp_UnattendCtxSetStringByNode
0x1800737e2  mov     edi, eax
0x1800737e4  test    eax, eax
0x1800737e6  js      short loc_180073819
0x1800737e8  lea     rcx, [rbp+var_38]
0x1800737ec  call    cs:__imp_UnattendFreeNode
0x1800737f2  mov     edi, eax
0x1800737f4  test    eax, eax
0x1800737f6  js      short loc_180073819
0x1800737f8  xorps   xmm0, xmm0
0x1800737fb  xor     eax, eax
0x1800737fd  movups  [rbp+var_38], xmm0
0x180073801  movups  [rbp+var_28], xmm0
0x180073805  mov     [rbp+var_18], rax
0x180073809  mov     rcx, [rbx+78h]
0x18007380d  call    cs:__imp_UnattendCtxCommitModify
0x180073813  mov     edi, eax
0x180073815  test    eax, eax
0x180073817  jns     short loc_180073820
0x180073819  mov     ecx, eax
0x18007381b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180073820  lea     rcx, [rbp+var_38]
0x180073824  call    cs:__imp_UnattendFreeNode
0x18007382a  mov     ecx, edi
0x18007382c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180073831  nop
0x180073832  mov     rbx, [rbp+arg_8]
0x180073836  test    rbx, rbx
0x180073839  jz      short loc_180073857
0x18007383b  call    cs:__imp_GetProcessHeap
0x180073841  mov     rcx, rax; hHeap
0x180073844  lea     r8, [rbx-4]; lpMem
0x180073848  xor     edx, edx; dwFlags
0x18007384a  call    cs:__imp_HeapFree
0x180073850  xor     ecx, ecx
0x180073852  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180073857  mov     eax, edi
0x180073859  add     rsp, 68h
0x18007385d  pop     rdi
0x18007385e  pop     rsi
0x18007385f  pop     rbx
0x180073860  pop     rbp
0x180073861  retn
```

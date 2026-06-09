# CDlpStateXml::SetQuadwordProperty(ushort const *,unsigned __int64)

- ea: `0x180074cd0`
- end: `0x180074de2`
- name: `?SetQuadwordProperty@CDlpStateXml@@UEAAJPEBG_K@Z`
- size: `274`
- prototype: `__int64 __fastcall(CDlpStateXml *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000aba4`
- `0x18001fd60`
- `0x180028640`
- `0x180068488`
- `0x180074cd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074dbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180074dbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180074dca`
- `UNATTEND!UnattendFreeNode` at `0x180074d6c`
- `UNATTEND!UnattendFreeNode` at `0x180074da4`
- `UNATTEND!UnattendFreeNode` at `0x180074d6c`
- `UNATTEND!UnattendFreeNode` at `0x180074da4`
- `UNATTEND!UnattendCtxBeginModify` at `0x180074d39`
- `UNATTEND!UnattendCtxBeginModify` at `0x180074d39`
- `UNATTEND!UnattendCtxCommitModify` at `0x180074d8d`
- `UNATTEND!UnattendCtxCommitModify` at `0x180074d8d`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x180074d5c`
- `UNATTEND!UnattendCtxSetStringByNode` at `0x180074d5c`

## pseudocode

```c
__int64 __fastcall CDlpStateXml::SetQuadwordProperty(CDlpStateXml *this, const unsigned __int16 *a2)
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
  v6 = STRAPI_Format(&v13, L"%I64X");
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
0x180074cd0  push    rbp
0x180074cd2  push    rbx
0x180074cd3  push    rsi
0x180074cd4  push    rdi
0x180074cd5  mov     rbp, rsp
0x180074cd8  sub     rsp, 68h
0x180074cdc  mov     rsi, rdx
0x180074cdf  mov     rbx, rcx
0x180074ce2  mov     [rbp+arg_8], 0
0x180074cea  xorps   xmm0, xmm0
0x180074ced  xor     eax, eax
0x180074cef  movups  [rbp+var_38], xmm0
0x180074cf3  movups  [rbp+var_28], xmm0
0x180074cf7  mov     [rbp+var_18], rax
0x180074cfb  test    rdx, rdx
0x180074cfe  jnz     short loc_180074D0C
0x180074d00  mov     edi, 80070057h
0x180074d05  mov     ecx, edi
0x180074d07  jmp     loc_180074D9B
0x180074d0c  lea     rdx, aI64x; "%I64X"
0x180074d13  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x180074d17  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x180074d1c  mov     edi, eax
0x180074d1e  test    eax, eax
0x180074d20  js      short loc_180074D99
0x180074d22  lea     rcx, [rbx-8]; this
0x180074d26  lea     rdx, [rbp+var_38]; struct _UNATTEND_NODE *
0x180074d2a  call    ?OpenCurrentNode@CDlpStateXml@@AEAAJPEAU_UNATTEND_NODE@@@Z; CDlpStateXml::OpenCurrentNode(_UNATTEND_NODE *)
0x180074d2f  mov     edi, eax
0x180074d31  test    eax, eax
0x180074d33  js      short loc_180074D99
0x180074d35  mov     rcx, [rbx+78h]
0x180074d39  call    cs:__imp_UnattendCtxBeginModify
0x180074d3f  mov     edi, eax
0x180074d41  test    eax, eax
0x180074d43  js      short loc_180074D99
0x180074d45  mov     rax, [rbp+arg_8]
0x180074d49  mov     [rsp+68h+var_48], rax
0x180074d4e  xor     r9d, r9d
0x180074d51  mov     r8, rsi
0x180074d54  lea     rdx, [rbp+var_38]
0x180074d58  mov     rcx, [rbx+78h]
0x180074d5c  call    cs:__imp_UnattendCtxSetStringByNode
0x180074d62  mov     edi, eax
0x180074d64  test    eax, eax
0x180074d66  js      short loc_180074D99
0x180074d68  lea     rcx, [rbp+var_38]
0x180074d6c  call    cs:__imp_UnattendFreeNode
0x180074d72  mov     edi, eax
0x180074d74  test    eax, eax
0x180074d76  js      short loc_180074D99
0x180074d78  xorps   xmm0, xmm0
0x180074d7b  xor     eax, eax
0x180074d7d  movups  [rbp+var_38], xmm0
0x180074d81  movups  [rbp+var_28], xmm0
0x180074d85  mov     [rbp+var_18], rax
0x180074d89  mov     rcx, [rbx+78h]
0x180074d8d  call    cs:__imp_UnattendCtxCommitModify
0x180074d93  mov     edi, eax
0x180074d95  test    eax, eax
0x180074d97  jns     short loc_180074DA0
0x180074d99  mov     ecx, eax
0x180074d9b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180074da0  lea     rcx, [rbp+var_38]
0x180074da4  call    cs:__imp_UnattendFreeNode
0x180074daa  mov     ecx, edi
0x180074dac  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180074db1  nop
0x180074db2  mov     rbx, [rbp+arg_8]
0x180074db6  test    rbx, rbx
0x180074db9  jz      short loc_180074DD7
0x180074dbb  call    cs:__imp_GetProcessHeap
0x180074dc1  mov     rcx, rax; hHeap
0x180074dc4  lea     r8, [rbx-4]; lpMem
0x180074dc8  xor     edx, edx; dwFlags
0x180074dca  call    cs:__imp_HeapFree
0x180074dd0  xor     ecx, ecx
0x180074dd2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180074dd7  mov     eax, edi
0x180074dd9  add     rsp, 68h
0x180074ddd  pop     rdi
0x180074dde  pop     rsi
0x180074ddf  pop     rbx
0x180074de0  pop     rbp
0x180074de1  retn
```

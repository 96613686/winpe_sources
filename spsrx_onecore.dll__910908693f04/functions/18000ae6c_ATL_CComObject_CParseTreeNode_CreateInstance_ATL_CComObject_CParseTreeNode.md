# ATL::CComObject<CParseTreeNode>::CreateInstance(ATL::CComObject<CParseTreeNode> * *)

- ea: `0x18000ae6c`
- end: `0x18000af4b`
- name: `?CreateInstance@?$CComObject@VCParseTreeNode@@@ATL@@SAJPEAPEAV12@@Z`
- size: `223`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000c2b8`
- `0x18000c478`
- `0x18000c514`

## callees

- `0x180001b50`
- `0x180002f3c`
- `0x180005284`
- `0x18000900c`
- `0x18000ae6c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aeae`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000aeae`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CParseTreeNode>::CreateInstance(int **a1)
{
  unsigned int v3; // edi
  LPVOID v4; // rax
  int *v5; // rbx
  int *v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rdi
  int v9; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = -2147024882;
  if ( g_heap && (v4 = HeapAlloc(g_heap, 0, 0x68u)) != 0 )
    v5 = (int *)ATL::CComObject<CParseTreeNode>::CComObject<CParseTreeNode>(v4);
  else
    v5 = 0;
  v6 = v5;
  if ( v5 )
  {
    ATL::CComMultiThreadModel::SafeIncrementReference(v5 + 2);
    v8 = v7 + 8;
    v9 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v7 + 8));
    if ( v9 >= 0 )
    {
      *(_BYTE *)(v8 + 40) = 1;
      v9 = 0;
    }
    v3 = 0;
    if ( v9 < 0 )
      v3 = v9;
    CTextNormMultiResult::InternalFinalConstructRelease((CTextNormMultiResult *)v5);
    if ( v3 )
    {
      (*(void (__fastcall **)(int *, __int64))(*(_QWORD *)v5 + 88LL))(v5, 1);
      v6 = 0;
    }
    else
    {
      v3 = 0;
    }
  }
  *a1 = v6;
  return v3;
}

```

## disassembly

```asm
0x18000ae6c  mov     [rsp+arg_0], rcx
0x18000ae71  push    rbx
0x18000ae72  push    rsi
0x18000ae73  push    rdi
0x18000ae74  push    r14
0x18000ae76  sub     rsp, 28h
0x18000ae7a  mov     rsi, rcx
0x18000ae7d  test    rcx, rcx
0x18000ae80  jnz     short loc_18000AE8C
0x18000ae82  mov     eax, 80004003h
0x18000ae87  jmp     loc_18000AF41
0x18000ae8c  mov     qword ptr [rcx], 0
0x18000ae93  mov     edi, 8007000Eh
0x18000ae98  mov     [rsp+48h+arg_8], edi
0x18000ae9c  mov     rcx, cs:?g_heap@@3VCHeap@@A; hHeap
0x18000aea3  test    rcx, rcx
0x18000aea6  jz      short loc_18000AEC6
0x18000aea8  xor     edx, edx; dwFlags
0x18000aeaa  lea     r8d, [rdx+68h]; dwBytes
0x18000aeae  call    cs:__imp_HeapAlloc
0x18000aeb4  test    rax, rax
0x18000aeb7  jz      short loc_18000AEC6
0x18000aeb9  mov     rcx, rax
0x18000aebc  call    ??0?$CComObject@VCParseTreeNode@@@ATL@@QEAA@PEAX@Z; ATL::CComObject<CParseTreeNode>::CComObject<CParseTreeNode>(void *)
0x18000aec1  mov     rbx, rax
0x18000aec4  jmp     short loc_18000AEC8
0x18000aec6  xor     ebx, ebx
0x18000aec8  mov     [rsp+48h+arg_10], rbx
0x18000aecd  mov     r14, rbx
0x18000aed0  mov     [rsp+48h+arg_18], rbx
0x18000aed5  jmp     short loc_18000AEEA
0x18000aed7  mov     rsi, [rsp+48h+arg_0]
0x18000aedc  mov     edi, [rsp+48h+arg_8]
0x18000aee0  mov     r14, [rsp+48h+arg_18]
0x18000aee5  mov     rbx, [rsp+48h+arg_10]
0x18000aeea  test    rbx, rbx
0x18000aeed  jz      short loc_18000AF3C
0x18000aeef  lea     rcx, [rbx+8]; int *
0x18000aef3  call    ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
0x18000aef8  lea     rdi, [rcx+8]
0x18000aefc  mov     rcx, rdi; this
0x18000aeff  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000af04  test    eax, eax
0x18000af06  js      short loc_18000AF0E
0x18000af08  mov     byte ptr [rdi+28h], 1
0x18000af0c  xor     eax, eax
0x18000af0e  xor     edi, edi
0x18000af10  test    eax, eax
0x18000af12  cmovs   edi, eax
0x18000af15  mov     rcx, rbx; this
0x18000af18  call    ?InternalFinalConstructRelease@CTextNormMultiResult@@QEAAXXZ; CTextNormMultiResult::InternalFinalConstructRelease(void)
0x18000af1d  test    edi, edi
0x18000af1f  jz      short loc_18000AF3A
0x18000af21  mov     rax, [rbx]
0x18000af24  mov     edx, 1
0x18000af29  mov     rcx, rbx
0x18000af2c  mov     rax, [rax+58h]
0x18000af30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af35  xor     r14d, r14d
0x18000af38  jmp     short loc_18000AF3C
0x18000af3a  xor     edi, edi
0x18000af3c  mov     [rsi], r14
0x18000af3f  mov     eax, edi
0x18000af41  add     rsp, 28h
0x18000af45  pop     r14
0x18000af47  pop     rdi
0x18000af48  pop     rsi
0x18000af49  pop     rbx
0x18000af4a  retn
```

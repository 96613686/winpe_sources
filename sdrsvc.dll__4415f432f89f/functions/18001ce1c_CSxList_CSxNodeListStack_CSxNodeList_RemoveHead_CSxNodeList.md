# CSxList<CSxNodeListStack,CSxNodeList>::RemoveHead(CSxNodeList * *)

- ea: `0x18001ce1c`
- end: `0x18001cec4`
- name: `?RemoveHead@?$CSxList@VCSxNodeListStack@@VCSxNodeList@@@@QEAAJPEAPEAVCSxNodeList@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c8ec`
- `0x18001cb3c`

## callees

- `0x180001554`
- `0x18001c8b4`
- `0x18001ce1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cea5`

## pseudocode

```c
__int64 __fastcall CSxList<CSxNodeListStack,CSxNodeList>::RemoveHead(__int64 a1, volatile signed __int32 **a2)
{
  _QWORD *v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  volatile signed __int32 *v6; // rdi

  if ( a2 )
    *a2 = 0;
  v2 = *(_QWORD **)(a1 + 8);
  v3 = 1;
  if ( v2 != (_QWORD *)(a1 + 24) )
  {
    _InterlockedAdd((volatile signed __int32 *)a1, 1u);
    v4 = *v2;
    if ( *(_QWORD **)(*v2 + 8LL) != v2 || (v5 = (_QWORD *)v2[1], (_QWORD *)*v5 != v2) )
      __fastfail(3u);
    *v5 = v4;
    v3 = 0;
    *(_QWORD *)(v4 + 8) = v5;
    v2[1] = v2;
    *v2 = v2;
    v6 = (volatile signed __int32 *)v2[2];
    if ( a2 )
    {
      *a2 = v6;
    }
    else if ( _InterlockedExchangeAdd(v6 + 10, 0xFFFFFFFF) == 1 && v6 )
    {
      CSxNodeList::~CSxNodeList((CSxNodeList *)v6);
      operator delete((void *)v6);
    }
    v2[2] = 0;
    CoTaskMemFree(v2);
  }
  return v3;
}

```

## disassembly

```asm
0x18001ce1c  mov     [rsp+arg_8], rbx
0x18001ce21  mov     [rsp+arg_10], rsi
0x18001ce26  push    rdi
0x18001ce27  sub     rsp, 20h
0x18001ce2b  test    rdx, rdx
0x18001ce2e  jz      short loc_18001CE37
0x18001ce30  mov     qword ptr [rdx], 0
0x18001ce37  mov     rbx, [rcx+8]
0x18001ce3b  lea     rax, [rcx+18h]
0x18001ce3f  mov     esi, 1
0x18001ce44  cmp     rbx, rax
0x18001ce47  jz      short loc_18001CEAB
0x18001ce49  lock add [rcx], esi
0x18001ce4c  mov     rcx, [rbx]
0x18001ce4f  cmp     [rcx+8], rbx
0x18001ce53  jnz     short loc_18001CEBD
0x18001ce55  mov     rax, [rbx+8]
0x18001ce59  cmp     [rax], rbx
0x18001ce5c  jnz     short loc_18001CEBD
0x18001ce5e  mov     [rax], rcx
0x18001ce61  xor     esi, esi
0x18001ce63  mov     [rcx+8], rax
0x18001ce67  mov     [rbx+8], rbx
0x18001ce6b  mov     [rbx], rbx
0x18001ce6e  mov     rdi, [rbx+10h]
0x18001ce72  test    rdx, rdx
0x18001ce75  jz      short loc_18001CE7C
0x18001ce77  mov     [rdx], rdi
0x18001ce7a  jmp     short loc_18001CE9E
0x18001ce7c  or      eax, 0FFFFFFFFh
0x18001ce7f  lock xadd [rdi+28h], eax
0x18001ce84  cmp     eax, 1
0x18001ce87  jnz     short loc_18001CE9E
0x18001ce89  test    rdi, rdi
0x18001ce8c  jz      short loc_18001CE9E
0x18001ce8e  mov     rcx, rdi; this
0x18001ce91  call    ??1CSxNodeList@@AEAA@XZ; CSxNodeList::~CSxNodeList(void)
0x18001ce96  mov     rcx, rdi; Block
0x18001ce99  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ce9e  mov     rcx, rbx; pv
0x18001cea1  mov     [rbx+10h], rsi
0x18001cea5  call    cs:__imp_CoTaskMemFree
0x18001ceab  mov     rbx, [rsp+28h+arg_8]
0x18001ceb0  mov     eax, esi
0x18001ceb2  mov     rsi, [rsp+28h+arg_10]
0x18001ceb7  add     rsp, 20h
0x18001cebb  pop     rdi
0x18001cebc  retn
0x18001cebd  mov     ecx, 3
0x18001cec2  int     29h; Win8: RtlFailFast(ecx)
```

# CSxList<CSxNodeList,CSxNodeItem>::RemoveHead(CSxNodeItem * *)

- ea: `0x18001cd6c`
- end: `0x18001ce14`
- name: `?RemoveHead@?$CSxList@VCSxNodeList@@VCSxNodeItem@@@@QEAAJPEAPEAVCSxNodeItem@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001c8b4`
- `0x18001dc74`

## callees

- `0x180001554`
- `0x18001cd6c`
- `0x180020488`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cdf5`

## pseudocode

```c
__int64 __fastcall CSxList<CSxNodeList,CSxNodeItem>::RemoveHead(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  unsigned int v3; // esi
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // rdi

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
    v6 = v2[2];
    if ( a2 )
    {
      *a2 = v6;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v6 + 16), 0xFFFFFFFF) == 1 && v6 )
    {
      CBsString::_Release((LPVOID *)v6);
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
0x18001cd6c  mov     [rsp+arg_8], rbx
0x18001cd71  mov     [rsp+arg_10], rsi
0x18001cd76  push    rdi
0x18001cd77  sub     rsp, 20h
0x18001cd7b  test    rdx, rdx
0x18001cd7e  jz      short loc_18001CD87
0x18001cd80  mov     qword ptr [rdx], 0
0x18001cd87  mov     rbx, [rcx+8]
0x18001cd8b  lea     rax, [rcx+18h]
0x18001cd8f  mov     esi, 1
0x18001cd94  cmp     rbx, rax
0x18001cd97  jz      short loc_18001CDFB
0x18001cd99  lock add [rcx], esi
0x18001cd9c  mov     rcx, [rbx]
0x18001cd9f  cmp     [rcx+8], rbx
0x18001cda3  jnz     short loc_18001CE0D
0x18001cda5  mov     rax, [rbx+8]
0x18001cda9  cmp     [rax], rbx
0x18001cdac  jnz     short loc_18001CE0D
0x18001cdae  mov     [rax], rcx
0x18001cdb1  xor     esi, esi
0x18001cdb3  mov     [rcx+8], rax
0x18001cdb7  mov     [rbx+8], rbx
0x18001cdbb  mov     [rbx], rbx
0x18001cdbe  mov     rdi, [rbx+10h]
0x18001cdc2  test    rdx, rdx
0x18001cdc5  jz      short loc_18001CDCC
0x18001cdc7  mov     [rdx], rdi
0x18001cdca  jmp     short loc_18001CDEE
0x18001cdcc  or      eax, 0FFFFFFFFh
0x18001cdcf  lock xadd [rdi+10h], eax
0x18001cdd4  cmp     eax, 1
0x18001cdd7  jnz     short loc_18001CDEE
0x18001cdd9  test    rdi, rdi
0x18001cddc  jz      short loc_18001CDEE
0x18001cdde  mov     rcx, rdi; this
0x18001cde1  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18001cde6  mov     rcx, rdi; Block
0x18001cde9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cdee  mov     rcx, rbx; pv
0x18001cdf1  mov     [rbx+10h], rsi
0x18001cdf5  call    cs:__imp_CoTaskMemFree
0x18001cdfb  mov     rbx, [rsp+28h+arg_8]
0x18001ce00  mov     eax, esi
0x18001ce02  mov     rsi, [rsp+28h+arg_10]
0x18001ce07  add     rsp, 20h
0x18001ce0b  pop     rdi
0x18001ce0c  retn
0x18001ce0d  mov     ecx, 3
0x18001ce12  int     29h; Win8: RtlFailFast(ecx)
```

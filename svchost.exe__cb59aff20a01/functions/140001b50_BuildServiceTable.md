# BuildServiceTable

- ea: `0x140001b50`
- end: `0x140001be9`
- name: `BuildServiceTable`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1400018d0`

## callees

- `0x140001b50`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001b83`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001b83`

## pseudocode

```c
_QWORD *BuildServiceTable()
{
  _QWORD *v1; // r9
  unsigned int v2; // r10d
  __int64 v3; // rcx
  __int64 v4; // r11
  __int64 v5; // r8
  __int64 v6; // rax

  if ( !ServiceArray || !ServiceCount )
    return 0;
  v1 = HeapAlloc(g_hHeap, 8u, 16LL * (unsigned int)(ServiceCount + 1));
  if ( v1 )
  {
    v2 = ServiceCount;
    v3 = 0;
    if ( ServiceCount )
    {
      v4 = ServiceArray;
      do
      {
        v5 = 2LL * (unsigned int)v3;
        v6 = 96 * v3;
        v3 = (unsigned int)(v3 + 1);
        v1[v5] = *(_QWORD *)(v6 + v4);
        v1[v5 + 1] = ServiceStarter;
      }
      while ( (unsigned int)v3 < v2 );
    }
  }
  return v1;
}

```

## disassembly

```asm
0x140001b50  sub     rsp, 28h
0x140001b54  cmp     cs:ServiceArray, 0
0x140001b5c  jnz     short loc_140001B65
0x140001b5e  xor     eax, eax
0x140001b60  add     rsp, 28h
0x140001b64  retn
0x140001b65  mov     eax, cs:ServiceCount
0x140001b6b  test    eax, eax
0x140001b6d  jz      short loc_140001B5E
0x140001b6f  mov     rcx, cs:g_hHeap; hHeap
0x140001b76  lea     r8d, [rax+1]
0x140001b7a  shl     r8, 4; dwBytes
0x140001b7e  mov     edx, 8; dwFlags
0x140001b83  call    cs:__imp_HeapAlloc
0x140001b89  mov     r9, rax
0x140001b8c  test    rax, rax
0x140001b8f  jnz     short loc_140001B99
0x140001b91  mov     rax, r9
0x140001b94  add     rsp, 28h
0x140001b98  retn
0x140001b99  mov     r10d, cs:ServiceCount
0x140001ba0  xor     ecx, ecx
0x140001ba2  test    r10d, r10d
0x140001ba5  jz      short loc_140001B91
0x140001ba7  mov     r11, cs:ServiceArray
0x140001bae  mov     [rsp+28h+var_8], rbx
0x140001bb3  lea     rbx, ServiceStarter
0x140001bba  nop     word ptr [rax+rax+00h]
0x140001bc0  lea     rax, [rcx+rcx*2]
0x140001bc4  mov     r8d, ecx
0x140001bc7  add     r8, r8
0x140001bca  shl     rax, 5
0x140001bce  inc     ecx
0x140001bd0  mov     rax, [rax+r11]
0x140001bd4  mov     [r9+r8*8], rax
0x140001bd8  mov     [r9+r8*8+8], rbx
0x140001bdd  cmp     ecx, r10d
0x140001be0  jb      short loc_140001BC0
0x140001be2  mov     rbx, [rsp+28h+var_8]
0x140001be7  jmp     short loc_140001B91
```

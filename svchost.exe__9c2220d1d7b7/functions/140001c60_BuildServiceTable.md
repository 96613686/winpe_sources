# BuildServiceTable

- ea: `0x140001c60`
- end: `0x140001d09`
- name: `BuildServiceTable`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140001970`

## callees

- `0x140001c60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001c94`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140001c94`

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
0x140001c60  sub     rsp, 28h
0x140001c64  cmp     cs:ServiceArray, 0
0x140001c6c  jnz     short loc_140001C76
0x140001c6e  xor     eax, eax
0x140001c70  add     rsp, 28h
0x140001c74  retn
0x140001c76  mov     eax, cs:ServiceCount
0x140001c7c  test    eax, eax
0x140001c7e  jz      short loc_140001C6E
0x140001c80  mov     rcx, cs:g_hHeap; hHeap
0x140001c87  lea     r8d, [rax+1]
0x140001c8b  shl     r8, 4; dwBytes
0x140001c8f  mov     edx, 8; dwFlags
0x140001c94  call    cs:__imp_HeapAlloc
0x140001c9b  nop     dword ptr [rax+rax+00h]
0x140001ca0  mov     r9, rax
0x140001ca3  test    rax, rax
0x140001ca6  jnz     short loc_140001CB1
0x140001ca8  mov     rax, r9
0x140001cab  add     rsp, 28h
0x140001caf  retn
0x140001cb1  mov     r10d, cs:ServiceCount
0x140001cb8  xor     ecx, ecx
0x140001cba  test    r10d, r10d
0x140001cbd  jz      short loc_140001CA8
0x140001cbf  mov     r11, cs:ServiceArray
0x140001cc6  mov     [rsp+28h+var_8], rbx
0x140001ccb  lea     rbx, ServiceStarter
0x140001cd2  nop     dword ptr [rax+00h]
0x140001cd6  nop     word ptr [rax+rax+00000000h]
0x140001ce0  lea     rax, [rcx+rcx*2]
0x140001ce4  mov     r8d, ecx
0x140001ce7  add     r8, r8
0x140001cea  shl     rax, 5
0x140001cee  inc     ecx
0x140001cf0  mov     rax, [rax+r11]
0x140001cf4  mov     [r9+r8*8], rax
0x140001cf8  mov     [r9+r8*8+8], rbx
0x140001cfd  cmp     ecx, r10d
0x140001d00  jb      short loc_140001CE0
0x140001d02  mov     rbx, [rsp+28h+var_8]
0x140001d07  jmp     short loc_140001CA8
```

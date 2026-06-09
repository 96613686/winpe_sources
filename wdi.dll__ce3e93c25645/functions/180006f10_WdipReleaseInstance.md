# WdipReleaseInstance

- ea: `0x180006f10`
- end: `0x180006ff7`
- name: `WdipReleaseInstance`
- size: `231`
- prototype: `void __fastcall(_DWORD *lpMem)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800063d0`
- `0x18000d228`

## callees

- `0x180006b40`
- `0x180006f10`
- `0x1800079a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f20`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006f20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006f9a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006fce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ff0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f88`

## pseudocode

```c
void __fastcall WdipReleaseInstance(_DWORD *lpMem)
{
  int v2; // eax
  int v3; // eax
  _QWORD *v4; // rax
  bool v5; // zf
  HANDLE ProcessHeap; // rax
  _QWORD *v7; // rcx

  EnterCriticalSection(&g_csWDI);
  if ( !lpMem || (v2 = lpMem[14]) != 0 && (v3 = v2 - 1, (lpMem[14] = v3) != 0) )
  {
LABEL_15:
    LeaveCriticalSection(&g_csWDI);
    return;
  }
  v4 = g_pWdiInstanceHead;
  if ( g_pWdiInstanceHead != lpMem )
  {
    if ( g_pWdiInstanceHead )
    {
      while ( 1 )
      {
        v7 = v4 + 8;
        v4 = (_QWORD *)v4[8];
        if ( v4 == (_QWORD *)lpMem )
          break;
        if ( !v4 )
          goto LABEL_15;
      }
      *v7 = *((_QWORD *)lpMem + 8);
      WdipFreeSpecificInstanceInfo(lpMem);
    }
    goto LABEL_15;
  }
  v5 = *((_QWORD *)lpMem + 4) == 0;
  g_pWdiInstanceHead = (LPVOID)*((_QWORD *)g_pWdiInstanceHead + 8);
  if ( !v5 )
    WdipDeleteParameterCollection((_QWORD *)lpMem + 4);
  if ( *((_QWORD *)lpMem + 3) )
    WdipDeleteParameterCollection((_QWORD *)lpMem + 3);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
  LeaveCriticalSection(&g_csWDI);
}

```

## disassembly

```asm
0x180006f10  push    rbx
0x180006f12  sub     rsp, 20h
0x180006f16  mov     rbx, rcx
0x180006f19  lea     rcx, g_csWDI; lpCriticalSection
0x180006f20  call    cs:__imp_EnterCriticalSection
0x180006f26  test    rbx, rbx
0x180006f29  jz      loc_180006FE4
0x180006f2f  mov     eax, [rbx+38h]
0x180006f32  test    eax, eax
0x180006f34  jz      short loc_180006F43
0x180006f36  dec     eax
0x180006f38  mov     [rbx+38h], eax
0x180006f3b  test    eax, eax
0x180006f3d  jnz     loc_180006FE4
0x180006f43  mov     rax, cs:g_pWdiInstanceHead
0x180006f4a  cmp     rax, rbx
0x180006f4d  jnz     short loc_180006FA1
0x180006f4f  cmp     qword ptr [rbx+20h], 0
0x180006f54  lea     rcx, [rbx+20h]
0x180006f58  mov     rax, [rax+40h]
0x180006f5c  mov     cs:g_pWdiInstanceHead, rax
0x180006f63  jz      short loc_180006F6A
0x180006f65  call    WdipDeleteParameterCollection
0x180006f6a  cmp     qword ptr [rbx+18h], 0
0x180006f6f  lea     rcx, [rbx+18h]
0x180006f73  jz      short loc_180006F7A
0x180006f75  call    WdipDeleteParameterCollection
0x180006f7a  call    cs:__imp_GetProcessHeap
0x180006f80  mov     r8, rbx; lpMem
0x180006f83  xor     edx, edx; dwFlags
0x180006f85  mov     rcx, rax; hHeap
0x180006f88  call    cs:__imp_HeapFree
0x180006f8e  lea     rcx, g_csWDI
0x180006f95  add     rsp, 20h
0x180006f99  pop     rbx
0x180006f9a  jmp     cs:__imp_LeaveCriticalSection
0x180006fa1  test    rax, rax
0x180006fa4  jz      short loc_180006FE4
0x180006fa6  nop     word ptr [rax+rax+00000000h]
0x180006fb0  lea     rcx, [rax+40h]
0x180006fb4  mov     rax, [rax+40h]
0x180006fb8  cmp     rax, rbx
0x180006fbb  jz      short loc_180006FD5
0x180006fbd  test    rax, rax
0x180006fc0  jnz     short loc_180006FB0
0x180006fc2  lea     rcx, g_csWDI
0x180006fc9  add     rsp, 20h
0x180006fcd  pop     rbx
0x180006fce  jmp     cs:__imp_LeaveCriticalSection
0x180006fd5  mov     rax, [rbx+40h]
0x180006fd9  mov     [rcx], rax
0x180006fdc  mov     rcx, rbx
0x180006fdf  call    WdipFreeSpecificInstanceInfo
0x180006fe4  lea     rcx, g_csWDI
0x180006feb  add     rsp, 20h
0x180006fef  pop     rbx
0x180006ff0  jmp     cs:__imp_LeaveCriticalSection
```

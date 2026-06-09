# TraceCreateServer

- ea: `0x180003450`
- end: `0x180003523`
- name: `TraceCreateServer`
- size: `211`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001100`
- `0x180001c20`
- `0x180005450`

## callees

- `0x180003000`
- `0x180003450`
- `0x180004456`
- `0x1800096bc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800034f3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003510`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800034f3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003510`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003464`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003464`

## pseudocode

```c
signed __int64 TraceCreateServer()
{
  _QWORD *v0; // rax
  signed __int64 v1; // rbx
  void *v2; // rcx
  _QWORD *v3; // rax
  signed __int64 v4; // rdi

  v0 = GlobalAlloc(0x40u, 0x340u);
  v1 = (signed __int64)v0;
  if ( !v0 )
    return 0;
  v0[8] = 60;
  v0[7] = 0;
  v2 = v0 + 14;
  v0[9] = 0;
  v0[10] = 0;
  v0[11] = 0;
  v3 = v0 + 12;
  v3[1] = v3;
  *v3 = v3;
  memset_0(v2, 0, 0xF0u);
  memset_0((void *)(v1 + 352), 0, 0x1E0u);
  if ( CreateReadWriteLock((LPCRITICAL_SECTION)v1) )
  {
    _InterlockedCompareExchange64((volatile signed __int64 *)&g_server, 0, v1);
    GlobalFree((HGLOBAL)v1);
    return 0;
  }
  v4 = _InterlockedCompareExchange64((volatile signed __int64 *)&g_server, v1, 0);
  if ( !v4 )
    return v1;
  if ( *(_QWORD *)(v1 + 48) )
    DeleteReadWriteLock((LPCRITICAL_SECTION)v1);
  GlobalFree((HGLOBAL)v1);
  return v4;
}

```

## disassembly

```asm
0x180003450  mov     [rsp+arg_0], rbx
0x180003455  push    rdi
0x180003456  sub     rsp, 20h
0x18000345a  mov     edx, 340h; dwBytes
0x18000345f  mov     ecx, 40h ; '@'; uFlags
0x180003464  call    cs:__imp_GlobalAlloc
0x18000346a  mov     rbx, rax
0x18000346d  test    rax, rax
0x180003470  jz      loc_180003516
0x180003476  xor     edi, edi
0x180003478  mov     qword ptr [rax+40h], 3Ch ; '<'
0x180003480  mov     [rax+38h], rdi
0x180003484  lea     rcx, [rbx+70h]; void *
0x180003488  mov     [rax+48h], rdi
0x18000348c  xor     edx, edx; Val
0x18000348e  mov     [rax+50h], rdi
0x180003492  mov     r8d, 0F0h; Size
0x180003498  mov     [rax+58h], rdi
0x18000349c  add     rax, 60h ; '`'
0x1800034a0  mov     [rax+8], rax
0x1800034a4  mov     [rax], rax
0x1800034a7  call    memset_0
0x1800034ac  lea     rcx, [rbx+160h]; void *
0x1800034b3  xor     edx, edx; Val
0x1800034b5  mov     r8d, 1E0h; Size
0x1800034bb  call    memset_0
0x1800034c0  mov     rcx, rbx; lpCriticalSection
0x1800034c3  call    CreateReadWriteLock
0x1800034c8  test    eax, eax
0x1800034ca  jnz     short loc_1800034FE
0x1800034cc  xor     eax, eax
0x1800034ce  lock cmpxchg cs:g_server, rbx
0x1800034d7  mov     rdi, rax
0x1800034da  jnz     short loc_1800034E1
0x1800034dc  mov     rax, rbx
0x1800034df  jmp     short loc_180003518
0x1800034e1  cmp     qword ptr [rbx+30h], 0
0x1800034e6  jz      short loc_1800034F0
0x1800034e8  mov     rcx, rbx; lpCriticalSection
0x1800034eb  call    DeleteReadWriteLock
0x1800034f0  mov     rcx, rbx; hMem
0x1800034f3  call    cs:__imp_GlobalFree
0x1800034f9  mov     rax, rdi
0x1800034fc  jmp     short loc_180003518
0x1800034fe  mov     rcx, rdi
0x180003501  mov     rax, rbx
0x180003504  lock cmpxchg cs:g_server, rcx
0x18000350d  mov     rcx, rbx; hMem
0x180003510  call    cs:__imp_GlobalFree
0x180003516  xor     eax, eax
0x180003518  mov     rbx, [rsp+28h+arg_0]
0x18000351d  add     rsp, 20h
0x180003521  pop     rdi
0x180003522  retn
```

# WapUriFreeUriObject

- ea: `0x180021e84`
- end: `0x180021fc6`
- name: `WapUriFreeUriObject`
- size: `322`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `21`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002de0`
- `0x180004340`
- `0x180007b20`
- `0x180009a4c`
- `0x180013870`
- `0x1800154c0`
- `0x1800156f0`
- `0x18001b150`
- `0x1800218e0`
- `0x180021d90`
- `0x180021dcc`
- `0x18003cad0`
- `0x18003d0c0`
- `0x180044fe0`
- `0x18004bc0c`
- `0x180057a90`
- `0x180059d98`
- `0x18005a454`
- `0x18005ad6c`
- `0x18007a5c0`
- `0x180080830`

## callees

- `0x180021e84`
- `0x180021fcc`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ee1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021ee1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021f6e`

## pseudocode

```c
int __fastcall WapUriFreeUriObject(char *lpMem)
{
  _QWORD **v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v4; // rcx
  _DWORD *v5; // r8
  bool v6; // zf
  _QWORD **v7; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  _DWORD *v10; // r8
  int result; // eax

  v2 = (_QWORD **)(lpMem + 16);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == v2 )
      break;
    if ( (_QWORD **)v3[1] != v2 || (v4 = (_QWORD *)*v3, *(_QWORD **)(*v3 + 8LL) != v3) )
LABEL_19:
      __fastfail(3u);
    v5 = v3 - 1;
    *v2 = v4;
    v4[1] = v2;
    if ( v3 != (_QWORD *)8 )
    {
      v6 = g_fWxHeapExtensionInitialized == 0;
      *v5 = 1768518261;
      if ( v6 )
        HeapFree(g_hWxProcessHeap, 0, v5);
      else
        g_WxHeapExtensionInterfaces(v5);
    }
  }
  v7 = (_QWORD **)(lpMem + 40);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_19;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_19;
    v10 = v8 - 1;
    *v7 = v9;
    v9[1] = v7;
    if ( v8 != (_QWORD *)8 )
    {
      v6 = g_fWxHeapExtensionInitialized == 0;
      *v10 = 1969844853;
      if ( v6 )
        HeapFree(g_hWxProcessHeap, 0, v10);
      else
        g_WxHeapExtensionInterfaces(v10);
    }
  }
  result = WapUriFreeHostInfo(lpMem + 64);
  *(_DWORD *)lpMem = 1869181557;
  if ( lpMem )
  {
    if ( g_fWxHeapExtensionInitialized )
      return g_WxHeapExtensionInterfaces(lpMem);
    else
      return HeapFree(g_hWxProcessHeap, 0, lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180021e84  mov     [rsp+arg_8], rbx
0x180021e89  push    rdi
0x180021e8a  sub     rsp, 20h
0x180021e8e  mov     rbx, rcx
0x180021e91  lea     rdi, [rcx+10h]
0x180021e95  mov     rax, [rdi]
0x180021e98  cmp     rax, rdi
0x180021e9b  jz      short loc_180021EEF
0x180021e9d  cmp     [rax+8], rdi
0x180021ea1  jnz     loc_180021F86
0x180021ea7  mov     rcx, [rax]
0x180021eaa  cmp     [rcx+8], rax
0x180021eae  jnz     loc_180021F86
0x180021eb4  lea     r8, [rax-8]; lpMem
0x180021eb8  mov     [rdi], rcx
0x180021ebb  mov     [rcx+8], rdi
0x180021ebf  test    r8, r8
0x180021ec2  jz      short loc_180021E95
0x180021ec4  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180021ecb  mov     dword ptr [r8], 69697275h
0x180021ed2  jnz     loc_180021FA1
0x180021ed8  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021edf  xor     edx, edx; dwFlags
0x180021ee1  call    cs:__imp_HeapFree
0x180021ee8  nop     dword ptr [rax+rax+00h]
0x180021eed  jmp     short loc_180021E95
0x180021eef  lea     rdi, [rbx+28h]
0x180021ef3  mov     rax, [rdi]
0x180021ef6  cmp     rax, rdi
0x180021ef9  jz      short loc_180021F45
0x180021efb  cmp     [rax+8], rdi
0x180021eff  jnz     loc_180021F86
0x180021f05  mov     rcx, [rax]
0x180021f08  cmp     [rcx+8], rax
0x180021f0c  jnz     short loc_180021F86
0x180021f0e  lea     r8, [rax-8]; lpMem
0x180021f12  mov     [rdi], rcx
0x180021f15  mov     [rcx+8], rdi
0x180021f19  test    r8, r8
0x180021f1c  jz      short loc_180021EF3
0x180021f1e  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180021f25  mov     dword ptr [r8], 75697275h
0x180021f2c  jnz     short loc_180021F8D
0x180021f2e  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021f35  xor     edx, edx; dwFlags
0x180021f37  call    cs:__imp_HeapFree
0x180021f3e  nop     dword ptr [rax+rax+00h]
0x180021f43  jmp     short loc_180021EF3
0x180021f45  lea     rcx, [rbx+40h]
0x180021f49  call    WapUriFreeHostInfo
0x180021f4e  mov     dword ptr [rbx], 6F697275h
0x180021f54  test    rbx, rbx
0x180021f57  jz      short loc_180021F7A
0x180021f59  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, 0; int g_fWxHeapExtensionInitialized
0x180021f60  jnz     short loc_180021FB5
0x180021f62  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x180021f69  mov     r8, rbx; lpMem
0x180021f6c  xor     edx, edx; dwFlags
0x180021f6e  call    cs:__imp_HeapFree
0x180021f75  nop     dword ptr [rax+rax+00h]
0x180021f7a  mov     rbx, [rsp+28h+arg_8]
0x180021f7f  add     rsp, 20h
0x180021f83  pop     rdi
0x180021f84  retn
0x180021f86  mov     ecx, 3
0x180021f8b  int     29h; Win8: RtlFailFast(ecx)
0x180021f8d  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180021f94  mov     rcx, r8
0x180021f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f9c  jmp     loc_180021EF3
0x180021fa1  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180021fa8  mov     rcx, r8
0x180021fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb0  jmp     loc_180021E95
0x180021fb5  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x180021fbc  mov     rcx, rbx
0x180021fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fc4  jmp     short loc_180021F7A
```

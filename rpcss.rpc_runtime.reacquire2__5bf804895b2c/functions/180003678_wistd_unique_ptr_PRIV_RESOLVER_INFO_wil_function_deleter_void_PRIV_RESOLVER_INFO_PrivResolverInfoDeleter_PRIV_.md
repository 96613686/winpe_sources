# wistd::unique_ptr<_PRIV_RESOLVER_INFO,wil::function_deleter<void (*)(_PRIV_RESOLVER_INFO *),&PrivResolverInfoDeleter(_PRIV_RESOLVER_INFO *)>>::reset(_PRIV_RESOLVER_INFO *)

- ea: `0x180003678`
- end: `0x180003773`
- name: `?reset@?$unique_ptr@U_PRIV_RESOLVER_INFO@@U?$function_deleter@P6AXPEAU_PRIV_RESOLVER_INFO@@@Z$1?PrivResolverInfoDeleter@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_PRIV_RESOLVER_INFO@@@Z`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180003678`
- `0x1800a3fcc`
- `0x1800b8428`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003756`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036f7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000371a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000372d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180003707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000371a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000372d`

## pseudocode

```c
BOOL __fastcall wistd::unique_ptr<_PRIV_RESOLVER_INFO,wil::function_deleter<void (*)(_PRIV_RESOLVER_INFO *),&void PrivResolverInfoDeleter(_PRIV_RESOLVER_INFO *)>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  void *v3; // rsi
  void *v4; // r8
  BOOL result; // eax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    HeapFree(g_hHeap, 0, *(LPVOID *)(v2 + 8));
    v3 = *(void **)(v2 + 48);
    if ( v3 )
    {
      ClearOrpcExtentArray(*(struct tagORPC_EXTENT_ARRAY **)(v2 + 48));
      HeapFree(g_hHeap, 0, v3);
    }
    *(_OWORD *)(v2 + 32) = 0;
    *(_QWORD *)(v2 + 48) = 0;
    v4 = *(void **)(v2 + 80);
    if ( v4 )
      HeapFree(g_hHeap, 0, v4);
    WindowsDeleteString(*(HSTRING *)(v2 + 120));
    WindowsDeleteString(*(HSTRING *)(v2 + 128));
    WindowsDeleteString(*(HSTRING *)(v2 + 136));
    memset_0((void *)(v2 + 16), 0, 0x98u);
    return HeapFree(g_hHeap, 0, (LPVOID)v2);
  }
  return result;
}

```

## disassembly

```asm
0x180003678  mov     [rsp+arg_0], rbx
0x18000367d  mov     [rsp+arg_8], rsi
0x180003682  push    rdi
0x180003683  sub     rsp, 20h
0x180003687  mov     rdi, [rcx]
0x18000368a  mov     [rcx], rdx
0x18000368d  test    rdi, rdi
0x180003690  jz      loc_180003762
0x180003696  mov     r8, [rdi+8]; lpMem
0x18000369a  xor     edx, edx; dwFlags
0x18000369c  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800036a3  call    cs:__imp_HeapFree
0x1800036aa  nop     dword ptr [rax+rax+00h]
0x1800036af  mov     rsi, [rdi+30h]
0x1800036b3  test    rsi, rsi
0x1800036b6  jz      short loc_1800036D8
0x1800036b8  mov     rcx, rsi; struct tagORPC_EXTENT_ARRAY *
0x1800036bb  call    ?ClearOrpcExtentArray@@YAXPEAUtagORPC_EXTENT_ARRAY@@@Z; ClearOrpcExtentArray(tagORPC_EXTENT_ARRAY *)
0x1800036c0  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800036c7  mov     r8, rsi; lpMem
0x1800036ca  xor     edx, edx; dwFlags
0x1800036cc  call    cs:__imp_HeapFree
0x1800036d3  nop     dword ptr [rax+rax+00h]
0x1800036d8  xor     eax, eax
0x1800036da  xorps   xmm0, xmm0
0x1800036dd  movups  xmmword ptr [rdi+20h], xmm0
0x1800036e1  mov     [rdi+30h], rax
0x1800036e5  mov     r8, [rdi+50h]; lpMem
0x1800036e9  test    r8, r8
0x1800036ec  jz      short loc_180003703
0x1800036ee  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800036f5  xor     edx, edx; dwFlags
0x1800036f7  call    cs:__imp_HeapFree
0x1800036fe  nop     dword ptr [rax+rax+00h]
0x180003703  mov     rcx, [rdi+78h]; string
0x180003707  call    cs:__imp_WindowsDeleteString
0x18000370e  nop     dword ptr [rax+rax+00h]
0x180003713  mov     rcx, [rdi+80h]; string
0x18000371a  call    cs:__imp_WindowsDeleteString
0x180003721  nop     dword ptr [rax+rax+00h]
0x180003726  mov     rcx, [rdi+88h]; string
0x18000372d  call    cs:__imp_WindowsDeleteString
0x180003734  nop     dword ptr [rax+rax+00h]
0x180003739  xor     edx, edx; Val
0x18000373b  lea     rcx, [rdi+10h]; void *
0x18000373f  mov     r8d, 98h; Size
0x180003745  call    memset_0
0x18000374a  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180003751  mov     r8, rdi; lpMem
0x180003754  xor     edx, edx; dwFlags
0x180003756  call    cs:__imp_HeapFree
0x18000375d  nop     dword ptr [rax+rax+00h]
0x180003762  mov     rbx, [rsp+28h+arg_0]
0x180003767  mov     rsi, [rsp+28h+arg_8]
0x18000376c  add     rsp, 20h
0x180003770  pop     rdi
0x180003771  retn
```

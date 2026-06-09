# InitDllMain

- ea: `0x100401050`
- end: `0x100401135`
- name: `InitDllMain`
- size: `229`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x100401050`
- `0x1004168f8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1004010b1`
- `KERNEL32!GetProcessHeap` at `0x1004010b1`
- `KERNEL32!HeapCreate` at `0x1004010ca`
- `KERNEL32!HeapCreate` at `0x1004010ca`
- `KERNEL32!HeapDestroy` at `0x10040111f`
- `KERNEL32!HeapDestroy` at `0x10040111f`

## pseudocode

```c
BOOL __stdcall InitDllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  DWORD v5; // edx
  DWORD v6; // edx
  BOOL result; // eax

  if ( !fdwReason )
  {
    if ( (unsigned int)DllMainCRTStartup(hinstDLL, 0, lpReserved) )
    {
      if ( g_hHeap )
        HeapDestroy(g_hHeap);
      return 1;
    }
    return 0;
  }
  v5 = fdwReason - 1;
  if ( !v5 )
  {
    g_hProcessHeap = (__int64)GetProcessHeap();
    if ( g_hProcessHeap )
    {
      g_hHeap = HeapCreate(0, 0, 0);
      if ( g_hHeap )
      {
        result = DllMainCRTStartup(hinstDLL, 1u, lpReserved);
        if ( !result )
          return result;
        return 1;
      }
    }
    return 0;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    result = DllMainCRTStartup(hinstDLL, 2u, lpReserved);
    if ( !result )
      return result;
    return 1;
  }
  if ( v6 != 1 )
    return 1;
  result = DllMainCRTStartup(hinstDLL, 3u, lpReserved);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x100401050  mov     [rsp+arg_0], rbx
0x100401055  push    rdi
0x100401056  sub     rsp, 20h
0x10040105a  mov     rbx, r8
0x10040105d  mov     rdi, rcx
0x100401060  test    edx, edx
0x100401062  jz      loc_1004010FB
0x100401068  sub     edx, 1
0x10040106b  jz      short loc_1004010B1
0x10040106d  sub     edx, 1
0x100401070  jz      short loc_100401098
0x100401072  cmp     edx, 1
0x100401075  jnz     loc_100401125
0x10040107b  mov     edx, 3; fdwReason
0x100401080  call    _DllMainCRTStartup
0x100401085  test    eax, eax
0x100401087  jnz     loc_100401125
0x10040108d  mov     rbx, [rsp+28h+arg_0]
0x100401092  add     rsp, 20h
0x100401096  pop     rdi
0x100401097  retn
0x100401098  mov     edx, 2; fdwReason
0x10040109d  call    _DllMainCRTStartup
0x1004010a2  test    eax, eax
0x1004010a4  jnz     short loc_100401125
0x1004010a6  mov     rbx, [rsp+28h+arg_0]
0x1004010ab  add     rsp, 20h
0x1004010af  pop     rdi
0x1004010b0  retn
0x1004010b1  call    cs:__imp_GetProcessHeap
0x1004010b7  mov     cs:g_hProcessHeap, rax
0x1004010be  test    rax, rax
0x1004010c1  jz      short loc_100401106
0x1004010c3  xor     r8d, r8d; dwMaximumSize
0x1004010c6  xor     edx, edx; dwInitialSize
0x1004010c8  xor     ecx, ecx; flOptions
0x1004010ca  call    cs:__imp_HeapCreate
0x1004010d0  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x1004010d7  test    rax, rax
0x1004010da  jz      short loc_100401106
0x1004010dc  mov     r8, rbx; lpvReserved
0x1004010df  mov     edx, 1; fdwReason
0x1004010e4  mov     rcx, rdi; hinstDLL
0x1004010e7  call    _DllMainCRTStartup
0x1004010ec  test    eax, eax
0x1004010ee  jnz     short loc_100401125
0x1004010f0  mov     rbx, [rsp+28h+arg_0]
0x1004010f5  add     rsp, 20h
0x1004010f9  pop     rdi
0x1004010fa  retn
0x1004010fb  xor     edx, edx; fdwReason
0x1004010fd  call    _DllMainCRTStartup
0x100401102  test    eax, eax
0x100401104  jnz     short loc_100401113
0x100401106  xor     eax, eax
0x100401108  mov     rbx, [rsp+28h+arg_0]
0x10040110d  add     rsp, 20h
0x100401111  pop     rdi
0x100401112  retn
0x100401113  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040111a  test    rcx, rcx
0x10040111d  jz      short loc_100401125
0x10040111f  call    cs:__imp_HeapDestroy
0x100401125  mov     rbx, [rsp+28h+arg_0]
0x10040112a  mov     eax, 1
0x10040112f  add     rsp, 20h
0x100401133  pop     rdi
0x100401134  retn
```

# InitDllMain

- ea: `0x1004011b0`
- end: `0x100401295`
- name: `InitDllMain`
- size: `229`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1004011b0`
- `0x1004268e8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x100401211`
- `KERNEL32!GetProcessHeap` at `0x100401211`
- `KERNEL32!HeapCreate` at `0x10040122a`
- `KERNEL32!HeapCreate` at `0x10040122a`
- `KERNEL32!HeapDestroy` at `0x10040127f`
- `KERNEL32!HeapDestroy` at `0x10040127f`

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
0x1004011b0  mov     [rsp+arg_0], rbx
0x1004011b5  push    rdi
0x1004011b6  sub     rsp, 20h
0x1004011ba  mov     rbx, r8
0x1004011bd  mov     rdi, rcx
0x1004011c0  test    edx, edx
0x1004011c2  jz      loc_10040125B
0x1004011c8  sub     edx, 1
0x1004011cb  jz      short loc_100401211
0x1004011cd  sub     edx, 1
0x1004011d0  jz      short loc_1004011F8
0x1004011d2  cmp     edx, 1
0x1004011d5  jnz     loc_100401285
0x1004011db  mov     edx, 3; fdwReason
0x1004011e0  call    _DllMainCRTStartup
0x1004011e5  test    eax, eax
0x1004011e7  jnz     loc_100401285
0x1004011ed  mov     rbx, [rsp+28h+arg_0]
0x1004011f2  add     rsp, 20h
0x1004011f6  pop     rdi
0x1004011f7  retn
0x1004011f8  mov     edx, 2; fdwReason
0x1004011fd  call    _DllMainCRTStartup
0x100401202  test    eax, eax
0x100401204  jnz     short loc_100401285
0x100401206  mov     rbx, [rsp+28h+arg_0]
0x10040120b  add     rsp, 20h
0x10040120f  pop     rdi
0x100401210  retn
0x100401211  call    cs:__imp_GetProcessHeap
0x100401217  mov     cs:g_hProcessHeap, rax
0x10040121e  test    rax, rax
0x100401221  jz      short loc_100401266
0x100401223  xor     r8d, r8d; dwMaximumSize
0x100401226  xor     edx, edx; dwInitialSize
0x100401228  xor     ecx, ecx; flOptions
0x10040122a  call    cs:__imp_HeapCreate
0x100401230  mov     cs:?g_hHeap@@3PEAXEA, rax; void * g_hHeap
0x100401237  test    rax, rax
0x10040123a  jz      short loc_100401266
0x10040123c  mov     r8, rbx; lpvReserved
0x10040123f  mov     edx, 1; fdwReason
0x100401244  mov     rcx, rdi; hinstDLL
0x100401247  call    _DllMainCRTStartup
0x10040124c  test    eax, eax
0x10040124e  jnz     short loc_100401285
0x100401250  mov     rbx, [rsp+28h+arg_0]
0x100401255  add     rsp, 20h
0x100401259  pop     rdi
0x10040125a  retn
0x10040125b  xor     edx, edx; fdwReason
0x10040125d  call    _DllMainCRTStartup
0x100401262  test    eax, eax
0x100401264  jnz     short loc_100401273
0x100401266  xor     eax, eax
0x100401268  mov     rbx, [rsp+28h+arg_0]
0x10040126d  add     rsp, 20h
0x100401271  pop     rdi
0x100401272  retn
0x100401273  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040127a  test    rcx, rcx
0x10040127d  jz      short loc_100401285
0x10040127f  call    cs:__imp_HeapDestroy
0x100401285  mov     rbx, [rsp+28h+arg_0]
0x10040128a  mov     eax, 1
0x10040128f  add     rsp, 20h
0x100401293  pop     rdi
0x100401294  retn
```

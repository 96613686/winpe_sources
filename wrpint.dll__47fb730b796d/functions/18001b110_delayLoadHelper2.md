# __delayLoadHelper2

- ea: `0x18001b110`
- end: `0x18001b304`
- name: `__delayLoadHelper2`
- size: `500`
- prototype: `FARPROC __fastcall(unsigned int *, FARPROC *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001d18`

## callees

- `0x180001d06`
- `0x180001d12`
- `0x18001b110`
- `0x18001b77a`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001b265`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExA` at `0x18001b265`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001b172`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001b187`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001b172`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18001b187`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001b2ea`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001b221`
- `api-ms-win-core-delayload-l1-1-0!DelayLoadFailureHook` at `0x18001b2ea`

## string_xrefs

- `0x18001b16b`: `api-ms-win-core-delayload-l1-1-1.dll`
- `0x18001b180`: `KERNEL32.DLL`
- `0x18001b1f3`: `ResolveDelayLoadsFromDll`

## pseudocode

```c
FARPROC __fastcall _delayLoadHelper2(unsigned int *a1, FARPROC *a2)
{
  __int64 v2; // rbp
  __int64 v3; // r15
  __int64 v5; // r12
  HMODULE v7; // rbx
  __int64 ModuleHandleW; // rdi
  const CHAR *v9; // rsi
  __int64 v10; // rdx
  const CHAR *v11; // rdi
  FARPROC result; // rax
  HMODULE Library; // rax
  signed __int64 v14; // rbp
  struct DelayLoadInfo v15[2]; // [rsp+40h] [rbp-98h] BYREF
  volatile signed __int64 *v16; // [rsp+E0h] [rbp+8h]

  v2 = a1[1];
  v3 = a1[3];
  v5 = a1[4];
  v16 = (volatile signed __int64 *)((char *)&_ImageBase.unused + a1[2]);
  v7 = (HMODULE)*v16;
  if ( DloadKernel32 != 1 )
  {
    if ( DloadKernel32 )
      return (FARPROC)((__int64 (__fastcall *)(struct HINSTANCE__ *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                        &_ImageBase,
                        a1,
                        _pfnDefaultDliFailureHook2,
                        DelayLoadFailureHook,
                        a2,
                        0);
    ModuleHandleW = (__int64)GetModuleHandleW(L"api-ms-win-core-delayload-l1-1-1.dll");
    if ( (ModuleHandleW || (ModuleHandleW = (__int64)GetModuleHandleW(L"KERNEL32.DLL")) != 0)
      && (DloadResolveDelayLoadedAPI = (__int64)GetProcAddress_0((HMODULE)ModuleHandleW, "ResolveDelayLoadedAPI")) != 0 )
    {
      DloadResolveDelayLoadsFromDll = (__int64)GetProcAddress_0((HMODULE)ModuleHandleW, "ResolveDelayLoadsFromDll");
      if ( !DloadResolveDelayLoadsFromDll )
        ModuleHandleW = 1;
      DloadKernel32 = ModuleHandleW;
      if ( ModuleHandleW != 1 )
        return (FARPROC)((__int64 (__fastcall *)(struct HINSTANCE__ *, unsigned int *, __int64, __int64 (__fastcall *)(_QWORD, _QWORD), FARPROC *, _DWORD))DloadResolveDelayLoadedAPI)(
                          &_ImageBase,
                          a1,
                          _pfnDefaultDliFailureHook2,
                          DelayLoadFailureHook,
                          a2,
                          0);
    }
    else
    {
      DloadKernel32 = 1;
    }
  }
  v9 = (char *)&_ImageBase + v2;
  v10 = v5 + 8LL * (unsigned int)(((char *)a2 - v3 - (char *)&_ImageBase) >> 3);
  if ( *(__int64 *)((char *)&_ImageBase.unused + v10) < 0 )
    v11 = (const CHAR *)*(unsigned __int16 *)((char *)&_ImageBase.unused + v10);
  else
    v11 = (char *)&_ImageBase.unused + *(unsigned int *)((char *)&_ImageBase.unused + v10) + 2;
  if ( !v7 )
  {
    Library = LoadLibraryExA((LPCSTR)&_ImageBase + v2, 0, 0);
    v7 = Library;
    if ( !Library )
      return (FARPROC)DelayLoadFailureHook(v9, v11);
    v14 = _InterlockedCompareExchange64(v16, (signed __int64)Library, 0);
    if ( v14 )
    {
      FreeLibrary_0(Library);
      v7 = (HMODULE)v14;
    }
    else
    {
      memset_0(v15, 0, 0x48u);
      v15[0].cb = 72;
      v15[0].szDll = v9;
      v15[0].hmodCur = v7;
      if ( _pfnDliNotifyHook2 )
        _pfnDliNotifyHook2(5u, v15);
    }
  }
  result = GetProcAddress_0(v7, v11);
  if ( result )
  {
    *a2 = result;
    return result;
  }
  return (FARPROC)DelayLoadFailureHook(v9, v11);
}

```

## disassembly

```asm
0x18001b110  push    rbx
0x18001b112  push    rbp
0x18001b113  push    rsi
0x18001b114  push    rdi
0x18001b115  push    r12
0x18001b117  push    r13
0x18001b119  push    r14
0x18001b11b  push    r15
0x18001b11d  sub     rsp, 98h
0x18001b124  mov     eax, [rcx+8]
0x18001b127  lea     r13, __ImageBase
0x18001b12e  mov     ebp, [rcx+4]
0x18001b131  add     rax, r13
0x18001b134  mov     r15d, [rcx+0Ch]
0x18001b138  mov     r14, rdx
0x18001b13b  mov     r12d, [rcx+10h]
0x18001b13f  mov     rsi, rcx
0x18001b142  mov     [rsp+0D8h+arg_0], rax
0x18001b14a  mov     rax, [rsp+0D8h+arg_0]
0x18001b152  mov     rbx, [rax]
0x18001b155  mov     rax, cs:DloadKernel32
0x18001b15c  cmp     rax, 1
0x18001b160  jz      short loc_18001B1A1
0x18001b162  test    rax, rax
0x18001b165  jnz     loc_18001B221
0x18001b16b  lea     rcx, aApiMsWinCoreDe_1; "api-ms-win-core-delayload-l1-1-1.dll"
0x18001b172  call    cs:__imp_GetModuleHandleW
0x18001b178  mov     rdi, rax
0x18001b17b  test    rax, rax
0x18001b17e  jnz     short loc_18001B1D8
0x18001b180  lea     rcx, aKernel32Dll; "KERNEL32.DLL"
0x18001b187  call    cs:__imp_GetModuleHandleW
0x18001b18d  mov     rdi, rax
0x18001b190  test    rax, rax
0x18001b193  jnz     short loc_18001B1D8
0x18001b195  mov     eax, 1
0x18001b19a  mov     cs:DloadKernel32, rax
0x18001b1a1  mov     rcx, r14
0x18001b1a4  mov     rsi, rbp
0x18001b1a7  sub     rcx, r15
0x18001b1aa  add     rsi, r13
0x18001b1ad  sub     rcx, r13
0x18001b1b0  sar     rcx, 3
0x18001b1b4  mov     ecx, ecx
0x18001b1b6  lea     rdx, [r12+rcx*8]
0x18001b1ba  cmp     qword ptr [rdx+r13], 0
0x18001b1bf  jl      loc_18001B253
0x18001b1c5  mov     edi, [rdx+r13]
0x18001b1c9  lea     rax, __ImageBase.unused+2
0x18001b1d0  add     rdi, rax
0x18001b1d3  jmp     loc_18001B258
0x18001b1d8  lea     rdx, aResolvedelaylo; "ResolveDelayLoadedAPI"
0x18001b1df  mov     rcx, rdi; hModule
0x18001b1e2  call    GetProcAddress_0
0x18001b1e7  mov     cs:DloadResolveDelayLoadedAPI, rax
0x18001b1ee  test    rax, rax
0x18001b1f1  jz      short loc_18001B195
0x18001b1f3  lea     rdx, aResolvedelaylo_0; "ResolveDelayLoadsFromDll"
0x18001b1fa  mov     rcx, rdi; hModule
0x18001b1fd  call    GetProcAddress_0
0x18001b202  test    rax, rax
0x18001b205  mov     cs:DloadResolveDelayLoadsFromDll, rax
0x18001b20c  mov     eax, 1
0x18001b211  cmovz   rdi, rax
0x18001b215  mov     cs:DloadKernel32, rdi
0x18001b21c  cmp     rdi, rax
0x18001b21f  jz      short loc_18001B1A1
0x18001b221  mov     r9, cs:__imp_DelayLoadFailureHook
0x18001b228  mov     rdx, rsi
0x18001b22b  mov     r8, cs:__pfnDefaultDliFailureHook2
0x18001b232  mov     rcx, r13
0x18001b235  mov     rax, cs:DloadResolveDelayLoadedAPI
0x18001b23c  mov     [rsp+0D8h+var_B0], 0
0x18001b244  mov     [rsp+0D8h+var_B8], r14
0x18001b249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b24e  jmp     loc_18001B2F0
0x18001b253  movzx   edi, word ptr [rdx+r13]
0x18001b258  test    rbx, rbx
0x18001b25b  jnz     short loc_18001B2CF
0x18001b25d  xor     r8d, r8d; dwFlags
0x18001b260  xor     edx, edx; hFile
0x18001b262  mov     rcx, rsi; lpLibFileName
0x18001b265  call    cs:__imp_LoadLibraryExA
0x18001b26b  mov     rbx, rax
0x18001b26e  test    rax, rax
0x18001b271  jz      short loc_18001B2E4
0x18001b273  mov     rcx, [rsp+0D8h+arg_0]
0x18001b27b  xor     eax, eax
0x18001b27d  lock cmpxchg [rcx], rbx
0x18001b282  mov     rbp, rax
0x18001b285  jnz     short loc_18001B2C4
0x18001b287  mov     ebp, 48h ; 'H'
0x18001b28c  lea     rcx, [rsp+0D8h+var_98]; void *
0x18001b291  mov     r8d, ebp; Size
0x18001b294  xor     edx, edx; Val
0x18001b296  call    memset_0
0x18001b29b  mov     rax, cs:__pfnDliNotifyHook2
0x18001b2a2  mov     [rsp+0D8h+var_98], ebp
0x18001b2a6  mov     [rsp+0D8h+var_80], rsi
0x18001b2ab  mov     [rsp+0D8h+var_68], rbx
0x18001b2b0  test    rax, rax
0x18001b2b3  jz      short loc_18001B2CF
0x18001b2b5  lea     rdx, [rsp+0D8h+var_98]
0x18001b2ba  lea     ecx, [rbp-43h]
0x18001b2bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2c2  jmp     short loc_18001B2CF
0x18001b2c4  mov     rcx, rbx; hLibModule
0x18001b2c7  call    FreeLibrary_0
0x18001b2cc  mov     rbx, rbp
0x18001b2cf  mov     rdx, rdi; lpProcName
0x18001b2d2  mov     rcx, rbx; hModule
0x18001b2d5  call    GetProcAddress_0
0x18001b2da  test    rax, rax
0x18001b2dd  jz      short loc_18001B2E4
0x18001b2df  mov     [r14], rax
0x18001b2e2  jmp     short loc_18001B2F0
0x18001b2e4  mov     rdx, rdi
0x18001b2e7  mov     rcx, rsi
0x18001b2ea  call    cs:__imp_DelayLoadFailureHook
0x18001b2f0  add     rsp, 98h
0x18001b2f7  pop     r15
0x18001b2f9  pop     r14
0x18001b2fb  pop     r13
0x18001b2fd  pop     r12
0x18001b2ff  pop     rdi
0x18001b300  pop     rsi
0x18001b301  pop     rbp
0x18001b302  pop     rbx
0x18001b303  retn
```

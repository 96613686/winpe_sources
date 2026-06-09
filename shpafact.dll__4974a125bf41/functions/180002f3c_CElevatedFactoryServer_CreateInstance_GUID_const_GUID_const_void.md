# CElevatedFactoryServer::CreateInstance(_GUID const &,_GUID const &,void * *)

- ea: `0x180002f3c`
- end: `0x180002ffa`
- name: `?CreateInstance@CElevatedFactoryServer@@SAJAEBU_GUID@@0PEAPEAX@Z`
- size: `190`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002c00`

## callees

- `0x1800026d4`
- `0x180002f3c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f67`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f55`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f55`

## pseudocode

```c
__int64 __fastcall CElevatedFactoryServer::CreateInstance(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  int v6; // ebx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rdi

  v6 = -2147024882;
  ProcessHeap = GetProcessHeap();
  v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0x20u);
  v9 = v8;
  if ( !v8
    || (*(_QWORD *)v8 = &CElevatedFactoryServer::`vftable',
        *(struct _GUID *)(v8 + 8) = *a1,
        _InterlockedIncrement(&g_cDllRefs),
        _InterlockedIncrement((volatile signed __int32 *)v8 + 6),
        v6 = (**(__int64 (__fastcall ***)(LPVOID, const struct _GUID *, void **))v8)(v8, a2, a3),
        (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9),
        v6 < 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_af1accad8eb7317774aa247aa557fa30_Traceguids,
        (unsigned int)v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002f3c  push    rbx
0x180002f3e  push    rbp
0x180002f3f  push    rsi
0x180002f40  push    rdi
0x180002f41  push    r14
0x180002f43  sub     rsp, 20h
0x180002f47  mov     rsi, r8
0x180002f4a  mov     rbp, rdx
0x180002f4d  mov     r14, rcx
0x180002f50  mov     ebx, 8007000Eh
0x180002f55  call    cs:__imp_GetProcessHeap
0x180002f5b  mov     edx, 8; dwFlags
0x180002f60  mov     rcx, rax; hHeap
0x180002f63  lea     r8d, [rdx+18h]; dwBytes
0x180002f67  call    cs:__imp_HeapAlloc
0x180002f6d  mov     rdi, rax
0x180002f70  test    rax, rax
0x180002f73  jz      short loc_180002FBC
0x180002f75  lea     rax, ??_7CElevatedFactoryServer@@6B@; const CElevatedFactoryServer::`vftable'
0x180002f7c  mov     [rdi], rax
0x180002f7f  movups  xmm0, xmmword ptr [r14]
0x180002f83  movdqu  xmmword ptr [rdi+8], xmm0
0x180002f88  lock inc cs:?g_cDllRefs@@3JA; long g_cDllRefs
0x180002f8f  lock inc dword ptr [rdi+18h]
0x180002f93  mov     rax, [rdi]
0x180002f96  mov     r8, rsi
0x180002f99  mov     rdx, rbp
0x180002f9c  mov     rcx, rdi
0x180002f9f  mov     rax, [rax]
0x180002fa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa7  mov     rcx, [rdi]
0x180002faa  mov     ebx, eax
0x180002fac  mov     rax, [rcx+10h]
0x180002fb0  mov     rcx, rdi
0x180002fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb8  test    ebx, ebx
0x180002fba  jns     short loc_180002FED
0x180002fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fc3  lea     rax, WPP_GLOBAL_Control
0x180002fca  cmp     rcx, rax
0x180002fcd  jz      short loc_180002FED
0x180002fcf  test    byte ptr [rcx+1Ch], 4
0x180002fd3  jz      short loc_180002FED
0x180002fd5  mov     rcx, [rcx+10h]
0x180002fd9  lea     r8, WPP_af1accad8eb7317774aa247aa557fa30_Traceguids
0x180002fe0  mov     edx, 0Ah
0x180002fe5  mov     r9d, ebx
0x180002fe8  call    WPP_SF_d
0x180002fed  mov     eax, ebx
0x180002fef  add     rsp, 20h
0x180002ff3  pop     r14
0x180002ff5  pop     rdi
0x180002ff6  pop     rsi
0x180002ff7  pop     rbp
0x180002ff8  pop     rbx
0x180002ff9  retn
```

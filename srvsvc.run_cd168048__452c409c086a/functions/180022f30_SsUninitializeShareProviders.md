# SsUninitializeShareProviders

- ea: `0x180022f30`
- end: `0x180022fde`
- name: `SsUninitializeShareProviders`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002dfb0`

## callees

- `0x180022f30`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fa3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022f9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022fa3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022f90`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180022f90`
- `ntdll!RtlDeleteResource` at `0x180022fc6`
- `ntdll!RtlDeleteResource` at `0x180022fc6`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022f50`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022f50`
- `ntdll!RtlReleaseResource` at `0x180022fb9`
- `ntdll!RtlReleaseResource` at `0x180022fb9`

## pseudocode

```c
void SsUninitializeShareProviders()
{
  HLOCAL v0; // rbx
  __int64 v1; // rax

  if ( ProvidersResourceInitialized )
  {
    RtlAcquireResourceExclusive(&stru_18005CE48, 1u);
    while ( 1 )
    {
      v0 = qword_18005CE38;
      if ( qword_18005CE38 == &qword_18005CE38 )
        break;
      if ( *((HLOCAL **)qword_18005CE38 + 1) != &qword_18005CE38
        || (v1 = *(_QWORD *)qword_18005CE38, *(HLOCAL *)(*(_QWORD *)qword_18005CE38 + 8LL) != qword_18005CE38) )
      {
        __fastfail(3u);
      }
      qword_18005CE38 = *(HLOCAL *)qword_18005CE38;
      *(_QWORD *)(v1 + 8) = &qword_18005CE38;
      (*((void (**)(void))v0 + 5))();
      FreeLibrary(*((HMODULE *)v0 + 3));
      LocalFree(*((HLOCAL *)v0 + 2));
      LocalFree(v0);
    }
    RtlReleaseResource(&stru_18005CE48);
    RtlDeleteResource(&stru_18005CE48);
    ProvidersResourceInitialized = 0;
  }
}

```

## disassembly

```asm
0x180022f30  mov     [rsp+arg_0], rbx
0x180022f35  push    rsi
0x180022f36  sub     rsp, 20h
0x180022f3a  cmp     cs:ProvidersResourceInitialized, 0
0x180022f41  jz      loc_180022FD3
0x180022f47  mov     dl, 1; Wait
0x180022f49  lea     rcx, stru_18005CE48; Resource
0x180022f50  call    cs:__imp_RtlAcquireResourceExclusive
0x180022f56  lea     rsi, qword_18005CE38
0x180022f5d  mov     rbx, cs:qword_18005CE38
0x180022f64  cmp     rbx, rsi
0x180022f67  jz      short loc_180022FB2
0x180022f69  cmp     [rbx+8], rsi
0x180022f6d  jnz     short loc_180022FAB
0x180022f6f  mov     rax, [rbx]
0x180022f72  cmp     [rax+8], rbx
0x180022f76  jnz     short loc_180022FAB
0x180022f78  mov     cs:qword_18005CE38, rax
0x180022f7f  mov     [rax+8], rsi
0x180022f83  mov     rax, [rbx+28h]
0x180022f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022f8c  mov     rcx, [rbx+18h]; hLibModule
0x180022f90  call    cs:__imp_FreeLibrary
0x180022f96  mov     rcx, [rbx+10h]; hMem
0x180022f9a  call    cs:__imp_LocalFree
0x180022fa0  mov     rcx, rbx; hMem
0x180022fa3  call    cs:__imp_LocalFree
0x180022fa9  jmp     short loc_180022F5D
0x180022fab  mov     ecx, 3
0x180022fb0  int     29h; Win8: RtlFailFast(ecx)
0x180022fb2  lea     rcx, stru_18005CE48; Resource
0x180022fb9  call    cs:__imp_RtlReleaseResource
0x180022fbf  lea     rcx, stru_18005CE48; Resource
0x180022fc6  call    cs:__imp_RtlDeleteResource
0x180022fcc  mov     cs:ProvidersResourceInitialized, 0
0x180022fd3  mov     rbx, [rsp+28h+arg_0]
0x180022fd8  add     rsp, 20h
0x180022fdc  pop     rsi
0x180022fdd  retn
```

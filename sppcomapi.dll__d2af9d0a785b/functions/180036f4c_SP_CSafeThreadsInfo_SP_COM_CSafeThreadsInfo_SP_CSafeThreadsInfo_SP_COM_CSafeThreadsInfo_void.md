# SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(void)

- ea: `0x180036f4c`
- end: `0x180036fbd`
- name: `??1?$SP@VCSafeThreadsInfo@@V?$SP_COM@VCSafeThreadsInfo@@@@@@QEAA@XZ`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180039a0c`

## callees

- `0x180036f4c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036f8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036f9e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036f76`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180036f76`

## pseudocode

```c
void __fastcall SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>::~SP<CSafeThreadsInfo,SP_COM<CSafeThreadsInfo>>(
        _QWORD **a1)
{
  _QWORD *v1; // rbx
  HMODULE v3; // rcx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1, 0xFFFFFFFF) == 1 )
    {
      v3 = (HMODULE)v1[3];
      if ( v3 )
      {
        FreeLibrary(v3);
        v1[3] = 0;
      }
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180036f4c  mov     [rsp+arg_0], rbx
0x180036f51  push    rdi
0x180036f52  sub     rsp, 20h
0x180036f56  mov     rbx, [rcx]
0x180036f59  mov     rdi, rcx
0x180036f5c  test    rbx, rbx
0x180036f5f  jz      short loc_180036FB1
0x180036f61  or      eax, 0FFFFFFFFh
0x180036f64  lock xadd [rbx], eax
0x180036f68  cmp     eax, 1
0x180036f6b  jnz     short loc_180036FAA
0x180036f6d  mov     rcx, [rbx+18h]; hLibModule
0x180036f71  test    rcx, rcx
0x180036f74  jz      short loc_180036F8A
0x180036f76  call    cs:__imp_FreeLibrary
0x180036f7d  nop     dword ptr [rax+rax+00h]
0x180036f82  mov     qword ptr [rbx+18h], 0
0x180036f8a  call    cs:__imp_GetProcessHeap
0x180036f91  nop     dword ptr [rax+rax+00h]
0x180036f96  mov     r8, rbx; lpMem
0x180036f99  xor     edx, edx; dwFlags
0x180036f9b  mov     rcx, rax; hHeap
0x180036f9e  call    cs:__imp_HeapFree
0x180036fa5  nop     dword ptr [rax+rax+00h]
0x180036faa  mov     qword ptr [rdi], 0
0x180036fb1  mov     rbx, [rsp+28h+arg_0]
0x180036fb6  add     rsp, 20h
0x180036fba  pop     rdi
0x180036fbb  retn
```

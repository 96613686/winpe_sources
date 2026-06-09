# SHAllocShared

- ea: `0x18001e530`
- end: `0x18001e5c2`
- name: `SHAllocShared`
- size: `146`
- prototype: `HANDLE __stdcall(const void *pvData, DWORD dwSize, DWORD dwProcessId)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001d940`
- `0x18001e530`
- `0x18001e5c8`
- `0x1800672e8`
- `0x18009341c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e575`

## pseudocode

```c
HANDLE __stdcall SHAllocShared(const void *pvData, DWORD dwSize, DWORD dwProcessId)
{
  size_t v4; // rdi
  void *v6; // rsi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  size_t v10; // rax

  v4 = dwSize;
  if ( GetCurrentProcessId() != dwProcessId )
    return _AllocSharedUsingAtom((unsigned int)v4, dwProcessId, pvData);
  v6 = 0;
  if ( (int)v4 + 16 >= (unsigned int)v4 )
  {
    v8 = CoTaskMemAlloc((unsigned int)(v4 + 16));
    v9 = v8;
    if ( v8 )
    {
      v10 = CTCoAllocPolicy::_CoTaskMemSize(v8);
      memset_0(v9, 0, v10);
      *v9 = v4;
      v9[1] = -1157686529;
      v9[2] = dwProcessId;
      v9[3] = dwProcessId;
      if ( pvData )
        memcpy_0(v9 + 4, pvData, v4);
      return v9;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001e530  push    rbx
0x18001e532  push    rbp
0x18001e533  push    rsi
0x18001e534  push    rdi
0x18001e535  push    r14
0x18001e537  sub     rsp, 20h
0x18001e53b  mov     ebp, r8d
0x18001e53e  mov     edi, edx
0x18001e540  mov     r14, rcx
0x18001e543  call    cs:__imp_GetCurrentProcessId
0x18001e549  cmp     eax, ebp
0x18001e54b  jz      short loc_18001E56A
0x18001e54d  mov     r8, r14; Src
0x18001e550  mov     edx, ebp; unsigned int
0x18001e552  mov     ecx, edi; Size
0x18001e554  call    ?_AllocSharedUsingAtom@@YAPEAXKKPEBX@Z; _AllocSharedUsingAtom(ulong,ulong,void const *)
0x18001e559  mov     rsi, rax
0x18001e55c  mov     rax, rsi
0x18001e55f  add     rsp, 20h
0x18001e563  pop     r14
0x18001e565  pop     rdi
0x18001e566  pop     rsi
0x18001e567  pop     rbp
0x18001e568  pop     rbx
0x18001e569  retn
0x18001e56a  xor     esi, esi
0x18001e56c  lea     eax, [rdi+10h]
0x18001e56f  cmp     eax, edi
0x18001e571  jb      short loc_18001E55C
0x18001e573  mov     ecx, eax; cb
0x18001e575  call    cs:__imp_CoTaskMemAlloc
0x18001e57b  mov     rbx, rax
0x18001e57e  test    rax, rax
0x18001e581  jz      short loc_18001E55C
0x18001e583  mov     rcx, rax; void *
0x18001e586  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001e58b  mov     r8, rax; Size
0x18001e58e  xor     edx, edx; Val
0x18001e590  mov     rcx, rbx; void *
0x18001e593  call    memset_0
0x18001e598  mov     [rbx], edi
0x18001e59a  mov     dword ptr [rbx+4], 0BAFF1AFFh
0x18001e5a1  mov     [rbx+8], ebp
0x18001e5a4  mov     [rbx+0Ch], ebp
0x18001e5a7  test    r14, r14
0x18001e5aa  jnz     short loc_18001E5B1
0x18001e5ac  mov     rsi, rbx
0x18001e5af  jmp     short loc_18001E55C
0x18001e5b1  mov     r8, rdi; Size
0x18001e5b4  lea     rcx, [rbx+10h]; void *
0x18001e5b8  mov     rdx, r14; Src
0x18001e5bb  call    memcpy_0
0x18001e5c0  jmp     short loc_18001E5AC
```

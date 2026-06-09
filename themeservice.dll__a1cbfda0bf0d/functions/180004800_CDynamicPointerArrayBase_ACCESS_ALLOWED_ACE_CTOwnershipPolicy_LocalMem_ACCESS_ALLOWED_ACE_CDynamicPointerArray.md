# CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>(void)

- ea: `0x180004800`
- end: `0x180004841`
- name: `??1?$CDynamicPointerArrayBase@U_ACCESS_ALLOWED_ACE@@V?$CTOwnershipPolicy_LocalMem@U_ACCESS_ALLOWED_ACE@@@@@@IEAA@XZ`
- size: `65`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000461c`
- `0x180004bb0`

## callees

- `0x1800034c4`
- `0x180004800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004824`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004824`

## pseudocode

```c
__int64 __fastcall CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>::~CDynamicPointerArrayBase<_ACCESS_ALLOWED_ACE,CTOwnershipPolicy_LocalMem<_ACCESS_ALLOWED_ACE>>(
        int *a1)
{
  _QWORD *v1; // rdi
  unsigned int v2; // ebx
  void *v3; // rcx

  v1 = a1 + 2;
  if ( *((_QWORD *)a1 + 1) )
  {
    v2 = *a1;
    while ( (--v2 & 0x80000000) == 0 )
    {
      v3 = *(void **)(*v1 + 8LL * v2);
      if ( v3 )
        LocalFree(v3);
    }
  }
  return ReleaseMemoryWorker(v1);
}

```

## disassembly

```asm
0x180004800  mov     [rsp+arg_0], rbx
0x180004805  push    rdi
0x180004806  sub     rsp, 20h
0x18000480a  lea     rdi, [rcx+8]
0x18000480e  cmp     qword ptr [rdi], 0
0x180004812  jz      short loc_18000482F
0x180004814  mov     ebx, [rcx]
0x180004816  jmp     short loc_18000482A
0x180004818  mov     rax, [rdi]
0x18000481b  mov     rcx, [rax+rbx*8]; hMem
0x18000481f  test    rcx, rcx
0x180004822  jz      short loc_18000482A
0x180004824  call    cs:__imp_LocalFree
0x18000482a  sub     ebx, 1
0x18000482d  jns     short loc_180004818
0x18000482f  mov     rcx, rdi
0x180004832  mov     rbx, [rsp+28h+arg_0]
0x180004837  add     rsp, 20h
0x18000483b  pop     rdi
0x18000483c  jmp     ReleaseMemoryWorker
```

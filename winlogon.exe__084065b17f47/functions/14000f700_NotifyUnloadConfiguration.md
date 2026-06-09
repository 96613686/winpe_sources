# NotifyUnloadConfiguration

- ea: `0x14000f700`
- end: `0x14000f867`
- name: `NotifyUnloadConfiguration`
- size: `359`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000db20`
- `0x14003732c`

## callees

- `0x14000f700`
- `0x14000f870`
- `0x14004137c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f776`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f814`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f776`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f814`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f768`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f768`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f84a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000f84a`
- `RPCRT4!RpcBindingUnbind` at `0x14000f7ae`
- `RPCRT4!RpcBindingUnbind` at `0x14000f7ae`
- `RPCRT4!RpcBindingFree` at `0x14000f7be`
- `RPCRT4!RpcBindingFree` at `0x14000f7be`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000f798`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000f83b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000f798`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x14000f83b`

## pseudocode

```c
void __fastcall NotifyUnloadConfiguration(__int64 *a1)
{
  __int64 v1; // rbx
  __int64 *v3; // rdi
  unsigned int i; // esi
  __int64 v5; // r14
  __int64 v6; // rbp
  void *v7; // r15
  HANDLE ProcessHeap; // rax
  SC_HANDLE v9; // rcx
  __int64 v10; // r14
  void *v11; // rcx
  __int64 *v12; // rsi
  unsigned int j; // edi
  __int64 v14; // r14
  void *v15; // r15
  HANDLE v16; // rax
  SC_HANDLE v17; // rcx
  HKEY v18; // rcx

  v1 = *a1;
  if ( *a1 && *(_DWORD *)v1 == 88 )
  {
    if ( *(_QWORD *)(v1 + 80) )
      WaitForAndDeleteTimer();
    v3 = (__int64 *)(v1 + 8);
    if ( *(_QWORD *)(v1 + 8) )
    {
      for ( i = 0; i < *(_DWORD *)(v1 + 4); ++i )
      {
        v5 = *v3;
        v6 = 608LL * i;
        v7 = *(void **)(*v3 + v6 + 576);
        if ( v7 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v7);
          *(_QWORD *)(v5 + v6 + 576) = 0;
        }
        v9 = *(SC_HANDLE *)(*v3 + v6 + 584);
        if ( v9 )
          CloseServiceHandle(v9);
        v10 = *v3;
        v11 = *(void **)(*v3 + v6 + 560);
        if ( v11 )
        {
          RpcBindingUnbind(v11);
          RpcBindingFree((RPC_BINDING_HANDLE *)(v6 + v10 + 560));
          *(_QWORD *)(v10 + v6 + 560) = 0;
        }
      }
      NotifyFree(v1 + 8);
    }
    v12 = (__int64 *)(v1 + 24);
    if ( *(_QWORD *)(v1 + 24) )
    {
      for ( j = 0; j < *(_DWORD *)(v1 + 16); ++j )
      {
        v14 = *v12;
        v15 = *(void **)(*v12 + 16LL * j + 8);
        if ( v15 )
        {
          v16 = GetProcessHeap();
          HeapFree(v16, 0, v15);
          *(_QWORD *)(v14 + 16LL * j + 8) = 0;
        }
      }
      NotifyFree(v1 + 24);
    }
    v17 = *(SC_HANDLE *)(v1 + 32);
    if ( v17 )
      CloseServiceHandle(v17);
    v18 = *(HKEY *)(v1 + 40);
    if ( v18 )
      RegCloseKey(v18);
    NotifyFree(a1);
  }
}

```

## disassembly

```asm
0x14000f700  push    rbx
0x14000f702  push    rbp
0x14000f703  push    rsi
0x14000f704  push    rdi
0x14000f705  push    r12
0x14000f707  push    r14
0x14000f709  push    r15
0x14000f70b  sub     rsp, 20h
0x14000f70f  mov     rbx, [rcx]
0x14000f712  mov     r12, rcx
0x14000f715  test    rbx, rbx
0x14000f718  jz      loc_14000F858
0x14000f71e  cmp     dword ptr [rbx], 58h ; 'X'
0x14000f721  jnz     loc_14000F858
0x14000f727  lea     rcx, [rbx+50h]
0x14000f72b  cmp     qword ptr [rcx], 0
0x14000f72f  jz      short loc_14000F736
0x14000f731  call    WaitForAndDeleteTimer
0x14000f736  lea     rdi, [rbx+8]
0x14000f73a  cmp     qword ptr [rdi], 0
0x14000f73e  jz      loc_14000F7E3
0x14000f744  xor     esi, esi
0x14000f746  cmp     [rbx+4], esi
0x14000f749  jbe     loc_14000F7DB
0x14000f74f  mov     r14, [rdi]
0x14000f752  mov     eax, esi
0x14000f754  imul    rbp, rax, 260h
0x14000f75b  mov     r15, [r14+rbp+240h]
0x14000f763  test    r15, r15
0x14000f766  jz      short loc_14000F788
0x14000f768  call    cs:__imp_GetProcessHeap
0x14000f76e  mov     r8, r15; lpMem
0x14000f771  xor     edx, edx; dwFlags
0x14000f773  mov     rcx, rax; hHeap
0x14000f776  call    cs:__imp_HeapFree
0x14000f77c  mov     qword ptr [r14+rbp+240h], 0
0x14000f788  mov     rax, [rdi]
0x14000f78b  mov     rcx, [rax+rbp+248h]; hSCObject
0x14000f793  test    rcx, rcx
0x14000f796  jz      short loc_14000F79E
0x14000f798  call    cs:__imp_CloseServiceHandle
0x14000f79e  mov     r14, [rdi]
0x14000f7a1  mov     rcx, [r14+rbp+230h]; Binding
0x14000f7a9  test    rcx, rcx
0x14000f7ac  jz      short loc_14000F7D0
0x14000f7ae  call    cs:__imp_RpcBindingUnbind
0x14000f7b4  lea     rcx, [r14+230h]
0x14000f7bb  add     rcx, rbp; Binding
0x14000f7be  call    cs:__imp_RpcBindingFree
0x14000f7c4  mov     qword ptr [r14+rbp+230h], 0
0x14000f7d0  inc     esi
0x14000f7d2  cmp     esi, [rbx+4]
0x14000f7d5  jb      loc_14000F74F
0x14000f7db  mov     rcx, rdi
0x14000f7de  call    NotifyFree
0x14000f7e3  lea     rsi, [rbx+18h]
0x14000f7e7  cmp     qword ptr [rsi], 0
0x14000f7eb  jz      short loc_14000F832
0x14000f7ed  xor     edi, edi
0x14000f7ef  cmp     [rbx+10h], edi
0x14000f7f2  jbe     short loc_14000F82A
0x14000f7f4  mov     r14, [rsi]
0x14000f7f7  mov     ebp, edi
0x14000f7f9  add     rbp, rbp
0x14000f7fc  mov     r15, [r14+rbp*8+8]
0x14000f801  test    r15, r15
0x14000f804  jz      short loc_14000F823
0x14000f806  call    cs:__imp_GetProcessHeap
0x14000f80c  mov     r8, r15; lpMem
0x14000f80f  xor     edx, edx; dwFlags
0x14000f811  mov     rcx, rax; hHeap
0x14000f814  call    cs:__imp_HeapFree
0x14000f81a  mov     qword ptr [r14+rbp*8+8], 0
0x14000f823  inc     edi
0x14000f825  cmp     edi, [rbx+10h]
0x14000f828  jb      short loc_14000F7F4
0x14000f82a  mov     rcx, rsi
0x14000f82d  call    NotifyFree
0x14000f832  mov     rcx, [rbx+20h]; hSCObject
0x14000f836  test    rcx, rcx
0x14000f839  jz      short loc_14000F841
0x14000f83b  call    cs:__imp_CloseServiceHandle
0x14000f841  mov     rcx, [rbx+28h]; hKey
0x14000f845  test    rcx, rcx
0x14000f848  jz      short loc_14000F850
0x14000f84a  call    cs:__imp_RegCloseKey
0x14000f850  mov     rcx, r12
0x14000f853  call    NotifyFree
0x14000f858  add     rsp, 20h
0x14000f85c  pop     r15
0x14000f85e  pop     r14
0x14000f860  pop     r12
0x14000f862  pop     rdi
0x14000f863  pop     rsi
0x14000f864  pop     rbp
0x14000f865  pop     rbx
0x14000f866  retn
```

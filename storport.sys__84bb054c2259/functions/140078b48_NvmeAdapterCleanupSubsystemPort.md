# NvmeAdapterCleanupSubsystemPort

- ea: `0x140078b48`
- end: `0x140078c65`
- name: `NvmeAdapterCleanupSubsystemPort`
- size: `285`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140078868`
- `0x1400f7374`
- `0x1400fca64`
- `0x1401a6500`

## callees

- `0x140078b48`
- `0x1400f8094`
- `0x1400fd068`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140078c21`
- `ntoskrnl!ExDeleteResourceLite` at `0x140078c21`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078b5d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140078b5d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078b72`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140078b72`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078bef`
- `ntoskrnl!ExReleaseResourceLite` at `0x140078bef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078c48`
- `ntoskrnl!ExFreePoolWithTag` at `0x140078c48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078bfb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140078bfb`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140078c34`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140078c34`

## pseudocode

```c
void __fastcall NvmeAdapterCleanupSubsystemPort(__int64 a1, char a2, PVOID *a3)
{
  char *v3; // rbx
  __int64 v7; // r9
  char *v8; // r8
  _QWORD **v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  __int64 v13; // rax

  v3 = (char *)*a3;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v3 + 632), 1u);
  while ( 1 )
  {
    v8 = (char *)*a3;
    v9 = (_QWORD **)((char *)*a3 + 608);
    v10 = *v9;
    if ( *v9 == v9 )
      break;
    if ( (_QWORD **)v10[1] != v9 || (v11 = (_QWORD *)*v10, *(_QWORD **)(*v10 + 8LL) != v10) )
      __fastfail(3u);
    *v9 = v11;
    v11[1] = v9;
    v12 = v10 - 8;
    --*((_DWORD *)v8 + 156);
    v13 = v10[9];
    if ( (v13 & 8) == 0 )
    {
      *((_DWORD *)v12 + 142) = 3;
      v12[17] = v13 | 8;
      LOBYTE(v7) = 1;
      NvmeAdapterDisconnectFabricsControllerInternal(a1, v12, v8 + 60, v7);
    }
  }
  ExReleaseResourceLite((PERESOURCE)(v8 + 632));
  KeLeaveCriticalRegion();
  if ( a2 )
    NvmeAdapterSendControlRemoveSubsystemPort(a1, *a3);
  ExDeleteResourceLite((PERESOURCE)((char *)*a3 + 632));
  ExFreeCacheAwareRundownProtection(*((PEX_RUNDOWN_REF_CACHE_AWARE *)*a3 + 5));
  ExFreePoolWithTag(*a3, 0x464E6152u);
  *a3 = 0;
}

```

## disassembly

```asm
0x140078b48  push    rbx
0x140078b4a  push    rbp
0x140078b4b  push    rsi
0x140078b4c  push    rdi
0x140078b4d  sub     rsp, 28h
0x140078b51  mov     rbx, [r8]
0x140078b54  mov     rdi, r8
0x140078b57  mov     bpl, dl
0x140078b5a  mov     rsi, rcx
0x140078b5d  call    cs:__imp_KeEnterCriticalRegion
0x140078b64  nop     dword ptr [rax+rax+00h]
0x140078b69  mov     dl, 1; Wait
0x140078b6b  lea     rcx, [rbx+278h]; Resource
0x140078b72  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140078b79  nop     dword ptr [rax+rax+00h]
0x140078b7e  mov     ebx, 3
0x140078b83  mov     r8, [rdi]
0x140078b86  lea     rcx, [r8+260h]
0x140078b8d  mov     rax, [rcx]
0x140078b90  cmp     rax, rcx
0x140078b93  jz      short loc_140078BE8
0x140078b95  cmp     [rax+8], rcx
0x140078b99  jnz     short loc_140078BE3
0x140078b9b  mov     rdx, [rax]
0x140078b9e  cmp     [rdx+8], rax
0x140078ba2  jnz     short loc_140078BE3
0x140078ba4  mov     [rcx], rdx
0x140078ba7  mov     [rdx+8], rcx
0x140078bab  lea     rdx, [rax-40h]
0x140078baf  dec     dword ptr [r8+270h]
0x140078bb6  mov     rax, [rdx+88h]
0x140078bbd  test    al, 8
0x140078bbf  jnz     short loc_140078B83
0x140078bc1  or      rax, 8
0x140078bc5  mov     [rdx+238h], ebx
0x140078bcb  add     r8, 3Ch ; '<'
0x140078bcf  mov     [rdx+88h], rax
0x140078bd6  mov     r9b, 1
0x140078bd9  mov     rcx, rsi
0x140078bdc  call    NvmeAdapterDisconnectFabricsControllerInternal
0x140078be1  jmp     short loc_140078B83
0x140078be3  mov     rcx, rbx
0x140078be6  int     29h; Win8: RtlFailFast(ecx)
0x140078be8  lea     rcx, [r8+278h]; Resource
0x140078bef  call    cs:__imp_ExReleaseResourceLite
0x140078bf6  nop     dword ptr [rax+rax+00h]
0x140078bfb  call    cs:__imp_KeLeaveCriticalRegion
0x140078c02  nop     dword ptr [rax+rax+00h]
0x140078c07  test    bpl, bpl
0x140078c0a  jz      short loc_140078C17
0x140078c0c  mov     rdx, [rdi]
0x140078c0f  mov     rcx, rsi
0x140078c12  call    NvmeAdapterSendControlRemoveSubsystemPort
0x140078c17  mov     rcx, [rdi]
0x140078c1a  add     rcx, 278h; Resource
0x140078c21  call    cs:__imp_ExDeleteResourceLite
0x140078c28  nop     dword ptr [rax+rax+00h]
0x140078c2d  mov     rcx, [rdi]
0x140078c30  mov     rcx, [rcx+28h]; RunRefCacheAware
0x140078c34  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140078c3b  nop     dword ptr [rax+rax+00h]
0x140078c40  mov     rcx, [rdi]; P
0x140078c43  mov     edx, 464E6152h; Tag
0x140078c48  call    cs:__imp_ExFreePoolWithTag
0x140078c4f  nop     dword ptr [rax+rax+00h]
0x140078c54  mov     qword ptr [rdi], 0
0x140078c5b  add     rsp, 28h
0x140078c5f  pop     rdi
0x140078c60  pop     rsi
0x140078c61  pop     rbp
0x140078c62  pop     rbx
0x140078c63  retn
```

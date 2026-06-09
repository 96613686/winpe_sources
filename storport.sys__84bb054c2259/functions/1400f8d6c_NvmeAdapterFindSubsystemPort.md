# NvmeAdapterFindSubsystemPort

- ea: `0x1400f8d6c`
- end: `0x1400f8eca`
- name: `NvmeAdapterFindSubsystemPort`
- size: `350`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1401a152c`
- `0x1401a20b4`
- `0x1401a3fc8`
- `0x1401a6500`

## callees

- `0x1400f8d6c`
- `0x1400fa1d0`
- `0x140100b40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8da8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8def`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8da8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8def`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8e35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8e9d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8e35`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8e9d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8e56`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8e86`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8e56`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8e86`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8e41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8ea9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8e41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8ea9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8dba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8e07`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8dba`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8e07`

## pseudocode

```c
_QWORD *__fastcall NvmeAdapterFindSubsystemPort(__int64 a1, _QWORD *a2, char a3, _QWORD *a4)
{
  _QWORD *v4; // rdi
  __int64 v9; // rbx
  _QWORD *i; // r14
  _QWORD *v11; // rbx
  _QWORD *v12; // rax

  v4 = 0;
  if ( !a3 || a4 )
  {
    if ( a4 )
      *a4 = 0;
    v9 = *(_QWORD *)(a1 + 616);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v9 + 24), 1u);
    for ( i = **(_QWORD ***)(a1 + 616); i != *(_QWORD **)(a1 + 616); i = (_QWORD *)*i )
    {
      v11 = i - 3;
      if ( (int)NvmeAdapterHostGatewayAcquireRundown(i - 3) >= 0 )
      {
        v4 = 0;
        KeEnterCriticalRegion();
        ExAcquireResourceSharedLite((PERESOURCE)(v11 + 48), 1u);
        v12 = (_QWORD *)v11[45];
        while ( v12 != v11 + 45 )
        {
          v4 = v12 - 1;
          if ( a2 == v12 - 1 )
            break;
          v12 = (_QWORD *)*v12;
          v4 = 0;
        }
        ExReleaseResourceLite((PERESOURCE)(v11 + 48));
        KeLeaveCriticalRegion();
        if ( v4 )
        {
          if ( (int)NvmeAdapterSubsystemPortAcquireRundown(v4) < 0 )
          {
            v4 = 0;
          }
          else if ( a3 )
          {
            *a4 = v11;
            break;
          }
          ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[7]);
          break;
        }
        ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[7]);
      }
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 616) + 24LL));
    KeLeaveCriticalRegion();
  }
  return v4;
}

```

## disassembly

```asm
0x1400f8d6c  push    rbx
0x1400f8d6e  push    rbp
0x1400f8d6f  push    rsi
0x1400f8d70  push    rdi
0x1400f8d71  push    r12
0x1400f8d73  push    r13
0x1400f8d75  push    r14
0x1400f8d77  push    r15
0x1400f8d79  sub     rsp, 28h
0x1400f8d7d  xor     edi, edi
0x1400f8d7f  mov     rsi, r9
0x1400f8d82  mov     r15b, r8b
0x1400f8d85  mov     r13, rdx
0x1400f8d88  mov     rbp, rcx
0x1400f8d8b  test    r8b, r8b
0x1400f8d8e  jz      short loc_1400F8D99
0x1400f8d90  test    r9, r9
0x1400f8d93  jz      loc_1400F8EB5
0x1400f8d99  test    rsi, rsi
0x1400f8d9c  jz      short loc_1400F8DA1
0x1400f8d9e  mov     [r9], rdi
0x1400f8da1  mov     rbx, [rcx+268h]
0x1400f8da8  call    cs:__imp_KeEnterCriticalRegion
0x1400f8daf  nop     dword ptr [rax+rax+00h]
0x1400f8db4  mov     dl, 1; Wait
0x1400f8db6  lea     rcx, [rbx+18h]; Resource
0x1400f8dba  call    cs:__imp_ExAcquireResourceSharedLite
0x1400f8dc1  nop     dword ptr [rax+rax+00h]
0x1400f8dc6  mov     rax, [rbp+268h]
0x1400f8dcd  mov     r14, [rax]
0x1400f8dd0  cmp     r14, [rbp+268h]
0x1400f8dd7  jz      loc_1400F8E92
0x1400f8ddd  lea     rbx, [r14-18h]
0x1400f8de1  mov     rcx, rbx
0x1400f8de4  call    NvmeAdapterHostGatewayAcquireRundown
0x1400f8de9  test    eax, eax
0x1400f8deb  js      short loc_1400F8E62
0x1400f8ded  xor     edi, edi
0x1400f8def  call    cs:__imp_KeEnterCriticalRegion
0x1400f8df6  nop     dword ptr [rax+rax+00h]
0x1400f8dfb  lea     r12, [rbx+180h]
0x1400f8e02  mov     dl, 1; Wait
0x1400f8e04  mov     rcx, r12; Resource
0x1400f8e07  call    cs:__imp_ExAcquireResourceSharedLite
0x1400f8e0e  nop     dword ptr [rax+rax+00h]
0x1400f8e13  lea     rdx, [rbx+168h]
0x1400f8e1a  mov     rax, [rdx]
0x1400f8e1d  jmp     short loc_1400F8E2D
0x1400f8e1f  lea     rdi, [rax-8]
0x1400f8e23  cmp     r13, rdi
0x1400f8e26  jz      short loc_1400F8E32
0x1400f8e28  mov     rax, [rax]
0x1400f8e2b  xor     edi, edi
0x1400f8e2d  cmp     rax, rdx
0x1400f8e30  jnz     short loc_1400F8E1F
0x1400f8e32  mov     rcx, r12; Resource
0x1400f8e35  call    cs:__imp_ExReleaseResourceLite
0x1400f8e3c  nop     dword ptr [rax+rax+00h]
0x1400f8e41  call    cs:__imp_KeLeaveCriticalRegion
0x1400f8e48  nop     dword ptr [rax+rax+00h]
0x1400f8e4d  test    rdi, rdi
0x1400f8e50  jnz     short loc_1400F8E6A
0x1400f8e52  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400f8e56  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f8e5d  nop     dword ptr [rax+rax+00h]
0x1400f8e62  mov     r14, [r14]
0x1400f8e65  jmp     loc_1400F8DD0
0x1400f8e6a  mov     rcx, rdi
0x1400f8e6d  call    NvmeAdapterSubsystemPortAcquireRundown
0x1400f8e72  test    eax, eax
0x1400f8e74  js      short loc_1400F8E80
0x1400f8e76  test    r15b, r15b
0x1400f8e79  jz      short loc_1400F8E82
0x1400f8e7b  mov     [rsi], rbx
0x1400f8e7e  jmp     short loc_1400F8E92
0x1400f8e80  xor     edi, edi
0x1400f8e82  mov     rcx, [rbx+38h]; RunRefCacheAware
0x1400f8e86  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f8e8d  nop     dword ptr [rax+rax+00h]
0x1400f8e92  mov     rcx, [rbp+268h]
0x1400f8e99  add     rcx, 18h; Resource
0x1400f8e9d  call    cs:__imp_ExReleaseResourceLite
0x1400f8ea4  nop     dword ptr [rax+rax+00h]
0x1400f8ea9  call    cs:__imp_KeLeaveCriticalRegion
0x1400f8eb0  nop     dword ptr [rax+rax+00h]
0x1400f8eb5  mov     rax, rdi
0x1400f8eb8  add     rsp, 28h
0x1400f8ebc  pop     r15
0x1400f8ebe  pop     r14
0x1400f8ec0  pop     r13
0x1400f8ec2  pop     r12
0x1400f8ec4  pop     rdi
0x1400f8ec5  pop     rsi
0x1400f8ec6  pop     rbp
0x1400f8ec7  pop     rbx
0x1400f8ec8  retn
```

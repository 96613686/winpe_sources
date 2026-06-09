# NvmeAdapterFindNvmeController

- ea: `0x1400f8b90`
- end: `0x1400f8d64`
- name: `NvmeAdapterFindNvmeController`
- size: `468`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1400f8330`
- `0x1401a34ac`
- `0x1401a535c`
- `0x1401a6048`

## callees

- `0x1400f8b90`
- `0x1400fa1d0`
- `0x140100b40`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8bd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8c50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8bd3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f8c50`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8c9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8cf7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8d33`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8c9f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8cf7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f8d33`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8cc0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8ce4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8d07`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8cc0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8ce4`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400f8d07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8cab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8d3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8cab`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f8d3f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8be5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8c1e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8c65`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8be5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8c1e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f8c65`

## pseudocode

```c
_QWORD *__fastcall NvmeAdapterFindNvmeController(__int64 a1, _QWORD *a2, char a3, _QWORD *a4)
{
  _QWORD *v4; // rdi
  __int64 v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  _QWORD *i; // r14
  _QWORD *v11; // rbp
  _QWORD *j; // rax

  v4 = 0;
  if ( !a3 || a4 )
  {
    if ( a4 )
      *a4 = 0;
    v7 = *(_QWORD *)(a1 + 616);
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite((PERESOURCE)(v7 + 24), 1u);
    v8 = *(_QWORD **)(a1 + 616);
    v9 = (_QWORD *)*v8;
    if ( (_QWORD *)*v8 != v8 )
    {
      do
      {
        if ( (int)NvmeAdapterHostGatewayAcquireRundown(v9 - 3) >= 0 )
        {
          ExAcquireResourceSharedLite((PERESOURCE)(v9 + 45), 1u);
          for ( i = (_QWORD *)v9[42]; i != v9 + 42; i = (_QWORD *)*i )
          {
            v11 = i - 1;
            if ( (int)NvmeAdapterSubsystemPortAcquireRundown(i - 1) >= 0 )
            {
              v4 = 0;
              KeEnterCriticalRegion();
              ExAcquireResourceSharedLite((PERESOURCE)(v11 + 79), 1u);
              for ( j = (_QWORD *)v11[76]; j != v11 + 76; v4 = 0 )
              {
                v4 = j - 8;
                if ( a2 == j - 8 )
                  break;
                j = (_QWORD *)*j;
              }
              ExReleaseResourceLite((PERESOURCE)(v11 + 79));
              KeLeaveCriticalRegion();
              if ( v4 )
              {
                if ( a3 )
                  *a4 = v11;
                else
                  ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[5]);
                break;
              }
              ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v11[5]);
            }
          }
          ExReleaseResourceLite((PERESOURCE)(v9 + 45));
          ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)v9[4]);
          if ( v4 )
            break;
        }
        v9 = (_QWORD *)*v9;
      }
      while ( v9 != *(_QWORD **)(a1 + 616) );
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a1 + 616) + 24LL));
    KeLeaveCriticalRegion();
  }
  return v4;
}

```

## disassembly

```asm
0x1400f8b90  mov     [rsp+arg_0], rbx
0x1400f8b95  mov     [rsp+arg_10], r8b
0x1400f8b9a  mov     [rsp+arg_8], rdx
0x1400f8b9f  push    rbp
0x1400f8ba0  push    rsi
0x1400f8ba1  push    rdi
0x1400f8ba2  push    r12
0x1400f8ba4  push    r13
0x1400f8ba6  push    r14
0x1400f8ba8  push    r15
0x1400f8baa  sub     rsp, 20h
0x1400f8bae  xor     edi, edi
0x1400f8bb0  mov     rsi, r9
0x1400f8bb3  mov     r15, rcx
0x1400f8bb6  test    r8b, r8b
0x1400f8bb9  jz      short loc_1400F8BC4
0x1400f8bbb  test    r9, r9
0x1400f8bbe  jz      loc_1400F8D4B
0x1400f8bc4  test    rsi, rsi
0x1400f8bc7  jz      short loc_1400F8BCC
0x1400f8bc9  mov     [r9], rdi
0x1400f8bcc  mov     rbx, [rcx+268h]
0x1400f8bd3  call    cs:__imp_KeEnterCriticalRegion
0x1400f8bda  nop     dword ptr [rax+rax+00h]
0x1400f8bdf  mov     dl, 1; Wait
0x1400f8be1  lea     rcx, [rbx+18h]; Resource
0x1400f8be5  call    cs:__imp_ExAcquireResourceSharedLite
0x1400f8bec  nop     dword ptr [rax+rax+00h]
0x1400f8bf1  mov     rax, [r15+268h]
0x1400f8bf8  mov     rbx, [rax]
0x1400f8bfb  cmp     rbx, rax
0x1400f8bfe  jz      loc_1400F8D28
0x1400f8c04  lea     rcx, [rbx-18h]
0x1400f8c08  call    NvmeAdapterHostGatewayAcquireRundown
0x1400f8c0d  test    eax, eax
0x1400f8c0f  js      loc_1400F8D18
0x1400f8c15  lea     rcx, [rbx+168h]; Resource
0x1400f8c1c  mov     dl, 1; Wait
0x1400f8c1e  call    cs:__imp_ExAcquireResourceSharedLite
0x1400f8c25  nop     dword ptr [rax+rax+00h]
0x1400f8c2a  lea     r12, [rbx+150h]
0x1400f8c31  mov     r14, [r12]
0x1400f8c35  cmp     r14, r12
0x1400f8c38  jz      loc_1400F8CF0
0x1400f8c3e  lea     rbp, [r14-8]
0x1400f8c42  mov     rcx, rbp
0x1400f8c45  call    NvmeAdapterSubsystemPortAcquireRundown
0x1400f8c4a  test    eax, eax
0x1400f8c4c  js      short loc_1400F8CCC
0x1400f8c4e  xor     edi, edi
0x1400f8c50  call    cs:__imp_KeEnterCriticalRegion
0x1400f8c57  nop     dword ptr [rax+rax+00h]
0x1400f8c5c  lea     rcx, [rbp+278h]; Resource
0x1400f8c63  mov     dl, 1; Wait
0x1400f8c65  call    cs:__imp_ExAcquireResourceSharedLite
0x1400f8c6c  nop     dword ptr [rax+rax+00h]
0x1400f8c71  lea     rdx, [rbp+260h]
0x1400f8c78  mov     rax, [rdx]
0x1400f8c7b  cmp     rax, rdx
0x1400f8c7e  jz      short loc_1400F8C98
0x1400f8c80  mov     rcx, [rsp+58h+arg_8]
0x1400f8c85  lea     rdi, [rax-40h]
0x1400f8c89  cmp     rcx, rdi
0x1400f8c8c  jz      short loc_1400F8C98
0x1400f8c8e  mov     rax, [rax]
0x1400f8c91  xor     edi, edi
0x1400f8c93  cmp     rax, rdx
0x1400f8c96  jnz     short loc_1400F8C85
0x1400f8c98  lea     rcx, [rbp+278h]; Resource
0x1400f8c9f  call    cs:__imp_ExReleaseResourceLite
0x1400f8ca6  nop     dword ptr [rax+rax+00h]
0x1400f8cab  call    cs:__imp_KeLeaveCriticalRegion
0x1400f8cb2  nop     dword ptr [rax+rax+00h]
0x1400f8cb7  test    rdi, rdi
0x1400f8cba  jnz     short loc_1400F8CD4
0x1400f8cbc  mov     rcx, [rbp+28h]; RunRefCacheAware
0x1400f8cc0  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f8cc7  nop     dword ptr [rax+rax+00h]
0x1400f8ccc  mov     r14, [r14]
0x1400f8ccf  jmp     loc_1400F8C35
0x1400f8cd4  cmp     [rsp+58h+arg_10], 0
0x1400f8cd9  jz      short loc_1400F8CE0
0x1400f8cdb  mov     [rsi], rbp
0x1400f8cde  jmp     short loc_1400F8CF0
0x1400f8ce0  mov     rcx, [rbp+28h]; RunRefCacheAware
0x1400f8ce4  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f8ceb  nop     dword ptr [rax+rax+00h]
0x1400f8cf0  lea     rcx, [rbx+168h]; Resource
0x1400f8cf7  call    cs:__imp_ExReleaseResourceLite
0x1400f8cfe  nop     dword ptr [rax+rax+00h]
0x1400f8d03  mov     rcx, [rbx+20h]; RunRefCacheAware
0x1400f8d07  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400f8d0e  nop     dword ptr [rax+rax+00h]
0x1400f8d13  test    rdi, rdi
0x1400f8d16  jnz     short loc_1400F8D28
0x1400f8d18  mov     rbx, [rbx]
0x1400f8d1b  cmp     rbx, [r15+268h]
0x1400f8d22  jnz     loc_1400F8C04
0x1400f8d28  mov     rcx, [r15+268h]
0x1400f8d2f  add     rcx, 18h; Resource
0x1400f8d33  call    cs:__imp_ExReleaseResourceLite
0x1400f8d3a  nop     dword ptr [rax+rax+00h]
0x1400f8d3f  call    cs:__imp_KeLeaveCriticalRegion
0x1400f8d46  nop     dword ptr [rax+rax+00h]
0x1400f8d4b  mov     rbx, [rsp+58h+arg_0]
0x1400f8d50  mov     rax, rdi
0x1400f8d53  add     rsp, 20h
0x1400f8d57  pop     r15
0x1400f8d59  pop     r14
0x1400f8d5b  pop     r13
0x1400f8d5d  pop     r12
0x1400f8d5f  pop     rdi
0x1400f8d60  pop     rsi
0x1400f8d61  pop     rbp
0x1400f8d62  retn
```

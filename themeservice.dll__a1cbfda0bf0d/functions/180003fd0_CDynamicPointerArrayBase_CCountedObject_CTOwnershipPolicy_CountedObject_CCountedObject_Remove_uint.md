# CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(uint)

- ea: `0x180003fd0`
- end: `0x18000407e`
- name: `?Remove@?$CDynamicPointerArrayBase@VCCountedObject@@V?$CTOwnershipPolicy_CountedObject@VCCountedObject@@@@@@QEAAJI@Z`
- size: `174`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003280`
- `0x180003790`
- `0x180006580`
- `0x18000b180`

## callees

- `0x180003fd0`
- `0x18000f9ce`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall CDynamicPointerArrayBase<CCountedObject,CTOwnershipPolicy_CountedObject<CCountedObject>>::Remove(
        unsigned int *a1,
        unsigned int a2)
{
  __int64 v2; // r9
  unsigned int v4; // ecx
  __int64 v5; // rdi
  unsigned int v6; // eax
  void (__fastcall **v8)(__int64, __int64); // rdx

  v2 = *((_QWORD *)a1 + 1);
  if ( !v2 )
    return 3221225485LL;
  if ( a2 >= *a1 )
    return 3221225485LL;
  _mm_lfence();
  v4 = *a1;
  if ( a2 >= v4 )
    return 3221225485LL;
  v5 = *(_QWORD *)(8LL * a2 + *((_QWORD *)a1 + 1));
  v6 = 8 * (v4 + ~a2);
  if ( v6 )
    memmove_0((void *)(8LL * a2 + v2), (const void *)(v2 + 8LL * (a2 + 1)), v6);
  *(_QWORD *)(*((_QWORD *)a1 + 1) + 8LL * --*a1) = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 8), 0xFFFFFFFF) == 1 )
  {
    v8 = *(void (__fastcall ***)(__int64, __int64))v5;
    *(_BYTE *)(v5 + 12) = 1;
    (*v8)(v5, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x180003fd0  push    rbx
0x180003fd2  sub     rsp, 20h
0x180003fd6  mov     r9, [rcx+8]
0x180003fda  mov     rbx, rcx
0x180003fdd  test    r9, r9
0x180003fe0  jz      loc_180004073
0x180003fe6  cmp     edx, [rcx]
0x180003fe8  jnb     loc_180004073
0x180003fee  lfence
0x180003ff1  mov     ecx, [rcx]
0x180003ff3  cmp     edx, ecx
0x180003ff5  jnb     short loc_180004073
0x180003ff7  mov     eax, edx
0x180003ff9  mov     [rsp+28h+arg_0], rdi
0x180003ffe  lea     r10, ds:0[rax*8]
0x180004006  mov     rax, [rbx+8]
0x18000400a  mov     rdi, [r10+rax]
0x18000400e  mov     eax, edx
0x180004010  not     eax
0x180004012  add     eax, ecx
0x180004014  shl     eax, 3
0x180004017  test    eax, eax
0x180004019  jz      short loc_18000402E
0x18000401b  mov     r8d, eax; Size
0x18000401e  lea     rcx, [r10+r9]; void *
0x180004022  lea     eax, [rdx+1]
0x180004025  lea     rdx, [r9+rax*8]; Src
0x180004029  call    memmove_0
0x18000402e  mov     ecx, [rbx]
0x180004030  xor     edx, edx
0x180004032  mov     rax, [rbx+8]
0x180004036  dec     ecx
0x180004038  mov     [rax+rcx*8], rdx
0x18000403c  mov     edx, 0FFFFFFFFh
0x180004041  dec     dword ptr [rbx]
0x180004043  lock xadd [rdi+8], edx
0x180004048  cmp     edx, 1
0x18000404b  jz      short loc_18000405A
0x18000404d  mov     rdi, [rsp+28h+arg_0]
0x180004052  xor     eax, eax
0x180004054  add     rsp, 20h
0x180004058  pop     rbx
0x180004059  retn
0x18000405a  mov     rdx, [rdi]
0x18000405d  mov     rcx, rdi
0x180004060  mov     byte ptr [rdi+0Ch], 1
0x180004064  mov     rax, [rdx]
0x180004067  mov     edx, 1
0x18000406c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004071  jmp     short loc_18000404D
0x180004073  mov     eax, 0C000000Dh
0x180004078  add     rsp, 20h
0x18000407c  pop     rbx
0x18000407d  retn
```

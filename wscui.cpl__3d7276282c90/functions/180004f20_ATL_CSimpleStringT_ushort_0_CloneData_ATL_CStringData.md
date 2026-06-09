# ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)

- ea: `0x180004f20`
- end: `0x180004fa5`
- name: `?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z`
- size: `133`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180004dd0`
- `0x1800052cc`
- `0x18000592c`
- `0x180005cf4`
- `0x18000750c`

## callees

- `0x180004d04`
- `0x180004f20`
- `0x18000c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180004f91`
- `msvcrt!memcpy_s` at `0x180004f91`

## pseudocode

```c
volatile signed __int32 *__fastcall ATL::CSimpleStringT<unsigned short,0>::CloneData(volatile signed __int32 *a1)
{
  __int64 (__fastcall ***v2)(_QWORD, _QWORD, __int64); // rax
  volatile signed __int32 *v3; // rdi
  __int64 v4; // rax
  rsize_t v5; // r9

  v2 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a1 + 32LL))(*(_QWORD *)a1);
  if ( *((int *)a1 + 4) >= 0 && v2 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))a1 )
  {
    v3 = a1;
    _InterlockedIncrement(a1 + 4);
  }
  else
  {
    v4 = (**v2)(v2, *((unsigned int *)a1 + 2), 2);
    v3 = (volatile signed __int32 *)v4;
    if ( !v4 )
      ATL::CSimpleStringT<unsigned short,0>::ThrowMemoryException();
    *(_DWORD *)(v4 + 8) = *((_DWORD *)a1 + 2);
    v5 = 2LL * (*((_DWORD *)a1 + 2) + 1);
    memcpy_s((void *const)(v4 + 24), v5, (const void *const)(a1 + 6), v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180004f20  mov     [rsp+arg_0], rbx
0x180004f25  push    rdi
0x180004f26  sub     rsp, 20h
0x180004f2a  mov     rbx, rcx
0x180004f2d  mov     rcx, [rcx]
0x180004f30  mov     rax, [rcx]
0x180004f33  mov     rax, [rax+20h]
0x180004f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3c  cmp     dword ptr [rbx+10h], 0
0x180004f40  mov     rcx, rax
0x180004f43  jl      short loc_180004F53
0x180004f45  cmp     rax, [rbx]
0x180004f48  jnz     short loc_180004F53
0x180004f4a  mov     rdi, rbx
0x180004f4d  lock inc dword ptr [rbx+10h]
0x180004f51  jmp     short loc_180004F97
0x180004f53  mov     rax, [rax]
0x180004f56  mov     r8d, 2
0x180004f5c  mov     edx, [rbx+8]
0x180004f5f  mov     rax, [rax]
0x180004f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f67  mov     rdi, rax
0x180004f6a  test    rax, rax
0x180004f6d  jnz     short loc_180004F75
0x180004f6f  call    ?ThrowMemoryException@?$CSimpleStringT@G$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<ushort,0>::ThrowMemoryException(void)
0x180004f75  mov     eax, [rbx+8]
0x180004f78  lea     r8, [rbx+18h]; Source
0x180004f7c  mov     [rdi+8], eax
0x180004f7f  lea     rcx, [rdi+18h]; Destination
0x180004f83  mov     eax, [rbx+8]
0x180004f86  inc     eax
0x180004f88  movsxd  rdx, eax
0x180004f8b  add     rdx, rdx; DestinationSize
0x180004f8e  mov     r9, rdx; SourceSize
0x180004f91  call    cs:__imp_memcpy_s
0x180004f97  mov     rbx, [rsp+28h+arg_0]
0x180004f9c  mov     rax, rdi
0x180004f9f  add     rsp, 20h
0x180004fa3  pop     rdi
0x180004fa4  retn
```

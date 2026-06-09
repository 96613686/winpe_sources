# ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(unsigned __int64,int)

- ea: `0x140002c50`
- end: `0x140002cd6`
- name: `?SetCount@?$CAtlArray@V?$CAutoPtr@VCAccessAce@CDacl@ATL@@@ATL@@V?$CAutoPtrElementTraits@VCAccessAce@CDacl@ATL@@@2@@ATL@@QEAA_N_KH@Z`
- size: `134`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400021b0`
- `0x140002250`
- `0x1400022d0`

## callees

- `0x140002c50`
- `0x14000c010`

## import_xrefs

- `msvcrt!free` at `0x140002caa`
- `msvcrt!free` at `0x140002caa`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::SetCount(
        __int64 a1)
{
  _QWORD *v1; // rdi
  unsigned __int64 v3; // rbx
  unsigned __int64 v4; // rbp
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  char result; // al

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = 0;
    v4 = *(_QWORD *)(a1 + 8);
    if ( v4 )
    {
      do
      {
        v5 = (void (__fastcall ***)(_QWORD, __int64))v1[v3];
        if ( v5 )
          (**v5)(v5, 1);
        v1[v3++] = 0;
      }
      while ( v3 < v4 );
    }
    free(*(void **)a1);
    *(_QWORD *)a1 = 0;
  }
  *(_QWORD *)(a1 + 8) = 0;
  result = 1;
  *(_QWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x140002c50  mov     [rsp+arg_10], rsi
0x140002c55  push    rdi
0x140002c56  push    r14
0x140002c58  push    r15
0x140002c5a  sub     rsp, 20h
0x140002c5e  mov     rdi, [rcx]
0x140002c61  xor     r15d, r15d
0x140002c64  mov     rsi, rcx
0x140002c67  test    rdi, rdi
0x140002c6a  jz      short loc_140002CBD
0x140002c6c  mov     [rsp+38h+arg_0], rbx
0x140002c71  mov     ebx, r15d
0x140002c74  mov     [rsp+38h+arg_8], rbp
0x140002c79  mov     rbp, [rcx+8]
0x140002c7d  test    rbp, rbp
0x140002c80  jz      short loc_140002CA7
0x140002c82  mov     rcx, [rdi+rbx*8]
0x140002c86  test    rcx, rcx
0x140002c89  jz      short loc_140002C9B
0x140002c8b  mov     rax, [rcx]
0x140002c8e  mov     edx, 1
0x140002c93  mov     rax, [rax]
0x140002c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c9b  mov     [rdi+rbx*8], r15
0x140002c9f  inc     rbx
0x140002ca2  cmp     rbx, rbp
0x140002ca5  jb      short loc_140002C82
0x140002ca7  mov     rcx, [rsi]; Block
0x140002caa  call    cs:__imp_free
0x140002cb0  mov     rbp, [rsp+38h+arg_8]
0x140002cb5  mov     rbx, [rsp+38h+arg_0]
0x140002cba  mov     [rsi], r15
0x140002cbd  mov     [rsi+8], r15
0x140002cc1  mov     al, 1
0x140002cc3  mov     [rsi+10h], r15
0x140002cc7  mov     rsi, [rsp+38h+arg_10]
0x140002ccc  add     rsp, 20h
0x140002cd0  pop     r15
0x140002cd2  pop     r14
0x140002cd4  pop     rdi
0x140002cd5  retn
```

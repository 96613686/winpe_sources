# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800114a0`
- end: `0x180011548`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000fdc8`
- `0x180011550`

## callees

- `0x18000213c`
- `0x1800114a0`
- `0x1800137dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800114f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001150b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800114f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001150b`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // edi
  unsigned int v5; // edx
  void *v6; // rcx
  __int64 result; // rax

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        __debugbreak();
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x180011547LL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v2 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    free(v6);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1800114a0  mov     [rsp+arg_0], rbx
0x1800114a5  mov     [rsp+arg_8], rsi
0x1800114aa  push    rdi
0x1800114ab  sub     rsp, 20h
0x1800114af  mov     eax, [rcx+10h]
0x1800114b2  mov     rbx, rcx
0x1800114b5  test    eax, eax
0x1800114b7  jle     short loc_1800114ED
0x1800114b9  xor     edi, edi
0x1800114bb  test    edi, edi
0x1800114bd  js      short loc_180011532
0x1800114bf  cmp     edi, eax
0x1800114c1  jge     short loc_180011532
0x1800114c3  mov     rcx, [rbx]
0x1800114c6  movsxd  rsi, edi
0x1800114c9  mov     rcx, [rcx+rsi*8]; Block
0x1800114cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800114d2  cmp     edi, [rbx+10h]
0x1800114d5  jge     short loc_18001153D
0x1800114d7  mov     rcx, [rbx+8]
0x1800114db  mov     rcx, [rcx+rsi*8]; Block
0x1800114df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800114e4  mov     eax, [rbx+10h]
0x1800114e7  inc     edi
0x1800114e9  cmp     edi, eax
0x1800114eb  jl      short loc_1800114BB
0x1800114ed  mov     rcx, [rbx]; Block
0x1800114f0  test    rcx, rcx
0x1800114f3  jz      short loc_180011502
0x1800114f5  call    cs:__imp_free
0x1800114fb  mov     qword ptr [rbx], 0
0x180011502  mov     rcx, [rbx+8]; Block
0x180011506  test    rcx, rcx
0x180011509  jz      short loc_180011519
0x18001150b  call    cs:__imp_free
0x180011511  mov     qword ptr [rbx+8], 0
0x180011519  mov     rsi, [rsp+28h+arg_8]
0x18001151e  xor     eax, eax
0x180011520  mov     dword ptr [rbx+10h], 0
0x180011527  mov     rbx, [rsp+28h+arg_0]
0x18001152c  add     rsp, 20h
0x180011530  pop     rdi
0x180011531  retn
0x180011532  mov     ecx, 0C000008Ch; unsigned int
0x180011537  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18001153c  int     3; Trap to Debugger
0x18001153d  mov     ecx, 0C000008Ch; unsigned int
0x180011542  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1400032c0`
- end: `0x140003368`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140001ff4`
- `0x140003370`

## callees

- `0x140001110`
- `0x1400032c0`
- `0x140005b9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003315`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000332b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003315`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000332b`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // edi
  void *v4; // rcx
  __int64 result; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C);
        JUMPOUT(0x140003367LL);
      }
      operator delete(*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v1 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    free(v4);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1400032c0  mov     [rsp+arg_0], rbx
0x1400032c5  mov     [rsp+arg_8], rsi
0x1400032ca  push    rdi
0x1400032cb  sub     rsp, 20h
0x1400032cf  mov     eax, [rcx+10h]
0x1400032d2  mov     rbx, rcx
0x1400032d5  test    eax, eax
0x1400032d7  jle     short loc_14000330D
0x1400032d9  xor     edi, edi
0x1400032db  test    edi, edi
0x1400032dd  js      short loc_140003352
0x1400032df  cmp     edi, eax
0x1400032e1  jge     short loc_140003352
0x1400032e3  mov     rcx, [rbx]
0x1400032e6  movsxd  rsi, edi
0x1400032e9  mov     rcx, [rcx+rsi*8]; Block
0x1400032ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400032f2  cmp     edi, [rbx+10h]
0x1400032f5  jge     short loc_14000335D
0x1400032f7  mov     rcx, [rbx+8]
0x1400032fb  mov     rcx, [rcx+rsi*8]; Block
0x1400032ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003304  mov     eax, [rbx+10h]
0x140003307  inc     edi
0x140003309  cmp     edi, eax
0x14000330b  jl      short loc_1400032DB
0x14000330d  mov     rcx, [rbx]; Block
0x140003310  test    rcx, rcx
0x140003313  jz      short loc_140003322
0x140003315  call    cs:__imp_free
0x14000331b  mov     qword ptr [rbx], 0
0x140003322  mov     rcx, [rbx+8]; Block
0x140003326  test    rcx, rcx
0x140003329  jz      short loc_140003339
0x14000332b  call    cs:__imp_free
0x140003331  mov     qword ptr [rbx+8], 0
0x140003339  mov     rsi, [rsp+28h+arg_8]
0x14000333e  xor     eax, eax
0x140003340  mov     dword ptr [rbx+10h], 0
0x140003347  mov     rbx, [rsp+28h+arg_0]
0x14000334c  add     rsp, 20h
0x140003350  pop     rdi
0x140003351  retn
0x140003352  mov     ecx, 0C000008Ch; unsigned int
0x140003357  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x14000335c  int     3; Trap to Debugger
0x14000335d  mov     ecx, 0C000008Ch; unsigned int
0x140003362  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

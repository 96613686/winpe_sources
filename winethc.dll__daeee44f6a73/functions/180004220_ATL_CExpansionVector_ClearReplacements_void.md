# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004220`
- end: `0x1800042d9`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002eb8`
- `0x1800042e0`

## callees

- `0x1800012cc`
- `0x180004220`
- `0x18000d798`

## import_xrefs

- `msvcrt!free` at `0x180004279`
- `msvcrt!free` at `0x180004295`
- `msvcrt!free` at `0x180004279`
- `msvcrt!free` at `0x180004295`

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
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v5);
        JUMPOUT(0x1800042D8LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
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
0x180004220  mov     [rsp+arg_0], rbx
0x180004225  mov     [rsp+arg_8], rsi
0x18000422a  push    rdi
0x18000422b  sub     rsp, 20h
0x18000422f  mov     eax, [rcx+10h]
0x180004232  mov     rbx, rcx
0x180004235  test    eax, eax
0x180004237  jle     short loc_180004271
0x180004239  xor     edi, edi
0x18000423b  test    edi, edi
0x18000423d  js      loc_1800042C3
0x180004243  cmp     edi, eax
0x180004245  jge     short loc_1800042C3
0x180004247  mov     rcx, [rbx]
0x18000424a  movsxd  rsi, edi
0x18000424d  mov     rcx, [rcx+rsi*8]; Block
0x180004251  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004256  cmp     edi, [rbx+10h]
0x180004259  jge     short loc_1800042CE
0x18000425b  mov     rcx, [rbx+8]
0x18000425f  mov     rcx, [rcx+rsi*8]; Block
0x180004263  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004268  mov     eax, [rbx+10h]
0x18000426b  inc     edi
0x18000426d  cmp     edi, eax
0x18000426f  jl      short loc_18000423B
0x180004271  mov     rcx, [rbx]; Block
0x180004274  test    rcx, rcx
0x180004277  jz      short loc_18000428C
0x180004279  call    cs:__imp_free
0x180004280  nop     dword ptr [rax+rax+00h]
0x180004285  mov     qword ptr [rbx], 0
0x18000428c  mov     rcx, [rbx+8]; Block
0x180004290  test    rcx, rcx
0x180004293  jz      short loc_1800042A9
0x180004295  call    cs:__imp_free
0x18000429c  nop     dword ptr [rax+rax+00h]
0x1800042a1  mov     qword ptr [rbx+8], 0
0x1800042a9  mov     rsi, [rsp+28h+arg_8]
0x1800042ae  xor     eax, eax
0x1800042b0  mov     dword ptr [rbx+10h], 0
0x1800042b7  mov     rbx, [rsp+28h+arg_0]
0x1800042bc  add     rsp, 20h
0x1800042c0  pop     rdi
0x1800042c1  retn
0x1800042c3  mov     ecx, 0C000008Ch; unsigned int
0x1800042c8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1800042cd  int     3; Trap to Debugger
0x1800042ce  mov     ecx, 0C000008Ch; unsigned int
0x1800042d3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

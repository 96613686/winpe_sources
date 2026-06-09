# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003898`
- end: `0x180003942`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002bcc`
- `0x180003950`

## callees

- `0x180003898`
- `0x180005b7c`

## import_xrefs

- `msvcrt!free` at `0x1800038ef`
- `msvcrt!free` at `0x180003905`
- `msvcrt!free` at `0x1800038ef`
- `msvcrt!free` at `0x180003905`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038d8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038c5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800038d8`

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
        JUMPOUT(0x180003941LL);
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
0x180003898  mov     [rsp+arg_0], rbx
0x18000389d  mov     [rsp+arg_8], rsi
0x1800038a2  push    rdi
0x1800038a3  sub     rsp, 20h
0x1800038a7  mov     eax, [rcx+10h]
0x1800038aa  mov     rbx, rcx
0x1800038ad  test    eax, eax
0x1800038af  jle     short loc_1800038E7
0x1800038b1  xor     edi, edi
0x1800038b3  test    edi, edi
0x1800038b5  js      short loc_18000392C
0x1800038b7  cmp     edi, eax
0x1800038b9  jge     short loc_18000392C
0x1800038bb  mov     rcx, [rbx]
0x1800038be  movsxd  rsi, edi
0x1800038c1  mov     rcx, [rcx+rsi*8]
0x1800038c5  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800038cb  cmp     edi, [rbx+10h]
0x1800038ce  jge     short loc_180003937
0x1800038d0  mov     rcx, [rbx+8]
0x1800038d4  mov     rcx, [rcx+rsi*8]
0x1800038d8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800038de  mov     eax, [rbx+10h]
0x1800038e1  inc     edi
0x1800038e3  cmp     edi, eax
0x1800038e5  jl      short loc_1800038B3
0x1800038e7  mov     rcx, [rbx]; Block
0x1800038ea  test    rcx, rcx
0x1800038ed  jz      short loc_1800038FC
0x1800038ef  call    cs:__imp_free
0x1800038f5  mov     qword ptr [rbx], 0
0x1800038fc  mov     rcx, [rbx+8]; Block
0x180003900  test    rcx, rcx
0x180003903  jz      short loc_180003913
0x180003905  call    cs:__imp_free
0x18000390b  mov     qword ptr [rbx+8], 0
0x180003913  mov     rsi, [rsp+28h+arg_8]
0x180003918  xor     eax, eax
0x18000391a  mov     dword ptr [rbx+10h], 0
0x180003921  mov     rbx, [rsp+28h+arg_0]
0x180003926  add     rsp, 20h
0x18000392a  pop     rdi
0x18000392b  retn
0x18000392c  mov     ecx, 0C000008Ch; unsigned int
0x180003931  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003936  int     3; Trap to Debugger
0x180003937  mov     ecx, 0C000008Ch; unsigned int
0x18000393c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

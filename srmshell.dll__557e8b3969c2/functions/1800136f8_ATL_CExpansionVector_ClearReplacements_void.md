# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800136f8`
- end: `0x1800137a2`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180011f90`
- `0x18001202c`
- `0x1800137b0`

## callees

- `0x1800136f8`
- `0x180015ac8`

## import_xrefs

- `msvcrt!free` at `0x18001374f`
- `msvcrt!free` at `0x180013765`
- `msvcrt!free` at `0x18001374f`
- `msvcrt!free` at `0x180013765`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180013725`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180013738`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180013725`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180013738`

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
        JUMPOUT(0x1800137A1LL);
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
0x1800136f8  mov     [rsp+arg_0], rbx
0x1800136fd  mov     [rsp+arg_8], rsi
0x180013702  push    rdi
0x180013703  sub     rsp, 20h
0x180013707  mov     eax, [rcx+10h]
0x18001370a  mov     rbx, rcx
0x18001370d  test    eax, eax
0x18001370f  jle     short loc_180013747
0x180013711  xor     edi, edi
0x180013713  test    edi, edi
0x180013715  js      short loc_18001378C
0x180013717  cmp     edi, eax
0x180013719  jge     short loc_18001378C
0x18001371b  mov     rcx, [rbx]
0x18001371e  movsxd  rsi, edi
0x180013721  mov     rcx, [rcx+rsi*8]
0x180013725  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001372b  cmp     edi, [rbx+10h]
0x18001372e  jge     short loc_180013797
0x180013730  mov     rcx, [rbx+8]
0x180013734  mov     rcx, [rcx+rsi*8]
0x180013738  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001373e  mov     eax, [rbx+10h]
0x180013741  inc     edi
0x180013743  cmp     edi, eax
0x180013745  jl      short loc_180013713
0x180013747  mov     rcx, [rbx]; Block
0x18001374a  test    rcx, rcx
0x18001374d  jz      short loc_18001375C
0x18001374f  call    cs:__imp_free
0x180013755  mov     qword ptr [rbx], 0
0x18001375c  mov     rcx, [rbx+8]; Block
0x180013760  test    rcx, rcx
0x180013763  jz      short loc_180013773
0x180013765  call    cs:__imp_free
0x18001376b  mov     qword ptr [rbx+8], 0
0x180013773  mov     rsi, [rsp+28h+arg_8]
0x180013778  xor     eax, eax
0x18001377a  mov     dword ptr [rbx+10h], 0
0x180013781  mov     rbx, [rsp+28h+arg_0]
0x180013786  add     rsp, 20h
0x18001378a  pop     rdi
0x18001378b  retn
0x18001378c  mov     ecx, 0C000008Ch; unsigned int
0x180013791  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180013796  int     3; Trap to Debugger
0x180013797  mov     ecx, 0C000008Ch; unsigned int
0x18001379c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

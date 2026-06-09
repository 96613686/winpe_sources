# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180008cbc`
- end: `0x180008d66`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `170`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, int, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007df8`
- `0x180008d70`

## callees

- `0x180008cbc`
- `0x18000c1d4`

## import_xrefs

- `msvcrt!free` at `0x180008d13`
- `msvcrt!free` at `0x180008d29`
- `msvcrt!free` at `0x180008d13`
- `msvcrt!free` at `0x180008d29`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ce9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008cfc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008ce9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180008cfc`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, int a2, unsigned int a3)
{
  int v3; // eax
  int i; // edi
  int v6; // edx
  unsigned int v7; // r8d
  void *v8; // rcx
  __int64 result; // rax

  v3 = *((_DWORD *)this + 4);
  if ( v3 > 0 )
  {
    for ( i = 0; i < v3; ++i )
    {
      if ( i < 0 || i >= v3 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, a2, a3);
        __debugbreak();
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      if ( i >= *((_DWORD *)this + 4) )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0xC000008CLL, v6, v7);
        JUMPOUT(0x180008D65LL);
      }
      operator delete[](*(void **)(*((_QWORD *)this + 1) + 8LL * i));
      v3 = *((_DWORD *)this + 4);
    }
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v8 = (void *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    free(v8);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180008cbc  mov     [rsp+arg_0], rbx
0x180008cc1  mov     [rsp+arg_8], rsi
0x180008cc6  push    rdi
0x180008cc7  sub     rsp, 20h
0x180008ccb  mov     eax, [rcx+10h]
0x180008cce  mov     rbx, rcx
0x180008cd1  test    eax, eax
0x180008cd3  jle     short loc_180008D0B
0x180008cd5  xor     edi, edi
0x180008cd7  test    edi, edi
0x180008cd9  js      short loc_180008D50
0x180008cdb  cmp     edi, eax
0x180008cdd  jge     short loc_180008D50
0x180008cdf  mov     rcx, [rbx]
0x180008ce2  movsxd  rsi, edi
0x180008ce5  mov     rcx, [rcx+rsi*8]
0x180008ce9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008cef  cmp     edi, [rbx+10h]
0x180008cf2  jge     short loc_180008D5B
0x180008cf4  mov     rcx, [rbx+8]
0x180008cf8  mov     rcx, [rcx+rsi*8]
0x180008cfc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180008d02  mov     eax, [rbx+10h]
0x180008d05  inc     edi
0x180008d07  cmp     edi, eax
0x180008d09  jl      short loc_180008CD7
0x180008d0b  mov     rcx, [rbx]; Block
0x180008d0e  test    rcx, rcx
0x180008d11  jz      short loc_180008D20
0x180008d13  call    cs:__imp_free
0x180008d19  mov     qword ptr [rbx], 0
0x180008d20  mov     rcx, [rbx+8]; Block
0x180008d24  test    rcx, rcx
0x180008d27  jz      short loc_180008D37
0x180008d29  call    cs:__imp_free
0x180008d2f  mov     qword ptr [rbx+8], 0
0x180008d37  mov     rsi, [rsp+28h+arg_8]
0x180008d3c  xor     eax, eax
0x180008d3e  mov     dword ptr [rbx+10h], 0
0x180008d45  mov     rbx, [rsp+28h+arg_0]
0x180008d4a  add     rsp, 20h
0x180008d4e  pop     rdi
0x180008d4f  retn
0x180008d50  mov     ecx, 0C000008Ch; this
0x180008d55  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180008d5a  int     3; Trap to Debugger
0x180008d5b  mov     ecx, 0C000008Ch; this
0x180008d60  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```

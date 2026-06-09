# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x14000302c`
- end: `0x1400030d4`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140002228`
- `0x1400030e0`

## callees

- `0x1400011b0`
- `0x14000302c`
- `0x14000539c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003081`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003097`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003081`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140003097`

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
        JUMPOUT(0x1400030D3LL);
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
0x14000302c  mov     [rsp+arg_0], rbx
0x140003031  mov     [rsp+arg_8], rsi
0x140003036  push    rdi
0x140003037  sub     rsp, 20h
0x14000303b  mov     eax, [rcx+10h]
0x14000303e  mov     rbx, rcx
0x140003041  test    eax, eax
0x140003043  jle     short loc_140003079
0x140003045  xor     edi, edi
0x140003047  test    edi, edi
0x140003049  js      short loc_1400030BE
0x14000304b  cmp     edi, eax
0x14000304d  jge     short loc_1400030BE
0x14000304f  mov     rcx, [rbx]
0x140003052  movsxd  rsi, edi
0x140003055  mov     rcx, [rcx+rsi*8]; Block
0x140003059  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000305e  cmp     edi, [rbx+10h]
0x140003061  jge     short loc_1400030C9
0x140003063  mov     rcx, [rbx+8]
0x140003067  mov     rcx, [rcx+rsi*8]; Block
0x14000306b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003070  mov     eax, [rbx+10h]
0x140003073  inc     edi
0x140003075  cmp     edi, eax
0x140003077  jl      short loc_140003047
0x140003079  mov     rcx, [rbx]; Block
0x14000307c  test    rcx, rcx
0x14000307f  jz      short loc_14000308E
0x140003081  call    cs:__imp_free
0x140003087  mov     qword ptr [rbx], 0
0x14000308e  mov     rcx, [rbx+8]; Block
0x140003092  test    rcx, rcx
0x140003095  jz      short loc_1400030A5
0x140003097  call    cs:__imp_free
0x14000309d  mov     qword ptr [rbx+8], 0
0x1400030a5  mov     rsi, [rsp+28h+arg_8]
0x1400030aa  xor     eax, eax
0x1400030ac  mov     dword ptr [rbx+10h], 0
0x1400030b3  mov     rbx, [rsp+28h+arg_0]
0x1400030b8  add     rsp, 20h
0x1400030bc  pop     rdi
0x1400030bd  retn
0x1400030be  mov     ecx, 0C000008Ch; unsigned int
0x1400030c3  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x1400030c8  int     3; Trap to Debugger
0x1400030c9  mov     ecx, 0C000008Ch; unsigned int
0x1400030ce  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

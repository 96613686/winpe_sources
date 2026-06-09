# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180003384`
- end: `0x180003441`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `189`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002718`
- `0x180003450`

## callees

- `0x1800015d4`
- `0x180003384`
- `0x180005404`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033fd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033e1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800033fd`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int v3; // esi
  __int64 v5; // rdi
  unsigned int v6; // edx
  void *v7; // rcx
  __int64 result; // rax

  v2 = *((_DWORD *)this + 4);
  v3 = 0;
  if ( v2 > 0 )
  {
    v5 = 0;
    do
    {
      if ( v5 < 0 || v3 >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        __debugbreak();
      }
      operator delete(*(void **)(v5 + *(_QWORD *)this));
      if ( v3 >= *((_DWORD *)this + 4) )
      {
        ATL::_AtlRaiseException(0xC000008C, v6);
        JUMPOUT(0x180003440LL);
      }
      operator delete(*(void **)(v5 + *((_QWORD *)this + 1)));
      v2 = *((_DWORD *)this + 4);
      ++v3;
      v5 += 8;
    }
    while ( v3 < v2 );
  }
  if ( *(_QWORD *)this )
  {
    free(*(void **)this);
    *(_QWORD *)this = 0;
  }
  v7 = (void *)*((_QWORD *)this + 1);
  if ( v7 )
  {
    free(v7);
    *((_QWORD *)this + 1) = 0;
  }
  result = 0;
  *((_DWORD *)this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x180003384  mov     [rsp+arg_0], rbx
0x180003389  mov     [rsp+arg_8], rsi
0x18000338e  push    rdi
0x18000338f  sub     rsp, 20h
0x180003393  mov     eax, [rcx+10h]
0x180003396  xor     esi, esi
0x180003398  mov     rbx, rcx
0x18000339b  test    eax, eax
0x18000339d  jle     short loc_1800033D9
0x18000339f  xor     edi, edi
0x1800033a1  test    rdi, rdi
0x1800033a4  js      loc_18000342B
0x1800033aa  cmp     esi, eax
0x1800033ac  jge     short loc_18000342B
0x1800033ae  mov     rcx, [rbx]
0x1800033b1  mov     rcx, [rdi+rcx]; Block
0x1800033b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800033ba  cmp     esi, [rbx+10h]
0x1800033bd  jge     short loc_180003436
0x1800033bf  mov     rcx, [rbx+8]
0x1800033c3  mov     rcx, [rdi+rcx]; Block
0x1800033c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800033cc  mov     eax, [rbx+10h]
0x1800033cf  inc     esi
0x1800033d1  add     rdi, 8
0x1800033d5  cmp     esi, eax
0x1800033d7  jl      short loc_1800033A1
0x1800033d9  mov     rcx, [rbx]; Block
0x1800033dc  test    rcx, rcx
0x1800033df  jz      short loc_1800033F4
0x1800033e1  call    cs:__imp_free
0x1800033e8  nop     dword ptr [rax+rax+00h]
0x1800033ed  mov     qword ptr [rbx], 0
0x1800033f4  mov     rcx, [rbx+8]; Block
0x1800033f8  test    rcx, rcx
0x1800033fb  jz      short loc_180003411
0x1800033fd  call    cs:__imp_free
0x180003404  nop     dword ptr [rax+rax+00h]
0x180003409  mov     qword ptr [rbx+8], 0
0x180003411  mov     rsi, [rsp+28h+arg_8]
0x180003416  xor     eax, eax
0x180003418  mov     dword ptr [rbx+10h], 0
0x18000341f  mov     rbx, [rsp+28h+arg_0]
0x180003424  add     rsp, 20h
0x180003428  pop     rdi
0x180003429  retn
0x18000342b  mov     ecx, 0C000008Ch; unsigned int
0x180003430  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180003435  int     3; Trap to Debugger
0x180003436  mov     ecx, 0C000008Ch; unsigned int
0x18000343b  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

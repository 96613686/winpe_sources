# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180002f58`
- end: `0x180003000`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002338`
- `0x180003010`

## callees

- `0x180001534`
- `0x180002f58`
- `0x180004a7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fc3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fad`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180002fc3`

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
        JUMPOUT(0x180002FFFLL);
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
0x180002f58  mov     [rsp+arg_0], rbx
0x180002f5d  mov     [rsp+arg_8], rsi
0x180002f62  push    rdi
0x180002f63  sub     rsp, 20h
0x180002f67  mov     eax, [rcx+10h]
0x180002f6a  mov     rbx, rcx
0x180002f6d  test    eax, eax
0x180002f6f  jle     short loc_180002FA5
0x180002f71  xor     edi, edi
0x180002f73  test    edi, edi
0x180002f75  js      short loc_180002FEA
0x180002f77  cmp     edi, eax
0x180002f79  jge     short loc_180002FEA
0x180002f7b  mov     rcx, [rbx]
0x180002f7e  movsxd  rsi, edi
0x180002f81  mov     rcx, [rcx+rsi*8]; Block
0x180002f85  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002f8a  cmp     edi, [rbx+10h]
0x180002f8d  jge     short loc_180002FF5
0x180002f8f  mov     rcx, [rbx+8]
0x180002f93  mov     rcx, [rcx+rsi*8]; Block
0x180002f97  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002f9c  mov     eax, [rbx+10h]
0x180002f9f  inc     edi
0x180002fa1  cmp     edi, eax
0x180002fa3  jl      short loc_180002F73
0x180002fa5  mov     rcx, [rbx]; Block
0x180002fa8  test    rcx, rcx
0x180002fab  jz      short loc_180002FBA
0x180002fad  call    cs:__imp_free
0x180002fb3  mov     qword ptr [rbx], 0
0x180002fba  mov     rcx, [rbx+8]; Block
0x180002fbe  test    rcx, rcx
0x180002fc1  jz      short loc_180002FD1
0x180002fc3  call    cs:__imp_free
0x180002fc9  mov     qword ptr [rbx+8], 0
0x180002fd1  mov     rsi, [rsp+28h+arg_8]
0x180002fd6  xor     eax, eax
0x180002fd8  mov     dword ptr [rbx+10h], 0
0x180002fdf  mov     rbx, [rsp+28h+arg_0]
0x180002fe4  add     rsp, 20h
0x180002fe8  pop     rdi
0x180002fe9  retn
0x180002fea  mov     ecx, 0C000008Ch; unsigned int
0x180002fef  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180002ff4  int     3; Trap to Debugger
0x180002ff5  mov     ecx, 0C000008Ch; unsigned int
0x180002ffa  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

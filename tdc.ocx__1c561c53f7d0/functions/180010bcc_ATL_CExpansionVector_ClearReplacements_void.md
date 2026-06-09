# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180010bcc`
- end: `0x180010c74`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `168`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000f0b0`
- `0x180010c80`

## callees

- `0x1800011a0`
- `0x180009994`
- `0x180010bcc`

## import_xrefs

- `msvcrt!free` at `0x180010c21`
- `msvcrt!free` at `0x180010c37`
- `msvcrt!free` at `0x180010c21`
- `msvcrt!free` at `0x180010c37`

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
        JUMPOUT(0x180010C73LL);
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
0x180010bcc  mov     [rsp+arg_0], rbx
0x180010bd1  mov     [rsp+arg_8], rsi
0x180010bd6  push    rdi
0x180010bd7  sub     rsp, 20h
0x180010bdb  mov     eax, [rcx+10h]
0x180010bde  mov     rbx, rcx
0x180010be1  test    eax, eax
0x180010be3  jle     short loc_180010C19
0x180010be5  xor     edi, edi
0x180010be7  test    edi, edi
0x180010be9  js      short loc_180010C5E
0x180010beb  cmp     edi, eax
0x180010bed  jge     short loc_180010C5E
0x180010bef  mov     rcx, [rbx]
0x180010bf2  movsxd  rsi, edi
0x180010bf5  mov     rcx, [rcx+rsi*8]; Block
0x180010bf9  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180010bfe  cmp     edi, [rbx+10h]
0x180010c01  jge     short loc_180010C69
0x180010c03  mov     rcx, [rbx+8]
0x180010c07  mov     rcx, [rcx+rsi*8]; Block
0x180010c0b  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180010c10  mov     eax, [rbx+10h]
0x180010c13  inc     edi
0x180010c15  cmp     edi, eax
0x180010c17  jl      short loc_180010BE7
0x180010c19  mov     rcx, [rbx]; Block
0x180010c1c  test    rcx, rcx
0x180010c1f  jz      short loc_180010C2E
0x180010c21  call    cs:__imp_free
0x180010c27  mov     qword ptr [rbx], 0
0x180010c2e  mov     rcx, [rbx+8]; Block
0x180010c32  test    rcx, rcx
0x180010c35  jz      short loc_180010C45
0x180010c37  call    cs:__imp_free
0x180010c3d  mov     qword ptr [rbx+8], 0
0x180010c45  mov     rsi, [rsp+28h+arg_8]
0x180010c4a  xor     eax, eax
0x180010c4c  mov     dword ptr [rbx+10h], 0
0x180010c53  mov     rbx, [rsp+28h+arg_0]
0x180010c58  add     rsp, 20h
0x180010c5c  pop     rdi
0x180010c5d  retn
0x180010c5e  mov     ecx, 0C000008Ch; unsigned int
0x180010c63  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180010c68  int     3; Trap to Debugger
0x180010c69  mov     ecx, 0C000008Ch; unsigned int
0x180010c6e  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```

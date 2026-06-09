# UL_DISCONNECT_CONTEXT::DereferenceUlDisconnectContext(void)

- ea: `0x180015ab0`
- end: `0x180015af3`
- name: `?DereferenceUlDisconnectContext@UL_DISCONNECT_CONTEXT@@QEAAXXZ`
- size: `67`
- prototype: `void __fastcall(UL_DISCONNECT_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800129e0`
- `0x180015b00`

## callees

- `0x180015ab0`

## import_xrefs

- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180015ae8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180015ae8`

## pseudocode

```c
void __fastcall UL_DISCONNECT_CONTEXT::DereferenceUlDisconnectContext(UL_DISCONNECT_CONTEXT *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 11, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      *(_QWORD *)this = &UL_DISCONNECT_CONTEXT::`vftable';
      _InterlockedDecrement(&UL_DISCONNECT_CONTEXT::sm_cOutstanding);
      *((_DWORD *)this + 10) = 1935961205;
      ALLOC_CACHE_HANDLER::Free(UL_DISCONNECT_CONTEXT::sm_pachDisconnects, this);
    }
  }
}

```

## disassembly

```asm
0x180015ab0  sub     rsp, 28h
0x180015ab4  or      eax, 0FFFFFFFFh
0x180015ab7  lock xadd [rcx+2Ch], eax
0x180015abc  cmp     eax, 1
0x180015abf  jnz     short loc_180015AEE
0x180015ac1  test    rcx, rcx
0x180015ac4  jz      short loc_180015AEE
0x180015ac6  lea     rax, ??_7UL_DISCONNECT_CONTEXT@@6B@; const UL_DISCONNECT_CONTEXT::`vftable'
0x180015acd  mov     rdx, rcx
0x180015ad0  mov     [rcx], rax
0x180015ad3  lock dec cs:?sm_cOutstanding@UL_DISCONNECT_CONTEXT@@0JA; long UL_DISCONNECT_CONTEXT::sm_cOutstanding
0x180015ada  mov     dword ptr [rcx+28h], 73646C75h
0x180015ae1  mov     rcx, cs:?sm_pachDisconnects@UL_DISCONNECT_CONTEXT@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_DISCONNECT_CONTEXT::sm_pachDisconnects
0x180015ae8  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180015aee  add     rsp, 28h
0x180015af2  retn
```

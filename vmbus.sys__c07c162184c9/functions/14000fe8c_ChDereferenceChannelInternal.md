# ChDereferenceChannelInternal

- ea: `0x14000fe8c`
- end: `0x14000ff2c`
- name: `ChDereferenceChannelInternal`
- size: `160`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003d5c`
- `0x1400049d0`
- `0x140005d50`
- `0x140005e6c`
- `0x140005fc8`
- `0x140007330`
- `0x14000f90c`
- `0x1400104c8`
- `0x140010ca0`
- `0x140010f54`
- `0x1400112f8`
- `0x140011418`
- `0x140011920`
- `0x140011a2c`
- `0x14002df08`

## callees

- `0x14000fe8c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000ff1a`
- `ntoskrnl!KeSetEvent` at `0x14000ff1a`

## pseudocode

```c
int __fastcall ChDereferenceChannelInternal(__int64 a1, int a2, __int16 a3)
{
  __int64 v3; // rax
  signed __int64 v4; // rax
  bool v5; // cc
  signed __int64 v6; // rax
  unsigned __int64 *v7; // rdx
  signed __int64 v8; // rcx

  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 1280), 1u) & 0x1F;
  *(_BYTE *)(a1 + 8 * v3 + 1284) = 0;
  *(_WORD *)(a1 + 8 * v3 + 1286) = a3;
  *(_DWORD *)(a1 + 8 * v3 + 1288) = a2;
  v4 = _InterlockedExchangeAdd64((volatile signed __int64 *)(a1 + 240), 0xFFFFFFFFFFFFFFFFuLL);
  v5 = v4 <= 1;
  v6 = v4 - 1;
  if ( v5 )
  {
    if ( v6 )
      __fastfail(0xEu);
    v7 = (unsigned __int64 *)(a1 + 224);
    _m_prefetchw(&ChLocalOfferRemoveWorkQueue);
    v6 = ChLocalOfferRemoveWorkQueue;
    do
    {
      *v7 = v6 & 0xFFFFFFFFFFFFFFFEuLL;
      v8 = v6;
      v6 = _InterlockedCompareExchange64(&ChLocalOfferRemoveWorkQueue, (signed __int64)v7, v6);
    }
    while ( v6 != v8 );
    if ( !v6 )
      LODWORD(v6) = KeSetEvent(&ChLocalOfferRemoveThreadWake, 0, 0);
  }
  return v6;
}

```

## disassembly

```asm
0x14000fe8c  sub     rsp, 28h
0x14000fe90  mov     eax, 1
0x14000fe95  lock xadd [rcx+500h], eax
0x14000fe9d  and     eax, 1Fh
0x14000fea0  mov     byte ptr [rcx+rax*8+504h], 0
0x14000fea8  mov     [rcx+rax*8+506h], r8w
0x14000feb1  mov     [rcx+rax*8+508h], edx
0x14000feb8  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000febc  lock xadd [rcx+0F0h], rax
0x14000fec5  sub     rax, 1
0x14000fec9  jg      short loc_14000FF26
0x14000fecb  test    rax, rax
0x14000fece  jz      short loc_14000FED9
0x14000fed0  mov     ecx, 0Eh
0x14000fed5  int     29h; Win8: RtlFailFast(ecx)
0x14000fed7  jmp     short loc_14000FF26
0x14000fed9  lea     rdx, [rcx+0E0h]
0x14000fee0  prefetchw byte ptr cs:ChLocalOfferRemoveWorkQueue
0x14000fee7  mov     rax, cs:ChLocalOfferRemoveWorkQueue
0x14000feee  mov     rcx, rax
0x14000fef1  and     rcx, 0FFFFFFFFFFFFFFFEh
0x14000fef5  mov     [rdx], rcx
0x14000fef8  mov     rcx, rax
0x14000fefb  lock cmpxchg cs:ChLocalOfferRemoveWorkQueue, rdx
0x14000ff04  cmp     rax, rcx
0x14000ff07  jnz     short loc_14000FEEE
0x14000ff09  test    rax, rax
0x14000ff0c  jnz     short loc_14000FF26
0x14000ff0e  xor     r8d, r8d; Wait
0x14000ff11  lea     rcx, ChLocalOfferRemoveThreadWake; Event
0x14000ff18  xor     edx, edx; Increment
0x14000ff1a  call    cs:__imp_KeSetEvent
0x14000ff21  nop     dword ptr [rax+rax+00h]
0x14000ff26  add     rsp, 28h
0x14000ff2a  retn
```

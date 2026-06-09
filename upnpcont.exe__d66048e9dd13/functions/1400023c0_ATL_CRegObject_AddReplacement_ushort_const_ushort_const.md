# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1400023c0`
- end: `0x14000241c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400021e4`
- `0x1400023c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400023fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400023fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400023e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400023e0`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = ATL::CExpansionVector::Add((ATL::CRegObject *)((char *)this + 8), a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return v6 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1400023c0  push    rbx
0x1400023c2  push    rbp
0x1400023c3  push    rsi
0x1400023c4  push    rdi
0x1400023c5  sub     rsp, 28h
0x1400023c9  mov     rbx, r8
0x1400023cc  mov     rsi, rdx
0x1400023cf  mov     rbp, rcx
0x1400023d2  test    rdx, rdx
0x1400023d5  jz      short loc_14000240E
0x1400023d7  test    rbx, rbx
0x1400023da  jz      short loc_14000240E
0x1400023dc  add     rcx, 20h ; ' '; lpCriticalSection
0x1400023e0  call    cs:__imp_EnterCriticalSection
0x1400023e6  lea     rcx, [rbp+8]; this
0x1400023ea  mov     r8, rbx; unsigned __int16 *
0x1400023ed  mov     rdx, rsi; unsigned __int16 *
0x1400023f0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1400023f5  lea     rcx, [rbp+20h]; lpCriticalSection
0x1400023f9  mov     ebx, eax
0x1400023fb  call    cs:__imp_LeaveCriticalSection
0x140002401  neg     ebx
0x140002403  sbb     eax, eax
0x140002405  not     eax
0x140002407  and     eax, 8007000Eh
0x14000240c  jmp     short loc_140002413
0x14000240e  mov     eax, 80070057h
0x140002413  add     rsp, 28h
0x140002417  pop     rdi
0x140002418  pop     rsi
0x140002419  pop     rbp
0x14000241a  pop     rbx
0x14000241b  retn
```

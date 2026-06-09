# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800085c0`
- end: `0x18000861c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008358`
- `0x1800085c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800085fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800085e0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800085e0`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::AddReplacement(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  BOOL v6; // ebx

  if ( !a2 || !a3 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v6 = ATL::CExpansionVector::Add((void **)this + 1, a2, a3);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return !v6 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x1800085c0  push    rbx
0x1800085c2  push    rbp
0x1800085c3  push    rsi
0x1800085c4  push    rdi
0x1800085c5  sub     rsp, 28h
0x1800085c9  mov     rbx, r8
0x1800085cc  mov     rsi, rdx
0x1800085cf  mov     rbp, rcx
0x1800085d2  test    rdx, rdx
0x1800085d5  jz      short loc_18000860E
0x1800085d7  test    rbx, rbx
0x1800085da  jz      short loc_18000860E
0x1800085dc  add     rcx, 20h ; ' '; lpCriticalSection
0x1800085e0  call    cs:__imp_EnterCriticalSection
0x1800085e6  lea     rcx, [rbp+8]; this
0x1800085ea  mov     r8, rbx; unsigned __int16 *
0x1800085ed  mov     rdx, rsi; unsigned __int16 *
0x1800085f0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800085f5  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800085f9  mov     ebx, eax
0x1800085fb  call    cs:__imp_LeaveCriticalSection
0x180008601  neg     ebx
0x180008603  sbb     eax, eax
0x180008605  not     eax
0x180008607  and     eax, 8007000Eh
0x18000860c  jmp     short loc_180008613
0x18000860e  mov     eax, 80070057h
0x180008613  add     rsp, 28h
0x180008617  pop     rdi
0x180008618  pop     rsi
0x180008619  pop     rbp
0x18000861a  pop     rbx
0x18000861b  retn
```

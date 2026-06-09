# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800026b0`
- end: `0x180002716`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000246c`
- `0x1800026b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800026d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800026f4`

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
0x1800026b0  push    rbx
0x1800026b2  push    rbp
0x1800026b3  push    rsi
0x1800026b4  push    rdi
0x1800026b5  sub     rsp, 28h
0x1800026b9  mov     rbx, r8
0x1800026bc  mov     rsi, rdx
0x1800026bf  mov     rbp, rcx
0x1800026c2  test    rdx, rdx
0x1800026c5  jz      short loc_180002708
0x1800026c7  test    rbx, rbx
0x1800026ca  jz      short loc_180002708
0x1800026cc  add     rcx, 20h ; ' '; lpCriticalSection
0x1800026d0  call    cs:__imp_EnterCriticalSection
0x1800026d6  mov     [rsp+48h+arg_8], 0
0x1800026df  lea     rcx, [rbp+8]; this
0x1800026e3  mov     r8, rbx; unsigned __int16 *
0x1800026e6  mov     rdx, rsi; unsigned __int16 *
0x1800026e9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800026ee  mov     ebx, eax
0x1800026f0  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800026f4  call    cs:__imp_LeaveCriticalSection
0x1800026fa  nop
0x1800026fb  neg     ebx
0x1800026fd  sbb     eax, eax
0x1800026ff  not     eax
0x180002701  and     eax, 8007000Eh
0x180002706  jmp     short loc_18000270D
0x180002708  mov     eax, 80070057h
0x18000270d  add     rsp, 28h
0x180002711  pop     rdi
0x180002712  pop     rsi
0x180002713  pop     rbp
0x180002714  pop     rbx
0x180002715  retn
```

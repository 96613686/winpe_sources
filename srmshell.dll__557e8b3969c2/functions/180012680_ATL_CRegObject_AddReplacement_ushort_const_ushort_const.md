# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180012680`
- end: `0x1800126e6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800122cc`
- `0x180012680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800126c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800126c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800126a0`

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
0x180012680  push    rbx
0x180012682  push    rbp
0x180012683  push    rsi
0x180012684  push    rdi
0x180012685  sub     rsp, 28h
0x180012689  mov     rbx, r8
0x18001268c  mov     rsi, rdx
0x18001268f  mov     rbp, rcx
0x180012692  test    rdx, rdx
0x180012695  jz      short loc_1800126D8
0x180012697  test    rbx, rbx
0x18001269a  jz      short loc_1800126D8
0x18001269c  add     rcx, 20h ; ' '; lpCriticalSection
0x1800126a0  call    cs:__imp_EnterCriticalSection
0x1800126a6  mov     [rsp+48h+arg_8], 0
0x1800126af  lea     rcx, [rbp+8]; this
0x1800126b3  mov     r8, rbx; unsigned __int16 *
0x1800126b6  mov     rdx, rsi; unsigned __int16 *
0x1800126b9  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800126be  mov     ebx, eax
0x1800126c0  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800126c4  call    cs:__imp_LeaveCriticalSection
0x1800126ca  nop
0x1800126cb  neg     ebx
0x1800126cd  sbb     eax, eax
0x1800126cf  not     eax
0x1800126d1  and     eax, 8007000Eh
0x1800126d6  jmp     short loc_1800126DD
0x1800126d8  mov     eax, 80070057h
0x1800126dd  add     rsp, 28h
0x1800126e1  pop     rdi
0x1800126e2  pop     rsi
0x1800126e3  pop     rbp
0x1800126e4  pop     rbx
0x1800126e5  retn
```

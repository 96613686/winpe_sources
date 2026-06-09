# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x140002850`
- end: `0x1400028b6`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `102`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000259c`
- `0x140002850`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140002870`
- `KERNEL32!EnterCriticalSection` at `0x140002870`
- `KERNEL32!LeaveCriticalSection` at `0x140002894`
- `KERNEL32!LeaveCriticalSection` at `0x140002894`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140002850  push    rbx
0x140002852  push    rbp
0x140002853  push    rsi
0x140002854  push    rdi
0x140002855  sub     rsp, 28h
0x140002859  mov     rbx, r8
0x14000285c  mov     rsi, rdx
0x14000285f  mov     rbp, rcx
0x140002862  test    rdx, rdx
0x140002865  jz      short loc_1400028A8
0x140002867  test    rbx, rbx
0x14000286a  jz      short loc_1400028A8
0x14000286c  add     rcx, 20h ; ' '; lpCriticalSection
0x140002870  call    cs:__imp_EnterCriticalSection
0x140002876  mov     [rsp+48h+arg_8], 0
0x14000287f  lea     rcx, [rbp+8]; this
0x140002883  mov     r8, rbx; unsigned __int16 *
0x140002886  mov     rdx, rsi; unsigned __int16 *
0x140002889  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x14000288e  mov     ebx, eax
0x140002890  lea     rcx, [rbp+20h]; lpCriticalSection
0x140002894  call    cs:__imp_LeaveCriticalSection
0x14000289a  nop
0x14000289b  neg     ebx
0x14000289d  sbb     eax, eax
0x14000289f  not     eax
0x1400028a1  and     eax, 8007000Eh
0x1400028a6  jmp     short loc_1400028AD
0x1400028a8  mov     eax, 80070057h
0x1400028ad  add     rsp, 28h
0x1400028b1  pop     rdi
0x1400028b2  pop     rsi
0x1400028b3  pop     rbp
0x1400028b4  pop     rbx
0x1400028b5  retn
```

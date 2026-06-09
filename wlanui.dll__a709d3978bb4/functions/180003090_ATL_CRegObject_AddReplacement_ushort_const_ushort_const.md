# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003090`
- end: `0x1800030ec`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002dc8`
- `0x180003090`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800030b0`
- `KERNEL32!EnterCriticalSection` at `0x1800030b0`
- `KERNEL32!LeaveCriticalSection` at `0x1800030cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800030cb`

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
0x180003090  push    rbx
0x180003092  push    rbp
0x180003093  push    rsi
0x180003094  push    rdi
0x180003095  sub     rsp, 28h
0x180003099  mov     rbx, r8
0x18000309c  mov     rsi, rdx
0x18000309f  mov     rbp, rcx
0x1800030a2  test    rdx, rdx
0x1800030a5  jz      short loc_1800030DE
0x1800030a7  test    rbx, rbx
0x1800030aa  jz      short loc_1800030DE
0x1800030ac  add     rcx, 20h ; ' '; lpCriticalSection
0x1800030b0  call    cs:__imp_EnterCriticalSection
0x1800030b6  lea     rcx, [rbp+8]; this
0x1800030ba  mov     r8, rbx; unsigned __int16 *
0x1800030bd  mov     rdx, rsi; unsigned __int16 *
0x1800030c0  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x1800030c5  lea     rcx, [rbp+20h]; lpCriticalSection
0x1800030c9  mov     ebx, eax
0x1800030cb  call    cs:__imp_LeaveCriticalSection
0x1800030d1  neg     ebx
0x1800030d3  sbb     eax, eax
0x1800030d5  not     eax
0x1800030d7  and     eax, 8007000Eh
0x1800030dc  jmp     short loc_1800030E3
0x1800030de  mov     eax, 80070057h
0x1800030e3  add     rsp, 28h
0x1800030e7  pop     rdi
0x1800030e8  pop     rsi
0x1800030e9  pop     rbp
0x1800030ea  pop     rbx
0x1800030eb  retn
```

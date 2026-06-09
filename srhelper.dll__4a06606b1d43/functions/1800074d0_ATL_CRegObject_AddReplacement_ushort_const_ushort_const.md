# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x1800074d0`
- end: `0x18000752c`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `92`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800072a8`
- `0x1800074d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000750b`
- `KERNEL32!LeaveCriticalSection` at `0x18000750b`
- `KERNEL32!EnterCriticalSection` at `0x1800074f0`
- `KERNEL32!EnterCriticalSection` at `0x1800074f0`

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
0x1800074d0  push    rbx
0x1800074d2  push    rbp
0x1800074d3  push    rsi
0x1800074d4  push    rdi
0x1800074d5  sub     rsp, 28h
0x1800074d9  mov     rbx, r8
0x1800074dc  mov     rsi, rdx
0x1800074df  mov     rbp, rcx
0x1800074e2  test    rdx, rdx
0x1800074e5  jz      short loc_18000751E
0x1800074e7  test    rbx, rbx
0x1800074ea  jz      short loc_18000751E
0x1800074ec  add     rcx, 20h ; ' '; lpCriticalSection
0x1800074f0  call    cs:__imp_EnterCriticalSection
0x1800074f6  lea     rcx, [rbp+8]; this
0x1800074fa  mov     r8, rbx; unsigned __int16 *
0x1800074fd  mov     rdx, rsi; unsigned __int16 *
0x180007500  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180007505  lea     rcx, [rbp+20h]; lpCriticalSection
0x180007509  mov     ebx, eax
0x18000750b  call    cs:__imp_LeaveCriticalSection
0x180007511  neg     ebx
0x180007513  sbb     eax, eax
0x180007515  not     eax
0x180007517  and     eax, 8007000Eh
0x18000751c  jmp     short loc_180007523
0x18000751e  mov     eax, 80070057h
0x180007523  add     rsp, 28h
0x180007527  pop     rdi
0x180007528  pop     rsi
0x180007529  pop     rbp
0x18000752a  pop     rbx
0x18000752b  retn
```

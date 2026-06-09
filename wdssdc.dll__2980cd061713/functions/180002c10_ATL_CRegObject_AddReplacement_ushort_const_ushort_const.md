# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180002c10`
- end: `0x180002c90`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `128`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800050c8`

## callees

- `0x18000291c`
- `0x180002c10`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180002c5c`
- `KERNEL32!LeaveCriticalSection` at `0x180002c5c`
- `KERNEL32!EnterCriticalSection` at `0x180002c3b`
- `KERNEL32!EnterCriticalSection` at `0x180002c3b`

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
0x180002c10  mov     [rsp+arg_0], rbx
0x180002c15  mov     [rsp+arg_8], rbp
0x180002c1a  mov     [rsp+arg_10], rsi
0x180002c1f  push    rdi
0x180002c20  sub     rsp, 20h
0x180002c24  mov     rbx, r8
0x180002c27  mov     rsi, rdx
0x180002c2a  mov     rbp, rcx
0x180002c2d  test    rdx, rdx
0x180002c30  jz      short loc_180002C75
0x180002c32  test    rbx, rbx
0x180002c35  jz      short loc_180002C75
0x180002c37  add     rcx, 20h ; ' '; lpCriticalSection
0x180002c3b  call    cs:__imp_EnterCriticalSection
0x180002c42  nop     dword ptr [rax+rax+00h]
0x180002c47  lea     rcx, [rbp+8]; this
0x180002c4b  mov     r8, rbx; unsigned __int16 *
0x180002c4e  mov     rdx, rsi; unsigned __int16 *
0x180002c51  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180002c56  lea     rcx, [rbp+20h]; lpCriticalSection
0x180002c5a  mov     ebx, eax
0x180002c5c  call    cs:__imp_LeaveCriticalSection
0x180002c63  nop     dword ptr [rax+rax+00h]
0x180002c68  neg     ebx
0x180002c6a  sbb     eax, eax
0x180002c6c  not     eax
0x180002c6e  and     eax, 8007000Eh
0x180002c73  jmp     short loc_180002C7A
0x180002c75  mov     eax, 80070057h
0x180002c7a  mov     rbx, [rsp+28h+arg_0]
0x180002c7f  mov     rbp, [rsp+28h+arg_8]
0x180002c84  mov     rsi, [rsp+28h+arg_10]
0x180002c89  add     rsp, 20h
0x180002c8d  pop     rdi
0x180002c8e  retn
```

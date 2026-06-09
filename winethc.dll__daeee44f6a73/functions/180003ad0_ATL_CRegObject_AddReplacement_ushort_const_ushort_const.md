# ATL::CRegObject::AddReplacement(ushort const *,ushort const *)

- ea: `0x180003ad0`
- end: `0x180003b39`
- name: `?AddReplacement@CRegObject@ATL@@UEAAJPEBG0@Z`
- size: `105`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ce24`

## callees

- `0x180003814`
- `0x180003ad0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003b11`
- `KERNEL32!LeaveCriticalSection` at `0x180003b11`
- `KERNEL32!EnterCriticalSection` at `0x180003af0`
- `KERNEL32!EnterCriticalSection` at `0x180003af0`

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
0x180003ad0  push    rbx
0x180003ad2  push    rbp
0x180003ad3  push    rsi
0x180003ad4  push    rdi
0x180003ad5  sub     rsp, 28h
0x180003ad9  mov     rbx, r8
0x180003adc  mov     rsi, rdx
0x180003adf  mov     rbp, rcx
0x180003ae2  test    rdx, rdx
0x180003ae5  jz      short loc_180003B2A
0x180003ae7  test    rbx, rbx
0x180003aea  jz      short loc_180003B2A
0x180003aec  add     rcx, 20h ; ' '; lpCriticalSection
0x180003af0  call    cs:__imp_EnterCriticalSection
0x180003af7  nop     dword ptr [rax+rax+00h]
0x180003afc  lea     rcx, [rbp+8]; this
0x180003b00  mov     r8, rbx; unsigned __int16 *
0x180003b03  mov     rdx, rsi; unsigned __int16 *
0x180003b06  call    ?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z; ATL::CExpansionVector::Add(ushort const *,ushort const *)
0x180003b0b  lea     rcx, [rbp+20h]; lpCriticalSection
0x180003b0f  mov     ebx, eax
0x180003b11  call    cs:__imp_LeaveCriticalSection
0x180003b18  nop     dword ptr [rax+rax+00h]
0x180003b1d  neg     ebx
0x180003b1f  sbb     eax, eax
0x180003b21  not     eax
0x180003b23  and     eax, 8007000Eh
0x180003b28  jmp     short loc_180003B2F
0x180003b2a  mov     eax, 80070057h
0x180003b2f  add     rsp, 28h
0x180003b33  pop     rdi
0x180003b34  pop     rsi
0x180003b35  pop     rbp
0x180003b36  pop     rbx
0x180003b37  retn
```

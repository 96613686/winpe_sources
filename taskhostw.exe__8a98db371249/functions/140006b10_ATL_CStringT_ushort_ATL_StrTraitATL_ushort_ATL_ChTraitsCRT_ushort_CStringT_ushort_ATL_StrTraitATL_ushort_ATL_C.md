# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x140006b10`
- end: `0x140006b40`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x14000ab20`
- `0x14000ab40`
- `0x14000ab60`
- `0x14000ab80`
- `0x14000ac10`
- `0x14000ac30`
- `0x14000ac50`
- `0x14000ac70`

## callees

- `0x140006b10`
- `0x14000c010`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  volatile signed __int32 *v1; // rdx
  signed __int32 v2; // eax
  bool v3; // cc
  __int64 result; // rax

  v1 = (volatile signed __int32 *)(*a1 - 24LL);
  v2 = _InterlockedExchangeAdd(v1 + 4, 0xFFFFFFFF);
  v3 = v2 <= 1;
  result = (unsigned int)(v2 - 1);
  if ( v3 )
    return (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  return result;
}

```

## disassembly

```asm
0x140006b10  sub     rsp, 28h
0x140006b14  mov     rdx, [rcx]
0x140006b17  mov     eax, 0FFFFFFFFh
0x140006b1c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140006b20  lock xadd [rdx+10h], eax
0x140006b25  sub     eax, 1
0x140006b28  jle     short loc_140006B2F
0x140006b2a  add     rsp, 28h
0x140006b2e  retn
0x140006b2f  mov     rcx, [rdx]
0x140006b32  mov     rax, [rcx]
0x140006b35  mov     rax, [rax+8]
0x140006b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b3e  jmp     short loc_140006B2A
```

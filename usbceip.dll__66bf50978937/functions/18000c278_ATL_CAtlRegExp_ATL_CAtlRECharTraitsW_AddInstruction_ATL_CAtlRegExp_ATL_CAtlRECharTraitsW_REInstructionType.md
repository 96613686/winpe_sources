# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)

- ea: `0x18000c278`
- end: `0x18000c2d2`
- name: `?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z`
- size: `90`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c2d8`
- `0x18000cf44`
- `0x18000d09c`
- `0x18000d288`
- `0x18000d424`
- `0x18000d564`
- `0x18000d974`
- `0x18000da1c`
- `0x18000dc64`

## callees

- `0x18000c24c`
- `0x18000c278`
- `0x18000e028`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(__int64 a1, int a2)
{
  if ( (unsigned __int8)ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(
                          a1 + 8,
                          *(_QWORD *)(a1 + 16) + 1LL) )
  {
    *(_DWORD *)ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](
                 (_QWORD *)(a1 + 8),
                 *(_QWORD *)(a1 + 16) - 1LL) = a2;
    return (unsigned int)(*(_DWORD *)(a1 + 16) - 1);
  }
  else
  {
    *(_DWORD *)a1 = 1;
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18000c278  mov     [rsp+arg_0], rbx
0x18000c27d  mov     [rsp+arg_8], rsi
0x18000c282  push    rdi
0x18000c283  sub     rsp, 20h
0x18000c287  mov     esi, edx
0x18000c289  mov     rbx, rcx
0x18000c28c  mov     rdx, [rcx+10h]
0x18000c290  add     rcx, 8
0x18000c294  inc     rdx
0x18000c297  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x18000c29c  test    al, al
0x18000c29e  jnz     short loc_18000C2AB
0x18000c2a0  mov     dword ptr [rbx], 1
0x18000c2a6  or      eax, 0FFFFFFFFh
0x18000c2a9  jmp     short loc_18000C2C2
0x18000c2ab  mov     rdx, [rbx+10h]
0x18000c2af  lea     rcx, [rbx+8]
0x18000c2b3  dec     rdx
0x18000c2b6  call    ??A?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAAAEAUINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::operator[](unsigned __int64)
0x18000c2bb  mov     [rax], esi
0x18000c2bd  mov     eax, [rbx+10h]
0x18000c2c0  dec     eax
0x18000c2c2  mov     rbx, [rsp+28h+arg_0]
0x18000c2c7  mov     rsi, [rsp+28h+arg_8]
0x18000c2cc  add     rsp, 20h
0x18000c2d0  pop     rdi
0x18000c2d1  retn
```

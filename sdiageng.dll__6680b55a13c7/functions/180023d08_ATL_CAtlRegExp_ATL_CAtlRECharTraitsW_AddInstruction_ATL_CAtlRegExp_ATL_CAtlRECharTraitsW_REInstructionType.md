# ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::REInstructionType)

- ea: `0x180023d08`
- end: `0x180023d72`
- name: `?AddInstruction@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@IEAAHW4REInstructionType@12@@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x180024cec`
- `0x180024e2c`
- `0x180025080`
- `0x180025270`
- `0x1800253e0`
- `0x180025904`
- `0x180025c50`

## callees

- `0x180023d08`
- `0x180023e08`
- `0x1800261dc`

## pseudocode

```c
__int64 __fastcall ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::AddInstruction(__int64 a1, int a2)
{
  __int64 v5; // rax

  if ( (unsigned __int8)ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(
                          a1 + 8,
                          *(_QWORD *)(a1 + 16) + 1LL) )
  {
    v5 = *(_QWORD *)(a1 + 16);
    if ( !v5 )
      ATL::AtlThrowImpl(-2147024809);
    *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16 * (v5 - 1)) = a2;
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
0x180023d08  mov     [rsp+arg_0], rbx
0x180023d0d  mov     [rsp+arg_8], rsi
0x180023d12  push    rdi
0x180023d13  sub     rsp, 20h
0x180023d17  mov     esi, edx
0x180023d19  mov     rbx, rcx
0x180023d1c  mov     rdx, [rcx+10h]
0x180023d20  add     rcx, 8
0x180023d24  inc     rdx
0x180023d27  call    ?SetCount@?$CAtlArray@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@V?$CElementTraits@UINSTRUCTION@?$CAtlRegExp@VCAtlRECharTraitsW@ATL@@@ATL@@@3@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION,ATL::CElementTraits<ATL::CAtlRegExp<ATL::CAtlRECharTraitsW>::INSTRUCTION>>::SetCount(unsigned __int64,int)
0x180023d2c  test    al, al
0x180023d2e  jnz     short loc_180023D3B
0x180023d30  mov     dword ptr [rbx], 1
0x180023d36  or      eax, 0FFFFFFFFh
0x180023d39  jmp     short loc_180023D57
0x180023d3b  mov     rax, [rbx+10h]
0x180023d3f  lea     rcx, [rax-1]
0x180023d43  cmp     rcx, rax
0x180023d46  jnb     short loc_180023D67
0x180023d48  mov     rax, [rbx+8]
0x180023d4c  add     rcx, rcx
0x180023d4f  mov     [rax+rcx*8], esi
0x180023d52  mov     eax, [rbx+10h]
0x180023d55  dec     eax
0x180023d57  mov     rbx, [rsp+28h+arg_0]
0x180023d5c  mov     rsi, [rsp+28h+arg_8]
0x180023d61  add     rsp, 20h
0x180023d65  pop     rdi
0x180023d66  retn
0x180023d67  mov     ecx, 80070057h; int
0x180023d6c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```

# std::_Uninit_move<_DUI_EAPDATA_MAPPING *,_DUI_EAPDATA_MAPPING *,std::allocator<_DUI_EAPDATA_MAPPING>,_DUI_EAPDATA_MAPPING>(_DUI_EAPDATA_MAPPING *,_DUI_EAPDATA_MAPPING *,_DUI_EAPDATA_MAPPING *,std::_Wrap_alloc<std::allocator<_DUI_EAPDATA_MAPPING>> &,_DUI_EAPDATA_MAPPING *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180019ad4`
- end: `0x180019b01`
- name: `??$_Uninit_move@PEAU_DUI_EAPDATA_MAPPING@@PEAU1@V?$allocator@U_DUI_EAPDATA_MAPPING@@@std@@U1@@std@@YAPEAU_DUI_EAPDATA_MAPPING@@PEAU1@00AEAU?$_Wrap_alloc@V?$allocator@U_DUI_EAPDATA_MAPPING@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b050`

## callees

- `0x180019ad4`

## pseudocode

```c
__int64 __fastcall std::_Uninit_move<_DUI_EAPDATA_MAPPING *,_DUI_EAPDATA_MAPPING *,std::allocator<_DUI_EAPDATA_MAPPING>,_DUI_EAPDATA_MAPPING>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  while ( a1 != a2 )
  {
    *(_OWORD *)a3 = *(_OWORD *)a1;
    *(_QWORD *)(a3 + 16) = *(_QWORD *)(a1 + 16);
    a3 += 24;
    a1 += 24;
  }
  return a3;
}

```

## disassembly

```asm
0x180019ad4  sub     rsp, 28h
0x180019ad8  jmp     short loc_180019AF4
0x180019ada  movups  xmm0, xmmword ptr [rcx]
0x180019add  movups  xmmword ptr [r8], xmm0
0x180019ae1  movsd   xmm1, qword ptr [rcx+10h]
0x180019ae6  movsd   qword ptr [r8+10h], xmm1
0x180019aec  add     r8, 18h
0x180019af0  add     rcx, 18h
0x180019af4  cmp     rcx, rdx
0x180019af7  jnz     short loc_180019ADA
0x180019af9  mov     rax, r8
0x180019afc  add     rsp, 28h
0x180019b00  retn
```

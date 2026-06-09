# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveAll(void)

- ea: `0x180021960`
- end: `0x180021a00`
- name: `?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@QEAAXXZ`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180020de0`

## callees

- `0x180021018`
- `0x1800210a0`
- `0x180021294`
- `0x180021698`
- `0x180021960`
- `0x180023650`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 result; // rax

  ++*(_DWORD *)(a1 + 48);
  if ( *(_QWORD *)a1 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 16); i = (unsigned int)(i + 1) )
    {
      v3 = *(_QWORD *)(*(_QWORD *)a1 + 8 * i);
      while ( v3 )
      {
        v4 = v3;
        v3 = *(_QWORD *)(v3 + 32);
        ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  CDebugFilter::DestroyObject(*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = (unsigned int)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::PickSize(
                         a1,
                         0);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::InitHashTable(
      a1,
      v5,
      0);
  }
  result = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x180021960  push    rdi
0x180021962  sub     rsp, 30h
0x180021966  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18002196f  mov     [rsp+38h+arg_0], rbx
0x180021974  mov     [rsp+38h+arg_8], rsi
0x180021979  mov     rbx, rcx
0x18002197c  inc     dword ptr [rcx+30h]
0x18002197f  cmp     qword ptr [rcx], 0
0x180021983  jz      short loc_1800219B0
0x180021985  xor     edi, edi
0x180021987  cmp     [rcx+10h], edi
0x18002198a  jbe     short loc_1800219B0
0x18002198c  mov     rax, [rbx]
0x18002198f  mov     rsi, [rax+rdi*8]
0x180021993  jmp     short loc_1800219A4
0x180021995  mov     rdx, rsi
0x180021998  mov     rsi, [rsi+20h]
0x18002199c  mov     rcx, rbx
0x18002199f  call    ?FreeNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreeNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *)
0x1800219a4  test    rsi, rsi
0x1800219a7  jnz     short loc_180021995
0x1800219a9  inc     edi
0x1800219ab  cmp     edi, [rbx+10h]
0x1800219ae  jb      short loc_18002198C
0x1800219b0  mov     rcx, [rbx]; Block
0x1800219b3  call    ?DestroyObject@CDebugFilter@@UEAAXXZ; CDebugFilter::DestroyObject(void)
0x1800219b8  mov     qword ptr [rbx], 0
0x1800219bf  mov     qword ptr [rbx+8], 0
0x1800219c7  cmp     dword ptr [rbx+30h], 0
0x1800219cb  jnz     short loc_1800219E4
0x1800219cd  xor     edx, edx
0x1800219cf  mov     rcx, rbx
0x1800219d2  call    ?PickSize@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::PickSize(unsigned __int64)
0x1800219d7  mov     edx, eax
0x1800219d9  xor     r8d, r8d
0x1800219dc  mov     rcx, rbx
0x1800219df  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::InitHashTable(uint,bool)
0x1800219e4  mov     rcx, rbx
0x1800219e7  call    ?FreePlexes@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreePlexes(void)
0x1800219ec  dec     dword ptr [rbx+30h]
0x1800219ef  mov     rbx, [rsp+38h+arg_0]
0x1800219f4  mov     rsi, [rsp+38h+arg_8]
0x1800219f9  add     rsp, 30h
0x1800219fd  pop     rdi
0x1800219fe  retn
```

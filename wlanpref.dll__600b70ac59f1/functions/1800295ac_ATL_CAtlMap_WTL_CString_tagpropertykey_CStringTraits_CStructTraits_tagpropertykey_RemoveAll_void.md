# ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::RemoveAll(void)

- ea: `0x1800295ac`
- end: `0x180029641`
- name: `?RemoveAll@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAAXXZ`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180028a54`
- `0x180028a60`

## callees

- `0x1800012f4`
- `0x180012804`
- `0x180012a70`
- `0x180012e80`
- `0x180028b4c`
- `0x1800295ac`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  unsigned int v5; // eax
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
        ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::FreeNode(a1, v4);
      }
    }
  }
  operator delete[](*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(a1, v5, 0);
  }
  result = ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x1800295ac  mov     [rsp+arg_0], rbx
0x1800295b1  mov     [rsp+arg_8], rsi
0x1800295b6  push    rdi
0x1800295b7  sub     rsp, 20h
0x1800295bb  mov     rbx, rcx
0x1800295be  inc     dword ptr [rcx+30h]
0x1800295c1  cmp     qword ptr [rcx], 0
0x1800295c5  jz      short loc_1800295F2
0x1800295c7  xor     edi, edi
0x1800295c9  cmp     [rcx+10h], edi
0x1800295cc  jbe     short loc_1800295F2
0x1800295ce  mov     rax, [rbx]
0x1800295d1  mov     rsi, [rax+rdi*8]
0x1800295d5  jmp     short loc_1800295E6
0x1800295d7  mov     rdx, rsi
0x1800295da  mov     rsi, [rsi+20h]
0x1800295de  mov     rcx, rbx
0x1800295e1  call    ?FreeNode@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::FreeNode(ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::CNode *)
0x1800295e6  test    rsi, rsi
0x1800295e9  jnz     short loc_1800295D7
0x1800295eb  inc     edi
0x1800295ed  cmp     edi, [rbx+10h]
0x1800295f0  jb      short loc_1800295CE
0x1800295f2  mov     rcx, [rbx]; Block
0x1800295f5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800295fa  mov     qword ptr [rbx], 0
0x180029601  mov     qword ptr [rbx+8], 0
0x180029609  cmp     dword ptr [rbx+30h], 0
0x18002960d  jnz     short loc_180029626
0x18002960f  xor     edx, edx
0x180029611  mov     rcx, rbx
0x180029614  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x180029619  mov     edx, eax
0x18002961b  xor     r8d, r8d
0x18002961e  mov     rcx, rbx
0x180029621  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x180029626  mov     rcx, rbx
0x180029629  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x18002962e  dec     dword ptr [rbx+30h]
0x180029631  mov     rbx, [rsp+28h+arg_0]
0x180029636  mov     rsi, [rsp+28h+arg_8]
0x18002963b  add     rsp, 20h
0x18002963f  pop     rdi
0x180029640  retn
```

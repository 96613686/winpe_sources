# ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::RemoveAll(void)

- ea: `0x180028064`
- end: `0x1800280f9`
- name: `?RemoveAll@?$CAtlMap@U_tagpropertykey@@VCString@WTL@@V?$CStructTraits@U_tagpropertykey@@@@VCStringTraits@@@ATL@@QEAAXXZ`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002754c`
- `0x180028a60`

## callees

- `0x1800012f4`
- `0x180012804`
- `0x180012a70`
- `0x180012e80`
- `0x180027790`
- `0x180028064`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::RemoveAll(
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
        ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::FreeNode(a1, v4);
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
0x180028064  mov     [rsp+arg_0], rbx
0x180028069  mov     [rsp+arg_8], rsi
0x18002806e  push    rdi
0x18002806f  sub     rsp, 20h
0x180028073  mov     rbx, rcx
0x180028076  inc     dword ptr [rcx+30h]
0x180028079  cmp     qword ptr [rcx], 0
0x18002807d  jz      short loc_1800280AA
0x18002807f  xor     edi, edi
0x180028081  cmp     [rcx+10h], edi
0x180028084  jbe     short loc_1800280AA
0x180028086  mov     rax, [rbx]
0x180028089  mov     rsi, [rax+rdi*8]
0x18002808d  jmp     short loc_18002809E
0x18002808f  mov     rdx, rsi
0x180028092  mov     rsi, [rsi+20h]
0x180028096  mov     rcx, rbx
0x180028099  call    ?FreeNode@?$CAtlMap@U_tagpropertykey@@VCString@WTL@@V?$CStructTraits@U_tagpropertykey@@@@VCStringTraits@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::FreeNode(ATL::CAtlMap<_tagpropertykey,WTL::CString,CStructTraits<_tagpropertykey>,CStringTraits>::CNode *)
0x18002809e  test    rsi, rsi
0x1800280a1  jnz     short loc_18002808F
0x1800280a3  inc     edi
0x1800280a5  cmp     edi, [rbx+10h]
0x1800280a8  jb      short loc_180028086
0x1800280aa  mov     rcx, [rbx]; Block
0x1800280ad  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800280b2  mov     qword ptr [rbx], 0
0x1800280b9  mov     qword ptr [rbx+8], 0
0x1800280c1  cmp     dword ptr [rbx+30h], 0
0x1800280c5  jnz     short loc_1800280DE
0x1800280c7  xor     edx, edx
0x1800280c9  mov     rcx, rbx
0x1800280cc  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x1800280d1  mov     edx, eax
0x1800280d3  xor     r8d, r8d
0x1800280d6  mov     rcx, rbx
0x1800280d9  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x1800280de  mov     rcx, rbx
0x1800280e1  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x1800280e6  dec     dword ptr [rbx+30h]
0x1800280e9  mov     rbx, [rsp+28h+arg_0]
0x1800280ee  mov     rsi, [rsp+28h+arg_8]
0x1800280f3  add     rsp, 20h
0x1800280f7  pop     rdi
0x1800280f8  retn
```

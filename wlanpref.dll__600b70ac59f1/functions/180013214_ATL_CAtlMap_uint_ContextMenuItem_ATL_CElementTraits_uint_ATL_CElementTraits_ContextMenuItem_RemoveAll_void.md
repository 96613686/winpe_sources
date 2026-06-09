# ATL::CAtlMap<uint,ContextMenuItem,ATL::CElementTraits<uint>,ATL::CElementTraits<ContextMenuItem>>::RemoveAll(void)

- ea: `0x180013214`
- end: `0x1800132e5`
- name: `?RemoveAll@?$CAtlMap@IVContextMenuItem@@V?$CElementTraits@I@ATL@@V?$CElementTraits@VContextMenuItem@@@3@@ATL@@QEAAXXZ`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18002f210`

## callees

- `0x1800012f4`
- `0x180012804`
- `0x180012a70`
- `0x180012e80`
- `0x180013088`
- `0x180013214`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CAtlMap<unsigned int,ContextMenuItem,ATL::CElementTraits<unsigned int>,ATL::CElementTraits<ContextMenuItem>>::RemoveAll(
        __int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // eax
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
        v5 = (_QWORD *)(v3 + 40);
        v3 = *(_QWORD *)(v3 + 40);
        *v5 = *(_QWORD *)(a1 + 64);
        *(_QWORD *)(a1 + 64) = v4;
        v6 = --*(_QWORD *)(a1 + 8);
        if ( v6 < *(_QWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 48) )
        {
          v7 = ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::PickSize(
                 a1,
                 v6);
          ATL::CAtlMap<unsigned int,ContextMenuItem,ATL::CElementTraits<unsigned int>,ATL::CElementTraits<ContextMenuItem>>::Rehash(
            a1,
            v7);
        }
        if ( !*(_QWORD *)(a1 + 8) )
          ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(a1);
      }
    }
  }
  operator delete[](*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v8 = ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(a1, v8, 0);
  }
  result = ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x180013214  mov     [rsp+arg_0], rbx
0x180013219  mov     [rsp+arg_8], rsi
0x18001321e  push    rdi
0x18001321f  sub     rsp, 20h
0x180013223  mov     rbx, rcx
0x180013226  inc     dword ptr [rcx+30h]
0x180013229  cmp     qword ptr [rcx], 0
0x18001322d  jz      short loc_180013296
0x18001322f  xor     edi, edi
0x180013231  cmp     [rcx+10h], edi
0x180013234  jbe     short loc_180013296
0x180013236  mov     rax, [rbx]
0x180013239  mov     rsi, [rax+rdi*8]
0x18001323d  jmp     short loc_18001328A
0x18001323f  mov     rdx, rsi
0x180013242  lea     rcx, [rsi+28h]
0x180013246  mov     rsi, [rcx]
0x180013249  mov     rax, [rbx+40h]
0x18001324d  mov     [rcx], rax
0x180013250  mov     [rbx+40h], rdx
0x180013254  dec     qword ptr [rbx+8]
0x180013258  mov     rdx, [rbx+8]
0x18001325c  cmp     rdx, [rbx+28h]
0x180013260  jnb     short loc_18001327A
0x180013262  cmp     dword ptr [rbx+30h], 0
0x180013266  jnz     short loc_18001327A
0x180013268  mov     rcx, rbx
0x18001326b  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x180013270  mov     edx, eax
0x180013272  mov     rcx, rbx
0x180013275  call    ?Rehash@?$CAtlMap@IVContextMenuItem@@V?$CElementTraits@I@ATL@@V?$CElementTraits@VContextMenuItem@@@3@@ATL@@QEAAXI@Z; ATL::CAtlMap<uint,ContextMenuItem,ATL::CElementTraits<uint>,ATL::CElementTraits<ContextMenuItem>>::Rehash(uint)
0x18001327a  cmp     qword ptr [rbx+8], 0
0x18001327f  jnz     short loc_18001328A
0x180013281  mov     rcx, rbx
0x180013284  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x180013289  nop
0x18001328a  test    rsi, rsi
0x18001328d  jnz     short loc_18001323F
0x18001328f  inc     edi
0x180013291  cmp     edi, [rbx+10h]
0x180013294  jb      short loc_180013236
0x180013296  mov     rcx, [rbx]; Block
0x180013299  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18001329e  mov     qword ptr [rbx], 0
0x1800132a5  mov     qword ptr [rbx+8], 0
0x1800132ad  cmp     dword ptr [rbx+30h], 0
0x1800132b1  jnz     short loc_1800132CA
0x1800132b3  xor     edx, edx
0x1800132b5  mov     rcx, rbx
0x1800132b8  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x1800132bd  mov     edx, eax
0x1800132bf  xor     r8d, r8d
0x1800132c2  mov     rcx, rbx
0x1800132c5  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x1800132ca  mov     rcx, rbx
0x1800132cd  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x1800132d2  dec     dword ptr [rbx+30h]
0x1800132d5  mov     rbx, [rsp+28h+arg_0]
0x1800132da  mov     rsi, [rsp+28h+arg_8]
0x1800132df  add     rsp, 20h
0x1800132e3  pop     rdi
0x1800132e4  retn
```

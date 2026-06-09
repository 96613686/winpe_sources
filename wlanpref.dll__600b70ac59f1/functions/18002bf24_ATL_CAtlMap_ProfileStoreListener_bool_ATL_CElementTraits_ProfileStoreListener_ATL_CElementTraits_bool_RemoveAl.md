# ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::RemoveAll(void)

- ea: `0x18002bf24`
- end: `0x18002bfb9`
- name: `?RemoveAll@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@QEAAXXZ`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180029b60`
- `0x180029bf4`

## callees

- `0x1800012f4`
- `0x180012804`
- `0x180012a70`
- `0x180012e80`
- `0x18002a538`
- `0x18002bf24`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 16);
        ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreeNode(
          a1,
          v4);
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
0x18002bf24  mov     [rsp+arg_0], rbx
0x18002bf29  mov     [rsp+arg_8], rsi
0x18002bf2e  push    rdi
0x18002bf2f  sub     rsp, 20h
0x18002bf33  mov     rbx, rcx
0x18002bf36  inc     dword ptr [rcx+30h]
0x18002bf39  cmp     qword ptr [rcx], 0
0x18002bf3d  jz      short loc_18002BF6A
0x18002bf3f  xor     edi, edi
0x18002bf41  cmp     [rcx+10h], edi
0x18002bf44  jbe     short loc_18002BF6A
0x18002bf46  mov     rax, [rbx]
0x18002bf49  mov     rsi, [rax+rdi*8]
0x18002bf4d  jmp     short loc_18002BF5E
0x18002bf4f  mov     rdx, rsi
0x18002bf52  mov     rsi, [rsi+10h]
0x18002bf56  mov     rcx, rbx
0x18002bf59  call    ?FreeNode@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreeNode(ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::CNode *)
0x18002bf5e  test    rsi, rsi
0x18002bf61  jnz     short loc_18002BF4F
0x18002bf63  inc     edi
0x18002bf65  cmp     edi, [rbx+10h]
0x18002bf68  jb      short loc_18002BF46
0x18002bf6a  mov     rcx, [rbx]; Block
0x18002bf6d  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18002bf72  mov     qword ptr [rbx], 0
0x18002bf79  mov     qword ptr [rbx+8], 0
0x18002bf81  cmp     dword ptr [rbx+30h], 0
0x18002bf85  jnz     short loc_18002BF9E
0x18002bf87  xor     edx, edx
0x18002bf89  mov     rcx, rbx
0x18002bf8c  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x18002bf91  mov     edx, eax
0x18002bf93  xor     r8d, r8d
0x18002bf96  mov     rcx, rbx
0x18002bf99  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x18002bf9e  mov     rcx, rbx
0x18002bfa1  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x18002bfa6  dec     dword ptr [rbx+30h]
0x18002bfa9  mov     rbx, [rsp+28h+arg_0]
0x18002bfae  mov     rsi, [rsp+28h+arg_8]
0x18002bfb3  add     rsp, 20h
0x18002bfb7  pop     rdi
0x18002bfb8  retn
```

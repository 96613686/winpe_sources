# ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::RemoveAll(void)

- ea: `0x180029510`
- end: `0x1800295a5`
- name: `?RemoveAll@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAAXXZ`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180028a48`
- `0x180028a60`

## callees

- `0x1800012f4`
- `0x180012804`
- `0x180012a70`
- `0x180012e80`
- `0x180028ae8`
- `0x180029510`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::RemoveAll(
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
        v3 = *(_QWORD *)(v3 + 24);
        ATL::CAtlMap<unsigned int,_tagpropertykey,ATL::CElementTraits<unsigned int>,CStructTraits<_tagpropertykey>>::FreeNode(
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
0x180029510  mov     [rsp+arg_0], rbx
0x180029515  mov     [rsp+arg_8], rsi
0x18002951a  push    rdi
0x18002951b  sub     rsp, 20h
0x18002951f  mov     rbx, rcx
0x180029522  inc     dword ptr [rcx+30h]
0x180029525  cmp     qword ptr [rcx], 0
0x180029529  jz      short loc_180029556
0x18002952b  xor     edi, edi
0x18002952d  cmp     [rcx+10h], edi
0x180029530  jbe     short loc_180029556
0x180029532  mov     rax, [rbx]
0x180029535  mov     rsi, [rax+rdi*8]
0x180029539  jmp     short loc_18002954A
0x18002953b  mov     rdx, rsi
0x18002953e  mov     rsi, [rsi+18h]
0x180029542  mov     rcx, rbx
0x180029545  call    ?FreeNode@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::FreeNode(ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::CNode *)
0x18002954a  test    rsi, rsi
0x18002954d  jnz     short loc_18002953B
0x18002954f  inc     edi
0x180029551  cmp     edi, [rbx+10h]
0x180029554  jb      short loc_180029532
0x180029556  mov     rcx, [rbx]; Block
0x180029559  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18002955e  mov     qword ptr [rbx], 0
0x180029565  mov     qword ptr [rbx+8], 0
0x18002956d  cmp     dword ptr [rbx+30h], 0
0x180029571  jnz     short loc_18002958A
0x180029573  xor     edx, edx
0x180029575  mov     rcx, rbx
0x180029578  call    ?PickSize@?$CAtlMap@IU_tagpropertykey@@V?$CElementTraits@I@ATL@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@AEBAI_K@Z; ATL::CAtlMap<uint,_tagpropertykey,ATL::CElementTraits<uint>,CStructTraits<_tagpropertykey>>::PickSize(unsigned __int64)
0x18002957d  mov     edx, eax
0x18002957f  xor     r8d, r8d
0x180029582  mov     rcx, rbx
0x180029585  call    ?InitHashTable@?$CAtlMap@VCString@WTL@@U_tagpropertykey@@VCStringTraits@@V?$CStructTraits@U_tagpropertykey@@@@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<WTL::CString,_tagpropertykey,CStringTraits,CStructTraits<_tagpropertykey>>::InitHashTable(uint,bool)
0x18002958a  mov     rcx, rbx
0x18002958d  call    ?FreePlexes@?$CAtlMap@PEAVProfileStoreListener@@_NV?$CElementTraits@PEAVProfileStoreListener@@@ATL@@V?$CElementTraits@_N@3@@ATL@@AEAAXXZ; ATL::CAtlMap<ProfileStoreListener *,bool,ATL::CElementTraits<ProfileStoreListener *>,ATL::CElementTraits<bool>>::FreePlexes(void)
0x180029592  dec     dword ptr [rbx+30h]
0x180029595  mov     rbx, [rsp+28h+arg_0]
0x18002959a  mov     rsi, [rsp+28h+arg_8]
0x18002959f  add     rsp, 20h
0x1800295a3  pop     rdi
0x1800295a4  retn
```

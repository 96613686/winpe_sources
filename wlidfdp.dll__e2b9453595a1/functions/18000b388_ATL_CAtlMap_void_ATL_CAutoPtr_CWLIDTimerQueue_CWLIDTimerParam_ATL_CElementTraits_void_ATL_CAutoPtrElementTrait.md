# ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveAll(void)

- ea: `0x18000b388`
- end: `0x18000b41d`
- name: `?RemoveAll@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@QEAAXXZ`
- size: `149`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180011420`

## callees

- `0x180002814`
- `0x18000a8e8`
- `0x18000a964`
- `0x18000aae4`
- `0x18000ae24`
- `0x18000b388`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveAll(
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
        ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreeNode(
          a1,
          v4);
      }
    }
  }
  operator delete(*(void **)a1);
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v5 = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::PickSize(
           a1,
           0);
    ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::InitHashTable(
      a1,
      v5,
      0);
  }
  result = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreePlexes(a1);
  --*(_DWORD *)(a1 + 48);
  return result;
}

```

## disassembly

```asm
0x18000b388  mov     [rsp+arg_0], rbx
0x18000b38d  mov     [rsp+arg_8], rsi
0x18000b392  push    rdi
0x18000b393  sub     rsp, 20h
0x18000b397  mov     rbx, rcx
0x18000b39a  inc     dword ptr [rcx+30h]
0x18000b39d  cmp     qword ptr [rcx], 0
0x18000b3a1  jz      short loc_18000B3CE
0x18000b3a3  xor     edi, edi
0x18000b3a5  cmp     [rcx+10h], edi
0x18000b3a8  jbe     short loc_18000B3CE
0x18000b3aa  mov     rax, [rbx]
0x18000b3ad  mov     rsi, [rax+rdi*8]
0x18000b3b1  jmp     short loc_18000B3C2
0x18000b3b3  mov     rdx, rsi
0x18000b3b6  mov     rsi, [rsi+10h]
0x18000b3ba  mov     rcx, rbx
0x18000b3bd  call    ?FreeNode@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreeNode(ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::CNode *)
0x18000b3c2  test    rsi, rsi
0x18000b3c5  jnz     short loc_18000B3B3
0x18000b3c7  inc     edi
0x18000b3c9  cmp     edi, [rbx+10h]
0x18000b3cc  jb      short loc_18000B3AA
0x18000b3ce  mov     rcx, [rbx]; Block
0x18000b3d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000b3d6  mov     qword ptr [rbx], 0
0x18000b3dd  mov     qword ptr [rbx+8], 0
0x18000b3e5  cmp     dword ptr [rbx+30h], 0
0x18000b3e9  jnz     short loc_18000B402
0x18000b3eb  xor     edx, edx
0x18000b3ed  mov     rcx, rbx
0x18000b3f0  call    ?PickSize@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEBAI_K@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::PickSize(unsigned __int64)
0x18000b3f5  mov     edx, eax
0x18000b3f7  xor     r8d, r8d
0x18000b3fa  mov     rcx, rbx
0x18000b3fd  call    ?InitHashTable@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::InitHashTable(uint,bool)
0x18000b402  mov     rcx, rbx
0x18000b405  call    ?FreePlexes@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEAAXXZ; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreePlexes(void)
0x18000b40a  dec     dword ptr [rbx+30h]
0x18000b40d  mov     rbx, [rsp+28h+arg_0]
0x18000b412  mov     rsi, [rsp+28h+arg_8]
0x18000b417  add     rsp, 20h
0x18000b41b  pop     rdi
0x18000b41c  retn
```

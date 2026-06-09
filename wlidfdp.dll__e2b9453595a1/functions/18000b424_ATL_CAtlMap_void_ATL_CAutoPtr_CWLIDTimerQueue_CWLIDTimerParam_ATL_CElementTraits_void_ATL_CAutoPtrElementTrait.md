# ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveKey(void *)

- ea: `0x18000b424`
- end: `0x18000b4a9`
- name: `?RemoveKey@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@QEAA_NPEAX@Z`
- size: `133`
- prototype: `char __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b4b0`

## callees

- `0x18000a8e8`
- `0x18000aa90`
- `0x18000b424`

## pseudocode

```c
char __fastcall ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::RemoveKey(
        __int64 a1,
        __int64 a2)
{
  __int64 Node; // rax
  int v4; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]
  unsigned int v6; // [rsp+50h] [rbp+18h] BYREF
  __int64 v7; // [rsp+58h] [rbp+20h] BYREF

  v5 = HIDWORD(a1);
  v6 = 0;
  v4 = 0;
  v7 = 0;
  Node = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::GetNode(
           a1,
           a2,
           &v6,
           &v4,
           &v7);
  if ( Node )
  {
    if ( v7 )
      *(_QWORD *)(v7 + 16) = *(_QWORD *)(Node + 16);
    else
      *(_QWORD *)(CWLIDTimerQueue::s_TimerQueueMap + 8LL * (*(_DWORD *)(Node + 24) % (unsigned int)dword_1800203F0)) = *(_QWORD *)(Node + 16);
    ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreeNode(
      &CWLIDTimerQueue::s_TimerQueueMap,
      Node);
    LOBYTE(Node) = 1;
  }
  return Node;
}

```

## disassembly

```asm
0x18000b424  mov     r11, rsp
0x18000b427  mov     [r11+8], rcx
0x18000b42b  sub     rsp, 38h
0x18000b42f  mov     [rsp+38h+arg_10], 0
0x18000b437  mov     [rsp+38h+arg_0], 0
0x18000b43f  mov     qword ptr [r11+20h], 0
0x18000b447  lea     rax, [r11+20h]
0x18000b44b  mov     [r11-18h], rax
0x18000b44f  lea     r9, [r11+8]
0x18000b453  lea     r8, [r11+18h]
0x18000b457  call    ?GetNode@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEBAPEAVCNode@12@PEAXAEAI1AEAPEAV312@@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::GetNode(void *,uint &,uint &,ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::CNode * &)
0x18000b45c  mov     r11, rax
0x18000b45f  test    rax, rax
0x18000b462  jz      short loc_18000B4A4
0x18000b464  mov     rcx, [rsp+38h+arg_18]
0x18000b469  test    rcx, rcx
0x18000b46c  jnz     short loc_18000B48A
0x18000b46e  xor     edx, edx
0x18000b470  mov     eax, [rax+18h]
0x18000b473  div     cs:dword_1800203F0
0x18000b479  mov     rcx, [r11+10h]
0x18000b47d  mov     rax, cs:?s_TimerQueueMap@CWLIDTimerQueue@@0V?$CMapToAutoPtr@PEAXVCWLIDTimerParam@CWLIDTimerQueue@@V?$CElementTraits@PEAX@ATL@@@ATL@@A; ATL::CMapToAutoPtr<void *,CWLIDTimerQueue::CWLIDTimerParam,ATL::CElementTraits<void *>> CWLIDTimerQueue::s_TimerQueueMap
0x18000b484  mov     [rax+rdx*8], rcx
0x18000b488  jmp     short loc_18000B492
0x18000b48a  mov     rax, [rax+10h]
0x18000b48e  mov     [rcx+10h], rax
0x18000b492  mov     rdx, r11
0x18000b495  lea     rcx, ?s_TimerQueueMap@CWLIDTimerQueue@@0V?$CMapToAutoPtr@PEAXVCWLIDTimerParam@CWLIDTimerQueue@@V?$CElementTraits@PEAX@ATL@@@ATL@@A; ATL::CMapToAutoPtr<void *,CWLIDTimerQueue::CWLIDTimerParam,ATL::CElementTraits<void *>> CWLIDTimerQueue::s_TimerQueueMap
0x18000b49c  call    ?FreeNode@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDTimerParam@CWLIDTimerQueue@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDTimerParam@CWLIDTimerQueue@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::FreeNode(ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDTimerQueue::CWLIDTimerParam>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDTimerQueue::CWLIDTimerParam>>::CNode *)
0x18000b4a1  nop
0x18000b4a2  mov     al, 1
0x18000b4a4  add     rsp, 38h
0x18000b4a8  retn
```

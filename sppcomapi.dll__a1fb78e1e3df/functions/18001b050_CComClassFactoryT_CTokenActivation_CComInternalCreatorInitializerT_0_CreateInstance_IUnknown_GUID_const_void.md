# CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001b050`
- end: `0x18001b09f`
- name: `?CreateInstance@?$CComClassFactoryT@VCTokenActivation@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001b050`
- `0x18001bbdc`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CTokenActivation,CComInternalCreatorInitializerT,0>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int Instance; // eax

  if ( !a4 )
  {
    v4 = -2147467261;
LABEL_3:
    v5 = v4;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_9;
  }
  *a4 = 0;
  if ( a2 )
  {
    v4 = -2147221232;
    goto LABEL_3;
  }
  Instance = CComInternalCreatorInitializerT<CTokenActivation,0>::CreateInstance(a3, (__int64)a4);
  v4 = Instance;
  if ( Instance < 0 )
  {
    v5 = (unsigned int)Instance;
    goto LABEL_8;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x18001b050  push    rbx
0x18001b052  sub     rsp, 20h
0x18001b056  test    r9, r9
0x18001b059  jnz     short loc_18001B064
0x18001b05b  mov     ebx, 80004003h
0x18001b060  mov     ecx, ebx
0x18001b062  jmp     short loc_18001B08A
0x18001b064  mov     qword ptr [r9], 0
0x18001b06b  test    rdx, rdx
0x18001b06e  jz      short loc_18001B077
0x18001b070  mov     ebx, 80040110h
0x18001b075  jmp     short loc_18001B060
0x18001b077  mov     rdx, r9
0x18001b07a  mov     rcx, r8
0x18001b07d  call    ?CreateInstance@?$CComInternalCreatorInitializerT@VCTokenActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; CComInternalCreatorInitializerT<CTokenActivation,0>::CreateInstance(_GUID const &,void * *)
0x18001b082  mov     ebx, eax
0x18001b084  test    eax, eax
0x18001b086  jns     short loc_18001B08F
0x18001b088  mov     ecx, eax
0x18001b08a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001b08f  mov     ecx, ebx
0x18001b091  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001b096  mov     eax, ebx
0x18001b098  add     rsp, 20h
0x18001b09c  pop     rbx
0x18001b09d  retn
```

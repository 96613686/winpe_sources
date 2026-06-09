# CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001aee0`
- end: `0x18001af2f`
- name: `?CreateInstance@?$CComClassFactoryT@VCOnlineActivation@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001aee0`
- `0x18001ba44`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<COnlineActivation,CComInternalCreatorInitializerT,0>::CreateInstance(
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
  Instance = CComInternalCreatorInitializerT<COnlineActivation,0>::CreateInstance(a3, (__int64)a4);
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
0x18001aee0  push    rbx
0x18001aee2  sub     rsp, 20h
0x18001aee6  test    r9, r9
0x18001aee9  jnz     short loc_18001AEF4
0x18001aeeb  mov     ebx, 80004003h
0x18001aef0  mov     ecx, ebx
0x18001aef2  jmp     short loc_18001AF1A
0x18001aef4  mov     qword ptr [r9], 0
0x18001aefb  test    rdx, rdx
0x18001aefe  jz      short loc_18001AF07
0x18001af00  mov     ebx, 80040110h
0x18001af05  jmp     short loc_18001AEF0
0x18001af07  mov     rdx, r9
0x18001af0a  mov     rcx, r8
0x18001af0d  call    ?CreateInstance@?$CComInternalCreatorInitializerT@VCOnlineActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; CComInternalCreatorInitializerT<COnlineActivation,0>::CreateInstance(_GUID const &,void * *)
0x18001af12  mov     ebx, eax
0x18001af14  test    eax, eax
0x18001af16  jns     short loc_18001AF1F
0x18001af18  mov     ecx, eax
0x18001af1a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001af1f  mov     ecx, ebx
0x18001af21  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001af26  mov     eax, ebx
0x18001af28  add     rsp, 20h
0x18001af2c  pop     rbx
0x18001af2d  retn
```

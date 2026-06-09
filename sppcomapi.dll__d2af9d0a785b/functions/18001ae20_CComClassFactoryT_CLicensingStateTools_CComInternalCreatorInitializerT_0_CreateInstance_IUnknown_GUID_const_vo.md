# CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001ae20`
- end: `0x18001ae6f`
- name: `?CreateInstance@?$CComClassFactoryT@VCLicensingStateTools@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ae20`
- `0x18001b6cc`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CLicensingStateTools,CComInternalCreatorInitializerT,0>::CreateInstance(
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
  Instance = CComInternalCreatorInitializerT<CLicensingStateTools,0>::CreateInstance(a3, (__int64)a4);
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
0x18001ae20  push    rbx
0x18001ae22  sub     rsp, 20h
0x18001ae26  test    r9, r9
0x18001ae29  jnz     short loc_18001AE34
0x18001ae2b  mov     ebx, 80004003h
0x18001ae30  mov     ecx, ebx
0x18001ae32  jmp     short loc_18001AE5A
0x18001ae34  mov     qword ptr [r9], 0
0x18001ae3b  test    rdx, rdx
0x18001ae3e  jz      short loc_18001AE47
0x18001ae40  mov     ebx, 80040110h
0x18001ae45  jmp     short loc_18001AE30
0x18001ae47  mov     rdx, r9
0x18001ae4a  mov     rcx, r8
0x18001ae4d  call    ?CreateInstance@?$CComInternalCreatorInitializerT@VCLicensingStateTools@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; CComInternalCreatorInitializerT<CLicensingStateTools,0>::CreateInstance(_GUID const &,void * *)
0x18001ae52  mov     ebx, eax
0x18001ae54  test    eax, eax
0x18001ae56  jns     short loc_18001AE5F
0x18001ae58  mov     ecx, eax
0x18001ae5a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ae5f  mov     ecx, ebx
0x18001ae61  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ae66  mov     eax, ebx
0x18001ae68  add     rsp, 20h
0x18001ae6c  pop     rbx
0x18001ae6d  retn
```

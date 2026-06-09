# CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001adc0`
- end: `0x18001ae0f`
- name: `?CreateInstance@?$CComClassFactoryT@VCElevationConfig@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001adc0`
- `0x18001b530`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<CElevationConfig,CComInternalCreatorInitializerT,0>::CreateInstance(
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
  Instance = CComInternalCreatorInitializerT<CElevationConfig,0>::CreateInstance(a3, (__int64)a4);
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
0x18001adc0  push    rbx
0x18001adc2  sub     rsp, 20h
0x18001adc6  test    r9, r9
0x18001adc9  jnz     short loc_18001ADD4
0x18001adcb  mov     ebx, 80004003h
0x18001add0  mov     ecx, ebx
0x18001add2  jmp     short loc_18001ADFA
0x18001add4  mov     qword ptr [r9], 0
0x18001addb  test    rdx, rdx
0x18001adde  jz      short loc_18001ADE7
0x18001ade0  mov     ebx, 80040110h
0x18001ade5  jmp     short loc_18001ADD0
0x18001ade7  mov     rdx, r9
0x18001adea  mov     rcx, r8
0x18001aded  call    ?CreateInstance@?$CComInternalCreatorInitializerT@VCElevationConfig@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; CComInternalCreatorInitializerT<CElevationConfig,0>::CreateInstance(_GUID const &,void * *)
0x18001adf2  mov     ebx, eax
0x18001adf4  test    eax, eax
0x18001adf6  jns     short loc_18001ADFF
0x18001adf8  mov     ecx, eax
0x18001adfa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001adff  mov     ecx, ebx
0x18001ae01  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ae06  mov     eax, ebx
0x18001ae08  add     rsp, 20h
0x18001ae0c  pop     rbx
0x18001ae0d  retn
```

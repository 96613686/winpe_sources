# CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18001ae80`
- end: `0x18001aecf`
- name: `?CreateInstance@?$CComClassFactoryT@VCOfflineActivation@@VCComInternalCreatorInitializerT@@$0A@@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ae80`
- `0x18001b864`

## pseudocode

```c
__int64 __fastcall CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>::CreateInstance(
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
  Instance = CComInternalCreatorInitializerT<COfflineActivation,0>::CreateInstance(a3, (__int64)a4);
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
0x18001ae80  push    rbx
0x18001ae82  sub     rsp, 20h
0x18001ae86  test    r9, r9
0x18001ae89  jnz     short loc_18001AE94
0x18001ae8b  mov     ebx, 80004003h
0x18001ae90  mov     ecx, ebx
0x18001ae92  jmp     short loc_18001AEBA
0x18001ae94  mov     qword ptr [r9], 0
0x18001ae9b  test    rdx, rdx
0x18001ae9e  jz      short loc_18001AEA7
0x18001aea0  mov     ebx, 80040110h
0x18001aea5  jmp     short loc_18001AE90
0x18001aea7  mov     rdx, r9
0x18001aeaa  mov     rcx, r8
0x18001aead  call    ?CreateInstance@?$CComInternalCreatorInitializerT@VCOfflineActivation@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; CComInternalCreatorInitializerT<COfflineActivation,0>::CreateInstance(_GUID const &,void * *)
0x18001aeb2  mov     ebx, eax
0x18001aeb4  test    eax, eax
0x18001aeb6  jns     short loc_18001AEBF
0x18001aeb8  mov     ecx, eax
0x18001aeba  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001aebf  mov     ecx, ebx
0x18001aec1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001aec6  mov     eax, ebx
0x18001aec8  add     rsp, 20h
0x18001aecc  pop     rbx
0x18001aecd  retn
```

# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004460`
- end: `0x180004482`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCWinInetHelperClass@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004460`
- `0x18000448c`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  if ( !a1 )
    return ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>::CreateInstance(0, a2, a3);
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  return 2147746064LL;
}

```

## disassembly

```asm
0x180004460  test    rcx, rcx
0x180004463  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCWinInetHelperClass@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CWinInetHelperClass>>::CreateInstance(void *,_GUID const &,void * *)
0x180004469  test    r8, r8
0x18000446c  jnz     short loc_180004475
0x18000446e  mov     eax, 80004003h
0x180004473  jmp     short locret_180004481
0x180004475  mov     qword ptr [r8], 0
0x18000447c  mov     eax, 80040110h
0x180004481  retn
```

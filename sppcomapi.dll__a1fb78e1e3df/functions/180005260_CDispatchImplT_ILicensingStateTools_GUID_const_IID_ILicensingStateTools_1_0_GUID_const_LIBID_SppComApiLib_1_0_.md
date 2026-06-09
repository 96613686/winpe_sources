# CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfoCount(uint *)

- ea: `0x180005260`
- end: `0x180005298`
- name: `?GetTypeInfoCount@?$CDispatchImplT@UILicensingStateTools@@$1?IID_ILicensingStateTools@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U3@B$00$0A@@@UEAAJPEAI@Z`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180005260`

## pseudocode

```c
__int64 __fastcall CDispatchImplT<ILicensingStateTools,&_GUID const IID_ILicensingStateTools,1,0,&_GUID const LIBID_SppComApiLib,1,0>::GetTypeInfoCount(
        __int64 a1,
        _DWORD *a2)
{
  unsigned int v2; // ebx

  if ( a2 )
  {
    v2 = 0;
    *a2 = *(_DWORD *)(a1 + 12) != 0;
  }
  else
  {
    v2 = -2147467261;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147500035LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x180005260  push    rbx
0x180005262  sub     rsp, 20h
0x180005266  mov     rax, rcx
0x180005269  test    rdx, rdx
0x18000526c  jnz     short loc_18000527C
0x18000526e  mov     ebx, 80004003h
0x180005273  mov     ecx, ebx
0x180005275  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000527a  jmp     short loc_180005288
0x18000527c  xor     ecx, ecx
0x18000527e  xor     ebx, ebx
0x180005280  cmp     [rax+0Ch], ecx
0x180005283  setnz   cl
0x180005286  mov     [rdx], ecx
0x180005288  mov     ecx, ebx
0x18000528a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000528f  mov     eax, ebx
0x180005291  add     rsp, 20h
0x180005295  pop     rbx
0x180005296  retn
```

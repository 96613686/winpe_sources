# CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get_Count(long *)

- ea: `0x180020b20`
- end: `0x180020b63`
- name: `?get_Count@?$CDispCollectionOnDispImpl@VCOfflineActivationPhoneStore@@VCOfflineActivationPhoneData@@UIOfflineActivationPhoneData@@UIOfflineActivationPhoneList@@$1?IID_IOfflineActivationPhoneList@@3U_GUID@@B$00$0A@$1?LIBID_SppComApiLib@@3U6@B@@UEAAJPEAJ@Z`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x180020b20`

## pseudocode

```c
__int64 __fastcall CDispCollectionOnDispImpl<COfflineActivationPhoneStore,COfflineActivationPhoneData,IOfflineActivationPhoneData,IOfflineActivationPhoneList,&_GUID const IID_IOfflineActivationPhoneList,1,0,&_GUID const LIBID_SppComApiLib>::get_Count(
        __int64 a1,
        _DWORD *a2)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx

  v2 = *(_QWORD *)(a1 + 136);
  if ( v2 )
  {
    if ( a2 )
    {
      v3 = 0;
      *a2 = *(_DWORD *)(v2 + 12);
      goto LABEL_7;
    }
    v3 = -2147024809;
  }
  else
  {
    v3 = -2147467259;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  return v3;
}

```

## disassembly

```asm
0x180020b20  push    rbx
0x180020b22  sub     rsp, 20h
0x180020b26  mov     rcx, [rcx+88h]
0x180020b2d  test    rcx, rcx
0x180020b30  jnz     short loc_180020B40
0x180020b32  mov     ebx, 80004005h
0x180020b37  mov     ecx, ebx
0x180020b39  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180020b3e  jmp     short loc_180020B53
0x180020b40  test    rdx, rdx
0x180020b43  jnz     short loc_180020B4C
0x180020b45  mov     ebx, 80070057h
0x180020b4a  jmp     short loc_180020B37
0x180020b4c  mov     ecx, [rcx+0Ch]
0x180020b4f  xor     ebx, ebx
0x180020b51  mov     [rdx], ecx
0x180020b53  mov     ecx, ebx
0x180020b55  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180020b5a  mov     eax, ebx
0x180020b5c  add     rsp, 20h
0x180020b60  pop     rbx
0x180020b61  retn
```

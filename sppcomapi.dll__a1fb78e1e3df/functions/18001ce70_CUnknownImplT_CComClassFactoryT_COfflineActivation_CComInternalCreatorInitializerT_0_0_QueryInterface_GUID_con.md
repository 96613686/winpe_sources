# CUnknownImplT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001ce70`
- end: `0x18001cee8`
- name: `?QueryInterface@?$CUnknownImplT@V?$CComClassFactoryT@VCOfflineActivation@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001ce70`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<COfflineActivation,CComInternalCreatorInitializerT,0>,0>::QueryInterface(
        __int64 *a1,
        _QWORD *a2,
        __int64 **a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r9
  int v9; // eax

  if ( !a3 )
  {
    v5 = -2147467261;
    v6 = 2147500035LL;
LABEL_9:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_10;
  }
  v7 = *(_QWORD *)&IID_IUnknown.Data1 - *a2;
  if ( *(_QWORD *)&IID_IUnknown.Data1 == *a2 )
    v7 = *(_QWORD *)IID_IUnknown.Data4 - a2[1];
  v8 = *a1;
  if ( v7 )
  {
    v9 = (*(__int64 (**)(void))(v8 + 40))();
    v5 = v9;
    if ( v9 < 0 )
    {
      v6 = (unsigned int)v9;
      goto LABEL_9;
    }
  }
  else
  {
    (*(void (**)(void))(v8 + 8))();
    *a3 = a1;
    v5 = 0;
  }
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18001ce70  mov     [rsp+arg_0], rbx
0x18001ce75  push    rdi
0x18001ce76  sub     rsp, 20h
0x18001ce7a  mov     rdi, r8
0x18001ce7d  mov     rbx, rcx
0x18001ce80  test    r8, r8
0x18001ce83  jnz     short loc_18001CE8E
0x18001ce85  mov     ebx, 80004003h
0x18001ce8a  mov     ecx, ebx
0x18001ce8c  jmp     short loc_18001CECE
0x18001ce8e  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18001ce95  sub     rax, [rdx]
0x18001ce98  jnz     short loc_18001CEA5
0x18001ce9a  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18001cea1  sub     rax, [rdx+8]
0x18001cea5  mov     r9, [rcx]
0x18001cea8  test    rax, rax
0x18001ceab  jnz     short loc_18001CEBD
0x18001cead  mov     rax, [r9+8]
0x18001ceb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ceb6  mov     [rdi], rbx
0x18001ceb9  xor     ebx, ebx
0x18001cebb  jmp     short loc_18001CED3
0x18001cebd  mov     rax, [r9+28h]
0x18001cec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec6  mov     ebx, eax
0x18001cec8  test    eax, eax
0x18001ceca  jns     short loc_18001CED3
0x18001cecc  mov     ecx, eax
0x18001cece  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001ced3  mov     ecx, ebx
0x18001ced5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001ceda  mov     eax, ebx
0x18001cedc  mov     rbx, [rsp+28h+arg_0]
0x18001cee1  add     rsp, 20h
0x18001cee5  pop     rdi
0x18001cee6  retn
```

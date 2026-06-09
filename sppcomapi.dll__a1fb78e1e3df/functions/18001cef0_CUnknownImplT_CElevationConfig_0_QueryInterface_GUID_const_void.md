# CUnknownImplT<CElevationConfig,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001cef0`
- end: `0x18001cf68`
- name: `?QueryInterface@?$CUnknownImplT@VCElevationConfig@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d020`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001cef0`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CElevationConfig,0>::QueryInterface(__int64 *a1, _QWORD *a2, __int64 **a3)
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
    v9 = (*(__int64 (**)(void))(v8 + 112))();
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
0x18001cef0  mov     [rsp+arg_0], rbx
0x18001cef5  push    rdi
0x18001cef6  sub     rsp, 20h
0x18001cefa  mov     rdi, r8
0x18001cefd  mov     rbx, rcx
0x18001cf00  test    r8, r8
0x18001cf03  jnz     short loc_18001CF0E
0x18001cf05  mov     ebx, 80004003h
0x18001cf0a  mov     ecx, ebx
0x18001cf0c  jmp     short loc_18001CF4E
0x18001cf0e  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18001cf15  sub     rax, [rdx]
0x18001cf18  jnz     short loc_18001CF25
0x18001cf1a  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18001cf21  sub     rax, [rdx+8]
0x18001cf25  mov     r9, [rcx]
0x18001cf28  test    rax, rax
0x18001cf2b  jnz     short loc_18001CF3D
0x18001cf2d  mov     rax, [r9+8]
0x18001cf31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf36  mov     [rdi], rbx
0x18001cf39  xor     ebx, ebx
0x18001cf3b  jmp     short loc_18001CF53
0x18001cf3d  mov     rax, [r9+70h]
0x18001cf41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf46  mov     ebx, eax
0x18001cf48  test    eax, eax
0x18001cf4a  jns     short loc_18001CF53
0x18001cf4c  mov     ecx, eax
0x18001cf4e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001cf53  mov     ecx, ebx
0x18001cf55  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001cf5a  mov     eax, ebx
0x18001cf5c  mov     rbx, [rsp+28h+arg_0]
0x18001cf61  add     rsp, 20h
0x18001cf65  pop     rdi
0x18001cf66  retn
```

# CUnknownImplT<CTokenActivation,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x18001d160`
- end: `0x18001d1d8`
- name: `?QueryInterface@?$CUnknownImplT@VCTokenActivation@@$0A@@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001d1e0`

## callees

- `0x180003520`
- `0x180004288`
- `0x18001d160`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CTokenActivation,0>::QueryInterface(__int64 *a1, _QWORD *a2, __int64 **a3)
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
    v9 = (*(__int64 (**)(void))(v8 + 80))();
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
0x18001d160  mov     [rsp+arg_0], rbx
0x18001d165  push    rdi
0x18001d166  sub     rsp, 20h
0x18001d16a  mov     rdi, r8
0x18001d16d  mov     rbx, rcx
0x18001d170  test    r8, r8
0x18001d173  jnz     short loc_18001D17E
0x18001d175  mov     ebx, 80004003h
0x18001d17a  mov     ecx, ebx
0x18001d17c  jmp     short loc_18001D1BE
0x18001d17e  mov     rax, qword ptr cs:IID_IUnknown.Data1
0x18001d185  sub     rax, [rdx]
0x18001d188  jnz     short loc_18001D195
0x18001d18a  mov     rax, qword ptr cs:IID_IUnknown.Data4
0x18001d191  sub     rax, [rdx+8]
0x18001d195  mov     r9, [rcx]
0x18001d198  test    rax, rax
0x18001d19b  jnz     short loc_18001D1AD
0x18001d19d  mov     rax, [r9+8]
0x18001d1a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a6  mov     [rdi], rbx
0x18001d1a9  xor     ebx, ebx
0x18001d1ab  jmp     short loc_18001D1C3
0x18001d1ad  mov     rax, [r9+50h]
0x18001d1b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1b6  mov     ebx, eax
0x18001d1b8  test    eax, eax
0x18001d1ba  jns     short loc_18001D1C3
0x18001d1bc  mov     ecx, eax
0x18001d1be  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001d1c3  mov     ecx, ebx
0x18001d1c5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18001d1ca  mov     eax, ebx
0x18001d1cc  mov     rbx, [rsp+28h+arg_0]
0x18001d1d1  add     rsp, 20h
0x18001d1d5  pop     rdi
0x18001d1d6  retn
```

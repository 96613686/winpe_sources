# CElevationConfig::ConfigureObject(IUnknown *)

- ea: `0x180003650`
- end: `0x1800036e3`
- name: `?ConfigureObject@CElevationConfig@@UEAAJPEAUIUnknown@@@Z`
- size: `147`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180003650`
- `0x180004288`
- `0x18003d010`

## pseudocode

```c
__int64 __fastcall CElevationConfig::ConfigureObject(CElevationConfig *this, struct IUnknown *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
    v4 = 2147942487LL;
LABEL_6:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_7;
  }
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IElevationConfigurable,
         &v7);
  v3 = v5;
  if ( v5 < 0
    || (v5 = (*(__int64 (__fastcall **)(__int64, CElevationConfig *))(*(_QWORD *)v7 + 24LL))(v7, this), v3 = v5, v5 < 0) )
  {
    v4 = (unsigned int)v5;
    goto LABEL_6;
  }
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v3;
}

```

## disassembly

```asm
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  push    rdi
0x180003656  sub     rsp, 20h
0x18000365a  mov     [rsp+28h+arg_8], 0
0x180003663  mov     r9, rdx
0x180003666  mov     rdi, rcx
0x180003669  test    rdx, rdx
0x18000366c  jnz     short loc_180003677
0x18000366e  mov     ebx, 80070057h
0x180003673  mov     ecx, ebx
0x180003675  jmp     short loc_1800036B3
0x180003677  mov     rax, [rdx]
0x18000367a  lea     r8, [rsp+28h+arg_8]
0x18000367f  lea     rdx, IID_IElevationConfigurable
0x180003686  mov     rcx, r9
0x180003689  mov     rax, [rax]
0x18000368c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003691  mov     ebx, eax
0x180003693  test    eax, eax
0x180003695  js      short loc_1800036B1
0x180003697  mov     rcx, [rsp+28h+arg_8]
0x18000369c  mov     rdx, rdi
0x18000369f  mov     rax, [rcx]
0x1800036a2  mov     rax, [rax+18h]
0x1800036a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ab  mov     ebx, eax
0x1800036ad  test    eax, eax
0x1800036af  jns     short loc_1800036B8
0x1800036b1  mov     ecx, eax
0x1800036b3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800036b8  mov     ecx, ebx
0x1800036ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800036bf  mov     rcx, [rsp+28h+arg_8]
0x1800036c4  test    rcx, rcx
0x1800036c7  jz      short loc_1800036D5
0x1800036c9  mov     rax, [rcx]
0x1800036cc  mov     rax, [rax+10h]
0x1800036d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d5  mov     eax, ebx
0x1800036d7  mov     rbx, [rsp+28h+arg_0]
0x1800036dc  add     rsp, 20h
0x1800036e0  pop     rdi
0x1800036e1  retn
```

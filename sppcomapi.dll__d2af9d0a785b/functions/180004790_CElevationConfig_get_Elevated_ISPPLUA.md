# CElevationConfig::get_Elevated(ISPPLUA * *)

- ea: `0x180004790`
- end: `0x1800047c6`
- name: `?get_Elevated@CElevationConfig@@UEAAJPEAPEAUISPPLUA@@@Z`
- size: `54`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, struct ISPPLUA **)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x180003e14`
- `0x180004288`
- `0x180004790`

## pseudocode

```c
__int64 __fastcall CElevationConfig::get_Elevated(CElevationConfig *this, struct ISPPLUA **a2)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  int Elevated; // eax

  if ( !a2 )
  {
    v2 = -2147024809;
    v3 = 2147942487LL;
LABEL_5:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
    goto LABEL_6;
  }
  Elevated = CElevationConfig::GetElevated(this, a2);
  v2 = Elevated;
  if ( Elevated < 0 )
  {
    v3 = (unsigned int)Elevated;
    goto LABEL_5;
  }
LABEL_6:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v2);
  return v2;
}

```

## disassembly

```asm
0x180004790  push    rbx
0x180004792  sub     rsp, 20h
0x180004796  test    rdx, rdx
0x180004799  jnz     short loc_1800047A4
0x18000479b  mov     ebx, 80070057h
0x1800047a0  mov     ecx, ebx; this
0x1800047a2  jmp     short loc_1800047B1
0x1800047a4  call    ?GetElevated@CElevationConfig@@QEAAJPEAPEAUISPPLUA@@@Z; CElevationConfig::GetElevated(ISPPLUA * *)
0x1800047a9  mov     ebx, eax
0x1800047ab  test    eax, eax
0x1800047ad  jns     short loc_1800047B6
0x1800047af  mov     ecx, eax
0x1800047b1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800047b6  mov     ecx, ebx
0x1800047b8  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800047bd  mov     eax, ebx
0x1800047bf  add     rsp, 20h
0x1800047c3  pop     rbx
0x1800047c4  retn
```

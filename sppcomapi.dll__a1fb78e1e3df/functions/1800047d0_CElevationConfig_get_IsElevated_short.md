# CElevationConfig::get_IsElevated(short *)

- ea: `0x1800047d0`
- end: `0x18000482c`
- name: `?get_IsElevated@CElevationConfig@@UEAAJPEAF@Z`
- size: `92`
- prototype: `__int64 __fastcall(CElevationConfig *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003520`
- `0x1800041c8`
- `0x180004288`
- `0x1800047d0`

## pseudocode

```c
__int64 __fastcall CElevationConfig::get_IsElevated(CElevationConfig *this, __int16 *a2)
{
  unsigned int v4; // ebx
  int v5; // eax

  if ( a2 )
  {
    v4 = 0;
    v5 = IsUserAdmin();
    if ( v5 || *((_QWORD *)this + 18) )
      LOWORD(v5) = -1;
    *a2 = v5;
  }
  else
  {
    v4 = -2147024809;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x1800047d0  mov     [rsp+arg_0], rbx
0x1800047d5  mov     [rsp+arg_8], rsi
0x1800047da  push    rdi
0x1800047db  sub     rsp, 20h
0x1800047df  mov     rdi, rdx
0x1800047e2  mov     rsi, rcx
0x1800047e5  test    rdx, rdx
0x1800047e8  jnz     short loc_1800047F8
0x1800047ea  mov     ebx, 80070057h
0x1800047ef  mov     ecx, ebx
0x1800047f1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800047f6  jmp     short loc_180004812
0x1800047f8  xor     ebx, ebx
0x1800047fa  call    ?IsUserAdmin@@YAHXZ; IsUserAdmin(void)
0x1800047ff  test    eax, eax
0x180004801  jnz     short loc_18000480C
0x180004803  cmp     [rsi+90h], rbx
0x18000480a  jz      short loc_18000480F
0x18000480c  or      eax, 0FFFFFFFFh
0x18000480f  mov     [rdi], ax
0x180004812  mov     ecx, ebx
0x180004814  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180004819  mov     rsi, [rsp+28h+arg_8]
0x18000481e  mov     eax, ebx
0x180004820  mov     rbx, [rsp+28h+arg_0]
0x180004825  add     rsp, 20h
0x180004829  pop     rdi
0x18000482a  retn
```

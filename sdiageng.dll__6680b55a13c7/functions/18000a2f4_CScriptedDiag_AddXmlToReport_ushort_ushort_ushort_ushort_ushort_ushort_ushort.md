# CScriptedDiag::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)

- ea: `0x18000a2f4`
- end: `0x18000a4d7`
- name: `?AddXmlToReport@CScriptedDiag@@QEAAJPEAG000000@Z`
- size: `483`
- prototype: `__int64 __fastcall(DiagPackage **this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *String2, unsigned __int16 *String1, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013c90`

## callees

- `0x18000a2f4`
- `0x18000a730`
- `0x180014544`
- `0x180026fa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a3e2`
- `msvcrt!_wcsicmp` at `0x18000a3f6`
- `msvcrt!_wcsicmp` at `0x18000a40a`
- `msvcrt!_wcsicmp` at `0x18000a41e`
- `msvcrt!_wcsicmp` at `0x18000a43a`
- `msvcrt!_wcsicmp` at `0x18000a44e`
- `msvcrt!_wcsicmp` at `0x18000a3e2`
- `msvcrt!_wcsicmp` at `0x18000a3f6`
- `msvcrt!_wcsicmp` at `0x18000a40a`
- `msvcrt!_wcsicmp` at `0x18000a41e`
- `msvcrt!_wcsicmp` at `0x18000a43a`
- `msvcrt!_wcsicmp` at `0x18000a44e`

## string_xrefs

- `0x18000a4b3`: `CScriptedDiag::AddXmlToReport`

## pseudocode

```c
__int64 __fastcall CScriptedDiag::AddXmlToReport(
        DiagPackage **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *String2,
        unsigned __int16 *String1,
        unsigned __int16 *a8)
{
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // r9d
  int v15; // r8d
  DiagPackage *v16; // rcx
  int v17; // eax
  _DWORD v19[22]; // [rsp+40h] [rbp-58h] BYREF

  v19[1] = 5;
  v19[2] = 6;
  v19[0] = 3;
  v12 = CScriptedDiag::CheckState((CScriptedDiag *)this, (enum Settings::SDIAG_ENGINE_STATE *)v19, 3u);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = v12;
    v15 = 2565;
LABEL_30:
    SdpDebugTrace(1u, L"CScriptedDiag::AddXmlToReport", v15, v14);
    return v13;
  }
  if ( !a2 )
  {
    v15 = 2567;
LABEL_29:
    v14 = -2147024809;
    v13 = -2147024809;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v15 = 2568;
    goto LABEL_29;
  }
  if ( !a4 )
  {
    v15 = 2569;
    goto LABEL_29;
  }
  if ( !a5 )
  {
    v15 = 2570;
    goto LABEL_29;
  }
  if ( !String2 )
  {
    v15 = 2571;
    goto LABEL_29;
  }
  if ( !String1 )
  {
    v15 = 2572;
    goto LABEL_29;
  }
  if ( !a8 )
  {
    v15 = 2573;
    goto LABEL_29;
  }
  if ( !_wcsicmp(String1, &word_18002DFCC) && _wcsicmp(a8, &word_18002DFCC)
    || !_wcsicmp(a8, &word_18002DFCC) && _wcsicmp(String1, &word_18002DFCC) )
  {
    v15 = 2582;
    goto LABEL_29;
  }
  if ( !_wcsicmp(a3, &word_18002DFCC) || !_wcsicmp(a2, &word_18002DFCC) )
  {
    v15 = 2592;
    goto LABEL_29;
  }
  v16 = this[4];
  if ( !v16 )
  {
    v13 = -2147467261;
    v15 = 2595;
    v14 = -2147467261;
    goto LABEL_30;
  }
  v17 = DiagPackage::AddXmlToReport(v16, a2, a3, a4, a5, String2, String1, a8);
  v13 = v17;
  if ( v17 < 0 )
  {
    v14 = v17;
    v15 = 2603;
    goto LABEL_30;
  }
  return v13;
}

```

## disassembly

```asm
0x18000a2f4  mov     rax, rsp
0x18000a2f7  push    rbx
0x18000a2f8  push    rbp
0x18000a2f9  push    rsi
0x18000a2fa  push    rdi
0x18000a2fb  push    r12
0x18000a2fd  push    r13
0x18000a2ff  push    r14
0x18000a301  push    r15
0x18000a303  sub     rsp, 58h
0x18000a307  mov     r14, r8
0x18000a30a  mov     dword ptr [rax-54h], 5
0x18000a311  mov     r8d, 3; unsigned int
0x18000a317  mov     dword ptr [rax-50h], 6
0x18000a31e  mov     r15, rdx
0x18000a321  mov     [rax-58h], r8d
0x18000a325  lea     rdx, [rax-58h]; enum Settings::SDIAG_ENGINE_STATE *
0x18000a329  mov     r12, r9
0x18000a32c  mov     r13, rcx
0x18000a32f  call    ?CheckState@CScriptedDiag@@AEAAJPEAW4SDIAG_ENGINE_STATE@Settings@@K@Z; CScriptedDiag::CheckState(Settings::SDIAG_ENGINE_STATE *,ulong)
0x18000a334  mov     ebx, eax
0x18000a336  test    eax, eax
0x18000a338  jns     short loc_18000A348
0x18000a33a  mov     r9d, eax
0x18000a33d  mov     r8d, 0A05h
0x18000a343  jmp     loc_18000A4B3
0x18000a348  test    r15, r15
0x18000a34b  jnz     short loc_18000A358
0x18000a34d  mov     r8d, 0A07h
0x18000a353  jmp     loc_18000A4AA
0x18000a358  test    r14, r14
0x18000a35b  jnz     short loc_18000A368
0x18000a35d  mov     r8d, 0A08h
0x18000a363  jmp     loc_18000A4AA
0x18000a368  test    r12, r12
0x18000a36b  jnz     short loc_18000A378
0x18000a36d  mov     r8d, 0A09h
0x18000a373  jmp     loc_18000A4AA
0x18000a378  mov     rsi, [rsp+98h+arg_20]
0x18000a380  test    rsi, rsi
0x18000a383  jnz     short loc_18000A390
0x18000a385  mov     r8d, 0A0Ah
0x18000a38b  jmp     loc_18000A4AA
0x18000a390  mov     rbp, [rsp+98h+arg_28]
0x18000a398  test    rbp, rbp
0x18000a39b  jnz     short loc_18000A3A8
0x18000a39d  mov     r8d, 0A0Bh
0x18000a3a3  jmp     loc_18000A4AA
0x18000a3a8  mov     rbx, [rsp+98h+String1]
0x18000a3b0  test    rbx, rbx
0x18000a3b3  jnz     short loc_18000A3C0
0x18000a3b5  mov     r8d, 0A0Ch
0x18000a3bb  jmp     loc_18000A4AA
0x18000a3c0  mov     rdi, [rsp+98h+arg_38]
0x18000a3c8  test    rdi, rdi
0x18000a3cb  jnz     short loc_18000A3D8
0x18000a3cd  mov     r8d, 0A0Dh
0x18000a3d3  jmp     loc_18000A4AA
0x18000a3d8  lea     rdx, word_18002DFCC; String2
0x18000a3df  mov     rcx, rbx; String1
0x18000a3e2  call    cs:__imp__wcsicmp
0x18000a3e8  test    eax, eax
0x18000a3ea  jnz     short loc_18000A400
0x18000a3ec  lea     rdx, word_18002DFCC; String2
0x18000a3f3  mov     rcx, rdi; String1
0x18000a3f6  call    cs:__imp__wcsicmp
0x18000a3fc  test    eax, eax
0x18000a3fe  jnz     short loc_18000A428
0x18000a400  lea     rdx, word_18002DFCC; String2
0x18000a407  mov     rcx, rdi; String1
0x18000a40a  call    cs:__imp__wcsicmp
0x18000a410  test    eax, eax
0x18000a412  jnz     short loc_18000A430
0x18000a414  lea     rdx, word_18002DFCC; String2
0x18000a41b  mov     rcx, rbx; String1
0x18000a41e  call    cs:__imp__wcsicmp
0x18000a424  test    eax, eax
0x18000a426  jz      short loc_18000A430
0x18000a428  mov     r8d, 0A16h
0x18000a42e  jmp     short loc_18000A4AA
0x18000a430  lea     rdx, word_18002DFCC; String2
0x18000a437  mov     rcx, r14; String1
0x18000a43a  call    cs:__imp__wcsicmp
0x18000a440  test    eax, eax
0x18000a442  jz      short loc_18000A4A4
0x18000a444  lea     rdx, word_18002DFCC; String2
0x18000a44b  mov     rcx, r15; String1
0x18000a44e  call    cs:__imp__wcsicmp
0x18000a454  test    eax, eax
0x18000a456  jz      short loc_18000A4A4
0x18000a458  mov     rcx, [r13+20h]; this
0x18000a45c  test    rcx, rcx
0x18000a45f  jnz     short loc_18000A471
0x18000a461  mov     ebx, 80004003h
0x18000a466  mov     r8d, 0A23h
0x18000a46c  mov     r9d, ebx
0x18000a46f  jmp     short loc_18000A4B3
0x18000a471  mov     [rsp+98h+var_60], rdi; wchar_t *
0x18000a476  mov     r9, r12; unsigned __int16 *
0x18000a479  mov     [rsp+98h+var_68], rbx; String1
0x18000a47e  mov     r8, r14; unsigned __int16 *
0x18000a481  mov     [rsp+98h+String2], rbp; String2
0x18000a486  mov     rdx, r15; unsigned __int16 *
0x18000a489  mov     [rsp+98h+var_78], rsi; unsigned __int16 *
0x18000a48e  call    ?AddXmlToReport@DiagPackage@@QEAAJPEAG000000@Z; DiagPackage::AddXmlToReport(ushort *,ushort *,ushort *,ushort *,ushort *,ushort *,ushort *)
0x18000a493  mov     ebx, eax
0x18000a495  test    eax, eax
0x18000a497  jns     short loc_18000A4C4
0x18000a499  mov     r9d, eax
0x18000a49c  mov     r8d, 0A2Bh
0x18000a4a2  jmp     short loc_18000A4B3
0x18000a4a4  mov     r8d, 0A20h; int
0x18000a4aa  mov     r9d, 80070057h; int
0x18000a4b0  mov     ebx, r9d
0x18000a4b3  lea     rdx, aCscripteddiagA; "CScriptedDiag::AddXmlToReport"
0x18000a4ba  mov     ecx, 1; Level
0x18000a4bf  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000a4c4  mov     eax, ebx
0x18000a4c6  add     rsp, 58h
0x18000a4ca  pop     r15
0x18000a4cc  pop     r14
0x18000a4ce  pop     r13
0x18000a4d0  pop     r12
0x18000a4d2  pop     rdi
0x18000a4d3  pop     rsi
0x18000a4d4  pop     rbp
0x18000a4d5  pop     rbx
0x18000a4d6  retn
```

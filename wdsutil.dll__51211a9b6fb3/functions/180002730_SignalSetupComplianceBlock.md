# SignalSetupComplianceBlock

- ea: `0x180002730`
- end: `0x180002891`
- name: `SignalSetupComplianceBlock`
- size: `353`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002730`
- `0x18000860c`
- `0x18000864c`
- `0x1800087cc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180002762`
- `KERNEL32!GetLastError` at `0x180002780`
- `KERNEL32!GetLastError` at `0x1800027b9`
- `KERNEL32!GetLastError` at `0x1800027d7`
- `KERNEL32!GetLastError` at `0x180002836`
- `KERNEL32!GetLastError` at `0x180002850`
- `KERNEL32!GetLastError` at `0x180002762`
- `KERNEL32!GetLastError` at `0x180002780`
- `KERNEL32!GetLastError` at `0x1800027b9`
- `KERNEL32!GetLastError` at `0x1800027d7`
- `KERNEL32!GetLastError` at `0x180002836`
- `KERNEL32!GetLastError` at `0x180002850`
- `WDSCORE!WdsDestroyBlackboard` at `0x180002877`
- `WDSCORE!WdsDestroyBlackboard` at `0x180002877`

## string_xrefs

- `0x1800027fd`: `Diagnostics\Dword\SetupCompliance`

## pseudocode

```c
__int64 __fastcall SignalSetupComplianceBlock(const unsigned __int16 *a1, int a2)
{
  int v3; // edi
  signed int v5; // ebx
  const unsigned __int16 *v6; // rdx
  struct _BLACKBOARD *Board; // rsi
  signed int LastError; // eax
  bool v9; // sf
  signed int v10; // eax
  signed int v11; // eax
  bool v12; // sf
  signed int v13; // eax
  unsigned int Dword; // eax
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // eax
  signed int v17; // eax
  bool v18; // sf
  signed int v19; // eax

  v3 = (int)a1;
  if ( !(_DWORD)a1 )
    return 2147942487LL;
  v5 = 0;
  Board = BbCreateBoard(a1);
  if ( Board )
    goto LABEL_10;
  LastError = GetLastError();
  v9 = LastError < 0;
  if ( LastError > 0 )
    v9 = 1;
  if ( v9 )
  {
    v10 = GetLastError();
    v5 = v10;
    if ( v10 > 0 )
      v5 = (unsigned __int16)v10 | 0x80070000;
    if ( v5 < 0 )
      return (unsigned int)v5;
LABEL_10:
    if ( !(unsigned int)BbSetDword(Board, v6, L"ID", 0x923u) )
    {
      v11 = GetLastError();
      v12 = v11 < 0;
      if ( v11 > 0 )
        v12 = 1;
      if ( !v12 )
        goto LABEL_27;
      v13 = GetLastError();
      v5 = v13;
      if ( v13 > 0 )
        v5 = (unsigned __int16)v13 | 0x80070000;
      if ( v5 < 0 )
        goto LABEL_28;
    }
    Dword = BbGetDword(Board, L"Diagnostics\\Dword\\SetupCompliance", L"Data", 0);
    if ( a2 == 1 )
      v16 = v3 | Dword;
    else
      v16 = ~v3 & Dword;
    if ( (unsigned int)BbSetDword(Board, v15, L"Data", v16) )
      goto LABEL_28;
    v17 = GetLastError();
    v18 = v17 < 0;
    if ( v17 > 0 )
      v18 = 1;
    if ( v18 )
    {
      v19 = GetLastError();
      v5 = v19;
      if ( v19 > 0 )
        v5 = (unsigned __int16)v19 | 0x80070000;
      goto LABEL_28;
    }
LABEL_27:
    v5 = -2147467259;
LABEL_28:
    if ( Board )
      WdsDestroyBlackboard(Board);
    return (unsigned int)v5;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180002730  push    rbx
0x180002732  push    rbp
0x180002733  push    rsi
0x180002734  push    rdi
0x180002735  push    r14
0x180002737  sub     rsp, 20h
0x18000273b  mov     ebp, edx
0x18000273d  mov     edi, ecx
0x18000273f  test    ecx, ecx
0x180002741  jnz     short loc_18000274D
0x180002743  mov     eax, 80070057h
0x180002748  jmp     loc_180002885
0x18000274d  xor     ebx, ebx
0x18000274f  call    ?BbCreateBoard@@YAPEAU_BLACKBOARD@@PEBGK@Z; BbCreateBoard(ushort const *,ulong)
0x180002754  mov     rsi, rax
0x180002757  mov     r14d, 80070000h
0x18000275d  test    rax, rax
0x180002760  jnz     short loc_1800027A0
0x180002762  call    cs:__imp_GetLastError
0x180002769  nop     dword ptr [rax+rax+00h]
0x18000276e  test    eax, eax
0x180002770  jle     short loc_18000277A
0x180002772  movzx   eax, ax
0x180002775  or      eax, r14d
0x180002778  test    eax, eax
0x18000277a  jns     loc_180002815
0x180002780  call    cs:__imp_GetLastError
0x180002787  nop     dword ptr [rax+rax+00h]
0x18000278c  mov     ebx, eax
0x18000278e  test    eax, eax
0x180002790  jle     short loc_180002798
0x180002792  movzx   ebx, ax
0x180002795  or      ebx, r14d
0x180002798  test    ebx, ebx
0x18000279a  js      loc_180002883
0x1800027a0  mov     r9d, 923h; unsigned int
0x1800027a6  lea     r8, aId; "ID"
0x1800027ad  mov     rcx, rsi; struct _BLACKBOARD *
0x1800027b0  call    ?BbSetDword@@YAHPEAU_BLACKBOARD@@PEBG1K@Z; BbSetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)
0x1800027b5  test    eax, eax
0x1800027b7  jnz     short loc_1800027F3
0x1800027b9  call    cs:__imp_GetLastError
0x1800027c0  nop     dword ptr [rax+rax+00h]
0x1800027c5  test    eax, eax
0x1800027c7  jle     short loc_1800027D1
0x1800027c9  movzx   eax, ax
0x1800027cc  or      eax, r14d
0x1800027cf  test    eax, eax
0x1800027d1  jns     loc_18000286A
0x1800027d7  call    cs:__imp_GetLastError
0x1800027de  nop     dword ptr [rax+rax+00h]
0x1800027e3  mov     ebx, eax
0x1800027e5  test    eax, eax
0x1800027e7  jle     short loc_1800027EF
0x1800027e9  movzx   ebx, ax
0x1800027ec  or      ebx, r14d
0x1800027ef  test    ebx, ebx
0x1800027f1  js      short loc_18000286F
0x1800027f3  xor     r9d, r9d; unsigned int
0x1800027f6  lea     r8, aData; "Data"
0x1800027fd  lea     rdx, aDiagnosticsDwo; "Diagnostics\\Dword\\SetupCompliance"
0x180002804  mov     rcx, rsi; struct _BLACKBOARD *
0x180002807  call    ?BbGetDword@@YAKPEAU_BLACKBOARD@@PEBG1K@Z; BbGetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)
0x18000280c  cmp     ebp, 1
0x18000280f  jnz     short loc_18000281C
0x180002811  or      eax, edi
0x180002813  jmp     short loc_180002820
0x180002815  mov     ebx, 80004005h
0x18000281a  jmp     short loc_180002883
0x18000281c  not     edi
0x18000281e  and     eax, edi
0x180002820  mov     r9d, eax; unsigned int
0x180002823  lea     r8, aData; "Data"
0x18000282a  mov     rcx, rsi; struct _BLACKBOARD *
0x18000282d  call    ?BbSetDword@@YAHPEAU_BLACKBOARD@@PEBG1K@Z; BbSetDword(_BLACKBOARD *,ushort const *,ushort const *,ulong)
0x180002832  test    eax, eax
0x180002834  jnz     short loc_18000286F
0x180002836  call    cs:__imp_GetLastError
0x18000283d  nop     dword ptr [rax+rax+00h]
0x180002842  test    eax, eax
0x180002844  jle     short loc_18000284E
0x180002846  movzx   eax, ax
0x180002849  or      eax, r14d
0x18000284c  test    eax, eax
0x18000284e  jns     short loc_18000286A
0x180002850  call    cs:__imp_GetLastError
0x180002857  nop     dword ptr [rax+rax+00h]
0x18000285c  mov     ebx, eax
0x18000285e  test    eax, eax
0x180002860  jle     short loc_18000286F
0x180002862  movzx   ebx, ax
0x180002865  or      ebx, r14d
0x180002868  jmp     short loc_18000286F
0x18000286a  mov     ebx, 80004005h
0x18000286f  test    rsi, rsi
0x180002872  jz      short loc_180002883
0x180002874  mov     rcx, rsi
0x180002877  call    cs:__imp_WdsDestroyBlackboard
0x18000287e  nop     dword ptr [rax+rax+00h]
0x180002883  mov     eax, ebx
0x180002885  add     rsp, 20h
0x180002889  pop     r14
0x18000288b  pop     rdi
0x18000288c  pop     rsi
0x18000288d  pop     rbp
0x18000288e  pop     rbx
0x18000288f  retn
```

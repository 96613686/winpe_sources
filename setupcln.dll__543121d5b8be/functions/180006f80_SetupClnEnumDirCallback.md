# SetupClnEnumDirCallback

- ea: `0x180006f80`
- end: `0x18000709c`
- name: `SetupClnEnumDirCallback`
- size: `284`
- prototype: `_BOOL8 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x1800047ac`
- `0x180004a54`
- `0x180006f80`
- `0x180007b68`
- `0x180008ad0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006fdc`
- `WDSCORE!CurrentIP` at `0x180006fe4`
- `WDSCORE!CurrentIP` at `0x180006fe4`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000704e`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000704e`

## string_xrefs

- `0x180006fee`: `SetupClnEnumDirCallback Failed to move [%s]. status: %x`

## pseudocode

```c
_BOOL8 __fastcall SetupClnEnumDirCallback(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // r14
  __int64 v6; // rcx
  int v7; // r15d
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  int v11; // eax
  __int64 v13; // [rsp+A0h] [rbp+8h] BYREF

  v13 = 0;
  if ( !a1 )
    return 1;
  if ( !a3 )
    return 1;
  v5 = *(_QWORD *)(a3 + 160);
  if ( !v5 )
    return 1;
  v6 = *(_QWORD *)(a3 + 16);
  if ( v6 )
  {
    v7 = SetupClnMoveFileToScratchReserve(v6, *(_QWORD *)(a1 + 40));
    if ( v7 < 0 )
    {
      LastError = GetLastError();
      v9 = CurrentIP();
      v10 = ConstructPartialMsgW(
              0x3000000u,
              "SetupClnEnumDirCallback Failed to move [%s]. status: %x",
              *(const char **)(a1 + 40),
              v7);
      WdsSetupLogMessageW(
        v10,
        0,
        L"D",
        0,
        1700,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnEnumDirCallback",
        v9,
        LastError,
        0,
        0);
    }
  }
  v11 = DuplicateString(*(unsigned __int16 **)(a1 + 40));
  if ( v11 >= 0 )
  {
    std::deque<unsigned short const *>::push_back(v5, &v13);
    return *(_DWORD *)(a3 + 28) == 0;
  }
  else
  {
    *(_DWORD *)(a3 + 24) = v11;
    return 0;
  }
}

```

## disassembly

```asm
0x180006f80  mov     rax, rsp
0x180006f83  push    rbx
0x180006f84  push    rbp
0x180006f85  push    rsi
0x180006f86  push    rdi
0x180006f87  push    r14
0x180006f89  push    r15
0x180006f8b  sub     rsp, 68h
0x180006f8f  mov     qword ptr [rax+8], 0
0x180006f97  mov     rsi, r8
0x180006f9a  mov     rbp, rcx
0x180006f9d  test    rcx, rcx
0x180006fa0  jz      loc_18000708A
0x180006fa6  test    r8, r8
0x180006fa9  jz      loc_18000708A
0x180006faf  mov     r14, [r8+0A0h]
0x180006fb6  test    r14, r14
0x180006fb9  jz      loc_18000708A
0x180006fbf  mov     rcx, [r8+10h]
0x180006fc3  test    rcx, rcx
0x180006fc6  jz      loc_180007054
0x180006fcc  mov     rdx, [rbp+28h]
0x180006fd0  call    SetupClnMoveFileToScratchReserve
0x180006fd5  mov     r15d, eax
0x180006fd8  test    eax, eax
0x180006fda  jns     short loc_180007054
0x180006fdc  call    cs:__imp_GetLastError
0x180006fe2  mov     edi, eax
0x180006fe4  call    cs:__imp_CurrentIP
0x180006fea  mov     r8, [rbp+28h]
0x180006fee  lea     rdx, aSetupclnenumdi_2; "SetupClnEnumDirCallback Failed to move "...
0x180006ff5  mov     r9d, r15d
0x180006ff8  mov     ecx, 3000000h; unsigned int
0x180006ffd  mov     rbx, rax
0x180007000  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007005  mov     [rsp+98h+var_48], 0
0x18000700d  lea     rcx, aSetupclnenumdi_1; "SetupClnEnumDirCallback"
0x180007014  mov     [rsp+98h+var_50], 0
0x18000701d  lea     r8, aD; "D"
0x180007024  mov     [rsp+98h+var_58], edi
0x180007028  xor     r9d, r9d
0x18000702b  mov     [rsp+98h+var_60], rbx
0x180007030  xor     edx, edx
0x180007032  mov     [rsp+98h+var_68], rcx
0x180007037  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x18000703e  mov     [rsp+98h+var_70], rcx
0x180007043  mov     rcx, rax
0x180007046  mov     [rsp+98h+var_78], 6A4h
0x18000704e  call    cs:__imp_WdsSetupLogMessageW
0x180007054  mov     rcx, [rbp+28h]; unsigned __int16 *
0x180007058  lea     rdx, [rsp+98h+arg_0]
0x180007060  call    DuplicateString
0x180007065  test    eax, eax
0x180007067  jns     short loc_180007070
0x180007069  mov     [rsi+18h], eax
0x18000706c  xor     eax, eax
0x18000706e  jmp     short loc_18000708F
0x180007070  lea     rdx, [rsp+98h+arg_0]
0x180007078  mov     rcx, r14
0x18000707b  call    ?push_back@?$deque@PEBGV?$allocator@PEBG@std@@@std@@QEAAXAEBQEBG@Z; std::deque<ushort const *>::push_back(ushort const * const &)
0x180007080  xor     eax, eax
0x180007082  cmp     [rsi+1Ch], eax
0x180007085  setz    al
0x180007088  jmp     short loc_18000708F
0x18000708a  mov     eax, 1
0x18000708f  add     rsp, 68h
0x180007093  pop     r15
0x180007095  pop     r14
0x180007097  pop     rdi
0x180007098  pop     rsi
0x180007099  pop     rbp
0x18000709a  pop     rbx
0x18000709b  retn
```

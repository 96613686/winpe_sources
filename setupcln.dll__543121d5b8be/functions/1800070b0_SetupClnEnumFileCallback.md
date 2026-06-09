# SetupClnEnumFileCallback

- ea: `0x1800070b0`
- end: `0x1800071a1`
- name: `SetupClnEnumFileCallback`
- size: `241`
- prototype: `_BOOL8 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callees

- `0x1800047ac`
- `0x1800070b0`
- `0x1800071a8`
- `0x180007b68`
- `0x180007c44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070f0`
- `WDSCORE!CurrentIP` at `0x1800070f8`
- `WDSCORE!CurrentIP` at `0x1800070f8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007162`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007162`

## string_xrefs

- `0x180007102`: `SetupClnEnumFileCallback Failed to move [%s] to scratch. status: %x`

## pseudocode

```c
_BOOL8 __fastcall SetupClnEnumFileCallback(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  int v5; // r14d
  DWORD LastError; // edi
  __int64 v7; // rbx
  struct tagLOG_PARTIAL_MSG *v8; // rax
  __int64 v9; // rax

  if ( !a1 || !a2 )
    return 1;
  v4 = *(_QWORD *)(a2 + 16);
  if ( v4 )
  {
    v5 = SetupClnMoveFileToScratchReserve(v4, *(_QWORD *)(a1 + 40));
    if ( v5 < 0 )
    {
      LastError = GetLastError();
      v7 = CurrentIP();
      v8 = ConstructPartialMsgW(
             0x3000000u,
             "SetupClnEnumFileCallback Failed to move [%s] to scratch. status: %x",
             *(const char **)(a1 + 40),
             v5);
      WdsSetupLogMessageW(
        v8,
        0,
        L"D",
        0,
        1662,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnEnumFileCallback",
        v7,
        LastError,
        0,
        0);
    }
  }
  v9 = SetupClnEstimateFileSize(a2, *(_QWORD *)(a1 + 40), *(_QWORD *)(a1 + 32));
  SetupClnVisitFile(a2, *(_QWORD *)(a1 + 40), v9);
  return *(_DWORD *)(a2 + 28) == 0;
}

```

## disassembly

```asm
0x1800070b0  push    rbx
0x1800070b2  push    rbp
0x1800070b3  push    rsi
0x1800070b4  push    rdi
0x1800070b5  push    r14
0x1800070b7  sub     rsp, 60h
0x1800070bb  mov     rsi, rdx
0x1800070be  mov     rbp, rcx
0x1800070c1  test    rcx, rcx
0x1800070c4  jz      loc_180007191
0x1800070ca  test    rdx, rdx
0x1800070cd  jz      loc_180007191
0x1800070d3  mov     rcx, [rdx+10h]
0x1800070d7  test    rcx, rcx
0x1800070da  jz      loc_180007168
0x1800070e0  mov     rdx, [rbp+28h]
0x1800070e4  call    SetupClnMoveFileToScratchReserve
0x1800070e9  mov     r14d, eax
0x1800070ec  test    eax, eax
0x1800070ee  jns     short loc_180007168
0x1800070f0  call    cs:__imp_GetLastError
0x1800070f6  mov     edi, eax
0x1800070f8  call    cs:__imp_CurrentIP
0x1800070fe  mov     r8, [rbp+28h]
0x180007102  lea     rdx, aSetupclnenumfi; "SetupClnEnumFileCallback Failed to move"...
0x180007109  mov     r9d, r14d
0x18000710c  mov     ecx, 3000000h; unsigned int
0x180007111  mov     rbx, rax
0x180007114  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007119  mov     [rsp+88h+var_38], 0
0x180007121  lea     rcx, aSetupclnenumfi_0; "SetupClnEnumFileCallback"
0x180007128  mov     [rsp+88h+var_40], 0
0x180007131  lea     r8, aD; "D"
0x180007138  mov     [rsp+88h+var_48], edi
0x18000713c  xor     r9d, r9d
0x18000713f  mov     [rsp+88h+var_50], rbx
0x180007144  xor     edx, edx
0x180007146  mov     [rsp+88h+var_58], rcx
0x18000714b  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180007152  mov     [rsp+88h+var_60], rcx
0x180007157  mov     rcx, rax
0x18000715a  mov     [rsp+88h+var_68], 67Eh
0x180007162  call    cs:__imp_WdsSetupLogMessageW
0x180007168  mov     r8, [rbp+20h]
0x18000716c  mov     rcx, rsi
0x18000716f  mov     rdx, [rbp+28h]
0x180007173  call    SetupClnEstimateFileSize
0x180007178  mov     rdx, [rbp+28h]
0x18000717c  mov     r8, rax
0x18000717f  mov     rcx, rsi
0x180007182  call    SetupClnVisitFile
0x180007187  xor     eax, eax
0x180007189  cmp     [rsi+1Ch], eax
0x18000718c  setz    al
0x18000718f  jmp     short loc_180007196
0x180007191  mov     eax, 1
0x180007196  add     rsp, 60h
0x18000719a  pop     r14
0x18000719c  pop     rdi
0x18000719d  pop     rsi
0x18000719e  pop     rbp
0x18000719f  pop     rbx
0x1800071a0  retn
```

# SetupClnMoveFileToScratchReserve

- ea: `0x180007b68`
- end: `0x180007c3e`
- name: `SetupClnMoveFileToScratchReserve`
- size: `214`
- prototype: `__int64 __fastcall(__int64, const char *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x180006868`
- `0x180006f80`
- `0x1800070b0`

## callees

- `0x1800047ac`
- `0x180007b68`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007bb5`
- `WDSCORE!CurrentIP` at `0x180007bbd`
- `WDSCORE!CurrentIP` at `0x180007bbd`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007c26`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007c26`

## string_xrefs

- `0x180007be5`: `SetupClnMoveFileToScratchReserve`
- `0x180007bc6`: `SetupClnMoveFileToScratchReserve Failed to move [%s] to Scratch directory. status: %x`

## pseudocode

```c
__int64 __fastcall SetupClnMoveFileToScratchReserve(__int64 a1, const char *a2)
{
  __int64 v3; // rax
  int v4; // esi
  DWORD LastError; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax

  if ( !a1 )
    return 1;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  if ( !v3 )
    return 1;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, const char *))(*(_QWORD *)v3 + 88LL))(v3, 6, 6, a2);
  if ( v4 < 0 )
  {
    LastError = GetLastError();
    v6 = CurrentIP();
    v7 = ConstructPartialMsgW(
           0x3000000u,
           "SetupClnMoveFileToScratchReserve Failed to move [%s] to Scratch directory. status: %x",
           a2,
           v4);
    WdsSetupLogMessageW(
      v7,
      0,
      L"D",
      0,
      1391,
      L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
      L"SetupClnMoveFileToScratchReserve",
      v6,
      LastError,
      0,
      0);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007b68  push    rbx
0x180007b6a  push    rbp
0x180007b6b  push    rsi
0x180007b6c  push    rdi
0x180007b6d  sub     rsp, 68h
0x180007b71  mov     rbp, rdx
0x180007b74  test    rcx, rcx
0x180007b77  jz      loc_180007C30
0x180007b7d  mov     rax, [rcx]
0x180007b80  mov     rax, [rax+8]
0x180007b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b89  mov     r10, rax
0x180007b8c  test    rax, rax
0x180007b8f  jz      loc_180007C30
0x180007b95  mov     rcx, [rax]
0x180007b98  mov     edx, 6
0x180007b9d  mov     r9, rbp
0x180007ba0  mov     r8d, edx
0x180007ba3  mov     rax, [rcx+58h]
0x180007ba7  mov     rcx, r10
0x180007baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007baf  mov     esi, eax
0x180007bb1  test    eax, eax
0x180007bb3  jns     short loc_180007C2C
0x180007bb5  call    cs:__imp_GetLastError
0x180007bbb  mov     edi, eax
0x180007bbd  call    cs:__imp_CurrentIP
0x180007bc3  mov     r9d, esi
0x180007bc6  lea     rdx, aSetupclnmovefi_0; "SetupClnMoveFileToScratchReserve Failed"...
0x180007bcd  mov     r8, rbp
0x180007bd0  mov     ecx, 3000000h; unsigned int
0x180007bd5  mov     rbx, rax
0x180007bd8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007bdd  mov     [rsp+88h+var_38], 0
0x180007be5  lea     rcx, aSetupclnmovefi; "SetupClnMoveFileToScratchReserve"
0x180007bec  mov     [rsp+88h+var_40], 0
0x180007bf5  lea     r8, aD; "D"
0x180007bfc  mov     [rsp+88h+var_48], edi
0x180007c00  xor     r9d, r9d
0x180007c03  mov     [rsp+88h+var_50], rbx
0x180007c08  xor     edx, edx
0x180007c0a  mov     [rsp+88h+var_58], rcx
0x180007c0f  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180007c16  mov     [rsp+88h+var_60], rcx
0x180007c1b  mov     rcx, rax
0x180007c1e  mov     [rsp+88h+var_68], 56Fh
0x180007c26  call    cs:__imp_WdsSetupLogMessageW
0x180007c2c  mov     eax, esi
0x180007c2e  jmp     short loc_180007C35
0x180007c30  mov     eax, 1
0x180007c35  add     rsp, 68h
0x180007c39  pop     rdi
0x180007c3a  pop     rsi
0x180007c3b  pop     rbp
0x180007c3c  pop     rbx
0x180007c3d  retn
```

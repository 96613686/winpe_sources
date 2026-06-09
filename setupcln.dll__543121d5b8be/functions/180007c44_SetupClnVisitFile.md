# SetupClnVisitFile

- ea: `0x180007c44`
- end: `0x180007e2e`
- name: `SetupClnVisitFile`
- size: `490`
- prototype: `void __fastcall(__int64, const char *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, installer_update`

## callers

- `0x1800070b0`

## callees

- `0x180002fe8`
- `0x1800047ac`
- `0x180007c44`
- `0x18000aa40`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d74`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180007d5d`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180007d5d`
- `WDSCORE!CurrentIP` at `0x180007ce5`
- `WDSCORE!CurrentIP` at `0x180007d7c`
- `WDSCORE!CurrentIP` at `0x180007ce5`
- `WDSCORE!CurrentIP` at `0x180007d7c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007d4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007dd7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007d4e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180007dd7`

## string_xrefs

- `0x180007cee`: `SetupClnVisitFile - DeleteFileEx2 for file: %s failed with status: %x`
- `0x180007d85`: `SetupClnVisitFile - MoveFileEx for file: %s - status: %x `

## pseudocode

```c
void __fastcall SetupClnVisitFile(__int64 a1, const char *a2, __int64 a3)
{
  int v5; // eax
  int v6; // eax
  int v7; // ebp
  __int64 v8; // rcx
  int v9; // eax
  DWORD LastError; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  BOOL v13; // eax
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  __int64 v17; // rcx

  if ( a1 && a2 && *(_WORD *)a2 )
  {
    if ( !*(_DWORD *)a1 )
    {
      *(_QWORD *)(a1 + 40) += a3;
      v17 = *(_QWORD *)(a1 + 8);
      if ( !v17 )
        return;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 24LL))(
             v17,
             *(_QWORD *)(a1 + 40),
             0,
             0);
LABEL_14:
      v7 = v9;
      *(_DWORD *)(a1 + 28) = v9 == -2147467260;
      if ( v9 >= 0 )
        return;
      goto LABEL_15;
    }
    *(_QWORD *)(a1 + 48) += a3;
    v5 = DeleteFileEx2(a2, 32);
    v6 = HrBool(v5);
    v7 = v6;
    if ( v6 == -2147024891 || v6 == -2147024864 )
    {
      LastError = GetLastError();
      v11 = CurrentIP();
      v12 = ConstructPartialMsgW(
              0x3000000u,
              "SetupClnVisitFile - DeleteFileEx2 for file: %s failed with status: %x",
              a2,
              v7);
      WdsSetupLogMessageW(
        v12,
        0,
        L"D",
        0,
        1760,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnVisitFile",
        v11,
        LastError,
        0,
        0);
      v13 = MoveFileExW((LPCWSTR)a2, 0, 4u);
      v7 = HrBool(v13);
      if ( v7 >= 0 )
        goto LABEL_8;
      v14 = GetLastError();
      v15 = CurrentIP();
      v16 = ConstructPartialMsgW(0x2000000u, "SetupClnVisitFile - MoveFileEx for file: %s - status: %x ", a2, v7);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        1769,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnVisitFile",
        v15,
        v14,
        0,
        0);
    }
    else if ( v6 >= 0 )
    {
LABEL_8:
      v8 = *(_QWORD *)(a1 + 8);
      if ( !v8 )
        return;
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v8 + 32LL))(
             v8,
             *(_QWORD *)(a1 + 48),
             *(_QWORD *)(a1 + 56),
             0,
             0);
      goto LABEL_14;
    }
LABEL_15:
    if ( *(int *)(a1 + 24) >= 0 )
      *(_DWORD *)(a1 + 24) = v7;
  }
}

```

## disassembly

```asm
0x180007c44  test    rcx, rcx
0x180007c47  jz      locret_180007E2D
0x180007c4d  push    rbx
0x180007c4e  push    rbp
0x180007c4f  push    rsi
0x180007c50  push    rdi
0x180007c51  push    r12
0x180007c53  push    r13
0x180007c55  push    r14
0x180007c57  sub     rsp, 60h
0x180007c5b  mov     r14, rdx
0x180007c5e  mov     rsi, rcx
0x180007c61  test    rdx, rdx
0x180007c64  jz      loc_180007E1F
0x180007c6a  xor     eax, eax
0x180007c6c  cmp     ax, [rdx]
0x180007c6f  jz      loc_180007E1F
0x180007c75  cmp     [rcx], eax
0x180007c77  jz      loc_180007DDF
0x180007c7d  add     [rcx+30h], r8
0x180007c81  lea     edx, [rax+20h]
0x180007c84  mov     rcx, r14
0x180007c87  call    DeleteFileEx2
0x180007c8c  mov     ecx, eax; int
0x180007c8e  call    ?HrBool@@YAJH@Z; HrBool(int)
0x180007c93  mov     ebp, eax
0x180007c95  cmp     eax, 80070005h
0x180007c9a  jz      short loc_180007CDD
0x180007c9c  cmp     eax, 80070020h
0x180007ca1  jz      short loc_180007CDD
0x180007ca3  test    eax, eax
0x180007ca5  js      loc_180007E16
0x180007cab  mov     rcx, [rsi+8]
0x180007caf  test    rcx, rcx
0x180007cb2  jz      loc_180007E1F
0x180007cb8  mov     rax, [rcx]
0x180007cbb  xor     r9d, r9d
0x180007cbe  mov     r8, [rsi+38h]
0x180007cc2  mov     rdx, [rsi+30h]
0x180007cc6  mov     [rsp+98h+var_78], 0
0x180007ccf  mov     rax, [rax+20h]
0x180007cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cd8  jmp     loc_180007E02
0x180007cdd  call    cs:__imp_GetLastError
0x180007ce3  mov     edi, eax
0x180007ce5  call    cs:__imp_CurrentIP
0x180007ceb  mov     r9d, ebp
0x180007cee  lea     rdx, aSetupclnvisitf_0; "SetupClnVisitFile - DeleteFileEx2 for f"...
0x180007cf5  mov     r8, r14
0x180007cf8  mov     ecx, 3000000h; unsigned int
0x180007cfd  mov     rbx, rax
0x180007d00  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007d05  mov     [rsp+98h+var_48], 0
0x180007d0d  lea     r12, aSetupclnvisitf; "SetupClnVisitFile"
0x180007d14  mov     [rsp+98h+var_50], 0
0x180007d1d  lea     r13, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180007d24  mov     [rsp+98h+var_58], edi
0x180007d28  lea     r8, aD; "D"
0x180007d2f  mov     [rsp+98h+var_60], rbx
0x180007d34  xor     r9d, r9d
0x180007d37  mov     [rsp+98h+var_68], r12
0x180007d3c  xor     edx, edx
0x180007d3e  mov     [rsp+98h+var_70], r13
0x180007d43  mov     rcx, rax
0x180007d46  mov     dword ptr [rsp+98h+var_78], 6E0h
0x180007d4e  call    cs:__imp_WdsSetupLogMessageW
0x180007d54  xor     edx, edx; lpNewFileName
0x180007d56  mov     rcx, r14; lpExistingFileName
0x180007d59  lea     r8d, [rdx+4]; dwFlags
0x180007d5d  call    cs:__imp_MoveFileExW
0x180007d63  mov     ecx, eax; int
0x180007d65  call    ?HrBool@@YAJH@Z; HrBool(int)
0x180007d6a  mov     ebp, eax
0x180007d6c  test    eax, eax
0x180007d6e  jns     loc_180007CAB
0x180007d74  call    cs:__imp_GetLastError
0x180007d7a  mov     edi, eax
0x180007d7c  call    cs:__imp_CurrentIP
0x180007d82  mov     r9d, ebp
0x180007d85  lea     rdx, aSetupclnvisitf_1; "SetupClnVisitFile - MoveFileEx for file"...
0x180007d8c  mov     r8, r14
0x180007d8f  mov     ecx, 2000000h; unsigned int
0x180007d94  mov     rbx, rax
0x180007d97  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180007d9c  mov     [rsp+98h+var_48], 0
0x180007da4  lea     r8, aD; "D"
0x180007dab  mov     [rsp+98h+var_50], 0
0x180007db4  xor     r9d, r9d
0x180007db7  mov     [rsp+98h+var_58], edi
0x180007dbb  xor     edx, edx
0x180007dbd  mov     [rsp+98h+var_60], rbx
0x180007dc2  mov     rcx, rax
0x180007dc5  mov     [rsp+98h+var_68], r12
0x180007dca  mov     [rsp+98h+var_70], r13
0x180007dcf  mov     dword ptr [rsp+98h+var_78], 6E9h
0x180007dd7  call    cs:__imp_WdsSetupLogMessageW
0x180007ddd  jmp     short loc_180007E16
0x180007ddf  add     [rcx+28h], r8
0x180007de3  mov     rcx, [rcx+8]
0x180007de7  test    rcx, rcx
0x180007dea  jz      short loc_180007E1F
0x180007dec  mov     rax, [rcx]
0x180007def  xor     r9d, r9d
0x180007df2  mov     rdx, [rsi+28h]
0x180007df6  xor     r8d, r8d
0x180007df9  mov     rax, [rax+18h]
0x180007dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e02  mov     ebp, eax
0x180007e04  xor     eax, eax
0x180007e06  cmp     ebp, 80004004h
0x180007e0c  setz    al
0x180007e0f  mov     [rsi+1Ch], eax
0x180007e12  test    ebp, ebp
0x180007e14  jns     short loc_180007E1F
0x180007e16  cmp     dword ptr [rsi+18h], 0
0x180007e1a  jl      short loc_180007E1F
0x180007e1c  mov     [rsi+18h], ebp
0x180007e1f  add     rsp, 60h
0x180007e23  pop     r14
0x180007e25  pop     r13
0x180007e27  pop     r12
0x180007e29  pop     rdi
0x180007e2a  pop     rsi
0x180007e2b  pop     rbp
0x180007e2c  pop     rbx
0x180007e2d  retn
```

# SetupClnDeleteResetLogs

- ea: `0x180006518`
- end: `0x180006860`
- name: `SetupClnDeleteResetLogs`
- size: `840`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800040c0`

## callees

- `0x1800047ac`
- `0x180006518`
- `0x180006868`
- `0x18000a780`
- `0x18000b044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000656b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000673a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000656b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006625`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800066b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000673a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ba`
- `WDSCORE!CurrentIP` at `0x180006573`
- `WDSCORE!CurrentIP` at `0x1800065d0`
- `WDSCORE!CurrentIP` at `0x18000662d`
- `WDSCORE!CurrentIP` at `0x1800066bc`
- `WDSCORE!CurrentIP` at `0x180006742`
- `WDSCORE!CurrentIP` at `0x1800067e7`
- `WDSCORE!CurrentIP` at `0x180006573`
- `WDSCORE!CurrentIP` at `0x1800065d0`
- `WDSCORE!CurrentIP` at `0x18000662d`
- `WDSCORE!CurrentIP` at `0x1800066bc`
- `WDSCORE!CurrentIP` at `0x180006742`
- `WDSCORE!CurrentIP` at `0x1800067e7`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000668c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006725`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800067a1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006846`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000668c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006725`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800067a1`
- `WDSCORE!WdsSetupLogMessageW` at `0x180006846`

## string_xrefs

- `0x180006595`: `SetupClnDeleteResetLogs`
- `0x1800065f2`: `SetupClnDeleteResetLogs`
- `0x18000664f`: `SetupClnDeleteResetLogs`
- `0x1800066e4`: `SetupClnDeleteResetLogs`
- `0x180006764`: `SetupClnDeleteResetLogs`
- `0x180006809`: `SetupClnDeleteResetLogs`
- `0x18000657c`: `SetupClnDeleteResetLogs - Was able to find %s.`
- `0x1800065d9`: `SetupClnDeleteResetLogs - Initialize phase was unable to find %s.`
- `0x180006636`: `SetupClnDeleteResetLogs - Iterating on: %s`
- `0x1800066c5`: `SetupClnDeleteResetLogs - Failed enumerating directory %s. Error: 0x%08X`
- `0x18000674b`: `SetupClnDeleteResetLogs - Directory %s doesn't exist, skipping...`
- `0x1800067f0`: `SetupClnDeleteResetLogs - Return status: %x`

## pseudocode

```c
__int64 __fastcall SetupClnDeleteResetLogs(__int64 a1)
{
  int v2; // r12d
  int v3; // r13d
  unsigned __int64 i; // r15
  wchar_t *v5; // rax
  char *v6; // rsi
  DWORD LastError; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  int v16; // r14d
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  HANDLE ProcessHeap; // rax
  int *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax

  v2 = 0;
  v3 = 0;
  for ( i = 0; i < 3; ++i )
  {
    v5 = BuildPath(*(STRSAFE_PCNZWCH *)(a1 + 24), off_180015DA0[i]);
    v6 = (char *)v5;
    if ( *(_DWORD *)(a1 + 4) )
    {
      if ( (unsigned int)DirectoryExists(v5) )
      {
        v3 = 1;
        LastError = GetLastError();
        v8 = CurrentIP();
        v9 = ConstructPartialMsgW(0x4000000, "SetupClnDeleteResetLogs - Was able to find %s.", v6);
        WdsSetupLogMessageW(
          v9,
          0,
          L"D",
          0,
          1832,
          L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
          L"SetupClnDeleteResetLogs",
          v8,
          LastError,
          0,
          0);
      }
      else
      {
        v10 = GetLastError();
        v11 = CurrentIP();
        v12 = ConstructPartialMsgW(0x4000000, "SetupClnDeleteResetLogs - Initialize phase was unable to find %s.", v6);
        WdsSetupLogMessageW(
          v12,
          0,
          L"D",
          0,
          1836,
          L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
          L"SetupClnDeleteResetLogs",
          v11,
          v10,
          0,
          0);
      }
    }
    else
    {
      v13 = GetLastError();
      v14 = CurrentIP();
      v15 = ConstructPartialMsgW(0x4000000, "SetupClnDeleteResetLogs - Iterating on: %s", v6);
      WdsSetupLogMessageW(
        v15,
        0,
        L"D",
        0,
        1843,
        L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
        L"SetupClnDeleteResetLogs",
        v14,
        v13,
        0,
        0);
      if ( (unsigned int)DirectoryExists((const wchar_t *)v6) )
      {
        v16 = SetupClnEnum((int *)a1, v6);
        if ( v16 < 0 )
        {
          v17 = GetLastError();
          v18 = CurrentIP();
          v19 = ConstructPartialMsgW(
                  0x2000000,
                  "SetupClnDeleteResetLogs - Failed enumerating directory %s. Error: 0x%08X",
                  v6,
                  v16);
          WdsSetupLogMessageW(
            v19,
            0,
            L"D",
            0,
            1850,
            L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
            L"SetupClnDeleteResetLogs",
            v18,
            v17,
            0,
            0);
        }
        if ( v2 < 0 )
          v16 = v2;
        v2 = v16;
      }
      else
      {
        v20 = GetLastError();
        v21 = CurrentIP();
        v22 = ConstructPartialMsgW(0x4000000, "SetupClnDeleteResetLogs - Directory %s doesn't exist, skipping...", v6);
        WdsSetupLogMessageW(
          v22,
          0,
          L"D",
          0,
          1856,
          L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
          L"SetupClnDeleteResetLogs",
          v21,
          v20,
          0,
          0);
      }
    }
    if ( v6 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v6);
    }
  }
  v24 = *(int **)(a1 + 8);
  if ( v24 && *(_DWORD *)(a1 + 4) )
    *v24 = v3;
  v25 = GetLastError();
  v26 = CurrentIP();
  v27 = ConstructPartialMsgW(0x4000000, "SetupClnDeleteResetLogs - Return status: %x", v2);
  WdsSetupLogMessageW(
    v27,
    0,
    L"D",
    0,
    1870,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"SetupClnDeleteResetLogs",
    v26,
    v25,
    0,
    0);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180006518  push    rbx
0x18000651a  push    rbp
0x18000651b  push    rsi
0x18000651c  push    rdi
0x18000651d  push    r12
0x18000651f  push    r13
0x180006521  push    r14
0x180006523  push    r15
0x180006525  sub     rsp, 68h
0x180006529  xor     r14d, r14d
0x18000652c  mov     rbp, rcx
0x18000652f  mov     r12d, r14d
0x180006532  mov     r13d, r14d
0x180006535  mov     r15d, r14d
0x180006538  mov     rcx, [rbp+18h]; pszSrc
0x18000653c  lea     rdx, off_180015DA0; "Windows\\Logs\\PBR"
0x180006543  mov     rdx, [rdx+r15*8]; STRSAFE_PCNZWCH
0x180006547  call    BuildPath
0x18000654c  mov     rsi, rax
0x18000654f  cmp     [rbp+4], r14d
0x180006553  jz      loc_180006625
0x180006559  mov     rcx, rax
0x18000655c  call    DirectoryExists
0x180006561  test    eax, eax
0x180006563  jz      short loc_1800065C8
0x180006565  mov     r13d, 1
0x18000656b  call    cs:__imp_GetLastError
0x180006571  mov     edi, eax
0x180006573  call    cs:__imp_CurrentIP
0x180006579  mov     r8, rsi
0x18000657c  lea     rdx, aSetupclndelete_5; "SetupClnDeleteResetLogs - Was able to f"...
0x180006583  mov     ecx, 4000000h; unsigned int
0x180006588  mov     rbx, rax
0x18000658b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006590  mov     [rsp+0A8h+var_58], r14d
0x180006595  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x18000659c  mov     [rsp+0A8h+var_60], r14
0x1800065a1  mov     [rsp+0A8h+var_68], edi
0x1800065a5  mov     [rsp+0A8h+var_70], rbx
0x1800065aa  mov     [rsp+0A8h+var_78], rcx
0x1800065af  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x1800065b6  mov     [rsp+0A8h+var_80], rcx
0x1800065bb  mov     [rsp+0A8h+var_88], 728h
0x1800065c3  jmp     loc_180006792
0x1800065c8  call    cs:__imp_GetLastError
0x1800065ce  mov     edi, eax
0x1800065d0  call    cs:__imp_CurrentIP
0x1800065d6  mov     r8, rsi
0x1800065d9  lea     rdx, aSetupclndelete_4; "SetupClnDeleteResetLogs - Initialize ph"...
0x1800065e0  mov     ecx, 4000000h; unsigned int
0x1800065e5  mov     rbx, rax
0x1800065e8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800065ed  mov     [rsp+0A8h+var_58], r14d
0x1800065f2  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x1800065f9  mov     [rsp+0A8h+var_60], r14
0x1800065fe  mov     [rsp+0A8h+var_68], edi
0x180006602  mov     [rsp+0A8h+var_70], rbx
0x180006607  mov     [rsp+0A8h+var_78], rcx
0x18000660c  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006613  mov     [rsp+0A8h+var_80], rcx
0x180006618  mov     [rsp+0A8h+var_88], 72Ch
0x180006620  jmp     loc_180006792
0x180006625  call    cs:__imp_GetLastError
0x18000662b  mov     edi, eax
0x18000662d  call    cs:__imp_CurrentIP
0x180006633  mov     r8, rsi
0x180006636  lea     rdx, aSetupclndelete_2; "SetupClnDeleteResetLogs - Iterating on:"...
0x18000663d  mov     ecx, 4000000h; unsigned int
0x180006642  mov     rbx, rax
0x180006645  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000664a  mov     [rsp+0A8h+var_58], r14d
0x18000664f  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x180006656  mov     [rsp+0A8h+var_60], r14
0x18000665b  lea     r8, aD; "D"
0x180006662  mov     [rsp+0A8h+var_68], edi
0x180006666  xor     r9d, r9d
0x180006669  mov     [rsp+0A8h+var_70], rbx
0x18000666e  xor     edx, edx
0x180006670  mov     [rsp+0A8h+var_78], rcx
0x180006675  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x18000667c  mov     [rsp+0A8h+var_80], rcx
0x180006681  mov     rcx, rax
0x180006684  mov     [rsp+0A8h+var_88], 733h
0x18000668c  call    cs:__imp_WdsSetupLogMessageW
0x180006692  mov     rcx, rsi
0x180006695  call    DirectoryExists
0x18000669a  test    eax, eax
0x18000669c  jz      loc_18000673A
0x1800066a2  mov     rdx, rsi
0x1800066a5  mov     rcx, rbp
0x1800066a8  call    SetupClnEnum
0x1800066ad  mov     r14d, eax
0x1800066b0  test    eax, eax
0x1800066b2  jns     short loc_18000672B
0x1800066b4  call    cs:__imp_GetLastError
0x1800066ba  mov     edi, eax
0x1800066bc  call    cs:__imp_CurrentIP
0x1800066c2  mov     r9d, r14d
0x1800066c5  lea     rdx, aSetupclndelete_3; "SetupClnDeleteResetLogs - Failed enumer"...
0x1800066cc  mov     r8, rsi
0x1800066cf  mov     ecx, 2000000h; unsigned int
0x1800066d4  mov     rbx, rax
0x1800066d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800066dc  mov     [rsp+0A8h+var_58], 0
0x1800066e4  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x1800066eb  mov     [rsp+0A8h+var_60], 0
0x1800066f4  lea     r8, aD; "D"
0x1800066fb  mov     [rsp+0A8h+var_68], edi
0x1800066ff  xor     r9d, r9d
0x180006702  mov     [rsp+0A8h+var_70], rbx
0x180006707  xor     edx, edx
0x180006709  mov     [rsp+0A8h+var_78], rcx
0x18000670e  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006715  mov     [rsp+0A8h+var_80], rcx
0x18000671a  mov     rcx, rax
0x18000671d  mov     [rsp+0A8h+var_88], 73Ah
0x180006725  call    cs:__imp_WdsSetupLogMessageW
0x18000672b  test    r12d, r12d
0x18000672e  cmovs   r14d, r12d
0x180006732  mov     r12d, r14d
0x180006735  xor     r14d, r14d
0x180006738  jmp     short loc_1800067A7
0x18000673a  call    cs:__imp_GetLastError
0x180006740  mov     edi, eax
0x180006742  call    cs:__imp_CurrentIP
0x180006748  mov     r8, rsi
0x18000674b  lea     rdx, aSetupclndelete_0; "SetupClnDeleteResetLogs - Directory %s "...
0x180006752  mov     ecx, 4000000h; unsigned int
0x180006757  mov     rbx, rax
0x18000675a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000675f  mov     [rsp+0A8h+var_58], r14d
0x180006764  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x18000676b  mov     [rsp+0A8h+var_60], r14
0x180006770  mov     [rsp+0A8h+var_68], edi
0x180006774  mov     [rsp+0A8h+var_70], rbx
0x180006779  mov     [rsp+0A8h+var_78], rcx
0x18000677e  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006785  mov     [rsp+0A8h+var_80], rcx
0x18000678a  mov     [rsp+0A8h+var_88], 740h
0x180006792  xor     r9d, r9d
0x180006795  lea     r8, aD; "D"
0x18000679c  xor     edx, edx
0x18000679e  mov     rcx, rax
0x1800067a1  call    cs:__imp_WdsSetupLogMessageW
0x1800067a7  test    rsi, rsi
0x1800067aa  jz      short loc_1800067C0
0x1800067ac  call    cs:__imp_GetProcessHeap
0x1800067b2  mov     r8, rsi; lpMem
0x1800067b5  xor     edx, edx; dwFlags
0x1800067b7  mov     rcx, rax; hHeap
0x1800067ba  call    cs:__imp_HeapFree
0x1800067c0  inc     r15
0x1800067c3  cmp     r15, 3
0x1800067c7  jb      loc_180006538
0x1800067cd  mov     rax, [rbp+8]
0x1800067d1  test    rax, rax
0x1800067d4  jz      short loc_1800067DF
0x1800067d6  cmp     [rbp+4], r14d
0x1800067da  jz      short loc_1800067DF
0x1800067dc  mov     [rax], r13d
0x1800067df  call    cs:__imp_GetLastError
0x1800067e5  mov     edi, eax
0x1800067e7  call    cs:__imp_CurrentIP
0x1800067ed  mov     r8d, r12d
0x1800067f0  lea     rdx, aSetupclndelete; "SetupClnDeleteResetLogs - Return status"...
0x1800067f7  mov     ecx, 4000000h; unsigned int
0x1800067fc  mov     rbx, rax
0x1800067ff  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180006804  mov     [rsp+0A8h+var_58], r14d
0x180006809  lea     rcx, aSetupclndelete_1; "SetupClnDeleteResetLogs"
0x180006810  mov     [rsp+0A8h+var_60], r14
0x180006815  lea     r8, aD; "D"
0x18000681c  mov     [rsp+0A8h+var_68], edi
0x180006820  xor     r9d, r9d
0x180006823  mov     [rsp+0A8h+var_70], rbx
0x180006828  xor     edx, edx
0x18000682a  mov     [rsp+0A8h+var_78], rcx
0x18000682f  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180006836  mov     [rsp+0A8h+var_80], rcx
0x18000683b  mov     rcx, rax
0x18000683e  mov     [rsp+0A8h+var_88], 74Eh
0x180006846  call    cs:__imp_WdsSetupLogMessageW
0x18000684c  mov     eax, r12d
0x18000684f  add     rsp, 68h
0x180006853  pop     r15
0x180006855  pop     r14
0x180006857  pop     r13
0x180006859  pop     r12
0x18000685b  pop     rdi
0x18000685c  pop     rsi
0x18000685d  pop     rbp
0x18000685e  pop     rbx
0x18000685f  retn
```

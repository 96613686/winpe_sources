# CSetupFilesCleanup::Deactivate(ulong *)

- ea: `0x1800049a0`
- end: `0x180004a4b`
- name: `?Deactivate@CSetupFilesCleanup@@UEAAJPEAK@Z`
- size: `171`
- prototype: `__int64 __fastcall(const char **this, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x1800047ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049b2`
- `WDSCORE!CurrentIP` at `0x1800049ba`
- `WDSCORE!CurrentIP` at `0x1800049ba`
- `WDSCORE!WdsTerminate` at `0x180004a33`
- `WDSCORE!WdsTerminate` at `0x180004a33`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004a1f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004a1f`

## string_xrefs

- `0x1800049c4`: `CSetupFilesCleanup::Deactivate - session deactivated for Plugin:%s, Client Process:%s`

## pseudocode

```c
__int64 __fastcall CSetupFilesCleanup::Deactivate(const char **this, unsigned int *a2)
{
  DWORD LastError; // esi
  __int64 v4; // rdi
  struct tagLOG_PARTIAL_MSG *v5; // rax

  LastError = GetLastError();
  v4 = CurrentIP();
  v5 = ConstructPartialMsgW(
         0x4000000u,
         "CSetupFilesCleanup::Deactivate - session deactivated for Plugin:%s, Client Process:%s",
         this[9],
         this[8]);
  WdsSetupLogMessageW(
    v5,
    0,
    L"D",
    0,
    756,
    L"base\\ntsetup\\setup\\tools\\setupcln\\setupcln.cpp",
    L"CSetupFilesCleanup::Deactivate",
    v4,
    LastError,
    0,
    0);
  g_WdsLibLog = 0;
  g_WdsNativeLibLog = 0;
  WdsTerminate();
  return 0;
}

```

## disassembly

```asm
0x1800049a0  mov     [rsp+arg_0], rbx
0x1800049a5  mov     [rsp+arg_8], rsi
0x1800049aa  push    rdi
0x1800049ab  sub     rsp, 60h
0x1800049af  mov     rbx, rcx
0x1800049b2  call    cs:__imp_GetLastError
0x1800049b8  mov     esi, eax
0x1800049ba  call    cs:__imp_CurrentIP
0x1800049c0  mov     r9, [rbx+40h]
0x1800049c4  lea     rdx, aCsetupfilescle_5; "CSetupFilesCleanup::Deactivate - sessio"...
0x1800049cb  mov     r8, [rbx+48h]
0x1800049cf  mov     ecx, 4000000h; unsigned int
0x1800049d4  mov     rdi, rax
0x1800049d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800049dc  xor     ebx, ebx
0x1800049de  lea     rcx, aCsetupfilescle_8; "CSetupFilesCleanup::Deactivate"
0x1800049e5  mov     [rsp+68h+var_18], ebx
0x1800049e9  lea     r8, aD; "D"
0x1800049f0  mov     [rsp+68h+var_20], rbx
0x1800049f5  xor     r9d, r9d
0x1800049f8  mov     [rsp+68h+var_28], esi
0x1800049fc  xor     edx, edx
0x1800049fe  mov     [rsp+68h+var_30], rdi
0x180004a03  mov     [rsp+68h+var_38], rcx
0x180004a08  lea     rcx, aBaseNtsetupSet; "base\\ntsetup\\setup\\tools\\setupcln\\"...
0x180004a0f  mov     [rsp+68h+var_40], rcx
0x180004a14  mov     rcx, rax
0x180004a17  mov     [rsp+68h+var_48], 2F4h
0x180004a1f  call    cs:__imp_WdsSetupLogMessageW
0x180004a25  mov     cs:g_WdsLibLog, rbx
0x180004a2c  mov     cs:g_WdsNativeLibLog, rbx
0x180004a33  call    cs:__imp_WdsTerminate
0x180004a39  mov     rbx, [rsp+68h+arg_0]
0x180004a3e  xor     eax, eax
0x180004a40  mov     rsi, [rsp+68h+arg_8]
0x180004a45  add     rsp, 60h
0x180004a49  pop     rdi
0x180004a4a  retn
```

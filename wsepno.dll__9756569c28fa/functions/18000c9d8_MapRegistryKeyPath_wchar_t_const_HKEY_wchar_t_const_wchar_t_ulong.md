# MapRegistryKeyPath(wchar_t const *,HKEY__ *,wchar_t const *,wchar_t *,ulong)

- ea: `0x18000c9d8`
- end: `0x18000caa2`
- name: `?MapRegistryKeyPath@@YA_NPEB_WPEAUHKEY__@@0PEA_WK@Z`
- size: `202`
- prototype: `bool __fastcall(const wchar_t *, HKEY, const wchar_t *, wchar_t *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800068e0`
- `0x18000ccac`
- `0x18000cd50`
- `0x18000cde4`

## callees

- `0x18000c9d8`
- `0x18000caa8`
- `0x18000d590`
- `0x18000d794`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ca68`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000ca68`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c9ff`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000c9ff`

## pseudocode

```c
bool __fastcall MapRegistryKeyPath(const wchar_t *a1, HKEY a2, const wchar_t *a3, wchar_t *a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  unsigned int v8; // r9d

  if ( a2 != HKEY_LOCAL_MACHINE || !a3 || !(unsigned __int8)RtlIsStateSeparationEnabled(a1) )
    return 0;
  v6 = 0;
  while ( 1 )
  {
    v7 = v6;
    if ( !wcscmp_0(off_180015170[69 * v6], L"WSearch") )
      break;
    if ( ++v6 >= 2 )
    {
      v7 = 2;
      goto LABEL_9;
    }
  }
  if ( v6 < 2uLL )
    return InitOnceExecuteOnce(
             (PINIT_ONCE)&qword_180015BC8[v7],
             lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_,
             (PVOID)v7,
             0)
        && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
             (CSearchRegistryRedirectHelper *)&qword_180015188[69 * v7],
             a3,
             a4,
             v8) >= 0;
LABEL_9:
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return InitOnceExecuteOnce(
           (PINIT_ONCE)&qword_180015BC8[v7],
           lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_,
           (PVOID)v7,
           0)
      && CSearchRegistryRedirectHelper::MapRegistryKeyPath(
           (CSearchRegistryRedirectHelper *)&qword_180015188[69 * v7],
           a3,
           a4,
           v8) >= 0;
}

```

## disassembly

```asm
0x18000c9d8  push    rbx
0x18000c9da  push    rbp
0x18000c9db  push    rsi
0x18000c9dc  push    rdi
0x18000c9dd  push    r14
0x18000c9df  sub     rsp, 20h
0x18000c9e3  mov     rbp, r9
0x18000c9e6  mov     rsi, r8
0x18000c9e9  cmp     rdx, 0FFFFFFFF80000002h
0x18000c9f0  jnz     loc_18000CA95
0x18000c9f6  test    r8, r8
0x18000c9f9  jz      loc_18000CA95
0x18000c9ff  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000ca05  test    al, al
0x18000ca07  jz      loc_18000CA95
0x18000ca0d  xor     ebx, ebx
0x18000ca0f  lea     r14, cs:180000000h
0x18000ca16  mov     edi, ebx
0x18000ca18  lea     rdx, aWsearch; "WSearch"
0x18000ca1f  imul    rcx, rdi, 228h
0x18000ca26  mov     rcx, [rcx+r14+15170h]; String1
0x18000ca2e  call    wcscmp_0
0x18000ca33  test    eax, eax
0x18000ca35  jz      short loc_18000CA45
0x18000ca37  inc     ebx
0x18000ca39  cmp     ebx, 2
0x18000ca3c  jb      short loc_18000CA16
0x18000ca3e  mov     edi, 2
0x18000ca43  jmp     short loc_18000CA4B
0x18000ca45  cmp     rdi, 2
0x18000ca49  jb      short loc_18000CA50
0x18000ca4b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000ca50  lea     rcx, rva qword_180015BC8[r14]
0x18000ca57  xor     r9d, r9d; Context
0x18000ca5a  lea     rcx, [rcx+rdi*8]; InitOnce
0x18000ca5e  mov     r8, rdi; Parameter
0x18000ca61  lea     rdx, _lambda_cd2099a84e29dd60a3ce15c92771ff9c____lambda_invoker_cdecl_; InitFn
0x18000ca68  call    cs:__imp_InitOnceExecuteOnce
0x18000ca6e  test    eax, eax
0x18000ca70  jz      short loc_18000CA95
0x18000ca72  lea     rax, qword_180015188
0x18000ca79  mov     r8, rbp; wchar_t *
0x18000ca7c  imul    rcx, rdi, 228h
0x18000ca83  mov     rdx, rsi; wchar_t *
0x18000ca86  add     rcx, rax; this
0x18000ca89  call    ?MapRegistryKeyPath@CSearchRegistryRedirectHelper@@QEAAJPEB_WPEA_WK@Z; CSearchRegistryRedirectHelper::MapRegistryKeyPath(wchar_t const *,wchar_t *,ulong)
0x18000ca8e  test    eax, eax
0x18000ca90  setns   al
0x18000ca93  jmp     short loc_18000CA97
0x18000ca95  xor     al, al
0x18000ca97  add     rsp, 20h
0x18000ca9b  pop     r14
0x18000ca9d  pop     rdi
0x18000ca9e  pop     rsi
0x18000ca9f  pop     rbp
0x18000caa0  pop     rbx
0x18000caa1  retn
```

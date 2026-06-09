# SrvNetRefreshParameters

- ea: `0x140056834`
- end: `0x1400568f7`
- name: `SrvNetRefreshParameters`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400564f0`

## callees

- `0x14002a4c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x1400568d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056898`
- `ntoskrnl!RtlInitUnicodeString` at `0x140056898`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400568a8`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400568a8`

## string_xrefs

- `0x140056858`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 SrvNetRefreshParameters()
{
  PVOID SystemRoutineAddress; // rax
  unsigned int v1; // ecx
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-29h] BYREF
  __int64 (__fastcall *v4)(wchar_t *); // [rsp+40h] [rbp-19h] BYREF
  int v5; // [rsp+48h] [rbp-11h]
  __int128 v6; // [rsp+50h] [rbp-9h]
  int v7; // [rsp+60h] [rbp+7h]
  __int64 v8; // [rsp+68h] [rbp+Fh]
  int v9; // [rsp+70h] [rbp+17h]
  __int64 v10; // [rsp+78h] [rbp+1Fh]
  int v11; // [rsp+80h] [rbp+27h]
  __int64 v12; // [rsp+88h] [rbp+2Fh]

  v5 = 16;
  v6 = 0;
  v4 = SrvNetSetRegistryParameter;
  v7 = 0;
  DestinationString = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v1 = ((__int64 (__fastcall *)(__int64, const wchar_t *, __int64 (__fastcall **)(wchar_t *), _QWORD, _QWORD))SystemRoutineAddress)(
         2147483649LL,
         L"SrvNet\\Parameters",
         &v4,
         0,
         0);
  result = 0;
  if ( v1 != -1073741772 )
    return v1;
  return result;
}

```

## disassembly

```asm
0x140056834  push    rbp
0x140056836  lea     rbp, [rsp-57h]
0x14005683b  sub     rsp, 0B0h
0x140056842  xorps   xmm0, xmm0
0x140056845  mov     [rbp+57h+var_68], 10h
0x14005684c  lea     rax, SrvNetSetRegistryParameter
0x140056853  movdqa  [rbp+57h+var_60], xmm0
0x140056858  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14005685f  mov     [rbp+57h+var_70], rax
0x140056863  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140056867  mov     [rbp+57h+var_50], 0
0x14005686e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140056872  mov     [rbp+57h+var_48], 0
0x14005687a  mov     [rbp+57h+var_40], 0
0x140056881  mov     [rbp+57h+var_38], 0
0x140056889  mov     [rbp+57h+var_30], 0
0x140056890  mov     [rbp+57h+var_28], 0
0x140056898  call    cs:__imp_RtlInitUnicodeString
0x14005689f  nop     dword ptr [rax+rax+00h]
0x1400568a4  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400568a8  call    cs:__imp_MmGetSystemRoutineAddress
0x1400568af  nop     dword ptr [rax+rax+00h]
0x1400568b4  lea     r8, [rbp+57h+var_70]
0x1400568b8  mov     [rsp+0B0h+var_90], 0
0x1400568c1  test    rax, rax
0x1400568c4  lea     rdx, aSrvnetParamete; "SrvNet\\Parameters"
0x1400568cb  mov     ecx, 80000001h
0x1400568d0  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400568d8  xor     r9d, r9d
0x1400568db  call    _guard_dispatch_icall
0x1400568e0  mov     ecx, eax
0x1400568e2  xor     eax, eax
0x1400568e4  cmp     ecx, 0C0000034h
0x1400568ea  cmovnz  eax, ecx
0x1400568ed  add     rsp, 0B0h
0x1400568f4  pop     rbp
0x1400568f5  retn
```

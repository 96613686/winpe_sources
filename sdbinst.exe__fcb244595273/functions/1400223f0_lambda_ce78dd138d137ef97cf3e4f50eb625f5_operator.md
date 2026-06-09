# _lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()

- ea: `0x1400223f0`
- end: `0x14002245c`
- name: `_lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()`
- size: `108`
- prototype: `__int64 __fastcall(HKEY **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140024958`

## callees

- `0x14001008c`
- `0x1400223f0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140022422`
- `ADVAPI32!RegOpenKeyExW` at `0x140022422`

## string_xrefs

- `0x14002242e`: `Failed to open the SdbUpdates key (%d)`
- `0x140022414`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`

## pseudocode

```c
__int64 __fastcall lambda_ce78dd138d137ef97cf3e4f50eb625f5_::operator()(HKEY **a1)
{
  HKEY *phkResult; // rax
  LSTATUS v2; // eax
  unsigned int v3; // ebx

  phkResult = *a1;
  if ( **a1 )
    return 0;
  *phkResult = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
         0,
         0x2001Fu,
         phkResult);
  v3 = v2;
  if ( !v2 )
    return 0;
  AslLogCallPrintf(
    1,
    "MergeSdb_FindAndMergeForTarget::<lambda_ce78dd138d137ef97cf3e4f50eb625f5>::operator ()",
    1923,
    "Failed to open the SdbUpdates key (%d)",
    v2);
  return v3;
}

```

## disassembly

```asm
0x1400223f0  push    rbx
0x1400223f2  sub     rsp, 30h
0x1400223f6  mov     rax, [rcx]
0x1400223f9  cmp     qword ptr [rax], 0
0x1400223fd  jnz     short loc_140022454
0x1400223ff  mov     r9d, 2001Fh; samDesired
0x140022405  mov     qword ptr [rax], 0
0x14002240c  xor     r8d, r8d; ulOptions
0x14002240f  mov     [rsp+38h+phkResult], rax; phkResult
0x140022414  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14002241b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140022422  call    cs:__imp_RegOpenKeyExW
0x140022428  mov     ebx, eax
0x14002242a  test    eax, eax
0x14002242c  jz      short loc_140022454
0x14002242e  lea     r9, aFailedToOpenTh; "Failed to open the SdbUpdates key (%d)"
0x140022435  mov     dword ptr [rsp+38h+phkResult], eax
0x140022439  mov     r8d, 783h
0x14002243f  lea     rdx, aMergesdbFindan; "MergeSdb_FindAndMergeForTarget::<lambda"...
0x140022446  mov     ecx, 1
0x14002244b  call    AslLogCallPrintf
0x140022450  mov     eax, ebx
0x140022452  jmp     short loc_140022456
0x140022454  xor     eax, eax
0x140022456  add     rsp, 30h
0x14002245a  pop     rbx
0x14002245b  retn
```

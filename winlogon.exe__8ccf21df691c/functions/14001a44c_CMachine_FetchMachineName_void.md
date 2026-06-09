# CMachine::FetchMachineName(void)

- ea: `0x14001a44c`
- end: `0x14001a515`
- name: `?FetchMachineName@CMachine@@AEAAKXZ`
- size: `201`
- prototype: `unsigned int __fastcall(CMachine *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001a3a8`

## callees

- `0x14001a44c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a491`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001a491`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a50d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009dd5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001a50d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14009dd5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4b6`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a4df`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14009dd7d`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14001a4df`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14009dd7d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x14001a4ac`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x14001a4ac`
- `ntdll!RtlLeaveCriticalSection` at `0x14001a4e9`
- `ntdll!RtlLeaveCriticalSection` at `0x14001a4e9`
- `ntdll!RtlEnterCriticalSection` at `0x14001a476`
- `ntdll!RtlEnterCriticalSection` at `0x14001a476`

## string_xrefs

- `0x14001a4d8`: `COMPUTERNAME`
- `0x14009dd76`: `COMPUTERNAME`

## pseudocode

```c
__int64 __fastcall CMachine::FetchMachineName(CMachine *this)
{
  DWORD LastError; // ebx
  WCHAR *v3; // rax
  WCHAR *v4; // rdi
  DWORD nSize; // [rsp+58h] [rbp+10h] BYREF

  LastError = 0;
  nSize = 16;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 16));
  if ( !*((_QWORD *)this + 8) )
  {
    v3 = (WCHAR *)HeapAlloc(*((HANDLE *)this + 1), 8u, 2LL * nSize);
    v4 = v3;
    if ( v3 )
    {
      if ( !GetComputerNameW(v3, &nSize) )
        LastError = GetLastError();
    }
    else
    {
      LastError = 14;
    }
    if ( LastError )
    {
      if ( v4 )
        HeapFree(*((HANDLE *)this + 1), 0, v4);
    }
    else
    {
      *((_QWORD *)this + 8) = v4;
      SetEnvironmentVariableW(L"COMPUTERNAME", v4);
    }
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 16));
  return LastError;
}

```

## disassembly

```asm
0x14001a44c  mov     rax, rsp
0x14001a44f  mov     [rax+18h], rbx
0x14001a453  mov     [rax+8], rcx
0x14001a457  push    rsi
0x14001a458  push    rdi
0x14001a459  push    r14
0x14001a45b  sub     rsp, 30h
0x14001a45f  mov     rsi, rcx
0x14001a462  xor     ebx, ebx
0x14001a464  mov     [rax-28h], ebx
0x14001a467  mov     dword ptr [rax+10h], 10h
0x14001a46e  mov     [rax-20h], rbx
0x14001a472  add     rcx, 10h; CriticalSection
0x14001a476  call    cs:__imp_RtlEnterCriticalSection
0x14001a47c  cmp     [rsi+40h], rbx
0x14001a480  jnz     short loc_14001A4E5
0x14001a482  mov     r8d, [rsp+48h+nSize]
0x14001a487  add     r8, r8; dwBytes
0x14001a48a  lea     edx, [rbx+8]; dwFlags
0x14001a48d  mov     rcx, [rsi+8]; hHeap
0x14001a491  call    cs:__imp_HeapAlloc
0x14001a497  mov     rdi, rax
0x14001a49a  mov     [rsp+48h+var_20], rax
0x14001a49f  test    rax, rax
0x14001a4a2  jz      short loc_14001A4C4
0x14001a4a4  lea     rdx, [rsp+48h+nSize]; nSize
0x14001a4a9  mov     rcx, rax; lpBuffer
0x14001a4ac  call    cs:__imp_GetComputerNameW
0x14001a4b2  test    eax, eax
0x14001a4b4  jnz     short loc_14001A4CD
0x14001a4b6  call    cs:__imp_GetLastError
0x14001a4bc  mov     ebx, eax
0x14001a4be  mov     [rsp+48h+var_28], eax
0x14001a4c2  jmp     short loc_14001A4CD
0x14001a4c4  mov     ebx, 0Eh
0x14001a4c9  mov     [rsp+48h+var_28], ebx
0x14001a4cd  test    ebx, ebx
0x14001a4cf  jnz     short loc_14001A4FF
0x14001a4d1  mov     [rsi+40h], rdi
0x14001a4d5  mov     rdx, rdi; lpValue
0x14001a4d8  lea     rcx, aComputername; "COMPUTERNAME"
0x14001a4df  call    cs:__imp_SetEnvironmentVariableW
0x14001a4e5  lea     rcx, [rsi+10h]; CriticalSection
0x14001a4e9  call    cs:__imp_RtlLeaveCriticalSection
0x14001a4ef  mov     eax, ebx
0x14001a4f1  mov     rbx, [rsp+48h+arg_10]
0x14001a4f6  add     rsp, 30h
0x14001a4fa  pop     r14
0x14001a4fc  pop     rdi
0x14001a4fd  pop     rsi
0x14001a4fe  retn
0x14001a4ff  test    rdi, rdi
0x14001a502  jz      short loc_14001A4E5
0x14001a504  mov     r8, rdi; lpMem
0x14001a507  xor     edx, edx; dwFlags
0x14001a509  mov     rcx, [rsi+8]; hHeap
0x14001a50d  call    cs:__imp_HeapFree
0x14001a513  jmp     short loc_14001A4E5
0x14009dd38  push    rbp
0x14009dd3a  sub     rsp, 20h
0x14009dd3e  mov     rbp, rdx
0x14009dd41  cmp     dword ptr [rbp+20h], 0
0x14009dd45  jz      short loc_14009DD6A
0x14009dd47  mov     r8, [rbp+28h]; lpMem
0x14009dd4b  test    r8, r8
0x14009dd4e  jz      short loc_14009DD84
0x14009dd50  xor     edx, edx; dwFlags
0x14009dd52  mov     rcx, [rbp+50h]
0x14009dd56  mov     rcx, [rcx+8]; hHeap
0x14009dd5a  call    cs:__imp_HeapFree
0x14009dd60  mov     qword ptr [rbp+28h], 0
0x14009dd68  jmp     short loc_14009DD84
0x14009dd6a  mov     rdx, [rbp+28h]; lpValue
0x14009dd6e  mov     rax, [rbp+50h]
0x14009dd72  mov     [rax+40h], rdx
0x14009dd76  lea     rcx, aComputername; "COMPUTERNAME"
0x14009dd7d  call    cs:__imp_SetEnvironmentVariableW
0x14009dd83  nop
0x14009dd84  add     rsp, 20h
0x14009dd88  pop     rbp
0x14009dd89  retn
```

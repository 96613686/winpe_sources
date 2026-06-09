# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x14000a0ac`
- end: `0x14000a243`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `407`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x14000506c`
- `0x140014bc0`

## callees

- `0x140002ce0`
- `0x140002d84`
- `0x14000494c`
- `0x140004c1c`
- `0x140004ce4`
- `0x140005260`
- `0x140009284`
- `0x14000a0ac`
- `0x14000aef0`
- `0x140015010`

## import_xrefs

- `KERNEL32!WaitForSingleObjectEx` at `0x14000a0f4`
- `KERNEL32!WaitForSingleObjectEx` at `0x14000a0f4`
- `KERNEL32!HeapFree` at `0x14000a161`
- `KERNEL32!HeapFree` at `0x14000a161`
- `KERNEL32!GetLastError` at `0x14000a12a`
- `KERNEL32!GetLastError` at `0x14000a12a`
- `KERNEL32!ReleaseMutex` at `0x14000a135`
- `KERNEL32!ReleaseMutex` at `0x14000a178`
- `KERNEL32!ReleaseMutex` at `0x14000a135`
- `KERNEL32!ReleaseMutex` at `0x14000a178`
- `KERNEL32!SetLastError` at `0x14000a145`
- `KERNEL32!SetLastError` at `0x14000a145`
- `KERNEL32!GetProcessHeap` at `0x14000a153`
- `KERNEL32!GetProcessHeap` at `0x14000a153`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(char *lpMem)
{
  void *v2; // rdi
  DWORD v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  const char *v6; // r9
  DWORD LastError; // esi
  unsigned int v8; // r8d
  const char *v9; // r9
  HANDLE ProcessHeap; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  _BYTE v13[64]; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v14[64]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v15[64]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( wil::details::g_processShutdownInProgress
    || wil::details::g_pfnDllShutdownInProgress && (unsigned __int8)wil::details::g_pfnDllShutdownInProgress() )
  {
    if ( !--*(_DWORD *)lpMem )
    {
      wil::details_abi::UsageIndexes::UsageIndexes((wil::details_abi::UsageIndexes *)v13);
      if ( lpMem[96] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v13,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 40));
      if ( lpMem[160] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v14,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 104));
      if ( lpMem[224] )
        wil::details_abi::RawUsageIndex::Swap(
          (wil::details_abi::RawUsageIndex *)v15,
          (struct wil::details_abi::RawUsageIndex *)(lpMem + 168));
      wil::details_abi::UsageIndexes::Record((wil::details_abi::UsageIndexes *)v13);
      wil::details_abi::UsageIndexes::~UsageIndexes((wil::details_abi::UsageIndexes *)v13);
    }
  }
  else
  {
    v2 = (void *)*((_QWORD *)lpMem + 1);
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(retaddr, v4, v5, v6);
    }
    if ( --*(_DWORD *)lpMem )
    {
      if ( v2 && !ReleaseMutex(v2) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v11, v12);
    }
    else
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 16));
      if ( v2 )
      {
        LastError = GetLastError();
        if ( !ReleaseMutex(v2) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA15, v8, v9);
        SetLastError(LastError);
      }
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
    }
  }
}

```

## disassembly

```asm
0x14000a0ac  mov     [rsp+arg_0], rbx
0x14000a0b1  mov     [rsp+arg_8], rsi
0x14000a0b6  push    rdi
0x14000a0b7  sub     rsp, 0E0h
0x14000a0be  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x14000a0c5  mov     rbx, rcx
0x14000a0c8  jnz     loc_14000A188
0x14000a0ce  mov     rax, cs:?g_pfnDllShutdownInProgress@details@wil@@3P6AEX_EEA
0x14000a0d5  test    rax, rax
0x14000a0d8  jz      short loc_14000A0E7
0x14000a0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0df  test    al, al
0x14000a0e1  jnz     loc_14000A188
0x14000a0e7  mov     rdi, [rbx+8]
0x14000a0eb  xor     r8d, r8d; bAlertable
0x14000a0ee  mov     rcx, rdi; hHandle
0x14000a0f1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000a0f4  call    cs:__imp_WaitForSingleObjectEx
0x14000a0fa  cmp     eax, 102h
0x14000a0ff  jz      short loc_14000A10E
0x14000a101  test    eax, 0FFFFFF7Fh
0x14000a106  jnz     loc_14000A222
0x14000a10c  jmp     short loc_14000A110
0x14000a10e  xor     edi, edi
0x14000a110  mov     eax, [rbx]
0x14000a112  dec     eax
0x14000a114  mov     [rbx], eax
0x14000a116  mov     eax, [rbx]
0x14000a118  test    eax, eax
0x14000a11a  jnz     short loc_14000A16C
0x14000a11c  lea     rcx, [rbx+10h]; this
0x14000a120  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x14000a125  test    rdi, rdi
0x14000a128  jz      short loc_14000A14B
0x14000a12a  call    cs:__imp_GetLastError
0x14000a130  mov     rcx, rdi; hMutex
0x14000a133  mov     esi, eax
0x14000a135  call    cs:__imp_ReleaseMutex
0x14000a13b  test    eax, eax
0x14000a13d  jz      loc_14000A20F
0x14000a143  mov     ecx, esi; dwErrCode
0x14000a145  call    cs:__imp_SetLastError
0x14000a14b  mov     rcx, rbx
0x14000a14e  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x14000a153  call    cs:__imp_GetProcessHeap
0x14000a159  mov     r8, rbx; lpMem
0x14000a15c  xor     edx, edx; dwFlags
0x14000a15e  mov     rcx, rax; hHeap
0x14000a161  call    cs:__imp_HeapFree
0x14000a167  jmp     loc_14000A1FA
0x14000a16c  test    rdi, rdi
0x14000a16f  jz      loc_14000A1FA
0x14000a175  mov     rcx, rdi; hMutex
0x14000a178  call    cs:__imp_ReleaseMutex
0x14000a17e  test    eax, eax
0x14000a180  jz      loc_14000A230
0x14000a186  jmp     short loc_14000A1FA
0x14000a188  mov     eax, [rbx]
0x14000a18a  dec     eax
0x14000a18c  mov     [rbx], eax
0x14000a18e  mov     eax, [rbx]
0x14000a190  test    eax, eax
0x14000a192  jnz     short loc_14000A1FA
0x14000a194  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a199  call    ??0UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::UsageIndexes(void)
0x14000a19e  lea     rdx, [rbx+28h]; struct wil::details_abi::RawUsageIndex *
0x14000a1a2  cmp     byte ptr [rdx+38h], 0
0x14000a1a6  jz      short loc_14000A1B2
0x14000a1a8  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a1ad  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a1b2  cmp     byte ptr [rbx+0A0h], 0
0x14000a1b9  jz      short loc_14000A1C9
0x14000a1bb  lea     rdx, [rbx+68h]; struct wil::details_abi::RawUsageIndex *
0x14000a1bf  lea     rcx, [rsp+0E8h+var_88]; this
0x14000a1c4  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a1c9  cmp     byte ptr [rbx+0E0h], 0
0x14000a1d0  jz      short loc_14000A1E6
0x14000a1d2  lea     rdx, [rbx+0A8h]; struct wil::details_abi::RawUsageIndex *
0x14000a1d9  lea     rcx, [rsp+0E8h+var_48]; this
0x14000a1e1  call    ?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z; wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)
0x14000a1e6  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a1eb  call    ?Record@UsageIndexes@details_abi@wil@@QEAAXXZ; wil::details_abi::UsageIndexes::Record(void)
0x14000a1f0  lea     rcx, [rsp+0E8h+var_C8]; this
0x14000a1f5  call    ??1UsageIndexes@details_abi@wil@@QEAA@XZ; wil::details_abi::UsageIndexes::~UsageIndexes(void)
0x14000a1fa  lea     r11, [rsp+0E8h+var_8]
0x14000a202  mov     rbx, [r11+10h]
0x14000a206  mov     rsi, [r11+18h]
0x14000a20a  mov     rsp, r11
0x14000a20d  pop     rdi
0x14000a20e  retn
0x14000a20f  mov     rcx, [rsp+0E8h]; this
0x14000a217  mov     edx, 0A15h; void *
0x14000a21c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000a222  mov     rcx, [rsp+0E8h]; this
0x14000a22a  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x14000a230  mov     rcx, [rsp+0E8h]; this
0x14000a238  mov     edx, 0A15h; void *
0x14000a23d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)

- ea: `0x18002d8e8`
- end: `0x18002d9b5`
- name: `?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ`
- size: `205`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002dfe0`

## callees

- `0x18002d8e8`
- `0x18002debc`
- `0x18003a6d4`
- `0x180046cec`
- `0x18004701c`
- `0x1800470c0`
- `0x1800480e4`
- `0x18004890c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002d984`
- `KERNEL32!GetProcessHeap` at `0x18002d984`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002d929`
- `KERNEL32!WaitForSingleObjectEx` at `0x18002d929`
- `KERNEL32!HeapFree` at `0x18002d992`
- `KERNEL32!HeapFree` at `0x18002d992`

## string_xrefs

- `0x18002d942`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(_QWORD *lpMem)
{
  void *v2; // rbx
  DWORD v3; // eax
  void *v4; // rdx
  const char *v5; // r9
  int v6; // eax
  HANDLE ProcessHeap; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v9; // [rsp+38h] [rbp+10h] BYREF

  if ( wil::ProcessShutdownInProgress((wil *)lpMem) )
  {
    if ( !--*(_DWORD *)lpMem )
      wil::details_abi::FeatureStateData::ProcessShutdown((wil::details_abi::FeatureStateData *)(lpMem + 4));
  }
  else
  {
    v2 = (void *)lpMem[1];
    v3 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    if ( v3 == 258 )
    {
      v2 = 0;
    }
    else if ( (v3 & 0xFFFFFF7F) != 0 )
    {
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xE01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v5);
    }
    v6 = *(_DWORD *)lpMem - 1;
    v9 = v2;
    *(_DWORD *)lpMem = v6;
    if ( !*(_DWORD *)lpMem )
    {
      wil::details_abi::SemaphoreValue::Destroy((wil::details_abi::SemaphoreValue *)(lpMem + 2));
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v9,
        0);
      wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(lpMem);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, lpMem);
      v2 = v9;
    }
    if ( v2 )
      wil::details::ReleaseMutex((wil::details *)v2, v4);
  }
}

```

## disassembly

```asm
0x18002d8e8  mov     [rsp+arg_0], rbx
0x18002d8ed  push    rdi
0x18002d8ee  sub     rsp, 20h
0x18002d8f2  mov     rdi, rcx
0x18002d8f5  call    ?ProcessShutdownInProgress@wil@@YA_NXZ; wil::ProcessShutdownInProgress(void)
0x18002d8fa  test    al, al
0x18002d8fc  jz      short loc_18002D91C
0x18002d8fe  mov     eax, [rdi]
0x18002d900  dec     eax
0x18002d902  mov     [rdi], eax
0x18002d904  mov     eax, [rdi]
0x18002d906  test    eax, eax
0x18002d908  jnz     loc_18002D9AA
0x18002d90e  lea     rcx, [rdi+20h]; this
0x18002d912  call    ?ProcessShutdown@FeatureStateData@details_abi@wil@@QEAAXXZ; wil::details_abi::FeatureStateData::ProcessShutdown(void)
0x18002d917  jmp     loc_18002D9AA
0x18002d91c  mov     rbx, [rdi+8]
0x18002d920  xor     r8d, r8d; bAlertable
0x18002d923  mov     rcx, rbx; hHandle
0x18002d926  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002d929  call    cs:__imp_WaitForSingleObjectEx
0x18002d92f  cmp     eax, 102h
0x18002d934  jz      short loc_18002D954
0x18002d936  test    eax, 0FFFFFF7Fh
0x18002d93b  jz      short loc_18002D956
0x18002d93d  mov     rcx, [rsp+28h]; this
0x18002d942  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002d949  mov     edx, 0E01h; void *
0x18002d94e  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18002d954  xor     ebx, ebx
0x18002d956  mov     eax, [rdi]
0x18002d958  dec     eax
0x18002d95a  mov     [rsp+28h+arg_8], rbx
0x18002d95f  mov     [rdi], eax
0x18002d961  mov     eax, [rdi]
0x18002d963  test    eax, eax
0x18002d965  jnz     short loc_18002D99D
0x18002d967  lea     rcx, [rdi+10h]; this
0x18002d96b  call    ?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ; wil::details_abi::SemaphoreValue::Destroy(void)
0x18002d970  xor     edx, edx
0x18002d972  lea     rcx, [rsp+28h+arg_8]
0x18002d977  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002d97c  mov     rcx, rdi
0x18002d97f  call    ??1?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAA@XZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::~ProcessLocalStorageData<wil::details_abi::FeatureStateData>(void)
0x18002d984  call    cs:__imp_GetProcessHeap
0x18002d98a  mov     r8, rdi; lpMem
0x18002d98d  xor     edx, edx; dwFlags
0x18002d98f  mov     rcx, rax; hHeap
0x18002d992  call    cs:__imp_HeapFree
0x18002d998  mov     rbx, [rsp+28h+arg_8]
0x18002d99d  test    rbx, rbx
0x18002d9a0  jz      short loc_18002D9AA
0x18002d9a2  mov     rcx, rbx; this
0x18002d9a5  call    ?ReleaseMutex@details@wil@@YAXPEAX@Z; wil::details::ReleaseMutex(void *)
0x18002d9aa  mov     rbx, [rsp+28h+arg_0]
0x18002d9af  add     rsp, 20h
0x18002d9b3  pop     rdi
0x18002d9b4  retn
```

# ??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ

- ea: `0x1800092f4`
- end: `0x180009326`
- name: `??1?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@QEAA@XZ`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000cd26`
- `0x18000cd80`

## callees

- `0x1800092f4`
- `0x18000c478`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180009300`
- `KERNEL32!CloseHandle` at `0x180009300`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_any_t_V__mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__QEAA_XZ(
        void **a1)
{
  void *v1; // rcx
  __int64 v2; // r8
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *a1;
  if ( v1 )
  {
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v2, v3);
  }
}

```

## disassembly

```asm
0x1800092f4  sub     rsp, 28h
0x1800092f8  mov     rcx, [rcx]; hObject
0x1800092fb  test    rcx, rcx
0x1800092fe  jz      short loc_180009315
0x180009300  call    cs:__imp_CloseHandle
0x180009307  nop     dword ptr [rax+rax+00h]
0x18000930c  mov     rcx, [rsp+28h]; this
0x180009311  test    eax, eax
0x180009313  jz      short loc_18000931B
0x180009315  add     rsp, 28h
0x180009319  retn
0x18000931b  mov     edx, 9DDh; void *
0x180009320  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

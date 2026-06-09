# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000bd84`
- end: `0x18000be20`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `156`
- prototype: `__int64 __fastcall(void **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c628`

## callees

- `0x180009b10`
- `0x18000ab04`
- `0x18000bd84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bdae`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18000bdae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bde1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bde1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bdd5`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEB_WKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // r14
  void *v8; // rdi
  DWORD LastError; // ebp
  __int64 v10; // r8
  const char *v11; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    v8 = *a1;
    if ( *a1 )
    {
      LastError = GetLastError();
      if ( !CloseHandle(v8) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v10, v11);
      SetLastError(LastError);
    }
    *a1 = Semaphore;
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x18000bd84  mov     rax, rsp
0x18000bd87  mov     [rax+8], rbx
0x18000bd8b  mov     [rax+10h], rbp
0x18000bd8f  mov     [rax+18h], rsi
0x18000bd93  mov     [rax+20h], rdi
0x18000bd97  push    r14
0x18000bd99  sub     rsp, 30h
0x18000bd9d  mov     rsi, rcx
0x18000bda0  mov     dword ptr [rax-10h], 1F0003h
0x18000bda7  xor     ebx, ebx
0x18000bda9  xor     ecx, ecx; lpSemaphoreAttributes
0x18000bdab  mov     [rax-18h], ebx
0x18000bdae  call    cs:__imp_CreateSemaphoreExW
0x18000bdb4  mov     r14, rax
0x18000bdb7  test    rax, rax
0x18000bdba  jz      short loc_18000BDEC
0x18000bdbc  call    cs:__imp_GetLastError
0x18000bdc2  mov     rdi, [rsi]
0x18000bdc5  test    rdi, rdi
0x18000bdc8  jz      short loc_18000BDE7
0x18000bdca  call    cs:__imp_GetLastError
0x18000bdd0  mov     rcx, rdi; hObject
0x18000bdd3  mov     ebp, eax
0x18000bdd5  call    cs:__imp_CloseHandle
0x18000bddb  test    eax, eax
0x18000bddd  jz      short loc_18000BE10
0x18000bddf  mov     ecx, ebp; dwErrCode
0x18000bde1  call    cs:__imp_SetLastError
0x18000bde7  mov     [rsi], r14
0x18000bdea  jmp     short loc_18000BDF3
0x18000bdec  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000bdf1  mov     ebx, eax
0x18000bdf3  mov     rbp, [rsp+38h+arg_8]
0x18000bdf8  mov     eax, ebx
0x18000bdfa  mov     rbx, [rsp+38h+arg_0]
0x18000bdff  mov     rsi, [rsp+38h+arg_10]
0x18000be04  mov     rdi, [rsp+38h+arg_18]
0x18000be09  add     rsp, 30h
0x18000be0d  pop     r14
0x18000be0f  retn
0x18000be10  mov     rcx, [rsp+38h]; this
0x18000be15  mov     edx, 9D1h; void *
0x18000be1a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```

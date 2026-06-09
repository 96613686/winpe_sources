# QuotaOriginData::QuotaOriginData(__int64)

- ea: `0x18007b654`
- end: `0x18007b6ed`
- name: `??0QuotaOriginData@@QEAA@_J@Z`
- size: `153`
- prototype: `QuotaOriginData *__fastcall(QuotaOriginData *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007b550`

## callees

- `0x180061c90`
- `0x18007b654`
- `0x18008a248`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18007b693`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18007b693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b6a1`

## string_xrefs

- `0x18007b6db`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
QuotaOriginData *__fastcall QuotaOriginData::QuotaOriginData(QuotaOriginData *this, __int64 a2)
{
  HANDLE Semaphore; // rdi
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = 0;
  Semaphore = CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u);
  if ( !Semaphore )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v5);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    this,
    Semaphore);
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  *((_QWORD *)this + 3) = a2;
  return this;
}

```

## disassembly

```asm
0x18007b654  mov     rax, rsp
0x18007b657  mov     [rax+10h], rbx
0x18007b65b  mov     [rax+18h], rsi
0x18007b65f  mov     [rax+8], rcx
0x18007b663  push    rdi
0x18007b664  sub     rsp, 30h
0x18007b668  mov     rsi, rdx
0x18007b66b  mov     rbx, rcx
0x18007b66e  mov     [rax+8], rcx
0x18007b672  mov     qword ptr [rcx], 0
0x18007b679  mov     dword ptr [rax-10h], 1F0003h
0x18007b680  mov     dword ptr [rax-18h], 0
0x18007b687  xor     r9d, r9d; lpName
0x18007b68a  lea     edx, [r9+1]; lInitialCount
0x18007b68e  mov     r8d, edx; lMaximumCount
0x18007b691  xor     ecx, ecx; lpSemaphoreAttributes
0x18007b693  call    cs:__imp_CreateSemaphoreExW
0x18007b699  mov     rdi, rax
0x18007b69c  test    rax, rax
0x18007b69f  jz      short loc_18007B6D6
0x18007b6a1  call    cs:__imp_GetLastError
0x18007b6a7  mov     rdx, rdi
0x18007b6aa  mov     rcx, rbx
0x18007b6ad  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18007b6b2  nop
0x18007b6b3  mov     qword ptr [rbx+8], 0
0x18007b6bb  mov     byte ptr [rbx+10h], 0
0x18007b6bf  mov     [rbx+18h], rsi
0x18007b6c3  mov     rax, rbx
0x18007b6c6  mov     rbx, [rsp+38h+arg_8]
0x18007b6cb  mov     rsi, [rsp+38h+arg_10]
0x18007b6d0  add     rsp, 30h
0x18007b6d4  pop     rdi
0x18007b6d5  retn
0x18007b6d6  mov     rcx, [rsp+38h]; this
0x18007b6db  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18007b6e2  mov     edx, 1CC8h; void *
0x18007b6e7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```

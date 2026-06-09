# ScoobeEligibility::Details::IsCompanionDeviceAccount(void)

- ea: `0x18004c0e8`
- end: `0x18004c175`
- name: `?IsCompanionDeviceAccount@Details@ScoobeEligibility@@YA_NXZ`
- size: `141`
- prototype: `bool __fastcall(ScoobeEligibility::Details *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180049bf8`

## callees

- `0x18004c0e8`
- `0x18004c17c`
- `0x18008fc6c`
- `0x1800b0dc8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004c165`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18004c165`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c116`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004c116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c12a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004c12a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall ScoobeEligibility::Details::IsCompanionDeviceAccount(struct _LSA_TRANSLATED_SID2 *this)
{
  PSID v1; // rbx
  bool v2; // si
  int CurrentUserSid; // eax
  PSID pSid2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  pSid2 = 0;
  pv = 0;
  v2 = 0;
  if ( (int)SHTranslateNameToSID(this, &pv) >= 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &pSid2,
      0);
    CurrentUserSid = GetCurrentUserSid(&pSid2);
    v1 = pSid2;
    if ( CurrentUserSid >= 0 )
    {
      if ( EqualSid(pv, pSid2) )
        v2 = 1;
    }
  }
  if ( v1 )
    LocalFree(v1);
  if ( pv )
    CoTaskMemFree(pv);
  return v2;
}

```

## disassembly

```asm
0x18004c0e8  mov     rax, rsp
0x18004c0eb  mov     [rax+18h], rbx
0x18004c0ef  push    rsi
0x18004c0f0  sub     rsp, 20h
0x18004c0f4  xor     ebx, ebx
0x18004c0f6  mov     [rax+8], rbx
0x18004c0fa  mov     [rax+10h], rbx
0x18004c0fe  lea     rdx, [rax+10h]
0x18004c102  call    SHTranslateNameToSID
0x18004c107  test    eax, eax
0x18004c109  jns     short loc_18004C13E
0x18004c10b  xor     sil, sil
0x18004c10e  test    rbx, rbx
0x18004c111  jz      short loc_18004C11D
0x18004c113  mov     rcx, rbx; hMem
0x18004c116  call    cs:__imp_LocalFree
0x18004c11c  nop
0x18004c11d  cmp     [rsp+28h+pv], 0
0x18004c123  jz      short loc_18004C130
0x18004c125  mov     rcx, [rsp+28h+pv]; pv
0x18004c12a  call    cs:__imp_CoTaskMemFree
0x18004c130  mov     al, sil
0x18004c133  mov     rbx, [rsp+28h+arg_10]
0x18004c138  add     rsp, 20h
0x18004c13c  pop     rsi
0x18004c13d  retn
0x18004c13e  xor     edx, edx
0x18004c140  lea     rcx, [rsp+28h+pSid2]
0x18004c145  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18004c14a  lea     rcx, [rsp+28h+pSid2]; void **
0x18004c14f  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x18004c154  mov     rbx, [rsp+28h+pSid2]
0x18004c159  test    eax, eax
0x18004c15b  js      short loc_18004C10B
0x18004c15d  mov     rdx, rbx; pSid2
0x18004c160  mov     rcx, [rsp+28h+pv]; pSid1
0x18004c165  call    cs:__imp_EqualSid
0x18004c16b  test    eax, eax
0x18004c16d  jz      short loc_18004C10B
0x18004c16f  mov     sil, 1
0x18004c172  jmp     short loc_18004C10E
```

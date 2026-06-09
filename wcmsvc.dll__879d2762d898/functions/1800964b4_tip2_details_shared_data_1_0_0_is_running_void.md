# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x1800964b4`
- end: `0x1800965b5`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `257`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005303c`
- `0x1800543d4`
- `0x18009a728`

## callees

- `0x180027630`
- `0x180084f50`
- `0x180095938`
- `0x1800964b4`
- `0x180097ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009654c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800965ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009654c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800965ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096535`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096591`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,0>::is_running(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  bool v7; // bl
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-40h] BYREF
  __int128 v9; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h]
  __int128 v11; // [rsp+48h] [rbp-18h]

  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1 + 192);
  v2 = *(_QWORD *)(a1 + 240);
  if ( !v2 || (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
  {
LABEL_6:
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 232) )
  {
    v3 = *(unsigned int *)(a1 + 184);
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
    v4 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *, LPCRITICAL_SECTION))TestQueryData)(
           v2,
           0,
           v3,
           &v9,
           lpCriticalSection);
    v5 = pv[1];
    if ( !v4 )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      goto LABEL_6;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
  }
  v7 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return v7;
}

```

## disassembly

```asm
0x1800964b4  mov     [rsp-8+arg_8], rbx
0x1800964b9  push    rbp
0x1800964ba  mov     rbp, rsp
0x1800964bd  sub     rsp, 60h
0x1800964c1  mov     rax, cs:__security_cookie
0x1800964c8  xor     rax, rsp
0x1800964cb  mov     [rbp+var_8], rax
0x1800964cf  mov     rbx, rcx
0x1800964d2  mov     [rbp+lpCriticalSection], 0
0x1800964da  lea     rdx, [rcx+0C0h]
0x1800964e1  lea     rcx, [rbp+lpCriticalSection]
0x1800964e5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800964ea  mov     rcx, [rbx+0F0h]
0x1800964f1  test    rcx, rcx
0x1800964f4  jz      short loc_180096543
0x1800964f6  test    dword ptr [rbx+40h], 100h
0x1800964fd  jnz     short loc_180096543
0x1800964ff  cmp     dword ptr [rbx+0E8h], 0
0x180096506  jnz     loc_180096597
0x18009650c  mov     r8d, [rbx+0B8h]
0x180096513  lea     r9, [rbp+var_38]
0x180096517  xorps   xmm0, xmm0
0x18009651a  xor     edx, edx
0x18009651c  movups  [rbp+var_38], xmm0
0x180096520  movups  xmmword ptr [rbp+pv], xmm0
0x180096524  movups  [rbp+var_18], xmm0
0x180096528  call    TestQueryData
0x18009652d  mov     rcx, [rbp+pv+8]; pv
0x180096531  test    eax, eax
0x180096533  jnz     short loc_18009656B
0x180096535  call    cs:__imp_CoTaskMemFree
0x18009653b  mov     [rbp+pv+8], 0
0x180096543  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180096547  test    rcx, rcx
0x18009654a  jz      short loc_180096552
0x18009654c  call    cs:__imp_LeaveCriticalSection
0x180096552  xor     al, al
0x180096554  mov     rcx, [rbp+var_8]
0x180096558  xor     rcx, rsp; StackCookie
0x18009655b  call    __security_check_cookie
0x180096560  mov     rbx, [rsp+60h+arg_8]
0x180096565  add     rsp, 60h
0x180096569  pop     rbp
0x18009656a  retn
0x18009656b  mov     eax, dword ptr [rbp+pv+4]
0x18009656e  or      [rbx+40h], eax
0x180096571  test    rcx, rcx
0x180096574  jz      short loc_180096588
0x180096576  lea     rdx, [rbp+var_38]
0x18009657a  mov     rcx, rbx
0x18009657d  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180096582  mov     rcx, [rbp+pv+8]
0x180096586  jmp     short loc_180096591
0x180096588  mov     eax, dword ptr [rbp+pv]
0x18009658b  mov     [rbx+0B8h], eax
0x180096591  call    cs:__imp_CoTaskMemFree
0x180096597  mov     ebx, [rbx+40h]
0x18009659a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18009659e  shr     ebx, 8
0x1800965a1  not     bl
0x1800965a3  and     bl, 1
0x1800965a6  test    rcx, rcx
0x1800965a9  jz      short loc_1800965B1
0x1800965ab  call    cs:__imp_LeaveCriticalSection
0x1800965b1  mov     al, bl
0x1800965b3  jmp     short loc_180096554
```

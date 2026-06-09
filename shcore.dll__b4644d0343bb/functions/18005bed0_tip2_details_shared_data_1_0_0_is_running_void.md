# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x18005bed0`
- end: `0x18005bfda`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `266`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042be4`
- `0x18005aee8`
- `0x1800836b8`

## callees

- `0x1800272a8`
- `0x180044bf0`
- `0x18005bed0`
- `0x18005bfe0`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bfb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bfb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005befd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005befd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005bf8e`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,0>::is_running(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // eax
  void *v6; // rcx
  bool v7; // bl
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+20h] [rbp-40h] BYREF
  __int128 v10; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pv[2]; // [rsp+38h] [rbp-28h]
  __int128 v12; // [rsp+48h] [rbp-18h]

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v3 = *(_QWORD *)(a1 + 240);
  v9 = v1;
  if ( v3 && (*(_DWORD *)(a1 + 64) & 0x100) == 0 )
  {
    if ( !*(_DWORD *)(a1 + 232) )
    {
      v4 = *(unsigned int *)(a1 + 184);
      v10 = 0;
      *(_OWORD *)pv = 0;
      v12 = 0;
      v5 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *, struct _RTL_CRITICAL_SECTION *))TestQueryData)(
             v3,
             0,
             v4,
             &v10,
             v9);
      v6 = pv[1];
      if ( !v5 )
      {
        CoTaskMemFree(pv[1]);
        v7 = 0;
        pv[1] = 0;
LABEL_11:
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
        return v7;
      }
      *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
      if ( v6 )
      {
        tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v10);
        v6 = pv[1];
      }
      else
      {
        *(_DWORD *)(a1 + 184) = pv[0];
      }
      CoTaskMemFree(v6);
    }
    v7 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
    goto LABEL_11;
  }
  if ( v1 )
    LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x18005bed0  mov     [rsp-8+arg_8], rbx
0x18005bed5  mov     [rsp-8+arg_10], rdi
0x18005beda  push    rbp
0x18005bedb  mov     rbp, rsp
0x18005bede  sub     rsp, 60h
0x18005bee2  mov     rax, cs:__security_cookie
0x18005bee9  xor     rax, rsp
0x18005beec  mov     [rbp+var_8], rax
0x18005bef0  lea     rdi, [rcx+0C0h]
0x18005bef7  mov     rbx, rcx
0x18005befa  mov     rcx, rdi; lpCriticalSection
0x18005befd  call    cs:__imp_EnterCriticalSection
0x18005bf03  mov     rcx, [rbx+0F0h]
0x18005bf0a  mov     [rbp+var_40], rdi
0x18005bf0e  test    rcx, rcx
0x18005bf11  jz      loc_18005BFAC
0x18005bf17  test    dword ptr [rbx+40h], 100h
0x18005bf1e  jnz     loc_18005BFAC
0x18005bf24  cmp     dword ptr [rbx+0E8h], 0
0x18005bf2b  jnz     short loc_18005BF94
0x18005bf2d  mov     r8d, [rbx+0B8h]
0x18005bf34  lea     r9, [rbp+var_38]
0x18005bf38  xorps   xmm0, xmm0
0x18005bf3b  xor     edx, edx
0x18005bf3d  movups  [rbp+var_38], xmm0
0x18005bf41  movups  xmmword ptr [rbp+pv], xmm0
0x18005bf45  movups  [rbp+var_18], xmm0
0x18005bf49  call    TestQueryData
0x18005bf4e  mov     rcx, [rbp+pv+8]; pv
0x18005bf52  test    eax, eax
0x18005bf54  jnz     short loc_18005BF68
0x18005bf56  call    cs:__imp_CoTaskMemFree
0x18005bf5c  xor     bl, bl
0x18005bf5e  mov     [rbp+pv+8], 0
0x18005bf66  jmp     short loc_18005BF9F
0x18005bf68  mov     eax, dword ptr [rbp+pv+4]
0x18005bf6b  or      [rbx+40h], eax
0x18005bf6e  test    rcx, rcx
0x18005bf71  jz      short loc_18005BF85
0x18005bf73  lea     rdx, [rbp+var_38]
0x18005bf77  mov     rcx, rbx
0x18005bf7a  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18005bf7f  mov     rcx, [rbp+pv+8]
0x18005bf83  jmp     short loc_18005BF8E
0x18005bf85  mov     eax, dword ptr [rbp+pv]
0x18005bf88  mov     [rbx+0B8h], eax
0x18005bf8e  call    cs:__imp_CoTaskMemFree
0x18005bf94  mov     ebx, [rbx+40h]
0x18005bf97  shr     ebx, 8
0x18005bf9a  not     bl
0x18005bf9c  and     bl, 1
0x18005bf9f  lea     rcx, [rbp+var_40]
0x18005bfa3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18005bfa8  mov     al, bl
0x18005bfaa  jmp     short loc_18005BFBC
0x18005bfac  test    rdi, rdi
0x18005bfaf  jz      short loc_18005BFBA
0x18005bfb1  mov     rcx, rdi; lpCriticalSection
0x18005bfb4  call    cs:__imp_LeaveCriticalSection
0x18005bfba  xor     al, al
0x18005bfbc  mov     rcx, [rbp+var_8]
0x18005bfc0  xor     rcx, rsp; StackCookie
0x18005bfc3  call    __security_check_cookie
0x18005bfc8  lea     r11, [rsp+60h+var_s0]
0x18005bfcd  mov     rbx, [r11+18h]
0x18005bfd1  mov     rdi, [r11+20h]
0x18005bfd5  mov     rsp, r11
0x18005bfd8  pop     rbp
0x18005bfd9  retn
```

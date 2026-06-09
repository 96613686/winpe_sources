# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x1800254d8`
- end: `0x1800255a5`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180023d40`
- `0x1800253f0`
- `0x180025a24`
- `0x180026744`
- `0x180052c50`
- `0x180053090`
- `0x180083b48`

## callees

- `0x1800254d8`
- `0x1800272a8`
- `0x18005bfe0`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800254f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800254f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002559b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025556`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002559b`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  int v4; // eax
  void *v5; // rcx
  __int128 v7; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v9; // [rsp+40h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  ++*(_DWORD *)(a1 + 232);
  if ( (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
    return 0;
  v2 = *(_QWORD *)(a1 + 240);
  if ( v2 && *(_DWORD *)(a1 + 232) == 1 )
  {
    v3 = *(unsigned int *)(a1 + 184);
    v7 = 0;
    *(_OWORD *)pv = 0;
    v9 = 0;
    v4 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v2, 1, v3, &v7);
    v5 = pv[1];
    if ( !v4 )
    {
      CoTaskMemFree(pv[1]);
      return 0;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v5 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v7);
      v5 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v5);
  }
  return 1;
}

```

## disassembly

```asm
0x1800254d8  push    rbx
0x1800254da  sub     rsp, 60h
0x1800254de  mov     rax, cs:__security_cookie
0x1800254e5  xor     rax, rsp
0x1800254e8  mov     [rsp+68h+var_18], rax
0x1800254ed  mov     rbx, rcx
0x1800254f0  add     rcx, 0C0h; lpCriticalSection
0x1800254f7  call    cs:__imp_EnterCriticalSection
0x1800254fd  inc     dword ptr [rbx+0E8h]
0x180025503  test    dword ptr [rbx+40h], 100h
0x18002550a  jnz     short loc_18002555C
0x18002550c  mov     rcx, [rbx+0F0h]
0x180025513  test    rcx, rcx
0x180025516  jz      loc_1800255A1
0x18002551c  cmp     dword ptr [rbx+0E8h], 1
0x180025523  jnz     short loc_1800255A1
0x180025525  mov     r8d, [rbx+0B8h]
0x18002552c  lea     r9, [rsp+68h+var_48]
0x180025531  xorps   xmm0, xmm0
0x180025534  mov     edx, 1
0x180025539  movups  [rsp+68h+var_48], xmm0
0x18002553e  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180025543  movups  [rsp+68h+var_28], xmm0
0x180025548  call    TestQueryData
0x18002554d  mov     rcx, [rsp+68h+pv+8]; pv
0x180025552  test    eax, eax
0x180025554  jnz     short loc_180025571
0x180025556  call    cs:__imp_CoTaskMemFree
0x18002555c  xor     al, al
0x18002555e  mov     rcx, [rsp+68h+var_18]
0x180025563  xor     rcx, rsp; StackCookie
0x180025566  call    __security_check_cookie
0x18002556b  add     rsp, 60h
0x18002556f  pop     rbx
0x180025570  retn
0x180025571  mov     eax, dword ptr [rsp+68h+pv+4]
0x180025575  or      [rbx+40h], eax
0x180025578  test    rcx, rcx
0x18002557b  jz      short loc_180025591
0x18002557d  lea     rdx, [rsp+68h+var_48]
0x180025582  mov     rcx, rbx
0x180025585  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18002558a  mov     rcx, [rsp+68h+pv+8]
0x18002558f  jmp     short loc_18002559B
0x180025591  mov     edx, dword ptr [rsp+68h+pv]
0x180025595  mov     [rbx+0B8h], edx
0x18002559b  call    cs:__imp_CoTaskMemFree
0x1800255a1  mov     al, 1
0x1800255a3  jmp     short loc_18002555E
```

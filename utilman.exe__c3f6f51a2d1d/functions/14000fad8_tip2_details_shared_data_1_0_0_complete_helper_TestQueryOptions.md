# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x14000fad8`
- end: `0x14000fb8f`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000cec0`
- `0x140022ea8`

## callees

- `0x140002480`
- `0x14000fad8`
- `0x14000fce8`
- `0x1400100c8`
- `0x140012c3c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000fb6f`
- `ole32!CoTaskMemFree` at `0x14000fb6f`

## pseudocode

```c
void __fastcall tip2::details::shared_data<1,0,0>::complete_helper(__int64 a1, __int64 a2)
{
  bool v2; // zf
  __int64 v4; // r8
  __int64 v5; // rcx
  __int128 v6; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v8; // [rsp+40h] [rbp-28h]

  v2 = *(_DWORD *)(a1 + 232) == 0;
  v6 = 0;
  *(_OWORD *)pv = 0;
  v8 = 0;
  if ( !v2 )
    a2 = (unsigned int)a2 | 8;
  v4 = *(unsigned int *)(a1 + 184);
  v5 = *(_QWORD *)(a1 + 240);
  *(_QWORD *)(a1 + 240) = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v5, a2, v4, &v6) )
  {
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( pv[1] )
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v6);
    else
      *(_DWORD *)(a1 + 184) = pv[0];
    tip2::details::shared_data<1,0,0>::evaluate_and_report(a1, v8);
  }
  CoTaskMemFree(pv[1]);
}

```

## disassembly

```asm
0x14000fad8  push    rbx
0x14000fada  sub     rsp, 60h
0x14000fade  mov     rax, cs:__security_cookie
0x14000fae5  xor     rax, rsp
0x14000fae8  mov     [rsp+68h+var_18], rax
0x14000faed  cmp     dword ptr [rcx+0E8h], 0
0x14000faf4  xorps   xmm0, xmm0
0x14000faf7  movups  [rsp+68h+var_48], xmm0
0x14000fafc  mov     rbx, rcx
0x14000faff  movups  xmmword ptr [rsp+68h+pv], xmm0
0x14000fb04  movups  [rsp+68h+var_28], xmm0
0x14000fb09  jbe     short loc_14000FB0E
0x14000fb0b  or      edx, 8
0x14000fb0e  mov     r8d, [rcx+0B8h]
0x14000fb15  lea     r9, [rsp+68h+var_48]
0x14000fb1a  mov     rcx, [rcx+0F0h]
0x14000fb21  mov     qword ptr [rbx+0F0h], 0
0x14000fb2c  call    TestQueryData
0x14000fb31  test    eax, eax
0x14000fb33  jz      short loc_14000FB6A
0x14000fb35  mov     eax, dword ptr [rsp+68h+pv+4]
0x14000fb39  or      [rbx+40h], eax
0x14000fb3c  cmp     [rsp+68h+pv+8], 0
0x14000fb42  jz      short loc_14000FB53
0x14000fb44  lea     rdx, [rsp+68h+var_48]
0x14000fb49  mov     rcx, rbx
0x14000fb4c  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x14000fb51  jmp     short loc_14000FB5D
0x14000fb53  mov     eax, dword ptr [rsp+68h+pv]
0x14000fb57  mov     [rbx+0B8h], eax
0x14000fb5d  mov     rdx, qword ptr [rsp+68h+var_28]
0x14000fb62  mov     rcx, rbx
0x14000fb65  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x14000fb6a  mov     rcx, [rsp+68h+pv+8]; pv
0x14000fb6f  call    cs:__imp_CoTaskMemFree
0x14000fb76  nop     dword ptr [rax+rax+00h]
0x14000fb7b  mov     rcx, [rsp+68h+var_18]
0x14000fb80  xor     rcx, rsp; StackCookie
0x14000fb83  call    __security_check_cookie
0x14000fb88  add     rsp, 60h
0x14000fb8c  pop     rbx
0x14000fb8d  retn
```

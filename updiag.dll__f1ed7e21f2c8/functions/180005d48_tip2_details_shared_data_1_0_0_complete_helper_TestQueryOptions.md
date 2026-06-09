# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x180005d48`
- end: `0x180005df8`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004d9c`
- `0x180005950`
- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`

## callees

- `0x180003ae0`
- `0x180005d48`
- `0x180005e00`
- `0x180006ab4`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ddf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005ddf`

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
0x180005d48  push    rbx
0x180005d4a  sub     rsp, 60h
0x180005d4e  mov     rax, cs:__security_cookie
0x180005d55  xor     rax, rsp
0x180005d58  mov     [rsp+68h+var_18], rax
0x180005d5d  cmp     dword ptr [rcx+0E8h], 0
0x180005d64  xorps   xmm0, xmm0
0x180005d67  movups  [rsp+68h+var_48], xmm0
0x180005d6c  mov     rbx, rcx
0x180005d6f  movups  xmmword ptr [rsp+68h+pv], xmm0
0x180005d74  movups  [rsp+68h+var_28], xmm0
0x180005d79  jbe     short loc_180005D7E
0x180005d7b  or      edx, 8
0x180005d7e  mov     r8d, [rcx+0B8h]
0x180005d85  lea     r9, [rsp+68h+var_48]
0x180005d8a  mov     rcx, [rcx+0F0h]
0x180005d91  mov     qword ptr [rbx+0F0h], 0
0x180005d9c  call    TestQueryData
0x180005da1  test    eax, eax
0x180005da3  jz      short loc_180005DDA
0x180005da5  mov     eax, dword ptr [rsp+68h+pv+4]
0x180005da9  or      [rbx+40h], eax
0x180005dac  cmp     [rsp+68h+pv+8], 0
0x180005db2  jz      short loc_180005DC3
0x180005db4  lea     rdx, [rsp+68h+var_48]
0x180005db9  mov     rcx, rbx
0x180005dbc  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180005dc1  jmp     short loc_180005DCD
0x180005dc3  mov     eax, dword ptr [rsp+68h+pv]
0x180005dc7  mov     [rbx+0B8h], eax
0x180005dcd  mov     rdx, qword ptr [rsp+68h+var_28]
0x180005dd2  mov     rcx, rbx
0x180005dd5  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x180005dda  mov     rcx, [rsp+68h+pv+8]; pv
0x180005ddf  call    cs:__imp_CoTaskMemFree
0x180005de5  mov     rcx, [rsp+68h+var_18]
0x180005dea  xor     rcx, rsp; StackCookie
0x180005ded  call    __security_check_cookie
0x180005df2  add     rsp, 60h
0x180005df6  pop     rbx
0x180005df7  retn
```

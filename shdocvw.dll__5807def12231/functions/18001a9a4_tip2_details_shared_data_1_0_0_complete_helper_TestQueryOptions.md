# tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)

- ea: `0x18001a9a4`
- end: `0x18001aa54`
- name: `?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z`
- size: `176`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014c74`
- `0x18001a950`

## callees

- `0x180008320`
- `0x18001a9a4`
- `0x18001aba8`
- `0x18001b164`
- `0x18001da84`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001aa3b`

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
0x18001a9a4  push    rbx
0x18001a9a6  sub     rsp, 60h
0x18001a9aa  mov     rax, cs:__security_cookie
0x18001a9b1  xor     rax, rsp
0x18001a9b4  mov     [rsp+68h+var_18], rax
0x18001a9b9  cmp     dword ptr [rcx+0E8h], 0
0x18001a9c0  xorps   xmm0, xmm0
0x18001a9c3  movups  [rsp+68h+var_48], xmm0
0x18001a9c8  mov     rbx, rcx
0x18001a9cb  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001a9d0  movups  [rsp+68h+var_28], xmm0
0x18001a9d5  jbe     short loc_18001A9DA
0x18001a9d7  or      edx, 8
0x18001a9da  mov     r8d, [rcx+0B8h]
0x18001a9e1  lea     r9, [rsp+68h+var_48]
0x18001a9e6  mov     rcx, [rcx+0F0h]
0x18001a9ed  mov     qword ptr [rbx+0F0h], 0
0x18001a9f8  call    TestQueryData
0x18001a9fd  test    eax, eax
0x18001a9ff  jz      short loc_18001AA36
0x18001aa01  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001aa05  or      [rbx+40h], eax
0x18001aa08  cmp     [rsp+68h+pv+8], 0
0x18001aa0e  jz      short loc_18001AA1F
0x18001aa10  lea     rdx, [rsp+68h+var_48]
0x18001aa15  mov     rcx, rbx
0x18001aa18  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001aa1d  jmp     short loc_18001AA29
0x18001aa1f  mov     eax, dword ptr [rsp+68h+pv]
0x18001aa23  mov     [rbx+0B8h], eax
0x18001aa29  mov     rdx, qword ptr [rsp+68h+var_28]
0x18001aa2e  mov     rcx, rbx
0x18001aa31  call    ?evaluate_and_report@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAX_J@Z; tip2::details::shared_data<1,0,0>::evaluate_and_report(__int64)
0x18001aa36  mov     rcx, [rsp+68h+pv+8]; pv
0x18001aa3b  call    cs:__imp_CoTaskMemFree
0x18001aa41  mov     rcx, [rsp+68h+var_18]
0x18001aa46  xor     rcx, rsp; StackCookie
0x18001aa49  call    __security_check_cookie
0x18001aa4e  add     rsp, 60h
0x18001aa52  pop     rbx
0x18001aa53  retn
```

# tip2::details::shared_data<1,1,1>::begin_update(void)

- ea: `0x1802d8a1c`
- end: `0x1802d8ae9`
- name: `?begin_update@?$shared_data@$00$00$00@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802d76c4`
- `0x1802d7fec`
- `0x1802d810c`
- `0x1802d8208`
- `0x1802d82e4`

## callees

- `0x18006ea84`
- `0x18011368c`
- `0x18015cb00`
- `0x1802d8a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802d8a3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802d8a3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d8a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d8adf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d8a9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802d8adf`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,1,1>::begin_update(__int64 a1)
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
      tip2::details::shared_data<1,1,1>::deserialize_data(a1, &v7);
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
0x1802d8a1c  push    rbx
0x1802d8a1e  sub     rsp, 60h
0x1802d8a22  mov     rax, cs:__security_cookie
0x1802d8a29  xor     rax, rsp
0x1802d8a2c  mov     [rsp+68h+var_18], rax
0x1802d8a31  mov     rbx, rcx
0x1802d8a34  add     rcx, 0C0h; lpCriticalSection
0x1802d8a3b  call    cs:__imp_EnterCriticalSection
0x1802d8a41  inc     dword ptr [rbx+0E8h]
0x1802d8a47  test    dword ptr [rbx+40h], 100h
0x1802d8a4e  jnz     short loc_1802D8AA0
0x1802d8a50  mov     rcx, [rbx+0F0h]
0x1802d8a57  test    rcx, rcx
0x1802d8a5a  jz      loc_1802D8AE5
0x1802d8a60  cmp     dword ptr [rbx+0E8h], 1
0x1802d8a67  jnz     short loc_1802D8AE5
0x1802d8a69  mov     r8d, [rbx+0B8h]
0x1802d8a70  lea     r9, [rsp+68h+var_48]
0x1802d8a75  xorps   xmm0, xmm0
0x1802d8a78  mov     edx, 1
0x1802d8a7d  movups  [rsp+68h+var_48], xmm0
0x1802d8a82  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1802d8a87  movups  [rsp+68h+var_28], xmm0
0x1802d8a8c  call    TestQueryData
0x1802d8a91  mov     rcx, [rsp+68h+pv+8]; pv
0x1802d8a96  test    eax, eax
0x1802d8a98  jnz     short loc_1802D8AB5
0x1802d8a9a  call    cs:__imp_CoTaskMemFree
0x1802d8aa0  xor     al, al
0x1802d8aa2  mov     rcx, [rsp+68h+var_18]
0x1802d8aa7  xor     rcx, rsp; StackCookie
0x1802d8aaa  call    __security_check_cookie
0x1802d8aaf  add     rsp, 60h
0x1802d8ab3  pop     rbx
0x1802d8ab4  retn
0x1802d8ab5  mov     eax, dword ptr [rsp+68h+pv+4]
0x1802d8ab9  or      [rbx+40h], eax
0x1802d8abc  test    rcx, rcx
0x1802d8abf  jz      short loc_1802D8AD5
0x1802d8ac1  lea     rdx, [rsp+68h+var_48]
0x1802d8ac6  mov     rcx, rbx
0x1802d8ac9  call    ?deserialize_data@?$shared_data@$00$00$00@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,1,1>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x1802d8ace  mov     rcx, [rsp+68h+pv+8]
0x1802d8ad3  jmp     short loc_1802D8ADF
0x1802d8ad5  mov     edx, dword ptr [rsp+68h+pv]
0x1802d8ad9  mov     [rbx+0B8h], edx
0x1802d8adf  call    cs:__imp_CoTaskMemFree
0x1802d8ae5  mov     al, 1
0x1802d8ae7  jmp     short loc_1802D8AA2
```

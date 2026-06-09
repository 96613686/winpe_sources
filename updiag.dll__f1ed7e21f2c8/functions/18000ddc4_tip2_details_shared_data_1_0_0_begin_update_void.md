# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18000ddc4`
- end: `0x18000de8e`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c9fc`
- `0x18000cb98`
- `0x18000cd28`
- `0x18000ceb8`
- `0x18000d048`
- `0x18000d1d8`
- `0x18000d368`
- `0x18000d4f8`
- `0x18000d6a0`
- `0x18000d880`

## callees

- `0x180003ae0`
- `0x180005e00`
- `0x18000ddc4`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de84`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000de84`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dde3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000dde3`

## pseudocode

```c
char __fastcall tip2::details::shared_data<1,0,0>::begin_update(__int64 a1)
{
  int v2; // eax
  bool v3; // zf
  __int64 v4; // rcx
  __int64 v5; // r8
  int v6; // eax
  void *v7; // rcx
  __int128 v9; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v11; // [rsp+40h] [rbp-28h]

  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v2 = *(_DWORD *)(a1 + 232) + 1;
  v3 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
  *(_DWORD *)(a1 + 232) = v2;
  if ( !v3 )
    return 0;
  v4 = *(_QWORD *)(a1 + 240);
  if ( v4 && v2 == 1 )
  {
    v5 = *(unsigned int *)(a1 + 184);
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
    v6 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))TestQueryData)(v4, 1, v5, &v9);
    v7 = pv[1];
    if ( !v6 )
    {
      CoTaskMemFree(pv[1]);
      return 0;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v7 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      v7 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v7);
  }
  return 1;
}

```

## disassembly

```asm
0x18000ddc4  push    rbx
0x18000ddc6  sub     rsp, 60h
0x18000ddca  mov     rax, cs:__security_cookie
0x18000ddd1  xor     rax, rsp
0x18000ddd4  mov     [rsp+68h+var_18], rax
0x18000ddd9  mov     rbx, rcx
0x18000dddc  add     rcx, 0C0h; lpCriticalSection
0x18000dde3  call    cs:__imp_EnterCriticalSection
0x18000dde9  mov     eax, [rbx+0E8h]
0x18000ddef  inc     eax
0x18000ddf1  test    dword ptr [rbx+40h], 100h
0x18000ddf8  mov     [rbx+0E8h], eax
0x18000ddfe  jnz     short loc_18000DE45
0x18000de00  mov     rcx, [rbx+0F0h]
0x18000de07  test    rcx, rcx
0x18000de0a  jz      short loc_18000DE8A
0x18000de0c  cmp     eax, 1
0x18000de0f  jnz     short loc_18000DE8A
0x18000de11  mov     r8d, [rbx+0B8h]
0x18000de18  lea     r9, [rsp+68h+var_48]
0x18000de1d  xorps   xmm0, xmm0
0x18000de20  mov     edx, eax
0x18000de22  movups  [rsp+68h+var_48], xmm0
0x18000de27  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18000de2c  movups  [rsp+68h+var_28], xmm0
0x18000de31  call    TestQueryData
0x18000de36  mov     rcx, [rsp+68h+pv+8]; pv
0x18000de3b  test    eax, eax
0x18000de3d  jnz     short loc_18000DE5A
0x18000de3f  call    cs:__imp_CoTaskMemFree
0x18000de45  xor     al, al
0x18000de47  mov     rcx, [rsp+68h+var_18]
0x18000de4c  xor     rcx, rsp; StackCookie
0x18000de4f  call    __security_check_cookie
0x18000de54  add     rsp, 60h
0x18000de58  pop     rbx
0x18000de59  retn
0x18000de5a  mov     eax, dword ptr [rsp+68h+pv+4]
0x18000de5e  or      [rbx+40h], eax
0x18000de61  test    rcx, rcx
0x18000de64  jz      short loc_18000DE7A
0x18000de66  lea     rdx, [rsp+68h+var_48]
0x18000de6b  mov     rcx, rbx
0x18000de6e  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18000de73  mov     rcx, [rsp+68h+pv+8]
0x18000de78  jmp     short loc_18000DE84
0x18000de7a  mov     edx, dword ptr [rsp+68h+pv]
0x18000de7e  mov     [rbx+0B8h], edx
0x18000de84  call    cs:__imp_CoTaskMemFree
0x18000de8a  mov     al, 1
0x18000de8c  jmp     short loc_18000DE47
```

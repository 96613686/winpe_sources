# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18034aa24`
- end: `0x18034aaf1`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180159738`
- `0x18034b30c`
- `0x1803b9070`
- `0x1804689f4`
- `0x180469060`

## callees

- `0x18006ea84`
- `0x180113504`
- `0x18015cb00`
- `0x18034aa24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18034aa43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18034aa43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034aaa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034aae7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034aaa2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18034aae7`

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
0x18034aa24  push    rbx
0x18034aa26  sub     rsp, 60h
0x18034aa2a  mov     rax, cs:__security_cookie
0x18034aa31  xor     rax, rsp
0x18034aa34  mov     [rsp+68h+var_18], rax
0x18034aa39  mov     rbx, rcx
0x18034aa3c  add     rcx, 0C0h; lpCriticalSection
0x18034aa43  call    cs:__imp_EnterCriticalSection
0x18034aa49  inc     dword ptr [rbx+0E8h]
0x18034aa4f  test    dword ptr [rbx+40h], 100h
0x18034aa56  jnz     short loc_18034AAA8
0x18034aa58  mov     rcx, [rbx+0F0h]
0x18034aa5f  test    rcx, rcx
0x18034aa62  jz      loc_18034AAED
0x18034aa68  cmp     dword ptr [rbx+0E8h], 1
0x18034aa6f  jnz     short loc_18034AAED
0x18034aa71  mov     r8d, [rbx+0B8h]
0x18034aa78  lea     r9, [rsp+68h+var_48]
0x18034aa7d  xorps   xmm0, xmm0
0x18034aa80  mov     edx, 1
0x18034aa85  movups  [rsp+68h+var_48], xmm0
0x18034aa8a  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18034aa8f  movups  [rsp+68h+var_28], xmm0
0x18034aa94  call    TestQueryData
0x18034aa99  mov     rcx, [rsp+68h+pv+8]; pv
0x18034aa9e  test    eax, eax
0x18034aaa0  jnz     short loc_18034AABD
0x18034aaa2  call    cs:__imp_CoTaskMemFree
0x18034aaa8  xor     al, al
0x18034aaaa  mov     rcx, [rsp+68h+var_18]
0x18034aaaf  xor     rcx, rsp; StackCookie
0x18034aab2  call    __security_check_cookie
0x18034aab7  add     rsp, 60h
0x18034aabb  pop     rbx
0x18034aabc  retn
0x18034aabd  mov     eax, dword ptr [rsp+68h+pv+4]
0x18034aac1  or      [rbx+40h], eax
0x18034aac4  test    rcx, rcx
0x18034aac7  jz      short loc_18034AADD
0x18034aac9  lea     rdx, [rsp+68h+var_48]
0x18034aace  mov     rcx, rbx
0x18034aad1  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18034aad6  mov     rcx, [rsp+68h+pv+8]
0x18034aadb  jmp     short loc_18034AAE7
0x18034aadd  mov     edx, dword ptr [rsp+68h+pv]
0x18034aae1  mov     [rbx+0B8h], edx
0x18034aae7  call    cs:__imp_CoTaskMemFree
0x18034aaed  mov     al, 1
0x18034aaef  jmp     short loc_18034AAAA
```

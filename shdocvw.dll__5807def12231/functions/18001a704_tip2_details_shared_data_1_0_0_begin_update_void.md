# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x18001a704`
- end: `0x18001a7d1`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001d900`

## callees

- `0x180008320`
- `0x18001a704`
- `0x18001aba8`
- `0x18001da84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a723`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a7c7`

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
0x18001a704  push    rbx
0x18001a706  sub     rsp, 60h
0x18001a70a  mov     rax, cs:__security_cookie
0x18001a711  xor     rax, rsp
0x18001a714  mov     [rsp+68h+var_18], rax
0x18001a719  mov     rbx, rcx
0x18001a71c  add     rcx, 0C0h; lpCriticalSection
0x18001a723  call    cs:__imp_EnterCriticalSection
0x18001a729  inc     dword ptr [rbx+0E8h]
0x18001a72f  test    dword ptr [rbx+40h], 100h
0x18001a736  jnz     short loc_18001A788
0x18001a738  mov     rcx, [rbx+0F0h]
0x18001a73f  test    rcx, rcx
0x18001a742  jz      loc_18001A7CD
0x18001a748  cmp     dword ptr [rbx+0E8h], 1
0x18001a74f  jnz     short loc_18001A7CD
0x18001a751  mov     r8d, [rbx+0B8h]
0x18001a758  lea     r9, [rsp+68h+var_48]
0x18001a75d  xorps   xmm0, xmm0
0x18001a760  mov     edx, 1
0x18001a765  movups  [rsp+68h+var_48], xmm0
0x18001a76a  movups  xmmword ptr [rsp+68h+pv], xmm0
0x18001a76f  movups  [rsp+68h+var_28], xmm0
0x18001a774  call    TestQueryData
0x18001a779  mov     rcx, [rsp+68h+pv+8]; pv
0x18001a77e  test    eax, eax
0x18001a780  jnz     short loc_18001A79D
0x18001a782  call    cs:__imp_CoTaskMemFree
0x18001a788  xor     al, al
0x18001a78a  mov     rcx, [rsp+68h+var_18]
0x18001a78f  xor     rcx, rsp; StackCookie
0x18001a792  call    __security_check_cookie
0x18001a797  add     rsp, 60h
0x18001a79b  pop     rbx
0x18001a79c  retn
0x18001a79d  mov     eax, dword ptr [rsp+68h+pv+4]
0x18001a7a1  or      [rbx+40h], eax
0x18001a7a4  test    rcx, rcx
0x18001a7a7  jz      short loc_18001A7BD
0x18001a7a9  lea     rdx, [rsp+68h+var_48]
0x18001a7ae  mov     rcx, rbx
0x18001a7b1  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x18001a7b6  mov     rcx, [rsp+68h+pv+8]
0x18001a7bb  jmp     short loc_18001A7C7
0x18001a7bd  mov     edx, dword ptr [rsp+68h+pv]
0x18001a7c1  mov     [rbx+0B8h], edx
0x18001a7c7  call    cs:__imp_CoTaskMemFree
0x18001a7cd  mov     al, 1
0x18001a7cf  jmp     short loc_18001A78A
```

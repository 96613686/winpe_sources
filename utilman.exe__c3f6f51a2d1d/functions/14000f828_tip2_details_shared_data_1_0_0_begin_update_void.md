# tip2::details::shared_data<1,0,0>::begin_update(void)

- ea: `0x14000f828`
- end: `0x14000f90c`
- name: `?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000e990`

## callees

- `0x140002480`
- `0x14000f828`
- `0x14000fce8`
- `0x140012c3c`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14000f847`
- `KERNEL32!EnterCriticalSection` at `0x14000f847`
- `ole32!CoTaskMemFree` at `0x14000f8b0`
- `ole32!CoTaskMemFree` at `0x14000f8fc`
- `ole32!CoTaskMemFree` at `0x14000f8b0`
- `ole32!CoTaskMemFree` at `0x14000f8fc`

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
0x14000f828  push    rbx
0x14000f82a  sub     rsp, 60h
0x14000f82e  mov     rax, cs:__security_cookie
0x14000f835  xor     rax, rsp
0x14000f838  mov     [rsp+68h+var_18], rax
0x14000f83d  mov     rbx, rcx
0x14000f840  add     rcx, 0C0h; lpCriticalSection
0x14000f847  call    cs:__imp_EnterCriticalSection
0x14000f84e  nop     dword ptr [rax+rax+00h]
0x14000f853  inc     dword ptr [rbx+0E8h]
0x14000f859  test    dword ptr [rbx+40h], 100h
0x14000f860  jnz     short loc_14000F8BC
0x14000f862  mov     rcx, [rbx+0F0h]
0x14000f869  test    rcx, rcx
0x14000f86c  jz      loc_14000F908
0x14000f872  cmp     dword ptr [rbx+0E8h], 1
0x14000f879  jnz     loc_14000F908
0x14000f87f  mov     r8d, [rbx+0B8h]
0x14000f886  lea     r9, [rsp+68h+var_48]
0x14000f88b  xorps   xmm0, xmm0
0x14000f88e  mov     edx, 1
0x14000f893  movups  [rsp+68h+var_48], xmm0
0x14000f898  movups  xmmword ptr [rsp+68h+pv], xmm0
0x14000f89d  movups  [rsp+68h+var_28], xmm0
0x14000f8a2  call    TestQueryData
0x14000f8a7  mov     rcx, [rsp+68h+pv+8]; pv
0x14000f8ac  test    eax, eax
0x14000f8ae  jnz     short loc_14000F8D2
0x14000f8b0  call    cs:__imp_CoTaskMemFree
0x14000f8b7  nop     dword ptr [rax+rax+00h]
0x14000f8bc  xor     al, al
0x14000f8be  mov     rcx, [rsp+68h+var_18]
0x14000f8c3  xor     rcx, rsp; StackCookie
0x14000f8c6  call    __security_check_cookie
0x14000f8cb  add     rsp, 60h
0x14000f8cf  pop     rbx
0x14000f8d0  retn
0x14000f8d2  mov     eax, dword ptr [rsp+68h+pv+4]
0x14000f8d6  or      [rbx+40h], eax
0x14000f8d9  test    rcx, rcx
0x14000f8dc  jz      short loc_14000F8F2
0x14000f8de  lea     rdx, [rsp+68h+var_48]
0x14000f8e3  mov     rcx, rbx
0x14000f8e6  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x14000f8eb  mov     rcx, [rsp+68h+pv+8]
0x14000f8f0  jmp     short loc_14000F8FC
0x14000f8f2  mov     edx, dword ptr [rsp+68h+pv]
0x14000f8f6  mov     [rbx+0B8h], edx
0x14000f8fc  call    cs:__imp_CoTaskMemFree
0x14000f903  nop     dword ptr [rax+rax+00h]
0x14000f908  mov     al, 1
0x14000f90a  jmp     short loc_14000F8BE
```

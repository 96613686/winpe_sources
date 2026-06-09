# tip2::details::shared_data<1,0,0>::is_running(void)

- ea: `0x180005848`
- end: `0x180005948`
- name: `?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004d9c`

## callees

- `0x180003ae0`
- `0x180005848`
- `0x180005e00`
- `0x18008fe00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800058c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005925`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000593e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800058db`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000593e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000586e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000586e`

## pseudocode

```c
bool __fastcall tip2::details::shared_data<1,0,0>::is_running(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // eax
  void *v6; // rcx
  bool v8; // bl
  __int128 v9; // [rsp+20h] [rbp-48h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-38h]
  __int128 v11; // [rsp+40h] [rbp-28h]

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 192));
  v3 = *(_QWORD *)(a1 + 240);
  if ( !v3 || (*(_DWORD *)(a1 + 64) & 0x100) != 0 )
  {
LABEL_6:
    if ( v1 )
      LeaveCriticalSection(v1);
    return 0;
  }
  if ( !*(_DWORD *)(a1 + 232) )
  {
    v4 = *(unsigned int *)(a1 + 184);
    v9 = 0;
    *(_OWORD *)pv = 0;
    v11 = 0;
    v5 = ((__int64 (__fastcall *)(__int64, _QWORD, __int64, __int128 *))TestQueryData)(v3, 0, v4, &v9);
    v6 = pv[1];
    if ( !v5 )
    {
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      goto LABEL_6;
    }
    *(_DWORD *)(a1 + 64) |= HIDWORD(pv[0]);
    if ( v6 )
    {
      tip2::details::shared_data<1,0,0>::deserialize_data(a1, &v9);
      v6 = pv[1];
    }
    else
    {
      *(_DWORD *)(a1 + 184) = pv[0];
    }
    CoTaskMemFree(v6);
  }
  v8 = (*(_DWORD *)(a1 + 64) & 0x100) == 0;
  if ( v1 )
    LeaveCriticalSection(v1);
  return v8;
}

```

## disassembly

```asm
0x180005848  mov     [rsp+arg_8], rbx
0x18000584d  push    rdi
0x18000584e  sub     rsp, 60h
0x180005852  mov     rax, cs:__security_cookie
0x180005859  xor     rax, rsp
0x18000585c  mov     [rsp+68h+var_18], rax
0x180005861  lea     rdi, [rcx+0C0h]
0x180005868  mov     rbx, rcx
0x18000586b  mov     rcx, rdi; lpCriticalSection
0x18000586e  call    cs:__imp_EnterCriticalSection
0x180005874  mov     rcx, [rbx+0F0h]
0x18000587b  test    rcx, rcx
0x18000587e  jz      short loc_1800058D3
0x180005880  test    dword ptr [rbx+40h], 100h
0x180005887  jnz     short loc_1800058D3
0x180005889  cmp     dword ptr [rbx+0E8h], 0
0x180005890  jnz     loc_18000592B
0x180005896  mov     r8d, [rbx+0B8h]
0x18000589d  lea     r9, [rsp+68h+var_48]
0x1800058a2  xorps   xmm0, xmm0
0x1800058a5  xor     edx, edx
0x1800058a7  movups  [rsp+68h+var_48], xmm0
0x1800058ac  movups  xmmword ptr [rsp+68h+pv], xmm0
0x1800058b1  movups  [rsp+68h+var_28], xmm0
0x1800058b6  call    TestQueryData
0x1800058bb  mov     rcx, [rsp+68h+pv+8]; pv
0x1800058c0  test    eax, eax
0x1800058c2  jnz     short loc_1800058FB
0x1800058c4  call    cs:__imp_CoTaskMemFree
0x1800058ca  mov     [rsp+68h+pv+8], 0
0x1800058d3  test    rdi, rdi
0x1800058d6  jz      short loc_1800058E1
0x1800058d8  mov     rcx, rdi; lpCriticalSection
0x1800058db  call    cs:__imp_LeaveCriticalSection
0x1800058e1  xor     al, al
0x1800058e3  mov     rcx, [rsp+68h+var_18]
0x1800058e8  xor     rcx, rsp; StackCookie
0x1800058eb  call    __security_check_cookie
0x1800058f0  mov     rbx, [rsp+68h+arg_8]
0x1800058f5  add     rsp, 60h
0x1800058f9  pop     rdi
0x1800058fa  retn
0x1800058fb  mov     eax, dword ptr [rsp+68h+pv+4]
0x1800058ff  or      [rbx+40h], eax
0x180005902  test    rcx, rcx
0x180005905  jz      short loc_18000591B
0x180005907  lea     rdx, [rsp+68h+var_48]
0x18000590c  mov     rcx, rbx
0x18000590f  call    ?deserialize_data@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXAEBUTestInfo@TestInfo_ODR_guard@@@Z; tip2::details::shared_data<1,0,0>::deserialize_data(TestInfo_ODR_guard::TestInfo const &)
0x180005914  mov     rcx, [rsp+68h+pv+8]
0x180005919  jmp     short loc_180005925
0x18000591b  mov     eax, dword ptr [rsp+68h+pv]
0x18000591f  mov     [rbx+0B8h], eax
0x180005925  call    cs:__imp_CoTaskMemFree
0x18000592b  mov     ebx, [rbx+40h]
0x18000592e  shr     ebx, 8
0x180005931  not     bl
0x180005933  and     bl, 1
0x180005936  test    rdi, rdi
0x180005939  jz      short loc_180005944
0x18000593b  mov     rcx, rdi; lpCriticalSection
0x18000593e  call    cs:__imp_LeaveCriticalSection
0x180005944  mov     al, bl
0x180005946  jmp     short loc_1800058E3
```

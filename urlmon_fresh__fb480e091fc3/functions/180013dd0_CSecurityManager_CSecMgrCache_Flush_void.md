# CSecurityManager::CSecMgrCache::Flush(void)

- ea: `0x180013dd0`
- end: `0x180013fc1`
- name: `?Flush@CSecMgrCache@CSecurityManager@@QEAAXXZ`
- size: `497`
- prototype: `void __fastcall(CSecurityManager::CSecMgrCache *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180012d10`
- `0x180013034`
- `0x180013854`
- `0x180013bf4`
- `0x180016914`
- `0x180018f50`
- `0x18001b230`
- `0x18001bba0`
- `0x180024790`

## callees

- `0x180013dd0`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013efd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013df5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013df5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013f95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013fab`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f30`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f60`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f30`
- `OLEAUT32!__imp_SysFreeString` at `0x180013f60`

## pseudocode

```c
void __fastcall CSecurityManager::CSecMgrCache::Flush(CSecurityManager::CSecMgrCache *this)
{
  __int64 v2; // rsi
  __int64 v3; // rbp
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  char *v8; // rdi
  OLECHAR *v9; // r14
  OLECHAR *v10; // r14
  DWORD LastError; // ebx
  DWORD v12; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v2 = 0;
  v3 = 0;
  do
  {
    v4 = *(_QWORD *)((char *)this + v3 + 48);
    if ( v4 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *(_QWORD *)((char *)this + v3 + 48) = 0;
    }
    v5 = *(void **)((char *)this + v3 + 96);
    if ( v5 )
    {
      CoTaskMemFree(v5);
      *(_QWORD *)((char *)this + v3 + 96) = 0;
    }
    v6 = *(void **)((char *)this + v3 + 56);
    if ( v6 )
    {
      CoTaskMemFree(v6);
      *(_QWORD *)((char *)this + v3 + 56) = 0;
    }
    v7 = *(void **)((char *)this + v3 + 88);
    *(_DWORD *)((char *)this + v3 + 64) = 0;
    if ( v7 )
    {
      CoTaskMemFree(v7);
      *(_QWORD *)((char *)this + v3 + 88) = 0;
    }
    *(_DWORD *)((char *)this + v3 + 68) = -1;
    v8 = (char *)this + 32 * v2;
    *(_DWORD *)((char *)this + v3 + 76) = -1;
    *(_DWORD *)((char *)this + v3 + 80) = 0;
    v9 = (OLECHAR *)*((_QWORD *)v8 + 231);
    if ( v9 )
    {
      LastError = GetLastError();
      SysFreeString(v9);
      SetLastError(LastError);
    }
    *((_QWORD *)v8 + 231) = 0;
    v10 = (OLECHAR *)*((_QWORD *)v8 + 233);
    if ( v10 )
    {
      v12 = GetLastError();
      SysFreeString(v10);
      SetLastError(v12);
    }
    *((_QWORD *)v8 + 233) = 0;
    ++v2;
    v3 += 56;
    *((_DWORD *)v8 + 468) = -1;
    *((_DWORD *)v8 + 464) = 0;
    *((_DWORD *)v8 + 465) = -2147024891;
  }
  while ( v2 != 32 );
  *((_DWORD *)this + 460) = 0;
  *((_DWORD *)this + 718) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180013dd0  push    r12
0x180013dd2  push    r13
0x180013dd4  push    r15
0x180013dd6  sub     rsp, 30h
0x180013dda  mov     [rsp+48h+arg_8], rbp
0x180013ddf  mov     r15, rcx
0x180013de2  mov     [rsp+48h+arg_10], rsi
0x180013de7  add     rcx, 8; lpCriticalSection
0x180013deb  mov     [rsp+48h+var_20], rdi
0x180013df0  mov     [rsp+48h+var_28], r14
0x180013df5  call    cs:__imp_EnterCriticalSection
0x180013dfc  nop     dword ptr [rax+rax+00h]
0x180013e01  xor     r13d, r13d
0x180013e04  mov     [rsp+48h+arg_0], rbx
0x180013e09  mov     esi, r13d
0x180013e0c  mov     ebp, r13d
0x180013e0f  nop
0x180013e10  mov     rcx, [r15+rbp+30h]
0x180013e15  test    rcx, rcx
0x180013e18  jnz     loc_180013F09
0x180013e1e  mov     rcx, [r15+rbp+60h]; pv
0x180013e23  test    rcx, rcx
0x180013e26  jnz     loc_180013F95
0x180013e2c  mov     rcx, [r15+rbp+38h]; pv
0x180013e31  test    rcx, rcx
0x180013e34  jnz     loc_180013F7F
0x180013e3a  mov     rcx, [r15+rbp+58h]; pv
0x180013e3f  mov     [r15+rbp+40h], r13d
0x180013e44  test    rcx, rcx
0x180013e47  jnz     loc_180013FAB
0x180013e4d  mov     rdi, rsi
0x180013e50  mov     dword ptr [r15+rbp+44h], 0FFFFFFFFh
0x180013e59  shl     rdi, 5
0x180013e5d  add     rdi, r15
0x180013e60  mov     dword ptr [r15+rbp+4Ch], 0FFFFFFFFh
0x180013e69  mov     [r15+rbp+50h], r13d
0x180013e6e  mov     r14, [rdi+738h]
0x180013e75  test    r14, r14
0x180013e78  jnz     loc_180013F1F
0x180013e7e  mov     [rdi+738h], r13
0x180013e85  mov     r14, [rdi+748h]
0x180013e8c  test    r14, r14
0x180013e8f  jnz     loc_180013F4F
0x180013e95  mov     [rdi+748h], r13
0x180013e9c  inc     rsi
0x180013e9f  add     rbp, 38h ; '8'
0x180013ea3  mov     dword ptr [rdi+750h], 0FFFFFFFFh
0x180013ead  mov     [rdi+740h], r13d
0x180013eb4  mov     dword ptr [rdi+744h], 80070005h
0x180013ebe  cmp     rsi, 20h ; ' '
0x180013ec2  jnz     loc_180013E10
0x180013ec8  mov     r14, [rsp+48h+var_28]
0x180013ecd  lea     rcx, [r15+8]
0x180013ed1  mov     rdi, [rsp+48h+var_20]
0x180013ed6  mov     rsi, [rsp+48h+arg_10]
0x180013edb  mov     rbp, [rsp+48h+arg_8]
0x180013ee0  mov     rbx, [rsp+48h+arg_0]
0x180013ee5  mov     [r15+730h], r13d
0x180013eec  mov     [r15+0B38h], r13d
0x180013ef3  add     rsp, 30h
0x180013ef7  pop     r15
0x180013ef9  pop     r13
0x180013efb  pop     r12
0x180013efd  jmp     cs:__imp_LeaveCriticalSection
0x180013f09  mov     rax, [rcx]
0x180013f0c  mov     rax, [rax+10h]
0x180013f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f15  mov     [r15+rbp+30h], r13
0x180013f1a  jmp     loc_180013E1E
0x180013f1f  call    cs:__imp_GetLastError
0x180013f26  nop     dword ptr [rax+rax+00h]
0x180013f2b  mov     rcx, r14; bstrString
0x180013f2e  mov     ebx, eax
0x180013f30  call    cs:__imp_SysFreeString
0x180013f37  nop     dword ptr [rax+rax+00h]
0x180013f3c  mov     ecx, ebx; dwErrCode
0x180013f3e  call    cs:__imp_SetLastError
0x180013f45  nop     dword ptr [rax+rax+00h]
0x180013f4a  jmp     loc_180013E7E
0x180013f4f  call    cs:__imp_GetLastError
0x180013f56  nop     dword ptr [rax+rax+00h]
0x180013f5b  mov     rcx, r14; bstrString
0x180013f5e  mov     ebx, eax
0x180013f60  call    cs:__imp_SysFreeString
0x180013f67  nop     dword ptr [rax+rax+00h]
0x180013f6c  mov     ecx, ebx; dwErrCode
0x180013f6e  call    cs:__imp_SetLastError
0x180013f75  nop     dword ptr [rax+rax+00h]
0x180013f7a  jmp     loc_180013E95
0x180013f7f  call    cs:__imp_CoTaskMemFree
0x180013f86  nop     dword ptr [rax+rax+00h]
0x180013f8b  mov     [r15+rbp+38h], r13
0x180013f90  jmp     loc_180013E3A
0x180013f95  call    cs:__imp_CoTaskMemFree
0x180013f9c  nop     dword ptr [rax+rax+00h]
0x180013fa1  mov     [r15+rbp+60h], r13
0x180013fa6  jmp     loc_180013E2C
0x180013fab  call    cs:__imp_CoTaskMemFree
0x180013fb2  nop     dword ptr [rax+rax+00h]
0x180013fb7  mov     [r15+rbp+58h], r13
0x180013fbc  jmp     loc_180013E4D
```

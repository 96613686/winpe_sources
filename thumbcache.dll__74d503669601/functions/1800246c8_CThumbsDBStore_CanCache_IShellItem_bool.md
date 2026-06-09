# CThumbsDBStore::CanCache(IShellItem *,bool *)

- ea: `0x1800246c8`
- end: `0x18002486c`
- name: `?CanCache@CThumbsDBStore@@QEAAHPEAUIShellItem@@PEA_N@Z`
- size: `420`
- prototype: `_BOOL8 __fastcall(CThumbsDBStore *this, struct IShellItem *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x18001f760`
- `0x1800246c8`
- `0x180024908`
- `0x180035830`
- `0x180035860`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180024785`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180024785`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024797`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024797`

## pseudocode

```c
_BOOL8 __fastcall CThumbsDBStore::CanCache(CThumbsDBStore *this, struct IShellItem *a2, bool *a3)
{
  BOOL v3; // ebx
  _DWORD *v7; // rsi
  struct IShellItemVtbl *lpVtbl; // rax
  __int64 *v9; // rsi
  __int64 v10; // rax
  CGlobalThumbsDBStore *v12; // rax
  CGlobalThumbsDBStore *v13; // rax
  CGlobalThumbsDBStore *v14; // rax
  unsigned int v15; // edx
  __int64 v16; // rax
  LPCWSTR pszPath; // [rsp+20h] [rbp-20h] BYREF
  __int64 *v18; // [rsp+28h] [rbp-18h] BYREF
  int v19; // [rsp+30h] [rbp-10h] BYREF
  int v20; // [rsp+34h] [rbp-Ch] BYREF

  v3 = 0;
  if ( !*(_QWORD *)this )
  {
    if ( !g_pThumbsDBStore )
    {
      v13 = (CGlobalThumbsDBStore *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v13 )
      {
        v14 = CGlobalThumbsDBStore::CGlobalThumbsDBStore(v13);
        if ( v14 )
        {
          if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pThumbsDBStore, (signed __int64)v14, 0) )
            CGlobalThumbsDBStore::`scalar deleting destructor'(v14, v15);
        }
      }
    }
    v12 = g_pThumbsDBStore;
    *(_QWORD *)this = g_pThumbsDBStore;
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)v12 + 1);
  }
  v7 = *(_DWORD **)this;
  if ( v7 )
  {
    lpVtbl = a2->lpVtbl;
    v18 = 0;
    if ( ((__int64 (__fastcall *)(struct IShellItem *, GUID *, __int64 **))lpVtbl->QueryInterface)(
           a2,
           &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
           &v18) >= 0 )
    {
      if ( a3 )
        *a3 = 0;
      if ( *v7 )
      {
        v9 = v18;
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64 *, __int64, int *))(*v18 + 48))(v18, 0x20000000, &v19) >= 0
          && v19 != 0x20000000 )
        {
          v10 = *v9;
          pszPath = 0;
          if ( (*(int (__fastcall **)(__int64 *, __int64, LPCWSTR *))(v10 + 40))(v9, 2147844096LL, &pszPath) >= 0 )
          {
            if ( PathIsNetworkPathW(pszPath) )
            {
              if ( a3 )
                *a3 = 1;
              v16 = *v9;
              v20 = 0;
              v3 = 1;
              if ( (*(int (__fastcall **)(__int64 *, const PROPERTYKEY *, int *))(v16 + 144))(
                     v9,
                     &PKEY_OfflineAvailability,
                     &v20) >= 0 )
                v3 = v20 != 2;
            }
            CoTaskMemFree((LPVOID)pszPath);
          }
        }
      }
      (*(void (__fastcall **)(__int64 *))(*v18 + 16))(v18);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800246c8  push    rbp
0x1800246ca  push    rbx
0x1800246cb  push    rsi
0x1800246cc  push    rdi
0x1800246cd  push    r14
0x1800246cf  mov     rbp, rsp
0x1800246d2  sub     rsp, 40h
0x1800246d6  mov     rax, cs:__security_cookie
0x1800246dd  xor     rax, rsp
0x1800246e0  mov     [rbp+var_8], rax
0x1800246e4  xor     ebx, ebx
0x1800246e6  mov     rdi, r8
0x1800246e9  mov     r14, rdx
0x1800246ec  mov     rsi, rcx
0x1800246ef  cmp     [rcx], rbx
0x1800246f2  jz      loc_1800247C6
0x1800246f8  mov     rsi, [rsi]
0x1800246fb  test    rsi, rsi
0x1800246fe  jz      loc_1800247AD
0x180024704  mov     rax, [r14]
0x180024707  lea     r8, [rbp+var_18]
0x18002470b  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180024712  mov     [rbp+var_18], rbx
0x180024716  mov     rcx, r14
0x180024719  mov     rax, [rax]
0x18002471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024721  test    eax, eax
0x180024723  js      loc_1800247AD
0x180024729  test    rdi, rdi
0x18002472c  jz      short loc_180024730
0x18002472e  mov     [rdi], bl
0x180024730  cmp     [rsi], ebx
0x180024732  jz      short loc_18002479D
0x180024734  mov     rsi, [rbp+var_18]
0x180024738  lea     r8, [rbp+var_10]
0x18002473c  mov     r14d, 20000000h
0x180024742  mov     [rbp+var_10], ebx
0x180024745  mov     edx, r14d
0x180024748  mov     rcx, rsi
0x18002474b  mov     rax, [rsi]
0x18002474e  mov     rax, [rax+30h]
0x180024752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024757  test    eax, eax
0x180024759  js      short loc_18002479D
0x18002475b  cmp     [rbp+var_10], r14d
0x18002475f  jz      short loc_18002479D
0x180024761  mov     rax, [rsi]
0x180024764  lea     r8, [rbp+pszPath]
0x180024768  mov     edx, 80058000h
0x18002476d  mov     [rbp+pszPath], rbx
0x180024771  mov     rcx, rsi
0x180024774  mov     rax, [rax+28h]
0x180024778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002477d  test    eax, eax
0x18002477f  js      short loc_18002479D
0x180024781  mov     rcx, [rbp+pszPath]; pszPath
0x180024785  call    cs:__imp_PathIsNetworkPathW
0x18002478b  test    eax, eax
0x18002478d  jnz     loc_180024825
0x180024793  mov     rcx, [rbp+pszPath]; pv
0x180024797  call    cs:__imp_CoTaskMemFree
0x18002479d  mov     rcx, [rbp+var_18]
0x1800247a1  mov     rdx, [rcx]
0x1800247a4  mov     rax, [rdx+10h]
0x1800247a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247ad  mov     eax, ebx
0x1800247af  mov     rcx, [rbp+var_8]
0x1800247b3  xor     rcx, rsp; StackCookie
0x1800247b6  call    __security_check_cookie
0x1800247bb  add     rsp, 40h
0x1800247bf  pop     r14
0x1800247c1  pop     rdi
0x1800247c2  pop     rsi
0x1800247c3  pop     rbx
0x1800247c4  pop     rbp
0x1800247c5  retn
0x1800247c6  cmp     cs:?g_pThumbsDBStore@@3PEAVCGlobalThumbsDBStore@@EA, rbx; CGlobalThumbsDBStore * g_pThumbsDBStore
0x1800247cd  jz      short loc_1800247EB
0x1800247cf  mov     rax, cs:?g_pThumbsDBStore@@3PEAVCGlobalThumbsDBStore@@EA; CGlobalThumbsDBStore * g_pThumbsDBStore
0x1800247d6  mov     [rsi], rax
0x1800247d9  test    rax, rax
0x1800247dc  jz      loc_1800246F8
0x1800247e2  lock inc dword ptr [rax+4]
0x1800247e6  jmp     loc_1800246F8
0x1800247eb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800247f2  mov     ecx, 30h ; '0'; unsigned __int64
0x1800247f7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800247fc  test    rax, rax
0x1800247ff  jz      short loc_1800247CF
0x180024801  mov     rcx, rax; this
0x180024804  call    ??0CGlobalThumbsDBStore@@QEAA@XZ; CGlobalThumbsDBStore::CGlobalThumbsDBStore(void)
0x180024809  mov     rcx, rax; this
0x18002480c  test    rax, rax
0x18002480f  jz      short loc_1800247CF
0x180024811  xor     eax, eax
0x180024813  lock cmpxchg cs:?g_pThumbsDBStore@@3PEAVCGlobalThumbsDBStore@@EA, rcx; CGlobalThumbsDBStore * g_pThumbsDBStore
0x18002481c  jz      short loc_1800247CF
0x18002481e  call    ??_GCGlobalThumbsDBStore@@QEAAPEAXI@Z; CGlobalThumbsDBStore::`scalar deleting destructor'(uint)
0x180024823  jmp     short loc_1800247CF
0x180024825  test    rdi, rdi
0x180024828  jz      short loc_18002482D
0x18002482a  mov     byte ptr [rdi], 1
0x18002482d  mov     rax, [rsi]
0x180024830  lea     r8, [rbp+var_C]
0x180024834  lea     rdx, PKEY_OfflineAvailability
0x18002483b  mov     [rbp+var_C], 0
0x180024842  mov     rcx, rsi
0x180024845  mov     ebx, 1
0x18002484a  mov     rax, [rax+90h]
0x180024851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024856  test    eax, eax
0x180024858  js      loc_180024793
0x18002485e  xor     eax, eax
0x180024860  cmp     [rbp+var_C], 2
0x180024864  cmovz   ebx, eax
0x180024867  jmp     loc_180024793
```

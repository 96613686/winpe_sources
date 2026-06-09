# CGlobalThumbsDBStore::CanCache(IShellItem2 *,bool *)

- ea: `0x180025004`
- end: `0x1800250ff`
- name: `?CanCache@CGlobalThumbsDBStore@@QEAAHPEAUIShellItem2@@PEA_N@Z`
- size: `251`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024cbc`

## callees

- `0x180025004`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180025089`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathIsNetworkPathW` at `0x180025089`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025098`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025098`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::CanCache(CGlobalThumbsDBStore *this, struct IShellItem2 *a2, bool *a3)
{
  unsigned int v5; // ebx
  struct IShellItem2Vtbl *lpVtbl; // rax
  struct IShellItem2Vtbl *v7; // rax
  struct IShellItem2Vtbl *v9; // rax
  LPCWSTR pszPath; // [rsp+20h] [rbp-28h] BYREF
  int v11; // [rsp+28h] [rbp-20h] BYREF
  int v12; // [rsp+2Ch] [rbp-1Ch] BYREF

  if ( a3 )
    *a3 = 0;
  v5 = 0;
  if ( *(_DWORD *)this )
  {
    lpVtbl = a2->lpVtbl;
    v11 = 0;
    if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, int *))lpVtbl->GetAttributes)(a2, 0x20000000, &v11) >= 0
      && v11 != 0x20000000 )
    {
      v7 = a2->lpVtbl;
      pszPath = 0;
      if ( ((int (__fastcall *)(struct IShellItem2 *, __int64, LPCWSTR *))v7->GetDisplayName)(
             a2,
             2147844096LL,
             &pszPath) >= 0 )
      {
        if ( PathIsNetworkPathW(pszPath) )
        {
          v5 = 1;
          if ( a3 )
            *a3 = 1;
          v9 = a2->lpVtbl;
          v12 = 0;
          if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, int *))v9->GetUInt32)(
                 a2,
                 &PKEY_OfflineAvailability,
                 &v12) >= 0
            && v12 == 2 )
          {
            v5 = 0;
          }
        }
        CoTaskMemFree((LPVOID)pszPath);
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180025004  mov     [rsp+arg_0], rbx
0x180025009  mov     [rsp+arg_18], rsi
0x18002500e  push    rdi
0x18002500f  sub     rsp, 40h
0x180025013  mov     rax, cs:__security_cookie
0x18002501a  xor     rax, rsp
0x18002501d  mov     [rsp+48h+var_18], rax
0x180025022  mov     rdi, r8
0x180025025  mov     rsi, rdx
0x180025028  test    r8, r8
0x18002502b  jz      short loc_180025031
0x18002502d  mov     byte ptr [r8], 0
0x180025031  xor     ebx, ebx
0x180025033  cmp     [rcx], ebx
0x180025035  jz      short loc_18002509E
0x180025037  mov     rax, [rdx]
0x18002503a  lea     r8, [rsp+48h+var_20]
0x18002503f  mov     edx, 20000000h
0x180025044  mov     [rsp+48h+var_20], ebx
0x180025048  mov     rcx, rsi
0x18002504b  mov     rax, [rax+30h]
0x18002504f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025054  test    eax, eax
0x180025056  js      short loc_18002509E
0x180025058  cmp     [rsp+48h+var_20], 20000000h
0x180025060  jz      short loc_18002509E
0x180025062  mov     rax, [rsi]
0x180025065  lea     r8, [rsp+48h+pszPath]
0x18002506a  mov     edx, 80058000h
0x18002506f  mov     [rsp+48h+pszPath], rbx
0x180025074  mov     rcx, rsi
0x180025077  mov     rax, [rax+28h]
0x18002507b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025080  test    eax, eax
0x180025082  js      short loc_18002509E
0x180025084  mov     rcx, [rsp+48h+pszPath]; pszPath
0x180025089  call    cs:__imp_PathIsNetworkPathW
0x18002508f  test    eax, eax
0x180025091  jnz     short loc_1800250BD
0x180025093  mov     rcx, [rsp+48h+pszPath]; pv
0x180025098  call    cs:__imp_CoTaskMemFree
0x18002509e  mov     eax, ebx
0x1800250a0  mov     rcx, [rsp+48h+var_18]
0x1800250a5  xor     rcx, rsp; StackCookie
0x1800250a8  call    __security_check_cookie
0x1800250ad  mov     rbx, [rsp+48h+arg_0]
0x1800250b2  mov     rsi, [rsp+48h+arg_18]
0x1800250b7  add     rsp, 40h
0x1800250bb  pop     rdi
0x1800250bc  retn
0x1800250bd  mov     ebx, 1
0x1800250c2  test    rdi, rdi
0x1800250c5  jz      short loc_1800250C9
0x1800250c7  mov     [rdi], bl
0x1800250c9  mov     rax, [rsi]
0x1800250cc  lea     r8, [rsp+48h+var_1C]
0x1800250d1  lea     rdx, PKEY_OfflineAvailability
0x1800250d8  mov     [rsp+48h+var_1C], 0
0x1800250e0  mov     rcx, rsi
0x1800250e3  mov     rax, [rax+90h]
0x1800250ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800250ef  test    eax, eax
0x1800250f1  js      short loc_180025093
0x1800250f3  xor     ecx, ecx
0x1800250f5  cmp     [rsp+48h+var_1C], 2
0x1800250fa  cmovz   ebx, ecx
0x1800250fd  jmp     short loc_180025093
```

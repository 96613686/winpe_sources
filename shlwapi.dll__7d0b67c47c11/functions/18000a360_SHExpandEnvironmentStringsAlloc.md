# SHExpandEnvironmentStringsAlloc

- ea: `0x18000a360`
- end: `0x18000a476`
- name: `SHExpandEnvironmentStringsAlloc`
- size: `278`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000a360`
- `0x18000a47c`
- `0x18000eaf0`
- `0x18000eb1c`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a3de`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a41e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a3de`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000a41e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a446`

## pseudocode

```c
__int64 __fastcall SHExpandEnvironmentStringsAlloc(WCHAR *lpSrc, LPWSTR *a2)
{
  int Error; // ebx
  LPWSTR v5; // rdi
  DWORD v6; // esi
  __int64 v7; // rcx
  int v8; // eax
  DWORD v9; // eax
  LPWSTR lpDst[2]; // [rsp+20h] [rbp-48h] BYREF

  *a2 = 0;
  lpDst[0] = 0;
  lpDst[1] = 0;
  if ( !is_mul_ok(0x104u, 2u) )
    return (unsigned int)-2147024362;
  Error = CTCoAllocPolicy::Alloc(lpSrc, 1u, 0x208u, (void **)lpDst);
  if ( Error >= 0 )
  {
    v5 = lpDst[0];
    v6 = ExpandEnvironmentStringsW(lpSrc, lpDst[0], 0x104u);
    if ( !v6 )
      goto LABEL_9;
    if ( v6 <= 0x104 )
      goto LABEL_10;
    CoTaskMemFree(v5);
    v8 = _AllocArray<unsigned short,CTCoAllocPolicy>(v7, 1, v6, lpDst);
    v5 = lpDst[0];
    Error = v8;
    if ( v8 < 0 )
    {
LABEL_11:
      CoTaskMemFree(v5);
      return (unsigned int)Error;
    }
    v9 = ExpandEnvironmentStringsW(lpSrc, lpDst[0], v6);
    if ( v9 )
    {
      if ( v9 > v6 )
      {
        Error = -2147418113;
        goto LABEL_11;
      }
    }
    else
    {
LABEL_9:
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_11;
    }
LABEL_10:
    *a2 = v5;
    v5 = 0;
    goto LABEL_11;
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a360  mov     r11, rsp
0x18000a363  mov     [r11+18h], rbx
0x18000a367  push    rbp
0x18000a368  push    rsi
0x18000a369  push    rdi
0x18000a36a  push    r12
0x18000a36c  push    r14
0x18000a36e  sub     rsp, 40h
0x18000a372  mov     rax, cs:__security_cookie
0x18000a379  xor     rax, rsp
0x18000a37c  mov     [rsp+68h+var_38], rax
0x18000a381  mov     eax, 2
0x18000a386  mov     qword ptr [rdx], 0
0x18000a38d  mov     r12d, 104h
0x18000a393  mov     qword ptr [r11-48h], 0
0x18000a39b  mov     r14, rdx
0x18000a39e  mov     qword ptr [r11-40h], 0
0x18000a3a6  mul     r12
0x18000a3a9  mov     rbp, rcx
0x18000a3ac  test    rdx, rdx
0x18000a3af  jnz     loc_18000A44E
0x18000a3b5  lea     r9, [r11-48h]; void **
0x18000a3b9  mov     r8, rax; unsigned __int64
0x18000a3bc  mov     edx, 1; unsigned int
0x18000a3c1  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18000a3c6  mov     ebx, eax
0x18000a3c8  test    eax, eax
0x18000a3ca  js      loc_18000A453
0x18000a3d0  mov     rdi, [rsp+68h+lpDst]
0x18000a3d5  mov     r8d, r12d; nSize
0x18000a3d8  mov     rdx, rdi; lpDst
0x18000a3db  mov     rcx, rbp; lpSrc
0x18000a3de  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a3e4  mov     esi, eax
0x18000a3e6  test    eax, eax
0x18000a3e8  jz      short loc_18000A433
0x18000a3ea  cmp     esi, r12d
0x18000a3ed  jbe     short loc_18000A43E
0x18000a3ef  mov     rcx, rdi; pv
0x18000a3f2  call    cs:__imp_CoTaskMemFree
0x18000a3f8  mov     r8d, esi
0x18000a3fb  lea     r9, [rsp+68h+lpDst]
0x18000a400  mov     edx, 1
0x18000a405  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x18000a40a  mov     rdi, [rsp+68h+lpDst]
0x18000a40f  mov     ebx, eax
0x18000a411  test    eax, eax
0x18000a413  js      short loc_18000A443
0x18000a415  mov     r8d, esi; nSize
0x18000a418  mov     rdx, rdi; lpDst
0x18000a41b  mov     rcx, rbp; lpSrc
0x18000a41e  call    cs:__imp_ExpandEnvironmentStringsW
0x18000a424  test    eax, eax
0x18000a426  jz      short loc_18000A433
0x18000a428  cmp     eax, esi
0x18000a42a  jbe     short loc_18000A43E
0x18000a42c  mov     ebx, 8000FFFFh
0x18000a431  jmp     short loc_18000A443
0x18000a433  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18000a438  mov     ebx, eax
0x18000a43a  test    eax, eax
0x18000a43c  js      short loc_18000A443
0x18000a43e  mov     [r14], rdi
0x18000a441  xor     edi, edi
0x18000a443  mov     rcx, rdi; pv
0x18000a446  call    cs:__imp_CoTaskMemFree
0x18000a44c  jmp     short loc_18000A453
0x18000a44e  mov     ebx, 80070216h
0x18000a453  mov     eax, ebx
0x18000a455  mov     rcx, [rsp+68h+var_38]
0x18000a45a  xor     rcx, rsp; StackCookie
0x18000a45d  call    __security_check_cookie
0x18000a462  mov     rbx, [rsp+68h+arg_10]
0x18000a46a  add     rsp, 40h
0x18000a46e  pop     r14
0x18000a470  pop     r12
0x18000a472  pop     rdi
0x18000a473  pop     rsi
0x18000a474  pop     rbp
0x18000a475  retn
```

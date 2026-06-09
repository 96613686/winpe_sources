# CGlobalThumbsDBStore::_GetFileHash(IShellItem2 *,unsigned __int64 *)

- ea: `0x180044c24`
- end: `0x180044d6e`
- name: `?_GetFileHash@CGlobalThumbsDBStore@@AEAAJPEAUIShellItem2@@PEA_K@Z`
- size: `330`
- prototype: `__int64 __fastcall(CGlobalThumbsDBStore *__hidden this, struct IShellItem2 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800249d0`
- `0x1800443fc`

## callees

- `0x180034f08`
- `0x180035830`
- `0x180044c24`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ce3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044ce3`

## pseudocode

```c
__int64 __fastcall CGlobalThumbsDBStore::_GetFileHash(
        CGlobalThumbsDBStore *this,
        struct IShellItem2 *a2,
        unsigned __int64 *a3)
{
  struct IShellItem2Vtbl *lpVtbl; // rax
  int v6; // edi
  struct IShellItem2Vtbl *v7; // rax
  __int64 v8; // r8
  LPVOID v9; // rdx
  struct IShellItem2Vtbl *v10; // rax
  const unsigned __int8 *v11; // rdx
  struct IShellItem2Vtbl *v12; // rax
  unsigned __int8 *v14; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int8 v15[8]; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int8 v16[8]; // [rsp+30h] [rbp-10h] BYREF

  *a3 = 0xBBA03D3F2F654661uLL;
  lpVtbl = a2->lpVtbl;
  *(_QWORD *)v15 = 0;
  if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, unsigned __int8 *))lpVtbl->GetUInt64)(
         a2,
         &PKEY_FileFRN,
         v15) < 0 )
  {
    v7 = a2->lpVtbl;
    v14 = 0;
    v6 = ((__int64 (__fastcall *)(struct IShellItem2 *, __int64, unsigned __int8 **))v7->GetDisplayName)(
           a2,
           2147581953LL,
           &v14);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)&v14[2 * v8] );
    *a3 = CalculateHashKey(*a3, v14, 2 * (int)v8);
    CoTaskMemFree(v9);
  }
  else
  {
    v6 = 0;
    *a3 = CalculateHashKey(*a3, v15, 8u);
  }
  v10 = a2->lpVtbl;
  v14 = 0;
  if ( ((int (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, unsigned __int8 **))v10->GetFileTime)(
         a2,
         &PKEY_DateModified,
         &v14) >= 0 )
  {
    v11 = (const unsigned __int8 *)&v14;
LABEL_11:
    *a3 = CalculateHashKey(*a3, v11, 8u);
    return (unsigned int)v6;
  }
  v12 = a2->lpVtbl;
  *(_QWORD *)v16 = 0;
  v6 = ((__int64 (__fastcall *)(struct IShellItem2 *, const PROPERTYKEY *, unsigned __int8 *))v12->GetUInt64)(
         a2,
         &PKEY_Size,
         v16);
  if ( v6 >= 0 )
  {
    v11 = v16;
    goto LABEL_11;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180044c24  mov     [rsp-18h+arg_0], rbx
0x180044c29  mov     [rsp-18h+arg_18], rsi
0x180044c2e  push    rbp
0x180044c2f  push    rdi
0x180044c30  push    r14
0x180044c32  mov     rbp, rsp
0x180044c35  sub     rsp, 40h
0x180044c39  mov     rax, cs:__security_cookie
0x180044c40  xor     rax, rsp
0x180044c43  mov     [rbp+var_8], rax
0x180044c47  mov     rsi, rdx
0x180044c4a  mov     rax, 0BBA03D3F2F654661h
0x180044c54  mov     [r8], rax
0x180044c57  mov     rbx, r8
0x180044c5a  mov     rax, [rdx]
0x180044c5d  lea     r8, [rbp+var_18]
0x180044c61  xor     r14d, r14d
0x180044c64  lea     rdx, PKEY_FileFRN
0x180044c6b  mov     rcx, rsi
0x180044c6e  mov     qword ptr [rbp+var_18], r14
0x180044c72  mov     rax, [rax+98h]
0x180044c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044c7e  test    eax, eax
0x180044c80  js      short loc_180044C9A
0x180044c82  mov     rcx, [rbx]; unsigned __int64
0x180044c85  lea     r8d, [r14+8]; unsigned int
0x180044c89  lea     rdx, [rbp+var_18]; unsigned __int8 *
0x180044c8d  mov     edi, r14d
0x180044c90  call    ?CalculateHashKey@@YA_K_KPEBEI@Z; CalculateHashKey(unsigned __int64,uchar const *,uint)
0x180044c95  mov     [rbx], rax
0x180044c98  jmp     short loc_180044CE9
0x180044c9a  mov     rax, [rsi]
0x180044c9d  lea     r8, [rbp+var_20]
0x180044ca1  mov     edx, 80018001h
0x180044ca6  mov     [rbp+var_20], r14
0x180044caa  mov     rcx, rsi
0x180044cad  mov     rax, [rax+28h]
0x180044cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044cb6  mov     edi, eax
0x180044cb8  test    eax, eax
0x180044cba  js      loc_180044D4D
0x180044cc0  mov     rdx, [rbp+var_20]; unsigned __int8 *
0x180044cc4  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044cc8  inc     r8
0x180044ccb  cmp     [rdx+r8*2], r14w
0x180044cd0  jnz     short loc_180044CC8
0x180044cd2  mov     rcx, [rbx]; unsigned __int64
0x180044cd5  add     r8d, r8d; unsigned int
0x180044cd8  call    ?CalculateHashKey@@YA_K_KPEBEI@Z; CalculateHashKey(unsigned __int64,uchar const *,uint)
0x180044cdd  mov     rcx, rdx; pv
0x180044ce0  mov     [rbx], rax
0x180044ce3  call    cs:__imp_CoTaskMemFree
0x180044ce9  mov     rax, [rsi]
0x180044cec  lea     r8, [rbp+var_20]
0x180044cf0  lea     rdx, PKEY_DateModified
0x180044cf7  mov     [rbp+var_20], r14
0x180044cfb  mov     rcx, rsi
0x180044cfe  mov     rax, [rax+78h]
0x180044d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d07  test    eax, eax
0x180044d09  js      short loc_180044D11
0x180044d0b  lea     rdx, [rbp+var_20]
0x180044d0f  jmp     short loc_180044D3C
0x180044d11  mov     rax, [rsi]
0x180044d14  lea     r8, [rbp+var_10]
0x180044d18  lea     rdx, PKEY_Size
0x180044d1f  mov     qword ptr [rbp+var_10], r14
0x180044d23  mov     rcx, rsi
0x180044d26  mov     rax, [rax+98h]
0x180044d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044d32  mov     edi, eax
0x180044d34  test    eax, eax
0x180044d36  js      short loc_180044D4D
0x180044d38  lea     rdx, [rbp+var_10]; unsigned __int8 *
0x180044d3c  mov     rcx, [rbx]; unsigned __int64
0x180044d3f  mov     r8d, 8; unsigned int
0x180044d45  call    ?CalculateHashKey@@YA_K_KPEBEI@Z; CalculateHashKey(unsigned __int64,uchar const *,uint)
0x180044d4a  mov     [rbx], rax
0x180044d4d  mov     eax, edi
0x180044d4f  mov     rcx, [rbp+var_8]
0x180044d53  xor     rcx, rsp; StackCookie
0x180044d56  call    __security_check_cookie
0x180044d5b  mov     rbx, [rsp+40h+arg_0]
0x180044d60  mov     rsi, [rsp+40h+arg_18]
0x180044d65  add     rsp, 40h
0x180044d69  pop     r14
0x180044d6b  pop     rdi
0x180044d6c  pop     rbp
0x180044d6d  retn
```

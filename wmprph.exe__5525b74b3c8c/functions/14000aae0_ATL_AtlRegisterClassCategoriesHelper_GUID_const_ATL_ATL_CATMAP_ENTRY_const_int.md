# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x14000aae0`
- end: `0x14000ac04`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `292`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000ccb8`

## callees

- `0x140001390`
- `0x14000aae0`
- `0x14000f010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14000ab40`
- `ole32!CoCreateInstance` at `0x14000ab40`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(
        const struct _GUID *a1,
        const struct ATL::_ATL_CATMAP_ENTRY *a2,
        int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rax
  int v11; // ecx
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int128 v13; // [rsp+38h] [rbp-18h] BYREF

  ppv = 0;
  v4 = a2;
  v13 = 0;
  if ( a2 )
  {
    if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &IID_ICatRegister, &ppv) >= 0 )
    {
      while ( 1 )
      {
        v11 = *(_DWORD *)v4;
        if ( !*(_DWORD *)v4 )
          break;
        v13 = *(_OWORD *)*((_QWORD *)v4 + 1);
        if ( a3 )
        {
          v7 = *(_QWORD *)ppv;
          if ( v11 == 1 )
            v8 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v7 + 40))(
                   ppv,
                   a1,
                   1,
                   &v13);
          else
            v8 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v7 + 56))(
                   ppv,
                   a1,
                   1,
                   &v13);
          v9 = v8;
          if ( v8 < 0 )
          {
            if ( ppv )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            return v9;
          }
        }
        else
        {
          v10 = *(_QWORD *)ppv;
          if ( v11 == 1 )
            (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v10 + 48))(ppv, a1, 1, &v13);
          else
            (*(void (__fastcall **)(LPVOID, const struct _GUID *, __int64, __int128 *))(v10 + 64))(ppv, a1, 1, &v13);
        }
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
      }
    }
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return 0;
}

```

## disassembly

```asm
0x14000aae0  mov     [rsp-28h+arg_10], rbx
0x14000aae5  push    rbp
0x14000aae6  push    rsi
0x14000aae7  push    rdi
0x14000aae8  push    r14
0x14000aaea  push    r15
0x14000aaec  mov     rbp, rsp
0x14000aaef  sub     rsp, 50h
0x14000aaf3  mov     rax, cs:__security_cookie
0x14000aafa  xor     rax, rsp
0x14000aafd  mov     [rbp+var_8], rax
0x14000ab01  mov     [rbp+var_20], 0
0x14000ab09  xorps   xmm0, xmm0
0x14000ab0c  mov     r14d, r8d
0x14000ab0f  mov     rbx, rdx
0x14000ab12  mov     rsi, rcx
0x14000ab15  movups  [rbp+var_18], xmm0
0x14000ab19  test    rdx, rdx
0x14000ab1c  jz      short loc_14000AB63
0x14000ab1e  lea     rax, [rbp+var_20]
0x14000ab22  mov     r15d, 1
0x14000ab28  mov     r8d, r15d; dwClsContext
0x14000ab2b  mov     [rsp+50h+ppv], rax; ppv
0x14000ab30  lea     r9, IID_ICatRegister; riid
0x14000ab37  xor     edx, edx; pUnkOuter
0x14000ab39  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x14000ab40  call    cs:__imp_CoCreateInstance
0x14000ab46  test    eax, eax
0x14000ab48  jns     loc_14000ABF9
0x14000ab4e  mov     rcx, [rbp+var_20]
0x14000ab52  test    rcx, rcx
0x14000ab55  jz      short loc_14000AB63
0x14000ab57  mov     rax, [rcx]
0x14000ab5a  mov     rax, [rax+10h]
0x14000ab5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ab63  xor     eax, eax
0x14000ab65  mov     rcx, [rbp+var_8]
0x14000ab69  xor     rcx, rsp; StackCookie
0x14000ab6c  call    __security_check_cookie
0x14000ab71  mov     rbx, [rsp+50h+arg_10]
0x14000ab79  add     rsp, 50h
0x14000ab7d  pop     r15
0x14000ab7f  pop     r14
0x14000ab81  pop     rdi
0x14000ab82  pop     rsi
0x14000ab83  pop     rbp
0x14000ab84  retn
0x14000ab85  mov     rax, [rbx+8]
0x14000ab89  lea     r9, [rbp+var_18]
0x14000ab8d  mov     r8d, r15d
0x14000ab90  mov     rdx, rsi
0x14000ab93  movups  xmm0, xmmword ptr [rax]
0x14000ab96  movdqu  [rbp+var_18], xmm0
0x14000ab9b  test    r14d, r14d
0x14000ab9e  jz      short loc_14000ABDA
0x14000aba0  cmp     ecx, r15d
0x14000aba3  mov     rcx, [rbp+var_20]
0x14000aba7  mov     rax, [rcx]
0x14000abaa  jnz     short loc_14000ABB2
0x14000abac  mov     rax, [rax+28h]
0x14000abb0  jmp     short loc_14000ABB6
0x14000abb2  mov     rax, [rax+38h]
0x14000abb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abbb  mov     edi, eax
0x14000abbd  test    eax, eax
0x14000abbf  jns     short loc_14000ABF5
0x14000abc1  mov     rcx, [rbp+var_20]
0x14000abc5  test    rcx, rcx
0x14000abc8  jz      short loc_14000ABD6
0x14000abca  mov     rax, [rcx]
0x14000abcd  mov     rax, [rax+10h]
0x14000abd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abd6  mov     eax, edi
0x14000abd8  jmp     short loc_14000AB65
0x14000abda  cmp     ecx, r15d
0x14000abdd  mov     rcx, [rbp+var_20]
0x14000abe1  mov     rax, [rcx]
0x14000abe4  jnz     short loc_14000ABEC
0x14000abe6  mov     rax, [rax+30h]
0x14000abea  jmp     short loc_14000ABF0
0x14000abec  mov     rax, [rax+40h]
0x14000abf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000abf5  add     rbx, 10h
0x14000abf9  mov     ecx, [rbx]
0x14000abfb  test    ecx, ecx
0x14000abfd  jnz     short loc_14000AB85
0x14000abff  jmp     loc_14000AB4E
```

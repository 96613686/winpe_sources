# ImportSecurityContextW

- ea: `0x18001ab40`
- end: `0x18001ac18`
- name: `ImportSecurityContextW`
- size: `216`
- prototype: `SECURITY_STATUS __stdcall(LPWSTR pszPackage, PSecBuffer pPackedContext, void *Token, PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009c90`
- `0x18001ab40`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001abbe`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001abbe`

## pseudocode

```c
SECURITY_STATUS __stdcall ImportSecurityContextW(
        LPWSTR pszPackage,
        PSecBuffer pPackedContext,
        void *Token,
        PCtxtHandle phContext)
{
  SECURITY_STATUS result; // eax
  _QWORD *v9; // rbx
  SECURITY_STATUS v10; // ecx
  LPVOID lpTlsValue; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  ULONG_PTR v13; // [rsp+40h] [rbp-38h]

  lpTlsValue = 0;
  v12 = -1;
  v13 = -1;
  if ( !pszPackage )
    return -2146893051;
  result = SecLocatePackageExW(1, pszPackage, &lpTlsValue);
  if ( result >= 0 )
  {
    v9 = lpTlsValue;
    if ( !*(_QWORD *)(*((_QWORD *)lpTlsValue + 21) + 168LL) )
      return -2146893054;
    TlsSetValue(SecTlsPackage, lpTlsValue);
    v10 = (*(__int64 (__fastcall **)(LPWSTR, PSecBuffer, void *, __int64 *))(v9[22] + 168LL))(
            pszPackage,
            pPackedContext,
            Token,
            &v12);
    if ( v10 >= 0 )
    {
      phContext->dwUpper = v13;
      phContext->dwLower = (ULONG_PTR)v9;
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x18001ab40  push    rbx
0x18001ab42  push    rbp
0x18001ab43  push    rsi
0x18001ab44  push    rdi
0x18001ab45  push    r14
0x18001ab47  sub     rsp, 50h
0x18001ab4b  mov     rax, cs:__security_cookie
0x18001ab52  xor     rax, rsp
0x18001ab55  mov     [rsp+78h+var_30], rax
0x18001ab5a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ab5e  mov     [rsp+78h+lpTlsValue], 0
0x18001ab67  mov     [rsp+78h+var_40], rax
0x18001ab6c  mov     rdi, r9
0x18001ab6f  mov     [rsp+78h+var_38], rax
0x18001ab74  mov     r14, r8
0x18001ab77  mov     rbp, rdx
0x18001ab7a  mov     rsi, rcx
0x18001ab7d  test    rcx, rcx
0x18001ab80  jnz     short loc_18001AB89
0x18001ab82  mov     eax, 80090305h
0x18001ab87  jmp     short loc_18001AC00
0x18001ab89  lea     r8, [rsp+78h+lpTlsValue]
0x18001ab8e  mov     rdx, rsi
0x18001ab91  mov     ecx, 1
0x18001ab96  call    SecLocatePackageExW
0x18001ab9b  test    eax, eax
0x18001ab9d  js      short loc_18001AC00
0x18001ab9f  mov     rbx, [rsp+78h+lpTlsValue]
0x18001aba4  mov     rax, [rbx+0A8h]
0x18001abab  cmp     qword ptr [rax+0A8h], 0
0x18001abb3  jz      short loc_18001ABF9
0x18001abb5  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001abbb  mov     rdx, rbx; lpTlsValue
0x18001abbe  call    cs:__imp_TlsSetValue
0x18001abc4  mov     rax, [rbx+0B0h]
0x18001abcb  lea     r9, [rsp+78h+var_40]
0x18001abd0  mov     r8, r14
0x18001abd3  mov     rdx, rbp
0x18001abd6  mov     rcx, rsi
0x18001abd9  mov     rax, [rax+0A8h]
0x18001abe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001abe5  mov     ecx, eax
0x18001abe7  test    eax, eax
0x18001abe9  js      short loc_18001ABFE
0x18001abeb  mov     rax, [rsp+78h+var_38]
0x18001abf0  mov     [rdi+8], rax
0x18001abf4  mov     [rdi], rbx
0x18001abf7  jmp     short loc_18001ABFE
0x18001abf9  mov     ecx, 80090302h
0x18001abfe  mov     eax, ecx
0x18001ac00  mov     rcx, [rsp+78h+var_30]
0x18001ac05  xor     rcx, rsp; StackCookie
0x18001ac08  call    __security_check_cookie
0x18001ac0d  add     rsp, 50h
0x18001ac11  pop     r14
0x18001ac13  pop     rdi
0x18001ac14  pop     rsi
0x18001ac15  pop     rbp
0x18001ac16  pop     rbx
0x18001ac17  retn
```

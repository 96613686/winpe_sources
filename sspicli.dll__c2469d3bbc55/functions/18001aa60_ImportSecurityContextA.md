# ImportSecurityContextA

- ea: `0x18001aa60`
- end: `0x18001ab38`
- name: `ImportSecurityContextA`
- size: `216`
- prototype: `SECURITY_STATUS __stdcall(LPSTR pszPackage, PSecBuffer pPackedContext, void *Token, PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007b58`
- `0x18001aa60`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001aade`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001aade`

## pseudocode

```c
SECURITY_STATUS __stdcall ImportSecurityContextA(
        LPSTR pszPackage,
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
  result = SecLocatePackageExA(1, pszPackage, (struct _DLL_SECURITY_PACKAGE **)&lpTlsValue);
  if ( result >= 0 )
  {
    v9 = lpTlsValue;
    if ( !*(_QWORD *)(*((_QWORD *)lpTlsValue + 20) + 168LL) )
      return -2146893054;
    TlsSetValue(SecTlsPackage, lpTlsValue);
    v10 = (*(__int64 (__fastcall **)(LPSTR, PSecBuffer, void *, __int64 *))(v9[20] + 168LL))(
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
0x18001aa60  push    rbx
0x18001aa62  push    rbp
0x18001aa63  push    rsi
0x18001aa64  push    rdi
0x18001aa65  push    r14
0x18001aa67  sub     rsp, 50h
0x18001aa6b  mov     rax, cs:__security_cookie
0x18001aa72  xor     rax, rsp
0x18001aa75  mov     [rsp+78h+var_30], rax
0x18001aa7a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001aa7e  mov     [rsp+78h+lpTlsValue], 0
0x18001aa87  mov     [rsp+78h+var_40], rax
0x18001aa8c  mov     rdi, r9
0x18001aa8f  mov     [rsp+78h+var_38], rax
0x18001aa94  mov     r14, r8
0x18001aa97  mov     rbp, rdx
0x18001aa9a  mov     rsi, rcx
0x18001aa9d  test    rcx, rcx
0x18001aaa0  jnz     short loc_18001AAA9
0x18001aaa2  mov     eax, 80090305h
0x18001aaa7  jmp     short loc_18001AB20
0x18001aaa9  lea     r8, [rsp+78h+lpTlsValue]
0x18001aaae  mov     rdx, rsi
0x18001aab1  mov     ecx, 1; int
0x18001aab6  call    SecLocatePackageExA
0x18001aabb  test    eax, eax
0x18001aabd  js      short loc_18001AB20
0x18001aabf  mov     rbx, [rsp+78h+lpTlsValue]
0x18001aac4  mov     rax, [rbx+0A0h]
0x18001aacb  cmp     qword ptr [rax+0A8h], 0
0x18001aad3  jz      short loc_18001AB19
0x18001aad5  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001aadb  mov     rdx, rbx; lpTlsValue
0x18001aade  call    cs:__imp_TlsSetValue
0x18001aae4  mov     rax, [rbx+0A0h]
0x18001aaeb  lea     r9, [rsp+78h+var_40]
0x18001aaf0  mov     r8, r14
0x18001aaf3  mov     rdx, rbp
0x18001aaf6  mov     rcx, rsi
0x18001aaf9  mov     rax, [rax+0A8h]
0x18001ab00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab05  mov     ecx, eax
0x18001ab07  test    eax, eax
0x18001ab09  js      short loc_18001AB1E
0x18001ab0b  mov     rax, [rsp+78h+var_38]
0x18001ab10  mov     [rdi+8], rax
0x18001ab14  mov     [rdi], rbx
0x18001ab17  jmp     short loc_18001AB1E
0x18001ab19  mov     ecx, 80090302h
0x18001ab1e  mov     eax, ecx
0x18001ab20  mov     rcx, [rsp+78h+var_30]
0x18001ab25  xor     rcx, rsp; StackCookie
0x18001ab28  call    __security_check_cookie
0x18001ab2d  add     rsp, 50h
0x18001ab31  pop     r14
0x18001ab33  pop     rdi
0x18001ab34  pop     rsi
0x18001ab35  pop     rbp
0x18001ab36  pop     rbx
0x18001ab37  retn
```

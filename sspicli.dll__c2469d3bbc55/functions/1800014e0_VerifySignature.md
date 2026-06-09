# VerifySignature

- ea: `0x1800014e0`
- end: `0x18000156d`
- name: `VerifySignature`
- size: `141`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pMessage, unsigned int MessageSeqNo, unsigned int *pfQOP)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800014e0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000152c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000152c`

## pseudocode

```c
SECURITY_STATUS __stdcall VerifySignature(
        PCtxtHandle phContext,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo,
        unsigned int *pfQOP)
{
  struct _DLL_SECURITY_PACKAGE *v7; // rax
  struct _DLL_SECURITY_PACKAGE *v8; // rbx
  struct _SecHandle v10; // [rsp+30h] [rbp-48h] BYREF

  v10 = 0;
  v7 = SecpValidateHandle(1, phContext, &v10);
  v8 = v7;
  if ( !v7 )
    return -2146893055;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, PSecBufferDesc, _QWORD, unsigned int *))(*((_QWORD *)v8 + 22)
                                                                                                + 120LL))(
           &v10,
           pMessage,
           MessageSeqNo,
           pfQOP);
}

```

## disassembly

```asm
0x1800014e0  push    rbx
0x1800014e2  push    rbp
0x1800014e3  push    rsi
0x1800014e4  push    rdi
0x1800014e5  sub     rsp, 58h
0x1800014e9  mov     rax, cs:__security_cookie
0x1800014f0  xor     rax, rsp
0x1800014f3  mov     [rsp+78h+var_38], rax
0x1800014f8  mov     rdi, rdx
0x1800014fb  mov     esi, r8d
0x1800014fe  mov     rdx, rcx; struct _SecHandle *
0x180001501  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001506  xorps   xmm0, xmm0
0x180001509  mov     ecx, 1; int
0x18000150e  mov     rbp, r9
0x180001511  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001516  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18000151b  mov     rbx, rax
0x18000151e  test    rax, rax
0x180001521  jz      short loc_180001552
0x180001523  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001529  mov     rdx, rax; lpTlsValue
0x18000152c  call    cs:__imp_TlsSetValue
0x180001532  mov     rax, [rbx+0B0h]
0x180001539  lea     rcx, [rsp+78h+var_48]
0x18000153e  mov     r9, rbp
0x180001541  mov     r8d, esi
0x180001544  mov     rdx, rdi
0x180001547  mov     rax, [rax+78h]
0x18000154b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001550  jmp     short loc_180001557
0x180001552  mov     eax, 80090301h
0x180001557  mov     rcx, [rsp+78h+var_38]
0x18000155c  xor     rcx, rsp; StackCookie
0x18000155f  call    __security_check_cookie
0x180001564  add     rsp, 58h
0x180001568  pop     rdi
0x180001569  pop     rsi
0x18000156a  pop     rbp
0x18000156b  pop     rbx
0x18000156c  retn
```

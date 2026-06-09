# EncryptMessage

- ea: `0x180001ef0`
- end: `0x180001f7e`
- name: `EncryptMessage`
- size: `142`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int fQOP, PSecBufferDesc pMessage, unsigned int MessageSeqNo)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800190b8`

## callees

- `0x180001ef0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001f3b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001f3b`

## pseudocode

```c
SECURITY_STATUS __stdcall EncryptMessage(
        PCtxtHandle phContext,
        unsigned int fQOP,
        PSecBufferDesc pMessage,
        unsigned int MessageSeqNo)
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
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, PSecBufferDesc, _QWORD))(*((_QWORD *)v8 + 22) + 144LL))(
           &v10,
           fQOP,
           pMessage,
           MessageSeqNo);
}

```

## disassembly

```asm
0x180001ef0  push    rbx; EncryptMessage
0x180001ef2  push    rbp
0x180001ef3  push    rsi
0x180001ef4  push    rdi
0x180001ef5  sub     rsp, 58h
0x180001ef9  mov     rax, cs:__security_cookie
0x180001f00  xor     rax, rsp
0x180001f03  mov     [rsp+78h+var_38], rax
0x180001f08  mov     edi, edx
0x180001f0a  mov     rsi, r8
0x180001f0d  mov     rdx, rcx; struct _SecHandle *
0x180001f10  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001f15  xorps   xmm0, xmm0
0x180001f18  mov     ecx, 1; int
0x180001f1d  mov     ebp, r9d
0x180001f20  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001f25  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001f2a  mov     rbx, rax
0x180001f2d  test    rax, rax
0x180001f30  jz      short loc_180001F77
0x180001f32  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001f38  mov     rdx, rax; lpTlsValue
0x180001f3b  call    cs:__imp_TlsSetValue
0x180001f41  mov     rax, [rbx+0B0h]
0x180001f48  lea     rcx, [rsp+78h+var_48]
0x180001f4d  mov     r9d, ebp
0x180001f50  mov     r8, rsi
0x180001f53  mov     edx, edi
0x180001f55  mov     rax, [rax+90h]
0x180001f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f61  mov     rcx, [rsp+78h+var_38]
0x180001f66  xor     rcx, rsp; StackCookie
0x180001f69  call    __security_check_cookie
0x180001f6e  add     rsp, 58h
0x180001f72  pop     rdi
0x180001f73  pop     rsi
0x180001f74  pop     rbp
0x180001f75  pop     rbx
0x180001f76  retn
0x180001f77  mov     eax, 80090301h
0x180001f7c  jmp     short loc_180001F61
```

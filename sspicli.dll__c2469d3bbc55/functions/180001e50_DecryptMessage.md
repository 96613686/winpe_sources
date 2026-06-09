# DecryptMessage

- ea: `0x180001e50`
- end: `0x180001ee0`
- name: `DecryptMessage`
- size: `144`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pMessage, unsigned int MessageSeqNo, unsigned int *pfQOP)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019368`

## callees

- `0x180001e50`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001e9c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001e9c`

## pseudocode

```c
SECURITY_STATUS __stdcall DecryptMessage(
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
                                                                                                + 152LL))(
           &v10,
           pMessage,
           MessageSeqNo,
           pfQOP);
}

```

## disassembly

```asm
0x180001e50  push    rbx; DecryptMessage
0x180001e52  push    rbp
0x180001e53  push    rsi
0x180001e54  push    rdi
0x180001e55  sub     rsp, 58h
0x180001e59  mov     rax, cs:__security_cookie
0x180001e60  xor     rax, rsp
0x180001e63  mov     [rsp+78h+var_38], rax
0x180001e68  mov     rdi, rdx
0x180001e6b  mov     esi, r8d
0x180001e6e  mov     rdx, rcx; struct _SecHandle *
0x180001e71  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001e76  xorps   xmm0, xmm0
0x180001e79  mov     ecx, 1; int
0x180001e7e  mov     rbp, r9
0x180001e81  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001e86  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001e8b  mov     rbx, rax
0x180001e8e  test    rax, rax
0x180001e91  jz      short loc_180001ED9
0x180001e93  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001e99  mov     rdx, rax; lpTlsValue
0x180001e9c  call    cs:__imp_TlsSetValue
0x180001ea2  mov     rax, [rbx+0B0h]
0x180001ea9  lea     rcx, [rsp+78h+var_48]
0x180001eae  mov     r9, rbp
0x180001eb1  mov     r8d, esi
0x180001eb4  mov     rdx, rdi
0x180001eb7  mov     rax, [rax+98h]
0x180001ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ec3  mov     rcx, [rsp+78h+var_38]
0x180001ec8  xor     rcx, rsp; StackCookie
0x180001ecb  call    __security_check_cookie
0x180001ed0  add     rsp, 58h
0x180001ed4  pop     rdi
0x180001ed5  pop     rsi
0x180001ed6  pop     rbp
0x180001ed7  pop     rbx
0x180001ed8  retn
0x180001ed9  mov     eax, 80090301h
0x180001ede  jmp     short loc_180001EC3
```

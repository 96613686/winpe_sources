# MakeSignature

- ea: `0x180001440`
- end: `0x1800014cb`
- name: `MakeSignature`
- size: `139`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int fQOP, PSecBufferDesc pMessage, unsigned int MessageSeqNo)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001440`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000148b`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000148b`

## pseudocode

```c
SECURITY_STATUS __stdcall MakeSignature(
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
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, PSecBufferDesc, _QWORD))(*((_QWORD *)v8 + 22) + 112LL))(
           &v10,
           fQOP,
           pMessage,
           MessageSeqNo);
}

```

## disassembly

```asm
0x180001440  push    rbx
0x180001442  push    rbp
0x180001443  push    rsi
0x180001444  push    rdi
0x180001445  sub     rsp, 58h
0x180001449  mov     rax, cs:__security_cookie
0x180001450  xor     rax, rsp
0x180001453  mov     [rsp+78h+var_38], rax
0x180001458  mov     edi, edx
0x18000145a  mov     rsi, r8
0x18000145d  mov     rdx, rcx; struct _SecHandle *
0x180001460  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001465  xorps   xmm0, xmm0
0x180001468  mov     ecx, 1; int
0x18000146d  mov     ebp, r9d
0x180001470  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001475  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18000147a  mov     rbx, rax
0x18000147d  test    rax, rax
0x180001480  jz      short loc_1800014B0
0x180001482  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001488  mov     rdx, rax; lpTlsValue
0x18000148b  call    cs:__imp_TlsSetValue
0x180001491  mov     rax, [rbx+0B0h]
0x180001498  lea     rcx, [rsp+78h+var_48]
0x18000149d  mov     r9d, ebp
0x1800014a0  mov     r8, rsi
0x1800014a3  mov     edx, edi
0x1800014a5  mov     rax, [rax+70h]
0x1800014a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014ae  jmp     short loc_1800014B5
0x1800014b0  mov     eax, 80090301h
0x1800014b5  mov     rcx, [rsp+78h+var_38]
0x1800014ba  xor     rcx, rsp; StackCookie
0x1800014bd  call    __security_check_cookie
0x1800014c2  add     rsp, 58h
0x1800014c6  pop     rdi
0x1800014c7  pop     rsi
0x1800014c8  pop     rbp
0x1800014c9  pop     rbx
0x1800014ca  retn
```

# QueryContextAttributesW

- ea: `0x180001ae0`
- end: `0x180001b63`
- name: `QueryContextAttributesW`
- size: `131`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800190b8`
- `0x180019c20`

## callees

- `0x180001ae0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001b27`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001b27`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesW(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)
{
  struct _DLL_SECURITY_PACKAGE *v5; // rax
  struct _DLL_SECURITY_PACKAGE *v6; // rbx
  struct _SecHandle v8; // [rsp+20h] [rbp-38h] BYREF

  v8 = 0;
  v5 = SecpValidateHandle(1, phContext, &v8);
  v6 = v5;
  if ( !v5 )
    return -2146893055;
  TlsSetValue(SecTlsPackage, v5);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *))(*((_QWORD *)v6 + 21) + 88LL))(
           &v8,
           ulAttribute,
           pBuffer);
}

```

## disassembly

```asm
0x180001ae0  push    rbx
0x180001ae2  push    rsi
0x180001ae3  push    rdi
0x180001ae4  sub     rsp, 40h
0x180001ae8  mov     rax, cs:__security_cookie
0x180001aef  xor     rax, rsp
0x180001af2  mov     [rsp+58h+var_28], rax
0x180001af7  mov     edi, edx
0x180001af9  mov     rsi, r8
0x180001afc  mov     rdx, rcx; struct _SecHandle *
0x180001aff  lea     r8, [rsp+58h+var_38]; struct _SecHandle *
0x180001b04  xorps   xmm0, xmm0
0x180001b07  mov     ecx, 1; int
0x180001b0c  movups  xmmword ptr [rsp+58h+var_38.dwLower], xmm0
0x180001b11  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001b16  mov     rbx, rax
0x180001b19  test    rax, rax
0x180001b1c  jz      short loc_180001B5C
0x180001b1e  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001b24  mov     rdx, rax; lpTlsValue
0x180001b27  call    cs:__imp_TlsSetValue
0x180001b2d  mov     rax, [rbx+0A8h]
0x180001b34  lea     rcx, [rsp+58h+var_38]
0x180001b39  mov     r8, rsi
0x180001b3c  mov     edx, edi
0x180001b3e  mov     rax, [rax+58h]
0x180001b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b47  mov     rcx, [rsp+58h+var_28]
0x180001b4c  xor     rcx, rsp; StackCookie
0x180001b4f  call    __security_check_cookie
0x180001b54  add     rsp, 40h
0x180001b58  pop     rdi
0x180001b59  pop     rsi
0x180001b5a  pop     rbx
0x180001b5b  retn
0x180001b5c  mov     eax, 80090301h
0x180001b61  jmp     short loc_180001B47
```

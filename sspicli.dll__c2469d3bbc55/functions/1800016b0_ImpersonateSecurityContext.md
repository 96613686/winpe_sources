# ImpersonateSecurityContext

- ea: `0x1800016b0`
- end: `0x180001725`
- name: `ImpersonateSecurityContext`
- size: `117`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800016b0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800016f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800016f0`

## pseudocode

```c
SECURITY_STATUS __stdcall ImpersonateSecurityContext(PCtxtHandle phContext)
{
  struct _DLL_SECURITY_PACKAGE *v1; // rax
  struct _DLL_SECURITY_PACKAGE *v2; // rbx
  struct _SecHandle v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  v1 = SecpValidateHandle(1, phContext, &v4);
  v2 = v1;
  if ( !v1 )
    return -2146893055;
  TlsSetValue(SecTlsPackage, v1);
  return (*(__int64 (__fastcall **)(struct _SecHandle *))(*((_QWORD *)v2 + 22) + 96LL))(&v4);
}

```

## disassembly

```asm
0x1800016b0  push    rbx
0x1800016b2  sub     rsp, 40h
0x1800016b6  mov     rax, cs:__security_cookie
0x1800016bd  xor     rax, rsp
0x1800016c0  mov     [rsp+48h+var_18], rax
0x1800016c5  xorps   xmm0, xmm0
0x1800016c8  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x1800016cd  mov     rdx, rcx; struct _SecHandle *
0x1800016d0  mov     ecx, 1; int
0x1800016d5  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x1800016da  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x1800016df  mov     rbx, rax
0x1800016e2  test    rax, rax
0x1800016e5  jz      short loc_18000171E
0x1800016e7  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x1800016ed  mov     rdx, rax; lpTlsValue
0x1800016f0  call    cs:__imp_TlsSetValue
0x1800016f6  mov     rax, [rbx+0B0h]
0x1800016fd  lea     rcx, [rsp+48h+var_28]
0x180001702  mov     rax, [rax+60h]
0x180001706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000170b  mov     rcx, [rsp+48h+var_18]
0x180001710  xor     rcx, rsp; StackCookie
0x180001713  call    __security_check_cookie
0x180001718  add     rsp, 40h
0x18000171c  pop     rbx
0x18000171d  retn
0x18000171e  mov     eax, 80090301h
0x180001723  jmp     short loc_18000170B
```

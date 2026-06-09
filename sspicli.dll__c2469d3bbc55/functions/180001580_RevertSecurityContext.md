# RevertSecurityContext

- ea: `0x180001580`
- end: `0x1800015f5`
- name: `RevertSecurityContext`
- size: `117`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001580`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800015c0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800015c0`

## pseudocode

```c
SECURITY_STATUS __stdcall RevertSecurityContext(PCtxtHandle phContext)
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
  return (*(__int64 (__fastcall **)(struct _SecHandle *))(*((_QWORD *)v2 + 22) + 104LL))(&v4);
}

```

## disassembly

```asm
0x180001580  push    rbx
0x180001582  sub     rsp, 40h
0x180001586  mov     rax, cs:__security_cookie
0x18000158d  xor     rax, rsp
0x180001590  mov     [rsp+48h+var_18], rax
0x180001595  xorps   xmm0, xmm0
0x180001598  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x18000159d  mov     rdx, rcx; struct _SecHandle *
0x1800015a0  mov     ecx, 1; int
0x1800015a5  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x1800015aa  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x1800015af  mov     rbx, rax
0x1800015b2  test    rax, rax
0x1800015b5  jz      short loc_1800015DD
0x1800015b7  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x1800015bd  mov     rdx, rax; lpTlsValue
0x1800015c0  call    cs:__imp_TlsSetValue
0x1800015c6  mov     rax, [rbx+0B0h]
0x1800015cd  lea     rcx, [rsp+48h+var_28]
0x1800015d2  mov     rax, [rax+68h]
0x1800015d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015db  jmp     short loc_1800015E2
0x1800015dd  mov     eax, 80090301h
0x1800015e2  mov     rcx, [rsp+48h+var_18]
0x1800015e7  xor     rcx, rsp; StackCookie
0x1800015ea  call    __security_check_cookie
0x1800015ef  add     rsp, 40h
0x1800015f3  pop     rbx
0x1800015f4  retn
```

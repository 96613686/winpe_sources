# FreeCredentialsHandle

- ea: `0x180001a60`
- end: `0x180001ad2`
- name: `FreeCredentialsHandle`
- size: `114`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001a60`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001a9d`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001a9d`

## pseudocode

```c
SECURITY_STATUS __stdcall FreeCredentialsHandle(PCredHandle phCredential)
{
  struct _DLL_SECURITY_PACKAGE *v1; // rax
  struct _DLL_SECURITY_PACKAGE *v2; // rbx
  struct _SecHandle v4; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  v1 = SecpValidateHandle(0, phCredential, &v4);
  v2 = v1;
  if ( !v1 )
    return -2146893055;
  TlsSetValue(SecTlsPackage, v1);
  return (*(__int64 (__fastcall **)(struct _SecHandle *))(*((_QWORD *)v2 + 22) + 32LL))(&v4);
}

```

## disassembly

```asm
0x180001a60  push    rbx
0x180001a62  sub     rsp, 40h
0x180001a66  mov     rax, cs:__security_cookie
0x180001a6d  xor     rax, rsp
0x180001a70  mov     [rsp+48h+var_18], rax
0x180001a75  xorps   xmm0, xmm0
0x180001a78  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x180001a7d  mov     rdx, rcx; struct _SecHandle *
0x180001a80  xor     ecx, ecx; int
0x180001a82  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x180001a87  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001a8c  mov     rbx, rax
0x180001a8f  test    rax, rax
0x180001a92  jz      short loc_180001ACB
0x180001a94  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001a9a  mov     rdx, rax; lpTlsValue
0x180001a9d  call    cs:__imp_TlsSetValue
0x180001aa3  mov     rax, [rbx+0B0h]
0x180001aaa  lea     rcx, [rsp+48h+var_28]
0x180001aaf  mov     rax, [rax+20h]
0x180001ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ab8  mov     rcx, [rsp+48h+var_18]
0x180001abd  xor     rcx, rsp; StackCookie
0x180001ac0  call    __security_check_cookie
0x180001ac5  add     rsp, 40h
0x180001ac9  pop     rbx
0x180001aca  retn
0x180001acb  mov     eax, 80090301h
0x180001ad0  jmp     short loc_180001AB8
```

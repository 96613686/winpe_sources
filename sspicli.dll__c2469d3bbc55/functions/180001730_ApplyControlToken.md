# ApplyControlToken

- ea: `0x180001730`
- end: `0x1800017b4`
- name: `ApplyControlToken`
- size: `132`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pInput)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001730`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001777`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001777`

## pseudocode

```c
SECURITY_STATUS __stdcall ApplyControlToken(PCtxtHandle phContext, PSecBufferDesc pInput)
{
  struct _DLL_SECURITY_PACKAGE *v3; // rax
  struct _DLL_SECURITY_PACKAGE *v4; // rbx
  struct _SecHandle v6; // [rsp+20h] [rbp-28h] BYREF

  v6 = 0;
  v3 = SecpValidateHandle(1, phContext, &v6);
  v4 = v3;
  if ( !v3 )
    return -2146893055;
  TlsSetValue(SecTlsPackage, v3);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, PSecBufferDesc))(*((_QWORD *)v4 + 22) + 80LL))(&v6, pInput);
}

```

## disassembly

```asm
0x180001730  mov     [rsp+arg_10], rbx
0x180001735  push    rdi
0x180001736  sub     rsp, 40h
0x18000173a  mov     rax, cs:__security_cookie
0x180001741  xor     rax, rsp
0x180001744  mov     [rsp+48h+var_18], rax
0x180001749  mov     rdi, rdx
0x18000174c  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x180001751  mov     rdx, rcx; struct _SecHandle *
0x180001754  xorps   xmm0, xmm0
0x180001757  mov     ecx, 1; int
0x18000175c  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x180001761  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001766  mov     rbx, rax
0x180001769  test    rax, rax
0x18000176c  jz      short loc_1800017AD
0x18000176e  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001774  mov     rdx, rax; lpTlsValue
0x180001777  call    cs:__imp_TlsSetValue
0x18000177d  mov     rax, [rbx+0B0h]
0x180001784  lea     rcx, [rsp+48h+var_28]
0x180001789  mov     rdx, rdi
0x18000178c  mov     rax, [rax+50h]
0x180001790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001795  mov     rcx, [rsp+48h+var_18]
0x18000179a  xor     rcx, rsp; StackCookie
0x18000179d  call    __security_check_cookie
0x1800017a2  mov     rbx, [rsp+48h+arg_10]
0x1800017a7  add     rsp, 40h
0x1800017ab  pop     rdi
0x1800017ac  retn
0x1800017ad  mov     eax, 80090301h
0x1800017b2  jmp     short loc_180001795
```

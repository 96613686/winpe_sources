# QueryContextAttributesA

- ea: `0x1800017c0`
- end: `0x180001843`
- name: `QueryContextAttributesA`
- size: `131`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001807`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001807`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesA(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer)
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
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *))(*((_QWORD *)v6 + 20) + 88LL))(
           &v8,
           ulAttribute,
           pBuffer);
}

```

## disassembly

```asm
0x1800017c0  push    rbx
0x1800017c2  push    rsi
0x1800017c3  push    rdi
0x1800017c4  sub     rsp, 40h
0x1800017c8  mov     rax, cs:__security_cookie
0x1800017cf  xor     rax, rsp
0x1800017d2  mov     [rsp+58h+var_28], rax
0x1800017d7  mov     edi, edx
0x1800017d9  mov     rsi, r8
0x1800017dc  mov     rdx, rcx; struct _SecHandle *
0x1800017df  lea     r8, [rsp+58h+var_38]; struct _SecHandle *
0x1800017e4  xorps   xmm0, xmm0
0x1800017e7  mov     ecx, 1; int
0x1800017ec  movups  xmmword ptr [rsp+58h+var_38.dwLower], xmm0
0x1800017f1  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x1800017f6  mov     rbx, rax
0x1800017f9  test    rax, rax
0x1800017fc  jz      short loc_18000183C
0x1800017fe  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001804  mov     rdx, rax; lpTlsValue
0x180001807  call    cs:__imp_TlsSetValue
0x18000180d  mov     rax, [rbx+0A0h]
0x180001814  lea     rcx, [rsp+58h+var_38]
0x180001819  mov     r8, rsi
0x18000181c  mov     edx, edi
0x18000181e  mov     rax, [rax+58h]
0x180001822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001827  mov     rcx, [rsp+58h+var_28]
0x18000182c  xor     rcx, rsp; StackCookie
0x18000182f  call    __security_check_cookie
0x180001834  add     rsp, 40h
0x180001838  pop     rdi
0x180001839  pop     rsi
0x18000183a  pop     rbx
0x18000183b  retn
0x18000183c  mov     eax, 80090301h
0x180001841  jmp     short loc_180001827
```

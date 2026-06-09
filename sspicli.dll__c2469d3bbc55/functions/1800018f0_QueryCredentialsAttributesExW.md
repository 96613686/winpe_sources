# QueryCredentialsAttributesExW

- ea: `0x1800018f0`
- end: `0x180001998`
- name: `QueryCredentialsAttributesExW`
- size: `168`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800018f0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000194e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000194e`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryCredentialsAttributesExW(
        PCredHandle phCredential,
        unsigned int ulAttribute,
        void *pBuffer,
        unsigned int cbBuffer)
{
  struct _DLL_SECURITY_PACKAGE *v7; // rax
  struct _DLL_SECURITY_PACKAGE *v8; // rbx
  __int64 v9; // rcx
  struct _SecHandle v11; // [rsp+30h] [rbp-48h] BYREF

  v11 = 0;
  v7 = SecpValidateHandle(0, phCredential, &v11);
  v8 = v7;
  if ( !v7 )
    return -2146893055;
  v9 = *((_QWORD *)v7 + 21);
  if ( *(_DWORD *)v9 <= 4u || !*(_QWORD *)(v9 + 248) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 21) + 248LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x1800018f0  push    rbx
0x1800018f2  push    rbp
0x1800018f3  push    rsi
0x1800018f4  push    rdi
0x1800018f5  sub     rsp, 58h
0x1800018f9  mov     rax, cs:__security_cookie
0x180001900  xor     rax, rsp
0x180001903  mov     [rsp+78h+var_38], rax
0x180001908  mov     edi, edx
0x18000190a  mov     rsi, r8
0x18000190d  mov     rdx, rcx; struct _SecHandle *
0x180001910  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001915  xorps   xmm0, xmm0
0x180001918  xor     ecx, ecx; int
0x18000191a  mov     ebp, r9d
0x18000191d  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001922  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001927  mov     rbx, rax
0x18000192a  test    rax, rax
0x18000192d  jz      short loc_180001991
0x18000192f  mov     rcx, [rax+0A8h]
0x180001936  cmp     dword ptr [rcx], 4
0x180001939  jbe     short loc_18000198A
0x18000193b  cmp     qword ptr [rcx+0F8h], 0
0x180001943  jz      short loc_18000198A
0x180001945  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18000194b  mov     rdx, rax; lpTlsValue
0x18000194e  call    cs:__imp_TlsSetValue
0x180001954  mov     rax, [rbx+0A8h]
0x18000195b  lea     rcx, [rsp+78h+var_48]
0x180001960  mov     r9d, ebp
0x180001963  mov     r8, rsi
0x180001966  mov     edx, edi
0x180001968  mov     rax, [rax+0F8h]
0x18000196f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001974  mov     rcx, [rsp+78h+var_38]
0x180001979  xor     rcx, rsp; StackCookie
0x18000197c  call    __security_check_cookie
0x180001981  add     rsp, 58h
0x180001985  pop     rdi
0x180001986  pop     rsi
0x180001987  pop     rbp
0x180001988  pop     rbx
0x180001989  retn
0x18000198a  mov     eax, 80090302h
0x18000198f  jmp     short loc_180001974
0x180001991  mov     eax, 80090301h
0x180001996  jmp     short loc_180001974
```

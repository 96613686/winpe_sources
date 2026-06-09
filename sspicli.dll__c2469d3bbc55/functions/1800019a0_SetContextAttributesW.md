# SetContextAttributesW

- ea: `0x1800019a0`
- end: `0x180001a4b`
- name: `SetContextAttributesW`
- size: `171`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019a0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001a1c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001a1c`

## pseudocode

```c
SECURITY_STATUS __stdcall SetContextAttributesW(
        PCtxtHandle phContext,
        unsigned int ulAttribute,
        void *pBuffer,
        unsigned int cbBuffer)
{
  struct _DLL_SECURITY_PACKAGE *v7; // rax
  struct _DLL_SECURITY_PACKAGE *v8; // rbx
  __int64 v9; // rcx
  struct _SecHandle v11; // [rsp+30h] [rbp-48h] BYREF

  v11 = 0;
  v7 = SecpValidateHandle(1, phContext, &v11);
  v8 = v7;
  if ( !v7 )
    return -2146893055;
  v9 = *((_QWORD *)v7 + 21);
  if ( *(_DWORD *)v9 < 2u || !*(_QWORD *)(v9 + 216) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 21) + 216LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x1800019a0  push    rbx
0x1800019a2  push    rbp
0x1800019a3  push    rsi
0x1800019a4  push    rdi
0x1800019a5  sub     rsp, 58h
0x1800019a9  mov     rax, cs:__security_cookie
0x1800019b0  xor     rax, rsp
0x1800019b3  mov     [rsp+78h+var_38], rax
0x1800019b8  mov     edi, edx
0x1800019ba  mov     rsi, r8
0x1800019bd  mov     rdx, rcx; struct _SecHandle *
0x1800019c0  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x1800019c5  xorps   xmm0, xmm0
0x1800019c8  mov     ecx, 1; int
0x1800019cd  mov     ebp, r9d
0x1800019d0  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x1800019d5  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x1800019da  mov     rbx, rax
0x1800019dd  test    rax, rax
0x1800019e0  jz      short loc_180001A44
0x1800019e2  mov     rcx, [rax+0A8h]
0x1800019e9  cmp     dword ptr [rcx], 2
0x1800019ec  jnb     short loc_180001A09
0x1800019ee  mov     eax, 80090302h
0x1800019f3  mov     rcx, [rsp+78h+var_38]
0x1800019f8  xor     rcx, rsp; StackCookie
0x1800019fb  call    __security_check_cookie
0x180001a00  add     rsp, 58h
0x180001a04  pop     rdi
0x180001a05  pop     rsi
0x180001a06  pop     rbp
0x180001a07  pop     rbx
0x180001a08  retn
0x180001a09  cmp     qword ptr [rcx+0D8h], 0
0x180001a11  jz      short loc_1800019EE
0x180001a13  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001a19  mov     rdx, rbx; lpTlsValue
0x180001a1c  call    cs:__imp_TlsSetValue
0x180001a22  mov     rax, [rbx+0A8h]
0x180001a29  lea     rcx, [rsp+78h+var_48]
0x180001a2e  mov     r9d, ebp
0x180001a31  mov     r8, rsi
0x180001a34  mov     edx, edi
0x180001a36  mov     rax, [rax+0D8h]
0x180001a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a42  jmp     short loc_1800019F3
0x180001a44  mov     eax, 80090301h
0x180001a49  jmp     short loc_1800019F3
```

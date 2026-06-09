# QueryContextAttributesExW

- ea: `0x180001cd0`
- end: `0x180001d7b`
- name: `QueryContextAttributesExW`
- size: `171`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cd0`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001d4c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001d4c`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesExW(
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
  if ( *(_DWORD *)v9 <= 4u || !*(_QWORD *)(v9 + 240) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 21) + 240LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x180001cd0  push    rbx
0x180001cd2  push    rbp
0x180001cd3  push    rsi
0x180001cd4  push    rdi
0x180001cd5  sub     rsp, 58h
0x180001cd9  mov     rax, cs:__security_cookie
0x180001ce0  xor     rax, rsp
0x180001ce3  mov     [rsp+78h+var_38], rax
0x180001ce8  mov     edi, edx
0x180001cea  mov     rsi, r8
0x180001ced  mov     rdx, rcx; struct _SecHandle *
0x180001cf0  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001cf5  xorps   xmm0, xmm0
0x180001cf8  mov     ecx, 1; int
0x180001cfd  mov     ebp, r9d
0x180001d00  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001d05  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001d0a  mov     rbx, rax
0x180001d0d  test    rax, rax
0x180001d10  jz      short loc_180001D74
0x180001d12  mov     rcx, [rax+0A8h]
0x180001d19  cmp     dword ptr [rcx], 4
0x180001d1c  jbe     short loc_180001D28
0x180001d1e  cmp     qword ptr [rcx+0F0h], 0
0x180001d26  jnz     short loc_180001D43
0x180001d28  mov     eax, 80090302h
0x180001d2d  mov     rcx, [rsp+78h+var_38]
0x180001d32  xor     rcx, rsp; StackCookie
0x180001d35  call    __security_check_cookie
0x180001d3a  add     rsp, 58h
0x180001d3e  pop     rdi
0x180001d3f  pop     rsi
0x180001d40  pop     rbp
0x180001d41  pop     rbx
0x180001d42  retn
0x180001d43  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001d49  mov     rdx, rbx; lpTlsValue
0x180001d4c  call    cs:__imp_TlsSetValue
0x180001d52  mov     rax, [rbx+0A8h]
0x180001d59  lea     rcx, [rsp+78h+var_48]
0x180001d5e  mov     r9d, ebp
0x180001d61  mov     r8, rsi
0x180001d64  mov     edx, edi
0x180001d66  mov     rax, [rax+0F0h]
0x180001d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d72  jmp     short loc_180001D2D
0x180001d74  mov     eax, 80090301h
0x180001d79  jmp     short loc_180001D2D
```

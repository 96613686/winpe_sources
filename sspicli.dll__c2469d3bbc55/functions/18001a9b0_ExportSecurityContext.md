# ExportSecurityContext

- ea: `0x18001a9b0`
- end: `0x18001aa56`
- name: `ExportSecurityContext`
- size: `166`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, ULONG fFlags, PSecBuffer pPackedContext, void **pToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001a9b0`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001aa0c`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001aa0c`

## pseudocode

```c
SECURITY_STATUS __stdcall ExportSecurityContext(
        PCtxtHandle phContext,
        ULONG fFlags,
        PSecBuffer pPackedContext,
        void **pToken)
{
  struct _DLL_SECURITY_PACKAGE *v7; // rax
  struct _DLL_SECURITY_PACKAGE *v8; // rbx
  struct _SecHandle v10; // [rsp+30h] [rbp-48h] BYREF

  v10 = 0;
  v7 = SecpValidateHandle(1, phContext, &v10);
  v8 = v7;
  if ( !v7 )
    return -2146893055;
  if ( !*(_QWORD *)(*((_QWORD *)v7 + 22) + 160LL) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, PSecBuffer, void **))(*((_QWORD *)v8 + 22) + 160LL))(
           &v10,
           fFlags,
           pPackedContext,
           pToken);
}

```

## disassembly

```asm
0x18001a9b0  push    rbx
0x18001a9b2  push    rbp
0x18001a9b3  push    rsi
0x18001a9b4  push    rdi
0x18001a9b5  sub     rsp, 58h
0x18001a9b9  mov     rax, cs:__security_cookie
0x18001a9c0  xor     rax, rsp
0x18001a9c3  mov     [rsp+78h+var_38], rax
0x18001a9c8  mov     edi, edx
0x18001a9ca  mov     rsi, r8
0x18001a9cd  mov     rdx, rcx; struct _SecHandle *
0x18001a9d0  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x18001a9d5  xorps   xmm0, xmm0
0x18001a9d8  mov     ecx, 1; int
0x18001a9dd  mov     rbp, r9
0x18001a9e0  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x18001a9e5  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001a9ea  mov     rbx, rax
0x18001a9ed  test    rax, rax
0x18001a9f0  jz      short loc_18001AA3B
0x18001a9f2  mov     rcx, [rax+0B0h]
0x18001a9f9  cmp     qword ptr [rcx+0A0h], 0
0x18001aa01  jz      short loc_18001AA34
0x18001aa03  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001aa09  mov     rdx, rax; lpTlsValue
0x18001aa0c  call    cs:__imp_TlsSetValue
0x18001aa12  mov     rax, [rbx+0B0h]
0x18001aa19  lea     rcx, [rsp+78h+var_48]
0x18001aa1e  mov     r9, rbp
0x18001aa21  mov     r8, rsi
0x18001aa24  mov     edx, edi
0x18001aa26  mov     rax, [rax+0A0h]
0x18001aa2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa32  jmp     short loc_18001AA40
0x18001aa34  mov     eax, 80090302h
0x18001aa39  jmp     short loc_18001AA40
0x18001aa3b  mov     eax, 80090301h
0x18001aa40  mov     rcx, [rsp+78h+var_38]
0x18001aa45  xor     rcx, rsp; StackCookie
0x18001aa48  call    __security_check_cookie
0x18001aa4d  add     rsp, 58h
0x18001aa51  pop     rdi
0x18001aa52  pop     rsi
0x18001aa53  pop     rbp
0x18001aa54  pop     rbx
0x18001aa55  retn
```

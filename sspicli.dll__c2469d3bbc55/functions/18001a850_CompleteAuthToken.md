# CompleteAuthToken

- ea: `0x18001a850`
- end: `0x18001a8d4`
- name: `CompleteAuthToken`
- size: `132`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, PSecBufferDesc pToken)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001a850`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a897`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a897`

## pseudocode

```c
SECURITY_STATUS __stdcall CompleteAuthToken(PCtxtHandle phContext, PSecBufferDesc pToken)
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
  return (*(__int64 (__fastcall **)(struct _SecHandle *, PSecBufferDesc))(*((_QWORD *)v4 + 22) + 64LL))(&v6, pToken);
}

```

## disassembly

```asm
0x18001a850  mov     [rsp+arg_10], rbx
0x18001a855  push    rdi
0x18001a856  sub     rsp, 40h
0x18001a85a  mov     rax, cs:__security_cookie
0x18001a861  xor     rax, rsp
0x18001a864  mov     [rsp+48h+var_18], rax
0x18001a869  mov     rdi, rdx
0x18001a86c  lea     r8, [rsp+48h+var_28]; struct _SecHandle *
0x18001a871  mov     rdx, rcx; struct _SecHandle *
0x18001a874  xorps   xmm0, xmm0
0x18001a877  mov     ecx, 1; int
0x18001a87c  movups  xmmword ptr [rsp+48h+var_28.dwLower], xmm0
0x18001a881  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001a886  mov     rbx, rax
0x18001a889  test    rax, rax
0x18001a88c  jz      short loc_18001A8B7
0x18001a88e  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001a894  mov     rdx, rax; lpTlsValue
0x18001a897  call    cs:__imp_TlsSetValue
0x18001a89d  mov     rax, [rbx+0B0h]
0x18001a8a4  lea     rcx, [rsp+48h+var_28]
0x18001a8a9  mov     rdx, rdi
0x18001a8ac  mov     rax, [rax+40h]
0x18001a8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8b5  jmp     short loc_18001A8BC
0x18001a8b7  mov     eax, 80090301h
0x18001a8bc  mov     rcx, [rsp+48h+var_18]
0x18001a8c1  xor     rcx, rsp; StackCookie
0x18001a8c4  call    __security_check_cookie
0x18001a8c9  mov     rbx, [rsp+48h+arg_10]
0x18001a8ce  add     rsp, 40h
0x18001a8d2  pop     rdi
0x18001a8d3  retn
```

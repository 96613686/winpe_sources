# SetContextAttributesA

- ea: `0x18001ae00`
- end: `0x18001aeab`
- name: `SetContextAttributesA`
- size: `171`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001ae00`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ae61`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ae61`

## pseudocode

```c
SECURITY_STATUS __stdcall SetContextAttributesA(
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
  v9 = *((_QWORD *)v7 + 20);
  if ( *(_DWORD *)v9 < 2u || !*(_QWORD *)(v9 + 216) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 20) + 216LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x18001ae00  push    rbx
0x18001ae02  push    rbp
0x18001ae03  push    rsi
0x18001ae04  push    rdi
0x18001ae05  sub     rsp, 58h
0x18001ae09  mov     rax, cs:__security_cookie
0x18001ae10  xor     rax, rsp
0x18001ae13  mov     [rsp+78h+var_38], rax
0x18001ae18  mov     edi, edx
0x18001ae1a  mov     rsi, r8
0x18001ae1d  mov     rdx, rcx; struct _SecHandle *
0x18001ae20  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x18001ae25  xorps   xmm0, xmm0
0x18001ae28  mov     ecx, 1; int
0x18001ae2d  mov     ebp, r9d
0x18001ae30  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x18001ae35  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001ae3a  mov     rbx, rax
0x18001ae3d  test    rax, rax
0x18001ae40  jz      short loc_18001AE90
0x18001ae42  mov     rcx, [rax+0A0h]
0x18001ae49  cmp     dword ptr [rcx], 2
0x18001ae4c  jb      short loc_18001AE89
0x18001ae4e  cmp     qword ptr [rcx+0D8h], 0
0x18001ae56  jz      short loc_18001AE89
0x18001ae58  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001ae5e  mov     rdx, rax; lpTlsValue
0x18001ae61  call    cs:__imp_TlsSetValue
0x18001ae67  mov     rax, [rbx+0A0h]
0x18001ae6e  lea     rcx, [rsp+78h+var_48]
0x18001ae73  mov     r9d, ebp
0x18001ae76  mov     r8, rsi
0x18001ae79  mov     edx, edi
0x18001ae7b  mov     rax, [rax+0D8h]
0x18001ae82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae87  jmp     short loc_18001AE95
0x18001ae89  mov     eax, 80090302h
0x18001ae8e  jmp     short loc_18001AE95
0x18001ae90  mov     eax, 80090301h
0x18001ae95  mov     rcx, [rsp+78h+var_38]
0x18001ae9a  xor     rcx, rsp; StackCookie
0x18001ae9d  call    __security_check_cookie
0x18001aea2  add     rsp, 58h
0x18001aea6  pop     rdi
0x18001aea7  pop     rsi
0x18001aea8  pop     rbp
0x18001aea9  pop     rbx
0x18001aeaa  retn
```

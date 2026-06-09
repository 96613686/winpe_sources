# QueryCredentialsAttributesExA

- ea: `0x18001ad10`
- end: `0x18001adb8`
- name: `QueryCredentialsAttributesExA`
- size: `168`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001ad10`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ad6e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001ad6e`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryCredentialsAttributesExA(
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
  v9 = *((_QWORD *)v7 + 20);
  if ( *(_DWORD *)v9 <= 4u || !*(_QWORD *)(v9 + 248) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 20) + 248LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x18001ad10  push    rbx
0x18001ad12  push    rbp
0x18001ad13  push    rsi
0x18001ad14  push    rdi
0x18001ad15  sub     rsp, 58h
0x18001ad19  mov     rax, cs:__security_cookie
0x18001ad20  xor     rax, rsp
0x18001ad23  mov     [rsp+78h+var_38], rax
0x18001ad28  mov     edi, edx
0x18001ad2a  mov     rsi, r8
0x18001ad2d  mov     rdx, rcx; struct _SecHandle *
0x18001ad30  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x18001ad35  xorps   xmm0, xmm0
0x18001ad38  xor     ecx, ecx; int
0x18001ad3a  mov     ebp, r9d
0x18001ad3d  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x18001ad42  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001ad47  mov     rbx, rax
0x18001ad4a  test    rax, rax
0x18001ad4d  jz      short loc_18001AD9D
0x18001ad4f  mov     rcx, [rax+0A0h]
0x18001ad56  cmp     dword ptr [rcx], 4
0x18001ad59  jbe     short loc_18001AD96
0x18001ad5b  cmp     qword ptr [rcx+0F8h], 0
0x18001ad63  jz      short loc_18001AD96
0x18001ad65  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001ad6b  mov     rdx, rax; lpTlsValue
0x18001ad6e  call    cs:__imp_TlsSetValue
0x18001ad74  mov     rax, [rbx+0A0h]
0x18001ad7b  lea     rcx, [rsp+78h+var_48]
0x18001ad80  mov     r9d, ebp
0x18001ad83  mov     r8, rsi
0x18001ad86  mov     edx, edi
0x18001ad88  mov     rax, [rax+0F8h]
0x18001ad8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad94  jmp     short loc_18001ADA2
0x18001ad96  mov     eax, 80090302h
0x18001ad9b  jmp     short loc_18001ADA2
0x18001ad9d  mov     eax, 80090301h
0x18001ada2  mov     rcx, [rsp+78h+var_38]
0x18001ada7  xor     rcx, rsp; StackCookie
0x18001adaa  call    __security_check_cookie
0x18001adaf  add     rsp, 58h
0x18001adb3  pop     rdi
0x18001adb4  pop     rsi
0x18001adb5  pop     rbp
0x18001adb6  pop     rbx
0x18001adb7  retn
```

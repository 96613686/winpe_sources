# QueryCredentialsAttributesA

- ea: `0x18001ac70`
- end: `0x18001ad05`
- name: `QueryCredentialsAttributesA`
- size: `149`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001ac70`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001acc2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001acc2`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryCredentialsAttributesA(
        PCredHandle phCredential,
        unsigned int ulAttribute,
        void *pBuffer)
{
  struct _DLL_SECURITY_PACKAGE *v5; // rax
  struct _DLL_SECURITY_PACKAGE *v6; // rbx
  struct _SecHandle v8; // [rsp+20h] [rbp-38h] BYREF

  v8 = 0;
  v5 = SecpValidateHandle(0, phCredential, &v8);
  v6 = v5;
  if ( !v5 )
    return -2146893055;
  if ( !*(_QWORD *)(*((_QWORD *)v5 + 20) + 16LL) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v5);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *))(*((_QWORD *)v6 + 20) + 16LL))(
           &v8,
           ulAttribute,
           pBuffer);
}

```

## disassembly

```asm
0x18001ac70  push    rbx
0x18001ac72  push    rsi
0x18001ac73  push    rdi
0x18001ac74  sub     rsp, 40h
0x18001ac78  mov     rax, cs:__security_cookie
0x18001ac7f  xor     rax, rsp
0x18001ac82  mov     [rsp+58h+var_28], rax
0x18001ac87  mov     edi, edx
0x18001ac89  mov     rsi, r8
0x18001ac8c  mov     rdx, rcx; struct _SecHandle *
0x18001ac8f  lea     r8, [rsp+58h+var_38]; struct _SecHandle *
0x18001ac94  xorps   xmm0, xmm0
0x18001ac97  xor     ecx, ecx; int
0x18001ac99  movups  xmmword ptr [rsp+58h+var_38.dwLower], xmm0
0x18001ac9e  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001aca3  mov     rbx, rax
0x18001aca6  test    rax, rax
0x18001aca9  jz      short loc_18001ACEB
0x18001acab  mov     rcx, [rax+0A0h]
0x18001acb2  cmp     qword ptr [rcx+10h], 0
0x18001acb7  jz      short loc_18001ACE4
0x18001acb9  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001acbf  mov     rdx, rax; lpTlsValue
0x18001acc2  call    cs:__imp_TlsSetValue
0x18001acc8  mov     rax, [rbx+0A0h]
0x18001accf  lea     rcx, [rsp+58h+var_38]
0x18001acd4  mov     r8, rsi
0x18001acd7  mov     edx, edi
0x18001acd9  mov     rax, [rax+10h]
0x18001acdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ace2  jmp     short loc_18001ACF0
0x18001ace4  mov     eax, 80090302h
0x18001ace9  jmp     short loc_18001ACF0
0x18001aceb  mov     eax, 80090301h
0x18001acf0  mov     rcx, [rsp+58h+var_28]
0x18001acf5  xor     rcx, rsp; StackCookie
0x18001acf8  call    __security_check_cookie
0x18001acfd  add     rsp, 40h
0x18001ad01  pop     rdi
0x18001ad02  pop     rsi
0x18001ad03  pop     rbx
0x18001ad04  retn
```

# QueryCredentialsAttributesW

- ea: `0x180001850`
- end: `0x1800018e5`
- name: `QueryCredentialsAttributesW`
- size: `149`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001850`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800018a2`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800018a2`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryCredentialsAttributesW(
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
  if ( !*(_QWORD *)(*((_QWORD *)v5 + 21) + 16LL) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v5);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *))(*((_QWORD *)v6 + 21) + 16LL))(
           &v8,
           ulAttribute,
           pBuffer);
}

```

## disassembly

```asm
0x180001850  push    rbx
0x180001852  push    rsi
0x180001853  push    rdi
0x180001854  sub     rsp, 40h
0x180001858  mov     rax, cs:__security_cookie
0x18000185f  xor     rax, rsp
0x180001862  mov     [rsp+58h+var_28], rax
0x180001867  mov     edi, edx
0x180001869  mov     rsi, r8
0x18000186c  mov     rdx, rcx; struct _SecHandle *
0x18000186f  lea     r8, [rsp+58h+var_38]; struct _SecHandle *
0x180001874  xorps   xmm0, xmm0
0x180001877  xor     ecx, ecx; int
0x180001879  movups  xmmword ptr [rsp+58h+var_38.dwLower], xmm0
0x18000187e  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001883  mov     rbx, rax
0x180001886  test    rax, rax
0x180001889  jz      short loc_1800018DE
0x18000188b  mov     rcx, [rax+0A8h]
0x180001892  cmp     qword ptr [rcx+10h], 0
0x180001897  jz      short loc_1800018D7
0x180001899  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18000189f  mov     rdx, rax; lpTlsValue
0x1800018a2  call    cs:__imp_TlsSetValue
0x1800018a8  mov     rax, [rbx+0A8h]
0x1800018af  lea     rcx, [rsp+58h+var_38]
0x1800018b4  mov     r8, rsi
0x1800018b7  mov     edx, edi
0x1800018b9  mov     rax, [rax+10h]
0x1800018bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018c2  mov     rcx, [rsp+58h+var_28]
0x1800018c7  xor     rcx, rsp; StackCookie
0x1800018ca  call    __security_check_cookie
0x1800018cf  add     rsp, 40h
0x1800018d3  pop     rdi
0x1800018d4  pop     rsi
0x1800018d5  pop     rbx
0x1800018d6  retn
0x1800018d7  mov     eax, 80090302h
0x1800018dc  jmp     short loc_1800018C2
0x1800018de  mov     eax, 80090301h
0x1800018e3  jmp     short loc_1800018C2
```

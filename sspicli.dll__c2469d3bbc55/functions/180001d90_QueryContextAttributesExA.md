# QueryContextAttributesExA

- ea: `0x180001d90`
- end: `0x180001e42`
- name: `QueryContextAttributesExA`
- size: `178`
- prototype: `SECURITY_STATUS __stdcall(PCtxtHandle phContext, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d90`
- `0x180001f90`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001e13`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x180001e13`

## pseudocode

```c
SECURITY_STATUS __stdcall QueryContextAttributesExA(
        PCtxtHandle phContext,
        unsigned int ulAttribute,
        void *pBuffer,
        unsigned int cbBuffer)
{
  struct _DLL_SECURITY_PACKAGE *v7; // rax
  struct _DLL_SECURITY_PACKAGE *v8; // rbx
  struct _SecHandle v10; // [rsp+30h] [rbp-48h] BYREF

  v10 = 0;
  v7 = SecpValidateHandle(1, phContext, &v10);
  v8 = v7;
  if ( !v7 )
    return -2146893055;
  if ( **((_DWORD **)v7 + 21) <= 4u || !*(_QWORD *)(*((_QWORD *)v7 + 20) + 240LL) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 20) + 240LL))(
           &v10,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x180001d90  push    rbx
0x180001d92  push    rbp
0x180001d93  push    rsi
0x180001d94  push    rdi
0x180001d95  sub     rsp, 58h
0x180001d99  mov     rax, cs:__security_cookie
0x180001da0  xor     rax, rsp
0x180001da3  mov     [rsp+78h+var_38], rax
0x180001da8  mov     edi, edx
0x180001daa  mov     rsi, r8
0x180001dad  mov     rdx, rcx; struct _SecHandle *
0x180001db0  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x180001db5  xorps   xmm0, xmm0
0x180001db8  mov     ecx, 1; int
0x180001dbd  mov     ebp, r9d
0x180001dc0  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x180001dc5  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x180001dca  mov     rbx, rax
0x180001dcd  test    rax, rax
0x180001dd0  jz      short loc_180001E3B
0x180001dd2  mov     rax, [rax+0A8h]
0x180001dd9  cmp     dword ptr [rax], 4
0x180001ddc  ja      short loc_180001DF9
0x180001dde  mov     eax, 80090302h
0x180001de3  mov     rcx, [rsp+78h+var_38]
0x180001de8  xor     rcx, rsp; StackCookie
0x180001deb  call    __security_check_cookie
0x180001df0  add     rsp, 58h
0x180001df4  pop     rdi
0x180001df5  pop     rsi
0x180001df6  pop     rbp
0x180001df7  pop     rbx
0x180001df8  retn
0x180001df9  mov     rax, [rbx+0A0h]
0x180001e00  cmp     qword ptr [rax+0F0h], 0
0x180001e08  jz      short loc_180001DDE
0x180001e0a  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x180001e10  mov     rdx, rbx; lpTlsValue
0x180001e13  call    cs:__imp_TlsSetValue
0x180001e19  mov     rax, [rbx+0A0h]
0x180001e20  lea     rcx, [rsp+78h+var_48]
0x180001e25  mov     r9d, ebp
0x180001e28  mov     r8, rsi
0x180001e2b  mov     edx, edi
0x180001e2d  mov     rax, [rax+0F0h]
0x180001e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001e39  jmp     short loc_180001DE3
0x180001e3b  mov     eax, 80090301h
0x180001e40  jmp     short loc_180001DE3
```

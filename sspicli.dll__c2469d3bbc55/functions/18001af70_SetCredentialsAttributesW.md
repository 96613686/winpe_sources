# SetCredentialsAttributesW

- ea: `0x18001af70`
- end: `0x18001b018`
- name: `SetCredentialsAttributesW`
- size: `168`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001af70`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001afce`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001afce`

## pseudocode

```c
SECURITY_STATUS __stdcall SetCredentialsAttributesW(
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
  if ( *(_DWORD *)v9 < 3u || !*(_QWORD *)(v9 + 224) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 21) + 224LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x18001af70  push    rbx
0x18001af72  push    rbp
0x18001af73  push    rsi
0x18001af74  push    rdi
0x18001af75  sub     rsp, 58h
0x18001af79  mov     rax, cs:__security_cookie
0x18001af80  xor     rax, rsp
0x18001af83  mov     [rsp+78h+var_38], rax
0x18001af88  mov     edi, edx
0x18001af8a  mov     rsi, r8
0x18001af8d  mov     rdx, rcx; struct _SecHandle *
0x18001af90  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x18001af95  xorps   xmm0, xmm0
0x18001af98  xor     ecx, ecx; int
0x18001af9a  mov     ebp, r9d
0x18001af9d  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x18001afa2  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001afa7  mov     rbx, rax
0x18001afaa  test    rax, rax
0x18001afad  jz      short loc_18001AFFD
0x18001afaf  mov     rcx, [rax+0A8h]
0x18001afb6  cmp     dword ptr [rcx], 3
0x18001afb9  jb      short loc_18001AFF6
0x18001afbb  cmp     qword ptr [rcx+0E0h], 0
0x18001afc3  jz      short loc_18001AFF6
0x18001afc5  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001afcb  mov     rdx, rax; lpTlsValue
0x18001afce  call    cs:__imp_TlsSetValue
0x18001afd4  mov     rax, [rbx+0A8h]
0x18001afdb  lea     rcx, [rsp+78h+var_48]
0x18001afe0  mov     r9d, ebp
0x18001afe3  mov     r8, rsi
0x18001afe6  mov     edx, edi
0x18001afe8  mov     rax, [rax+0E0h]
0x18001afef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aff4  jmp     short loc_18001B002
0x18001aff6  mov     eax, 80090302h
0x18001affb  jmp     short loc_18001B002
0x18001affd  mov     eax, 80090301h
0x18001b002  mov     rcx, [rsp+78h+var_38]
0x18001b007  xor     rcx, rsp; StackCookie
0x18001b00a  call    __security_check_cookie
0x18001b00f  add     rsp, 58h
0x18001b013  pop     rdi
0x18001b014  pop     rsi
0x18001b015  pop     rbp
0x18001b016  pop     rbx
0x18001b017  retn
```

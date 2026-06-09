# SetCredentialsAttributesA

- ea: `0x18001aec0`
- end: `0x18001af68`
- name: `SetCredentialsAttributesA`
- size: `168`
- prototype: `SECURITY_STATUS __stdcall(PCredHandle phCredential, unsigned int ulAttribute, void *pBuffer, unsigned int cbBuffer)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f90`
- `0x18001aec0`
- `0x180022190`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001af1e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001af1e`

## pseudocode

```c
SECURITY_STATUS __stdcall SetCredentialsAttributesA(
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
  if ( *(_DWORD *)v9 < 3u || !*(_QWORD *)(v9 + 224) )
    return -2146893054;
  TlsSetValue(SecTlsPackage, v7);
  return (*(__int64 (__fastcall **)(struct _SecHandle *, _QWORD, void *, _QWORD))(*((_QWORD *)v8 + 20) + 224LL))(
           &v11,
           ulAttribute,
           pBuffer,
           cbBuffer);
}

```

## disassembly

```asm
0x18001aec0  push    rbx
0x18001aec2  push    rbp
0x18001aec3  push    rsi
0x18001aec4  push    rdi
0x18001aec5  sub     rsp, 58h
0x18001aec9  mov     rax, cs:__security_cookie
0x18001aed0  xor     rax, rsp
0x18001aed3  mov     [rsp+78h+var_38], rax
0x18001aed8  mov     edi, edx
0x18001aeda  mov     rsi, r8
0x18001aedd  mov     rdx, rcx; struct _SecHandle *
0x18001aee0  lea     r8, [rsp+78h+var_48]; struct _SecHandle *
0x18001aee5  xorps   xmm0, xmm0
0x18001aee8  xor     ecx, ecx; int
0x18001aeea  mov     ebp, r9d
0x18001aeed  movups  xmmword ptr [rsp+78h+var_48.dwLower], xmm0
0x18001aef2  call    ?SecpValidateHandle@@YAPEAU_DLL_SECURITY_PACKAGE@@HPEAU_SecHandle@@0@Z; SecpValidateHandle(int,_SecHandle *,_SecHandle *)
0x18001aef7  mov     rbx, rax
0x18001aefa  test    rax, rax
0x18001aefd  jz      short loc_18001AF4D
0x18001aeff  mov     rcx, [rax+0A0h]
0x18001af06  cmp     dword ptr [rcx], 3
0x18001af09  jb      short loc_18001AF46
0x18001af0b  cmp     qword ptr [rcx+0E0h], 0
0x18001af13  jz      short loc_18001AF46
0x18001af15  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001af1b  mov     rdx, rax; lpTlsValue
0x18001af1e  call    cs:__imp_TlsSetValue
0x18001af24  mov     rax, [rbx+0A0h]
0x18001af2b  lea     rcx, [rsp+78h+var_48]
0x18001af30  mov     r9d, ebp
0x18001af33  mov     r8, rsi
0x18001af36  mov     edx, edi
0x18001af38  mov     rax, [rax+0E0h]
0x18001af3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af44  jmp     short loc_18001AF52
0x18001af46  mov     eax, 80090302h
0x18001af4b  jmp     short loc_18001AF52
0x18001af4d  mov     eax, 80090301h
0x18001af52  mov     rcx, [rsp+78h+var_38]
0x18001af57  xor     rcx, rsp; StackCookie
0x18001af5a  call    __security_check_cookie
0x18001af5f  add     rsp, 58h
0x18001af63  pop     rdi
0x18001af64  pop     rsi
0x18001af65  pop     rbp
0x18001af66  pop     rbx
0x18001af67  retn
```

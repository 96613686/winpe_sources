# CryptStream::CryptStream(ldap_connection *,_SECURITY_FUNCTION_TABLE_W *,uchar)

- ea: `0x180031a34`
- end: `0x180031c90`
- name: `??0CryptStream@@QEAA@PEAUldap_connection@@PEAU_SECURITY_FUNCTION_TABLE_W@@E@Z`
- size: `604`
- prototype: `CryptStream *__fastcall(CryptStream *__hidden this, struct ldap_connection *, struct _SECURITY_FUNCTION_TABLE_W *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017854`
- `0x180049bf0`

## callees

- `0x1800037a8`
- `0x180031a34`
- `0x18004d010`

## pseudocode

```c
CryptStream *__fastcall CryptStream::CryptStream(
        CryptStream *this,
        struct ldap_connection *a2,
        struct _SECURITY_FUNCTION_TABLE_W *a3,
        char a4)
{
  __int64 v6; // r9
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rcx
  int v10; // ebx
  int v11; // eax
  int *v12; // rbx
  int v13; // ecx
  __int64 v15; // [rsp+80h] [rbp+8h] BYREF

  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 3) = a3;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 24) = 0;
  *((_DWORD *)this + 47) = 0;
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 7) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 8) = 0xFFFFFFFFLL;
  *((_QWORD *)this + 10) = 0xFFFFFFFFLL;
  v6 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_BYTE *)this + 272) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_DWORD *)this + 56) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 30) = (char *)this + 232;
  *((_QWORD *)this + 29) = (char *)this + 232;
  if ( a4 )
  {
    *(_QWORD *)this = *(_QWORD *)(v6 + 144);
    *((_QWORD *)this + 1) = *(_QWORD *)(v6 + 152);
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(char *, _QWORD, char *))(v6 + 88))((char *)a2 + 216, 0, (char *)this + 124);
    if ( g_fTracingOn )
    {
      if ( g_fProviderEnabled )
      {
        if ( (g_ulTraceFlags & 0x20) != 0 )
        {
          LDAPClientPrint(32, "QryContextAttributes returned 0x%x\n", v7);
          LDAPClientPrint(
            32,
            "Negotiate attribute sizes %d %d %d %d\n",
            *((_DWORD *)this + 31),
            *((_DWORD *)this + 32),
            *((_DWORD *)this + 33),
            *((_DWORD *)this + 34));
          v8 = *((_QWORD *)this + 3);
          v9 = *((_QWORD *)this + 2);
          v15 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(v8 + 88))(v9 + 216, 10, &v15);
          LDAPClientPrint(
            32,
            "PackageInfo: '%S' '%S' %d\n",
            *(const wchar_t **)(v15 + 16),
            *(const wchar_t **)(v15 + 24),
            *(unsigned __int16 *)(v15 + 6));
          if ( !v10 )
            (*(void (__fastcall **)(__int64))(*((_QWORD *)this + 3) + 128LL))(v15);
        }
      }
    }
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, char *))(*((_QWORD *)this + 3) + 88LL))(
            *((_QWORD *)this + 2) + 216LL,
            4,
            (char *)this + 104);
    v12 = (int *)((char *)this + 112);
    if ( v11 || (v13 = *v12) == 0 )
      v13 = -1;
    *((_DWORD *)this + 47) = v13;
    if ( g_fTracingOn && g_fProviderEnabled && (g_ulTraceFlags & 0x20) != 0 )
    {
      LDAPClientPrint(32, "QryContextAttributes for SECPKG_ATTR_STREAM_SIZES returned 0x%x\n", v11);
      LDAPClientPrint(
        32,
        "Stream sizes %d %d %d %d ",
        *((_DWORD *)this + 26),
        *((_DWORD *)this + 27),
        *v12,
        *((_DWORD *)this + 29));
      LDAPClientPrint(32, "Block size %d\n", *((_DWORD *)this + 30));
    }
  }
  *((_BYTE *)this + 40) = a4;
  return this;
}

```

## disassembly

```asm
0x180031a34  push    rbx
0x180031a36  push    rbp
0x180031a37  push    rsi
0x180031a38  push    rdi
0x180031a39  push    r12
0x180031a3b  push    r13
0x180031a3d  push    r14
0x180031a3f  push    r15
0x180031a41  sub     rsp, 38h
0x180031a45  xor     r14d, r14d
0x180031a48  xor     eax, eax
0x180031a4a  mov     [rcx+30h], rax
0x180031a4e  mov     r12d, 0FFFFFFFFh
0x180031a54  mov     bpl, r9b
0x180031a57  mov     [rcx+18h], r8
0x180031a5b  mov     [rcx+8], r14
0x180031a5f  lea     rax, [rcx+0E8h]
0x180031a66  mov     [rcx+10h], rdx
0x180031a6a  mov     rdi, rcx
0x180031a6d  mov     [rcx+0C0h], r14
0x180031a74  mov     [rcx+0BCh], r14d
0x180031a7b  mov     [rcx+118h], r14
0x180031a82  mov     [rcx+120h], r14
0x180031a89  mov     [rcx+38h], r12
0x180031a8d  mov     [rcx+40h], r12
0x180031a91  mov     [rcx+50h], r12
0x180031a95  mov     r9, [rcx+18h]
0x180031a99  mov     [rcx+0F8h], r14
0x180031aa0  mov     [rcx+100h], r14
0x180031aa7  mov     [rcx+110h], r14b
0x180031aae  mov     [rcx+128h], r14
0x180031ab5  mov     [rcx+0E0h], r14d
0x180031abc  mov     [rcx+0D8h], r14
0x180031ac3  mov     [rcx+0F0h], rax
0x180031aca  mov     [rax], rax
0x180031acd  test    bpl, bpl
0x180031ad0  jnz     loc_180031C62
0x180031ad6  mov     rax, [r9+58h]
0x180031ada  lea     r8, [rdi+7Ch]
0x180031ade  mov     r13d, 0D8h
0x180031ae4  lea     rcx, [rdx+r13]
0x180031ae8  xor     edx, edx
0x180031aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031aef  cmp     cs:g_fTracingOn, r14d
0x180031af6  lea     r15d, [r14+20h]
0x180031afa  jz      loc_180031BC8
0x180031b00  cmp     cs:g_fProviderEnabled, r14d
0x180031b07  jz      loc_180031BC8
0x180031b0d  test    byte ptr cs:g_ulTraceFlags, r15b
0x180031b14  jz      loc_180031BC8
0x180031b1a  mov     r8d, eax
0x180031b1d  lea     rdx, aQrycontextattr_0; "QryContextAttributes returned 0x%x\n"
0x180031b24  mov     ecx, r15d
0x180031b27  call    LDAPClientPrint
0x180031b2c  mov     eax, [rdi+88h]
0x180031b32  lea     rdx, aNegotiateAttri; "Negotiate attribute sizes %d %d %d %d\n"
0x180031b39  mov     r9d, [rdi+80h]
0x180031b40  mov     ecx, r15d
0x180031b43  mov     r8d, [rdi+7Ch]
0x180031b47  mov     [rsp+78h+var_50], eax
0x180031b4b  mov     eax, [rdi+84h]
0x180031b51  mov     [rsp+78h+var_58], eax
0x180031b55  call    LDAPClientPrint
0x180031b5a  mov     rax, [rdi+18h]
0x180031b5e  lea     r8, [rsp+78h+arg_0]
0x180031b66  mov     rcx, [rdi+10h]
0x180031b6a  lea     edx, [r14+0Ah]
0x180031b6e  mov     [rsp+78h+arg_0], r14
0x180031b76  add     rcx, r13
0x180031b79  mov     rax, [rax+58h]
0x180031b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b82  mov     r8, [rsp+78h+arg_0]
0x180031b8a  lea     rdx, aPackageinfoSSD; "PackageInfo: '%S' '%S' %d\n"
0x180031b91  mov     ebx, eax
0x180031b93  movzx   ecx, word ptr [r8+6]
0x180031b98  mov     r9, [r8+18h]
0x180031b9c  mov     r8, [r8+10h]
0x180031ba0  mov     [rsp+78h+var_58], ecx
0x180031ba4  mov     ecx, r15d
0x180031ba7  call    LDAPClientPrint
0x180031bac  test    ebx, ebx
0x180031bae  jnz     short loc_180031BC8
0x180031bb0  mov     rax, [rdi+18h]
0x180031bb4  mov     rcx, [rsp+78h+arg_0]
0x180031bbc  mov     rax, [rax+80h]
0x180031bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bc8  mov     rax, [rdi+18h]
0x180031bcc  lea     r8, [rdi+68h]
0x180031bd0  mov     rcx, [rdi+10h]
0x180031bd4  mov     edx, 4
0x180031bd9  add     rcx, r13
0x180031bdc  mov     rax, [rax+58h]
0x180031be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031be5  lea     rbx, [rdi+70h]
0x180031be9  test    eax, eax
0x180031beb  jnz     short loc_180031BF3
0x180031bed  mov     ecx, [rbx]
0x180031bef  test    ecx, ecx
0x180031bf1  jnz     short loc_180031BF6
0x180031bf3  mov     ecx, r12d
0x180031bf6  mov     [rdi+0BCh], ecx
0x180031bfc  cmp     cs:g_fTracingOn, r14d
0x180031c03  jz      short loc_180031C77
0x180031c05  cmp     cs:g_fProviderEnabled, r14d
0x180031c0c  jz      short loc_180031C77
0x180031c0e  test    byte ptr cs:g_ulTraceFlags, r15b
0x180031c15  jz      short loc_180031C77
0x180031c17  mov     r8d, eax
0x180031c1a  lea     rdx, aQrycontextattr; "QryContextAttributes for SECPKG_ATTR_ST"...
0x180031c21  mov     ecx, r15d
0x180031c24  call    LDAPClientPrint
0x180031c29  mov     eax, [rdi+74h]
0x180031c2c  lea     rdx, aStreamSizesDDD; "Stream sizes %d %d %d %d "
0x180031c33  mov     r9d, [rdi+6Ch]
0x180031c37  mov     ecx, r15d
0x180031c3a  mov     r8d, [rdi+68h]
0x180031c3e  mov     [rsp+78h+var_50], eax
0x180031c42  mov     eax, [rbx]
0x180031c44  mov     [rsp+78h+var_58], eax
0x180031c48  call    LDAPClientPrint
0x180031c4d  mov     r8d, [rdi+78h]
0x180031c51  lea     rdx, aBlockSizeD; "Block size %d\n"
0x180031c58  mov     ecx, r15d
0x180031c5b  call    LDAPClientPrint
0x180031c60  jmp     short loc_180031C77
0x180031c62  mov     rax, [r9+90h]
0x180031c69  mov     [rcx], rax
0x180031c6c  mov     rax, [r9+98h]
0x180031c73  mov     [rcx+8], rax
0x180031c77  mov     [rdi+28h], bpl
0x180031c7b  mov     rax, rdi
0x180031c7e  add     rsp, 38h
0x180031c82  pop     r15
0x180031c84  pop     r14
0x180031c86  pop     r13
0x180031c88  pop     r12
0x180031c8a  pop     rdi
0x180031c8b  pop     rsi
0x180031c8c  pop     rbp
0x180031c8d  pop     rbx
0x180031c8e  retn
```

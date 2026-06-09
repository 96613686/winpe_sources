# OSF_CCALL_AVRF::GetBuffer(_RPC_MESSAGE *,_GUID *)

- ea: `0x1800b0d30`
- end: `0x1800b11e9`
- name: `?GetBuffer@OSF_CCALL_AVRF@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z`
- size: `1209`
- prototype: `__int64 __fastcall(OSF_CCALL_AVRF *__hidden this, struct _RPC_MESSAGE *, struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18006112c`
- `0x180061620`
- `0x18006d460`
- `0x1800aa300`
- `0x1800adb74`
- `0x1800adbc0`
- `0x1800adc00`
- `0x1800b0d30`
- `0x1800ce5d0`
- `0x1800cec91`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!_wcslwr` at `0x1800b0f45`
- `ntdll!_wcslwr` at `0x1800b0f57`
- `ntdll!_wcslwr` at `0x1800b0f45`
- `ntdll!_wcslwr` at `0x1800b0f57`
- `ntdll!wcsstr` at `0x1800b0f6c`
- `ntdll!wcsstr` at `0x1800b0f6c`
- `ntdll!DbgPrint` at `0x1800b108f`
- `ntdll!DbgPrint` at `0x1800b10cf`
- `ntdll!DbgPrint` at `0x1800b10f0`
- `ntdll!DbgPrint` at `0x1800b110b`
- `ntdll!DbgPrint` at `0x1800b111e`
- `ntdll!DbgPrint` at `0x1800b113e`
- `ntdll!DbgPrint` at `0x1800b108f`
- `ntdll!DbgPrint` at `0x1800b10cf`
- `ntdll!DbgPrint` at `0x1800b10f0`
- `ntdll!DbgPrint` at `0x1800b110b`
- `ntdll!DbgPrint` at `0x1800b111e`
- `ntdll!DbgPrint` at `0x1800b113e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b0fa7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b0fda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b100d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b1040`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b0fa7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b0fda`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b100d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b1040`

## string_xrefs

- `0x1800b1081`: `Possible security threat: Client is calling a remote endpoint without RPC_C_AUTHN_LEVEL_PKT_PRIVACY`
- `0x1800b10c1`: `Possible security threat: Client is calling a remote endpoint without mutual authentication`
- `0x1800b10e6`: `RPC: Protocol: %S NetworkAddress: %S Interface UUID: `
- `0x1800b1137`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`

## pseudocode

```c
__int64 __fastcall OSF_CCALL_AVRF::GetBuffer(OSF_CCALL_AVRF *this, struct _RPC_MESSAGE *a2, struct _GUID *a3)
{
  int v3; // eax
  struct _GUID **v4; // rdi
  struct _GUID *v5; // r9
  __int64 v8; // r15
  _WORD *v9; // rcx
  __int64 v10; // rsi
  size_t v11; // r14
  struct _GUID **v12; // rbx
  size_t v13; // rcx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  _DWORD *v18; // rax
  size_t v19; // rsi
  size_t v20; // rcx
  __int64 v21; // rcx
  unsigned __int64 v22; // rcx
  void *v23; // rsp
  void *v24; // rsp
  _DWORD *v25; // rax
  __int64 result; // rax
  wchar_t *v27; // rsi
  wchar_t *v28; // rdi
  struct _GUID *v29; // rbx
  int v30; // r11d
  int v31; // edx
  unsigned int BufferLength; // ebx
  struct _GUID *v33; // r9
  _BYTE v34[32]; // [rsp+0h] [rbp-30h] BYREF
  struct _GUID *v35; // [rsp+30h] [rbp+0h] BYREF
  __int64 v36; // [rsp+38h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 114);
  v4 = 0;
  v35 = a3;
  v5 = a3;
  if ( (v3 & 0x80u) == 0 )
  {
    if ( gfRPCVerifierEnabled )
    {
      if ( !*((_DWORD *)pRpcVerifierSettings + 33) )
      {
        v8 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 34) + 24LL) + 24LL);
        v9 = *(_WORD **)(v8 + 8);
        if ( *v9 )
        {
          v10 = -1;
          v11 = 2LL * gLocalComputerNameLength;
          do
            ++v10;
          while ( v9[v10] );
          v12 = 0;
          if ( v11 )
          {
            if ( v11 <= g_ulMaxStackAllocSize )
            {
              v13 = v11 + g_ulAdditionalProbeSize + 8;
              if ( v13 >= v11 )
              {
                if ( (unsigned int)VerifyStackAvailable(v13, a2) )
                {
                  v14 = v11 + 23;
                  if ( v11 + 23 <= v11 + 8 )
                    v14 = 0xFFFFFFFFFFFFFF0LL;
                  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
                  v16 = alloca(v15);
                  v17 = alloca(v15);
                  v12 = &v35;
                  if ( v34 != (_BYTE *)-48LL )
                  {
                    LODWORD(v35) = 1801679955;
                    v12 = (struct _GUID **)&v36;
                    if ( &v36 )
                    {
LABEL_19:
                      v19 = 2 * v10 + 2;
                      if ( !v19 )
                        goto LABEL_27;
                      if ( v19 > g_ulMaxStackAllocSize )
                        goto LABEL_27;
                      v20 = v19 + g_ulAdditionalProbeSize + 8;
                      if ( v20 < v19 || !(unsigned int)VerifyStackAvailable(v20, a2) )
                        goto LABEL_27;
                      v21 = v19 + 23;
                      if ( v19 + 23 <= v19 + 8 )
                        v21 = 0xFFFFFFFFFFFFFF0LL;
                      v22 = v21 & 0xFFFFFFFFFFFFFFF0uLL;
                      v23 = alloca(v22);
                      v24 = alloca(v22);
                      v4 = &v35;
                      if ( v34 == (_BYTE *)-48LL || (LODWORD(v35) = 1801679955, (v4 = (struct _GUID **)&v36) == 0) )
                      {
LABEL_27:
                        if ( v19 + 8 >= v19 )
                        {
                          v25 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
                          if ( !v25 )
                            goto LABEL_31;
                          *v25 = 1885431112;
                          v4 = (struct _GUID **)(v25 + 2);
                        }
                        if ( !v4 )
                        {
LABEL_31:
                          if ( v12 )
                          {
                            if ( *((_DWORD *)v12 - 2) == 1885431112 )
                              ((void (*)(void))g_pfnFree)();
                          }
                          return 14;
                        }
                      }
                      memcpy_0(v12, gLocalComputerName, v11);
                      memcpy_0(v4, *(const void **)(v8 + 8), v19);
                      v27 = _wcslwr((wchar_t *)v12);
                      v28 = _wcslwr((wchar_t *)v4);
                      if ( wcsstr(v28, v27) == v28
                        || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v8 + 8), -1, L"localhost", -1) == 2
                        || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v8 + 8), -1, L"127.0.0.1", -1) == 2
                        || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v8 + 8), -1, L"\\\\.", -1) == 2
                        || CompareStringW(0x7Fu, 1u, *(PCNZWCH *)(v8 + 8), -1, L".", -1) == 2 )
                      {
                        goto LABEL_48;
                      }
                      v29 = (struct _GUID *)((char *)a2->RpcInterfaceInformation + 4);
                      if ( *(_DWORD *)OSF_CCALL::GetCallSecurityContext(this) != 6
                        && !(unsigned int)IsInterfaceExempt(v29, 2u) )
                      {
                        DbgPrint(
                          "%s : type (0x%x)",
                          "Possible security threat: Client is calling a remote endpoint without RPC_C_AUTHN_LEVEL_PKT_PRIVACY",
                          48);
                      }
                      if ( (*((_BYTE *)OSF_CCALL::GetCallSecurityContext(this) + 60) & 1) != 0
                        || (unsigned int)IsInterfaceExempt(v29, 4u) )
                      {
                        if ( !v30 )
                          goto LABEL_48;
                      }
                      else
                      {
                        DbgPrint(
                          "%s : type (0x%x)",
                          "Possible security threat: Client is calling a remote endpoint without mutual authentication",
                          v31 + 44);
                      }
                      DbgPrint(
                        "RPC: Protocol: %S NetworkAddress: %S Interface UUID: ",
                        *(const wchar_t **)v8,
                        *(const wchar_t **)(v8 + 8));
                      DbgPrintUUID(v29);
                      DbgPrint("\n");
                      DbgPrint("RPC: Offending Stack:\n");
                      PrintCurrentStackTrace(3u, 4u);
                      DbgPrint(
                        "RPC: To determine the symbolic stack, do an \"ln\" on the above addresses in the context of the "
                        "faulting process.\n"
                        "\n");
LABEL_48:
                      if ( v28 && *((_DWORD *)v28 - 2) == 1885431112 )
                        ((void (*)(void))g_pfnFree)();
                      if ( v27 && *((_DWORD *)v27 - 2) == 1885431112 )
                        ((void (*)(void))g_pfnFree)();
                      v5 = v35;
                      goto LABEL_55;
                    }
                  }
                }
              }
            }
          }
          if ( v11 + 8 >= v11 )
          {
            v18 = (_DWORD *)((__int64 (__fastcall *)(size_t, struct _RPC_MESSAGE *, struct _GUID *, struct _GUID *))g_pfnAllocate)(
                              v11 + 8,
                              a2,
                              a3,
                              v5);
            if ( !v18 )
              return 14;
            *v18 = 1885431112;
            v12 = (struct _GUID **)(v18 + 2);
          }
          if ( v12 )
            goto LABEL_19;
          return 14;
        }
      }
    }
  }
LABEL_55:
  if ( !*((_DWORD *)pRpcVerifierSettings + 6) )
    return OSF_CCALL::GetBuffer(this, a2, v5);
  BufferLength = a2->BufferLength;
  if ( !BufferLength )
    return OSF_CCALL::GetBuffer(this, a2, v5);
  a2->BufferLength = NDRVerifierGetExtendedRpcMessageBufferLength(BufferLength);
  result = OSF_CCALL::GetBuffer(this, a2, v33);
  a2->BufferLength = BufferLength;
  return result;
}

```

## disassembly

```asm
0x1800b0d30  push    rbp
0x1800b0d32  push    rbx
0x1800b0d33  push    rsi
0x1800b0d34  push    rdi
0x1800b0d35  push    r12
0x1800b0d37  push    r13
0x1800b0d39  push    r14
0x1800b0d3b  push    r15
0x1800b0d3d  sub     rsp, 58h
0x1800b0d41  lea     rbp, [rsp+30h]
0x1800b0d46  mov     rax, cs:__security_cookie
0x1800b0d4d  xor     rax, rbp
0x1800b0d50  mov     [rbp+60h+var_50], rax
0x1800b0d54  mov     eax, [rcx+1C8h]
0x1800b0d5a  xor     edi, edi
0x1800b0d5c  mov     [rbp+60h+var_60], r8
0x1800b0d60  mov     r9, r8
0x1800b0d63  mov     r13, rdx
0x1800b0d66  mov     r12, rcx
0x1800b0d69  test    al, al
0x1800b0d6b  js      loc_1800B118A
0x1800b0d71  cmp     cs:?gfRPCVerifierEnabled@@3HA, edi; int gfRPCVerifierEnabled
0x1800b0d77  jz      loc_1800B118A
0x1800b0d7d  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800b0d84  cmp     [rax+84h], edi
0x1800b0d8a  jnz     loc_1800B118A
0x1800b0d90  mov     rax, [rcx+110h]
0x1800b0d97  mov     rcx, [rax+18h]
0x1800b0d9b  mov     r15, [rcx+18h]
0x1800b0d9f  mov     rcx, [r15+8]
0x1800b0da3  cmp     [rcx], di
0x1800b0da6  jz      loc_1800B118A
0x1800b0dac  mov     eax, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x1800b0db2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800b0db6  lea     r14, [rax+rax]
0x1800b0dba  inc     rsi
0x1800b0dbd  cmp     [rcx+rsi*2], di
0x1800b0dc1  jnz     short loc_1800B0DBA
0x1800b0dc3  mov     rbx, rdi
0x1800b0dc6  test    r14, r14
0x1800b0dc9  jz      short loc_1800B0E2C
0x1800b0dcb  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800b0dd2  ja      short loc_1800B0E2C
0x1800b0dd4  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b0ddb  add     rcx, 8
0x1800b0ddf  add     rcx, r14
0x1800b0de2  cmp     rcx, r14
0x1800b0de5  jb      short loc_1800B0E2C
0x1800b0de7  call    VerifyStackAvailable
0x1800b0dec  test    eax, eax
0x1800b0dee  jz      short loc_1800B0E2C
0x1800b0df0  lea     rax, [r14+8]
0x1800b0df4  lea     rcx, [rax+0Fh]
0x1800b0df8  cmp     rcx, rax
0x1800b0dfb  ja      short loc_1800B0E07
0x1800b0dfd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b0e07  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b0e0b  mov     rax, rcx
0x1800b0e0e  call    __chkstk_0
0x1800b0e13  sub     rsp, rcx
0x1800b0e16  lea     rbx, [rsp+90h+var_60]
0x1800b0e1b  test    rbx, rbx
0x1800b0e1e  jz      short loc_1800B0E2C
0x1800b0e20  mov     dword ptr [rbx], 6B637453h
0x1800b0e26  add     rbx, 8
0x1800b0e2a  jnz     short loc_1800B0E60
0x1800b0e2c  lea     rcx, [r14+8]
0x1800b0e30  cmp     rcx, r14
0x1800b0e33  jb      short loc_1800B0E57
0x1800b0e35  mov     rax, cs:g_pfnAllocate
0x1800b0e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0e41  mov     rbx, rax
0x1800b0e44  test    rax, rax
0x1800b0e47  jz      loc_1800B0F17
0x1800b0e4d  mov     dword ptr [rax], 70616548h
0x1800b0e53  add     rbx, 8
0x1800b0e57  test    rbx, rbx
0x1800b0e5a  jz      loc_1800B0F17
0x1800b0e60  lea     rsi, ds:2[rsi*2]
0x1800b0e68  test    rsi, rsi
0x1800b0e6b  jz      short loc_1800B0ECE
0x1800b0e6d  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800b0e74  ja      short loc_1800B0ECE
0x1800b0e76  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800b0e7d  add     rcx, 8
0x1800b0e81  add     rcx, rsi
0x1800b0e84  cmp     rcx, rsi
0x1800b0e87  jb      short loc_1800B0ECE
0x1800b0e89  call    VerifyStackAvailable
0x1800b0e8e  test    eax, eax
0x1800b0e90  jz      short loc_1800B0ECE
0x1800b0e92  lea     rax, [rsi+8]
0x1800b0e96  lea     rcx, [rax+0Fh]
0x1800b0e9a  cmp     rcx, rax
0x1800b0e9d  ja      short loc_1800B0EA9
0x1800b0e9f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800b0ea9  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800b0ead  mov     rax, rcx
0x1800b0eb0  call    __chkstk_0
0x1800b0eb5  sub     rsp, rcx
0x1800b0eb8  lea     rdi, [rsp+90h+var_60]
0x1800b0ebd  test    rdi, rdi
0x1800b0ec0  jz      short loc_1800B0ECE
0x1800b0ec2  mov     dword ptr [rdi], 6B637453h
0x1800b0ec8  add     rdi, 8
0x1800b0ecc  jnz     short loc_1800B0F21
0x1800b0ece  lea     rcx, [rsi+8]
0x1800b0ed2  cmp     rcx, rsi
0x1800b0ed5  jb      short loc_1800B0EF5
0x1800b0ed7  mov     rax, cs:g_pfnAllocate
0x1800b0ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0ee3  mov     rdi, rax
0x1800b0ee6  test    rax, rax
0x1800b0ee9  jz      short loc_1800B0EFA
0x1800b0eeb  mov     dword ptr [rax], 70616548h
0x1800b0ef1  add     rdi, 8
0x1800b0ef5  test    rdi, rdi
0x1800b0ef8  jnz     short loc_1800B0F21
0x1800b0efa  test    rbx, rbx
0x1800b0efd  jz      short loc_1800B0F17
0x1800b0eff  lea     rcx, [rbx-8]
0x1800b0f03  cmp     dword ptr [rcx], 70616548h
0x1800b0f09  jnz     short loc_1800B0F17
0x1800b0f0b  mov     rax, cs:g_pfnFree
0x1800b0f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0f17  mov     eax, 0Eh
0x1800b0f1c  jmp     loc_1800B11CB
0x1800b0f21  mov     rdx, cs:?gLocalComputerName@@3PEAGEA; Src
0x1800b0f28  mov     r8, r14; Size
0x1800b0f2b  mov     rcx, rbx; void *
0x1800b0f2e  call    memcpy_0
0x1800b0f33  mov     rdx, [r15+8]; Src
0x1800b0f37  mov     r8, rsi; Size
0x1800b0f3a  mov     rcx, rdi; void *
0x1800b0f3d  call    memcpy_0
0x1800b0f42  mov     rcx, rbx; String
0x1800b0f45  call    cs:__imp__wcslwr
0x1800b0f4c  nop     dword ptr [rax+rax+00h]
0x1800b0f51  mov     rcx, rdi; String
0x1800b0f54  mov     rsi, rax
0x1800b0f57  call    cs:__imp__wcslwr
0x1800b0f5e  nop     dword ptr [rax+rax+00h]
0x1800b0f63  mov     rcx, rax; Str
0x1800b0f66  mov     rdx, rsi; SubStr
0x1800b0f69  mov     rdi, rax
0x1800b0f6c  call    cs:__imp_wcsstr
0x1800b0f73  nop     dword ptr [rax+rax+00h]
0x1800b0f78  cmp     rax, rdi
0x1800b0f7b  jz      loc_1800B114A
0x1800b0f81  mov     r8, [r15+8]; lpString1
0x1800b0f85  lea     rax, aLocalhost; "localhost"
0x1800b0f8c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b0f90  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800b0f94  mov     r9d, ebx; cchCount1
0x1800b0f97  mov     [rsp+90h+lpString2], rax; lpString2
0x1800b0f9c  lea     r14d, [rbx+2]
0x1800b0fa0  mov     edx, r14d; dwCmpFlags
0x1800b0fa3  lea     ecx, [r14+7Eh]; Locale
0x1800b0fa7  call    cs:__imp_CompareStringW
0x1800b0fae  nop     dword ptr [rax+rax+00h]
0x1800b0fb3  cmp     eax, 2
0x1800b0fb6  jz      loc_1800B114A
0x1800b0fbc  mov     r8, [r15+8]; lpString1
0x1800b0fc0  lea     rax, a127001; "127.0.0.1"
0x1800b0fc7  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800b0fcb  lea     ecx, [r14+7Eh]; Locale
0x1800b0fcf  mov     r9d, ebx; cchCount1
0x1800b0fd2  mov     [rsp+90h+lpString2], rax; lpString2
0x1800b0fd7  mov     edx, r14d; dwCmpFlags
0x1800b0fda  call    cs:__imp_CompareStringW
0x1800b0fe1  nop     dword ptr [rax+rax+00h]
0x1800b0fe6  cmp     eax, 2
0x1800b0fe9  jz      loc_1800B114A
0x1800b0fef  mov     r8, [r15+8]; lpString1
0x1800b0ff3  lea     rax, asc_1800E7D00; "\\\\."
0x1800b0ffa  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800b0ffe  lea     ecx, [r14+7Eh]; Locale
0x1800b1002  mov     r9d, ebx; cchCount1
0x1800b1005  mov     [rsp+90h+lpString2], rax; lpString2
0x1800b100a  mov     edx, r14d; dwCmpFlags
0x1800b100d  call    cs:__imp_CompareStringW
0x1800b1014  nop     dword ptr [rax+rax+00h]
0x1800b1019  cmp     eax, 2
0x1800b101c  jz      loc_1800B114A
0x1800b1022  mov     r8, [r15+8]; lpString1
0x1800b1026  lea     rax, asc_1800E72A8; "."
0x1800b102d  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800b1031  lea     ecx, [r14+7Eh]; Locale
0x1800b1035  mov     r9d, ebx; cchCount1
0x1800b1038  mov     [rsp+90h+lpString2], rax; lpString2
0x1800b103d  mov     edx, r14d; dwCmpFlags
0x1800b1040  call    cs:__imp_CompareStringW
0x1800b1047  nop     dword ptr [rax+rax+00h]
0x1800b104c  cmp     eax, 2
0x1800b104f  jz      loc_1800B114A
0x1800b1055  mov     rbx, [r13+28h]
0x1800b1059  mov     rcx, r12; this
0x1800b105c  add     rbx, 4
0x1800b1060  xor     r11d, r11d
0x1800b1063  call    ?GetCallSecurityContext@OSF_CCALL@@QEAAPEAVCSECURITY_CONTEXT@@XZ; OSF_CCALL::GetCallSecurityContext(void)
0x1800b1068  cmp     dword ptr [rax], 6
0x1800b106b  jz      short loc_1800B109E
0x1800b106d  lea     edx, [r14+1]; unsigned int
0x1800b1071  mov     rcx, rbx; struct _GUID *
0x1800b1074  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x1800b1079  test    eax, eax
0x1800b107b  jnz     short loc_1800B109E
0x1800b107d  lea     r8d, [r14+2Fh]
0x1800b1081  lea     rdx, aPossibleSecuri_2; "Possible security threat: Client is cal"...
0x1800b1088  lea     rcx, Format; "%s : type (0x%x)"
0x1800b108f  call    cs:__imp_DbgPrint
0x1800b1096  nop     dword ptr [rax+rax+00h]
0x1800b109b  mov     r11d, r14d
0x1800b109e  mov     rcx, r12; this
0x1800b10a1  call    ?GetCallSecurityContext@OSF_CCALL@@QEAAPEAVCSECURITY_CONTEXT@@XZ; OSF_CCALL::GetCallSecurityContext(void)
0x1800b10a6  test    [rax+3Ch], r14b
0x1800b10aa  jnz     short loc_1800B10DD
0x1800b10ac  mov     edx, 4; unsigned int
0x1800b10b1  mov     rcx, rbx; struct _GUID *
0x1800b10b4  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x1800b10b9  test    eax, eax
0x1800b10bb  jnz     short loc_1800B10DD
0x1800b10bd  lea     r8d, [rdx+2Ch]
0x1800b10c1  lea     rdx, aPossibleSecuri_4; "Possible security threat: Client is cal"...
0x1800b10c8  lea     rcx, Format; "%s : type (0x%x)"
0x1800b10cf  call    cs:__imp_DbgPrint
0x1800b10d6  nop     dword ptr [rax+rax+00h]
0x1800b10db  jmp     short loc_1800B10E2
0x1800b10dd  test    r11d, r11d
0x1800b10e0  jz      short loc_1800B114A
0x1800b10e2  mov     r8, [r15+8]
0x1800b10e6  lea     rcx, aRpcProtocolSNe; "RPC: Protocol: %S NetworkAddress: %S In"...
0x1800b10ed  mov     rdx, [r15]
0x1800b10f0  call    cs:__imp_DbgPrint
0x1800b10f7  nop     dword ptr [rax+rax+00h]
0x1800b10fc  mov     rcx, rbx; struct _GUID *
0x1800b10ff  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x1800b1104  lea     rcx, asc_1800E9378; "\n"
0x1800b110b  call    cs:__imp_DbgPrint
0x1800b1112  nop     dword ptr [rax+rax+00h]
0x1800b1117  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x1800b111e  call    cs:__imp_DbgPrint
0x1800b1125  nop     dword ptr [rax+rax+00h]
0x1800b112a  mov     edx, 4; FramesToCapture
0x1800b112f  lea     ecx, [rdx-1]; FramesToSkip
0x1800b1132  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x1800b1137  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x1800b113e  call    cs:__imp_DbgPrint
0x1800b1145  nop     dword ptr [rax+rax+00h]
0x1800b114a  test    rdi, rdi
0x1800b114d  jz      short loc_1800B1167
0x1800b114f  lea     rcx, [rdi-8]
0x1800b1153  cmp     dword ptr [rcx], 70616548h
0x1800b1159  jnz     short loc_1800B1167
0x1800b115b  mov     rax, cs:g_pfnFree
0x1800b1162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1167  xor     edi, edi
0x1800b1169  test    rsi, rsi
0x1800b116c  jz      short loc_1800B1186
0x1800b116e  lea     rcx, [rsi-8]
0x1800b1172  cmp     dword ptr [rcx], 70616548h
0x1800b1178  jnz     short loc_1800B1186
0x1800b117a  mov     rax, cs:g_pfnFree
0x1800b1181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1186  mov     r9, [rbp+60h+var_60]
0x1800b118a  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800b1191  cmp     [rax+18h], edi
0x1800b1194  jz      short loc_1800B11BD
0x1800b1196  mov     ebx, [r13+18h]
0x1800b119a  test    ebx, ebx
0x1800b119c  jz      short loc_1800B11BD
0x1800b119e  mov     ecx, ebx; unsigned int
0x1800b11a0  call    ?NDRVerifierGetExtendedRpcMessageBufferLength@@YAII@Z; NDRVerifierGetExtendedRpcMessageBufferLength(uint)
0x1800b11a5  mov     r8, r9; struct _GUID *
0x1800b11a8  mov     [r13+18h], eax
0x1800b11ac  mov     rdx, r13; struct _RPC_MESSAGE *
0x1800b11af  mov     rcx, r12; this
0x1800b11b2  call    ?GetBuffer@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z; OSF_CCALL::GetBuffer(_RPC_MESSAGE *,_GUID *)
0x1800b11b7  mov     [r13+18h], ebx
0x1800b11bb  jmp     short loc_1800B11CB
0x1800b11bd  mov     r8, r9; struct _GUID *
0x1800b11c0  mov     rdx, r13; struct _RPC_MESSAGE *
0x1800b11c3  mov     rcx, r12; this
0x1800b11c6  call    ?GetBuffer@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z; OSF_CCALL::GetBuffer(_RPC_MESSAGE *,_GUID *)
0x1800b11cb  mov     rcx, [rbp+60h+var_50]
0x1800b11cf  xor     rcx, rbp; StackCookie
0x1800b11d2  call    __security_check_cookie
0x1800b11d7  lea     rsp, [rbp+28h]
0x1800b11db  pop     r15
0x1800b11dd  pop     r14
0x1800b11df  pop     r13
0x1800b11e1  pop     r12
0x1800b11e3  pop     rdi
0x1800b11e4  pop     rsi
0x1800b11e5  pop     rbx
0x1800b11e6  pop     rbp
0x1800b11e7  retn
```

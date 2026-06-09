# OSF_CCALL_AVRF::GetBuffer(_RPC_MESSAGE *,_GUID *)

- ea: `0x1800ad1f0`
- end: `0x1800ad65a`
- name: `?GetBuffer@OSF_CCALL_AVRF@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z`
- size: `1130`
- prototype: `__int64 __fastcall(OSF_CCALL_AVRF *__hidden this, struct _RPC_MESSAGE *, struct _GUID *)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180058b5c`
- `0x180059020`
- `0x18005ceb0`
- `0x1800a6a40`
- `0x1800aa1d0`
- `0x1800aa21c`
- `0x1800aa250`
- `0x1800ad1f0`
- `0x1800c99a0`
- `0x1800ca031`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!_wcslwr` at `0x1800ad405`
- `ntdll!_wcslwr` at `0x1800ad411`
- `ntdll!_wcslwr` at `0x1800ad405`
- `ntdll!_wcslwr` at `0x1800ad411`
- `ntdll!wcsstr` at `0x1800ad420`
- `ntdll!wcsstr` at `0x1800ad420`
- `ntdll!DbgPrint` at `0x1800ad525`
- `ntdll!DbgPrint` at `0x1800ad55f`
- `ntdll!DbgPrint` at `0x1800ad57a`
- `ntdll!DbgPrint` at `0x1800ad58f`
- `ntdll!DbgPrint` at `0x1800ad59c`
- `ntdll!DbgPrint` at `0x1800ad5b6`
- `ntdll!DbgPrint` at `0x1800ad525`
- `ntdll!DbgPrint` at `0x1800ad55f`
- `ntdll!DbgPrint` at `0x1800ad57a`
- `ntdll!DbgPrint` at `0x1800ad58f`
- `ntdll!DbgPrint` at `0x1800ad59c`
- `ntdll!DbgPrint` at `0x1800ad5b6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad455`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad482`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad4af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad4dc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad455`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad482`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad4af`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800ad4dc`

## string_xrefs

- `0x1800ad517`: `Possible security threat: Client is calling a remote endpoint without RPC_C_AUTHN_LEVEL_PKT_PRIVACY`
- `0x1800ad551`: `Possible security threat: Client is calling a remote endpoint without mutual authentication`
- `0x1800ad570`: `RPC: Protocol: %S NetworkAddress: %S Interface UUID: `
- `0x1800ad5af`: `RPC: To determine the symbolic stack, do an "ln" on the above addresses in the context of the faulting process.\n\n`

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
0x1800ad1f0  push    rbp
0x1800ad1f2  push    rbx
0x1800ad1f3  push    rsi
0x1800ad1f4  push    rdi
0x1800ad1f5  push    r12
0x1800ad1f7  push    r13
0x1800ad1f9  push    r14
0x1800ad1fb  push    r15
0x1800ad1fd  sub     rsp, 58h
0x1800ad201  lea     rbp, [rsp+30h]
0x1800ad206  mov     rax, cs:__security_cookie
0x1800ad20d  xor     rax, rbp
0x1800ad210  mov     [rbp+60h+var_50], rax
0x1800ad214  mov     eax, [rcx+1C8h]
0x1800ad21a  xor     edi, edi
0x1800ad21c  mov     [rbp+60h+var_60], r8
0x1800ad220  mov     r9, r8
0x1800ad223  mov     r13, rdx
0x1800ad226  mov     r12, rcx
0x1800ad229  test    al, al
0x1800ad22b  js      loc_1800AD5FC
0x1800ad231  cmp     cs:?gfRPCVerifierEnabled@@3HA, edi; int gfRPCVerifierEnabled
0x1800ad237  jz      loc_1800AD5FC
0x1800ad23d  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800ad244  cmp     [rax+84h], edi
0x1800ad24a  jnz     loc_1800AD5FC
0x1800ad250  mov     rax, [rcx+110h]
0x1800ad257  mov     rcx, [rax+18h]
0x1800ad25b  mov     r15, [rcx+18h]
0x1800ad25f  mov     rcx, [r15+8]
0x1800ad263  cmp     [rcx], di
0x1800ad266  jz      loc_1800AD5FC
0x1800ad26c  mov     eax, cs:?gLocalComputerNameLength@@3KA; ulong gLocalComputerNameLength
0x1800ad272  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800ad276  lea     r14, [rax+rax]
0x1800ad27a  inc     rsi
0x1800ad27d  cmp     [rcx+rsi*2], di
0x1800ad281  jnz     short loc_1800AD27A
0x1800ad283  mov     rbx, rdi
0x1800ad286  test    r14, r14
0x1800ad289  jz      short loc_1800AD2EC
0x1800ad28b  cmp     r14, cs:g_ulMaxStackAllocSize
0x1800ad292  ja      short loc_1800AD2EC
0x1800ad294  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800ad29b  add     rcx, 8
0x1800ad29f  add     rcx, r14
0x1800ad2a2  cmp     rcx, r14
0x1800ad2a5  jb      short loc_1800AD2EC
0x1800ad2a7  call    VerifyStackAvailable
0x1800ad2ac  test    eax, eax
0x1800ad2ae  jz      short loc_1800AD2EC
0x1800ad2b0  lea     rax, [r14+8]
0x1800ad2b4  lea     rcx, [rax+0Fh]
0x1800ad2b8  cmp     rcx, rax
0x1800ad2bb  ja      short loc_1800AD2C7
0x1800ad2bd  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ad2c7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800ad2cb  mov     rax, rcx
0x1800ad2ce  call    __chkstk_0
0x1800ad2d3  sub     rsp, rcx
0x1800ad2d6  lea     rbx, [rsp+90h+var_60]
0x1800ad2db  test    rbx, rbx
0x1800ad2de  jz      short loc_1800AD2EC
0x1800ad2e0  mov     dword ptr [rbx], 6B637453h
0x1800ad2e6  add     rbx, 8
0x1800ad2ea  jnz     short loc_1800AD320
0x1800ad2ec  lea     rcx, [r14+8]
0x1800ad2f0  cmp     rcx, r14
0x1800ad2f3  jb      short loc_1800AD317
0x1800ad2f5  mov     rax, cs:g_pfnAllocate
0x1800ad2fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad301  mov     rbx, rax
0x1800ad304  test    rax, rax
0x1800ad307  jz      loc_1800AD3D7
0x1800ad30d  mov     dword ptr [rax], 70616548h
0x1800ad313  add     rbx, 8
0x1800ad317  test    rbx, rbx
0x1800ad31a  jz      loc_1800AD3D7
0x1800ad320  lea     rsi, ds:2[rsi*2]
0x1800ad328  test    rsi, rsi
0x1800ad32b  jz      short loc_1800AD38E
0x1800ad32d  cmp     rsi, cs:g_ulMaxStackAllocSize
0x1800ad334  ja      short loc_1800AD38E
0x1800ad336  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800ad33d  add     rcx, 8
0x1800ad341  add     rcx, rsi
0x1800ad344  cmp     rcx, rsi
0x1800ad347  jb      short loc_1800AD38E
0x1800ad349  call    VerifyStackAvailable
0x1800ad34e  test    eax, eax
0x1800ad350  jz      short loc_1800AD38E
0x1800ad352  lea     rax, [rsi+8]
0x1800ad356  lea     rcx, [rax+0Fh]
0x1800ad35a  cmp     rcx, rax
0x1800ad35d  ja      short loc_1800AD369
0x1800ad35f  mov     rcx, 0FFFFFFFFFFFFFF0h
0x1800ad369  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800ad36d  mov     rax, rcx
0x1800ad370  call    __chkstk_0
0x1800ad375  sub     rsp, rcx
0x1800ad378  lea     rdi, [rsp+90h+var_60]
0x1800ad37d  test    rdi, rdi
0x1800ad380  jz      short loc_1800AD38E
0x1800ad382  mov     dword ptr [rdi], 6B637453h
0x1800ad388  add     rdi, 8
0x1800ad38c  jnz     short loc_1800AD3E1
0x1800ad38e  lea     rcx, [rsi+8]
0x1800ad392  cmp     rcx, rsi
0x1800ad395  jb      short loc_1800AD3B5
0x1800ad397  mov     rax, cs:g_pfnAllocate
0x1800ad39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3a3  mov     rdi, rax
0x1800ad3a6  test    rax, rax
0x1800ad3a9  jz      short loc_1800AD3BA
0x1800ad3ab  mov     dword ptr [rax], 70616548h
0x1800ad3b1  add     rdi, 8
0x1800ad3b5  test    rdi, rdi
0x1800ad3b8  jnz     short loc_1800AD3E1
0x1800ad3ba  test    rbx, rbx
0x1800ad3bd  jz      short loc_1800AD3D7
0x1800ad3bf  lea     rcx, [rbx-8]
0x1800ad3c3  cmp     dword ptr [rcx], 70616548h
0x1800ad3c9  jnz     short loc_1800AD3D7
0x1800ad3cb  mov     rax, cs:g_pfnFree
0x1800ad3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad3d7  mov     eax, 0Eh
0x1800ad3dc  jmp     loc_1800AD63D
0x1800ad3e1  mov     rdx, cs:?gLocalComputerName@@3PEAGEA; Src
0x1800ad3e8  mov     r8, r14; Size
0x1800ad3eb  mov     rcx, rbx; void *
0x1800ad3ee  call    memcpy_0
0x1800ad3f3  mov     rdx, [r15+8]; Src
0x1800ad3f7  mov     r8, rsi; Size
0x1800ad3fa  mov     rcx, rdi; void *
0x1800ad3fd  call    memcpy_0
0x1800ad402  mov     rcx, rbx; String
0x1800ad405  call    cs:__imp__wcslwr
0x1800ad40b  mov     rcx, rdi; String
0x1800ad40e  mov     rsi, rax
0x1800ad411  call    cs:__imp__wcslwr
0x1800ad417  mov     rcx, rax; Str
0x1800ad41a  mov     rdx, rsi; SubStr
0x1800ad41d  mov     rdi, rax
0x1800ad420  call    cs:__imp_wcsstr
0x1800ad426  cmp     rax, rdi
0x1800ad429  jz      loc_1800AD5BC
0x1800ad42f  mov     r8, [r15+8]; lpString1
0x1800ad433  lea     rax, aLocalhost; "localhost"
0x1800ad43a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ad43e  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800ad442  mov     r9d, ebx; cchCount1
0x1800ad445  mov     [rsp+90h+lpString2], rax; lpString2
0x1800ad44a  lea     r14d, [rbx+2]
0x1800ad44e  mov     edx, r14d; dwCmpFlags
0x1800ad451  lea     ecx, [r14+7Eh]; Locale
0x1800ad455  call    cs:__imp_CompareStringW
0x1800ad45b  cmp     eax, 2
0x1800ad45e  jz      loc_1800AD5BC
0x1800ad464  mov     r8, [r15+8]; lpString1
0x1800ad468  lea     rax, a127001; "127.0.0.1"
0x1800ad46f  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800ad473  lea     ecx, [r14+7Eh]; Locale
0x1800ad477  mov     r9d, ebx; cchCount1
0x1800ad47a  mov     [rsp+90h+lpString2], rax; lpString2
0x1800ad47f  mov     edx, r14d; dwCmpFlags
0x1800ad482  call    cs:__imp_CompareStringW
0x1800ad488  cmp     eax, 2
0x1800ad48b  jz      loc_1800AD5BC
0x1800ad491  mov     r8, [r15+8]; lpString1
0x1800ad495  lea     rax, asc_1800E2D38; "\\\\."
0x1800ad49c  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800ad4a0  lea     ecx, [r14+7Eh]; Locale
0x1800ad4a4  mov     r9d, ebx; cchCount1
0x1800ad4a7  mov     [rsp+90h+lpString2], rax; lpString2
0x1800ad4ac  mov     edx, r14d; dwCmpFlags
0x1800ad4af  call    cs:__imp_CompareStringW
0x1800ad4b5  cmp     eax, 2
0x1800ad4b8  jz      loc_1800AD5BC
0x1800ad4be  mov     r8, [r15+8]; lpString1
0x1800ad4c2  lea     rax, asc_1800E2440; "."
0x1800ad4c9  mov     [rsp+90h+cchCount2], ebx; cchCount2
0x1800ad4cd  lea     ecx, [r14+7Eh]; Locale
0x1800ad4d1  mov     r9d, ebx; cchCount1
0x1800ad4d4  mov     [rsp+90h+lpString2], rax; lpString2
0x1800ad4d9  mov     edx, r14d; dwCmpFlags
0x1800ad4dc  call    cs:__imp_CompareStringW
0x1800ad4e2  cmp     eax, 2
0x1800ad4e5  jz      loc_1800AD5BC
0x1800ad4eb  mov     rbx, [r13+28h]
0x1800ad4ef  mov     rcx, r12; this
0x1800ad4f2  add     rbx, 4
0x1800ad4f6  xor     r11d, r11d
0x1800ad4f9  call    ?GetCallSecurityContext@OSF_CCALL@@QEAAPEAVCSECURITY_CONTEXT@@XZ; OSF_CCALL::GetCallSecurityContext(void)
0x1800ad4fe  cmp     dword ptr [rax], 6
0x1800ad501  jz      short loc_1800AD52E
0x1800ad503  lea     edx, [r14+1]; unsigned int
0x1800ad507  mov     rcx, rbx; struct _GUID *
0x1800ad50a  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x1800ad50f  test    eax, eax
0x1800ad511  jnz     short loc_1800AD52E
0x1800ad513  lea     r8d, [r14+2Fh]
0x1800ad517  lea     rdx, aPossibleSecuri_2; "Possible security threat: Client is cal"...
0x1800ad51e  lea     rcx, aSType0xX; "%s : type (0x%x)"
0x1800ad525  call    cs:__imp_DbgPrint
0x1800ad52b  mov     r11d, r14d
0x1800ad52e  mov     rcx, r12; this
0x1800ad531  call    ?GetCallSecurityContext@OSF_CCALL@@QEAAPEAVCSECURITY_CONTEXT@@XZ; OSF_CCALL::GetCallSecurityContext(void)
0x1800ad536  test    [rax+3Ch], r14b
0x1800ad53a  jnz     short loc_1800AD567
0x1800ad53c  mov     edx, 4; unsigned int
0x1800ad541  mov     rcx, rbx; struct _GUID *
0x1800ad544  call    ?IsInterfaceExempt@@YAHPEAU_GUID@@K@Z; IsInterfaceExempt(_GUID *,ulong)
0x1800ad549  test    eax, eax
0x1800ad54b  jnz     short loc_1800AD567
0x1800ad54d  lea     r8d, [rdx+2Ch]
0x1800ad551  lea     rdx, aPossibleSecuri_4; "Possible security threat: Client is cal"...
0x1800ad558  lea     rcx, aSType0xX; "%s : type (0x%x)"
0x1800ad55f  call    cs:__imp_DbgPrint
0x1800ad565  jmp     short loc_1800AD56C
0x1800ad567  test    r11d, r11d
0x1800ad56a  jz      short loc_1800AD5BC
0x1800ad56c  mov     r8, [r15+8]
0x1800ad570  lea     rcx, aRpcProtocolSNe; "RPC: Protocol: %S NetworkAddress: %S In"...
0x1800ad577  mov     rdx, [r15]
0x1800ad57a  call    cs:__imp_DbgPrint
0x1800ad580  mov     rcx, rbx; struct _GUID *
0x1800ad583  call    ?DbgPrintUUID@@YAXPEAU_GUID@@@Z; DbgPrintUUID(_GUID *)
0x1800ad588  lea     rcx, asc_1800E4358; "\n"
0x1800ad58f  call    cs:__imp_DbgPrint
0x1800ad595  lea     rcx, aRpcOffendingSt; "RPC: Offending Stack:\n"
0x1800ad59c  call    cs:__imp_DbgPrint
0x1800ad5a2  mov     edx, 4; FramesToCapture
0x1800ad5a7  lea     ecx, [rdx-1]; FramesToSkip
0x1800ad5aa  call    ?PrintCurrentStackTrace@@YAXII@Z; PrintCurrentStackTrace(uint,uint)
0x1800ad5af  lea     rcx, aRpcToDetermine_0; "RPC: To determine the symbolic stack, d"...
0x1800ad5b6  call    cs:__imp_DbgPrint
0x1800ad5bc  test    rdi, rdi
0x1800ad5bf  jz      short loc_1800AD5D9
0x1800ad5c1  lea     rcx, [rdi-8]
0x1800ad5c5  cmp     dword ptr [rcx], 70616548h
0x1800ad5cb  jnz     short loc_1800AD5D9
0x1800ad5cd  mov     rax, cs:g_pfnFree
0x1800ad5d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5d9  xor     edi, edi
0x1800ad5db  test    rsi, rsi
0x1800ad5de  jz      short loc_1800AD5F8
0x1800ad5e0  lea     rcx, [rsi-8]
0x1800ad5e4  cmp     dword ptr [rcx], 70616548h
0x1800ad5ea  jnz     short loc_1800AD5F8
0x1800ad5ec  mov     rax, cs:g_pfnFree
0x1800ad5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad5f8  mov     r9, [rbp+60h+var_60]
0x1800ad5fc  mov     rax, cs:?pRpcVerifierSettings@@3PEAU_tRpcVerifierSettings@@EA; _tRpcVerifierSettings * pRpcVerifierSettings
0x1800ad603  cmp     [rax+18h], edi
0x1800ad606  jz      short loc_1800AD62F
0x1800ad608  mov     ebx, [r13+18h]
0x1800ad60c  test    ebx, ebx
0x1800ad60e  jz      short loc_1800AD62F
0x1800ad610  mov     ecx, ebx; unsigned int
0x1800ad612  call    ?NDRVerifierGetExtendedRpcMessageBufferLength@@YAII@Z; NDRVerifierGetExtendedRpcMessageBufferLength(uint)
0x1800ad617  mov     r8, r9; struct _GUID *
0x1800ad61a  mov     [r13+18h], eax
0x1800ad61e  mov     rdx, r13; struct _RPC_MESSAGE *
0x1800ad621  mov     rcx, r12; this
0x1800ad624  call    ?GetBuffer@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z; OSF_CCALL::GetBuffer(_RPC_MESSAGE *,_GUID *)
0x1800ad629  mov     [r13+18h], ebx
0x1800ad62d  jmp     short loc_1800AD63D
0x1800ad62f  mov     r8, r9; struct _GUID *
0x1800ad632  mov     rdx, r13; struct _RPC_MESSAGE *
0x1800ad635  mov     rcx, r12; this
0x1800ad638  call    ?GetBuffer@OSF_CCALL@@UEAAJPEAU_RPC_MESSAGE@@PEAU_GUID@@@Z; OSF_CCALL::GetBuffer(_RPC_MESSAGE *,_GUID *)
0x1800ad63d  mov     rcx, [rbp+60h+var_50]
0x1800ad641  xor     rcx, rbp; StackCookie
0x1800ad644  call    __security_check_cookie
0x1800ad649  lea     rsp, [rbp+28h]
0x1800ad64d  pop     r15
0x1800ad64f  pop     r14
0x1800ad651  pop     r13
0x1800ad653  pop     r12
0x1800ad655  pop     rdi
0x1800ad656  pop     rsi
0x1800ad657  pop     rbx
0x1800ad658  pop     rbp
0x1800ad659  retn
```

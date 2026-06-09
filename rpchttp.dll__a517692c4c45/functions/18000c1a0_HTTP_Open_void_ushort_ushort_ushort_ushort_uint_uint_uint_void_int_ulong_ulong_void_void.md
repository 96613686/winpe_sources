# HTTP_Open(void *,ushort *,ushort *,ushort *,ushort *,uint,uint,uint,void *,int,ulong,ulong,void *,void *)

- ea: `0x18000c1a0`
- end: `0x18000c75e`
- name: `?HTTP_Open@@YAJPEAXPEAG111III0HKK00@Z`
- size: `1470`
- prototype: `__int64 __fastcall(HTTP2ClientVirtualConnection *this, unsigned int *AuthnSchemes, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned int, unsigned int, HTTPResolverHint *, int, DWORD dwMilliseconds, unsigned int, struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *, void *)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002498`
- `0x180002e4c`
- `0x180006050`
- `0x18000a5dc`
- `0x18000aa98`
- `0x18000aac4`
- `0x18000bd9c`
- `0x18000c1a0`
- `0x18000cbdc`
- `0x18000d288`
- `0x18000d4fc`
- `0x18000d5a0`
- `0x180019954`
- `0x18001cb10`
- `0x18001d2b8`
- `0x18001d380`
- `0x18001efe8`
- `0x18001f040`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!RtlIntegerToChar` at `0x18000c642`
- `ntdll!RtlIntegerToChar` at `0x18000c66d`
- `ntdll!RtlIntegerToChar` at `0x18000c642`
- `ntdll!RtlIntegerToChar` at `0x18000c66d`
- `RPCRT4!I_RpcFree` at `0x18000c3af`
- `RPCRT4!I_RpcFree` at `0x18000c3dc`
- `RPCRT4!I_RpcFree` at `0x18000c720`
- `RPCRT4!I_RpcFree` at `0x18000c72e`
- `RPCRT4!I_RpcFree` at `0x18000c3af`
- `RPCRT4!I_RpcFree` at `0x18000c3dc`
- `RPCRT4!I_RpcFree` at `0x18000c720`
- `RPCRT4!I_RpcFree` at `0x18000c72e`
- `RPCRT4!I_RpcAllocate` at `0x18000c396`
- `RPCRT4!I_RpcAllocate` at `0x18000c396`

## pseudocode

```c
__int64 __fastcall HTTP_Open(
        HTTP2ClientVirtualConnection *this,
        unsigned int *AuthnSchemes,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        HTTPResolverHint *a9,
        int a10,
        DWORD dwMilliseconds,
        unsigned int a12,
        struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *a13,
        void *a14)
{
  unsigned int v14; // edi
  HTTP2ClientVirtualConnection *v16; // r14
  char *v17; // r12
  int v19; // r15d
  struct _RUNTIME_IMPORT_TABLE *v20; // rax
  _OWORD *v21; // rcx
  __int64 v22; // r15
  __int64 v23; // rdx
  unsigned int v24; // edx
  unsigned int v25; // eax
  char *v26; // rax
  int v27; // eax
  _DWORD *v28; // rsi
  unsigned int v29; // eax
  HTTP2ClientVirtualConnection *v30; // rdi
  int v31; // eax
  struct _RUNTIME_IMPORT_TABLE *v32; // rax
  unsigned int v33; // eax
  int v34; // eax
  unsigned int v35; // [rsp+50h] [rbp-59h] BYREF
  unsigned int Size; // [rsp+54h] [rbp-55h]
  unsigned int v37; // [rsp+58h] [rbp-51h] BYREF
  void *Object; // [rsp+60h] [rbp-49h] BYREF
  _OWORD *v39; // [rsp+68h] [rbp-41h] BYREF
  char *v40; // [rsp+70h] [rbp-39h] BYREF
  unsigned __int16 *v41; // [rsp+78h] [rbp-31h]
  unsigned __int16 *v42; // [rsp+80h] [rbp-29h]
  void *v43; // [rsp+88h] [rbp-21h]
  CHAR String[24]; // [rsp+90h] [rbp-19h] BYREF

  v14 = 0;
  v16 = this;
  v17 = 0;
  v41 = a5;
  v43 = a14;
  v42 = a4;
  Object = 0;
  v40 = 0;
  Size = 0;
  v35 = 0;
  v39 = 0;
  if ( a12 >= 2 )
    return 1764;
  if ( a13 )
  {
    AuthnSchemes = a13->AuthnSchemes;
    if ( AuthnSchemes )
    {
      if ( *AuthnSchemes == 0x10000 )
      {
        this = (HTTP2ClientVirtualConnection *)((a13->Flags & 2) != 0 ? 0x40000 : 0x20000);
        *AuthnSchemes = (unsigned int)this;
      }
    }
  }
  if ( g_fHttpClientInitialized )
  {
    v37 = 0;
  }
  else
  {
    (*((void (__fastcall **)(HTTP2ClientVirtualConnection *, unsigned int *))pRuntimeImportTable + 6))(
      this,
      AuthnSchemes);
    if ( !g_fHttpClientInitialized )
    {
      v14 = InitializeHttpCommon();
      if ( !v14 )
      {
        v14 = InitializeDefaultChannelLifetime();
        if ( !v14 )
        {
          v14 = InitializeMinConnectionTimeout();
          if ( !v14 )
            g_fHttpClientInitialized = 1;
        }
      }
    }
    (*((void (**)(void))pRuntimeImportTable + 7))();
    v37 = v14;
    if ( v14 )
      return v14;
    v14 = 0;
  }
  v19 = 0;
  if ( a10 )
  {
    v28 = (_DWORD *)((char *)a9 + 32);
LABEL_50:
    while ( *((_DWORD *)a9 + 7) == 1 )
    {
      v30 = HTTP2ClientVirtualConnection::HTTP2ClientVirtualConnection(v16, a13, v43);
      v31 = HTTP2ClientVirtualConnection::ClientOpenInternal(v30, a9, a10, a6, dwMilliseconds, 1, 1, 0, 0);
      if ( v31 != 1728 && v31 != -1073606647 )
        goto LABEL_56;
      if ( a13 )
      {
        v31 = 1722;
LABEL_56:
        v35 = v31;
        *((_DWORD *)v30 + 3) = 10;
        if ( !v31 )
          goto LABEL_79;
        *((_QWORD *)v30 + 77) = 0;
        HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(v30);
        goto LABEL_77;
      }
      *((_DWORD *)a9 + 7) = 0;
      *((_QWORD *)v30 + 77) = 0;
      HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(v30);
    }
    if ( !*v28 )
      *v28 = 1;
    (*((void (__fastcall **)(HTTP2ClientVirtualConnection *, _QWORD, _QWORD, _QWORD))pRuntimeImportTable + 9))(
      v16,
      0,
      0,
      0);
    *(_QWORD *)v16 = &WS_CONNECTION::`vftable';
    v32 = pRuntimeImportTable;
    *((_DWORD *)v16 + 3) = 6;
    v33 = (*((__int64 (__fastcall **)(HTTP2ClientVirtualConnection *, _QWORD, _QWORD, _QWORD, unsigned int, DWORD, _DWORD))v32
           + 11))(
            v16,
            0,
            a6,
            a7,
            a8,
            dwMilliseconds,
            0);
    if ( v33 )
    {
      v35 = v33;
    }
    else
    {
      if ( *v28 != 2 )
      {
        if ( (unsigned int)HTTP_CheckIPAddressForDirectConnection(a9) )
        {
          v35 = 14;
          goto LABEL_77;
        }
        if ( *v28 != 1 || (unsigned int)HTTP_TryConnect(*((_QWORD *)v16 + 5), *((char **)a9 + 12), *((_WORD *)a9 + 54)) )
          goto LABEL_88;
      }
      if ( *v28 != 1 )
      {
LABEL_88:
        if ( (unsigned int)HTTP_TryConnect(*((_QWORD *)v16 + 5), *((char **)a9 + 14), *((_WORD *)a9 + 60)) )
          goto LABEL_74;
        RtlIntegerToChar(*((unsigned __int16 *)a9 + 54), 0xAu, 6u, String);
        if ( !(unsigned int)HttpTunnelToRpcProxy(*((_QWORD *)v16 + 5), *((char **)a9 + 12), String) )
          goto LABEL_74;
      }
      RtlIntegerToChar(*((unsigned __int16 *)a9 + 46), 0xAu, 6u, String);
      if ( (unsigned int)HttpTunnelToRpcServer(*((_QWORD *)v16 + 5), *((char **)a9 + 5), String) )
      {
        v34 = (*((__int64 (__fastcall **)(_QWORD, unsigned int *))pRuntimeImportTable + 18))(*((_QWORD *)v16 + 5), &v35);
        if ( !v35 )
        {
          if ( v34 )
            *(_QWORD *)v16 = &WS_SAN_CLIENT_CONNECTION::`vftable';
          v35 = 0;
          goto LABEL_79;
        }
      }
      else
      {
LABEL_74:
        v35 = 1722;
      }
      (*((void (__fastcall **)(HTTP2ClientVirtualConnection *))pRuntimeImportTable + 59))(v16);
    }
LABEL_77:
    if ( !v19 )
      goto LABEL_79;
LABEL_78:
    HTTPResolverHint::FreeRpcServer(a9);
    HTTPResolverHint::FreeRpcProxy(a9);
    HTTPResolverHint::FreeHTTPProxy(a9);
    goto LABEL_79;
  }
  v20 = pRuntimeImportTable;
  *((_QWORD *)a9 + 14) = 0;
  *((_QWORD *)a9 + 12) = 0;
  *((_QWORD *)a9 + 5) = 0;
  (*((void (__fastcall **)(HTTP2ClientVirtualConnection *, _QWORD, _QWORD, _OWORD **))v20 + 20))(v16, 0, 0, &v39);
  v21 = (_OWORD *)((char *)a9 + 122);
  if ( v39 )
  {
    *v21 = *v39;
LABEL_20:
    v22 = -1;
    v23 = -1;
    do
      ++v23;
    while ( a3[v23] );
    Size = v23;
    if ( (_DWORD)v23 )
    {
      v24 = v23 + 1;
      Size = v24;
    }
    else
    {
      a3 = (unsigned __int16 *)(*((__int64 (__fastcall **)(__int64, __int64, _QWORD))pRuntimeImportTable + 4))(1, 7, 0);
      if ( !a3 )
        return 14;
      v24 = Size;
      v14 = 1;
    }
    if ( v24 <= 0x28 )
    {
      v26 = (char *)a9 + 48;
      *((_QWORD *)a9 + 5) = (char *)a9 + 48;
LABEL_35:
      SimpleUnicodeToAnsi(a3, v24, v26);
      *((_DWORD *)a9 + 22) = Size - 1;
      if ( v14 )
        I_RpcFree(a3);
      if ( !a13 || (v27 = 1, (a13->Flags & 1) == 0) )
        v27 = 0;
      v28 = (_DWORD *)((char *)a9 + 32);
      if ( !(unsigned int)HttpParseNetworkOptions(
                            v41,
                            *((char **)a9 + 5),
                            (char **)a9 + 12,
                            (char **)&Object,
                            v27,
                            (char **)a9 + 14,
                            &v40,
                            (HTTPResolverHint *)((char *)a9 + 32),
                            &v37) )
      {
        HTTPResolverHint::FreeRpcServer(a9);
        return v37;
      }
      v29 = EndpointToPortNumber(v42, (unsigned __int16 *)a9 + 46);
      v17 = v40;
      if ( !v29 )
      {
        v29 = EndpointToPortNumberA((char *)Object, (unsigned __int16 *)a9 + 54);
        if ( !v29 )
        {
          do
            ++v22;
          while ( *(_BYTE *)(*((_QWORD *)a9 + 12) + v22) );
          *((_DWORD *)a9 + 26) = v22;
          if ( !*((_QWORD *)a9 + 14) || (v29 = EndpointToPortNumberA(v17, (unsigned __int16 *)a9 + 60)) == 0 )
          {
            v19 = 1;
            *((_DWORD *)a9 + 7) = 1;
            goto LABEL_50;
          }
        }
      }
      v35 = v29;
      goto LABEL_78;
    }
    v26 = (char *)I_RpcAllocate(v24);
    *((_QWORD *)a9 + 5) = v26;
    if ( v26 )
    {
      v24 = Size;
      goto LABEL_35;
    }
    if ( v14 )
      I_RpcFree(a3);
    return 14;
  }
  v25 = (*((__int64 (__fastcall **)(_OWORD *, __int64))pRuntimeImportTable + 3))(v21, 16);
  v37 = v25;
  if ( !v25 )
    goto LABEL_20;
  v35 = v25;
LABEL_79:
  if ( v35 == 164 )
    v35 = 1721;
  if ( Object )
    I_RpcFree(Object);
  if ( v17 )
    I_RpcFree(v17);
  return v35;
}

```

## disassembly

```asm
0x18000c1a0  mov     [rsp-8+arg_8], rbx
0x18000c1a5  push    rbp
0x18000c1a6  push    rsi
0x18000c1a7  push    rdi
0x18000c1a8  push    r12
0x18000c1aa  push    r13
0x18000c1ac  push    r14
0x18000c1ae  push    r15
0x18000c1b0  lea     rbp, [rsp-7]
0x18000c1b5  sub     rsp, 0B0h
0x18000c1bc  mov     rax, cs:__security_cookie
0x18000c1c3  xor     rax, rsp
0x18000c1c6  mov     [rbp+37h+var_38], rax
0x18000c1ca  mov     rax, [rbp+37h+arg_20]
0x18000c1ce  xor     edi, edi
0x18000c1d0  cmp     [rbp+37h+arg_58], 2
0x18000c1d7  mov     rsi, r8
0x18000c1da  mov     rbx, [rbp+37h+arg_40]
0x18000c1e1  mov     r14, rcx
0x18000c1e4  mov     r13, [rbp+37h+arg_60]
0x18000c1eb  mov     r12d, edi
0x18000c1ee  mov     [rbp+37h+var_68], rax
0x18000c1f2  mov     rax, [rbp+37h+arg_68]
0x18000c1f9  mov     [rbp+37h+var_58], rax
0x18000c1fd  mov     [rbp+37h+var_60], r9
0x18000c201  mov     [rbp+37h+Object], rdi
0x18000c205  mov     [rbp+37h+var_70], rdi
0x18000c209  mov     [rbp+37h+Size], edi
0x18000c20c  mov     [rbp+37h+var_90], edi
0x18000c20f  mov     [rbp+37h+var_78], rdi
0x18000c213  jb      short loc_18000C21F
0x18000c215  mov     eax, 6E4h
0x18000c21a  jmp     loc_18000C737
0x18000c21f  test    r13, r13
0x18000c222  jz      short loc_18000C24A
0x18000c224  mov     rdx, [r13+18h]
0x18000c228  test    rdx, rdx
0x18000c22b  jz      short loc_18000C24A
0x18000c22d  cmp     dword ptr [rdx], 10000h
0x18000c233  jnz     short loc_18000C24A
0x18000c235  mov     al, [r13+8]
0x18000c239  and     al, 2
0x18000c23b  neg     al
0x18000c23d  mov     eax, 20000h
0x18000c242  sbb     ecx, ecx
0x18000c244  and     ecx, eax
0x18000c246  add     ecx, eax
0x18000c248  mov     [rdx], ecx
0x18000c24a  cmp     cs:?g_fHttpClientInitialized@@3HA, edi; int g_fHttpClientInitialized
0x18000c250  jz      short loc_18000C257
0x18000c252  mov     [rbp+37h+var_88], edi
0x18000c255  jmp     short loc_18000C2BA
0x18000c257  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c25e  mov     rax, [rax+30h]
0x18000c262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c267  cmp     cs:?g_fHttpClientInitialized@@3HA, edi; int g_fHttpClientInitialized
0x18000c26d  jnz     short loc_18000C29A
0x18000c26f  call    ?InitializeHttpCommon@@YAJXZ; InitializeHttpCommon(void)
0x18000c274  mov     edi, eax
0x18000c276  test    eax, eax
0x18000c278  jnz     short loc_18000C29A
0x18000c27a  call    ?InitializeDefaultChannelLifetime@@YAJXZ; InitializeDefaultChannelLifetime(void)
0x18000c27f  mov     edi, eax
0x18000c281  test    eax, eax
0x18000c283  jnz     short loc_18000C29A
0x18000c285  call    ?InitializeMinConnectionTimeout@@YAJXZ; InitializeMinConnectionTimeout(void)
0x18000c28a  mov     edi, eax
0x18000c28c  test    eax, eax
0x18000c28e  jnz     short loc_18000C29A
0x18000c290  mov     cs:?g_fHttpClientInitialized@@3HA, 1; int g_fHttpClientInitialized
0x18000c29a  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c2a1  mov     rax, [rax+38h]
0x18000c2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2aa  mov     [rbp+37h+var_88], edi
0x18000c2ad  test    edi, edi
0x18000c2af  jz      short loc_18000C2B8
0x18000c2b1  mov     eax, edi
0x18000c2b3  jmp     loc_18000C737
0x18000c2b8  xor     edi, edi
0x18000c2ba  mov     r15d, edi
0x18000c2bd  cmp     [rbp+37h+arg_48], edi
0x18000c2c3  jnz     loc_18000C4AA
0x18000c2c9  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c2d0  lea     r9, [rbp+37h+var_78]
0x18000c2d4  mov     [rbx+70h], rdi
0x18000c2d8  xor     r8d, r8d
0x18000c2db  mov     [rbx+60h], rdi
0x18000c2df  xor     edx, edx
0x18000c2e1  mov     [rbx+28h], rdi
0x18000c2e5  mov     rcx, r14
0x18000c2e8  mov     rax, [rax+0A0h]
0x18000c2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2f4  mov     rax, [rbp+37h+var_78]
0x18000c2f8  lea     rcx, [rbx+7Ah]
0x18000c2fc  test    rax, rax
0x18000c2ff  jz      short loc_18000C359
0x18000c301  movups  xmm0, xmmword ptr [rax]
0x18000c304  movdqu  xmmword ptr [rcx], xmm0
0x18000c308  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000c30c  mov     rdx, r15
0x18000c30f  inc     rdx
0x18000c312  cmp     [rsi+rdx*2], di
0x18000c316  jnz     short loc_18000C30F
0x18000c318  mov     [rbp+37h+Size], edx
0x18000c31b  test    edx, edx
0x18000c31d  jnz     short loc_18000C37D
0x18000c31f  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c326  lea     rcx, [rbp+37h+Size]
0x18000c32a  xor     r9d, r9d
0x18000c32d  mov     qword ptr [rsp+0E0h+dwMilliseconds], rcx
0x18000c332  xor     r8d, r8d
0x18000c335  mov     rax, [rax+20h]
0x18000c339  lea     r12d, [r9+1]
0x18000c33d  mov     ecx, r12d
0x18000c340  lea     edx, [r9+7]
0x18000c344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c349  mov     rsi, rax
0x18000c34c  test    rax, rax
0x18000c34f  jz      short loc_18000C3B5
0x18000c351  mov     edx, [rbp+37h+Size]
0x18000c354  mov     edi, r12d
0x18000c357  jmp     short loc_18000C382
0x18000c359  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c360  mov     edx, 10h
0x18000c365  mov     rax, [rax+18h]
0x18000c369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c36e  mov     [rbp+37h+var_88], eax
0x18000c371  test    eax, eax
0x18000c373  jz      short loc_18000C308
0x18000c375  mov     [rbp+37h+var_90], eax
0x18000c378  jmp     loc_18000C704
0x18000c37d  inc     edx
0x18000c37f  mov     [rbp+37h+Size], edx
0x18000c382  cmp     edx, 28h ; '('
0x18000c385  ja      short loc_18000C394
0x18000c387  lea     rax, [rbx+30h]
0x18000c38b  xor     r12d, r12d
0x18000c38e  mov     [rbx+28h], rax
0x18000c392  jmp     short loc_18000C3C2
0x18000c394  mov     ecx, edx; Size
0x18000c396  call    cs:__imp_I_RpcAllocate
0x18000c39c  xor     r12d, r12d
0x18000c39f  mov     [rbx+28h], rax
0x18000c3a3  test    rax, rax
0x18000c3a6  jnz     short loc_18000C3BF
0x18000c3a8  test    edi, edi
0x18000c3aa  jz      short loc_18000C3B5
0x18000c3ac  mov     rcx, rsi; Object
0x18000c3af  call    cs:__imp_I_RpcFree
0x18000c3b5  mov     eax, 0Eh
0x18000c3ba  jmp     loc_18000C737
0x18000c3bf  mov     edx, [rbp+37h+Size]; unsigned int
0x18000c3c2  mov     r8, rax; char *
0x18000c3c5  mov     rcx, rsi; unsigned __int16 *
0x18000c3c8  call    ?SimpleUnicodeToAnsi@@YAXPEAGKPEAD@Z; SimpleUnicodeToAnsi(ushort *,ulong,char *)
0x18000c3cd  mov     ecx, [rbp+37h+Size]
0x18000c3d0  dec     ecx
0x18000c3d2  mov     [rbx+58h], ecx
0x18000c3d5  test    edi, edi
0x18000c3d7  jz      short loc_18000C3E2
0x18000c3d9  mov     rcx, rsi; Object
0x18000c3dc  call    cs:__imp_I_RpcFree
0x18000c3e2  test    r13, r13
0x18000c3e5  jz      short loc_18000C3F3
0x18000c3e7  test    byte ptr [r13+8], 1
0x18000c3ec  mov     eax, 1
0x18000c3f1  jnz     short loc_18000C3F6
0x18000c3f3  mov     eax, r12d
0x18000c3f6  mov     rdx, [rbx+28h]; char *
0x18000c3fa  lea     rcx, [rbp+37h+var_88]
0x18000c3fe  mov     [rsp+0E0h+var_A0], rcx; unsigned int *
0x18000c403  lea     rsi, [rbx+20h]
0x18000c407  mov     [rsp+0E0h+var_A8], rsi; enum tagRPCProxyAccessType *
0x18000c40c  lea     rcx, [rbp+37h+var_70]
0x18000c410  mov     [rsp+0E0h+var_B0], rcx; char **
0x18000c415  lea     r9, [rbp+37h+Object]; char **
0x18000c419  lea     rcx, [rbx+70h]
0x18000c41d  mov     [rsp+0E0h+var_B8], rcx; char **
0x18000c422  lea     r8, [rbx+60h]; char **
0x18000c426  mov     rcx, [rbp+37h+var_68]; unsigned __int16 *
0x18000c42a  mov     [rsp+0E0h+dwMilliseconds], eax; int
0x18000c42e  call    ?HttpParseNetworkOptions@@YAHPEAGPEADPEAPEAD2H22PEAW4tagRPCProxyAccessType@@PEAK@Z; HttpParseNetworkOptions(ushort *,char *,char * *,char * *,int,char * *,char * *,tagRPCProxyAccessType *,ulong *)
0x18000c433  test    eax, eax
0x18000c435  jnz     short loc_18000C447
0x18000c437  mov     rcx, rbx; this
0x18000c43a  call    ?FreeRpcServer@HTTPResolverHint@@QEAAXXZ; HTTPResolverHint::FreeRpcServer(void)
0x18000c43f  mov     eax, [rbp+37h+var_88]
0x18000c442  jmp     loc_18000C737
0x18000c447  mov     rcx, [rbp+37h+var_60]; unsigned __int16 *
0x18000c44b  lea     rdx, [rbx+5Ch]; unsigned __int16 *
0x18000c44f  call    ?EndpointToPortNumber@@YAJPEAGAEAG@Z; EndpointToPortNumber(ushort *,ushort &)
0x18000c454  mov     r12, [rbp+37h+var_70]
0x18000c458  test    eax, eax
0x18000c45a  jnz     short loc_18000C4A2
0x18000c45c  mov     rcx, [rbp+37h+Object]; char *
0x18000c460  lea     rdx, [rbx+6Ch]; unsigned __int16 *
0x18000c464  call    ?EndpointToPortNumberA@@YAJPEADAEAG@Z; EndpointToPortNumberA(char *,ushort &)
0x18000c469  test    eax, eax
0x18000c46b  jnz     short loc_18000C4A2
0x18000c46d  mov     rax, [rbx+60h]
0x18000c471  xor     edi, edi
0x18000c473  inc     r15
0x18000c476  cmp     [rax+r15], dil
0x18000c47a  jnz     short loc_18000C473
0x18000c47c  mov     [rbx+68h], r15d
0x18000c480  cmp     [rbx+70h], rdi
0x18000c484  jz      short loc_18000C496
0x18000c486  lea     rdx, [rbx+78h]; unsigned __int16 *
0x18000c48a  mov     rcx, r12; char *
0x18000c48d  call    ?EndpointToPortNumberA@@YAJPEADAEAG@Z; EndpointToPortNumberA(char *,ushort &)
0x18000c492  test    eax, eax
0x18000c494  jnz     short loc_18000C4A2
0x18000c496  mov     r15d, 1
0x18000c49c  mov     [rbx+1Ch], r15d
0x18000c4a0  jmp     short loc_18000C4AE
0x18000c4a2  mov     [rbp+37h+var_90], eax
0x18000c4a5  jmp     loc_18000C6EC
0x18000c4aa  lea     rsi, [rbx+20h]
0x18000c4ae  cmp     dword ptr [rbx+1Ch], 1
0x18000c4b2  jnz     loc_18000C570
0x18000c4b8  mov     r8, [rbp+37h+var_58]; void *
0x18000c4bc  mov     rdx, r13; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x18000c4bf  mov     rcx, r14; this
0x18000c4c2  call    ??0HTTP2ClientVirtualConnection@@QEAA@PEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@PEAX@Z; HTTP2ClientVirtualConnection::HTTP2ClientVirtualConnection(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *,void *)
0x18000c4c7  mov     r9d, [rbp+37h+arg_28]; unsigned int
0x18000c4cb  mov     rdi, rax
0x18000c4ce  mov     r8d, [rbp+37h+arg_48]; int
0x18000c4d5  mov     eax, 1
0x18000c4da  mov     dword ptr [rsp+0E0h+var_A0], 0; int
0x18000c4e2  mov     rdx, rbx; struct HTTPResolverHint *
0x18000c4e5  mov     dword ptr [rsp+0E0h+var_A8], 0; int
0x18000c4ed  mov     rcx, rdi; this
0x18000c4f0  mov     dword ptr [rsp+0E0h+var_B0], eax; int
0x18000c4f4  mov     dword ptr [rsp+0E0h+var_B8], eax; int
0x18000c4f8  mov     eax, [rbp+37h+arg_50]
0x18000c4fe  mov     [rsp+0E0h+dwMilliseconds], eax; dwMilliseconds
0x18000c502  call    ?ClientOpenInternal@HTTP2ClientVirtualConnection@@AEAAJPEAVHTTPResolverHint@@HIKHHHH@Z; HTTP2ClientVirtualConnection::ClientOpenInternal(HTTPResolverHint *,int,uint,ulong,int,int,int,int)
0x18000c507  mov     ecx, 6C0h
0x18000c50c  cmp     eax, ecx
0x18000c50e  jz      short loc_18000C517
0x18000c510  cmp     eax, 0C0021009h
0x18000c515  jnz     short loc_18000C544
0x18000c517  test    r13, r13
0x18000c51a  jnz     short loc_18000C534
0x18000c51c  mov     [rbx+1Ch], r13d
0x18000c520  mov     rcx, rdi; this
0x18000c523  mov     [rdi+268h], r13
0x18000c52a  call    ??1HTTP2ClientVirtualConnection@@UEAA@XZ; HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(void)
0x18000c52f  jmp     loc_18000C4AE
0x18000c534  cmp     eax, ecx
0x18000c536  jz      short loc_18000C53F
0x18000c538  cmp     eax, 0C0021009h
0x18000c53d  jnz     short loc_18000C544
0x18000c53f  mov     eax, 6BAh
0x18000c544  mov     [rbp+37h+var_90], eax
0x18000c547  mov     ecx, eax
0x18000c549  mov     dword ptr [rdi+0Ch], 0Ah
0x18000c550  test    eax, eax
0x18000c552  jz      loc_18000C704
0x18000c558  mov     rcx, rdi; this
0x18000c55b  mov     qword ptr [rdi+268h], 0
0x18000c566  call    ??1HTTP2ClientVirtualConnection@@UEAA@XZ; HTTP2ClientVirtualConnection::~HTTP2ClientVirtualConnection(void)
0x18000c56b  jmp     loc_18000C6E7
0x18000c570  xor     edi, edi
0x18000c572  cmp     [rsi], edi
0x18000c574  jnz     short loc_18000C57C
0x18000c576  mov     dword ptr [rsi], 1
0x18000c57c  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c583  xor     r9d, r9d
0x18000c586  xor     r8d, r8d
0x18000c589  xor     edx, edx
0x18000c58b  mov     rcx, r14
0x18000c58e  mov     rax, [rax+48h]
0x18000c592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c597  mov     ecx, [rbp+37h+arg_50]
0x18000c59d  lea     rax, ??_7WS_CONNECTION@@6B@; const WS_CONNECTION::`vftable'
0x18000c5a4  mov     r9d, [rbp+37h+arg_30]
0x18000c5a8  mov     r13d, 6
0x18000c5ae  mov     r8d, [rbp+37h+arg_28]
0x18000c5b2  xor     edx, edx
0x18000c5b4  mov     [r14], rax
0x18000c5b7  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18000c5be  mov     dword ptr [rsp+0E0h+var_B0], edi
0x18000c5c2  mov     dword ptr [rsp+0E0h+var_B8], ecx
0x18000c5c6  mov     ecx, [rbp+37h+arg_38]
0x18000c5c9  mov     [r14+0Ch], r13d
0x18000c5cd  mov     rax, [rax+58h]
0x18000c5d1  mov     [rsp+0E0h+dwMilliseconds], ecx
0x18000c5d5  mov     rcx, r14
0x18000c5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5dd  test    eax, eax
0x18000c5df  jnz     loc_18000C6E4
0x18000c5e5  cmp     dword ptr [rsi], 2
0x18000c5e8  jz      short loc_18000C615
0x18000c5ea  mov     rcx, rbx; struct HTTPResolverHint *
0x18000c5ed  call    ?HTTP_CheckIPAddressForDirectConnection@@YAJPEAVHTTPResolverHint@@@Z; HTTP_CheckIPAddressForDirectConnection(HTTPResolverHint *)
0x18000c5f2  test    eax, eax
0x18000c5f4  jnz     loc_18000C6BB
0x18000c5fa  cmp     dword ptr [rsi], 1
0x18000c5fd  jnz     short loc_18000C61A
  ... truncated ...
```

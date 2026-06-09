# HttpProcessProxySettings(ushort *,int,ushort *,ushort *,ushort * *,ushort * *,tagRPCProxyAccessType *)

- ea: `0x18001deb0`
- end: `0x18001e16c`
- name: `?HttpProcessProxySettings@@YAJPEAGH00PEAPEAG1PEAW4tagRPCProxyAccessType@@@Z`
- size: `700`
- prototype: `__int64 __fastcall(unsigned __int16 *, int, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, enum tagRPCProxyAccessType *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cb10`

## callees

- `0x180002d80`
- `0x18001db64`
- `0x18001dc14`
- `0x18001deb0`
- `0x18001e2cc`
- `0x18001f1f4`
- `0x18001f214`
- `0x180024629`
- `0x180024640`
- `0x180025010`

## import_xrefs

- `ntdll!_wcsicmp` at `0x18001dfbd`
- `ntdll!_wcsicmp` at `0x18001dfbd`
- `KERNEL32!CompareStringW` at `0x18001e032`
- `KERNEL32!CompareStringW` at `0x18001e032`
- `RPCRT4!I_RpcFree` at `0x18001e0c4`
- `RPCRT4!I_RpcFree` at `0x18001e0f3`
- `RPCRT4!I_RpcFree` at `0x18001e105`
- `RPCRT4!I_RpcFree` at `0x18001e11e`
- `RPCRT4!I_RpcFree` at `0x18001e12c`
- `RPCRT4!I_RpcFree` at `0x18001e13a`
- `RPCRT4!I_RpcFree` at `0x18001e0c4`
- `RPCRT4!I_RpcFree` at `0x18001e0f3`
- `RPCRT4!I_RpcFree` at `0x18001e105`
- `RPCRT4!I_RpcFree` at `0x18001e11e`
- `RPCRT4!I_RpcFree` at `0x18001e12c`
- `RPCRT4!I_RpcFree` at `0x18001e13a`

## pseudocode

```c
__int64 __fastcall HttpProcessProxySettings(
        unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        enum tagRPCProxyAccessType *a7)
{
  unsigned __int16 **v7; // rsi
  int v10; // r13d
  unsigned __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // edi
  unsigned __int16 *v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // r14d
  unsigned __int16 *v21; // rcx
  unsigned int v22; // eax
  __int64 v23; // rdx
  int matched; // ebx
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  void *Object; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 **v28; // [rsp+40h] [rbp-C0h] BYREF
  enum tagRPCProxyAccessType *v29; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v30; // [rsp+50h] [rbp-B0h]
  _BYTE v31[96]; // [rsp+60h] [rbp-A0h] BYREF
  sockaddr_storage v32; // [rsp+C0h] [rbp-40h] BYREF

  v7 = 0;
  v30 = a1;
  v10 = 2;
  v29 = a7;
  v26 = 0;
  IP_ADDRESS_RESOLVER::IP_ADDRESS_RESOLVER(v31, a1, a3, 2);
  memset_0(&v32, 0, sizeof(v32));
  *a5 = 0;
  Object = 0;
  *a6 = 0;
  v28 = 0;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( v12 > 0xFDE8 )
      goto LABEL_36;
  }
  v13 = HttpParseProxyName(a3, a2, a5, a6);
  v14 = 0;
  v15 = v13;
  if ( v13 )
    goto LABEL_37;
  v16 = *a5;
  v17 = -1;
  do
    ++v17;
  while ( v16[v17] );
  if ( v17 > 0x3E8 )
    goto LABEL_36;
  v18 = -1;
  do
    ++v18;
  while ( (*a6)[v18] );
  if ( v18 > 5 )
  {
LABEL_36:
    v15 = 1724;
    goto LABEL_37;
  }
  if ( !*v16 || !_wcsicmp(v16, L"<none>") )
    goto LABEL_32;
  if ( !a4 )
  {
    *(_DWORD *)v29 = 2;
    goto LABEL_43;
  }
  v19 = HttpParseProxyBypassList(a4, &v28, &v26);
  v7 = v28;
  v15 = v19;
  if ( v19 )
    goto LABEL_37;
  v20 = v26;
  if ( v28 )
  {
    while ( v14 < v20 )
    {
      if ( CompareStringW(0x7Fu, 1u, L"<local>", -1, v7[v14], -1) == 2 )
      {
        v10 = 0;
        break;
      }
      ++v14;
    }
  }
  v21 = v30;
  *(_DWORD *)v29 = v10;
  if ( (unsigned int)MatchREList(v21, v7, v20) )
  {
    v15 = 0;
LABEL_32:
    *(_DWORD *)v29 = 1;
    if ( *a5 )
    {
      I_RpcFree(*a5);
      *a5 = 0;
    }
    if ( *a6 )
    {
      I_RpcFree(*a6);
      *a6 = 0;
    }
    goto LABEL_41;
  }
  while ( 1 )
  {
    v22 = IP_ADDRESS_RESOLVER::NextAddress((IP_ADDRESS_RESOLVER *)v31, &v32);
    v15 = v22;
    if ( v22 )
      break;
    v23 = 9;
    if ( v32.ss_family != 23 )
      v23 = v22 + 1;
    v15 = (*((__int64 (__fastcall **)(sockaddr_storage *, __int64, void **))pRuntimeImportTable + 17))(
            &v32,
            v23,
            &Object);
    if ( v15 )
      goto LABEL_37;
    matched = MatchREList((unsigned __int16 *)Object, v7, v20);
    I_RpcFree(Object);
    if ( matched )
      goto LABEL_32;
  }
  if ( v22 != 1722 )
  {
LABEL_37:
    if ( *a5 )
      I_RpcFree(*a5);
    if ( *a6 )
      I_RpcFree(*a6);
    goto LABEL_41;
  }
  v15 = 0;
LABEL_41:
  if ( v7 )
    I_RpcFree(v7);
LABEL_43:
  IP_ADDRESS_RESOLVER::~IP_ADDRESS_RESOLVER((IP_ADDRESS_RESOLVER *)v31);
  return v15;
}

```

## disassembly

```asm
0x18001deb0  push    rbp
0x18001deb2  push    rbx
0x18001deb3  push    rsi
0x18001deb4  push    rdi
0x18001deb5  push    r12
0x18001deb7  push    r13
0x18001deb9  push    r14
0x18001debb  push    r15
0x18001debd  lea     rbp, [rsp-58h]
0x18001dec2  sub     rsp, 158h
0x18001dec9  mov     rax, cs:__security_cookie
0x18001ded0  xor     rax, rsp
0x18001ded3  mov     [rbp+90h+var_50], rax
0x18001ded7  mov     rax, [rbp+90h+arg_30]
0x18001dede  xor     esi, esi
0x18001dee0  mov     r12, [rbp+90h+arg_20]
0x18001dee7  mov     edi, edx
0x18001dee9  mov     r15, [rbp+90h+arg_28]
0x18001def0  mov     rdx, rcx
0x18001def3  mov     r14, r9
0x18001def6  mov     [rsp+190h+var_140], rcx
0x18001defb  lea     r13d, [rsi+2]
0x18001deff  mov     [rsp+190h+var_148], rax
0x18001df04  mov     r9d, r13d
0x18001df07  mov     [rsp+190h+var_160], esi
0x18001df0b  lea     rcx, [rsp+190h+var_130]
0x18001df10  mov     rbx, r8
0x18001df13  call    ??0IP_ADDRESS_RESOLVER@@QEAA@PEAGW4tagClientOrServer@@W4tagIPVersionToUse@@@Z; IP_ADDRESS_RESOLVER::IP_ADDRESS_RESOLVER(ushort *,tagClientOrServer,tagIPVersionToUse)
0x18001df18  xor     edx, edx; Val
0x18001df1a  lea     r8d, [r13+7Eh]; Size
0x18001df1e  lea     rcx, [rbp+90h+var_D0]; void *
0x18001df22  call    memset_0
0x18001df27  xor     ecx, ecx
0x18001df29  mov     [r12], rsi
0x18001df2d  mov     [rsp+190h+Object], rsi
0x18001df32  mov     [r15], rsi
0x18001df35  mov     [rsp+190h+var_150], rsi
0x18001df3a  test    rbx, rbx
0x18001df3d  jz      short loc_18001DF58
0x18001df3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001df43  inc     rax
0x18001df46  cmp     [rbx+rax*2], cx
0x18001df4a  jnz     short loc_18001DF43
0x18001df4c  cmp     rax, 0FDE8h
0x18001df52  ja      loc_18001E110
0x18001df58  mov     r9, r15; unsigned __int16 **
0x18001df5b  mov     r8, r12; unsigned __int16 **
0x18001df5e  mov     edx, edi; int
0x18001df60  mov     rcx, rbx; Src
0x18001df63  call    ?HttpParseProxyName@@YAJPEAGHPEAPEAG1@Z; HttpParseProxyName(ushort *,int,ushort * *,ushort * *)
0x18001df68  xor     ebx, ebx
0x18001df6a  mov     edi, eax
0x18001df6c  test    eax, eax
0x18001df6e  jnz     loc_18001E115
0x18001df74  mov     rcx, [r12]; String1
0x18001df78  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001df7c  mov     rax, r8
0x18001df7f  inc     rax
0x18001df82  cmp     [rcx+rax*2], bx
0x18001df86  jnz     short loc_18001DF7F
0x18001df88  cmp     rax, 3E8h
0x18001df8e  ja      loc_18001E110
0x18001df94  mov     rdx, [r15]
0x18001df97  mov     rax, r8
0x18001df9a  inc     rax
0x18001df9d  cmp     [rdx+rax*2], bx
0x18001dfa1  jnz     short loc_18001DF9A
0x18001dfa3  cmp     rax, 5
0x18001dfa7  ja      loc_18001E110
0x18001dfad  cmp     [rcx], bx
0x18001dfb0  jz      loc_18001E0DF
0x18001dfb6  lea     rdx, aNone; "<none>"
0x18001dfbd  call    cs:__imp__wcsicmp
0x18001dfc3  test    eax, eax
0x18001dfc5  jz      loc_18001E0DF
0x18001dfcb  test    r14, r14
0x18001dfce  jnz     short loc_18001DFDD
0x18001dfd0  mov     rax, [rsp+190h+var_148]
0x18001dfd5  mov     [rax], r13d
0x18001dfd8  jmp     loc_18001E140
0x18001dfdd  lea     r8, [rsp+190h+var_160]; unsigned int *
0x18001dfe2  mov     rcx, r14; unsigned __int16 *
0x18001dfe5  lea     rdx, [rsp+190h+var_150]; unsigned __int16 ***
0x18001dfea  call    ?HttpParseProxyBypassList@@YAJPEAGPEAPEAPEAGPEAK@Z; HttpParseProxyBypassList(ushort *,ushort * * *,ulong *)
0x18001dfef  mov     rsi, [rsp+190h+var_150]
0x18001dff4  mov     edi, eax
0x18001dff6  test    eax, eax
0x18001dff8  jnz     loc_18001E115
0x18001dffe  mov     r14d, [rsp+190h+var_160]
0x18001e003  test    rsi, rsi
0x18001e006  jz      short loc_18001E04A
0x18001e008  cmp     ebx, r14d
0x18001e00b  jnb     short loc_18001E048
0x18001e00d  or      r9d, 0FFFFFFFFh; cchCount1
0x18001e011  mov     eax, ebx
0x18001e013  mov     [rsp+190h+cchCount2], 0FFFFFFFFh; cchCount2
0x18001e01b  lea     r8, String1; "<local>"
0x18001e022  mov     rax, [rsi+rax*8]
0x18001e026  lea     edx, [r9+2]; dwCmpFlags
0x18001e02a  lea     ecx, [rdx+7Eh]; Locale
0x18001e02d  mov     [rsp+190h+lpString2], rax; lpString2
0x18001e032  call    cs:__imp_CompareStringW
0x18001e038  cmp     eax, r13d
0x18001e03b  jz      short loc_18001E041
0x18001e03d  inc     ebx
0x18001e03f  jmp     short loc_18001E008
0x18001e041  xor     ebx, ebx
0x18001e043  mov     r13d, ebx
0x18001e046  jmp     short loc_18001E04A
0x18001e048  xor     ebx, ebx
0x18001e04a  mov     rax, [rsp+190h+var_148]
0x18001e04f  mov     r8d, r14d; unsigned int
0x18001e052  mov     rcx, [rsp+190h+var_140]; unsigned __int16 *
0x18001e057  mov     rdx, rsi; unsigned __int16 **
0x18001e05a  mov     [rax], r13d
0x18001e05d  call    ?MatchREList@@YAHPEAGPEAPEAGK@Z; MatchREList(ushort *,ushort * *,ulong)
0x18001e062  test    eax, eax
0x18001e064  jz      short loc_18001E06A
0x18001e066  mov     edi, ebx
0x18001e068  jmp     short loc_18001E0DF
0x18001e06a  lea     rdx, [rbp+90h+var_D0]; struct sockaddr_storage *
0x18001e06e  lea     rcx, [rsp+190h+var_130]; this
0x18001e073  call    ?NextAddress@IP_ADDRESS_RESOLVER@@QEAAJPEAUsockaddr_storage@@@Z; IP_ADDRESS_RESOLVER::NextAddress(sockaddr_storage *)
0x18001e078  mov     edi, eax
0x18001e07a  test    eax, eax
0x18001e07c  jnz     short loc_18001E0D2
0x18001e07e  cmp     [rbp+90h+var_D0.ss_family], 17h
0x18001e083  lea     r8, [rsp+190h+Object]
0x18001e088  mov     rax, cs:?pRuntimeImportTable@@3PEAU_RUNTIME_IMPORT_TABLE@@EA; _RUNTIME_IMPORT_TABLE * pRuntimeImportTable
0x18001e08f  lea     rcx, [rbp+90h+var_D0]
0x18001e093  lea     edx, [rdi+9]
0x18001e096  mov     rax, [rax+88h]
0x18001e09d  jz      short loc_18001E0A2
0x18001e09f  lea     edx, [rdi+1]
0x18001e0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0a7  mov     edi, eax
0x18001e0a9  test    eax, eax
0x18001e0ab  jnz     short loc_18001E115
0x18001e0ad  mov     rcx, [rsp+190h+Object]; unsigned __int16 *
0x18001e0b2  mov     r8d, r14d; unsigned int
0x18001e0b5  mov     rdx, rsi; unsigned __int16 **
0x18001e0b8  call    ?MatchREList@@YAHPEAGPEAPEAGK@Z; MatchREList(ushort *,ushort * *,ulong)
0x18001e0bd  mov     rcx, [rsp+190h+Object]; Object
0x18001e0c2  mov     ebx, eax
0x18001e0c4  call    cs:__imp_I_RpcFree
0x18001e0ca  test    ebx, ebx
0x18001e0cc  jnz     short loc_18001E0DD
0x18001e0ce  xor     ebx, ebx
0x18001e0d0  jmp     short loc_18001E06A
0x18001e0d2  cmp     eax, 6BAh
0x18001e0d7  jnz     short loc_18001E115
0x18001e0d9  mov     edi, ebx
0x18001e0db  jmp     short loc_18001E132
0x18001e0dd  xor     ebx, ebx
0x18001e0df  mov     rax, [rsp+190h+var_148]
0x18001e0e4  mov     dword ptr [rax], 1
0x18001e0ea  mov     rcx, [r12]; Object
0x18001e0ee  test    rcx, rcx
0x18001e0f1  jz      short loc_18001E0FD
0x18001e0f3  call    cs:__imp_I_RpcFree
0x18001e0f9  mov     [r12], rbx
0x18001e0fd  mov     rcx, [r15]; Object
0x18001e100  test    rcx, rcx
0x18001e103  jz      short loc_18001E132
0x18001e105  call    cs:__imp_I_RpcFree
0x18001e10b  mov     [r15], rbx
0x18001e10e  jmp     short loc_18001E132
0x18001e110  mov     edi, 6BCh
0x18001e115  mov     rcx, [r12]; Object
0x18001e119  test    rcx, rcx
0x18001e11c  jz      short loc_18001E124
0x18001e11e  call    cs:__imp_I_RpcFree
0x18001e124  mov     rcx, [r15]; Object
0x18001e127  test    rcx, rcx
0x18001e12a  jz      short loc_18001E132
0x18001e12c  call    cs:__imp_I_RpcFree
0x18001e132  test    rsi, rsi
0x18001e135  jz      short loc_18001E140
0x18001e137  mov     rcx, rsi; Object
0x18001e13a  call    cs:__imp_I_RpcFree
0x18001e140  lea     rcx, [rsp+190h+var_130]; this
0x18001e145  call    ??1IP_ADDRESS_RESOLVER@@QEAA@XZ; IP_ADDRESS_RESOLVER::~IP_ADDRESS_RESOLVER(void)
0x18001e14a  mov     eax, edi
0x18001e14c  mov     rcx, [rbp+90h+var_50]
0x18001e150  xor     rcx, rsp; StackCookie
0x18001e153  call    __security_check_cookie
0x18001e158  add     rsp, 158h
0x18001e15f  pop     r15
0x18001e161  pop     r14
0x18001e163  pop     r13
0x18001e165  pop     r12
0x18001e167  pop     rdi
0x18001e168  pop     rsi
0x18001e169  pop     rbx
0x18001e16a  pop     rbp
0x18001e16b  retn
```

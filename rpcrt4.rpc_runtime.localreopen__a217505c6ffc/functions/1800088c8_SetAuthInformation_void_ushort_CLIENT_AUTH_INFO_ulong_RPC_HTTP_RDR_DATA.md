# SetAuthInformation(void *,ushort *,CLIENT_AUTH_INFO *,ulong,RPC_HTTP_RDR_DATA *)

- ea: `0x1800088c8`
- end: `0x180008b4a`
- name: `?SetAuthInformation@@YAJPEAXPEAGPEAUCLIENT_AUTH_INFO@@KPEAVRPC_HTTP_RDR_DATA@@@Z`
- size: `642`
- prototype: `__int64 __usercall@<rax>(OSF_BINDING_HANDLE *this@<rcx>, unsigned __int16 *@<rdx>, struct CLIENT_AUTH_INFO *@<r8>, unsigned int@<r9d>, struct RPC_HTTP_RDR_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006fb4`

## callees

- `0x1800088c8`
- `0x18000add8`
- `0x180012f68`
- `0x180023a40`
- `0x180086bf0`
- `0x1800a8be0`
- `0x1800a9178`
- `0x1800b260c`
- `0x1800bb8a0`
- `0x1800c0088`
- `0x1800d7010`

## import_xrefs

- `SspiCli!SspiLocalFree` at `0x180008a5f`
- `SspiCli!SspiLocalFree` at `0x180008a5f`
- `SspiCli!SspiGetComputerNameForSPN` at `0x180008a2c`
- `SspiCli!SspiGetComputerNameForSPN` at `0x180008a2c`

## pseudocode

```c
__int64 __fastcall SetAuthInformation(
        OSF_BINDING_HANDLE *this,
        unsigned __int16 *a2,
        struct CLIENT_AUTH_INFO *a3,
        char a4,
        struct RPC_HTTP_RDR_DATA *a5)
{
  bool v5; // zf
  struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *v10; // rbx
  unsigned __int16 *v11; // rsi
  unsigned int v12; // ebp
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // ecx
  __int64 v16; // r8
  unsigned int v17; // edi
  struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *v19; // rax
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  int v22; // ecx
  unsigned int v23; // esi
  RPC_AUTH_IDENTITY_HANDLE TransportCredentials; // rcx
  RPC_AUTH_IDENTITY_HANDLE ProxyCredentials; // rcx
  PVOID DataBuffer; // [rsp+E0h] [rbp+8h] BYREF

  v5 = *((_DWORD *)a3 + 16) == 1;
  DataBuffer = 0;
  if ( !v5 )
  {
    v10 = 0;
    goto LABEL_3;
  }
  v19 = DuplicateHttpTransportCredentials(*((const struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W **)a3 + 9));
  v10 = v19;
  if ( !v19 )
    return 14;
  if ( v19->TransportCredentials )
  {
    v23 = DecryptAuthIdentity(v19->TransportCredentials);
    if ( v23 )
    {
      TransportCredentials = v10->TransportCredentials;
LABEL_26:
      WipeOutAuthIdentity(TransportCredentials);
      FreeHttpTransportCredentials(v10);
      return v23;
    }
  }
  ProxyCredentials = v10->ProxyCredentials;
  if ( ProxyCredentials )
  {
    v23 = DecryptAuthIdentity(ProxyCredentials);
    if ( v23 )
    {
      TransportCredentials = v10->ProxyCredentials;
      goto LABEL_26;
    }
  }
  if ( v10->TransportCredentials || v10->ProxyCredentials )
    v10->Flags &= ~4u;
LABEL_3:
  v11 = 0;
  if ( (g_fAuthenticatedEpResolution || (a4 & 1) != 0)
    && *(_DWORD *)a3 != 1
    && (v20 = *((_DWORD *)a3 + 1)) != 0
    && !(unsigned int)IsCertBasedAuthnService(v20) )
  {
    v12 = 5;
    if ( (unsigned int)CLIENT_AUTH_INFO::IsStdCredsSecurityProvider(v21) )
    {
      if ( (unsigned __int8)SspiGetComputerNameForSPN(a2, &DataBuffer) )
      {
        v11 = DuplicateString2(L"RPC/", (const unsigned __int16 *)DataBuffer);
        SspiLocalFree(DataBuffer);
        v13 = 9;
      }
      else
      {
        v13 = 10;
      }
      v14 = *((_QWORD *)a3 + 4);
      v15 = 2;
      v16 = *((_QWORD *)a3 + 5);
      goto LABEL_8;
    }
    v13 = 10;
    if ( v22 != 68 )
    {
      v14 = *((_QWORD *)a3 + 4);
      goto LABEL_7;
    }
  }
  else
  {
    v12 = 1;
    v13 = 0;
  }
  v14 = 0;
LABEL_7:
  v15 = 0;
  v16 = 0;
LABEL_8:
  v17 = (*(__int64 (__fastcall **)(OSF_BINDING_HANDLE *, unsigned __int16 *, _QWORD, __int64, __int64, __int64, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, unsigned int, _DWORD, struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *, _QWORD, _DWORD, int, _QWORD))(*(_QWORD *)this + 224LL))(
          this,
          v11,
          v12,
          v13,
          v14,
          v16,
          *((_DWORD *)a3 + 12),
          0,
          *((_DWORD *)a3 + 14),
          *((_DWORD *)a3 + 13),
          *((_DWORD *)a3 + 15),
          v15 | 1u,
          *((_DWORD *)a3 + 16),
          v10,
          0,
          0,
          1,
          0);
  if ( v10 )
  {
    WipeOutAuthIdentity(v10->TransportCredentials);
    WipeOutAuthIdentity(v10->ProxyCredentials);
    FreeHttpTransportCredentials(v10);
  }
  if ( !v17 && a5 )
    v17 = OSF_BINDING_HANDLE::SetRdrData(this, a5);
  if ( v11 )
    FreeWrapper(v11);
  return v17;
}

```

## disassembly

```asm
0x1800088c8  mov     rax, rsp
0x1800088cb  push    rbx
0x1800088cc  push    rbp
0x1800088cd  push    rsi
0x1800088ce  push    rdi
0x1800088cf  push    r14
0x1800088d1  push    r15
0x1800088d3  sub     rsp, 0A8h
0x1800088da  cmp     dword ptr [r8+40h], 1
0x1800088df  mov     ebp, r9d
0x1800088e2  mov     rdi, r8
0x1800088e5  mov     qword ptr [rax+8], 0
0x1800088ed  mov     r14, rdx
0x1800088f0  mov     r15, rcx
0x1800088f3  jz      loc_1800089D6
0x1800088f9  xor     ebx, ebx
0x1800088fb  xor     esi, esi
0x1800088fd  cmp     cs:?g_fAuthenticatedEpResolution@@3HA, esi; int g_fAuthenticatedEpResolution
0x180008903  jnz     loc_1800089F0
0x180008909  test    bpl, 1
0x18000890d  jnz     loc_1800089F0
0x180008913  mov     ebp, 1
0x180008918  xor     r9d, r9d
0x18000891b  xor     edx, edx
0x18000891d  xor     ecx, ecx
0x18000891f  xor     r8d, r8d
0x180008922  mov     rax, [r15]
0x180008925  or      ecx, 1
0x180008928  mov     [rsp+0D8h+var_50], 0
0x180008934  mov     [rsp+0D8h+var_58], 1
0x18000893f  mov     [rsp+0D8h+var_60], 0
0x180008947  mov     r10, [rax+0E0h]
0x18000894e  mov     eax, [rdi+40h]
0x180008951  mov     [rsp+0D8h+var_68], 0
0x18000895a  mov     [rsp+0D8h+var_70], rbx
0x18000895f  mov     [rsp+0D8h+var_78], eax
0x180008963  mov     rax, r10
0x180008966  mov     [rsp+0D8h+var_80], ecx
0x18000896a  mov     ecx, [rdi+3Ch]
0x18000896d  mov     [rsp+0D8h+var_88], ecx
0x180008971  mov     ecx, [rdi+34h]
0x180008974  mov     [rsp+0D8h+var_90], ecx
0x180008978  mov     ecx, [rdi+38h]
0x18000897b  mov     [rsp+0D8h+var_98], ecx
0x18000897f  mov     ecx, [rdi+30h]
0x180008982  mov     [rsp+0D8h+var_A0], 0
0x18000898b  mov     [rsp+0D8h+var_A8], ecx
0x18000898f  mov     rcx, r15
0x180008992  mov     [rsp+0D8h+var_B0], r8
0x180008997  mov     r8d, ebp
0x18000899a  mov     [rsp+0D8h+var_B8], rdx
0x18000899f  mov     rdx, rsi
0x1800089a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089a7  mov     edi, eax
0x1800089a9  test    rbx, rbx
0x1800089ac  jnz     loc_180008AFF
0x1800089b2  test    edi, edi
0x1800089b4  jz      loc_180008B1D
0x1800089ba  test    rsi, rsi
0x1800089bd  jnz     loc_180008B3D
0x1800089c3  mov     eax, edi
0x1800089c5  add     rsp, 0A8h
0x1800089cc  pop     r15
0x1800089ce  pop     r14
0x1800089d0  pop     rdi
0x1800089d1  pop     rsi
0x1800089d2  pop     rbp
0x1800089d3  pop     rbx
0x1800089d4  retn
0x1800089d6  mov     rcx, [r8+48h]; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x1800089da  call    ?DuplicateHttpTransportCredentials@@YAPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@PEBU1@@Z; DuplicateHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W const *)
0x1800089df  mov     rbx, rax
0x1800089e2  test    rax, rax
0x1800089e5  jnz     loc_180008A71
0x1800089eb  lea     eax, [rbx+0Eh]
0x1800089ee  jmp     short loc_1800089C5
0x1800089f0  cmp     dword ptr [rdi], 1
0x1800089f3  jz      loc_180008913
0x1800089f9  mov     ecx, [rdi+4]; unsigned int
0x1800089fc  test    ecx, ecx
0x1800089fe  jz      loc_180008913
0x180008a04  call    ?IsCertBasedAuthnService@@YAHK@Z; IsCertBasedAuthnService(ulong)
0x180008a09  test    eax, eax
0x180008a0b  jnz     loc_180008913
0x180008a11  lea     ebp, [rax+5]
0x180008a14  call    ?IsStdCredsSecurityProvider@CLIENT_AUTH_INFO@@SAHK@Z; CLIENT_AUTH_INFO::IsStdCredsSecurityProvider(ulong)
0x180008a19  test    eax, eax
0x180008a1b  jz      loc_180008AE7
0x180008a21  lea     rdx, [rsp+0D8h+DataBuffer]
0x180008a29  mov     rcx, r14
0x180008a2c  call    cs:__imp_SspiGetComputerNameForSPN
0x180008a33  nop     dword ptr [rax+rax+00h]
0x180008a38  test    al, al
0x180008a3a  jz      loc_180008ACF
0x180008a40  mov     rdx, [rsp+0D8h+DataBuffer]; unsigned __int16 *
0x180008a48  lea     rcx, aRpc; "RPC/"
0x180008a4f  call    ?DuplicateString2@@YAPEAGPEBG0@Z; DuplicateString2(ushort const *,ushort const *)
0x180008a54  mov     rcx, [rsp+0D8h+DataBuffer]; DataBuffer
0x180008a5c  mov     rsi, rax
0x180008a5f  call    cs:__imp_SspiLocalFree
0x180008a66  nop     dword ptr [rax+rax+00h]
0x180008a6b  lea     r9d, [rbp+4]
0x180008a6f  jmp     short loc_180008AD5
0x180008a71  mov     rcx, [rax]; void *
0x180008a74  test    rcx, rcx
0x180008a77  jz      short loc_180008AA1
0x180008a79  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x180008a7e  mov     esi, eax
0x180008a80  test    eax, eax
0x180008a82  jz      short loc_180008AA1
0x180008a84  mov     rcx, [rbx]
0x180008a87  jmp     short loc_180008A8D
0x180008a89  mov     rcx, [rbx+28h]; void *
0x180008a8d  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x180008a92  mov     rcx, rbx; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x180008a95  call    ?FreeHttpTransportCredentials@@YAXPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@@Z; FreeHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *)
0x180008a9a  mov     eax, esi
0x180008a9c  jmp     loc_1800089C5
0x180008aa1  mov     rcx, [rbx+28h]; void *
0x180008aa5  test    rcx, rcx
0x180008aa8  jz      short loc_180008AB5
0x180008aaa  call    ?DecryptAuthIdentity@@YAJPEAX@Z; DecryptAuthIdentity(void *)
0x180008aaf  mov     esi, eax
0x180008ab1  test    eax, eax
0x180008ab3  jnz     short loc_180008A89
0x180008ab5  cmp     qword ptr [rbx], 0
0x180008ab9  jnz     short loc_180008AC6
0x180008abb  cmp     qword ptr [rbx+28h], 0
0x180008ac0  jz      loc_1800088FB
0x180008ac6  and     dword ptr [rbx+8], 0FFFFFFFBh
0x180008aca  jmp     loc_1800088FB
0x180008acf  mov     r9d, 0Ah
0x180008ad5  mov     rdx, [rdi+20h]
0x180008ad9  mov     ecx, 2
0x180008ade  mov     r8, [rdi+28h]
0x180008ae2  jmp     loc_180008922
0x180008ae7  mov     r9d, 0Ah
0x180008aed  cmp     ecx, 44h ; 'D'
0x180008af0  jz      loc_18000891B
0x180008af6  mov     rdx, [rdi+20h]
0x180008afa  jmp     loc_18000891D
0x180008aff  mov     rcx, [rbx]; void *
0x180008b02  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x180008b07  mov     rcx, [rbx+28h]; void *
0x180008b0b  call    ?WipeOutAuthIdentity@@YAXPEAX@Z; WipeOutAuthIdentity(void *)
0x180008b10  mov     rcx, rbx; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *
0x180008b13  call    ?FreeHttpTransportCredentials@@YAXPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W@@@Z; FreeHttpTransportCredentials(_RPC_HTTP_TRANSPORT_CREDENTIALS_V3_W *)
0x180008b18  jmp     loc_1800089B2
0x180008b1d  mov     rdx, [rsp+0D8h+arg_20]; struct RPC_HTTP_RDR_DATA *
0x180008b25  test    rdx, rdx
0x180008b28  jz      loc_1800089BA
0x180008b2e  mov     rcx, r15; this
0x180008b31  call    ?SetRdrData@OSF_BINDING_HANDLE@@QEAAJPEBVRPC_HTTP_RDR_DATA@@@Z; OSF_BINDING_HANDLE::SetRdrData(RPC_HTTP_RDR_DATA const *)
0x180008b36  mov     edi, eax
0x180008b38  jmp     loc_1800089BA
0x180008b3d  mov     rcx, rsi; lpMem
0x180008b40  call    ?FreeWrapper@@YAXPEAX@Z; FreeWrapper(void *)
0x180008b45  jmp     loc_1800089C3
```

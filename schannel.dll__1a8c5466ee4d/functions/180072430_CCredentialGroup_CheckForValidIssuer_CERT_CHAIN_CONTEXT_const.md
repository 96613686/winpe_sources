# CCredentialGroup::CheckForValidIssuer(_CERT_CHAIN_CONTEXT const *)

- ea: `0x180072430`
- end: `0x180072578`
- name: `?CheckForValidIssuer@CCredentialGroup@@QEAAEPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `328`
- prototype: `unsigned __int8 __fastcall(CCredentialGroup *__hidden this, const struct _CERT_CHAIN_CONTEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180084b18`

## callees

- `0x180021da8`
- `0x180057c8c`
- `0x180072430`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x1800724a0`
- `ntdll!RtlReleaseResource` at `0x1800724a0`
- `ntdll!RtlAcquireResourceShared` at `0x18007245d`
- `ntdll!RtlAcquireResourceShared` at `0x18007245d`
- `CRYPT32!CertCompareCertificateName` at `0x18007254f`
- `CRYPT32!CertCompareCertificateName` at `0x18007254f`

## pseudocode

```c
char __fastcall CCredentialGroup::CheckForValidIssuer(CCredentialGroup *this, const struct _CERT_CHAIN_CONTEXT *a2)
{
  struct _RTL_RESOURCE *v2; // r12
  char v5; // bl
  unsigned __int8 *v6; // rdi
  __int64 v8; // rsi
  unsigned __int64 v9; // r15
  PCERT_SIMPLE_CHAIN v10; // r13
  _BYTE *v11; // r14
  __int64 i; // rbp
  PCCERT_CONTEXT pCertContext; // rcx
  struct _CRYPTOAPI_BLOB pCertName2; // [rsp+20h] [rbp-58h] BYREF

  v2 = (struct _RTL_RESOURCE *)((char *)this + 112);
  v5 = 1;
  pCertName2 = 0;
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)this + 112), 1u);
  v6 = (unsigned __int8 *)*((_QWORD *)this + 116);
  if ( v6 )
  {
    v8 = *((unsigned int *)this + 230);
    if ( (unsigned int)v8 >= 2 )
    {
      v9 = (unsigned __int64)&v6[v8];
      v10 = *a2->rgpChain;
      while ( 1 )
      {
        v11 = v6 + 1;
        if ( (unsigned __int64)(v6 + 1) >= v9 )
          break;
        pCertName2.pbData = v6 + 2;
        LOBYTE(pCertName2.cbData) = *v11;
        BYTE1(pCertName2.cbData) = *v6;
        if ( pCertName2.cbData > (unsigned int)v8 )
          break;
        for ( i = 0; (unsigned int)i < v10->cElement; i = (unsigned int)(i + 1) )
        {
          pCertContext = v10->rgpElement[i]->pCertContext;
          if ( CertCompareCertificateName(
                 pCertContext->dwCertEncodingType,
                 &pCertContext->pCertInfo->Issuer,
                 &pCertName2) )
          {
            goto LABEL_6;
          }
        }
        v6 += ((unsigned __int8)*v11 | ((unsigned __int64)*v6 << 8)) + 2;
      }
    }
    else if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        39,
        WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids,
        (unsigned int)v8);
    }
  }
  else if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids);
  }
  v5 = 0;
LABEL_6:
  RtlReleaseResource(v2);
  return v5;
}

```

## disassembly

```asm
0x180072430  push    rbx
0x180072432  push    rbp
0x180072433  push    rsi
0x180072434  push    rdi
0x180072435  push    r12
0x180072437  push    r13
0x180072439  push    r14
0x18007243b  push    r15
0x18007243d  sub     rsp, 38h
0x180072441  lea     r12, [rcx+70h]
0x180072445  mov     rbp, rdx
0x180072448  mov     rsi, rcx
0x18007244b  xorps   xmm0, xmm0
0x18007244e  mov     ebx, 1
0x180072453  mov     rcx, r12; Resource
0x180072456  mov     dl, bl; Wait
0x180072458  movups  xmmword ptr [rsp+78h+pCertName2.cbData], xmm0
0x18007245d  call    cs:__imp_RtlAcquireResourceShared
0x180072463  mov     rdi, [rsi+3A0h]
0x18007246a  test    rdi, rdi
0x18007246d  jnz     short loc_1800724B9
0x18007246f  mov     rcx, cs:WPP_GLOBAL_Control
0x180072476  lea     rax, WPP_GLOBAL_Control
0x18007247d  cmp     rcx, rax
0x180072480  jz      short loc_18007249B
0x180072482  test    byte ptr [rcx+1Ch], 2
0x180072486  jz      short loc_18007249B
0x180072488  mov     rcx, [rcx+10h]
0x18007248c  lea     edx, [rbx+25h]
0x18007248f  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x180072496  call    WPP_SF_
0x18007249b  xor     bl, bl
0x18007249d  mov     rcx, r12; Resource
0x1800724a0  call    cs:__imp_RtlReleaseResource
0x1800724a6  mov     al, bl
0x1800724a8  add     rsp, 38h
0x1800724ac  pop     r15
0x1800724ae  pop     r14
0x1800724b0  pop     r13
0x1800724b2  pop     r12
0x1800724b4  pop     rdi
0x1800724b5  pop     rsi
0x1800724b6  pop     rbp
0x1800724b7  pop     rbx
0x1800724b8  retn
0x1800724b9  mov     esi, [rsi+398h]
0x1800724bf  cmp     esi, 2
0x1800724c2  jnb     short loc_1800724F7
0x1800724c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800724cb  lea     rax, WPP_GLOBAL_Control
0x1800724d2  cmp     rcx, rax
0x1800724d5  jz      short loc_18007249B
0x1800724d7  test    byte ptr [rcx+1Ch], 2
0x1800724db  jz      short loc_18007249B
0x1800724dd  mov     rcx, [rcx+10h]
0x1800724e1  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x1800724e8  mov     edx, 27h ; '''
0x1800724ed  mov     r9d, esi
0x1800724f0  call    WPP_SF_d
0x1800724f5  jmp     short loc_18007249B
0x1800724f7  mov     rax, [rbp+10h]
0x1800724fb  lea     r15, [rdi+rsi]
0x1800724ff  mov     r13, [rax]
0x180072502  lea     r14, [rdi+1]
0x180072506  cmp     r14, r15
0x180072509  jnb     short loc_18007249B
0x18007250b  lea     rax, [rdi+2]
0x18007250f  mov     [rsp+78h+pCertName2.pbData], rax
0x180072514  movzx   ecx, byte ptr [rdi]
0x180072517  movzx   eax, byte ptr [r14]
0x18007251b  shl     ecx, 8
0x18007251e  or      ecx, eax
0x180072520  mov     [rsp+78h+pCertName2.cbData], ecx
0x180072524  cmp     ecx, esi
0x180072526  ja      loc_18007249B
0x18007252c  xor     ebp, ebp
0x18007252e  cmp     ebp, [r13+0Ch]
0x180072532  jnb     short loc_180072561
0x180072534  mov     rax, [r13+10h]
0x180072538  lea     r8, [rsp+78h+pCertName2]; pCertName2
0x18007253d  mov     rcx, [rax+rbp*8]
0x180072541  mov     rcx, [rcx+8]
0x180072545  mov     rdx, [rcx+18h]
0x180072549  mov     ecx, [rcx]; dwCertEncodingType
0x18007254b  add     rdx, 30h ; '0'; pCertName1
0x18007254f  call    cs:__imp_CertCompareCertificateName
0x180072555  test    eax, eax
0x180072557  jnz     loc_18007249D
0x18007255d  add     ebp, ebx
0x18007255f  jmp     short loc_18007252E
0x180072561  movzx   ecx, byte ptr [rdi]
0x180072564  add     rdi, 2
0x180072568  movzx   eax, byte ptr [r14]
0x18007256c  shl     rcx, 8
0x180072570  or      rcx, rax
0x180072573  add     rdi, rcx
0x180072576  jmp     short loc_180072502
```

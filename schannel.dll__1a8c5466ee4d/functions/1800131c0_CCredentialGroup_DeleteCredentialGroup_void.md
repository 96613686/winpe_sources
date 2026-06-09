# CCredentialGroup::DeleteCredentialGroup(void)

- ea: `0x1800131c0`
- end: `0x1800136d5`
- name: `?DeleteCredentialGroup@CCredentialGroup@@AEAAXXZ`
- size: `1301`
- prototype: `void __fastcall(CCredentialGroup *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013130`

## callees

- `0x1800131c0`
- `0x180014240`
- `0x18003f740`
- `0x18005c3a0`
- `0x1800736f4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013513`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001353d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013508`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013513`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001353d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013548`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800135c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800136ca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008ad27`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18008ad27`
- `ntdll!RtlDeleteResource` at `0x18001346f`
- `ntdll!RtlDeleteResource` at `0x18001346f`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800131f5`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800131f5`
- `ntdll!RtlReleaseResource` at `0x180013465`
- `ntdll!RtlReleaseResource` at `0x180013465`
- `ntdll!NtClose` at `0x180013427`
- `ntdll!NtClose` at `0x180013427`
- `CRYPT32!CertCloseStore` at `0x18008ad01`
- `CRYPT32!CertCloseStore` at `0x18008ad16`
- `CRYPT32!CertCloseStore` at `0x18008ad3c`
- `CRYPT32!CertCloseStore` at `0x18008ad51`
- `CRYPT32!CertCloseStore` at `0x18008ad01`
- `CRYPT32!CertCloseStore` at `0x18008ad16`
- `CRYPT32!CertCloseStore` at `0x18008ad3c`
- `CRYPT32!CertCloseStore` at `0x18008ad51`
- `CRYPT32!CertFreeCTLContext` at `0x1800135f7`
- `CRYPT32!CertFreeCTLContext` at `0x1800135f7`
- `CRYPT32!CryptObjectLocatorFree` at `0x18001365b`
- `CRYPT32!CryptObjectLocatorFree` at `0x180013666`
- `CRYPT32!CryptObjectLocatorFree` at `0x18001365b`
- `CRYPT32!CryptObjectLocatorFree` at `0x180013666`

## pseudocode

```c
void __fastcall CCredentialGroup::DeleteCredentialGroup(CCredentialGroup *this)
{
  unsigned int v1; // r13d
  void *v3; // rcx
  char *v4; // rdi
  unsigned int v5; // esi
  unsigned int v6; // r12d
  __int64 v7; // r15
  char *v8; // r14
  void *v9; // rcx
  unsigned int v10; // r14d
  __int64 v11; // rdx
  __int64 v12; // r13
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  CCredentialGroup *v16; // rcx
  _QWORD *v17; // rdi
  void *v18; // rdx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rdx
  void *v24; // rdx
  void *v25; // rcx
  void *v26; // rcx
  __int64 v27; // rcx
  _QWORD *v28; // rdi
  _QWORD *v29; // rsi
  unsigned int v30; // ecx
  void *v31; // rcx
  _QWORD *v32; // rcx
  void *v33; // rcx
  __int64 v34; // rdx
  const CTL_CONTEXT *v35; // rcx
  CCredentialGroup *v36; // rcx
  unsigned int i; // [rsp+60h] [rbp+8h]
  int v38; // [rsp+68h] [rbp+10h] BYREF

  v1 = 0;
  v38 = 0;
  if ( *((_DWORD *)this + 52) )
  {
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)this + 112), 1u);
    if ( *((_DWORD *)this + 23) )
    {
      v28 = (_QWORD *)*((_QWORD *)this + 12);
      v29 = (_QWORD *)((char *)this + 96);
      while ( v28 != v29 )
      {
        v32 = v28 - 1;
        v28 = (_QWORD *)*v28;
        if ( v32 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v32 + 8LL))(v32, 1);
      }
      *((_DWORD *)this + 23) = 0;
      *v29 = 0;
      *((_QWORD *)this + 13) = 0;
    }
    v3 = (void *)*((_QWORD *)this + 31);
    if ( v3 )
      SPExternalFree(v3);
    v4 = (char *)*((_QWORD *)this + 33);
    if ( v4 )
    {
      v5 = 0;
      v6 = *((_DWORD *)this + 65);
      if ( v6 )
      {
        do
        {
          v7 = 40LL * v5;
          v8 = &v4[v7];
          if ( *(_DWORD *)&v4[v7] )
          {
            do
            {
              v27 = *((_QWORD *)v8 + 1);
              if ( v27 )
              {
                v33 = *(void **)(v27 + 16LL * v1 + 8);
                if ( v33 )
                  SPExternalFree(v33);
              }
              ++v1;
            }
            while ( v1 < *(_DWORD *)&v4[v7] );
          }
          v9 = (void *)*((_QWORD *)v8 + 1);
          if ( v9 )
          {
            if ( LsaTable )
              (*(void (**)(void))(LsaTable + 48))();
            else
              LocalFree(v9);
            v1 = 0;
            *((_QWORD *)v8 + 1) = 0;
            *(_DWORD *)&v4[v7] = 0;
          }
          else
          {
            v1 = 0;
          }
          v10 = 0;
          if ( *(_DWORD *)&v4[v7 + 20] )
          {
            do
            {
              v11 = *(_QWORD *)&v4[v7 + 24];
              if ( !v11 )
                break;
              v12 = v11 + 48LL * v10;
              v13 = *(void **)(v12 + 16);
              if ( v13 )
              {
                if ( LsaTable )
                  (*(void (**)(void))(LsaTable + 48))();
                else
                  LocalFree(v13);
              }
              if ( *(_QWORD *)(v12 + 32) )
              {
                v30 = 0;
                for ( i = 0; v30 < *(_DWORD *)(v12 + 24); i = v30 )
                {
                  v34 = *(_QWORD *)(v12 + 32);
                  if ( v34 && *(_QWORD *)(v34 + 16LL * v30 + 8) )
                  {
                    SPExternalFree(*(void **)(v34 + 16LL * v30 + 8));
                    v30 = i;
                  }
                  ++v30;
                }
                v31 = *(void **)(v12 + 32);
                if ( v31 )
                {
                  SPExternalFree(v31);
                  *(_QWORD *)(v12 + 32) = 0;
                }
              }
              ++v10;
            }
            while ( v10 < *(_DWORD *)&v4[v7 + 20] );
            v1 = 0;
          }
          v14 = *(void **)&v4[v7 + 24];
          if ( v14 )
          {
            if ( LsaTable )
              (*(void (**)(void))(LsaTable + 48))();
            else
              LocalFree(v14);
            *(_QWORD *)&v4[v7 + 24] = 0;
            *(_DWORD *)&v4[v7 + 20] = 0;
          }
          ++v5;
        }
        while ( v5 < v6 );
      }
      if ( LsaTable )
        (*(void (__fastcall **)(char *))(LsaTable + 48))(v4);
      else
        LocalFree(v4);
      *((_QWORD *)this + 33) = 0;
      *((_DWORD *)this + 65) = 0;
    }
    v15 = (void *)*((_QWORD *)this + 116);
    if ( v15 )
      LocalFree(v15);
    v16 = (CCredentialGroup *)*((_QWORD *)this + 117);
    if ( v16 )
      (*(void (__fastcall **)(CCredentialGroup *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 1);
    v17 = (_QWORD *)*((_QWORD *)this + 114);
    if ( v17 )
    {
      v35 = (const CTL_CONTEXT *)v17[5];
      if ( v35 )
        CertFreeCTLContext(v35);
      SPExternalFree(v17);
    }
    v18 = (void *)*((_QWORD *)this + 104);
    if ( v18 )
    {
      if ( *((_QWORD *)this + 105) )
        CCredentialGroup::UnsubscribeCertStoreChangeNotification(v16, v18, (void **)this + 105);
      CertCloseStore(*((HCERTSTORE *)this + 104), 0);
    }
    v19 = (void *)*((_QWORD *)this + 118);
    if ( v19 )
      SPExternalFree(v19);
    v20 = (void *)*((_QWORD *)this + 119);
    if ( v20 )
      SPExternalFree(v20);
    if ( *((_QWORD *)this + 106) )
    {
      if ( !SslImpersonateClient(*((void **)this + 102), &v38) && *((_QWORD *)this + 107) )
        CCredentialGroup::UnsubscribeCertStoreChangeNotification(v36, *((void **)this + 106), (void **)this + 107);
      CertCloseStore(*((HCERTSTORE *)this + 106), 0);
      if ( v38 )
        RevertToSelf();
    }
    v21 = (void *)*((_QWORD *)this + 108);
    if ( v21 )
      CryptObjectLocatorFree(v21);
    v22 = (void *)*((_QWORD *)this + 109);
    if ( v22 )
      CryptObjectLocatorFree(v22);
    v23 = (void *)*((_QWORD *)this + 110);
    if ( v23 )
    {
      if ( *((_QWORD *)this + 111) )
        CCredentialGroup::UnsubscribeCertStoreChangeNotification((CCredentialGroup *)v22, v23, (void **)this + 111);
      CertCloseStore(*((HCERTSTORE *)this + 110), 0);
    }
    v24 = (void *)*((_QWORD *)this + 112);
    if ( v24 )
    {
      if ( *((_QWORD *)this + 113) )
        CCredentialGroup::UnsubscribeCertStoreChangeNotification((CCredentialGroup *)v22, v24, (void **)this + 113);
      CertCloseStore(*((HCERTSTORE *)this + 112), 0);
    }
    v25 = (void *)*((_QWORD *)this + 102);
    if ( v25 )
    {
      NtClose(v25);
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          24,
          WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids,
          *((_QWORD *)this + 102));
      *((_QWORD *)this + 102) = 0;
    }
    v26 = (void *)*((_QWORD *)this + 120);
    if ( v26 )
      LocalFree(v26);
    RtlReleaseResource((PRTL_RESOURCE)((char *)this + 112));
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 112));
  }
}

```

## disassembly

```asm
0x1800131c0  push    rbx
0x1800131c2  push    r13
0x1800131c4  sub     rsp, 48h
0x1800131c8  xor     r13d, r13d
0x1800131cb  mov     rbx, rcx
0x1800131ce  mov     [rsp+58h+arg_8], r13d
0x1800131d3  cmp     [rcx+0D0h], r13d
0x1800131da  jz      loc_18001347A
0x1800131e0  mov     [rsp+58h+arg_10], rbp
0x1800131e5  mov     dl, 1; Wait
0x1800131e7  mov     [rsp+58h+var_20], rdi
0x1800131ec  add     rcx, 70h ; 'p'; Resource
0x1800131f0  mov     [rsp+58h+var_18], rsi
0x1800131f5  call    cs:__imp_RtlAcquireResourceExclusive
0x1800131fb  cmp     [rbx+5Ch], r13d
0x1800131ff  jnz     loc_1800134BC
0x180013205  mov     rcx, [rbx+0F8h]; void *
0x18001320c  test    rcx, rcx
0x18001320f  jnz     loc_1800135B1
0x180013215  mov     rdi, [rbx+108h]
0x18001321c  test    rdi, rdi
0x18001321f  jz      loc_180013363
0x180013225  mov     [rsp+58h+var_28], r12
0x18001322a  mov     esi, r13d
0x18001322d  mov     r12d, [rbx+104h]
0x180013234  test    r12d, r12d
0x180013237  jz      loc_180013334
0x18001323d  mov     [rsp+58h+var_30], r14
0x180013242  mov     [rsp+58h+var_38], r15
0x180013247  mov     eax, esi
0x180013249  lea     rcx, [rax+rax*4]
0x18001324d  lea     r15, ds:0[rcx*8]
0x180013255  cmp     dword ptr [r15+rdi], 0
0x18001325a  lea     r14, [r15+rdi]
0x18001325e  ja      loc_1800134A0
0x180013264  mov     rcx, [r14+8]; hMem
0x180013268  test    rcx, rcx
0x18001326b  jz      loc_180013482
0x180013271  mov     rax, cs:LsaTable
0x180013278  test    rax, rax
0x18001327b  jz      loc_180013548
0x180013281  mov     rax, [rax+30h]
0x180013285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001328a  xor     r13d, r13d
0x18001328d  mov     [r14+8], r13
0x180013291  mov     [r15+rdi], r13d
0x180013295  cmp     dword ptr [rdi+r15+14h], 0
0x18001329b  mov     r14d, r13d
0x18001329e  jbe     short loc_1800132F2
0x1800132a0  mov     rdx, [r15+rdi+18h]
0x1800132a5  test    rdx, rdx
0x1800132a8  jz      short loc_1800132EF
0x1800132aa  mov     eax, r14d
0x1800132ad  lea     r13, [rax+rax*2]
0x1800132b1  shl     r13, 4
0x1800132b5  add     r13, rdx
0x1800132b8  mov     rcx, [r13+10h]; hMem
0x1800132bc  test    rcx, rcx
0x1800132bf  jz      short loc_1800132DA
0x1800132c1  mov     rax, cs:LsaTable
0x1800132c8  test    rax, rax
0x1800132cb  jz      loc_18001353D
0x1800132d1  mov     rax, [rax+30h]
0x1800132d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132da  cmp     qword ptr [r13+20h], 0
0x1800132df  jnz     loc_1800134D9
0x1800132e5  inc     r14d
0x1800132e8  cmp     r14d, [rdi+r15+14h]
0x1800132ed  jb      short loc_1800132A0
0x1800132ef  xor     r13d, r13d
0x1800132f2  mov     rcx, [r15+rdi+18h]; hMem
0x1800132f7  test    rcx, rcx
0x1800132fa  jz      short loc_18001331F
0x1800132fc  mov     rax, cs:LsaTable
0x180013303  test    rax, rax
0x180013306  jz      loc_180013513
0x18001330c  mov     rax, [rax+30h]
0x180013310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013315  mov     [r15+rdi+18h], r13
0x18001331a  mov     [rdi+r15+14h], r13d
0x18001331f  inc     esi
0x180013321  cmp     esi, r12d
0x180013324  jb      loc_180013247
0x18001332a  mov     r15, [rsp+58h+var_38]
0x18001332f  mov     r14, [rsp+58h+var_30]
0x180013334  mov     rax, cs:LsaTable
0x18001333b  mov     rcx, rdi; hMem
0x18001333e  mov     r12, [rsp+58h+var_28]
0x180013343  test    rax, rax
0x180013346  jz      loc_180013508
0x18001334c  mov     rax, [rax+30h]
0x180013350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013355  mov     [rbx+108h], r13
0x18001335c  mov     [rbx+104h], r13d
0x180013363  mov     rcx, [rbx+3A0h]; hMem
0x18001336a  mov     rsi, [rsp+58h+var_18]
0x18001336f  test    rcx, rcx
0x180013372  jnz     loc_1800135C9
0x180013378  mov     rcx, [rbx+3A8h]; this
0x18001337f  test    rcx, rcx
0x180013382  jnz     loc_1800135D4
0x180013388  mov     rdi, [rbx+390h]
0x18001338f  test    rdi, rdi
0x180013392  jnz     loc_1800135EA
0x180013398  mov     rdx, [rbx+340h]; void *
0x18001339f  mov     rdi, [rsp+58h+var_20]
0x1800133a4  test    rdx, rdx
0x1800133a7  jnz     loc_180013603
0x1800133ad  mov     rcx, [rbx+3B0h]; void *
0x1800133b4  test    rcx, rcx
0x1800133b7  jnz     loc_18001348A
0x1800133bd  mov     rcx, [rbx+3B8h]; void *
0x1800133c4  test    rcx, rcx
0x1800133c7  jnz     loc_180013533
0x1800133cd  cmp     qword ptr [rbx+350h], 0
0x1800133d5  jnz     loc_18001361F
0x1800133db  mov     rcx, [rbx+360h]
0x1800133e2  test    rcx, rcx
0x1800133e5  jnz     loc_18001365B
0x1800133eb  mov     rcx, [rbx+368h]; this
0x1800133f2  test    rcx, rcx
0x1800133f5  jnz     loc_180013666
0x1800133fb  mov     rdx, [rbx+370h]; void *
0x180013402  test    rdx, rdx
0x180013405  jnz     loc_180013671
0x18001340b  mov     rdx, [rbx+380h]; void *
0x180013412  test    rdx, rdx
0x180013415  jnz     loc_18001368D
0x18001341b  mov     rcx, [rbx+330h]; Handle
0x180013422  test    rcx, rcx
0x180013425  jz      short loc_180013451
0x180013427  call    cs:__imp_NtClose
0x18001342d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013434  lea     rax, WPP_GLOBAL_Control
0x18001343b  cmp     rcx, rax
0x18001343e  jz      short loc_18001344A
0x180013440  test    byte ptr [rcx+1Ch], 4
0x180013444  jnz     loc_1800136A9
0x18001344a  mov     [rbx+330h], r13
0x180013451  mov     rcx, [rbx+3C0h]; hMem
0x180013458  test    rcx, rcx
0x18001345b  jnz     loc_1800136CA
0x180013461  lea     rcx, [rbx+70h]; Resource
0x180013465  call    cs:__imp_RtlReleaseResource
0x18001346b  lea     rcx, [rbx+70h]; Resource
0x18001346f  call    cs:__imp_RtlDeleteResource
0x180013475  mov     rbp, [rsp+58h+arg_10]
0x18001347a  add     rsp, 48h
0x18001347e  pop     r13
0x180013480  pop     rbx
0x180013481  retn
0x180013482  xor     r13d, r13d
0x180013485  jmp     loc_180013295
0x18001348a  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18001348f  jmp     loc_1800133BD
0x1800134a0  mov     rcx, [r14+8]
0x1800134a4  test    rcx, rcx
0x1800134a7  jnz     loc_180013553
0x1800134ad  inc     r13d
0x1800134b0  cmp     r13d, [r15+rdi]
0x1800134b4  jnb     loc_180013264
0x1800134ba  jmp     short loc_1800134A0
0x1800134bc  mov     rdi, [rbx+60h]
0x1800134c0  lea     rsi, [rbx+60h]
0x1800134c4  cmp     rdi, rsi
0x1800134c7  jnz     short loc_180013520
0x1800134c9  mov     [rbx+5Ch], r13d
0x1800134cd  mov     [rsi], r13
0x1800134d0  mov     [rbx+68h], r13
0x1800134d4  jmp     loc_180013205
0x1800134d9  xor     ecx, ecx
0x1800134db  mov     [rsp+58h+arg_0], ecx
0x1800134df  cmp     [r13+18h], ecx
0x1800134e3  ja      loc_180013571
0x1800134e9  mov     rcx, [r13+20h]; void *
0x1800134ed  test    rcx, rcx
0x1800134f0  jz      loc_1800132E5
0x1800134f6  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x1800134fb  mov     qword ptr [r13+20h], 0
0x180013503  jmp     loc_1800132E5
0x180013508  call    cs:__imp_LocalFree
0x18001350e  jmp     loc_180013355
0x180013513  call    cs:__imp_LocalFree
0x180013519  jmp     loc_180013315
0x180013520  lea     rcx, [rdi-8]
0x180013524  mov     rdi, [rdi]
0x180013527  test    rcx, rcx
0x18001352a  jnz     short loc_18001359B
0x18001352c  cmp     rdi, rsi
0x18001352f  jz      short loc_1800134C9
0x180013531  jmp     short loc_180013520
0x180013533  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x180013538  jmp     loc_1800133CD
0x18001353d  call    cs:__imp_LocalFree
0x180013543  jmp     loc_1800132DA
0x180013548  call    cs:__imp_LocalFree
0x18001354e  jmp     loc_18001328A
0x180013553  mov     eax, r13d
0x180013556  add     rax, rax
0x180013559  mov     rcx, [rcx+rax*8+8]; void *
0x18001355e  test    rcx, rcx
0x180013561  jz      loc_1800134AD
0x180013567  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18001356c  jmp     loc_1800134AD
0x180013571  mov     rdx, [r13+20h]
0x180013575  test    rdx, rdx
0x180013578  jz      short loc_180013589
0x18001357a  mov     eax, ecx
0x18001357c  add     rax, rax
0x18001357f  mov     r8, [rdx+rax*8+8]
0x180013584  test    r8, r8
0x180013587  jnz     short loc_1800135BB
0x180013589  inc     ecx
0x18001358b  mov     [rsp+58h+arg_0], ecx
0x18001358f  cmp     ecx, [r13+18h]
0x180013593  jnb     loc_1800134E9
0x180013599  jmp     short loc_180013571
0x18001359b  mov     rax, [rcx]
0x18001359e  mov     edx, 1
0x1800135a3  mov     rax, [rax+8]
0x1800135a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135ac  jmp     loc_18001352C
0x1800135b1  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x1800135b6  jmp     loc_180013215
0x1800135bb  mov     rcx, r8; void *
0x1800135be  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x1800135c3  mov     ecx, [rsp+58h+arg_0]
0x1800135c7  jmp     short loc_180013589
0x1800135c9  call    cs:__imp_LocalFree
0x1800135cf  jmp     loc_180013378
0x1800135d4  mov     rax, [rcx]
0x1800135d7  mov     edx, 1
0x1800135dc  mov     rax, [rax+8]
0x1800135e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135e5  jmp     loc_180013388
0x1800135ea  mov     rcx, [rdi+28h]; pCtlContext
0x1800135ee  test    rcx, rcx
0x1800135f1  jz      loc_18008ACEA
0x1800135f7  call    cs:__imp_CertFreeCTLContext
0x1800135fd  nop
0x1800135fe  jmp     loc_18008ACEA
0x180013603  lea     r8, [rbx+348h]; void **
0x18001360a  cmp     qword ptr [r8], 0
0x18001360e  jz      loc_18008ACF8
0x180013614  call    ?UnsubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAXPEAXPEAPEAX@Z; CCredentialGroup::UnsubscribeCertStoreChangeNotification(void *,void * *)
0x180013619  nop
0x18001361a  jmp     loc_18008ACF8
0x18001361f  mov     rcx, [rbx+330h]; void *
0x180013626  lea     rdx, [rsp+58h+arg_8]; int *
0x18001362b  call    ?SslImpersonateClient@@YAKPEAXPEAH@Z; SslImpersonateClient(void *,int *)
0x180013630  test    eax, eax
0x180013632  jnz     loc_18008AD0D
0x180013638  lea     r8, [rbx+358h]; void **
0x18001363f  cmp     qword ptr [r8], 0
0x180013643  jz      loc_18008AD0D
0x180013649  mov     rdx, [rbx+350h]; void *
0x180013650  call    ?UnsubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAXPEAXPEAPEAX@Z; CCredentialGroup::UnsubscribeCertStoreChangeNotification(void *,void * *)
0x180013655  nop
0x180013656  jmp     loc_18008AD0D
0x18001365b  call    cs:__imp_?CryptObjectLocatorFree@@YAXPEAX@Z; CryptObjectLocatorFree(void *)
0x180013661  jmp     loc_1800133EB
0x180013666  call    cs:__imp_?CryptObjectLocatorFree@@YAXPEAX@Z; CryptObjectLocatorFree(void *)
0x18001366c  jmp     loc_1800133FB
0x180013671  lea     r8, [rbx+378h]; void **
0x180013678  cmp     qword ptr [r8], 0
0x18001367c  jz      loc_18008AD33
0x180013682  call    ?UnsubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAXPEAXPEAPEAX@Z; CCredentialGroup::UnsubscribeCertStoreChangeNotification(void *,void * *)
0x180013687  nop
0x180013688  jmp     loc_18008AD33
0x18001368d  lea     r8, [rbx+388h]; void **
0x180013694  cmp     qword ptr [r8], 0
0x180013698  jz      loc_18008AD48
0x18001369e  call    ?UnsubscribeCertStoreChangeNotification@CCredentialGroup@@AEAAXPEAXPEAPEAX@Z; CCredentialGroup::UnsubscribeCertStoreChangeNotification(void *,void * *)
0x1800136a3  nop
0x1800136a4  jmp     loc_18008AD48
0x1800136a9  mov     r9, [rbx+330h]
0x1800136b0  lea     r8, WPP_4353d526375b3dcf7f004b46f692ad9d_Traceguids
0x1800136b7  mov     rcx, [rcx+10h]
0x1800136bb  mov     edx, 18h
0x1800136c0  call    WPP_SF_q
0x1800136c5  jmp     loc_18001344A
0x1800136ca  call    cs:__imp_LocalFree
0x1800136d0  jmp     loc_180013461
0x18008acea  mov     rcx, rdi; void *
0x18008aced  call    ?SPExternalFree@@YAXPEAX@Z; SPExternalFree(void *)
0x18008acf2  nop
0x18008acf3  jmp     loc_180013398
0x18008acf8  mov     rcx, [rbx+340h]; hCertStore
0x18008acff  xor     edx, edx; dwFlags
0x18008ad01  call    cs:__imp_CertCloseStore
0x18008ad07  nop
0x18008ad08  jmp     loc_1800133AD
0x18008ad0d  mov     rcx, [rbx+350h]; hCertStore
0x18008ad14  xor     edx, edx; dwFlags
0x18008ad16  call    cs:__imp_CertCloseStore
0x18008ad1c  cmp     [rsp+58h+arg_8], 0
0x18008ad21  jz      loc_1800133DB
0x18008ad27  call    cs:__imp_RevertToSelf
0x18008ad2d  nop
0x18008ad2e  jmp     loc_1800133DB
  ... truncated ...
```

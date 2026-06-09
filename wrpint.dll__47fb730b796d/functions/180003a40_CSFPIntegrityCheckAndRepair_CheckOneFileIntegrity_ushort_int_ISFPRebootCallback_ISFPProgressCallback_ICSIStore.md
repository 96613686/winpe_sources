# CSFPIntegrityCheckAndRepair::CheckOneFileIntegrity(ushort *,int,ISFPRebootCallback *,ISFPProgressCallback *,ICSIStore2 *,IStore2 *,ushort *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x180003a40`
- end: `0x180003de6`
- name: `?CheckOneFileIntegrity@CSFPIntegrityCheckAndRepair@@EEAAJPEAGHPEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAUICSIStore2@@PEAUIStore2@@0PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAK@Z`
- size: `934`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this, unsigned __int16 *, int, struct ISFPRebootCallback *, struct ISFPProgressCallback *, struct ICSIStore2 *, struct IStore2 *, unsigned __int16 *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800029a4`
- `0x180003a40`
- `0x18000423c`
- `0x1800043ac`
- `0x180004bfc`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckOneFileIntegrity(
        CSFPIntegrityCheckAndRepair *this,
        unsigned __int16 *a2,
        int a3,
        struct ISFPRebootCallback *a4,
        struct ISFPProgressCallback *a5,
        struct ICSIStore2 *a6,
        struct IStore2 *a7,
        unsigned __int16 *a8,
        int *a9,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a10,
        unsigned int *a11)
{
  int IsBootRecovery; // ebx
  int v14; // eax
  int v15; // r14d
  struct IDefinitionIdentity *v16; // rcx
  int v17; // esi
  int v18; // eax
  int v20; // [rsp+30h] [rbp-89h] BYREF
  struct ISFPRebootCallback *v21; // [rsp+38h] [rbp-81h]
  int *v22; // [rsp+40h] [rbp-79h]
  struct ICSIRepairTransaction *v23; // [rsp+48h] [rbp-71h] BYREF
  __int64 v24; // [rsp+50h] [rbp-69h] BYREF
  __int64 v25; // [rsp+58h] [rbp-61h] BYREF
  __int64 v26; // [rsp+60h] [rbp-59h] BYREF
  struct IDefinitionIdentity *v27; // [rsp+68h] [rbp-51h] BYREF
  __int64 v28; // [rsp+70h] [rbp-49h] BYREF
  struct IDefinitionIdentity *v29[2]; // [rsp+78h] [rbp-41h]
  __int64 v30; // [rsp+88h] [rbp-31h] BYREF
  __int128 v31; // [rsp+90h] [rbp-29h]
  unsigned int v32; // [rsp+A0h] [rbp-19h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v34; // [rsp+B0h] [rbp-9h] BYREF

  v23 = 0;
  v25 = 0;
  v24 = 0;
  v30 = 0;
  v34 = 0;
  v26 = 0;
  v28 = 0;
  v33 = 0;
  v27 = 0;
  v32 = 0;
  v20 = 0;
  v22 = a9;
  v21 = a4;
  v31 = 0;
  *a11 = 1;
  *(_OWORD *)v29 = 0;
  IsBootRecovery = BeginRepairTransaction(a6, 6, 1, &v23, &v32);
  if ( IsBootRecovery >= 0 )
  {
    if ( (int)GetComponentIDFromFilename(a8, a2, &v27) < 0 )
    {
      IsBootRecovery = -2147024894;
      goto LABEL_35;
    }
    v14 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, struct IDefinitionIdentity *, unsigned int *))(*(_QWORD *)v23 + 24LL))(
            v23,
            1,
            v27,
            &v32);
    IsBootRecovery = v14;
    if ( v32 == 2 )
      *a11 = 2;
    if ( v14 >= 0 )
    {
      IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, __int64 *))(*(_QWORD *)v23 + 32LL))(
                         v23,
                         0,
                         &v26);
      if ( IsBootRecovery >= 0 )
      {
        IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v26 + 24LL))(
                           v26,
                           1,
                           &v28,
                           &v33);
        if ( !IsBootRecovery )
        {
          if ( v33 )
          {
            v15 = v28;
            if ( !(_DWORD)v28 )
              goto LABEL_33;
            v16 = v29[0];
            ++*(_DWORD *)a10;
            IsBootRecovery = ComponentIsBootRecovery(v16, a7, &v20);
            if ( IsBootRecovery < 0 )
              goto LABEL_35;
            v17 = v20;
            if ( v20 )
              ++*((_DWORD *)a10 + 2);
            if ( !a3 )
            {
LABEL_33:
              if ( v29[0] )
              {
                (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
                v29[0] = 0;
              }
              goto LABEL_35;
            }
            v18 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, struct IDefinitionIdentity *, unsigned int *))(*(_QWORD *)v23 + 40LL))(
                    v23,
                    1,
                    v29[0],
                    &v32);
            IsBootRecovery = v18;
            if ( v32 == 2 )
              *a11 = 2;
            if ( v18 >= 0 )
            {
              IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v23 + 48LL))(
                                 v23,
                                 0,
                                 &v25,
                                 0);
              if ( IsBootRecovery >= 0 )
              {
                IsBootRecovery = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 24LL))(
                                   v25,
                                   0,
                                   &v24);
                if ( IsBootRecovery >= 0 )
                {
                  IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v24 + 24LL))(
                                     v24,
                                     1,
                                     &v30,
                                     &v34);
                  if ( !IsBootRecovery && v34 )
                  {
                    if ( (_DWORD)v30 )
                    {
                      IsBootRecovery = CommitWrapper(v23, v22, v21);
                      if ( IsBootRecovery < 0 )
                        goto LABEL_35;
                      if ( (_DWORD)v30 == v15 )
                      {
                        ++*((_DWORD *)a10 + 1);
                        if ( v17 )
                        {
                          ++*((_DWORD *)a10 + 3);
                          --*((_DWORD *)a10 + 2);
                        }
                      }
                    }
                    if ( (_QWORD)v31 )
                    {
                      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31 + 16LL))(v31);
                      *(_QWORD *)&v31 = 0;
                    }
                  }
                  if ( v25 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                    v25 = 0;
                  }
                  if ( v24 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
                    v24 = 0;
                  }
                  goto LABEL_33;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_35:
  if ( v23 )
    (*(void (__fastcall **)(struct ICSIRepairTransaction *))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v27 )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v29[0] )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v29[0] + 16LL))(v29[0]);
  if ( (_QWORD)v31 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31 + 16LL))(v31);
  return (unsigned int)IsBootRecovery;
}

```

## disassembly

```asm
0x180003a40  mov     [rsp-8+arg_0], rbx
0x180003a45  push    rbp
0x180003a46  push    rsi
0x180003a47  push    rdi
0x180003a48  push    r12
0x180003a4a  push    r13
0x180003a4c  push    r14
0x180003a4e  push    r15
0x180003a50  lea     rbp, [rsp-7]
0x180003a55  sub     rsp, 0C0h
0x180003a5c  mov     rax, cs:__security_cookie
0x180003a63  xor     rax, rsp
0x180003a66  mov     [rbp+37h+var_38], rax
0x180003a6a  mov     rax, [rbp+37h+arg_40]
0x180003a71  mov     rsi, rdx
0x180003a74  mov     r15, [rbp+37h+arg_50]
0x180003a7b  xor     edx, edx
0x180003a7d  mov     rcx, [rbp+37h+arg_28]; struct ICSIStore2 *
0x180003a81  xorps   xmm0, xmm0
0x180003a84  mov     rdi, [rbp+37h+arg_48]
0x180003a8b  mov     r12d, r8d
0x180003a8e  mov     r13, [rbp+37h+arg_30]
0x180003a92  mov     r14, [rbp+37h+arg_38]
0x180003a96  mov     [rbp+37h+var_A8], rdx
0x180003a9a  mov     [rbp+37h+var_98], rdx
0x180003a9e  mov     [rbp+37h+var_A0], rdx
0x180003aa2  mov     [rbp+37h+var_68], rdx
0x180003aa6  mov     [rbp+37h+var_40], rdx
0x180003aaa  mov     [rbp+37h+var_90], rdx
0x180003aae  mov     [rbp+37h+var_80], rdx
0x180003ab2  mov     [rbp+37h+var_48], rdx
0x180003ab6  mov     [rbp+37h+var_88], rdx
0x180003aba  mov     [rbp+37h+var_50], edx
0x180003abd  mov     [rsp+0F0h+var_C0], edx
0x180003ac1  mov     edx, 6; unsigned int
0x180003ac6  mov     [rbp+37h+var_B0], rax
0x180003aca  lea     rax, [rbp+37h+var_50]
0x180003ace  mov     [rsp+0F0h+var_B8], r9
0x180003ad3  lea     r9, [rbp+37h+var_A8]; struct ICSIRepairTransaction **
0x180003ad7  movdqu  [rbp+37h+var_60], xmm0
0x180003adc  lea     r8d, [rdx-5]; int
0x180003ae0  mov     dword ptr [r15], 1
0x180003ae7  movdqu  xmmword ptr [rbp+37h+var_78], xmm0
0x180003aec  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180003af1  call    ?BeginRepairTransaction@@YAJPEAUICSIStore2@@KHPEAPEAUICSIRepairTransaction@@PEAK@Z; BeginRepairTransaction(ICSIStore2 *,ulong,int,ICSIRepairTransaction * *,ulong *)
0x180003af6  mov     ebx, eax
0x180003af8  test    eax, eax
0x180003afa  js      loc_180003D2A
0x180003b00  lea     r8, [rbp+37h+var_88]; struct IDefinitionIdentity **
0x180003b04  mov     rdx, rsi; unsigned __int16 *
0x180003b07  mov     rcx, r14; unsigned __int16 *
0x180003b0a  call    ?GetComponentIDFromFilename@@YAJPEBGPEAGPEAPEAUIDefinitionIdentity@@@Z; GetComponentIDFromFilename(ushort const *,ushort *,IDefinitionIdentity * *)
0x180003b0f  test    eax, eax
0x180003b11  jns     short loc_180003B1D
0x180003b13  mov     ebx, 80070002h
0x180003b18  jmp     loc_180003D2A
0x180003b1d  mov     rcx, [rbp+37h+var_A8]
0x180003b21  lea     r9, [rbp+37h+var_50]
0x180003b25  mov     r8, [rbp+37h+var_88]
0x180003b29  mov     esi, 1
0x180003b2e  mov     edx, esi
0x180003b30  mov     rax, [rcx]
0x180003b33  mov     rax, [rax+18h]
0x180003b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b3c  cmp     [rbp+37h+var_50], 2
0x180003b40  mov     ebx, eax
0x180003b42  jnz     short loc_180003B4B
0x180003b44  mov     dword ptr [r15], 2
0x180003b4b  test    eax, eax
0x180003b4d  js      loc_180003D2A
0x180003b53  mov     rcx, [rbp+37h+var_A8]
0x180003b57  lea     r8, [rbp+37h+var_90]
0x180003b5b  xor     edx, edx
0x180003b5d  mov     rax, [rcx]
0x180003b60  mov     rax, [rax+20h]
0x180003b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b69  mov     ebx, eax
0x180003b6b  test    eax, eax
0x180003b6d  js      loc_180003D2A
0x180003b73  mov     rcx, [rbp+37h+var_90]
0x180003b77  lea     r9, [rbp+37h+var_48]
0x180003b7b  lea     r8, [rbp+37h+var_80]
0x180003b7f  mov     rdx, rsi
0x180003b82  mov     rax, [rcx]
0x180003b85  mov     rax, [rax+18h]
0x180003b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b8e  mov     ebx, eax
0x180003b90  test    eax, eax
0x180003b92  jnz     loc_180003D2A
0x180003b98  cmp     [rbp+37h+var_48], 0
0x180003b9d  jbe     loc_180003D2A
0x180003ba3  mov     r14d, dword ptr [rbp+37h+var_80]
0x180003ba7  test    r14d, r14d
0x180003baa  jz      loc_180003D0D
0x180003bb0  mov     rcx, [rbp+37h+var_78]; struct IDefinitionIdentity *
0x180003bb4  lea     r8, [rsp+0F0h+var_C0]; int *
0x180003bb9  add     [rdi], esi
0x180003bbb  mov     rdx, r13; struct IStore2 *
0x180003bbe  call    ?ComponentIsBootRecovery@@YAJPEAUIDefinitionIdentity@@PEAUIStore2@@PEAH@Z; ComponentIsBootRecovery(IDefinitionIdentity *,IStore2 *,int *)
0x180003bc3  mov     ebx, eax
0x180003bc5  test    eax, eax
0x180003bc7  js      loc_180003D2A
0x180003bcd  mov     esi, [rsp+0F0h+var_C0]
0x180003bd1  test    esi, esi
0x180003bd3  jz      short loc_180003BD8
0x180003bd5  inc     dword ptr [rdi+8]
0x180003bd8  test    r12d, r12d
0x180003bdb  jz      loc_180003D0D
0x180003be1  mov     rcx, [rbp+37h+var_A8]
0x180003be5  lea     r9, [rbp+37h+var_50]
0x180003be9  mov     r8, [rbp+37h+var_78]
0x180003bed  mov     edx, 1
0x180003bf2  mov     rax, [rcx]
0x180003bf5  mov     rax, [rax+28h]
0x180003bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bfe  cmp     [rbp+37h+var_50], 2
0x180003c02  mov     ebx, eax
0x180003c04  jnz     short loc_180003C0D
0x180003c06  mov     dword ptr [r15], 2
0x180003c0d  test    eax, eax
0x180003c0f  js      loc_180003D2A
0x180003c15  mov     rcx, [rbp+37h+var_A8]
0x180003c19  lea     r8, [rbp+37h+var_98]
0x180003c1d  xor     r9d, r9d
0x180003c20  xor     edx, edx
0x180003c22  mov     rax, [rcx]
0x180003c25  mov     rax, [rax+30h]
0x180003c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c2e  mov     ebx, eax
0x180003c30  test    eax, eax
0x180003c32  js      loc_180003D2A
0x180003c38  mov     rcx, [rbp+37h+var_98]
0x180003c3c  lea     r8, [rbp+37h+var_A0]
0x180003c40  xor     edx, edx
0x180003c42  mov     rax, [rcx]
0x180003c45  mov     rax, [rax+18h]
0x180003c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c4e  mov     ebx, eax
0x180003c50  test    eax, eax
0x180003c52  js      loc_180003D2A
0x180003c58  mov     rcx, [rbp+37h+var_A0]
0x180003c5c  lea     r9, [rbp+37h+var_40]
0x180003c60  lea     r8, [rbp+37h+var_68]
0x180003c64  mov     edx, 1
0x180003c69  mov     rax, [rcx]
0x180003c6c  mov     rax, [rax+18h]
0x180003c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c75  mov     ebx, eax
0x180003c77  test    eax, eax
0x180003c79  jnz     short loc_180003CD3
0x180003c7b  cmp     [rbp+37h+var_40], 0
0x180003c80  jbe     short loc_180003CD3
0x180003c82  cmp     dword ptr [rbp+37h+var_68], eax
0x180003c85  jz      short loc_180003CB6
0x180003c87  mov     r8, [rsp+0F0h+var_B8]; struct ISFPRebootCallback *
0x180003c8c  mov     rdx, [rbp+37h+var_B0]; int *
0x180003c90  mov     rcx, [rbp+37h+var_A8]; struct ICSIRepairTransaction *
0x180003c94  call    ?CommitWrapper@@YAJPEAUICSIRepairTransaction@@PEAHPEAUISFPRebootCallback@@@Z; CommitWrapper(ICSIRepairTransaction *,int *,ISFPRebootCallback *)
0x180003c99  mov     ebx, eax
0x180003c9b  test    eax, eax
0x180003c9d  js      loc_180003D2A
0x180003ca3  cmp     dword ptr [rbp+37h+var_68], r14d
0x180003ca7  jnz     short loc_180003CB6
0x180003ca9  inc     dword ptr [rdi+4]
0x180003cac  test    esi, esi
0x180003cae  jz      short loc_180003CB6
0x180003cb0  inc     dword ptr [rdi+0Ch]
0x180003cb3  dec     dword ptr [rdi+8]
0x180003cb6  mov     rcx, qword ptr [rbp+37h+var_60]
0x180003cba  test    rcx, rcx
0x180003cbd  jz      short loc_180003CD3
0x180003cbf  mov     rax, [rcx]
0x180003cc2  mov     rax, [rax+10h]
0x180003cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ccb  mov     qword ptr [rbp+37h+var_60], 0
0x180003cd3  mov     rcx, [rbp+37h+var_98]
0x180003cd7  test    rcx, rcx
0x180003cda  jz      short loc_180003CF0
0x180003cdc  mov     rax, [rcx]
0x180003cdf  mov     rax, [rax+10h]
0x180003ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce8  mov     [rbp+37h+var_98], 0
0x180003cf0  mov     rcx, [rbp+37h+var_A0]
0x180003cf4  test    rcx, rcx
0x180003cf7  jz      short loc_180003D0D
0x180003cf9  mov     rax, [rcx]
0x180003cfc  mov     rax, [rax+10h]
0x180003d00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d05  mov     [rbp+37h+var_A0], 0
0x180003d0d  mov     rcx, [rbp+37h+var_78]
0x180003d11  test    rcx, rcx
0x180003d14  jz      short loc_180003D2A
0x180003d16  mov     rax, [rcx]
0x180003d19  mov     rax, [rax+10h]
0x180003d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d22  mov     [rbp+37h+var_78], 0
0x180003d2a  mov     rcx, [rbp+37h+var_A8]
0x180003d2e  test    rcx, rcx
0x180003d31  jz      short loc_180003D3F
0x180003d33  mov     rax, [rcx]
0x180003d36  mov     rax, [rax+10h]
0x180003d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d3f  mov     rcx, [rbp+37h+var_90]
0x180003d43  test    rcx, rcx
0x180003d46  jz      short loc_180003D54
0x180003d48  mov     rax, [rcx]
0x180003d4b  mov     rax, [rax+10h]
0x180003d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d54  mov     rcx, [rbp+37h+var_A0]
0x180003d58  test    rcx, rcx
0x180003d5b  jz      short loc_180003D69
0x180003d5d  mov     rax, [rcx]
0x180003d60  mov     rax, [rax+10h]
0x180003d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d69  mov     rcx, [rbp+37h+var_98]
0x180003d6d  test    rcx, rcx
0x180003d70  jz      short loc_180003D7E
0x180003d72  mov     rax, [rcx]
0x180003d75  mov     rax, [rax+10h]
0x180003d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d7e  mov     rcx, [rbp+37h+var_88]
0x180003d82  test    rcx, rcx
0x180003d85  jz      short loc_180003D93
0x180003d87  mov     rax, [rcx]
0x180003d8a  mov     rax, [rax+10h]
0x180003d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d93  mov     rcx, [rbp+37h+var_78]
0x180003d97  test    rcx, rcx
0x180003d9a  jz      short loc_180003DA8
0x180003d9c  mov     rax, [rcx]
0x180003d9f  mov     rax, [rax+10h]
0x180003da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003da8  mov     rcx, qword ptr [rbp+37h+var_60]
0x180003dac  test    rcx, rcx
0x180003daf  jz      short loc_180003DBD
0x180003db1  mov     rax, [rcx]
0x180003db4  mov     rax, [rax+10h]
0x180003db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbd  mov     eax, ebx
0x180003dbf  mov     rcx, [rbp+37h+var_38]
0x180003dc3  xor     rcx, rsp; StackCookie
0x180003dc6  call    __security_check_cookie
0x180003dcb  mov     rbx, [rsp+0F0h+arg_0]
0x180003dd3  add     rsp, 0C0h
0x180003dda  pop     r15
0x180003ddc  pop     r14
0x180003dde  pop     r13
0x180003de0  pop     r12
0x180003de2  pop     rdi
0x180003de3  pop     rsi
0x180003de4  pop     rbp
0x180003de5  retn
```

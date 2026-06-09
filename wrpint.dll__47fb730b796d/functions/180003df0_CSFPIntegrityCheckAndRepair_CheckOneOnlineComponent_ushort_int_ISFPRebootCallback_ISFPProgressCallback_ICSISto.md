# CSFPIntegrityCheckAndRepair::CheckOneOnlineComponent(ushort *,int,ISFPRebootCallback *,ISFPProgressCallback *,ICSIStore2 *,IStore2 *,_CSI_COMPONENT,unsigned __int64,ICSIRepairTransaction *,ICSIRepairTransaction * *,ulong,ulong *,int *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x180003df0`
- end: `0x180004127`
- name: `?CheckOneOnlineComponent@CSFPIntegrityCheckAndRepair@@EEAAJPEAGHPEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAUICSIStore2@@PEAUIStore2@@U_CSI_COMPONENT@@_KPEAUICSIRepairTransaction@@PEAPEAU7@KPEAKPEAHPEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@9@Z`
- size: `823`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64, __int64 *, struct IStore2 *, __int64, __int64, __int64, _QWORD *, __int64, _DWORD *, _DWORD *, __int64, _DWORD *, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003df0`
- `0x1800043ac`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckOneOnlineComponent(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        struct IStore2 *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        _QWORD *a11,
        __int64 a12,
        _DWORD *a13,
        _DWORD *a14,
        __int64 a15,
        _DWORD *a16,
        _DWORD *a17)
{
  int IsBootRecovery; // ebx
  int v18; // eax
  int v19; // esi
  struct IStore2 *v20; // rdx
  struct IDefinitionIdentity *v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  int v26; // [rsp+40h] [rbp-71h] BYREF
  int v27; // [rsp+44h] [rbp-6Dh]
  struct IStore2 *v28; // [rsp+48h] [rbp-69h]
  __int64 v29; // [rsp+50h] [rbp-61h]
  __int64 *v30; // [rsp+58h] [rbp-59h]
  __int64 v31; // [rsp+60h] [rbp-51h]
  __int64 v32; // [rsp+68h] [rbp-49h] BYREF
  __int64 v33; // [rsp+70h] [rbp-41h] BYREF
  struct IDefinitionIdentity *v34[2]; // [rsp+78h] [rbp-39h]
  int v35; // [rsp+88h] [rbp-29h] BYREF
  __int64 v36; // [rsp+90h] [rbp-21h] BYREF
  GUID v37; // [rsp+98h] [rbp-19h] BYREF

  IsBootRecovery = 0;
  v31 = a5;
  v30 = a6;
  v28 = a7;
  v27 = a3;
  v29 = a10;
  *(_QWORD *)&v37.Data1 = a17;
  v32 = 0;
  v33 = 0;
  *(_OWORD *)v34 = 0;
  v36 = 0;
  v35 = 0;
  v26 = 0;
  *a17 = 1;
  if ( a9 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(*(_QWORD *)*a11 + 24LL))(
            *a11,
            1,
            *(_QWORD *)(a8 + 8),
            &v35);
    IsBootRecovery = v18;
    if ( v35 == 2 )
      *a17 = 2;
    if ( v18 < 0 )
      goto LABEL_39;
    ++*a13;
    IsBootRecovery = 0;
  }
  else
  {
    *a14 = 1;
  }
  if ( !*a14 && *a13 != 100 * (*a13 / 0x64u) )
  {
LABEL_37:
    v24 = *(_QWORD *)(a8 + 8);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_39;
  }
  IsBootRecovery = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*a11 + 32LL))(*a11, 0, &v32);
  if ( IsBootRecovery >= 0 )
  {
    v19 = 0;
    while ( 1 )
    {
      IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v32 + 24LL))(
                         v32,
                         1,
                         &v33,
                         &v36);
      if ( IsBootRecovery < 0 )
        break;
      if ( !v36 )
        goto LABEL_29;
      if ( (_DWORD)v33 )
      {
        v20 = v28;
        v21 = v34[0];
        ++*a16;
        IsBootRecovery = ComponentIsBootRecovery(v21, v20, &v26);
        if ( IsBootRecovery < 0 )
          break;
        if ( v26 )
          ++a16[2];
        if ( v27 )
        {
          if ( (unsigned int)++v19 > 0x3E8 )
          {
            a16[4] = 1;
          }
          else
          {
            IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, struct IDefinitionIdentity *, int *))(*(_QWORD *)v29 + 40LL))(
                               v29,
                               1,
                               v34[0],
                               &v35);
            if ( v35 == 2 )
              **(_DWORD **)&v37.Data1 = 2;
            if ( IsBootRecovery < 0 )
              break;
          }
        }
      }
      if ( v34[0] )
      {
        (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
        v34[0] = 0;
      }
    }
  }
  else
  {
    ++*a16;
    if ( v27 )
      goto LABEL_39;
LABEL_29:
    if ( v32 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      v32 = 0;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)*a11 + 64LL))(*a11, 0, 0);
    if ( *a11 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a11 + 16LL))(*a11);
      *a11 = 0;
    }
    v22 = *v30;
    v37 = GUID_NULL;
    v23 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *, _QWORD, GUID *, _QWORD *, _QWORD))(v22 + 24))(
            v30,
            0,
            &v37,
            0,
            &GUID_b891714f_67db_4eca_8881_e5932a0f0f94,
            a11,
            0);
    IsBootRecovery = 0;
    if ( v23 < 0 )
      IsBootRecovery = v23;
    if ( IsBootRecovery >= 0 )
    {
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 24LL))(v31, 1);
      IsBootRecovery = 0;
      goto LABEL_37;
    }
  }
LABEL_39:
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v34[0] )
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
  return (unsigned int)IsBootRecovery;
}

```

## disassembly

```asm
0x180003df0  push    rbp
0x180003df2  push    rbx
0x180003df3  push    rsi
0x180003df4  push    rdi
0x180003df5  push    r12
0x180003df7  push    r13
0x180003df9  push    r14
0x180003dfb  push    r15
0x180003dfd  lea     rbp, [rsp-7]
0x180003e02  sub     rsp, 0B8h
0x180003e09  mov     rax, cs:__security_cookie
0x180003e10  xor     rax, rsp
0x180003e13  mov     [rbp+3Fh+var_48], rax
0x180003e17  mov     rax, [rbp+3Fh+arg_20]
0x180003e1b  xor     ebx, ebx
0x180003e1d  xorps   xmm0, xmm0
0x180003e20  mov     r15, [rbp+3Fh+arg_80]
0x180003e27  mov     rcx, [rbp+3Fh+arg_48]
0x180003e2e  mov     rdi, [rbp+3Fh+arg_78]
0x180003e35  mov     r12, [rbp+3Fh+arg_38]
0x180003e3c  mov     r14, [rbp+3Fh+arg_50]
0x180003e43  mov     r13, [rbp+3Fh+arg_60]
0x180003e4a  mov     rsi, [rbp+3Fh+arg_68]
0x180003e51  mov     [rbp+3Fh+var_90], rax
0x180003e55  mov     rax, [rbp+3Fh+arg_28]
0x180003e59  mov     [rbp+3Fh+var_98], rax
0x180003e5d  mov     rax, [rbp+3Fh+arg_30]
0x180003e61  mov     [rbp+3Fh+var_A8], rax
0x180003e65  mov     [rbp+3Fh+var_AC], r8d
0x180003e69  mov     [rbp+3Fh+var_A0], rcx
0x180003e6d  mov     qword ptr [rbp+3Fh+var_58], r15
0x180003e71  mov     [rbp+3Fh+var_88], rbx
0x180003e75  mov     [rbp+3Fh+var_80], rbx
0x180003e79  movdqu  xmmword ptr [rbp+3Fh+var_78], xmm0
0x180003e7e  mov     [rbp+3Fh+var_60], rbx
0x180003e82  mov     [rbp+3Fh+var_68], ebx
0x180003e85  mov     [rbp+3Fh+var_B0], ebx
0x180003e88  mov     dword ptr [r15], 1
0x180003e8f  cmp     [rbp+3Fh+arg_40], rbx
0x180003e96  jz      short loc_180003ED2
0x180003e98  mov     rcx, [r14]
0x180003e9b  lea     r9, [rbp+3Fh+var_68]
0x180003e9f  mov     r8, [r12+8]
0x180003ea4  lea     edx, [rbx+1]
0x180003ea7  mov     rax, [rcx]
0x180003eaa  mov     rax, [rax+18h]
0x180003eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eb3  cmp     [rbp+3Fh+var_68], 2
0x180003eb7  mov     ebx, eax
0x180003eb9  jnz     short loc_180003EC2
0x180003ebb  mov     dword ptr [r15], 2
0x180003ec2  test    eax, eax
0x180003ec4  js      loc_1800040DB
0x180003eca  inc     dword ptr [r13+0]
0x180003ece  xor     ebx, ebx
0x180003ed0  jmp     short loc_180003ED8
0x180003ed2  mov     dword ptr [rsi], 1
0x180003ed8  cmp     [rsi], ebx
0x180003eda  jnz     short loc_180003EF5
0x180003edc  mov     eax, 51EB851Fh
0x180003ee1  mul     dword ptr [r13+0]
0x180003ee5  shr     edx, 5
0x180003ee8  imul    eax, edx, 64h ; 'd'
0x180003eeb  cmp     [r13+0], eax
0x180003eef  jnz     loc_1800040C5
0x180003ef5  mov     rcx, [r14]
0x180003ef8  lea     r8, [rbp+3Fh+var_88]
0x180003efc  xor     edx, edx
0x180003efe  mov     r15d, ebx
0x180003f01  mov     rax, [rcx]
0x180003f04  mov     rax, [rax+20h]
0x180003f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0d  mov     ebx, eax
0x180003f0f  test    eax, eax
0x180003f11  jns     short loc_180003F24
0x180003f13  inc     dword ptr [rdi]
0x180003f15  cmp     [rbp+3Fh+var_AC], 0
0x180003f19  jnz     loc_1800040DB
0x180003f1f  jmp     loc_180003FFA
0x180003f24  xor     esi, esi
0x180003f26  mov     rcx, [rbp+3Fh+var_88]
0x180003f2a  lea     r9, [rbp+3Fh+var_60]
0x180003f2e  lea     r8, [rbp+3Fh+var_80]
0x180003f32  mov     edx, 1
0x180003f37  mov     rax, [rcx]
0x180003f3a  mov     rax, [rax+18h]
0x180003f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f43  mov     ebx, eax
0x180003f45  test    eax, eax
0x180003f47  js      loc_1800040DB
0x180003f4d  cmp     [rbp+3Fh+var_60], 0
0x180003f52  jz      loc_180003FFA
0x180003f58  cmp     dword ptr [rbp+3Fh+var_80], 0
0x180003f5c  jz      short loc_180003FD4
0x180003f5e  mov     rdx, [rbp+3Fh+var_A8]; struct IStore2 *
0x180003f62  lea     r8, [rbp+3Fh+var_B0]; int *
0x180003f66  mov     rcx, [rbp+3Fh+var_78]; struct IDefinitionIdentity *
0x180003f6a  inc     dword ptr [rdi]
0x180003f6c  call    ?ComponentIsBootRecovery@@YAJPEAUIDefinitionIdentity@@PEAUIStore2@@PEAH@Z; ComponentIsBootRecovery(IDefinitionIdentity *,IStore2 *,int *)
0x180003f71  mov     ebx, eax
0x180003f73  test    eax, eax
0x180003f75  js      loc_1800040DB
0x180003f7b  cmp     [rbp+3Fh+var_B0], 0
0x180003f7f  jz      short loc_180003F84
0x180003f81  inc     dword ptr [rdi+8]
0x180003f84  cmp     [rbp+3Fh+var_AC], 0
0x180003f88  jz      short loc_180003FD4
0x180003f8a  inc     esi
0x180003f8c  cmp     esi, 3E8h
0x180003f92  ja      short loc_180003FCD
0x180003f94  mov     rcx, [rbp+3Fh+var_A0]
0x180003f98  lea     r9, [rbp+3Fh+var_68]
0x180003f9c  mov     r8, [rbp+3Fh+var_78]
0x180003fa0  mov     edx, 1
0x180003fa5  mov     rax, [rcx]
0x180003fa8  mov     rax, [rax+28h]
0x180003fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb1  cmp     [rbp+3Fh+var_68], 2
0x180003fb5  mov     ebx, eax
0x180003fb7  jnz     short loc_180003FC3
0x180003fb9  mov     rax, qword ptr [rbp+3Fh+var_58]
0x180003fbd  mov     dword ptr [rax], 2
0x180003fc3  test    ebx, ebx
0x180003fc5  js      loc_1800040DB
0x180003fcb  jmp     short loc_180003FD4
0x180003fcd  mov     dword ptr [rdi+10h], 1
0x180003fd4  mov     rcx, [rbp+3Fh+var_78]
0x180003fd8  test    rcx, rcx
0x180003fdb  jz      short loc_180003FF1
0x180003fdd  mov     rax, [rcx]
0x180003fe0  mov     rax, [rax+10h]
0x180003fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fe9  mov     [rbp+3Fh+var_78], 0
0x180003ff1  test    r15d, r15d
0x180003ff4  jz      loc_180003F26
0x180003ffa  mov     rcx, [rbp+3Fh+var_88]
0x180003ffe  test    rcx, rcx
0x180004001  jz      short loc_180004017
0x180004003  mov     rax, [rcx]
0x180004006  mov     rax, [rax+10h]
0x18000400a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000400f  mov     [rbp+3Fh+var_88], 0
0x180004017  mov     rcx, [r14]
0x18000401a  xor     r8d, r8d
0x18000401d  xor     edx, edx
0x18000401f  mov     rax, [rcx]
0x180004022  mov     rax, [rax+40h]
0x180004026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000402b  mov     rcx, [r14]
0x18000402e  test    rcx, rcx
0x180004031  jz      short loc_180004046
0x180004033  mov     rax, [rcx]
0x180004036  mov     rax, [rax+10h]
0x18000403a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403f  mov     qword ptr [r14], 0
0x180004046  mov     rcx, [rbp+3Fh+var_98]
0x18000404a  lea     rdx, _GUID_b891714f_67db_4eca_8881_e5932a0f0f94
0x180004051  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180004058  mov     [rsp+0F0h+var_C0], 0
0x180004061  lea     r8, [rbp+3Fh+var_58]
0x180004065  mov     [rsp+0F0h+var_C8], r14
0x18000406a  xor     r9d, r9d
0x18000406d  mov     rax, [rcx]
0x180004070  mov     [rsp+0F0h+var_D0], rdx
0x180004075  xor     edx, edx
0x180004077  movdqu  [rbp+3Fh+var_58], xmm0
0x18000407c  mov     rax, [rax+18h]
0x180004080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004085  xor     ebx, ebx
0x180004087  test    eax, eax
0x180004089  cmovs   ebx, eax
0x18000408c  test    ebx, ebx
0x18000408e  js      short loc_1800040DB
0x180004090  mov     eax, [r13+0]
0x180004094  xorps   xmm2, xmm2
0x180004097  mov     rcx, [rbp+3Fh+var_90]
0x18000409b  xorps   xmm0, xmm0
0x18000409e  mov     edx, 1
0x1800040a3  cvtsi2sd xmm2, rax
0x1800040a8  mov     eax, [rbp+3Fh+arg_58]
0x1800040ae  mov     r8, [rcx]
0x1800040b1  cvtsi2sd xmm0, rax
0x1800040b6  mov     rax, [r8+18h]
0x1800040ba  divsd   xmm2, xmm0
0x1800040be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040c3  xor     ebx, ebx
0x1800040c5  mov     rcx, [r12+8]
0x1800040ca  test    rcx, rcx
0x1800040cd  jz      short loc_1800040DB
0x1800040cf  mov     rax, [rcx]
0x1800040d2  mov     rax, [rax+10h]
0x1800040d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040db  mov     rcx, [rbp+3Fh+var_88]
0x1800040df  test    rcx, rcx
0x1800040e2  jz      short loc_1800040F0
0x1800040e4  mov     rax, [rcx]
0x1800040e7  mov     rax, [rax+10h]
0x1800040eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f0  mov     rcx, [rbp+3Fh+var_78]
0x1800040f4  test    rcx, rcx
0x1800040f7  jz      short loc_180004105
0x1800040f9  mov     rax, [rcx]
0x1800040fc  mov     rax, [rax+10h]
0x180004100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004105  mov     eax, ebx
0x180004107  mov     rcx, [rbp+3Fh+var_48]
0x18000410b  xor     rcx, rsp; StackCookie
0x18000410e  call    __security_check_cookie
0x180004113  add     rsp, 0B8h
0x18000411a  pop     r15
0x18000411c  pop     r14
0x18000411e  pop     r13
0x180004120  pop     r12
0x180004122  pop     rdi
0x180004123  pop     rsi
0x180004124  pop     rbx
0x180004125  pop     rbp
0x180004126  retn
```

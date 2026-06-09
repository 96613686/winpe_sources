# CSFPIntegrityCheckAndRepair::CheckCSIIntegrityOffline(ushort *,int,ISFPRebootCallback *,ISFPProgressCallback *,ICSIStore2 *,IStore2 *,ICSIInventory *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ulong *)

- ea: `0x180002d00`
- end: `0x1800031b6`
- name: `?CheckCSIIntegrityOffline@CSFPIntegrityCheckAndRepair@@EEAAJPEAGHPEAUISFPRebootCallback@@PEAUISFPProgressCallback@@PEAUICSIStore2@@PEAUIStore2@@PEAUICSIInventory@@PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAK@Z`
- size: `1206`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *__hidden this, unsigned __int16 *, int, struct ISFPRebootCallback *, struct ISFPProgressCallback *, struct ICSIStore2 *, struct IStore2 *, struct ICSIInventory *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800029a4`
- `0x180002d00`
- `0x18000423c`
- `0x1800043ac`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::CheckCSIIntegrityOffline(
        CSFPIntegrityCheckAndRepair *this,
        unsigned __int16 *a2,
        int a3,
        struct ISFPRebootCallback *a4,
        struct ISFPProgressCallback *a5,
        struct ICSIStore2 *a6,
        struct IStore2 *a7,
        struct ICSIInventory *a8,
        int *a9,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a10,
        unsigned int *a11)
{
  struct ICSIStore2 *v12; // rsi
  __int64 v13; // rax
  __int64 (__fastcall *v14)(struct ICSIInventory *, __int64, __int64 *); // rax
  int IsBootRecovery; // ebx
  int v16; // eax
  int v17; // r14d
  struct IDefinitionIdentity *v18; // rcx
  int v19; // esi
  int v20; // eax
  int v22; // [rsp+30h] [rbp-B1h] BYREF
  struct ICSIStore2 *v23; // [rsp+38h] [rbp-A9h]
  struct ISFPRebootCallback *v24; // [rsp+40h] [rbp-A1h]
  int *v25; // [rsp+48h] [rbp-99h]
  struct ICSIRepairTransaction *v26; // [rsp+50h] [rbp-91h] BYREF
  __int64 v27; // [rsp+58h] [rbp-89h] BYREF
  __int64 v28; // [rsp+60h] [rbp-81h] BYREF
  __int64 v29; // [rsp+68h] [rbp-79h] BYREF
  __int64 v30; // [rsp+70h] [rbp-71h] BYREF
  __int64 v31; // [rsp+78h] [rbp-69h]
  __int64 v32; // [rsp+80h] [rbp-61h] BYREF
  __int64 v33; // [rsp+88h] [rbp-59h] BYREF
  struct IDefinitionIdentity *v34[2]; // [rsp+90h] [rbp-51h]
  __int64 v35; // [rsp+A0h] [rbp-41h] BYREF
  __int128 v36; // [rsp+A8h] [rbp-39h]
  unsigned int v37; // [rsp+B8h] [rbp-29h] BYREF
  __int64 v38; // [rsp+C0h] [rbp-21h] BYREF
  __int64 v39; // [rsp+C8h] [rbp-19h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-11h] BYREF

  v12 = a6;
  v25 = a9;
  *a11 = 1;
  v13 = *(_QWORD *)a8;
  v24 = a4;
  v23 = a6;
  v26 = 0;
  v14 = *(__int64 (__fastcall **)(struct ICSIInventory *, __int64, __int64 *))(v13 + 24);
  v29 = 0;
  v28 = 0;
  v35 = 0;
  v36 = 0;
  v40 = 0;
  v27 = 0;
  v33 = 0;
  *(_OWORD *)v34 = 0;
  v39 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  v38 = 0;
  v22 = 0;
  v37 = 0;
  IsBootRecovery = v14(a8, 4, &v32);
  if ( IsBootRecovery >= 0 )
  {
    while ( 1 )
    {
      IsBootRecovery = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v32 + 24LL))(
                         v32,
                         1,
                         &v30,
                         &v38);
      if ( IsBootRecovery )
        break;
      if ( !v38 )
        break;
      IsBootRecovery = BeginRepairTransaction(v12, (unsigned int)(IsBootRecovery + 6), IsBootRecovery + 1, &v26, &v37);
      if ( IsBootRecovery < 0 )
        break;
      v16 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, __int64, unsigned int *))(*(_QWORD *)v26 + 24LL))(
              v26,
              1,
              v31,
              &v37);
      IsBootRecovery = v16;
      if ( v37 == 2 )
        *a11 = 2;
      if ( v16 < 0 )
        break;
      IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, __int64 *))(*(_QWORD *)v26 + 32LL))(
                         v26,
                         0,
                         &v27);
      if ( IsBootRecovery < 0 )
        break;
      if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v27 + 24LL))(
              v27,
              1,
              &v33,
              &v39)
        && v39 )
      {
        v17 = v33;
        if ( (_DWORD)v33 )
        {
          v18 = v34[0];
          ++*(_DWORD *)a10;
          IsBootRecovery = ComponentIsBootRecovery(v18, a7, &v22);
          if ( IsBootRecovery < 0 )
            break;
          v19 = v22;
          if ( v22 )
            ++*((_DWORD *)a10 + 2);
          if ( a3 )
          {
            v20 = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, __int64, struct IDefinitionIdentity *, unsigned int *))(*(_QWORD *)v26 + 40LL))(
                    v26,
                    1,
                    v34[0],
                    &v37);
            IsBootRecovery = v20;
            if ( v37 == 2 )
              *a11 = 2;
            if ( v20 < 0 )
              break;
            IsBootRecovery = (*(__int64 (__fastcall **)(struct ICSIRepairTransaction *, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v26 + 48LL))(
                               v26,
                               0,
                               &v29,
                               0);
            if ( IsBootRecovery < 0 )
              break;
            IsBootRecovery = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 24LL))(
                               v29,
                               0,
                               &v28);
            if ( IsBootRecovery < 0 )
              break;
            if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, __int64 *))(*(_QWORD *)v28 + 24LL))(
                    v28,
                    1,
                    &v35,
                    &v40)
              && v40 )
            {
              if ( (_DWORD)v35 )
              {
                IsBootRecovery = CommitWrapper(v26, v25, v24);
                if ( IsBootRecovery < 0 )
                  break;
                if ( (_DWORD)v35 == v17 )
                {
                  ++*((_DWORD *)a10 + 1);
                  if ( v19 )
                  {
                    ++*((_DWORD *)a10 + 3);
                    --*((_DWORD *)a10 + 2);
                  }
                }
              }
              if ( (_QWORD)v36 )
              {
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v36 + 16LL))(v36);
                *(_QWORD *)&v36 = 0;
              }
            }
            if ( v29 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
              v29 = 0;
            }
            if ( v28 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
              v28 = 0;
            }
          }
          v12 = v23;
        }
        if ( v34[0] )
        {
          (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
          v34[0] = 0;
        }
      }
      if ( v27 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v27 = 0;
      }
      if ( v26 )
      {
        (*(void (__fastcall **)(struct ICSIRepairTransaction *))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
      if ( v31 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v31 = 0;
      }
    }
  }
  if ( v26 )
    (*(void (__fastcall **)(struct ICSIRepairTransaction *))(*(_QWORD *)v26 + 16LL))(v26);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
  if ( v34[0] )
  {
    (*(void (__fastcall **)(struct IDefinitionIdentity *))(*(_QWORD *)v34[0] + 16LL))(v34[0]);
    v34[0] = 0;
  }
  if ( (_QWORD)v36 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v36 + 16LL))(v36);
  return (unsigned int)IsBootRecovery;
}

```

## disassembly

```asm
0x180002d00  push    rbp
0x180002d02  push    rbx
0x180002d03  push    rsi
0x180002d04  push    rdi
0x180002d05  push    r12
0x180002d07  push    r13
0x180002d09  push    r14
0x180002d0b  push    r15
0x180002d0d  lea     rbp, [rsp-7]
0x180002d12  sub     rsp, 0E8h
0x180002d19  mov     rax, cs:__security_cookie
0x180002d20  xor     rax, rsp
0x180002d23  mov     [rbp+3Fh+var_48], rax
0x180002d27  mov     rcx, [rbp+3Fh+arg_38]
0x180002d2e  xorps   xmm0, xmm0
0x180002d31  mov     rax, [rbp+3Fh+arg_40]
0x180002d38  mov     r12d, r8d
0x180002d3b  mov     r15, [rbp+3Fh+arg_50]
0x180002d42  lea     r8, [rbp+3Fh+var_A0]
0x180002d46  mov     rsi, [rbp+3Fh+arg_28]
0x180002d4a  mov     edx, 4
0x180002d4f  mov     rdi, [rbp+3Fh+arg_48]
0x180002d56  mov     r13, [rbp+3Fh+arg_30]
0x180002d5a  mov     [rsp+120h+var_D8], rax
0x180002d5f  mov     dword ptr [r15], 1
0x180002d66  mov     rax, [rcx]
0x180002d69  mov     [rsp+120h+var_E0], r9
0x180002d6e  mov     [rsp+120h+var_E8], rsi
0x180002d73  mov     [rsp+120h+var_D0], 0
0x180002d7c  mov     rax, [rax+18h]
0x180002d80  mov     [rbp+3Fh+var_B8], 0
0x180002d88  mov     [rsp+120h+var_C0], 0
0x180002d91  mov     [rbp+3Fh+var_80], 0
0x180002d99  movdqu  [rbp+3Fh+var_78], xmm0
0x180002d9e  mov     [rbp+3Fh+var_50], 0
0x180002da6  mov     [rsp+120h+var_C8], 0
0x180002daf  mov     [rbp+3Fh+var_98], 0
0x180002db7  movdqu  xmmword ptr [rbp+3Fh+var_90], xmm0
0x180002dbc  mov     [rbp+3Fh+var_58], 0
0x180002dc4  mov     [rbp+3Fh+var_A0], 0
0x180002dcc  mov     [rbp+3Fh+var_B0], 0
0x180002dd4  mov     [rbp+3Fh+var_A8], 0
0x180002ddc  mov     [rbp+3Fh+var_60], 0
0x180002de4  mov     [rsp+120h+var_F0], 0
0x180002dec  mov     [rbp+3Fh+var_68], 0
0x180002df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df8  mov     ebx, eax
0x180002dfa  test    eax, eax
0x180002dfc  js      loc_1800030D9
0x180002e02  mov     rcx, [rbp+3Fh+var_A0]
0x180002e06  lea     r9, [rbp+3Fh+var_60]
0x180002e0a  lea     r8, [rbp+3Fh+var_B0]
0x180002e0e  mov     edx, 1
0x180002e13  mov     rax, [rcx]
0x180002e16  mov     rax, [rax+18h]
0x180002e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e1f  mov     ebx, eax
0x180002e21  test    eax, eax
0x180002e23  jnz     loc_1800030D9
0x180002e29  cmp     [rbp+3Fh+var_60], 0
0x180002e2e  jbe     loc_1800030D9
0x180002e34  lea     rax, [rbp+3Fh+var_68]
0x180002e38  mov     rcx, rsi; struct ICSIStore2 *
0x180002e3b  lea     r9, [rsp+120h+var_D0]; struct ICSIRepairTransaction **
0x180002e40  mov     [rsp+120h+var_100], rax; unsigned int *
0x180002e45  lea     edx, [rbx+6]; unsigned int
0x180002e48  lea     r8d, [rbx+1]; int
0x180002e4c  call    ?BeginRepairTransaction@@YAJPEAUICSIStore2@@KHPEAPEAUICSIRepairTransaction@@PEAK@Z; BeginRepairTransaction(ICSIStore2 *,ulong,int,ICSIRepairTransaction * *,ulong *)
0x180002e51  mov     ebx, eax
0x180002e53  test    eax, eax
0x180002e55  js      loc_1800030D9
0x180002e5b  mov     rcx, [rsp+120h+var_D0]
0x180002e60  lea     r9, [rbp+3Fh+var_68]
0x180002e64  mov     r8, [rbp+3Fh+var_A8]
0x180002e68  mov     edx, 1
0x180002e6d  mov     rax, [rcx]
0x180002e70  mov     rax, [rax+18h]
0x180002e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e79  cmp     [rbp+3Fh+var_68], 2
0x180002e7d  mov     ebx, eax
0x180002e7f  jnz     short loc_180002E88
0x180002e81  mov     dword ptr [r15], 2
0x180002e88  test    eax, eax
0x180002e8a  js      loc_1800030D9
0x180002e90  mov     rcx, [rsp+120h+var_D0]
0x180002e95  lea     r8, [rsp+120h+var_C8]
0x180002e9a  xor     edx, edx
0x180002e9c  mov     rax, [rcx]
0x180002e9f  mov     rax, [rax+20h]
0x180002ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea8  mov     ebx, eax
0x180002eaa  test    eax, eax
0x180002eac  js      loc_1800030D9
0x180002eb2  mov     rcx, [rsp+120h+var_C8]
0x180002eb7  lea     r9, [rbp+3Fh+var_58]
0x180002ebb  lea     r8, [rbp+3Fh+var_98]
0x180002ebf  mov     edx, 1
0x180002ec4  mov     rax, [rcx]
0x180002ec7  mov     rax, [rax+18h]
0x180002ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed0  test    eax, eax
0x180002ed2  jnz     loc_180003075
0x180002ed8  cmp     [rbp+3Fh+var_58], 0
0x180002edd  jbe     loc_180003075
0x180002ee3  mov     r14d, dword ptr [rbp+3Fh+var_98]
0x180002ee7  test    r14d, r14d
0x180002eea  jz      loc_180003058
0x180002ef0  mov     rcx, [rbp+3Fh+var_90]; struct IDefinitionIdentity *
0x180002ef4  lea     r8, [rsp+120h+var_F0]; int *
0x180002ef9  inc     dword ptr [rdi]
0x180002efb  mov     rdx, r13; struct IStore2 *
0x180002efe  call    ?ComponentIsBootRecovery@@YAJPEAUIDefinitionIdentity@@PEAUIStore2@@PEAH@Z; ComponentIsBootRecovery(IDefinitionIdentity *,IStore2 *,int *)
0x180002f03  mov     ebx, eax
0x180002f05  test    eax, eax
0x180002f07  js      loc_1800030D9
0x180002f0d  mov     esi, [rsp+120h+var_F0]
0x180002f11  test    esi, esi
0x180002f13  jz      short loc_180002F18
0x180002f15  inc     dword ptr [rdi+8]
0x180002f18  test    r12d, r12d
0x180002f1b  jz      loc_180003053
0x180002f21  mov     rcx, [rsp+120h+var_D0]
0x180002f26  lea     r9, [rbp+3Fh+var_68]
0x180002f2a  mov     r8, [rbp+3Fh+var_90]
0x180002f2e  mov     edx, 1
0x180002f33  mov     rax, [rcx]
0x180002f36  mov     rax, [rax+28h]
0x180002f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3f  cmp     [rbp+3Fh+var_68], 2
0x180002f43  mov     ebx, eax
0x180002f45  jnz     short loc_180002F4E
0x180002f47  mov     dword ptr [r15], 2
0x180002f4e  test    eax, eax
0x180002f50  js      loc_1800030D9
0x180002f56  mov     rcx, [rsp+120h+var_D0]
0x180002f5b  lea     r8, [rbp+3Fh+var_B8]
0x180002f5f  xor     r9d, r9d
0x180002f62  xor     edx, edx
0x180002f64  mov     rax, [rcx]
0x180002f67  mov     rax, [rax+30h]
0x180002f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f70  mov     ebx, eax
0x180002f72  test    eax, eax
0x180002f74  js      loc_1800030D9
0x180002f7a  mov     rcx, [rbp+3Fh+var_B8]
0x180002f7e  lea     r8, [rsp+120h+var_C0]
0x180002f83  xor     edx, edx
0x180002f85  mov     rax, [rcx]
0x180002f88  mov     rax, [rax+18h]
0x180002f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f91  mov     ebx, eax
0x180002f93  test    eax, eax
0x180002f95  js      loc_1800030D9
0x180002f9b  mov     rcx, [rsp+120h+var_C0]
0x180002fa0  lea     r9, [rbp+3Fh+var_50]
0x180002fa4  lea     r8, [rbp+3Fh+var_80]
0x180002fa8  mov     edx, 1
0x180002fad  mov     rax, [rcx]
0x180002fb0  mov     rax, [rax+18h]
0x180002fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb9  test    eax, eax
0x180002fbb  jnz     short loc_180003017
0x180002fbd  cmp     [rbp+3Fh+var_50], 0
0x180002fc2  jbe     short loc_180003017
0x180002fc4  cmp     dword ptr [rbp+3Fh+var_80], eax
0x180002fc7  jz      short loc_180002FFA
0x180002fc9  mov     r8, [rsp+120h+var_E0]; struct ISFPRebootCallback *
0x180002fce  mov     rdx, [rsp+120h+var_D8]; int *
0x180002fd3  mov     rcx, [rsp+120h+var_D0]; struct ICSIRepairTransaction *
0x180002fd8  call    ?CommitWrapper@@YAJPEAUICSIRepairTransaction@@PEAHPEAUISFPRebootCallback@@@Z; CommitWrapper(ICSIRepairTransaction *,int *,ISFPRebootCallback *)
0x180002fdd  mov     ebx, eax
0x180002fdf  test    eax, eax
0x180002fe1  js      loc_1800030D9
0x180002fe7  cmp     dword ptr [rbp+3Fh+var_80], r14d
0x180002feb  jnz     short loc_180002FFA
0x180002fed  inc     dword ptr [rdi+4]
0x180002ff0  test    esi, esi
0x180002ff2  jz      short loc_180002FFA
0x180002ff4  inc     dword ptr [rdi+0Ch]
0x180002ff7  dec     dword ptr [rdi+8]
0x180002ffa  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x180002ffe  test    rcx, rcx
0x180003001  jz      short loc_180003017
0x180003003  mov     rax, [rcx]
0x180003006  mov     rax, [rax+10h]
0x18000300a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000300f  mov     qword ptr [rbp+3Fh+var_78], 0
0x180003017  mov     rcx, [rbp+3Fh+var_B8]
0x18000301b  test    rcx, rcx
0x18000301e  jz      short loc_180003034
0x180003020  mov     rax, [rcx]
0x180003023  mov     rax, [rax+10h]
0x180003027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000302c  mov     [rbp+3Fh+var_B8], 0
0x180003034  mov     rcx, [rsp+120h+var_C0]
0x180003039  test    rcx, rcx
0x18000303c  jz      short loc_180003053
0x18000303e  mov     rax, [rcx]
0x180003041  mov     rax, [rax+10h]
0x180003045  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304a  mov     [rsp+120h+var_C0], 0
0x180003053  mov     rsi, [rsp+120h+var_E8]
0x180003058  mov     rcx, [rbp+3Fh+var_90]
0x18000305c  test    rcx, rcx
0x18000305f  jz      short loc_180003075
0x180003061  mov     rax, [rcx]
0x180003064  mov     rax, [rax+10h]
0x180003068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306d  mov     [rbp+3Fh+var_90], 0
0x180003075  mov     rcx, [rsp+120h+var_C8]
0x18000307a  test    rcx, rcx
0x18000307d  jz      short loc_180003094
0x18000307f  mov     rax, [rcx]
0x180003082  mov     rax, [rax+10h]
0x180003086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308b  mov     [rsp+120h+var_C8], 0
0x180003094  mov     rcx, [rsp+120h+var_D0]
0x180003099  test    rcx, rcx
0x18000309c  jz      short loc_1800030B3
0x18000309e  mov     rax, [rcx]
0x1800030a1  mov     rax, [rax+10h]
0x1800030a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030aa  mov     [rsp+120h+var_D0], 0
0x1800030b3  mov     rcx, [rbp+3Fh+var_A8]
0x1800030b7  test    rcx, rcx
0x1800030ba  jz      loc_180002E02
0x1800030c0  mov     rax, [rcx]
0x1800030c3  mov     rax, [rax+10h]
0x1800030c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030cc  mov     [rbp+3Fh+var_A8], 0
0x1800030d4  jmp     loc_180002E02
0x1800030d9  mov     rcx, [rsp+120h+var_D0]
0x1800030de  test    rcx, rcx
0x1800030e1  jz      short loc_1800030EF
0x1800030e3  mov     rax, [rcx]
0x1800030e6  mov     rax, [rax+10h]
0x1800030ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ef  mov     rcx, [rbp+3Fh+var_A0]
0x1800030f3  test    rcx, rcx
0x1800030f6  jz      short loc_180003104
0x1800030f8  mov     rax, [rcx]
0x1800030fb  mov     rax, [rax+10h]
0x1800030ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003104  mov     rcx, [rsp+120h+var_C8]
0x180003109  test    rcx, rcx
0x18000310c  jz      short loc_18000311A
0x18000310e  mov     rax, [rcx]
0x180003111  mov     rax, [rax+10h]
0x180003115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000311a  mov     rcx, [rsp+120h+var_C0]
0x18000311f  test    rcx, rcx
0x180003122  jz      short loc_180003130
0x180003124  mov     rax, [rcx]
0x180003127  mov     rax, [rax+10h]
0x18000312b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003130  mov     rcx, [rbp+3Fh+var_B8]
0x180003134  test    rcx, rcx
0x180003137  jz      short loc_180003145
0x180003139  mov     rax, [rcx]
0x18000313c  mov     rax, [rax+10h]
0x180003140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003145  mov     rcx, [rbp+3Fh+var_A8]
0x180003149  test    rcx, rcx
0x18000314c  jz      short loc_180003162
0x18000314e  mov     rax, [rcx]
0x180003151  mov     rax, [rax+10h]
0x180003155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315a  mov     [rbp+3Fh+var_A8], 0
0x180003162  mov     rcx, [rbp+3Fh+var_90]
0x180003166  test    rcx, rcx
0x180003169  jz      short loc_18000317F
0x18000316b  mov     rax, [rcx]
0x18000316e  mov     rax, [rax+10h]
0x180003172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003177  mov     [rbp+3Fh+var_90], 0
0x18000317f  mov     rcx, qword ptr [rbp+3Fh+var_78]
0x180003183  test    rcx, rcx
0x180003186  jz      short loc_180003194
0x180003188  mov     rax, [rcx]
0x18000318b  mov     rax, [rax+10h]
0x18000318f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003194  mov     eax, ebx
0x180003196  mov     rcx, [rbp+3Fh+var_48]
0x18000319a  xor     rcx, rsp; StackCookie
0x18000319d  call    __security_check_cookie
0x1800031a2  add     rsp, 0E8h
0x1800031a9  pop     r15
0x1800031ab  pop     r14
0x1800031ad  pop     r13
0x1800031af  pop     r12
0x1800031b1  pop     rdi
0x1800031b2  pop     rsi
0x1800031b3  pop     rbx
0x1800031b4  pop     rbp
0x1800031b5  retn
```

# ScControlService(void *,CServiceRecord *,ulong,ulong,int,ushort const *,_SERVICE_STATUS_PROCESS *,int)

- ea: `0x140007d80`
- end: `0x1400083e4`
- name: `?ScControlService@@YAKPEAXPEAVCServiceRecord@@KKHPEBGPEAU_SERVICE_STATUS_PROCESS@@H@Z`
- size: `1636`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, struct CServiceRecord *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int, const unsigned __int16 *, struct _SERVICE_STATUS_PROCESS *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x140007ac0`
- `0x140007d00`

## callees

- `0x140003e54`
- `0x140007d80`
- `0x1400083f0`
- `0x140008548`
- `0x1400089c8`
- `0x1400188fc`
- `0x14002a54c`
- `0x140030168`
- `0x140040ac0`
- `0x1400731bc`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007e43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140008064`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000820d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140007e43`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140008064`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x14000820d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007eeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400080d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008226`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140007eeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1400080d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140008226`
- `ntdll!RtlReleaseResource` at `0x1400080e2`
- `ntdll!RtlReleaseResource` at `0x14000823c`
- `ntdll!RtlReleaseResource` at `0x140008348`
- `ntdll!RtlReleaseResource` at `0x1400080e2`
- `ntdll!RtlReleaseResource` at `0x14000823c`
- `ntdll!RtlReleaseResource` at `0x140008348`
- `ntdll!RtlAcquireResourceShared` at `0x14000805b`
- `ntdll!RtlAcquireResourceShared` at `0x1400081fd`
- `ntdll!RtlAcquireResourceShared` at `0x14000805b`
- `ntdll!RtlAcquireResourceShared` at `0x1400081fd`
- `ntdll!RtlAreAllAccessesGranted` at `0x140007df2`
- `ntdll!RtlAreAllAccessesGranted` at `0x140007df2`

## pseudocode

```c
unsigned int __fastcall ScControlService(
        _QWORD *a1,
        struct CServiceRecord *a2,
        unsigned int a3,
        int a4,
        int a5,
        const unsigned __int16 *a6,
        struct _SERVICE_STATUS *a7,
        int a8)
{
  int v11; // r14d
  ACCESS_MASK v12; // ebp
  int v13; // esi
  __int64 v14; // rbx
  int v15; // eax
  int v16; // edx
  int v17; // r8d
  int v18; // r15d
  int v19; // r12d
  unsigned int result; // eax
  RTL_SRWLOCK *v21; // r14
  int v22; // eax
  int v23; // r15d
  const wchar_t *v24; // rax

  a8 = 0;
  if ( a1 )
    ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
    return 1115;
  if ( !a1 || *(_DWORD *)a1 != 1215456627 )
    return 6;
  v11 = 0;
  if ( a3 == 4 )
  {
    v12 = 128;
    goto LABEL_8;
  }
  if ( a3 - 128 > 0x7F )
  {
    if ( (unsigned int)ScCheckServiceProtectedProcess(a1, a3 == 1) )
      return 5;
    if ( a3 == 32 )
    {
      v12 = 16;
      v11 = 1024;
LABEL_8:
      if ( RtlAreAllAccessesGranted(*((_DWORD *)a1 + 2), v12) )
      {
        v13 = 0;
        if ( a3 == 32 )
        {
          result = ScStatusAccessCheck(0);
          v13 = result;
          if ( result )
            return result;
        }
        v14 = a1[2];
        v15 = *(_DWORD *)(v14 + 80);
        if ( (v15 & 0x400) != 0 )
          return 1052;
        if ( (v15 & 0xB) != 0 )
          return ScControlDriver(a3, (struct CDriverRecord *)v14, a7);
        AcquireSRWLockShared((PSRWLOCK)(v14 + 312));
        (*(void (__fastcall **)(__int64, struct _SERVICE_STATUS *))(*(_QWORD *)v14 + 152LL))(v14, a7);
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) )
        {
          a7[1].dwServiceType = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) + 40);
          if ( (*(_BYTE *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) + 104) & 2) != 0 )
            a7[1].dwCurrentState |= 1u;
        }
        v18 = *(_DWORD *)(v14 + 84);
        v19 = *(_DWORD *)(v14 + 88);
        if ( v18 == 1 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) )
          v13 = 1062;
        if ( v14 != -312 )
          ReleaseSRWLockShared((PSRWLOCK)(v14 + 312));
        if ( v13 )
          return v13;
        if ( v18 == 3 )
          return 1061;
        if ( v18 == 2 && a3 != 1 )
        {
          if ( a3 == 4 )
            return 0;
          return 1061;
        }
        if ( (v11 & v19) != v11 )
          return 1052;
        if ( a3 == 1 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
          {
            v24 = L"NULL";
            if ( a6 )
              v24 = a6;
            WPP_SF_SdLS(WPP_GLOBAL_Control->StubInfo, v16, v17, *(_QWORD *)(v14 + 56), 1, a4, (__int64)v24);
          }
          RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
          v21 = (RTL_SRWLOCK *)(v14 + 312);
          AcquireSRWLockShared((PSRWLOCK)(v14 + 312));
          v23 = CServiceRecord::AreDependentsStoppedLocked((CServiceRecord *)v14);
          if ( v14 != -312 )
            ReleaseSRWLockShared((PSRWLOCK)(v14 + 312));
          if ( !v23 )
          {
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_S(
                WPP_GLOBAL_Control->StubInfo,
                11,
                WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                *(_QWORD *)(v14 + 56));
            }
            v13 = 1051;
            RtlReleaseResource(&ScServiceRecordLock);
            return v13;
          }
          RtlReleaseResource(&ScServiceRecordLock);
        }
        else
        {
          v21 = (RTL_SRWLOCK *)(v14 + 312);
        }
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *, _DWORD, _DWORD, int, const unsigned __int16 *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v14 + 64LL))(
                v14,
                0,
                a3,
                0,
                0,
                0,
                &a8,
                0,
                0,
                a4,
                a6,
                0,
                0,
                0);
        v22 = a8;
        if ( v12 == 256 && a5 )
        {
          if ( v13 )
          {
LABEL_50:
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              WPP_SF_Sd(
                WPP_GLOBAL_Control->StubInfo,
                12,
                (unsigned int)WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids,
                *(_QWORD *)(v14 + 56),
                v13);
              v22 = a8;
            }
            if ( a3 == 1 && (v13 != 1061 || v22 != 0x80000000) )
              ScRemoveService((struct CWin32ServiceRecord *)v14, 1, 1);
            return v13;
          }
          if ( a8 == 120 || !a8 )
          {
LABEL_36:
            RtlAcquireResourceShared(&ScServiceRecordLock, 1u);
            AcquireSRWLockShared(v21);
            if ( a7 )
            {
              *(_OWORD *)&a7->dwServiceType = *(_OWORD *)(v14 + 80);
              *(_OWORD *)&a7->dwWin32ExitCode = *(_OWORD *)(v14 + 92);
            }
            if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) )
            {
              a7[1].dwServiceType = *(_DWORD *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) + 40);
              if ( (*(_BYTE *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 160LL))(v14) + 104) & 2) != 0 )
                a7[1].dwCurrentState |= 1u;
            }
            if ( v21 )
              ReleaseSRWLockShared(v21);
            RtlReleaseResource(&ScServiceRecordLock);
            return v13;
          }
          v13 = a8;
        }
        if ( v13 )
          goto LABEL_50;
        goto LABEL_36;
      }
      return 5;
    }
  }
  switch ( a3 )
  {
    case 1u:
      v12 = 32;
      v11 = 1;
      goto LABEL_8;
    case 2u:
    case 3u:
      v12 = 64;
      v11 = 2;
      goto LABEL_8;
    case 6u:
      v12 = 64;
      v11 = 8;
      goto LABEL_8;
    case 7u:
    case 8u:
    case 9u:
    case 0xAu:
      v12 = 64;
      v11 = 16;
      goto LABEL_8;
    case 0x60u:
      v12 = 16;
      v11 = 0x2000;
      goto LABEL_8;
    default:
      if ( a3 - 128 <= 0x7F )
      {
        v12 = 256;
        goto LABEL_8;
      }
      result = 87;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x140007d80  push    rbx
0x140007d82  push    rdi
0x140007d83  push    r13
0x140007d85  sub     rsp, 90h
0x140007d8c  mov     [rsp+0A8h+arg_38], 0
0x140007d97  mov     r13d, r9d
0x140007d9a  mov     edi, r8d
0x140007d9d  mov     rbx, rcx
0x140007da0  test    rcx, rcx
0x140007da3  jz      short loc_140007DAA
0x140007da5  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x140007daa  cmp     cs:?ScShutdownInProgress@@3KA, 0; ulong ScShutdownInProgress
0x140007db1  jnz     loc_1400081CD
0x140007db7  mov     [rsp+0A8h+arg_0], rbp
0x140007dbf  mov     [rsp+0A8h+var_20], r14
0x140007dc7  test    rbx, rbx
0x140007dca  jz      loc_140007FA6
0x140007dd0  cmp     dword ptr [rbx], 48726573h
0x140007dd6  jnz     loc_140007FA6
0x140007ddc  xor     r14d, r14d
0x140007ddf  cmp     edi, 4
0x140007de2  jnz     loc_140007F6B
0x140007de8  mov     ebp, 80h
0x140007ded  mov     ecx, [rbx+8]; GrantedAccess
0x140007df0  mov     edx, ebp; DesiredAccess
0x140007df2  call    cs:__imp_RtlAreAllAccessesGranted
0x140007df8  test    al, al
0x140007dfa  jz      loc_14000827A
0x140007e00  mov     [rsp+0A8h+arg_8], rsi
0x140007e08  xor     esi, esi
0x140007e0a  cmp     edi, 20h ; ' '
0x140007e0d  jz      loc_1400080ED
0x140007e13  mov     rbx, [rbx+10h]
0x140007e17  mov     eax, [rbx+50h]
0x140007e1a  bt      eax, 0Ah
0x140007e1e  jb      loc_140007F64
0x140007e24  test    al, 0Bh
0x140007e26  jnz     loc_140007F50
0x140007e2c  mov     [rsp+0A8h+arg_10], r12
0x140007e34  lea     rcx, [rbx+138h]; SRWLock
0x140007e3b  mov     [rsp+0A8h+var_28], r15
0x140007e43  call    cs:__imp_AcquireSRWLockShared
0x140007e49  mov     rax, [rbx]
0x140007e4c  mov     rcx, rbx
0x140007e4f  mov     r15, [rsp+0A8h+arg_30]
0x140007e57  mov     rdx, r15
0x140007e5a  mov     rax, [rax+98h]
0x140007e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e66  mov     rax, [rbx]
0x140007e69  mov     rcx, rbx
0x140007e6c  mov     rax, [rax+0A0h]
0x140007e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e78  test    rax, rax
0x140007e7b  jz      short loc_140007EB2
0x140007e7d  mov     rax, [rbx]
0x140007e80  mov     rcx, rbx
0x140007e83  mov     rax, [rax+0A0h]
0x140007e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007e8f  mov     ecx, [rax+28h]
0x140007e92  mov     [r15+1Ch], ecx
0x140007e96  mov     rcx, rbx
0x140007e99  mov     rax, [rbx]
0x140007e9c  mov     rax, [rax+0A0h]
0x140007ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ea8  test    byte ptr [rax+68h], 2
0x140007eac  jnz     loc_14000813A
0x140007eb2  mov     r15d, [rbx+54h]
0x140007eb6  mov     r12d, [rbx+58h]
0x140007eba  cmp     r15d, 1
0x140007ebe  jz      loc_140008247
0x140007ec4  mov     rax, [rbx]
0x140007ec7  mov     rcx, rbx
0x140007eca  mov     rax, [rax+0A0h]
0x140007ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ed6  test    rax, rax
0x140007ed9  jz      loc_140008247
0x140007edf  lea     rcx, [rbx+138h]; SRWLock
0x140007ee6  test    rcx, rcx
0x140007ee9  jz      short loc_140007EF1
0x140007eeb  call    cs:__imp_ReleaseSRWLockShared
0x140007ef1  test    esi, esi
0x140007ef3  jnz     short loc_140007F1A
0x140007ef5  cmp     r15d, 3
0x140007ef9  jz      loc_1400082BE
0x140007eff  cmp     r15d, 2
0x140007f03  jz      loc_1400082C8
0x140007f09  and     r12d, r14d
0x140007f0c  cmp     r12d, r14d
0x140007f0f  jz      loc_140007FAD
0x140007f15  mov     esi, 41Ch
0x140007f1a  mov     r15, [rsp+0A8h+var_28]
0x140007f22  mov     eax, esi
0x140007f24  mov     r12, [rsp+0A8h+arg_10]
0x140007f2c  mov     rsi, [rsp+0A8h+arg_8]
0x140007f34  mov     rbp, [rsp+0A8h+arg_0]
0x140007f3c  mov     r14, [rsp+0A8h+var_20]
0x140007f44  add     rsp, 90h
0x140007f4b  pop     r13
0x140007f4d  pop     rdi
0x140007f4e  pop     rbx
0x140007f4f  retn
0x140007f50  mov     r8, [rsp+0A8h+arg_30]; struct _SERVICE_STATUS *
0x140007f58  mov     rdx, rbx; struct CDriverRecord *
0x140007f5b  mov     ecx, edi; unsigned int
0x140007f5d  call    ?ScControlDriver@@YAKKPEAVCDriverRecord@@PEAU_SERVICE_STATUS@@@Z; ScControlDriver(ulong,CDriverRecord *,_SERVICE_STATUS *)
0x140007f62  jmp     short loc_140007F2C
0x140007f64  mov     eax, 41Ch
0x140007f69  jmp     short loc_140007F2C
0x140007f6b  lea     eax, [rdi-80h]
0x140007f6e  cmp     eax, 7Fh
0x140007f71  jbe     loc_140008103
0x140007f77  cmp     edi, 1
0x140007f7a  mov     rcx, rbx; void *
0x140007f7d  setz    dl; unsigned __int8
0x140007f80  call    ?ScCheckServiceProtectedProcess@@YAKPEAXE@Z; ScCheckServiceProtectedProcess(void *,uchar)
0x140007f85  test    eax, eax
0x140007f87  jnz     loc_14000827A
0x140007f8d  cmp     edi, 20h ; ' '
0x140007f90  jnz     loc_140008103
0x140007f96  mov     ebp, 10h
0x140007f9b  mov     r14d, 400h
0x140007fa1  jmp     loc_140007DED
0x140007fa6  mov     eax, 6
0x140007fab  jmp     short loc_140007F34
0x140007fad  mov     rsi, [rsp+0A8h+arg_28]
0x140007fb5  lea     r12, WPP_GLOBAL_Control
0x140007fbc  cmp     edi, 1
0x140007fbf  jz      loc_1400081DE
0x140007fc5  lea     r14, [rbx+138h]
0x140007fcc  mov     rax, [rbx]
0x140007fcf  lea     rcx, [rsp+0A8h+arg_38]
0x140007fd7  mov     [rsp+0A8h+var_40], 0
0x140007fdf  xor     r9d, r9d
0x140007fe2  mov     [rsp+0A8h+var_48], 0
0x140007feb  mov     r8d, edi
0x140007fee  mov     [rsp+0A8h+var_50], 0
0x140007ff7  xor     edx, edx
0x140007ff9  mov     rax, [rax+40h]
0x140007ffd  mov     [rsp+0A8h+var_58], rsi
0x140008002  mov     [rsp+0A8h+var_60], r13d
0x140008007  mov     [rsp+0A8h+var_68], 0
0x14000800f  mov     [rsp+0A8h+var_70], 0
0x140008017  mov     [rsp+0A8h+var_78], rcx
0x14000801c  mov     rcx, rbx
0x14000801f  mov     [rsp+0A8h+var_80], 0
0x140008027  mov     [rsp+0A8h+var_88], 0
0x140008030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008035  mov     esi, eax
0x140008037  mov     eax, [rsp+0A8h+arg_38]
0x14000803e  cmp     ebp, 100h
0x140008044  jz      loc_14000814A
0x14000804a  test    esi, esi
0x14000804c  jnz     loc_140008160
0x140008052  mov     dl, 1; Wait
0x140008054  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14000805b  call    cs:__imp_RtlAcquireResourceShared
0x140008061  mov     rcx, r14; SRWLock
0x140008064  call    cs:__imp_AcquireSRWLockShared
0x14000806a  mov     rdi, [rsp+0A8h+arg_30]
0x140008072  test    rdi, rdi
0x140008075  jz      short loc_140008086
0x140008077  movups  xmm0, xmmword ptr [rbx+50h]
0x14000807b  movups  xmmword ptr [rdi], xmm0
0x14000807e  movups  xmm1, xmmword ptr [rbx+5Ch]
0x140008082  movups  xmmword ptr [rdi+0Ch], xmm1
0x140008086  mov     rax, [rbx]
0x140008089  mov     rcx, rbx
0x14000808c  mov     rax, [rax+0A0h]
0x140008093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008098  test    rax, rax
0x14000809b  jz      short loc_1400080CD
0x14000809d  mov     rax, [rbx]
0x1400080a0  mov     rcx, rbx
0x1400080a3  mov     rax, [rax+0A0h]
0x1400080aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080af  mov     ecx, [rax+28h]
0x1400080b2  mov     [rdi+1Ch], ecx
0x1400080b5  mov     rcx, rbx
0x1400080b8  mov     rax, [rbx]
0x1400080bb  mov     rax, [rax+0A0h]
0x1400080c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080c7  test    byte ptr [rax+68h], 2
0x1400080cb  jnz     short loc_140008144
0x1400080cd  test    r14, r14
0x1400080d0  jz      short loc_1400080DB
0x1400080d2  mov     rcx, r14; SRWLock
0x1400080d5  call    cs:__imp_ReleaseSRWLockShared
0x1400080db  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400080e2  call    cs:__imp_RtlReleaseResource
0x1400080e8  jmp     loc_140007F1A
0x1400080ed  xor     ecx, ecx; struct CServiceRecord *
0x1400080ef  call    ?ScStatusAccessCheck@@YAKPEAVCServiceRecord@@@Z; ScStatusAccessCheck(CServiceRecord *)
0x1400080f4  mov     esi, eax
0x1400080f6  test    eax, eax
0x1400080f8  jz      loc_140007E13
0x1400080fe  jmp     loc_140007F2C
0x140008103  lea     eax, [rdi-1]; switch 96 cases
0x140008106  cmp     eax, 5Fh
0x140008109  ja      def_140008128; jumptable 0000000140008128 default case, cases 4,5,11-95
0x14000810f  lea     rdx, __ImageBase
0x140008116  movzx   eax, ds:(byte_140008384 - 140000000h)[rdx+rax]
0x14000811e  mov     ecx, ds:(jpt_140008128 - 140000000h)[rdx+rax*4]
0x140008125  add     rcx, rdx
0x140008128  jmp     rcx; switch jump
0x14000812a  mov     ebp, 40h ; '@'; jumptable 0000000140008128 cases 2,3
0x14000812f  mov     r14d, 2
0x140008135  jmp     loc_140007DED
0x14000813a  or      dword ptr [r15+20h], 1
0x14000813f  jmp     loc_140007EB2
0x140008144  or      dword ptr [rdi+20h], 1
0x140008148  jmp     short loc_1400080CD
0x14000814a  cmp     [rsp+0A8h+arg_20], 0
0x140008152  jz      loc_14000804A
0x140008158  test    esi, esi
0x14000815a  jz      loc_140008353
0x140008160  mov     rcx, cs:WPP_GLOBAL_Control
0x140008167  cmp     rcx, r12
0x14000816a  jz      short loc_140008176
0x14000816c  test    byte ptr [rcx+1Ch], 1
0x140008170  jnz     loc_140008251
0x140008176  cmp     edi, 1
0x140008179  jnz     loc_140007F1A
0x14000817f  cmp     esi, 425h
0x140008185  jnz     short loc_140008192
0x140008187  cmp     eax, 80000000h
0x14000818c  jz      loc_140007F1A
0x140008192  mov     edx, 1; int
0x140008197  mov     rcx, rbx; struct CWin32ServiceRecord *
0x14000819a  mov     r8d, edx; int
0x14000819d  call    ?ScRemoveService@@YAKPEAVCWin32ServiceRecord@@HH@Z; ScRemoveService(CWin32ServiceRecord *,int,int)
0x1400081a2  jmp     loc_140007F1A
0x1400081a7  lea     eax, [rdi-80h]; jumptable 0000000140008128 default case, cases 4,5,11-95
0x1400081aa  cmp     eax, 7Fh
0x1400081ad  ja      loc_1400082B4
0x1400081b3  mov     ebp, 100h
0x1400081b8  jmp     loc_140007DED
0x1400081bd  mov     ebp, 40h ; '@'; jumptable 0000000140008128 case 6
0x1400081c2  mov     r14d, 8
0x1400081c8  jmp     loc_140007DED
0x1400081cd  mov     eax, 45Bh
0x1400081d2  add     rsp, 90h
0x1400081d9  pop     r13
0x1400081db  pop     rdi
0x1400081dc  pop     rbx
0x1400081dd  retn
0x1400081de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081e5  cmp     rcx, r12
0x1400081e8  jz      short loc_1400081F4
0x1400081ea  test    byte ptr [rcx+1Ch], 4
0x1400081ee  jnz     loc_1400082DF
0x1400081f4  mov     dl, 1; Wait
0x1400081f6  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400081fd  call    cs:__imp_RtlAcquireResourceShared
0x140008203  lea     r14, [rbx+138h]
0x14000820a  mov     rcx, r14; SRWLock
0x14000820d  call    cs:__imp_AcquireSRWLockShared
0x140008213  mov     rcx, rbx; this
0x140008216  call    ?AreDependentsStoppedLocked@CServiceRecord@@QEAAHXZ; CServiceRecord::AreDependentsStoppedLocked(void)
0x14000821b  mov     r15d, eax
0x14000821e  test    r14, r14
0x140008221  jz      short loc_14000822C
0x140008223  mov     rcx, r14; SRWLock
0x140008226  call    cs:__imp_ReleaseSRWLockShared
0x14000822c  test    r15d, r15d
0x14000822f  jz      loc_140008311
0x140008235  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x14000823c  call    cs:__imp_RtlReleaseResource
0x140008242  jmp     loc_140007FCC
0x140008247  mov     esi, 426h
0x14000824c  jmp     loc_140007EDF
0x140008251  mov     r9, [rbx+38h]
0x140008255  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14000825c  mov     rcx, [rcx+10h]
0x140008260  mov     edx, 0Ch
0x140008265  mov     dword ptr [rsp+0A8h+var_88], esi
0x140008269  call    WPP_SF_Sd
0x14000826e  mov     eax, [rsp+0A8h+arg_38]
0x140008275  jmp     loc_140008176
0x14000827a  mov     eax, 5
0x14000827f  jmp     loc_140007F34
0x140008284  mov     ebp, 20h ; ' '; jumptable 0000000140008128 case 1
0x140008289  mov     r14d, 1
0x14000828f  jmp     loc_140007DED
0x140008294  mov     ebp, 40h ; '@'; jumptable 0000000140008128 cases 7-10
0x140008299  mov     r14d, 10h
0x14000829f  jmp     loc_140007DED
0x1400082a4  mov     ebp, 10h; jumptable 0000000140008128 case 96
0x1400082a9  mov     r14d, 2000h
0x1400082af  jmp     loc_140007DED
0x1400082b4  mov     eax, 57h ; 'W'
0x1400082b9  jmp     loc_140007F34
0x1400082be  mov     esi, 425h
0x1400082c3  jmp     loc_140007F1A
0x1400082c8  mov     eax, edi
0x1400082ca  sub     eax, 1
0x1400082cd  jz      loc_140007F09
0x1400082d3  cmp     eax, 3
0x1400082d6  jnz     short loc_1400082BE
0x1400082d8  xor     esi, esi
0x1400082da  jmp     loc_140007F1A
  ... truncated ...
```

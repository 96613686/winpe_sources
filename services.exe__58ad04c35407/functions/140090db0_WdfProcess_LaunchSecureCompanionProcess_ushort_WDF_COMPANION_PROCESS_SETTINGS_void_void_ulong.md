# WdfProcess::LaunchSecureCompanionProcess(ushort *,_WDF_COMPANION_PROCESS_SETTINGS *,void *,void *,ulong)

- ea: `0x140090db0`
- end: `0x140091303`
- name: `?LaunchSecureCompanionProcess@WdfProcess@@AEAAJPEAGPEAU_WDF_COMPANION_PROCESS_SETTINGS@@PEAX2K@Z`
- size: `1363`
- prototype: `__int64 __fastcall(WdfProcess *__hidden this, unsigned __int16 *, struct _WDF_COMPANION_PROCESS_SETTINGS *, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14008f640`

## callees

- `0x140004c58`
- `0x1400575b0`
- `0x140090db0`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14009128c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14009128c`
- `ntdll!NtClose` at `0x1400912c2`
- `ntdll!NtClose` at `0x1400912d1`
- `ntdll!NtClose` at `0x1400912c2`
- `ntdll!NtClose` at `0x1400912d1`
- `ntdll!RtlInitUnicodeString` at `0x140090e76`
- `ntdll!RtlInitUnicodeString` at `0x140090e76`
- `ntdll!RtlFreeHeap` at `0x1400912b3`
- `ntdll!RtlFreeHeap` at `0x1400912b3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140090f8c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x140090f8c`
- `ntdll!RtlCreateProcessParametersEx` at `0x14009106c`
- `ntdll!RtlCreateProcessParametersEx` at `0x14009106c`
- `ntdll!NtCreateUserProcess` at `0x14009123c`
- `ntdll!NtCreateUserProcess` at `0x14009123c`

## pseudocode

```c
__int64 __fastcall WdfProcess::LaunchSecureCompanionProcess(
        WdfProcess *this,
        unsigned __int16 *a2,
        struct _WDF_COMPANION_PROCESS_SETTINGS *a3,
        void *a4,
        void *a5,
        unsigned int a6)
{
  signed int v10; // ebx
  PRPC_ASYNC_STATE v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  _QWORD *v14; // r15
  _WORD *v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdx
  _WORD *v18; // rax
  unsigned __int16 *v19; // rax
  __int16 v20; // di
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rdi
  void *v22; // rcx
  __int64 v23; // rax
  char v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  __int128 v28; // [rsp+80h] [rbp-80h] BYREF
  __int64 v29; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+98h] [rbp-68h]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  void *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  __int128 v34; // [rsp+C0h] [rbp-40h]
  int v35; // [rsp+D0h] [rbp-30h]
  _DWORD v36[27]; // [rsp+D4h] [rbp-2Ch] BYREF
  _QWORD v37[12]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v38[22]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset(v38, 0, 0xA8u);
  v28 = 0;
  memset(v37, 0, 0x58u);
  v29 = 48;
  v26 = 0;
  v31 = 0;
  v32 = a4;
  v33 = 0;
  v25 = (a6 == 128) + 2;
  DestinationString = 0;
  v30 = 0;
  memset(v36, 0, 0x64u);
  v35 = 104;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !a3 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_49;
    }
    v12 = 43;
    goto LABEL_6;
  }
  v14 = (_QWORD *)((char *)a3 + 8);
  if ( !*v14 )
  {
    v10 = -1073741811;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_49;
    }
    v12 = 44;
LABEL_6:
    v13 = 3221225485LL;
LABEL_7:
    WPP_SF_d(v11->u.APC.hThread, v12, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, v13);
LABEL_49:
    if ( DestinationString.Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
    if ( *(_QWORD *)&v36[1] )
      NtClose(*(HANDLE *)&v36[1]);
    if ( *(_QWORD *)&v36[3] )
      NtClose(*(HANDLE *)&v36[3]);
    return (unsigned int)v10;
  }
  v15 = (_WORD *)*((_QWORD *)this + 14);
  v16 = 0x7FFF;
  v34 = 0;
  if ( v15 )
  {
    v17 = 0x7FFF;
    v18 = v15;
    while ( *v18 )
    {
      ++v18;
      if ( !--v17 )
      {
        v10 = -1073741811;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
          && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
        {
          v12 = 45;
          goto LABEL_6;
        }
        goto LABEL_49;
      }
    }
  }
  else
  {
    v15 = (_WORD *)*((_QWORD *)&v34 + 1);
  }
  v10 = RtlDosPathNameToNtPathName_U_WithStatus(v15, &DestinationString, 0, 0);
  if ( v10 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_49;
    }
    v12 = 46;
    goto LABEL_27;
  }
  v28 = 0;
  if ( a2 )
  {
    v19 = a2;
    do
    {
      if ( !*v19 )
        break;
      ++v19;
      --v16;
    }
    while ( v16 );
    v10 = v16 == 0 ? 0xC000000D : 0;
    if ( !v16 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
        || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
        || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
      {
        goto LABEL_49;
      }
      v12 = 47;
LABEL_27:
      v13 = (unsigned int)v10;
      goto LABEL_7;
    }
    v20 = 2 * v16;
    *((_QWORD *)&v28 + 1) = a2;
    LOWORD(v28) = -2 - v20;
    WORD1(v28) = -v20;
  }
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  v10 = RtlCreateProcessParametersEx(&v26, &DestinationString, 0, 0, &v28, 0, 0, 0, 0, 0, 1);
  if ( v10 >= 0 )
  {
    *(_DWORD *)(v26 + 1032) = ProcessParameters[1].Flags;
    memset(v37, 0, 0x58u);
    v37[0] = 88;
    v38[3] = &v36[5];
    v38[6] = DestinationString.Length;
    v38[7] = DestinationString.Buffer;
    v38[15] = a5;
    v38[19] = &v25;
    LOBYTE(v37[2]) = 4;
    v38[1] = 65539;
    v38[2] = 16;
    v38[4] = 0;
    v38[5] = 131077;
    v38[8] = 0;
    v38[9] = 131090;
    v38[10] = 8;
    v38[12] = 0;
    v38[11] = v14;
    v38[13] = 393218;
    v38[14] = 8;
    v38[16] = 0;
    v38[17] = 131080;
    v38[18] = 1;
    v38[20] = 0;
    v38[0] = 168;
    v10 = NtCreateUserProcess(&v36[1], &v36[3], 0x2000000, 0x2000000, &v29, 0, 256, 0, v26, v37, v38);
    if ( v10 >= 0 )
    {
      v22 = *(void **)&v36[1];
      v23 = *(_QWORD *)&v36[3];
      *((_QWORD *)this + 15) = *(_QWORD *)&v36[1];
      *((_QWORD *)this + 16) = v23;
      *(_QWORD *)&v36[1] = 0;
      *(_QWORD *)&v36[3] = 0;
      *((_DWORD *)this + 34) = GetProcessId(v22);
      goto LABEL_49;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
      || (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) == 0
      || *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) < 2u )
    {
      goto LABEL_49;
    }
    v12 = 49;
    goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
    && (*((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 20) & 8) != 0
    && *((_BYTE *)&WPP_GLOBAL_Control->u.NotificationRoutine + 17) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->u.APC.hThread, 48, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids, (unsigned int)v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140090db0  mov     [rsp-8+arg_8], rbx
0x140090db5  push    rbp
0x140090db6  push    rsi
0x140090db7  push    rdi
0x140090db8  push    r12
0x140090dba  push    r13
0x140090dbc  push    r14
0x140090dbe  push    r15
0x140090dc0  lea     rbp, [rsp-160h]
0x140090dc8  sub     rsp, 260h
0x140090dcf  mov     rax, cs:__security_cookie
0x140090dd6  xor     rax, rsp
0x140090dd9  mov     [rbp+190h+var_40], rax
0x140090de0  mov     r15, r8
0x140090de3  mov     r14, rdx
0x140090de6  mov     rsi, rcx
0x140090de9  xor     edx, edx; Val
0x140090deb  mov     r8d, 0A8h; Size
0x140090df1  lea     rcx, [rbp+190h+var_F0]; void *
0x140090df8  mov     rbx, r9
0x140090dfb  call    memset
0x140090e00  xor     edx, edx; Val
0x140090e02  lea     rcx, [rbp+190h+var_150]; void *
0x140090e06  xorps   xmm0, xmm0
0x140090e09  movups  [rbp+190h+var_210], xmm0
0x140090e0d  lea     r8d, [rdx+58h]; Size
0x140090e11  call    memset
0x140090e16  xor     r12d, r12d
0x140090e19  mov     [rbp+190h+var_200], 30h ; '0'
0x140090e21  cmp     [rbp+190h+arg_28], 80h
0x140090e2b  lea     rcx, [rbp+190h+var_1BC]; void *
0x140090e2f  xorps   xmm0, xmm0
0x140090e32  mov     [rsp+290h+var_228], r12
0x140090e37  setz    al
0x140090e3a  mov     [rbp+190h+var_1E8], r12
0x140090e3e  lea     r13d, [r12+2]
0x140090e43  mov     [rbp+190h+var_1E0], rbx
0x140090e47  add     al, r13b
0x140090e4a  mov     [rbp+190h+var_1D8], r12
0x140090e4e  xor     edx, edx; Val
0x140090e50  mov     [rsp+290h+var_230], al
0x140090e54  lea     r8d, [r12+64h]; Size
0x140090e59  movups  xmmword ptr [rsp+290h+DestinationString.Length], xmm0
0x140090e5e  movdqu  [rbp+190h+var_1F8], xmm0
0x140090e63  call    memset
0x140090e68  xor     edx, edx; SourceString
0x140090e6a  mov     [rbp+190h+var_1C0], 68h ; 'h'
0x140090e71  lea     rcx, [rsp+290h+DestinationString]; DestinationString
0x140090e76  call    cs:__imp_RtlInitUnicodeString
0x140090e7c  test    r15, r15
0x140090e7f  jnz     short loc_140090ED2
0x140090e81  mov     r8d, 0C000000Dh
0x140090e87  mov     ebx, r8d
0x140090e8a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090e91  lea     rax, WPP_GLOBAL_Control
0x140090e98  cmp     rcx, rax
0x140090e9b  jz      loc_140091298
0x140090ea1  test    byte ptr [rcx+44h], 8
0x140090ea5  jz      loc_140091298
0x140090eab  cmp     [rcx+41h], r13b
0x140090eaf  jb      loc_140091298
0x140090eb5  lea     edx, [r12+2Bh]
0x140090eba  mov     r9d, r8d
0x140090ebd  mov     rcx, [rcx+38h]
0x140090ec1  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x140090ec8  call    WPP_SF_d
0x140090ecd  jmp     loc_140091298
0x140090ed2  add     r15, 8
0x140090ed6  cmp     [r15], r12
0x140090ed9  jnz     short loc_140090F16
0x140090edb  mov     r8d, 0C000000Dh
0x140090ee1  mov     ebx, r8d
0x140090ee4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090eeb  lea     rax, WPP_GLOBAL_Control
0x140090ef2  cmp     rcx, rax
0x140090ef5  jz      loc_140091298
0x140090efb  test    byte ptr [rcx+44h], 8
0x140090eff  jz      loc_140091298
0x140090f05  cmp     [rcx+41h], r13b
0x140090f09  jb      loc_140091298
0x140090f0f  mov     edx, 2Ch ; ','
0x140090f14  jmp     short loc_140090EBA
0x140090f16  mov     rcx, [rsi+70h]
0x140090f1a  xorps   xmm0, xmm0
0x140090f1d  mov     edi, 7FFFh
0x140090f22  movups  [rbp+190h+var_1D0], xmm0
0x140090f26  test    rcx, rcx
0x140090f29  jz      short loc_140090F7D
0x140090f2b  mov     edx, edi
0x140090f2d  mov     rax, rcx
0x140090f30  cmp     [rax], r12w
0x140090f34  jz      short loc_140090F81
0x140090f36  add     rax, r13
0x140090f39  sub     rdx, 1
0x140090f3d  jnz     short loc_140090F30
0x140090f3f  mov     r8d, 0C000000Dh
0x140090f45  mov     ebx, r8d
0x140090f48  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090f4f  lea     rax, WPP_GLOBAL_Control
0x140090f56  cmp     rcx, rax
0x140090f59  jz      loc_140091298
0x140090f5f  test    byte ptr [rcx+44h], 8
0x140090f63  jz      loc_140091298
0x140090f69  cmp     [rcx+41h], r13b
0x140090f6d  jb      loc_140091298
0x140090f73  mov     edx, 2Dh ; '-'
0x140090f78  jmp     loc_140090EBA
0x140090f7d  mov     rcx, qword ptr [rbp+190h+var_1D0+8]
0x140090f81  xor     r9d, r9d
0x140090f84  lea     rdx, [rsp+290h+DestinationString]
0x140090f89  xor     r8d, r8d
0x140090f8c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x140090f92  mov     ebx, eax
0x140090f94  test    eax, eax
0x140090f96  jns     short loc_140090FD0
0x140090f98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140090f9f  lea     rax, WPP_GLOBAL_Control
0x140090fa6  cmp     rcx, rax
0x140090fa9  jz      loc_140091298
0x140090faf  test    byte ptr [rcx+44h], 8
0x140090fb3  jz      loc_140091298
0x140090fb9  cmp     [rcx+41h], r13b
0x140090fbd  jb      loc_140091298
0x140090fc3  mov     edx, 2Eh ; '.'
0x140090fc8  mov     r9d, ebx
0x140090fcb  jmp     loc_140090EBD
0x140090fd0  xorps   xmm0, xmm0
0x140090fd3  movups  [rbp+190h+var_210], xmm0
0x140090fd7  test    r14, r14
0x140090fda  jz      short loc_140091022
0x140090fdc  mov     rax, r14
0x140090fdf  cmp     [rax], r12w
0x140090fe3  jz      short loc_140090FEE
0x140090fe5  add     rax, r13
0x140090fe8  sub     rdi, 1
0x140090fec  jnz     short loc_140090FDF
0x140090fee  mov     rax, rdi
0x140090ff1  neg     rax
0x140090ff4  sbb     ebx, ebx
0x140090ff6  not     ebx
0x140090ff8  and     ebx, 0C000000Dh
0x140090ffe  test    rdi, rdi
0x140091001  jz      loc_1400910BF
0x140091007  add     di, di
0x14009100a  mov     qword ptr [rbp+190h+var_210+8], r14
0x14009100e  mov     eax, 0FFFEh
0x140091013  sub     ax, di
0x140091016  mov     word ptr [rbp+190h+var_210], ax
0x14009101a  add     ax, r13w
0x14009101e  mov     word ptr [rbp+190h+var_210+2], ax
0x140091022  mov     rax, gs:60h
0x14009102b  lea     rdx, [rsp+290h+DestinationString]
0x140091030  mov     r14d, 1
0x140091036  lea     rcx, [rsp+290h+var_228]
0x14009103b  mov     dword ptr [rsp+290h+var_240], r14d
0x140091040  xor     r9d, r9d
0x140091043  mov     [rsp+290h+var_248], r12
0x140091048  xor     r8d, r8d
0x14009104b  mov     rdi, [rax+20h]
0x14009104f  lea     rax, [rbp+190h+var_210]
0x140091053  mov     [rsp+290h+var_250], r12
0x140091058  mov     [rsp+290h+var_258], r12
0x14009105d  mov     [rsp+290h+var_260], r12
0x140091062  mov     [rsp+290h+var_268], r12
0x140091067  mov     [rsp+290h+var_270], rax
0x14009106c  call    cs:__imp_RtlCreateProcessParametersEx
0x140091072  mov     ebx, eax
0x140091074  test    eax, eax
0x140091076  jns     short loc_1400910F4
0x140091078  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009107f  lea     rax, WPP_GLOBAL_Control
0x140091086  cmp     rcx, rax
0x140091089  jz      loc_1400912D7
0x14009108f  test    byte ptr [rcx+44h], 8
0x140091093  jz      loc_1400912D7
0x140091099  cmp     [rcx+41h], r13b
0x14009109d  jb      loc_1400912D7
0x1400910a3  mov     rcx, [rcx+38h]
0x1400910a7  lea     edx, [r14+2Fh]
0x1400910ab  mov     r9d, ebx
0x1400910ae  lea     r8, WPP_9e86a345ea7c3fd289cca579774c5c03_Traceguids
0x1400910b5  call    WPP_SF_d
0x1400910ba  jmp     loc_1400912D7
0x1400910bf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400910c6  lea     rax, WPP_GLOBAL_Control
0x1400910cd  cmp     rcx, rax
0x1400910d0  jz      loc_140091298
0x1400910d6  test    byte ptr [rcx+44h], 8
0x1400910da  jz      loc_140091298
0x1400910e0  cmp     [rcx+41h], r13b
0x1400910e4  jb      loc_140091298
0x1400910ea  mov     edx, 2Fh ; '/'
0x1400910ef  jmp     loc_140090FC8
0x1400910f4  mov     ecx, [rdi+408h]
0x1400910fa  mov     ebx, 58h ; 'X'
0x1400910ff  mov     rax, [rsp+290h+var_228]
0x140091104  mov     r8d, ebx; Size
0x140091107  xor     edx, edx; Val
0x140091109  mov     [rax+408h], ecx
0x14009110f  lea     rcx, [rbp+190h+var_150]; void *
0x140091113  call    memset
0x140091118  lea     rax, [rbp+190h+var_1A8]
0x14009111c  mov     [rbp+190h+var_150], rbx
0x140091120  mov     [rbp+190h+var_D8], rax
0x140091127  lea     rdx, [rbp+190h+Handle]
0x14009112b  movzx   eax, [rsp+290h+DestinationString.Length]
0x140091130  lea     rcx, [rbp+190h+Process]
0x140091134  mov     [rbp+190h+var_C0], rax
0x14009113b  mov     r8d, 2000000h
0x140091141  mov     rax, [rsp+290h+DestinationString.Buffer]
0x140091146  mov     r9d, r8d
0x140091149  mov     [rbp+190h+var_B8], rax
0x140091150  mov     rax, [rbp+190h+arg_20]
0x140091157  mov     [rbp+190h+var_78], rax
0x14009115e  lea     rax, [rsp+290h+var_230]
0x140091163  mov     [rbp+190h+var_58], rax
0x14009116a  lea     rax, [rbp+190h+var_F0]
0x140091171  mov     [rsp+290h+var_240], rax
0x140091176  lea     rax, [rbp+190h+var_150]
0x14009117a  mov     [rsp+290h+var_248], rax
0x14009117f  mov     rax, [rsp+290h+var_228]
0x140091184  mov     [rsp+290h+var_250], rax
0x140091189  lea     rax, [rbp+190h+var_200]
0x14009118d  mov     dword ptr [rsp+290h+var_258], r12d
0x140091192  mov     dword ptr [rsp+290h+var_260], 100h
0x14009119a  mov     [rsp+290h+var_268], r12
0x14009119f  mov     [rsp+290h+var_270], rax
0x1400911a4  mov     [rbp+190h+var_140], 4
0x1400911a8  mov     [rbp+190h+var_E8], 10003h
0x1400911b3  mov     [rbp+190h+var_E0], 10h
0x1400911be  mov     [rbp+190h+var_D0], r12
0x1400911c5  mov     [rbp+190h+var_C8], 20005h
0x1400911d0  mov     [rbp+190h+var_B0], r12
0x1400911d7  mov     [rbp+190h+var_A8], 20012h
0x1400911e2  mov     [rbp+190h+var_A0], 8
0x1400911ed  mov     [rbp+190h+var_90], r12
0x1400911f4  mov     [rbp+190h+var_98], r15
0x1400911fb  mov     [rbp+190h+var_88], 60002h
0x140091206  mov     [rbp+190h+var_80], 8
0x140091211  mov     [rbp+190h+var_70], r12
0x140091218  mov     [rbp+190h+var_68], 20008h
0x140091223  mov     [rbp+190h+var_60], r14
0x14009122a  mov     [rbp+190h+var_50], r12
0x140091231  mov     [rbp+190h+var_F0], 0A8h
0x14009123c  call    cs:__imp_NtCreateUserProcess
0x140091242  mov     ebx, eax
0x140091244  test    eax, eax
0x140091246  jns     short loc_140091271
0x140091248  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14009124f  lea     rax, WPP_GLOBAL_Control
0x140091256  cmp     rcx, rax
0x140091259  jz      short loc_140091298
0x14009125b  test    byte ptr [rcx+44h], 8
0x14009125f  jz      short loc_140091298
0x140091261  cmp     [rcx+41h], r13b
0x140091265  jb      short loc_140091298
0x140091267  mov     edx, 31h ; '1'
0x14009126c  jmp     loc_140090FC8
0x140091271  mov     rcx, [rbp+190h+Process]; Process
0x140091275  mov     rax, [rbp+190h+Handle]
0x140091279  mov     [rsi+78h], rcx
0x14009127d  mov     [rsi+80h], rax
0x140091284  mov     [rbp+190h+Process], r12
0x140091288  mov     [rbp+190h+Handle], r12
0x14009128c  call    cs:__imp_GetProcessId
0x140091292  mov     [rsi+88h], eax
0x140091298  cmp     [rsp+290h+DestinationString.Buffer], r12
0x14009129d  jz      short loc_1400912B9
0x14009129f  mov     rcx, gs:60h
0x1400912a8  xor     edx, edx; Flags
0x1400912aa  mov     r8, [rsp+290h+DestinationString.Buffer]; P
0x1400912af  mov     rcx, [rcx+30h]; HeapHandle
0x1400912b3  call    cs:__imp_RtlFreeHeap
0x1400912b9  mov     rcx, [rbp+190h+Process]; Handle
0x1400912bd  test    rcx, rcx
0x1400912c0  jz      short loc_1400912C8
0x1400912c2  call    cs:__imp_NtClose
0x1400912c8  mov     rcx, [rbp+190h+Handle]; Handle
0x1400912cc  test    rcx, rcx
0x1400912cf  jz      short loc_1400912D7
0x1400912d1  call    cs:__imp_NtClose
0x1400912d7  mov     eax, ebx
0x1400912d9  mov     rcx, [rbp+190h+var_40]
0x1400912e0  xor     rcx, rsp; StackCookie
0x1400912e3  call    __security_check_cookie
0x1400912e8  mov     rbx, [rsp+290h+arg_8]
0x1400912f0  add     rsp, 260h
0x1400912f7  pop     r15
0x1400912f9  pop     r14
0x1400912fb  pop     r13
0x1400912fd  pop     r12
0x1400912ff  pop     rdi
0x140091300  pop     rsi
0x140091301  pop     rbp
0x140091302  retn
```

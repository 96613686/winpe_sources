# UbpmRunConsumerActions

- ea: `0x18000dda4`
- end: `0x18000e09f`
- name: `UbpmRunConsumerActions`
- size: `763`
- prototype: `__int64 __usercall@<rax>(struct _UBPM_TRIGGER_CONSUMER_BLOCK *@<rcx>, int, unsigned __int64, unsigned int, unsigned int, __int64, struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000f880`
- `0x180028b20`
- `0x18002c950`

## callees

- `0x18000d0d0`
- `0x18000dda4`
- `0x18000fbf0`
- `0x1800103c0`
- `0x1800150c0`
- `0x18001af64`
- `0x180037e9c`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000df1e`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000df1e`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000de95`
- `ntdll!RtlAcquireSRWLockShared` at `0x18000de95`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000df0e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000df0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e004`
- `RPCRT4!UuidCreate` at `0x18000de79`
- `RPCRT4!UuidCreate` at `0x18000de79`

## pseudocode

```c
__int64 __fastcall UbpmRunConsumerActions(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        struct _GUID *a4,
        int a5,
        unsigned __int64 a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int8 *a9,
        struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *a10,
        _QWORD *a11)
{
  struct _GUID *v12; // rcx
  _QWORD *v14; // r14
  int v15; // ebx
  unsigned __int64 v16; // rax
  _QWORD *v17; // rax
  struct _GUID *v18; // rbp
  DWORD LastError; // esi
  unsigned int v20; // eax
  _QWORD *v22; // r10
  int v23; // edx
  _QWORD *v24; // rcx
  int v25; // edx
  unsigned int v26; // [rsp+60h] [rbp-88h] BYREF
  int v27; // [rsp+64h] [rbp-84h] BYREF
  unsigned __int8 *v28; // [rsp+68h] [rbp-80h]
  unsigned __int64 v29; // [rsp+70h] [rbp-78h]
  unsigned __int64 v30; // [rsp+78h] [rbp-70h]
  __int128 v31; // [rsp+80h] [rbp-68h] BYREF

  v12 = (struct _GUID *)(*((_QWORD *)a1 + 3) + 84LL);
  v28 = a9;
  v27 = 0;
  v31 = 0;
  v14 = 0;
  v29 = a3;
  v15 = 0;
  v30 = a2;
  v26 = 0;
  v16 = -*(_QWORD *)&v12->Data1;
  if ( !*(_QWORD *)&v12->Data1 )
    v16 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] - *(_QWORD *)v12->Data4;
  if ( v16 && (int)UbpmUtilIsNetworkConnected(v12, &v26) >= 0 )
    LOBYTE(v15) = v26 != 0;
  v27 = v15;
  if ( a10 )
  {
    if ( !*((_BYTE *)a10 + 40) || *((_QWORD *)a10 + 6) )
    {
      if ( !*((_BYTE *)a10 + 56) || *((_QWORD *)a10 + 8) )
        goto LABEL_5;
      LastError = 87;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v23 = 25;
    }
    else
    {
      LastError = 87;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v23 = 24;
    }
    WPP_SF_Sd(
      v22[2],
      v23,
      (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
      87);
    goto LABEL_11;
  }
LABEL_5:
  if ( a11 )
  {
    v17 = UbpmAlloc(0x18u);
    v14 = v17;
    if ( !v17 )
    {
      LastError = GetLastError();
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_11;
      v25 = 26;
LABEL_30:
      WPP_SF_Sd(
        v24[2],
        v25,
        (unsigned int)WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids,
        *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
        LastError);
      goto LABEL_11;
    }
    v18 = (struct _GUID *)(v17 + 1);
    *v17 = v17 + 1;
  }
  else
  {
    v18 = (struct _GUID *)&v31;
  }
  if ( a4 )
  {
    v18 = a4;
    goto LABEL_10;
  }
  LastError = UuidCreate(v18);
  if ( LastError )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_11;
    v25 = 27;
    goto LABEL_30;
  }
LABEL_10:
  RtlAcquireSRWLockShared((char *)a1 + 48);
  UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_TRIGGER_CONSUMER_BLOCK *)((char *)a1 + 208));
  v20 = UbpmpRunConsumerActions(
          a1,
          (struct _UBPM_CONSTRAINT_PRECHECK_INFO *)&v27,
          v30,
          v29,
          v18,
          0,
          a6,
          a7,
          a8,
          v28,
          a10);
  *((_DWORD *)a1 + 54) = 0;
  LastError = v20;
  RtlReleaseSRWLockExclusive((char *)a1 + 208);
  RtlReleaseSRWLockShared((char *)a1 + 48);
  if ( !LastError && a11 )
  {
    *a11 = v14;
    v14 = 0;
  }
LABEL_11:
  UBPM_MIDL_user_free(v14, a2, a3, a4);
  return LastError;
}

```

## disassembly

```asm
0x18000dda4  push    rbx
0x18000dda6  push    rbp
0x18000dda7  push    rsi
0x18000dda8  push    rdi
0x18000dda9  push    r12
0x18000ddab  push    r13
0x18000ddad  push    r14
0x18000ddaf  push    r15
0x18000ddb1  sub     rsp, 0A8h
0x18000ddb8  mov     rax, cs:__security_cookie
0x18000ddbf  xor     rax, rsp
0x18000ddc2  mov     [rsp+0E8h+var_58], rax
0x18000ddca  mov     rax, [rsp+0E8h+arg_40]
0x18000ddd2  xor     esi, esi
0x18000ddd4  mov     r15, [rsp+0E8h+arg_48]
0x18000dddc  mov     r13, rcx
0x18000dddf  mov     rcx, [rcx+18h]
0x18000dde3  xorps   xmm0, xmm0
0x18000dde6  mov     r12, [rsp+0E8h+arg_50]
0x18000ddee  add     rcx, 54h ; 'T'; struct _GUID *
0x18000ddf2  mov     [rsp+0E8h+var_80], rax
0x18000ddf7  mov     rdi, r9
0x18000ddfa  movq    rax, xmm0
0x18000ddff  mov     [rsp+0E8h+var_84], esi
0x18000de03  movups  [rsp+0E8h+var_68], xmm0
0x18000de0b  mov     r14d, esi
0x18000de0e  mov     [rsp+0E8h+var_78], r8
0x18000de13  mov     ebx, esi
0x18000de15  mov     [rsp+0E8h+var_70], rdx
0x18000de1a  mov     [rsp+0E8h+var_88], esi
0x18000de1e  sub     rax, [rcx]
0x18000de21  jnz     short loc_18000DE31
0x18000de23  psrldq  xmm0, 8
0x18000de28  movq    rax, xmm0
0x18000de2d  sub     rax, [rcx+8]
0x18000de31  test    rax, rax
0x18000de34  jnz     loc_18000E059
0x18000de3a  mov     [rsp+0E8h+var_84], ebx
0x18000de3e  test    r15, r15
0x18000de41  jnz     loc_18000DF80
0x18000de47  test    r12, r12
0x18000de4a  jz      loc_18000DF73
0x18000de50  mov     ecx, 18h; Size
0x18000de55  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18000de5a  mov     r14, rax
0x18000de5d  test    rax, rax
0x18000de60  jz      loc_18000E004
0x18000de66  lea     rbp, [rax+8]
0x18000de6a  mov     [rax], rbp
0x18000de6d  test    rdi, rdi
0x18000de70  jnz     loc_18000DF6B
0x18000de76  mov     rcx, rbp; Uuid
0x18000de79  call    cs:__imp_UuidCreate
0x18000de80  nop     dword ptr [rax+rax+00h]
0x18000de85  mov     esi, eax
0x18000de87  test    eax, eax
0x18000de89  jnz     loc_18000E077
0x18000de8f  xor     esi, esi
0x18000de91  lea     rcx, [r13+30h]
0x18000de95  call    cs:__imp_RtlAcquireSRWLockShared
0x18000de9c  nop     dword ptr [rax+rax+00h]
0x18000dea1  lea     rbx, [r13+0D0h]
0x18000dea8  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18000deab  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18000deb0  mov     rax, [rsp+0E8h+var_80]
0x18000deb5  lea     rdx, [rsp+0E8h+var_84]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18000deba  mov     r9, [rsp+0E8h+var_78]; unsigned __int64
0x18000debf  mov     rcx, r13; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x18000dec2  mov     r8, [rsp+0E8h+var_70]; unsigned __int64
0x18000dec7  mov     [rsp+0E8h+var_98], r15; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x18000decc  mov     [rsp+0E8h+var_A0], rax; unsigned __int8 *
0x18000ded1  mov     eax, [rsp+0E8h+arg_38]
0x18000ded8  mov     [rsp+0E8h+var_A8], eax; unsigned int
0x18000dedc  mov     eax, [rsp+0E8h+arg_30]
0x18000dee3  mov     [rsp+0E8h+var_B0], eax; unsigned int
0x18000dee7  mov     rax, [rsp+0E8h+arg_28]
0x18000deef  mov     [rsp+0E8h+var_B8], rax; unsigned __int64
0x18000def4  mov     [rsp+0E8h+var_C0], esi; unsigned int
0x18000def8  mov     [rsp+0E8h+var_C8], rbp; struct _GUID *
0x18000defd  call    ?UbpmpRunConsumerActions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@_K2PEAU_GUID@@K2KKPEAEPEAU_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1@@@Z; UbpmpRunConsumerActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,unsigned __int64,unsigned __int64,_GUID *,ulong,unsigned __int64,ulong,ulong,uchar *,_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)
0x18000df02  mov     rcx, rbx
0x18000df05  mov     dword ptr [rbx+8], 0
0x18000df0c  mov     esi, eax
0x18000df0e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000df15  nop     dword ptr [rax+rax+00h]
0x18000df1a  lea     rcx, [r13+30h]
0x18000df1e  call    cs:__imp_RtlReleaseSRWLockShared
0x18000df25  nop     dword ptr [rax+rax+00h]
0x18000df2a  test    esi, esi
0x18000df2c  jz      short loc_18000DF5D
0x18000df2e  mov     rcx, r14
0x18000df31  call    UBPM_MIDL_user_free
0x18000df36  mov     eax, esi
0x18000df38  mov     rcx, [rsp+0E8h+var_58]
0x18000df40  xor     rcx, rsp; StackCookie
0x18000df43  call    __security_check_cookie
0x18000df48  add     rsp, 0A8h
0x18000df4f  pop     r15
0x18000df51  pop     r14
0x18000df53  pop     r13
0x18000df55  pop     r12
0x18000df57  pop     rdi
0x18000df58  pop     rsi
0x18000df59  pop     rbp
0x18000df5a  pop     rbx
0x18000df5b  retn
0x18000df5d  test    r12, r12
0x18000df60  jz      short loc_18000DF2E
0x18000df62  mov     [r12], r14
0x18000df66  xor     r14d, r14d
0x18000df69  jmp     short loc_18000DF2E
0x18000df6b  mov     rbp, rdi
0x18000df6e  jmp     loc_18000DE91
0x18000df73  lea     rbp, [rsp+0E8h+var_68]
0x18000df7b  jmp     loc_18000DE6D
0x18000df80  cmp     [r15+28h], sil
0x18000df84  jnz     short loc_18000DFD0
0x18000df86  cmp     [r15+38h], sil
0x18000df8a  jz      loc_18000DE47
0x18000df90  cmp     [r15+40h], rsi
0x18000df94  jnz     loc_18000DE47
0x18000df9a  mov     ecx, 57h ; 'W'
0x18000df9f  mov     esi, ecx
0x18000dfa1  mov     r10, cs:WPP_GLOBAL_Control
0x18000dfa8  lea     rax, WPP_GLOBAL_Control
0x18000dfaf  cmp     r10, rax
0x18000dfb2  jz      loc_18000DF2E
0x18000dfb8  test    byte ptr [r10+1Ch], 1
0x18000dfbd  jz      loc_18000DF2E
0x18000dfc3  lea     edx, [rcx-3Eh]
0x18000dfc6  mov     dword ptr [rsp+0E8h+var_C8], ecx
0x18000dfca  mov     rcx, [r10+10h]
0x18000dfce  jmp     short loc_18000E040
0x18000dfd0  cmp     [r15+30h], rsi
0x18000dfd4  jnz     short loc_18000DF86
0x18000dfd6  mov     ecx, 57h ; 'W'
0x18000dfdb  mov     esi, ecx
0x18000dfdd  mov     r10, cs:WPP_GLOBAL_Control
0x18000dfe4  lea     rax, WPP_GLOBAL_Control
0x18000dfeb  cmp     r10, rax
0x18000dfee  jz      loc_18000DF2E
0x18000dff4  test    byte ptr [r10+1Ch], 1
0x18000dff9  jz      loc_18000DF2E
0x18000dfff  lea     edx, [rcx-3Fh]
0x18000e002  jmp     short loc_18000DFC6
0x18000e004  call    cs:__imp_GetLastError
0x18000e00b  nop     dword ptr [rax+rax+00h]
0x18000e010  mov     esi, eax
0x18000e012  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e019  lea     rax, WPP_GLOBAL_Control
0x18000e020  cmp     rcx, rax
0x18000e023  jz      loc_18000DF2E
0x18000e029  test    byte ptr [rcx+1Ch], 1
0x18000e02d  jz      loc_18000DF2E
0x18000e033  mov     edx, 1Ah
0x18000e038  mov     rcx, [rcx+10h]
0x18000e03c  mov     dword ptr [rsp+0E8h+var_C8], esi
0x18000e040  mov     r9, [r13+18h]
0x18000e044  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x18000e04b  mov     r9, [r9+8]
0x18000e04f  call    WPP_SF_Sd
0x18000e054  jmp     loc_18000DF2E
0x18000e059  lea     rdx, [rsp+0E8h+var_88]; unsigned int *
0x18000e05e  call    ?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z; UbpmUtilIsNetworkConnected(_GUID *,ulong *)
0x18000e063  test    eax, eax
0x18000e065  js      loc_18000DE3A
0x18000e06b  cmp     [rsp+0E8h+var_88], esi
0x18000e06f  setnz   bl
0x18000e072  jmp     loc_18000DE3A
0x18000e077  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e07e  lea     rax, WPP_GLOBAL_Control
0x18000e085  cmp     rcx, rax
0x18000e088  jz      loc_18000DF2E
0x18000e08e  test    byte ptr [rcx+1Ch], 1
0x18000e092  jz      loc_18000DF2E
0x18000e098  mov     edx, 1Bh
0x18000e09d  jmp     short loc_18000E038
```

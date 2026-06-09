# UbpmRunConsumerActions

- ea: `0x180018254`
- end: `0x180018530`
- name: `UbpmRunConsumerActions`
- size: `732`
- prototype: `__int64 __usercall@<rax>(struct _UBPM_TRIGGER_CONSUMER_BLOCK *@<rcx>, int, unsigned __int64, unsigned int, unsigned int, __int64, struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *, __int64)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800179d0`
- `0x180019a30`
- `0x18002acb0`

## callees

- `0x18000a6e0`
- `0x18000f9a0`
- `0x180018254`
- `0x180019d90`
- `0x18001c400`
- `0x18001e9f4`
- `0x180035944`
- `0x18003d810`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800183bc`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800183bc`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001833f`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001833f`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800183b2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800183b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001849b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001849b`
- `RPCRT4!UuidCreate` at `0x180018329`
- `RPCRT4!UuidCreate` at `0x180018329`

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
  UBPM_MIDL_user_free(v14);
  return LastError;
}

```

## disassembly

```asm
0x180018254  push    rbx
0x180018256  push    rbp
0x180018257  push    rsi
0x180018258  push    rdi
0x180018259  push    r12
0x18001825b  push    r13
0x18001825d  push    r14
0x18001825f  push    r15
0x180018261  sub     rsp, 0A8h
0x180018268  mov     rax, cs:__security_cookie
0x18001826f  xor     rax, rsp
0x180018272  mov     [rsp+0E8h+var_58], rax
0x18001827a  mov     rax, [rsp+0E8h+arg_40]
0x180018282  xor     esi, esi
0x180018284  mov     r15, [rsp+0E8h+arg_48]
0x18001828c  mov     r13, rcx
0x18001828f  mov     rcx, [rcx+18h]
0x180018293  xorps   xmm0, xmm0
0x180018296  mov     r12, [rsp+0E8h+arg_50]
0x18001829e  add     rcx, 54h ; 'T'; struct _GUID *
0x1800182a2  mov     [rsp+0E8h+var_80], rax
0x1800182a7  mov     rdi, r9
0x1800182aa  movq    rax, xmm0
0x1800182af  mov     [rsp+0E8h+var_84], esi
0x1800182b3  movups  [rsp+0E8h+var_68], xmm0
0x1800182bb  mov     r14d, esi
0x1800182be  mov     [rsp+0E8h+var_78], r8
0x1800182c3  mov     ebx, esi
0x1800182c5  mov     [rsp+0E8h+var_70], rdx
0x1800182ca  mov     [rsp+0E8h+var_88], esi
0x1800182ce  sub     rax, [rcx]
0x1800182d1  jnz     short loc_1800182E1
0x1800182d3  psrldq  xmm0, 8
0x1800182d8  movq    rax, xmm0
0x1800182dd  sub     rax, [rcx+8]
0x1800182e1  test    rax, rax
0x1800182e4  jnz     loc_1800184EA
0x1800182ea  mov     [rsp+0E8h+var_84], ebx
0x1800182ee  test    r15, r15
0x1800182f1  jnz     loc_180018417
0x1800182f7  test    r12, r12
0x1800182fa  jz      loc_18001840A
0x180018300  mov     ecx, 18h; Size
0x180018305  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18001830a  mov     r14, rax
0x18001830d  test    rax, rax
0x180018310  jz      loc_18001849B
0x180018316  lea     rbp, [rax+8]
0x18001831a  mov     [rax], rbp
0x18001831d  test    rdi, rdi
0x180018320  jnz     loc_180018402
0x180018326  mov     rcx, rbp; Uuid
0x180018329  call    cs:__imp_UuidCreate
0x18001832f  mov     esi, eax
0x180018331  test    eax, eax
0x180018333  jnz     loc_180018508
0x180018339  xor     esi, esi
0x18001833b  lea     rcx, [r13+30h]
0x18001833f  call    cs:__imp_RtlAcquireSRWLockShared
0x180018345  lea     rbx, [r13+0D0h]
0x18001834c  mov     rcx, rbx; struct _UBPM_SRWLOCK *
0x18001834f  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x180018354  mov     rax, [rsp+0E8h+var_80]
0x180018359  lea     rdx, [rsp+0E8h+var_84]; struct _UBPM_CONSTRAINT_PRECHECK_INFO *
0x18001835e  mov     r9, [rsp+0E8h+var_78]; unsigned __int64
0x180018363  mov     rcx, r13; struct _UBPM_TRIGGER_CONSUMER_BLOCK *
0x180018366  mov     r8, [rsp+0E8h+var_70]; unsigned __int64
0x18001836b  mov     [rsp+0E8h+var_98], r15; struct _UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *
0x180018370  mov     [rsp+0E8h+var_A0], rax; unsigned __int8 *
0x180018375  mov     eax, [rsp+0E8h+arg_38]
0x18001837c  mov     [rsp+0E8h+var_A8], eax; unsigned int
0x180018380  mov     eax, [rsp+0E8h+arg_30]
0x180018387  mov     [rsp+0E8h+var_B0], eax; unsigned int
0x18001838b  mov     rax, [rsp+0E8h+arg_28]
0x180018393  mov     [rsp+0E8h+var_B8], rax; unsigned __int64
0x180018398  mov     [rsp+0E8h+var_C0], esi; unsigned int
0x18001839c  mov     [rsp+0E8h+var_C8], rbp; struct _GUID *
0x1800183a1  call    ?UbpmpRunConsumerActions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_UBPM_CONSTRAINT_PRECHECK_INFO@@_K2PEAU_GUID@@K2KKPEAEPEAU_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1@@@Z; UbpmpRunConsumerActions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_UBPM_CONSTRAINT_PRECHECK_INFO *,unsigned __int64,unsigned __int64,_GUID *,ulong,unsigned __int64,ulong,ulong,uchar *,_UBPM_TRIGGER_CONSUMER_CONTROL_INFO_IN_1 *)
0x1800183a6  mov     rcx, rbx
0x1800183a9  mov     dword ptr [rbx+8], 0
0x1800183b0  mov     esi, eax
0x1800183b2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800183b8  lea     rcx, [r13+30h]
0x1800183bc  call    cs:__imp_RtlReleaseSRWLockShared
0x1800183c2  test    esi, esi
0x1800183c4  jz      short loc_1800183F4
0x1800183c6  mov     rcx, r14
0x1800183c9  call    UBPM_MIDL_user_free
0x1800183ce  mov     eax, esi
0x1800183d0  mov     rcx, [rsp+0E8h+var_58]
0x1800183d8  xor     rcx, rsp; StackCookie
0x1800183db  call    __security_check_cookie
0x1800183e0  add     rsp, 0A8h
0x1800183e7  pop     r15
0x1800183e9  pop     r14
0x1800183eb  pop     r13
0x1800183ed  pop     r12
0x1800183ef  pop     rdi
0x1800183f0  pop     rsi
0x1800183f1  pop     rbp
0x1800183f2  pop     rbx
0x1800183f3  retn
0x1800183f4  test    r12, r12
0x1800183f7  jz      short loc_1800183C6
0x1800183f9  mov     [r12], r14
0x1800183fd  xor     r14d, r14d
0x180018400  jmp     short loc_1800183C6
0x180018402  mov     rbp, rdi
0x180018405  jmp     loc_18001833B
0x18001840a  lea     rbp, [rsp+0E8h+var_68]
0x180018412  jmp     loc_18001831D
0x180018417  cmp     [r15+28h], sil
0x18001841b  jnz     short loc_180018467
0x18001841d  cmp     [r15+38h], sil
0x180018421  jz      loc_1800182F7
0x180018427  cmp     [r15+40h], rsi
0x18001842b  jnz     loc_1800182F7
0x180018431  mov     ecx, 57h ; 'W'
0x180018436  mov     esi, ecx
0x180018438  mov     r10, cs:WPP_GLOBAL_Control
0x18001843f  lea     rax, WPP_GLOBAL_Control
0x180018446  cmp     r10, rax
0x180018449  jz      loc_1800183C6
0x18001844f  test    byte ptr [r10+1Ch], 1
0x180018454  jz      loc_1800183C6
0x18001845a  lea     edx, [rcx-3Eh]
0x18001845d  mov     dword ptr [rsp+0E8h+var_C8], ecx
0x180018461  mov     rcx, [r10+10h]
0x180018465  jmp     short loc_1800184D1
0x180018467  cmp     [r15+30h], rsi
0x18001846b  jnz     short loc_18001841D
0x18001846d  mov     ecx, 57h ; 'W'
0x180018472  mov     esi, ecx
0x180018474  mov     r10, cs:WPP_GLOBAL_Control
0x18001847b  lea     rax, WPP_GLOBAL_Control
0x180018482  cmp     r10, rax
0x180018485  jz      loc_1800183C6
0x18001848b  test    byte ptr [r10+1Ch], 1
0x180018490  jz      loc_1800183C6
0x180018496  lea     edx, [rcx-3Fh]
0x180018499  jmp     short loc_18001845D
0x18001849b  call    cs:__imp_GetLastError
0x1800184a1  mov     esi, eax
0x1800184a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184aa  lea     rax, WPP_GLOBAL_Control
0x1800184b1  cmp     rcx, rax
0x1800184b4  jz      loc_1800183C6
0x1800184ba  test    byte ptr [rcx+1Ch], 1
0x1800184be  jz      loc_1800183C6
0x1800184c4  mov     edx, 1Ah
0x1800184c9  mov     rcx, [rcx+10h]
0x1800184cd  mov     dword ptr [rsp+0E8h+var_C8], esi
0x1800184d1  mov     r9, [r13+18h]
0x1800184d5  lea     r8, WPP_dcdc688f20ff37c56e3e77310b95cc70_Traceguids
0x1800184dc  mov     r9, [r9+8]
0x1800184e0  call    WPP_SF_Sd
0x1800184e5  jmp     loc_1800183C6
0x1800184ea  lea     rdx, [rsp+0E8h+var_88]; unsigned int *
0x1800184ef  call    ?UbpmUtilIsNetworkConnected@@YAJPEAU_GUID@@PEAK@Z; UbpmUtilIsNetworkConnected(_GUID *,ulong *)
0x1800184f4  test    eax, eax
0x1800184f6  js      loc_1800182EA
0x1800184fc  cmp     [rsp+0E8h+var_88], esi
0x180018500  setnz   bl
0x180018503  jmp     loc_1800182EA
0x180018508  mov     rcx, cs:WPP_GLOBAL_Control
0x18001850f  lea     rax, WPP_GLOBAL_Control
0x180018516  cmp     rcx, rax
0x180018519  jz      loc_1800183C6
0x18001851f  test    byte ptr [rcx+1Ch], 1
0x180018523  jz      loc_1800183C6
0x180018529  mov     edx, 1Bh
0x18001852e  jmp     short loc_1800184C9
```

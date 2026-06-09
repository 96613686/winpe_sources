# CPicturePasswordVault::GetEnrollment(void *,ushort * *,GESTURE_SIGNATURE * *,unsigned __int64 *)

- ea: `0x180018f10`
- end: `0x1800191be`
- name: `?GetEnrollment@CPicturePasswordVault@@SAJPEAXPEAPEAGPEAPEAUGESTURE_SIGNATURE@@PEA_K@Z`
- size: `686`
- prototype: `__int64 __fastcall(PSID pSid, unsigned __int16 **, struct GESTURE_SIGNATURE **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006f80`

## callees

- `0x180002610`
- `0x180005a2c`
- `0x18000a0e4`
- `0x18000a218`
- `0x180015b00`
- `0x180018d64`
- `0x180018f10`
- `0x1800191c4`
- `0x180019610`
- `0x18001a880`
- `0x18001e3a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018fbd`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180018fbd`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x180018ff5`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultGetItem` at `0x180018ff5`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x180019196`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultCloseVault` at `0x180019196`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18001918c`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultFree` at `0x18001918c`

## pseudocode

```c
__int64 __fastcall CPicturePasswordVault::GetEnrollment(
        PSID pSid,
        unsigned __int16 **a2,
        struct GESTURE_SIGNATURE **a3,
        unsigned __int64 *a4)
{
  signed int v7; // ebx
  int Item; // eax
  __int64 v9; // rbx
  const unsigned __int16 *v10; // r15
  unsigned __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r14
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // r9
  unsigned __int16 *v18; // rdi
  __int64 v19; // rsi
  unsigned __int64 v20; // rcx
  __int64 i; // rax
  unsigned __int16 *v23; // [rsp+48h] [rbp-61h] BYREF
  void *v24; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 *v25; // [rsp+58h] [rbp-51h]
  __int128 v26; // [rsp+60h] [rbp-49h] BYREF
  __int128 v27; // [rsp+70h] [rbp-39h]
  _QWORD v28[4]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-9h] BYREF

  v25 = a4;
  if ( a2 )
    *a2 = 0;
  *a3 = 0;
  if ( (unsigned int)CPicturePasswordVault::GetEnrollmentStatus(pSid) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v24 = 0;
  v7 = _OpenPicturePasswordVault(&v24);
  if ( v7 >= 0 )
  {
    v28[0] = 1;
    v28[1] = 7;
    v29 = c_guidPicturePasswordVaultSchema;
    v28[3] = 0;
    v28[2] = L"Picture Password Vault Resource";
    v26 = 0;
    LODWORD(v26) = 2;
    DWORD2(v26) = 8;
    v27 = 0;
    LODWORD(v27) = GetLengthSid(pSid);
    *((_QWORD *)&v27 + 1) = pSid;
    Item = VaultGetItem(v24, &v29, v28, &v26);
    v7 = Item;
    if ( Item > 0 )
      v7 = (unsigned __int16)Item | 0x80070000;
    if ( v7 >= 0 )
    {
      v9 = MEMORY[0x28];
      if ( *(_DWORD *)(MEMORY[0x28] + 8LL) != 8 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v10 = *(const unsigned __int16 **)(v9 + 24);
      v11 = (unsigned __int64)*(unsigned int *)(v9 + 16) >> 1;
      v23 = 0;
      v7 = StringCchLengthW(v10, v11, (unsigned __int64 *)&v23);
      if ( v7 >= 0 )
      {
        v14 = -1;
        v15 = -1;
        do
          ++v15;
        while ( v10[v15] );
        v23 = 0;
        v16 = v15 + 1;
        if ( v15 + 1 < v15 )
        {
          v7 = -2147024362;
        }
        else
        {
          v7 = _AllocArray<unsigned short,CTLocalAllocPolicy>(v13, v12, v15 + 1, &v23);
          if ( v7 >= 0 )
          {
            v17 = v15;
            v18 = v23;
            StringCchCopyNExW(v23, v16, v10, v17, 0, 0, 0);
            if ( MEMORY[0x44] != 1 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( *MEMORY[0x48] != 100 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v19 = MEMORY[0x48];
            if ( *(_DWORD *)(MEMORY[0x48] + 8LL) != 8 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            if ( !*(_DWORD *)(v19 + 16) )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v20 = *(unsigned int *)(v19 + 16);
            if ( v20 != 20 * (v20 / 0x14) )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v7 = CTLocalAllocPolicy::Alloc((void *)v20, 0x40u, *(unsigned int *)(v19 + 16), (void **)a3);
            if ( v7 >= 0 )
            {
              memcpy_0(*a3, *(const void **)(v19 + 24), *(unsigned int *)(v19 + 16));
              *v25 = *(unsigned int *)(v19 + 16) / 0x14uLL;
              if ( a2 )
              {
                v23 = 0;
                *a2 = v18;
                v18 = 0;
              }
            }
            if ( v18 )
            {
              do
                ++v14;
              while ( v18[v14] );
              for ( i = 2 * v14; i; --i )
              {
                *(_BYTE *)v18 = 0;
                v18 = (unsigned __int16 *)((char *)v18 + 1);
              }
            }
          }
        }
        CLocalMemPtr<unsigned short>::~CLocalMemPtr<unsigned short>((void **)&v23);
      }
      VaultFree(0);
    }
    VaultCloseVault(&v24);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180018f10  push    rbp
0x180018f12  push    rbx
0x180018f13  push    rsi
0x180018f14  push    rdi
0x180018f15  push    r12
0x180018f17  push    r13
0x180018f19  push    r14
0x180018f1b  push    r15
0x180018f1d  lea     rbp, [rsp-1Fh]
0x180018f22  sub     rsp, 0C8h
0x180018f29  mov     rax, cs:__security_cookie
0x180018f30  xor     rax, rsp
0x180018f33  mov     [rbp+57h+var_50], rax
0x180018f37  xor     esi, esi
0x180018f39  mov     [rbp+57h+var_A8], r9
0x180018f3d  mov     r13, r8
0x180018f40  mov     r12, rdx
0x180018f43  mov     rdi, rcx
0x180018f46  test    rdx, rdx
0x180018f49  jz      short loc_180018F4E
0x180018f4b  mov     [rdx], rsi
0x180018f4e  mov     [r8], rsi
0x180018f51  call    ?GetEnrollmentStatus@CPicturePasswordVault@@SAJPEAX@Z; CPicturePasswordVault::GetEnrollmentStatus(void *)
0x180018f56  test    eax, eax
0x180018f58  jz      short loc_180018F5F
0x180018f5a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018f5f  lea     rcx, [rbp+57h+var_B0]; void **
0x180018f63  mov     [rbp+57h+var_B0], rsi
0x180018f67  call    ?_OpenPicturePasswordVault@@YAJPEAPEAX@Z; _OpenPicturePasswordVault(void * *)
0x180018f6c  mov     ebx, eax
0x180018f6e  test    eax, eax
0x180018f70  js      loc_18001919C
0x180018f76  movups  xmm0, cs:c_guidPicturePasswordVaultSchema
0x180018f7d  lea     rax, aPicturePasswor_1; "Picture Password Vault Resource"
0x180018f84  mov     [rbp+57h+var_80], 1
0x180018f8c  mov     rcx, rdi; pSid
0x180018f8f  mov     [rbp+57h+var_78], 7
0x180018f97  movdqu  [rbp+57h+var_60], xmm0
0x180018f9c  mov     [rbp+57h+var_68], rsi
0x180018fa0  xorps   xmm0, xmm0
0x180018fa3  mov     [rbp+57h+var_70], rax
0x180018fa7  movups  [rbp+57h+var_A0], xmm0
0x180018fab  mov     dword ptr [rbp+57h+var_A0], 2
0x180018fb2  mov     dword ptr [rbp+57h+var_A0+8], 8
0x180018fb9  movups  [rbp+57h+var_90], xmm0
0x180018fbd  call    cs:__imp_GetLengthSid
0x180018fc3  mov     rcx, [rbp+57h+var_B0]
0x180018fc7  lea     r9, [rbp+57h+var_A0]
0x180018fcb  mov     dword ptr [rbp+57h+var_90], eax
0x180018fce  lea     r8, [rbp+57h+var_80]
0x180018fd2  lea     rax, [rbp+57h+var_C0]
0x180018fd6  mov     qword ptr [rbp+57h+var_90+8], rdi
0x180018fda  mov     [rsp+100h+var_C8], rax
0x180018fdf  lea     rdx, [rbp+57h+var_60]
0x180018fe3  mov     [rsp+100h+var_D0], esi; unsigned int
0x180018fe7  mov     [rsp+100h+var_D8], rsi; unsigned __int64 *
0x180018fec  mov     [rsp+100h+var_E0], rsi; unsigned __int16 **
0x180018ff1  mov     [rbp+57h+var_C0], rsi
0x180018ff5  call    cs:__imp_VaultGetItem
0x180018ffb  mov     ebx, eax
0x180018ffd  test    eax, eax
0x180018fff  jle     short loc_18001900A
0x180019001  movzx   ebx, ax
0x180019004  or      ebx, 80070000h
0x18001900a  test    ebx, ebx
0x18001900c  js      loc_180019192
0x180019012  mov     rax, [rbp+57h+var_C0]
0x180019016  mov     rbx, [rax+28h]
0x18001901a  cmp     dword ptr [rbx+8], 8
0x18001901e  jz      short loc_180019025
0x180019020  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019025  mov     r15, [rbx+18h]
0x180019029  lea     r8, [rbp+57h+var_B8]; unsigned __int64 *
0x18001902d  mov     edx, [rbx+10h]
0x180019030  mov     rcx, r15; unsigned __int16 *
0x180019033  shr     rdx, 1; unsigned __int64
0x180019036  mov     [rbp+57h+var_B8], rsi
0x18001903a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001903f  mov     ebx, eax
0x180019041  test    eax, eax
0x180019043  js      loc_180019188
0x180019049  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001904d  mov     rdi, r14
0x180019050  inc     rdi
0x180019053  cmp     [r15+rdi*2], si
0x180019058  jnz     short loc_180019050
0x18001905a  mov     [rbp+57h+var_B8], rsi
0x18001905e  lea     rsi, [rdi+1]
0x180019062  cmp     rsi, rdi
0x180019065  jb      loc_18001917A
0x18001906b  lea     r9, [rbp+57h+var_B8]
0x18001906f  mov     r8, rsi
0x180019072  call    ??$_AllocArray@GVCTLocalAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTLocalAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180019077  mov     ebx, eax
0x180019079  test    eax, eax
0x18001907b  js      loc_18001917F
0x180019081  mov     r9, rdi; unsigned __int64
0x180019084  mov     r8, r15; unsigned __int16 *
0x180019087  mov     rdi, [rbp+57h+var_B8]
0x18001908b  mov     rdx, rsi; unsigned __int64
0x18001908e  mov     rcx, rdi; unsigned __int16 *
0x180019091  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180019096  mov     rcx, [rbp+57h+var_C0]
0x18001909a  cmp     dword ptr [rcx+44h], 1
0x18001909e  jz      short loc_1800190A9
0x1800190a0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190a5  mov     rcx, [rbp+57h+var_C0]
0x1800190a9  mov     rax, [rcx+48h]
0x1800190ad  cmp     dword ptr [rax], 64h ; 'd'
0x1800190b0  jz      short loc_1800190BB
0x1800190b2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190b7  mov     rcx, [rbp+57h+var_C0]
0x1800190bb  mov     rsi, [rcx+48h]
0x1800190bf  cmp     dword ptr [rsi+8], 8
0x1800190c3  jz      short loc_1800190CA
0x1800190c5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190ca  xor     r15d, r15d
0x1800190cd  cmp     [rsi+10h], r15d
0x1800190d1  ja      short loc_1800190D8
0x1800190d3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190d8  mov     ecx, [rsi+10h]
0x1800190db  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800190e5  mul     rcx
0x1800190e8  shr     rdx, 4
0x1800190ec  lea     rax, [rdx+rdx*4]
0x1800190f0  shl     rax, 2
0x1800190f4  cmp     rcx, rax
0x1800190f7  jz      short loc_1800190FE
0x1800190f9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800190fe  mov     r8d, [rsi+10h]; unsigned __int64
0x180019102  mov     r9, r13; void **
0x180019105  mov     edx, 40h ; '@'; unsigned int
0x18001910a  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001910f  mov     ebx, eax
0x180019111  test    eax, eax
0x180019113  js      short loc_180019154
0x180019115  mov     r8d, [rsi+10h]; Size
0x180019119  mov     rdx, [rsi+18h]; Src
0x18001911d  mov     rcx, [r13+0]; void *
0x180019121  call    memcpy_0
0x180019126  mov     ecx, [rsi+10h]
0x180019129  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180019133  mul     rcx
0x180019136  mov     rax, [rbp+57h+var_A8]
0x18001913a  shr     rdx, 4
0x18001913e  mov     [rax], rdx
0x180019141  test    r12, r12
0x180019144  jz      short loc_180019154
0x180019146  mov     rax, rdi
0x180019149  mov     [rbp+57h+var_B8], r15
0x18001914d  mov     [r12], rax
0x180019151  mov     rdi, r15
0x180019154  test    rdi, rdi
0x180019157  jz      short loc_18001917F
0x180019159  inc     r14
0x18001915c  cmp     [rdi+r14*2], r15w
0x180019161  jnz     short loc_180019159
0x180019163  lea     rax, [r14+r14]
0x180019167  test    rax, rax
0x18001916a  jz      short loc_18001917F
0x18001916c  mov     [rdi], r15b
0x18001916f  inc     rdi
0x180019172  sub     rax, 1
0x180019176  jnz     short loc_18001916C
0x180019178  jmp     short loc_18001917F
0x18001917a  mov     ebx, 80070216h
0x18001917f  lea     rcx, [rbp+57h+var_B8]
0x180019183  call    ??1?$CLocalMemPtr@G@@QEAA@XZ; CLocalMemPtr<ushort>::~CLocalMemPtr<ushort>(void)
0x180019188  mov     rcx, [rbp+57h+var_C0]
0x18001918c  call    cs:__imp_VaultFree
0x180019192  lea     rcx, [rbp+57h+var_B0]
0x180019196  call    cs:__imp_VaultCloseVault
0x18001919c  mov     eax, ebx
0x18001919e  mov     rcx, [rbp+57h+var_50]
0x1800191a2  xor     rcx, rsp; StackCookie
0x1800191a5  call    __security_check_cookie
0x1800191aa  add     rsp, 0C8h
0x1800191b1  pop     r15
0x1800191b3  pop     r14
0x1800191b5  pop     r13
0x1800191b7  pop     r12
0x1800191b9  pop     rdi
0x1800191ba  pop     rsi
0x1800191bb  pop     rbx
0x1800191bc  pop     rbp
0x1800191bd  retn
```

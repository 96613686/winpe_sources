# CredentialUpdateNotify

- ea: `0x180024ea0`
- end: `0x180025524`
- name: `CredentialUpdateNotify`
- size: `1668`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PCUNICODE_STRING Source, PCUNICODE_STRING SourceString, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800277a0`

## callees

- `0x1800061a0`
- `0x180006d00`
- `0x180011fec`
- `0x1800185b8`
- `0x18001874c`
- `0x180018874`
- `0x180024ea0`
- `0x180025a14`
- `0x180033500`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18002500e`
- `ntdll!RtlCopyUnicodeString` at `0x18002522a`
- `ntdll!RtlCopyUnicodeString` at `0x18002500e`
- `ntdll!RtlCopyUnicodeString` at `0x18002522a`
- `ntdll!RtlAppendUnicodeToString` at `0x18002523b`
- `ntdll!RtlAppendUnicodeToString` at `0x18002523b`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180025279`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180025279`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002501f`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002501f`
- `ntdll!RtlInitUnicodeString` at `0x180025360`
- `ntdll!RtlInitUnicodeString` at `0x180025360`

## pseudocode

```c
__int64 __fastcall CredentialUpdateNotify(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        PCUNICODE_STRING Source,
        PCUNICODE_STRING SourceString,
        __int64 a8,
        __int64 *a9,
        _DWORD *a10)
{
  PVOID *v11; // rcx
  __int64 Memory; // r15
  int appended; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // rsi
  __int16 v19; // r14
  __int16 v20; // r14
  __int64 v21; // rcx
  __int64 v22; // rsi
  __int16 v23; // r14
  __int64 v24; // rsi
  __int16 v25; // r14
  __int64 v26; // rbx
  unsigned __int16 v27; // si
  __int64 v28; // r14
  __int64 v30; // [rsp+20h] [rbp-61h]
  unsigned __int16 v31; // [rsp+30h] [rbp-51h] BYREF
  __int64 v32; // [rsp+38h] [rbp-49h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-41h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-31h] BYREF
  struct _UNICODE_STRING v35; // [rsp+60h] [rbp-21h] BYREF
  _OWORD v36[5]; // [rsp+70h] [rbp-11h] BYREF

  v31 = 0;
  DestinationString = 0;
  Destination = 0;
  v36[0] = 0;
  v35 = 0;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids);
      v11 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 )
      WPP_SF_ZZZ((TRACEHANDLE)v11[2], (__int64)Source, a8);
  }
  *a9 = 0;
  *a10 = 0;
  Memory = DigestAllocateMemory(0x1E0u);
  if ( Memory )
  {
    appended = UnicodeStringAllocate((__int64)&DestinationString, ((unsigned __int64)SourceString->Length + 2) >> 1);
    if ( appended >= 0 )
    {
      RtlCopyUnicodeString(&DestinationString, SourceString);
      appended = RtlUpcaseUnicodeString(&DestinationString, &DestinationString, 0);
      if ( appended >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_Z(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids,
            &DestinationString);
        *(_BYTE *)Memory = 49;
        *(_WORD *)(Memory + 2) = 7425;
        v31 = 464;
        v17 = PrecalcForms((_DWORD)Source, (unsigned int)&DestinationString, a1, 0, Memory + 16, (__int64)&v31);
        appended = v17;
        if ( v17 >= 0 )
        {
          v18 = v31 + Memory + 16;
          v19 = v31 + 16;
          v31 = 480 - (v31 + 16);
          appended = PrecalcForms((_DWORD)Source, a8, a1, 0, v18, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 17;
            goto LABEL_15;
          }
          v20 = v31 + v19;
          v21 = v18 + v31;
          v31 = 480 - v20;
          v32 = v21;
          appended = PrecalcForms(a5, (unsigned int)v36, a1, 1, v21, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 18;
            goto LABEL_15;
          }
          v22 = v31;
          v23 = v31 + v20;
          appended = UnicodeStringAllocate(
                       (__int64)&Destination,
                       ((unsigned __int64)(DestinationString.Length + (unsigned int)Source->Length) + 2) >> 1);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 19;
            goto LABEL_15;
          }
          RtlCopyUnicodeString(&Destination, &DestinationString);
          appended = RtlAppendUnicodeToString(&Destination, L"\\");
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 20;
            goto LABEL_15;
          }
          appended = RtlAppendUnicodeStringToString(&Destination, Source);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 21;
            goto LABEL_15;
          }
          v24 = v32 + v22;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_Z(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids,
              &Destination);
          v31 = 480 - v23;
          appended = PrecalcForms((unsigned int)&Destination, (unsigned int)v36, a1, 1, v24, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 23;
            goto LABEL_15;
          }
          v25 = v31 + v23;
          v26 = v24 + v31;
          v32 = v26;
          RtlInitUnicodeString(&v35, L"Digest");
          v31 = 480 - v25;
          appended = PrecalcForms((_DWORD)Source, (unsigned int)&v35, a1, 1, v26, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 24;
            goto LABEL_15;
          }
          v27 = 480 - v25 - v31;
          v28 = v32 + v31;
          v31 = v27;
          appended = PrecalcForms(a5, (unsigned int)&v35, a1, 1, v28, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 25;
            goto LABEL_15;
          }
          v30 = v28 + v31;
          v31 = v27 - v31;
          appended = PrecalcForms((unsigned int)&Destination, (unsigned int)&v35, a1, 1, v30, (__int64)&v31);
          if ( appended < 0 )
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_70;
            v15 = 26;
            goto LABEL_15;
          }
          *a9 = Memory;
          *a10 = 480;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            goto LABEL_70;
          v15 = 27;
          v16 = 480;
        }
        else
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_70;
          v15 = 16;
          v16 = (unsigned int)v17;
        }
LABEL_69:
        WPP_SF_d(v14[2], v15, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids, v16);
        goto LABEL_70;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v15 = 14;
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_70;
      v15 = 13;
    }
LABEL_15:
    v16 = (unsigned int)appended;
    goto LABEL_69;
  }
  appended = -1073741670;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids, 3221225626LL);
LABEL_70:
  UnicodeStringFree(&DestinationString);
  UnicodeStringFree(&Destination);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids,
      (unsigned int)appended);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180024ea0  push    rbp
0x180024ea2  push    rbx
0x180024ea3  push    rsi
0x180024ea4  push    rdi
0x180024ea5  push    r12
0x180024ea7  push    r13
0x180024ea9  push    r14
0x180024eab  push    r15
0x180024ead  lea     rbp, [rsp-7]
0x180024eb2  sub     rsp, 88h
0x180024eb9  xorps   xmm0, xmm0
0x180024ebc  xorps   xmm1, xmm1
0x180024ebf  xor     eax, eax
0x180024ec1  mov     r13, rcx
0x180024ec4  mov     [rbp+3Fh+var_90], ax
0x180024ec8  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x180024ecc  movups  xmmword ptr [rbp+3Fh+Destination.Length], xmm1
0x180024ed0  movups  [rbp+3Fh+var_50], xmm0
0x180024ed4  movups  xmmword ptr [rbp+3Fh+var_60.Length], xmm1
0x180024ed8  mov     rcx, cs:WPP_GLOBAL_Control
0x180024edf  lea     rbx, WPP_GLOBAL_Control
0x180024ee6  mov     r12, [rbp+3Fh+Source]
0x180024eea  cmp     rcx, rbx
0x180024eed  jz      short loc_180024F44
0x180024eef  test    byte ptr [rcx+1Ch], 80h
0x180024ef3  jz      short loc_180024F0F
0x180024ef5  mov     rcx, [rcx+10h]
0x180024ef9  lea     edx, [rax+0Ah]
0x180024efc  lea     r8, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids
0x180024f03  call    WPP_SF_
0x180024f08  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f0f  cmp     rcx, rbx
0x180024f12  jz      short loc_180024F44
0x180024f14  test    byte ptr [rcx+1Ch], 4
0x180024f18  jz      short loc_180024F44
0x180024f1a  mov     rax, [rbp+3Fh+arg_38]
0x180024f21  lea     r8, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids
0x180024f28  mov     r9, [rbp+3Fh+arg_20]
0x180024f2c  mov     edx, 0Bh
0x180024f31  mov     rcx, [rcx+10h]; LoggerHandle
0x180024f35  mov     [rsp+0C0h+var_98], rax; __int64
0x180024f3a  mov     [rsp+0C0h+var_A0], r12; __int64
0x180024f3f  call    WPP_SF_ZZZ
0x180024f44  mov     rax, [rbp+3Fh+arg_40]
0x180024f4b  mov     ecx, 1E0h; Size
0x180024f50  mov     qword ptr [rax], 0
0x180024f57  mov     rax, [rbp+3Fh+arg_48]
0x180024f5e  mov     dword ptr [rax], 0
0x180024f64  call    DigestAllocateMemory
0x180024f69  mov     r15, rax
0x180024f6c  test    rax, rax
0x180024f6f  jnz     short loc_180024FB9
0x180024f71  mov     ebx, 0C000009Ah
0x180024f76  mov     rcx, cs:WPP_GLOBAL_Control
0x180024f7d  lea     rax, WPP_GLOBAL_Control
0x180024f84  cmp     rcx, rax
0x180024f87  jz      loc_1800254CB
0x180024f8d  lea     edi, [r15+1]
0x180024f91  test    [rcx+1Ch], dil
0x180024f95  jz      loc_1800254CB
0x180024f9b  mov     rcx, [rcx+10h]
0x180024f9f  lea     edx, [rdi+0Bh]
0x180024fa2  mov     r9d, 0C000009Ah
0x180024fa8  lea     r8, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids
0x180024faf  call    WPP_SF_d
0x180024fb4  jmp     loc_1800254CB
0x180024fb9  mov     rdi, [rbp+3Fh+SourceString]
0x180024fbd  lea     rcx, [rbp+3Fh+DestinationString]
0x180024fc1  movzx   edx, word ptr [rdi]
0x180024fc4  add     rdx, 2
0x180024fc8  shr     rdx, 1
0x180024fcb  call    UnicodeStringAllocate
0x180024fd0  mov     ebx, eax
0x180024fd2  test    eax, eax
0x180024fd4  jns     short loc_180025007
0x180024fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fdd  lea     rax, WPP_GLOBAL_Control
0x180024fe4  cmp     rcx, rax
0x180024fe7  jz      loc_1800254CB
0x180024fed  mov     edi, 1
0x180024ff2  test    [rcx+1Ch], dil
0x180024ff6  jz      loc_1800254CB
0x180024ffc  lea     edx, [rdi+0Ch]
0x180024fff  mov     r9d, ebx
0x180025002  jmp     loc_1800254BB
0x180025007  mov     rdx, rdi; SourceString
0x18002500a  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18002500e  call    cs:__imp_RtlCopyUnicodeString
0x180025014  xor     r8d, r8d; AllocateDestinationString
0x180025017  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x18002501b  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x18002501f  call    cs:__imp_RtlUpcaseUnicodeString
0x180025025  mov     ebx, eax
0x180025027  test    eax, eax
0x180025029  jns     short loc_180025056
0x18002502b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025032  lea     rax, WPP_GLOBAL_Control
0x180025039  cmp     rcx, rax
0x18002503c  jz      loc_1800254CB
0x180025042  mov     edi, 1
0x180025047  test    [rcx+1Ch], dil
0x18002504b  jz      loc_1800254CB
0x180025051  lea     edx, [rdi+0Dh]
0x180025054  jmp     short loc_180024FFF
0x180025056  mov     rcx, cs:WPP_GLOBAL_Control
0x18002505d  lea     r14, WPP_GLOBAL_Control
0x180025064  cmp     rcx, r14
0x180025067  jz      short loc_180025088
0x180025069  test    byte ptr [rcx+1Ch], 4
0x18002506d  jz      short loc_180025088
0x18002506f  mov     rcx, [rcx+10h]
0x180025073  lea     r9, [rbp+3Fh+DestinationString]
0x180025077  mov     edx, 0Fh
0x18002507c  lea     r8, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids
0x180025083  call    WPP_SF_Z
0x180025088  mov     eax, 1D0h
0x18002508d  mov     byte ptr [r15], 31h ; '1'
0x180025091  mov     word ptr [r15+2], 1D01h
0x180025098  lea     rsi, [r15+10h]
0x18002509c  mov     [rbp+3Fh+var_90], ax
0x1800250a0  lea     rdx, [rbp+3Fh+DestinationString]
0x1800250a4  lea     rax, [rbp+3Fh+var_90]
0x1800250a8  xor     r9d, r9d
0x1800250ab  mov     [rsp+0C0h+var_98], rax
0x1800250b0  mov     r8, r13
0x1800250b3  mov     rcx, r12
0x1800250b6  mov     [rsp+0C0h+var_A0], rsi
0x1800250bb  mov     edi, 1
0x1800250c0  call    PrecalcForms
0x1800250c5  mov     ebx, eax
0x1800250c7  test    eax, eax
0x1800250c9  jns     short loc_1800250F0
0x1800250cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800250d2  cmp     rcx, r14
0x1800250d5  jz      loc_1800254CB
0x1800250db  test    [rcx+1Ch], dil
0x1800250df  jz      loc_1800254CB
0x1800250e5  lea     edx, [rdi+0Fh]
0x1800250e8  mov     r9d, eax
0x1800250eb  jmp     loc_1800254BB
0x1800250f0  movzx   r14d, [rbp+3Fh+var_90]
0x1800250f5  mov     eax, 1E0h
0x1800250fa  mov     rdx, [rbp+3Fh+arg_38]
0x180025101  add     rsi, r14
0x180025104  add     r14w, 10h
0x180025109  xor     r9d, r9d
0x18002510c  sub     ax, r14w
0x180025110  mov     r8, r13
0x180025113  mov     [rbp+3Fh+var_90], ax
0x180025117  mov     rcx, r12
0x18002511a  lea     rax, [rbp+3Fh+var_90]
0x18002511e  mov     [rsp+0C0h+var_98], rax
0x180025123  mov     [rsp+0C0h+var_A0], rsi
0x180025128  call    PrecalcForms
0x18002512d  mov     ebx, eax
0x18002512f  test    eax, eax
0x180025131  jns     short loc_18002515E
0x180025133  mov     rcx, cs:WPP_GLOBAL_Control
0x18002513a  lea     rax, WPP_GLOBAL_Control
0x180025141  cmp     rcx, rax
0x180025144  jz      loc_1800254CB
0x18002514a  test    [rcx+1Ch], dil
0x18002514e  jz      loc_1800254CB
0x180025154  mov     edx, 11h
0x180025159  jmp     loc_180024FFF
0x18002515e  add     r14w, [rbp+3Fh+var_90]
0x180025163  lea     rdx, [rbp+3Fh+var_50]
0x180025167  movzx   ecx, [rbp+3Fh+var_90]
0x18002516b  mov     eax, 1E0h
0x180025170  add     rcx, rsi
0x180025173  sub     ax, r14w
0x180025177  mov     [rbp+3Fh+var_90], ax
0x18002517b  mov     r9d, edi
0x18002517e  lea     rax, [rbp+3Fh+var_90]
0x180025182  mov     [rbp+3Fh+var_88], rcx
0x180025186  mov     [rsp+0C0h+var_98], rax
0x18002518b  mov     r8, r13
0x18002518e  mov     [rsp+0C0h+var_A0], rcx
0x180025193  mov     rcx, [rbp+3Fh+arg_20]
0x180025197  call    PrecalcForms
0x18002519c  mov     ebx, eax
0x18002519e  test    eax, eax
0x1800251a0  jns     short loc_1800251CD
0x1800251a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251a9  lea     rax, WPP_GLOBAL_Control
0x1800251b0  cmp     rcx, rax
0x1800251b3  jz      loc_1800254CB
0x1800251b9  test    [rcx+1Ch], dil
0x1800251bd  jz      loc_1800254CB
0x1800251c3  mov     edx, 12h
0x1800251c8  jmp     loc_180024FFF
0x1800251cd  movzx   edx, word ptr [r12]
0x1800251d2  lea     rcx, [rbp+3Fh+Destination]
0x1800251d6  movzx   eax, [rbp+3Fh+DestinationString.Length]
0x1800251da  movzx   esi, [rbp+3Fh+var_90]
0x1800251de  add     edx, eax
0x1800251e0  add     r14w, [rbp+3Fh+var_90]
0x1800251e5  add     rdx, 2
0x1800251e9  shr     rdx, 1
0x1800251ec  call    UnicodeStringAllocate
0x1800251f1  mov     ebx, eax
0x1800251f3  test    eax, eax
0x1800251f5  jns     short loc_180025222
0x1800251f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800251fe  lea     rax, WPP_GLOBAL_Control
0x180025205  cmp     rcx, rax
0x180025208  jz      loc_1800254CB
0x18002520e  test    [rcx+1Ch], dil
0x180025212  jz      loc_1800254CB
0x180025218  mov     edx, 13h
0x18002521d  jmp     loc_180024FFF
0x180025222  lea     rdx, [rbp+3Fh+DestinationString]; SourceString
0x180025226  lea     rcx, [rbp+3Fh+Destination]; DestinationString
0x18002522a  call    cs:__imp_RtlCopyUnicodeString
0x180025230  lea     rdx, asc_18003BA30; "\\"
0x180025237  lea     rcx, [rbp+3Fh+Destination]; Destination
0x18002523b  call    cs:__imp_RtlAppendUnicodeToString
0x180025241  mov     ebx, eax
0x180025243  test    eax, eax
0x180025245  jns     short loc_180025272
0x180025247  mov     rcx, cs:WPP_GLOBAL_Control
0x18002524e  lea     rax, WPP_GLOBAL_Control
0x180025255  cmp     rcx, rax
0x180025258  jz      loc_1800254CB
0x18002525e  test    [rcx+1Ch], dil
0x180025262  jz      loc_1800254CB
0x180025268  mov     edx, 14h
0x18002526d  jmp     loc_180024FFF
0x180025272  mov     rdx, r12; Source
0x180025275  lea     rcx, [rbp+3Fh+Destination]; Destination
0x180025279  call    cs:__imp_RtlAppendUnicodeStringToString
0x18002527f  mov     ebx, eax
0x180025281  test    eax, eax
0x180025283  jns     short loc_1800252B0
0x180025285  mov     rcx, cs:WPP_GLOBAL_Control
0x18002528c  lea     rax, WPP_GLOBAL_Control
0x180025293  cmp     rcx, rax
0x180025296  jz      loc_1800254CB
0x18002529c  test    [rcx+1Ch], dil
0x1800252a0  jz      loc_1800254CB
0x1800252a6  mov     edx, 15h
0x1800252ab  jmp     loc_180024FFF
0x1800252b0  add     rsi, [rbp+3Fh+var_88]
0x1800252b4  lea     rax, WPP_GLOBAL_Control
0x1800252bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800252c2  cmp     rcx, rax
0x1800252c5  jz      short loc_1800252E6
0x1800252c7  test    byte ptr [rcx+1Ch], 4
0x1800252cb  jz      short loc_1800252E6
0x1800252cd  mov     rcx, [rcx+10h]
0x1800252d1  lea     r9, [rbp+3Fh+Destination]
0x1800252d5  mov     edx, 16h
0x1800252da  lea     r8, WPP_e0e5a0c64c5431bddc09967e0f72dd60_Traceguids
0x1800252e1  call    WPP_SF_Z
0x1800252e6  mov     eax, 1E0h
0x1800252eb  lea     rdx, [rbp+3Fh+var_50]
0x1800252ef  sub     ax, r14w
0x1800252f3  lea     rcx, [rbp+3Fh+Destination]
0x1800252f7  mov     [rbp+3Fh+var_90], ax
0x1800252fb  mov     r9d, edi
0x1800252fe  lea     rax, [rbp+3Fh+var_90]
0x180025302  mov     r8, r13
0x180025305  mov     [rsp+0C0h+var_98], rax
0x18002530a  mov     [rsp+0C0h+var_A0], rsi
0x18002530f  call    PrecalcForms
0x180025314  mov     ebx, eax
0x180025316  test    eax, eax
0x180025318  jns     short loc_180025345
0x18002531a  mov     rcx, cs:WPP_GLOBAL_Control
0x180025321  lea     rax, WPP_GLOBAL_Control
0x180025328  cmp     rcx, rax
0x18002532b  jz      loc_1800254CB
0x180025331  test    [rcx+1Ch], dil
0x180025335  jz      loc_1800254CB
0x18002533b  mov     edx, 17h
0x180025340  jmp     loc_180024FFF
0x180025345  movzx   ebx, [rbp+3Fh+var_90]
0x180025349  lea     rdx, aDigest; "Digest"
0x180025350  add     r14w, [rbp+3Fh+var_90]
0x180025355  lea     rcx, [rbp+3Fh+var_60]; DestinationString
0x180025359  add     rbx, rsi
0x18002535c  mov     [rbp+3Fh+var_88], rbx
0x180025360  call    cs:__imp_RtlInitUnicodeString
0x180025366  lea     rax, [rbp+3Fh+var_90]
0x18002536a  mov     esi, 1E0h
0x18002536f  mov     [rsp+0C0h+var_98], rax
0x180025374  lea     rdx, [rbp+3Fh+var_60]
0x180025378  sub     si, r14w
0x18002537c  mov     [rsp+0C0h+var_A0], rbx
0x180025381  mov     r9d, edi
0x180025384  mov     [rbp+3Fh+var_90], si
0x180025388  mov     r8, r13
0x18002538b  mov     rcx, r12
0x18002538e  call    PrecalcForms
0x180025393  mov     ebx, eax
0x180025395  test    eax, eax
0x180025397  jns     short loc_1800253C4
0x180025399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800253a0  lea     rax, WPP_GLOBAL_Control
0x1800253a7  cmp     rcx, rax
  ... truncated ...
```

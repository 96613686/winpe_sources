# SclRegProcessOfflineRegistry

- ea: `0x1800111bc`
- end: `0x1800117dd`
- name: `SclRegProcessOfflineRegistry`
- size: `1569`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800065f8`

## callees

- `0x180005a20`
- `0x18000a524`
- `0x18000a69c`
- `0x18000acec`
- `0x18000bc68`
- `0x1800111bc`
- `0x180014fa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800113c9`
- `ntdll!RtlFreeHeap` at `0x1800114a1`
- `ntdll!RtlFreeHeap` at `0x18001156f`
- `ntdll!RtlFreeHeap` at `0x18001163d`
- `ntdll!RtlFreeHeap` at `0x1800117bd`
- `ntdll!RtlFreeHeap` at `0x1800113c9`
- `ntdll!RtlFreeHeap` at `0x1800114a1`
- `ntdll!RtlFreeHeap` at `0x18001156f`
- `ntdll!RtlFreeHeap` at `0x18001163d`
- `ntdll!RtlFreeHeap` at `0x1800117bd`

## string_xrefs

- `0x1800114e9`: `SECURITY`
- `0x180011519`: `SECURITY`
- `0x1800111ef`: `Marking event [&SclEvent_ProcessSystemRegistry_Start]`
- `0x1800116ca`: `Marking event [&SclEvent_ProcessSystemRegistry_Stop]`
- `0x180011770`: `(%lx): Failed to process offline registry`
- `0x180011787`: `SclRegProcessOfflineRegistry`

## pseudocode

```c
__int64 __fastcall SclRegProcessOfflineRegistry(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v5; // rcx
  int v7; // esi
  char v8; // r12
  __int64 v9; // r13
  PVOID v10; // rdi
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // r14
  int v19; // eax
  __int64 v20; // r13
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v28; // [rsp+40h] [rbp-20h]
  __int64 v29; // [rsp+48h] [rbp-18h]
  __int64 v30; // [rsp+50h] [rbp-10h]
  __int64 v31; // [rsp+58h] [rbp-8h]
  PVOID P; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+58h]

  v5 = a1 + 1152;
  v7 = 0;
  if ( !a1 )
    v5 = 0;
  v31 = v5;
  SclLogTimingEvent(v5, SclEvent_ProcessSystemRegistry_Start, "Marking event [&SclEvent_ProcessSystemRegistry_Start]");
  v8 = 1;
  v34 = 0;
  v9 = 0;
  v28 = 0;
  v10 = 0;
  v29 = 0;
  v30 = 0;
  P = 0;
  if ( !a3 )
    goto LABEL_27;
  if ( (*(_DWORD *)(a1 + 8) & 0x8000) != 0 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 && *a3 && *(_QWORD *)*a3
      || (*(_DWORD *)(a1 + 8) & 0x200) != 0 && (v11 = (_QWORD *)a3[1]) != 0 && *v11
      || (*(_DWORD *)(a1 + 8) & 0x400) != 0 && (v12 = (_QWORD *)a3[2]) != 0 && *v12
      || (*(_DWORD *)(a1 + 8) & 0x800) != 0 && (v13 = (_QWORD *)a3[3]) != 0 && *v13
      || (*(_DWORD *)(a1 + 8) & 0x1000) != 0 && (v14 = (_QWORD *)a3[4]) != 0 && *v14 )
    {
      v7 = -1073741811;
      goto LABEL_83;
    }
  }
  else if ( *a3 && a3[1] && a3[2] && a3[3] )
  {
    v8 = a3[4] == 0;
  }
  v15 = a3[2];
  v9 = *a3;
  v34 = a3[1];
  v28 = v15;
  v29 = a3[3];
  v30 = a3[4];
  if ( v8 )
  {
LABEL_27:
    if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
      goto LABEL_35;
    if ( v9 )
    {
      v16 = CanonicalizeObjectPathByHandle(*(HANDLE *)(a2 + 24), &P);
      v10 = P;
      v7 = v16;
      if ( v16 < 0 )
        goto LABEL_83;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)P + v17) );
      *(_QWORD *)(v9 + 8) = v17;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)L"DEFAULT");
    v7 = SclRegProcessKeyByHandle(a1, *(void **)(a2 + 24), v8, v9);
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)L"DEFAULT");
  }
LABEL_35:
  if ( v7 < 0 )
    goto LABEL_83;
  v18 = v34;
  if ( v8 && (*(_DWORD *)(a1 + 8) & 0x200) != 0 && v34 )
  {
    if ( v10 )
    {
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
      P = 0;
    }
    v19 = CanonicalizeObjectPathByHandle(*(HANDLE *)(a2 + 32), &P);
    v10 = P;
    v7 = v19;
    if ( v19 < 0 )
      goto LABEL_83;
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)P + v21) );
    *(_QWORD *)(v18 + 8) = v21;
  }
  else
  {
    v20 = -1;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x200) != 0 )
  {
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)L"SAM");
    v7 = SclRegProcessKeyByHandle(a1, *(void **)(a2 + 32), v8, v18);
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)L"SAM");
  }
  if ( v7 < 0 )
    goto LABEL_83;
  if ( v8 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x400) == 0 )
      goto LABEL_60;
    if ( v28 )
    {
      if ( v10 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
        P = 0;
      }
      v22 = CanonicalizeObjectPathByHandle(*(HANDLE *)(a2 + 40), &P);
      v10 = P;
      v7 = v22;
      if ( v22 < 0 )
        goto LABEL_83;
      v23 = -1;
      do
        ++v23;
      while ( *((_WORD *)P + v23) );
      *(_QWORD *)(v28 + 8) = v23;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x400) != 0 )
  {
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)L"SECURITY");
    v7 = SclRegProcessKeyByHandle(a1, *(void **)(a2 + 40), v8, v28);
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)L"SECURITY");
  }
LABEL_60:
  if ( v7 < 0 )
    goto LABEL_83;
  if ( v8 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x800) == 0 )
      goto LABEL_72;
    if ( v29 )
    {
      if ( v10 )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
        P = 0;
      }
      v24 = CanonicalizeObjectPathByHandle(*(HANDLE *)(a2 + 48), &P);
      v10 = P;
      v7 = v24;
      if ( v24 < 0 )
        goto LABEL_83;
      v25 = -1;
      do
        ++v25;
      while ( *((_WORD *)P + v25) );
      *(_QWORD *)(v29 + 8) = v25;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x800) != 0 )
  {
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)L"SOFTWARE");
    v7 = SclRegProcessKeyByHandle(a1, *(void **)(a2 + 48), v8, v29);
    SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)L"SOFTWARE");
  }
LABEL_72:
  if ( v7 < 0 )
    goto LABEL_83;
  if ( !v8 )
    goto LABEL_81;
  if ( (*(_DWORD *)(a1 + 8) & 0x1000) == 0 )
    goto LABEL_83;
  if ( !v30 )
    goto LABEL_81;
  if ( v10 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
    P = 0;
  }
  v26 = CanonicalizeObjectPathByHandle(*(HANDLE *)(a2 + 56), &P);
  v10 = P;
  v7 = v26;
  if ( v26 >= 0 )
  {
    do
      ++v20;
    while ( *((_WORD *)P + v20) );
    *(_QWORD *)(v30 + 8) = v20;
LABEL_81:
    if ( (*(_DWORD *)(a1 + 8) & 0x1000) != 0 )
    {
      SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Start, (__int64)L"SYSTEM");
      v7 = SclRegProcessKeyByHandle(a1, *(void **)(a2 + 56), v8, v30);
      SclEtwWriteString(a1 + 1152, (__int64)SclEvent_ProcessRegistryHive_Stop, (__int64)L"SYSTEM");
    }
  }
LABEL_83:
  SclLogTimingEvent(v31, SclEvent_ProcessSystemRegistry_Stop, "Marking event [&SclEvent_ProcessSystemRegistry_Stop]");
  if ( v7 >= 0 )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x2000) == 0 )
      goto LABEL_92;
    if ( *(_QWORD *)(a2 + 16) && *(_QWORD *)(a2 + 8) && *(_QWORD *)(a2 + 48) )
    {
      SclLogTimingEvent(v31, SclEvent_ProcessUserProfiles_Start, "Marking event [&SclEvent_ProcessUserProfiles_Start]");
      v7 = SclRegProcessUserProfileHives(
             a1,
             *(_QWORD *)(a2 + 48),
             (unsigned int)L"MICROSOFT\\WINDOWS NT\\CURRENTVERSION\\PROFILELIST",
             (unsigned int)L"MICROSOFT\\WINDOWS NT\\CURRENTVERSION",
             *(_QWORD *)(a2 + 16),
             *(_QWORD *)(a2 + 8));
      SclLogTimingEvent(v31, SclEvent_ProcessUserProfiles_Stop, "Marking event [&SclEvent_ProcessUserProfiles_Stop]");
      if ( v7 >= 0 )
        goto LABEL_92;
    }
    else
    {
      v7 = -1073741811;
    }
  }
  SclLogGenericMessage(
    v31,
    3,
    (int)SclEvent_Generic_Error,
    389,
    (__int64)"SclRegProcessOfflineRegistry",
    "(%lx): Failed to process offline registry",
    v7);
LABEL_92:
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800111bc  mov     [rsp-38h+arg_8], rbx
0x1800111c1  mov     [rsp-38h+arg_0], rcx
0x1800111c6  push    rbp
0x1800111c7  push    rsi
0x1800111c8  push    rdi
0x1800111c9  push    r12
0x1800111cb  push    r13
0x1800111cd  push    r14
0x1800111cf  push    r15
0x1800111d1  mov     rbp, rsp
0x1800111d4  sub     rsp, 60h
0x1800111d8  mov     rbx, rcx
0x1800111db  mov     r15, rdx
0x1800111de  xor     edx, edx
0x1800111e0  add     rcx, 480h
0x1800111e7  mov     r14, r8
0x1800111ea  mov     esi, edx
0x1800111ec  test    rbx, rbx
0x1800111ef  lea     r8, aMarkingEventSc_11; "Marking event [&SclEvent_ProcessSystemR"...
0x1800111f6  cmovz   rcx, rdx
0x1800111fa  lea     rdx, SclEvent_ProcessSystemRegistry_Start
0x180011201  mov     [rbp+var_8], rcx
0x180011205  call    SclLogTimingEvent
0x18001120a  xor     ecx, ecx
0x18001120c  mov     r12b, 1
0x18001120f  mov     [rbp+arg_18], rcx
0x180011213  mov     r13d, ecx
0x180011216  mov     [rbp+var_20], rcx
0x18001121a  mov     edi, ecx
0x18001121c  mov     [rbp+var_18], rcx
0x180011220  mov     edx, 100h
0x180011225  mov     [rbp+var_10], rcx
0x180011229  mov     [rbp+P], rcx
0x18001122d  test    r14, r14
0x180011230  jz      loc_180011302
0x180011236  test    dword ptr [rbx+8], 8000h
0x18001123d  jz      short loc_1800112B7
0x18001123f  test    [rbx+8], edx
0x180011242  jz      short loc_180011251
0x180011244  mov     rax, [r14]
0x180011247  test    rax, rax
0x18001124a  jz      short loc_180011251
0x18001124c  cmp     [rax], rcx
0x18001124f  jnz     short loc_1800112AD
0x180011251  test    dword ptr [rbx+8], 200h
0x180011258  jz      short loc_180011268
0x18001125a  mov     rax, [r14+8]
0x18001125e  test    rax, rax
0x180011261  jz      short loc_180011268
0x180011263  cmp     [rax], rcx
0x180011266  jnz     short loc_1800112AD
0x180011268  test    dword ptr [rbx+8], 400h
0x18001126f  jz      short loc_18001127F
0x180011271  mov     rax, [r14+10h]
0x180011275  test    rax, rax
0x180011278  jz      short loc_18001127F
0x18001127a  cmp     [rax], rcx
0x18001127d  jnz     short loc_1800112AD
0x18001127f  test    dword ptr [rbx+8], 800h
0x180011286  jz      short loc_180011296
0x180011288  mov     rax, [r14+18h]
0x18001128c  test    rax, rax
0x18001128f  jz      short loc_180011296
0x180011291  cmp     [rax], rcx
0x180011294  jnz     short loc_1800112AD
0x180011296  test    dword ptr [rbx+8], 1000h
0x18001129d  jz      short loc_1800112DA
0x18001129f  mov     rax, [r14+20h]
0x1800112a3  test    rax, rax
0x1800112a6  jz      short loc_1800112DA
0x1800112a8  cmp     [rax], rcx
0x1800112ab  jz      short loc_1800112DA
0x1800112ad  mov     esi, 0C000000Dh
0x1800112b2  jmp     loc_1800116C6
0x1800112b7  cmp     [r14], rcx
0x1800112ba  jz      short loc_1800112DA
0x1800112bc  cmp     [r14+8], rcx
0x1800112c0  jz      short loc_1800112DA
0x1800112c2  cmp     [r14+10h], rcx
0x1800112c6  jz      short loc_1800112DA
0x1800112c8  cmp     [r14+18h], rcx
0x1800112cc  jz      short loc_1800112DA
0x1800112ce  cmp     [r14+20h], rcx
0x1800112d2  movzx   r12d, r12b
0x1800112d6  cmovnz  r12d, ecx
0x1800112da  mov     rax, [r14+8]
0x1800112de  mov     rcx, [r14+10h]
0x1800112e2  mov     r13, [r14]
0x1800112e5  mov     [rbp+arg_18], rax
0x1800112e9  mov     rax, [r14+18h]
0x1800112ed  mov     [rbp+var_20], rcx
0x1800112f1  mov     rcx, [r14+20h]
0x1800112f5  mov     [rbp+var_18], rax
0x1800112f9  mov     [rbp+var_10], rcx
0x1800112fd  test    r12b, r12b
0x180011300  jz      short loc_180011343
0x180011302  test    [rbx+8], edx
0x180011305  jz      loc_180011393
0x18001130b  test    r13, r13
0x18001130e  jz      short loc_180011343
0x180011310  mov     rcx, [r15+18h]; Handle
0x180011314  lea     rdx, [rbp+P]
0x180011318  call    CanonicalizeObjectPathByHandle
0x18001131d  mov     rdi, [rbp+P]
0x180011321  xor     ecx, ecx
0x180011323  mov     esi, eax
0x180011325  test    eax, eax
0x180011327  js      loc_1800116C6
0x18001132d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011331  inc     rax
0x180011334  cmp     [rdi+rax*2], cx
0x180011338  jnz     short loc_180011331
0x18001133a  mov     [r13+8], rax
0x18001133e  mov     edx, 100h
0x180011343  test    [rbx+8], edx
0x180011346  jz      short loc_180011393
0x180011348  mov     rsi, [rbp+arg_0]
0x18001134c  lea     r8, aDefault_0; "DEFAULT"
0x180011353  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x18001135a  lea     r14, [rsi+480h]
0x180011361  mov     rcx, r14
0x180011364  call    SclEtwWriteString
0x180011369  mov     rdx, [r15+18h]
0x18001136d  mov     r9, r13
0x180011370  mov     r8b, r12b
0x180011373  mov     rcx, rsi
0x180011376  call    SclRegProcessKeyByHandle
0x18001137b  lea     r8, aDefault_0; "DEFAULT"
0x180011382  mov     rcx, r14
0x180011385  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x18001138c  mov     esi, eax
0x18001138e  call    SclEtwWriteString
0x180011393  test    esi, esi
0x180011395  js      loc_1800116C6
0x18001139b  mov     r14, [rbp+arg_18]
0x18001139f  test    r12b, r12b
0x1800113a2  jz      short loc_18001140A
0x1800113a4  test    dword ptr [rbx+8], 200h
0x1800113ab  jz      short loc_18001140A
0x1800113ad  test    r14, r14
0x1800113b0  jz      short loc_18001140A
0x1800113b2  test    rdi, rdi
0x1800113b5  jz      short loc_1800113D7
0x1800113b7  mov     rcx, gs:60h
0x1800113c0  mov     r8, rdi; P
0x1800113c3  xor     edx, edx; Flags
0x1800113c5  mov     rcx, [rcx+30h]; HeapHandle
0x1800113c9  call    cs:__imp_RtlFreeHeap
0x1800113cf  mov     [rbp+P], 0
0x1800113d7  mov     rcx, [r15+20h]; Handle
0x1800113db  lea     rdx, [rbp+P]
0x1800113df  call    CanonicalizeObjectPathByHandle
0x1800113e4  mov     rdi, [rbp+P]
0x1800113e8  xor     ecx, ecx
0x1800113ea  mov     esi, eax
0x1800113ec  test    eax, eax
0x1800113ee  js      loc_1800116C6
0x1800113f4  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800113f8  mov     rax, r13
0x1800113fb  inc     rax
0x1800113fe  cmp     [rdi+rax*2], cx
0x180011402  jnz     short loc_1800113FB
0x180011404  mov     [r14+8], rax
0x180011408  jmp     short loc_18001140E
0x18001140a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001140e  test    dword ptr [rbx+8], 200h
0x180011415  jz      short loc_180011467
0x180011417  mov     rsi, [rbp+arg_0]
0x18001141b  lea     r8, aSam; "SAM"
0x180011422  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x180011429  lea     rcx, [rsi+480h]
0x180011430  call    SclEtwWriteString
0x180011435  mov     rdx, [r15+20h]
0x180011439  mov     r9, r14
0x18001143c  mov     r8b, r12b
0x18001143f  mov     rcx, rsi
0x180011442  call    SclRegProcessKeyByHandle
0x180011447  mov     rcx, [rbp+arg_0]
0x18001144b  lea     r8, aSam; "SAM"
0x180011452  add     rcx, 480h
0x180011459  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x180011460  mov     esi, eax
0x180011462  call    SclEtwWriteString
0x180011467  test    esi, esi
0x180011469  js      loc_1800116C6
0x18001146f  mov     r14, [rbp+var_20]
0x180011473  test    r12b, r12b
0x180011476  jz      short loc_1800114DC
0x180011478  test    dword ptr [rbx+8], 400h
0x18001147f  jz      loc_180011535
0x180011485  test    r14, r14
0x180011488  jz      short loc_1800114DC
0x18001148a  test    rdi, rdi
0x18001148d  jz      short loc_1800114AF
0x18001148f  mov     rcx, gs:60h
0x180011498  mov     r8, rdi; P
0x18001149b  xor     edx, edx; Flags
0x18001149d  mov     rcx, [rcx+30h]; HeapHandle
0x1800114a1  call    cs:__imp_RtlFreeHeap
0x1800114a7  mov     [rbp+P], 0
0x1800114af  mov     rcx, [r15+28h]; Handle
0x1800114b3  lea     rdx, [rbp+P]
0x1800114b7  call    CanonicalizeObjectPathByHandle
0x1800114bc  mov     rdi, [rbp+P]
0x1800114c0  xor     ecx, ecx
0x1800114c2  mov     esi, eax
0x1800114c4  test    eax, eax
0x1800114c6  js      loc_1800116C6
0x1800114cc  mov     rax, r13
0x1800114cf  inc     rax
0x1800114d2  cmp     [rdi+rax*2], cx
0x1800114d6  jnz     short loc_1800114CF
0x1800114d8  mov     [r14+8], rax
0x1800114dc  test    dword ptr [rbx+8], 400h
0x1800114e3  jz      short loc_180011535
0x1800114e5  mov     rsi, [rbp+arg_0]
0x1800114e9  lea     r8, aSecurity; "SECURITY"
0x1800114f0  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x1800114f7  lea     rcx, [rsi+480h]
0x1800114fe  call    SclEtwWriteString
0x180011503  mov     rdx, [r15+28h]
0x180011507  mov     r9, r14
0x18001150a  mov     r8b, r12b
0x18001150d  mov     rcx, rsi
0x180011510  call    SclRegProcessKeyByHandle
0x180011515  mov     rcx, [rbp+arg_0]
0x180011519  lea     r8, aSecurity; "SECURITY"
0x180011520  add     rcx, 480h
0x180011527  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x18001152e  mov     esi, eax
0x180011530  call    SclEtwWriteString
0x180011535  test    esi, esi
0x180011537  js      loc_1800116C6
0x18001153d  mov     r14, [rbp+var_18]
0x180011541  test    r12b, r12b
0x180011544  jz      short loc_1800115AA
0x180011546  test    dword ptr [rbx+8], 800h
0x18001154d  jz      loc_180011603
0x180011553  test    r14, r14
0x180011556  jz      short loc_1800115AA
0x180011558  test    rdi, rdi
0x18001155b  jz      short loc_18001157D
0x18001155d  mov     rcx, gs:60h
0x180011566  mov     r8, rdi; P
0x180011569  xor     edx, edx; Flags
0x18001156b  mov     rcx, [rcx+30h]; HeapHandle
0x18001156f  call    cs:__imp_RtlFreeHeap
0x180011575  mov     [rbp+P], 0
0x18001157d  mov     rcx, [r15+30h]; Handle
0x180011581  lea     rdx, [rbp+P]
0x180011585  call    CanonicalizeObjectPathByHandle
0x18001158a  mov     rdi, [rbp+P]
0x18001158e  xor     ecx, ecx
0x180011590  mov     esi, eax
0x180011592  test    eax, eax
0x180011594  js      loc_1800116C6
0x18001159a  mov     rax, r13
0x18001159d  inc     rax
0x1800115a0  cmp     [rdi+rax*2], cx
0x1800115a4  jnz     short loc_18001159D
0x1800115a6  mov     [r14+8], rax
0x1800115aa  test    dword ptr [rbx+8], 800h
0x1800115b1  jz      short loc_180011603
0x1800115b3  mov     rsi, [rbp+arg_0]
0x1800115b7  lea     r8, aSoftware; "SOFTWARE"
0x1800115be  lea     rdx, SclEvent_ProcessRegistryHive_Start
0x1800115c5  lea     rcx, [rsi+480h]
0x1800115cc  call    SclEtwWriteString
0x1800115d1  mov     rdx, [r15+30h]
0x1800115d5  mov     r9, r14
0x1800115d8  mov     r8b, r12b
0x1800115db  mov     rcx, rsi
0x1800115de  call    SclRegProcessKeyByHandle
0x1800115e3  mov     rcx, [rbp+arg_0]
0x1800115e7  lea     r8, aSoftware; "SOFTWARE"
0x1800115ee  add     rcx, 480h
0x1800115f5  lea     rdx, SclEvent_ProcessRegistryHive_Stop
0x1800115fc  mov     esi, eax
0x1800115fe  call    SclEtwWriteString
0x180011603  test    esi, esi
0x180011605  js      loc_1800116C6
0x18001160b  mov     r14, [rbp+var_10]
0x18001160f  test    r12b, r12b
0x180011612  jz      short loc_180011672
0x180011614  test    dword ptr [rbx+8], 1000h
0x18001161b  jz      loc_1800116C6
0x180011621  test    r14, r14
0x180011624  jz      short loc_180011672
0x180011626  test    rdi, rdi
0x180011629  jz      short loc_18001164B
0x18001162b  mov     rcx, gs:60h
0x180011634  mov     r8, rdi; P
0x180011637  xor     edx, edx; Flags
0x180011639  mov     rcx, [rcx+30h]; HeapHandle
0x18001163d  call    cs:__imp_RtlFreeHeap
0x180011643  mov     [rbp+P], 0
0x18001164b  mov     rcx, [r15+38h]; Handle
0x18001164f  lea     rdx, [rbp+P]
0x180011653  call    CanonicalizeObjectPathByHandle
0x180011658  mov     rdi, [rbp+P]
  ... truncated ...
```

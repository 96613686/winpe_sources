# SclPendRequest

- ea: `0x180002640`
- end: `0x180002a53`
- name: `SclPendRequest`
- size: `1043`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180005a90`

## callees

- `0x180001010`
- `0x180001970`
- `0x180001cd4`
- `0x180002640`
- `0x180003374`
- `0x18000505c`
- `0x18000540c`
- `0x180006484`
- `0x18000de94`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800027d3`
- `ntdll!RtlLengthSid` at `0x180002811`
- `ntdll!RtlLengthSid` at `0x1800027d3`
- `ntdll!RtlLengthSid` at `0x180002811`
- `ntdll!NtClose` at `0x180002a19`
- `ntdll!NtClose` at `0x180002a19`
- `ntdll!NtFlushKey` at `0x1800029d4`
- `ntdll!NtFlushKey` at `0x1800029d4`

## string_xrefs

- `0x1800027e2`: `SidAccountDomainOld`
- `0x180002820`: `SidAccountDomainNew`

## pseudocode

```c
__int64 __fastcall SclPendRequest(__int64 a1, __int64 a2)
{
  __int64 v4; // r14
  int updated; // ebx
  unsigned int v6; // r11d
  __int16 v7; // cx
  _WORD *v8; // rdx
  __int16 v9; // cx
  _WORD *v10; // rdx
  void *v11; // rcx
  void *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  _WORD *v15; // r8
  __int64 v16; // rdx
  _WORD *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  HANDLE KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+38h] [rbp-C8h]
  PVOID P[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v24[40]; // [rsp+50h] [rbp-B0h] BYREF
  _WORD v25[264]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v26[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  KeyHandle = 0;
  P[0] = 0;
  if ( !(unsigned __int8)SclRequestIsValid(a2, a1) || !(unsigned __int8)SclOSIsValid(a2) )
    return 3221225485LL;
  v4 = -1;
  updated = SclAcquireRequiredPrivileges(P);
  if ( updated >= 0 )
  {
    updated = SclpStateOpenRequestKey(a2, (__int64)&KeyHandle);
    if ( updated >= 0 )
    {
      updated = RtlStringCchCopyW(v25, 260, a1 + 24);
      if ( updated >= 0 )
      {
        updated = RtlStringCchCopyW(v26, v6, a1 + 544);
        if ( updated >= 0 )
        {
          v7 = v25[0];
          if ( v25[0] )
          {
            v8 = v25;
            do
            {
              if ( v7 == 92 )
                *v8 = 124;
              v7 = *++v8;
            }
            while ( *v8 );
          }
          v9 = v26[0];
          if ( v26[0] )
          {
            v10 = v26;
            do
            {
              if ( v9 == 92 )
                *v10 = 124;
              v9 = *++v10;
            }
            while ( *v10 );
          }
          updated = RtlStringCchCopyW(v24, 36, a1 + 1072);
          if ( updated >= 0 )
          {
            v22 = *(_DWORD *)a1 & 0xFF3F;
            updated = SclpStateUpdateRequestField(KeyHandle, L"OperationFlags", 4);
            if ( updated >= 0 )
            {
              v11 = *(void **)(a1 + 8);
              if ( v11 )
                RtlLengthSid(v11);
              updated = SclpStateUpdateRequestField(KeyHandle, L"SidAccountDomainOld", 1567387834);
              if ( updated >= 0 )
              {
                v12 = *(void **)(a1 + 16);
                if ( v12 )
                  RtlLengthSid(v12);
                updated = SclpStateUpdateRequestField(KeyHandle, L"SidAccountDomainNew", 1567387834);
                if ( updated >= 0 )
                {
                  if ( v25[0] )
                  {
                    v13 = -1;
                    do
                      ++v13;
                    while ( v25[v13] );
                  }
                  updated = SclpStateUpdateRequestField(KeyHandle, L"WinDirOld", 1);
                  if ( updated >= 0 )
                  {
                    if ( v26[0] )
                    {
                      v14 = -1;
                      do
                        ++v14;
                      while ( v26[v14] );
                    }
                    updated = SclpStateUpdateRequestField(KeyHandle, L"WinDirNew", 1);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  v15 = *(_WORD **)(a1 + 1064);
  if ( !v15 )
  {
    if ( updated >= 0 )
      goto LABEL_44;
LABEL_51:
    SclReleasePrivileges(P[0]);
    goto LABEL_52;
  }
  if ( updated < 0 )
    goto LABEL_51;
  if ( *v15 )
  {
    v16 = 0;
    v17 = *(_WORD **)(a1 + 1064);
    do
    {
      v18 = -1;
      do
        ++v18;
      while ( v17[v18] );
      if ( v18 )
        v16 += v18 + 1;
      v17 += v18 + 1;
    }
    while ( *v17 );
  }
LABEL_44:
  updated = SclpStateUpdateRequestField(KeyHandle, L"OS Footprint", 7);
  if ( updated < 0 )
    goto LABEL_51;
  if ( v24[0] )
  {
    do
      ++v4;
    while ( v24[v4] );
  }
  updated = SclpStateUpdateRequestField(KeyHandle, L"PartitionName", 1);
  if ( updated < 0 )
    goto LABEL_51;
  updated = NtFlushKey(KeyHandle);
  if ( updated < 0 )
    goto LABEL_51;
  LOBYTE(v19) = (*(_DWORD *)a1 & 0x4019) == 0;
  updated = SclStateEnableBootTimeExecution(a2, v19);
  if ( updated < 0 )
    goto LABEL_51;
  updated = SclReleasePrivileges(P[0]);
LABEL_52:
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180002640  mov     [rsp-8+arg_10], rbx
0x180002645  mov     [rsp-8+arg_18], rsi
0x18000264a  push    rbp
0x18000264b  push    rdi
0x18000264c  push    r12
0x18000264e  push    r14
0x180002650  push    r15
0x180002652  lea     rbp, [rsp-3D0h]
0x18000265a  sub     rsp, 4D0h
0x180002661  mov     rax, cs:__security_cookie
0x180002668  xor     rax, rsp
0x18000266b  mov     [rbp+3F0h+var_30], rax
0x180002672  mov     r15, rdx
0x180002675  mov     rdi, rcx
0x180002678  mov     rdx, rcx
0x18000267b  xor     r12d, r12d
0x18000267e  mov     rcx, r15
0x180002681  mov     [rsp+4F0h+KeyHandle], r12
0x180002686  mov     [rsp+4F0h+P], r12
0x18000268b  call    SclRequestIsValid
0x180002690  test    al, al
0x180002692  jz      loc_180002A23
0x180002698  mov     rcx, r15
0x18000269b  call    SclOSIsValid
0x1800026a0  test    al, al
0x1800026a2  jz      loc_180002A23
0x1800026a8  lea     rcx, [rsp+4F0h+P]
0x1800026ad  call    SclAcquireRequiredPrivileges
0x1800026b2  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800026b6  lea     esi, [r12+2]
0x1800026bb  mov     ebx, eax
0x1800026bd  test    eax, eax
0x1800026bf  js      loc_1800028F3
0x1800026c5  lea     rdx, [rsp+4F0h+KeyHandle]
0x1800026ca  mov     rcx, r15
0x1800026cd  call    SclpStateOpenRequestKey
0x1800026d2  mov     ebx, eax
0x1800026d4  test    eax, eax
0x1800026d6  js      loc_1800028F3
0x1800026dc  mov     r11d, 104h
0x1800026e2  lea     r8, [rdi+18h]
0x1800026e6  mov     edx, r11d
0x1800026e9  lea     rcx, [rbp+3F0h+var_450]
0x1800026ed  call    RtlStringCchCopyW
0x1800026f2  mov     ebx, eax
0x1800026f4  test    eax, eax
0x1800026f6  js      loc_1800028F3
0x1800026fc  lea     r8, [rdi+220h]
0x180002703  mov     edx, r11d
0x180002706  lea     rcx, [rbp+3F0h+var_240]
0x18000270d  call    RtlStringCchCopyW
0x180002712  mov     ebx, eax
0x180002714  test    eax, eax
0x180002716  js      loc_1800028F3
0x18000271c  movzx   ecx, [rbp+3F0h+var_450]
0x180002720  lea     r9d, [r12+5Ch]
0x180002725  lea     r8d, [r12+7Ch]
0x18000272a  cmp     r12w, cx
0x18000272e  jz      short loc_18000274A
0x180002730  lea     rdx, [rbp+3F0h+var_450]
0x180002734  cmp     r9w, cx
0x180002738  jnz     short loc_18000273E
0x18000273a  mov     [rdx], r8w
0x18000273e  add     rdx, rsi
0x180002741  movzx   ecx, word ptr [rdx]
0x180002744  cmp     r12w, cx
0x180002748  jnz     short loc_180002734
0x18000274a  movzx   ecx, [rbp+3F0h+var_240]
0x180002751  cmp     r12w, cx
0x180002755  jz      short loc_180002774
0x180002757  lea     rdx, [rbp+3F0h+var_240]
0x18000275e  cmp     r9w, cx
0x180002762  jnz     short loc_180002768
0x180002764  mov     [rdx], r8w
0x180002768  add     rdx, rsi
0x18000276b  movzx   ecx, word ptr [rdx]
0x18000276e  cmp     r12w, cx
0x180002772  jnz     short loc_18000275E
0x180002774  lea     r8, [rdi+430h]
0x18000277b  mov     edx, 24h ; '$'
0x180002780  lea     rcx, [rsp+4F0h+var_4A0]
0x180002785  call    RtlStringCchCopyW
0x18000278a  mov     ebx, eax
0x18000278c  test    eax, eax
0x18000278e  js      loc_1800028F3
0x180002794  mov     eax, [rdi]
0x180002796  lea     r8, [rsp+4F0h+var_4B8]
0x18000279b  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800027a0  lea     rdx, aOperationflags; "OperationFlags"
0x1800027a7  and     eax, 0FF3Fh
0x1800027ac  mov     r9d, 4
0x1800027b2  mov     [rsp+4F0h+var_4B8], eax
0x1800027b6  mov     [rsp+4F0h+var_4D0], r9d; int
0x1800027bb  call    SclpStateUpdateRequestField
0x1800027c0  mov     ebx, eax
0x1800027c2  test    eax, eax
0x1800027c4  js      loc_1800028F3
0x1800027ca  mov     rcx, [rdi+8]; Sid
0x1800027ce  test    rcx, rcx
0x1800027d1  jz      short loc_1800027DB
0x1800027d3  call    cs:__imp_RtlLengthSid
0x1800027d9  jmp     short loc_1800027DE
0x1800027db  mov     eax, r12d
0x1800027de  mov     r8, [rdi+8]
0x1800027e2  lea     rdx, aSidaccountdoma; "SidAccountDomainOld"
0x1800027e9  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800027ee  mov     r9d, eax
0x1800027f1  mov     [rsp+4F0h+var_4D0], 5D6C70BAh; int
0x1800027f9  call    SclpStateUpdateRequestField
0x1800027fe  mov     ebx, eax
0x180002800  test    eax, eax
0x180002802  js      loc_1800028F3
0x180002808  mov     rcx, [rdi+10h]; Sid
0x18000280c  test    rcx, rcx
0x18000280f  jz      short loc_180002819
0x180002811  call    cs:__imp_RtlLengthSid
0x180002817  jmp     short loc_18000281C
0x180002819  mov     eax, r12d
0x18000281c  mov     r8, [rdi+10h]
0x180002820  lea     rdx, aSidaccountdoma_0; "SidAccountDomainNew"
0x180002827  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x18000282c  mov     r9d, eax
0x18000282f  mov     [rsp+4F0h+var_4D0], 5D6C70BAh; int
0x180002837  call    SclpStateUpdateRequestField
0x18000283c  mov     ebx, eax
0x18000283e  test    eax, eax
0x180002840  js      loc_1800028F3
0x180002846  movzx   ecx, [rbp+3F0h+var_450]
0x18000284a  cmp     r12w, cx
0x18000284e  jz      short loc_18000286B
0x180002850  lea     rdx, [rbp+3F0h+var_450]
0x180002854  mov     rax, r14
0x180002857  inc     rax
0x18000285a  cmp     [rdx+rax*2], r12w
0x18000285f  jnz     short loc_180002857
0x180002861  lea     r9, ds:2[rax*2]
0x180002869  jmp     short loc_18000286E
0x18000286b  mov     r9, r12
0x18000286e  xor     edx, edx
0x180002870  mov     [rsp+4F0h+var_4D0], 1; int
0x180002878  cmp     dx, cx
0x18000287b  lea     r8, [rbp+3F0h+var_450]
0x18000287f  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180002884  lea     rdx, aWindirold; "WinDirOld"
0x18000288b  cmovz   r8, r12
0x18000288f  call    SclpStateUpdateRequestField
0x180002894  mov     ebx, eax
0x180002896  test    eax, eax
0x180002898  js      short loc_1800028F3
0x18000289a  movzx   ecx, [rbp+3F0h+var_240]
0x1800028a1  cmp     r12w, cx
0x1800028a5  jz      short loc_1800028C5
0x1800028a7  lea     rdx, [rbp+3F0h+var_240]
0x1800028ae  mov     rax, r14
0x1800028b1  inc     rax
0x1800028b4  cmp     [rdx+rax*2], r12w
0x1800028b9  jnz     short loc_1800028B1
0x1800028bb  lea     r9, ds:2[rax*2]
0x1800028c3  jmp     short loc_1800028C8
0x1800028c5  mov     r9, r12
0x1800028c8  xor     edx, edx
0x1800028ca  mov     [rsp+4F0h+var_4D0], 1; int
0x1800028d2  cmp     dx, cx
0x1800028d5  lea     r8, [rbp+3F0h+var_240]
0x1800028dc  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800028e1  lea     rdx, aWindirnew; "WinDirNew"
0x1800028e8  cmovz   r8, r12
0x1800028ec  call    SclpStateUpdateRequestField
0x1800028f1  mov     ebx, eax
0x1800028f3  mov     r8, [rdi+428h]
0x1800028fa  test    r8, r8
0x1800028fd  jz      short loc_180002942
0x1800028ff  test    ebx, ebx
0x180002901  js      loc_180002A05
0x180002907  cmp     r12w, [r8]
0x18000290b  jz      short loc_180002955
0x18000290d  mov     rdx, r12
0x180002910  mov     rcx, r8
0x180002913  mov     rax, r14
0x180002916  inc     rax
0x180002919  cmp     [rcx+rax*2], r12w
0x18000291e  jnz     short loc_180002916
0x180002920  test    rax, rax
0x180002923  jz      short loc_18000292B
0x180002925  inc     rdx
0x180002928  add     rdx, rax
0x18000292b  lea     rcx, [rcx+rax*2]
0x18000292f  add     rcx, rsi
0x180002932  cmp     r12w, [rcx]
0x180002936  jnz     short loc_180002913
0x180002938  lea     rsi, ds:2[rdx*2]
0x180002940  jmp     short loc_18000294D
0x180002942  mov     rsi, r12
0x180002945  test    ebx, ebx
0x180002947  js      loc_180002A05
0x18000294d  test    rsi, rsi
0x180002950  jnz     short loc_180002955
0x180002952  mov     r8, r12
0x180002955  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x18000295a  lea     rdx, aOsFootprint; "OS Footprint"
0x180002961  mov     r9, rsi
0x180002964  mov     [rsp+4F0h+var_4D0], 7; int
0x18000296c  call    SclpStateUpdateRequestField
0x180002971  mov     ebx, eax
0x180002973  test    eax, eax
0x180002975  js      loc_180002A05
0x18000297b  movzx   ecx, [rsp+4F0h+var_4A0]
0x180002980  cmp     r12w, cx
0x180002984  jz      short loc_18000299F
0x180002986  lea     rax, [rsp+4F0h+var_4A0]
0x18000298b  inc     r14
0x18000298e  cmp     [rax+r14*2], r12w
0x180002993  jnz     short loc_18000298B
0x180002995  lea     r9, ds:2[r14*2]
0x18000299d  jmp     short loc_1800029A2
0x18000299f  mov     r9, r12
0x1800029a2  xor     edx, edx
0x1800029a4  mov     [rsp+4F0h+var_4D0], 1; int
0x1800029ac  cmp     dx, cx
0x1800029af  lea     r8, [rsp+4F0h+var_4A0]
0x1800029b4  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800029b9  lea     rdx, aPartitionname; "PartitionName"
0x1800029c0  cmovz   r8, r12
0x1800029c4  call    SclpStateUpdateRequestField
0x1800029c9  mov     ebx, eax
0x1800029cb  test    eax, eax
0x1800029cd  js      short loc_180002A05
0x1800029cf  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x1800029d4  call    cs:__imp_NtFlushKey
0x1800029da  mov     ebx, eax
0x1800029dc  test    eax, eax
0x1800029de  js      short loc_180002A05
0x1800029e0  test    dword ptr [rdi], 4019h
0x1800029e6  mov     rcx, r15
0x1800029e9  setz    dl
0x1800029ec  call    SclStateEnableBootTimeExecution
0x1800029f1  mov     ebx, eax
0x1800029f3  test    eax, eax
0x1800029f5  js      short loc_180002A05
0x1800029f7  mov     rcx, [rsp+4F0h+P]; P
0x1800029fc  call    SclReleasePrivileges
0x180002a01  mov     ebx, eax
0x180002a03  jmp     short loc_180002A0F
0x180002a05  mov     rcx, [rsp+4F0h+P]; P
0x180002a0a  call    SclReleasePrivileges
0x180002a0f  mov     rcx, [rsp+4F0h+KeyHandle]; Handle
0x180002a14  test    rcx, rcx
0x180002a17  jz      short loc_180002A1F
0x180002a19  call    cs:__imp_NtClose
0x180002a1f  mov     eax, ebx
0x180002a21  jmp     short loc_180002A28
0x180002a23  mov     eax, 0C000000Dh
0x180002a28  mov     rcx, [rbp+3F0h+var_30]
0x180002a2f  xor     rcx, rsp; StackCookie
0x180002a32  call    __security_check_cookie
0x180002a37  lea     r11, [rsp+4F0h+var_20]
0x180002a3f  mov     rbx, [r11+40h]
0x180002a43  mov     rsi, [r11+48h]
0x180002a47  mov     rsp, r11
0x180002a4a  pop     r15
0x180002a4c  pop     r14
0x180002a4e  pop     r12
0x180002a50  pop     rdi
0x180002a51  pop     rbp
0x180002a52  retn
```

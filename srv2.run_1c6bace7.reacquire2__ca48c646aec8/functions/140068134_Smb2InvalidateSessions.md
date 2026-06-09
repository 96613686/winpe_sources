# Smb2InvalidateSessions

- ea: `0x140068134`
- end: `0x140068557`
- name: `Smb2InvalidateSessions`
- size: `1059`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400766cc`
- `0x140092240`

## callees

- `0x140005070`
- `0x14000c450`
- `0x140012c30`
- `0x140013920`
- `0x14002019c`
- `0x140022690`
- `0x140030244`
- `0x14003037c`
- `0x140037c24`
- `0x140038490`
- `0x14005a364`
- `0x140068014`
- `0x140068134`
- `0x140077020`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006816b`
- `ntoskrnl!ExAllocatePool2` at `0x14006816b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068324`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140068324`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068514`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068514`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400684a9`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400684a9`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400681cf`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400681cf`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140068280`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140068280`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006822f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006822f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400682db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400683ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068486`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400682db`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400683ef`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068486`
- `ntoskrnl!RtlEqualSid` at `0x140068262`
- `ntoskrnl!RtlEqualSid` at `0x140068262`

## string_xrefs

- `0x140068304`: `Srv2PostToThreadPool`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateSessions(__int64 a1)
{
  struct _EX_RUNDOWN_REF *Pool2; // r14
  __int64 result; // rax
  _QWORD *v4; // rsi
  __int64 v5; // rbx
  char v6; // r12
  unsigned int i; // r15d
  _QWORD *v8; // rdi
  __int64 SessionGlobal; // rax
  __int64 v10; // rdx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rbp
  int SessionSelfUserSid; // esi
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rdi
  bool v20; // zf
  __int64 v21; // rsi
  USHORT CurrentNodeNumber; // ax
  __int64 v23; // r8
  char v24; // si
  int v25; // eax
  __int64 v26; // rcx
  int v27; // [rsp+20h] [rbp-3B8h]
  __int64 v28; // [rsp+30h] [rbp-3A8h]
  __int64 Instance; // [rsp+38h] [rbp-3A0h]
  _QWORD v30[2]; // [rsp+40h] [rbp-398h] BYREF
  _BYTE Sid1[816]; // [rsp+50h] [rbp-388h] BYREF

  Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(66, 8, 1932677964);
  if ( !Pool2 )
    return 3221225626LL;
  Instance = Srv2GetInstance(0);
  v4 = (_QWORD *)Instance;
  if ( !Instance )
    return 3231186949LL;
  v5 = 0;
  v6 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    v5 = MEMORY[0xFFFFF78000000014];
  ExInitializeRundownProtection(Pool2);
  for ( i = 0; i < *(_DWORD *)(a1 + 4); ++i )
  {
    v8 = (_QWORD *)(88LL * i + a1 + 24);
    v28 = 88LL * i;
    SessionGlobal = Smb2FindSessionGlobal(v4[20], *v8);
    v13 = SessionGlobal;
    if ( SessionGlobal )
    {
      SessionSelfUserSid = Smb2GetSessionSelfUserSid(SessionGlobal, v10, Sid1);
      ExAcquirePushLockExclusiveEx(*(_QWORD *)(v13 + 24) + 80LL, 0);
      if ( *(_QWORD *)(v13 + 200) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 21, v15, *v8);
        }
        *(_DWORD *)(v28 + a1 + 36) = 0;
      }
      else
      {
        if ( SessionSelfUserSid >= 0 && RtlEqualSid(Sid1, (PSID)(a1 + v28 + 40)) )
        {
          *(_QWORD *)(v13 + 200) = Pool2;
          if ( !ExAcquireRundownProtection(Pool2) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids);
            }
            ExReleasePushLockExclusiveEx(*(_QWORD *)(v13 + 24) + 80LL, 0);
            Smb2DereferenceSession(v13);
            v4 = (_QWORD *)Instance;
            goto LABEL_44;
          }
          v6 = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qdi(WPP_GLOBAL_Control->AttachedDevice, v16, v17, v13, i, *v8);
          }
          ExReleasePushLockExclusiveEx(*(_QWORD *)(v13 + 24) + 80LL, 0);
          v19 = *(_QWORD *)(v13 + 24);
          v20 = *(_DWORD *)(v19 + 8) == 5;
          *(_DWORD *)(v19 + 72) = 0;
          if ( v20 )
          {
            LOBYTE(v27) = 1;
            LOBYTE(v18) = 1;
            SRV2_PERF_ENTER_EX(v19 + 584, v18, 391, "Srv2PostToThreadPool", v27);
          }
          v21 = *(_QWORD *)(*(_QWORD *)(v19 + 64) + 136LL);
          CurrentNodeNumber = KeGetCurrentNodeNumber();
          LOBYTE(v23) = 1;
          RfspThreadPoolNodeQueueWorkItem(*(_QWORD *)(v21 + 8LL * CurrentNodeNumber + 8), v19 + 32, v23);
          v24 = 0;
          v25 = 0;
        }
        else
        {
          v24 = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 20, v15, *v8);
          }
          v25 = -1073741790;
        }
        *(_DWORD *)(v28 + a1 + 36) = v25;
        if ( !v24 )
          goto LABEL_27;
      }
      ExReleasePushLockExclusiveEx(*(_QWORD *)(v13 + 24) + 80LL, 0);
      Smb2DereferenceSession(v13);
LABEL_27:
      v4 = (_QWORD *)Instance;
      continue;
    }
    v26 = v4[20];
    v30[0] = 88LL * i + a1 + 24;
    v30[1] = Pool2;
    if ( (int)RfsHashTableLookupAndProcess(*(_QWORD *)(v26 + 2176), (_DWORD)v8, v11, v12, (__int64)v30) >= 0 )
      v6 = 1;
  }
  if ( !v6 )
    goto LABEL_45;
LABEL_44:
  ExWaitForRundownProtectionRelease(Pool2);
LABEL_45:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids,
      MEMORY[0xFFFFF78000000014] - v5,
      v5);
  }
  ExFreePoolWithTag(Pool2, 0);
  Srv2DereferenceInstance(v4);
  result = 0;
  *(_DWORD *)(a1 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x140068134  push    rbx
0x140068136  push    rbp
0x140068137  push    rsi
0x140068138  push    rdi
0x140068139  push    r12
0x14006813b  push    r13
0x14006813d  push    r14
0x14006813f  push    r15
0x140068141  sub     rsp, 398h
0x140068148  mov     rax, cs:__security_cookie
0x14006814f  xor     rax, rsp
0x140068152  mov     [rsp+3D8h+var_58], rax
0x14006815a  mov     edx, 8
0x14006815f  mov     r13, rcx
0x140068162  mov     r8d, 7332534Ch
0x140068168  lea     ecx, [rdx+3Ah]
0x14006816b  call    cs:__imp_ExAllocatePool2
0x140068172  nop     dword ptr [rax+rax+00h]
0x140068177  mov     r14, rax
0x14006817a  test    rax, rax
0x14006817d  jnz     short loc_140068189
0x14006817f  mov     eax, 0C000009Ah
0x140068184  jmp     loc_140068532
0x140068189  xor     ecx, ecx
0x14006818b  call    Srv2GetInstance
0x140068190  mov     [rsp+3D8h+var_3A0], rax
0x140068195  mov     rsi, rax
0x140068198  test    rax, rax
0x14006819b  jnz     short loc_1400681A7
0x14006819d  mov     eax, 0C0980005h
0x1400681a2  jmp     loc_140068532
0x1400681a7  mov     rax, cs:WPP_GLOBAL_Control
0x1400681ae  xor     ebx, ebx
0x1400681b0  xor     r12b, r12b
0x1400681b3  mov     rbp, 0FFFFF78000000014h
0x1400681bd  mov     ecx, [rax+2Ch]
0x1400681c0  lea     edi, [rbx+1]
0x1400681c3  test    dil, cl
0x1400681c6  jz      short loc_1400681CC
0x1400681c8  mov     rbx, [rbp+0]
0x1400681cc  mov     rcx, r14; RunRef
0x1400681cf  call    cs:__imp_ExInitializeRundownProtection
0x1400681d6  nop     dword ptr [rax+rax+00h]
0x1400681db  xor     r15d, r15d
0x1400681de  cmp     r15d, [r13+4]
0x1400681e2  jnb     loc_1400684A1
0x1400681e8  mov     rcx, [rsi+0A0h]
0x1400681ef  lea     rdi, [r13+18h]
0x1400681f3  mov     eax, r15d
0x1400681f6  imul    rax, 58h ; 'X'
0x1400681fa  add     rdi, rax
0x1400681fd  mov     [rsp+3D8h+var_3A8], rax
0x140068202  mov     rdx, [rdi]
0x140068205  call    Smb2FindSessionGlobal
0x14006820a  mov     rbp, rax
0x14006820d  test    rax, rax
0x140068210  jz      loc_140068405
0x140068216  lea     r8, [rsp+3D8h+Sid1]
0x14006821b  mov     rcx, rax
0x14006821e  call    Smb2GetSessionSelfUserSid
0x140068223  mov     rcx, [rbp+18h]
0x140068227  xor     edx, edx
0x140068229  add     rcx, 50h ; 'P'
0x14006822d  mov     esi, eax
0x14006822f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140068236  nop     dword ptr [rax+rax+00h]
0x14006823b  cmp     qword ptr [rbp+0C8h], 0
0x140068243  jnz     loc_1400683A6
0x140068249  test    esi, esi
0x14006824b  js      loc_14006834B
0x140068251  mov     rdx, [rsp+3D8h+var_3A8]
0x140068256  lea     rcx, [rsp+3D8h+Sid1]; Sid1
0x14006825b  add     rdx, 28h ; '('
0x14006825f  add     rdx, r13; Sid2
0x140068262  call    cs:__imp_RtlEqualSid
0x140068269  nop     dword ptr [rax+rax+00h]
0x14006826e  test    al, al
0x140068270  jz      loc_14006834B
0x140068276  mov     rcx, r14; RunRef
0x140068279  mov     [rbp+0C8h], r14
0x140068280  call    cs:__imp_ExAcquireRundownProtection
0x140068287  nop     dword ptr [rax+rax+00h]
0x14006828c  test    al, al
0x14006828e  jz      loc_140068443
0x140068294  mov     r12b, 1
0x140068297  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006829e  lea     rax, WPP_GLOBAL_Control
0x1400682a5  cmp     rcx, rax
0x1400682a8  jz      short loc_1400682D1
0x1400682aa  mov     eax, [rcx+2Ch]
0x1400682ad  test    r12b, al
0x1400682b0  jz      short loc_1400682D1
0x1400682b2  cmp     byte ptr [rcx+29h], 2
0x1400682b6  jb      short loc_1400682D1
0x1400682b8  mov     rax, [rdi]
0x1400682bb  mov     r9, rbp
0x1400682be  mov     rcx, [rcx+18h]
0x1400682c2  mov     [rsp+3D8h+var_3B0], rax
0x1400682c7  mov     dword ptr [rsp+3D8h+var_3B8], r15d
0x1400682cc  call    WPP_SF_qdi
0x1400682d1  mov     rcx, [rbp+18h]
0x1400682d5  xor     edx, edx
0x1400682d7  add     rcx, 50h ; 'P'
0x1400682db  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400682e2  nop     dword ptr [rax+rax+00h]
0x1400682e7  mov     rdi, [rbp+18h]
0x1400682eb  cmp     dword ptr [rdi+8], 5
0x1400682ef  mov     dword ptr [rdi+48h], 0
0x1400682f6  jnz     short loc_140068319
0x1400682f8  lea     rcx, [rdi+248h]
0x1400682ff  mov     byte ptr [rsp+3D8h+var_3B8], r12b
0x140068304  lea     r9, SourceString; "Srv2PostToThreadPool"
0x14006830b  mov     r8d, 187h
0x140068311  mov     dl, r12b
0x140068314  call    SRV2_PERF_ENTER_EX
0x140068319  mov     rax, [rdi+40h]
0x14006831d  mov     rsi, [rax+88h]
0x140068324  call    cs:__imp_KeGetCurrentNodeNumber
0x14006832b  nop     dword ptr [rax+rax+00h]
0x140068330  movzx   ecx, ax
0x140068333  mov     r8b, r12b
0x140068336  lea     rdx, [rdi+20h]
0x14006833a  mov     rcx, [rsi+rcx*8+8]
0x14006833f  call    RfspThreadPoolNodeQueueWorkItem
0x140068344  xor     sil, sil
0x140068347  xor     eax, eax
0x140068349  jmp     short loc_140068385
0x14006834b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068352  lea     rax, WPP_GLOBAL_Control
0x140068359  mov     sil, 1
0x14006835c  cmp     rcx, rax
0x14006835f  jz      short loc_140068380
0x140068361  mov     eax, [rcx+2Ch]
0x140068364  test    sil, al
0x140068367  jz      short loc_140068380
0x140068369  cmp     byte ptr [rcx+29h], 2
0x14006836d  jb      short loc_140068380
0x14006836f  mov     r9, [rdi]
0x140068372  mov     edx, 14h
0x140068377  mov     rcx, [rcx+18h]
0x14006837b  call    WPP_SF_i
0x140068380  mov     eax, 0C0000022h
0x140068385  mov     rcx, [rsp+3D8h+var_3A8]
0x14006838a  mov     [rcx+r13+24h], eax
0x14006838f  test    sil, sil
0x140068392  jnz     short loc_1400683E5
0x140068394  mov     rsi, [rsp+3D8h+var_3A0]
0x140068399  mov     edi, 1
0x14006839e  add     r15d, edi
0x1400683a1  jmp     loc_1400681DE
0x1400683a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400683ad  lea     rax, WPP_GLOBAL_Control
0x1400683b4  cmp     rcx, rax
0x1400683b7  jz      short loc_1400683D7
0x1400683b9  mov     eax, [rcx+2Ch]
0x1400683bc  test    al, 1
0x1400683be  jz      short loc_1400683D7
0x1400683c0  cmp     byte ptr [rcx+29h], 2
0x1400683c4  jb      short loc_1400683D7
0x1400683c6  mov     r9, [rdi]
0x1400683c9  mov     edx, 15h
0x1400683ce  mov     rcx, [rcx+18h]
0x1400683d2  call    WPP_SF_i
0x1400683d7  mov     rax, [rsp+3D8h+var_3A8]
0x1400683dc  mov     dword ptr [rax+r13+24h], 0
0x1400683e5  mov     rcx, [rbp+18h]
0x1400683e9  xor     edx, edx
0x1400683eb  add     rcx, 50h ; 'P'
0x1400683ef  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400683f6  nop     dword ptr [rax+rax+00h]
0x1400683fb  mov     rcx, rbp
0x1400683fe  call    Smb2DereferenceSession
0x140068403  jmp     short loc_140068394
0x140068405  mov     rcx, [rsi+0A0h]
0x14006840c  lea     rax, [rsp+3D8h+var_398]
0x140068411  mov     [rsp+3D8h+var_398], rdi
0x140068416  mov     rdx, rdi
0x140068419  mov     [rsp+3D8h+var_390], r14
0x14006841e  mov     [rsp+3D8h+var_3B8], rax
0x140068423  mov     rcx, [rcx+880h]
0x14006842a  call    RfsHashTableLookupAndProcess
0x14006842f  test    eax, eax
0x140068431  movzx   r12d, r12b
0x140068435  mov     edi, 1
0x14006843a  cmovns  r12d, edi
0x14006843e  jmp     loc_14006839E
0x140068443  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006844a  lea     rax, WPP_GLOBAL_Control
0x140068451  mov     edi, 1
0x140068456  cmp     rcx, rax
0x140068459  jz      short loc_14006847C
0x14006845b  mov     eax, [rcx+2Ch]
0x14006845e  test    dil, al
0x140068461  jz      short loc_14006847C
0x140068463  cmp     byte ptr [rcx+29h], 2
0x140068467  jb      short loc_14006847C
0x140068469  mov     rcx, [rcx+18h]
0x14006846d  lea     edx, [rdi+11h]
0x140068470  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x140068477  call    WPP_SF_
0x14006847c  mov     rcx, [rbp+18h]
0x140068480  xor     edx, edx
0x140068482  add     rcx, 50h ; 'P'
0x140068486  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006848d  nop     dword ptr [rax+rax+00h]
0x140068492  mov     rcx, rbp
0x140068495  call    Smb2DereferenceSession
0x14006849a  mov     rsi, [rsp+3D8h+var_3A0]
0x14006849f  jmp     short loc_1400684A6
0x1400684a1  test    r12b, r12b
0x1400684a4  jz      short loc_1400684B5
0x1400684a6  mov     rcx, r14; RunRef
0x1400684a9  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400684b0  nop     dword ptr [rax+rax+00h]
0x1400684b5  mov     rax, cs:WPP_GLOBAL_Control
0x1400684bc  mov     ecx, [rax+2Ch]
0x1400684bf  test    dil, cl
0x1400684c2  jz      short loc_14006850F
0x1400684c4  mov     r9, 0FFFFF78000000014h
0x1400684ce  mov     r9, [r9]
0x1400684d1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400684d8  lea     rax, WPP_GLOBAL_Control
0x1400684df  cmp     rcx, rax
0x1400684e2  jz      short loc_14006850F
0x1400684e4  mov     eax, [rcx+2Ch]
0x1400684e7  test    dil, al
0x1400684ea  jz      short loc_14006850F
0x1400684ec  cmp     byte ptr [rcx+29h], 2
0x1400684f0  jb      short loc_14006850F
0x1400684f2  mov     rcx, [rcx+18h]
0x1400684f6  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x1400684fd  sub     r9, rbx
0x140068500  mov     [rsp+3D8h+var_3B8], rbx
0x140068505  mov     edx, 16h
0x14006850a  call    WPP_SF_qq
0x14006850f  xor     edx, edx; Tag
0x140068511  mov     rcx, r14; P
0x140068514  call    cs:__imp_ExFreePoolWithTag
0x14006851b  nop     dword ptr [rax+rax+00h]
0x140068520  mov     rcx, rsi; Context
0x140068523  call    Srv2DereferenceInstance
0x140068528  xor     eax, eax
0x14006852a  mov     dword ptr [r13+10h], 0
0x140068532  mov     rcx, [rsp+3D8h+var_58]
0x14006853a  xor     rcx, rsp; StackCookie
0x14006853d  call    __security_check_cookie
0x140068542  add     rsp, 398h
0x140068549  pop     r15
0x14006854b  pop     r14
0x14006854d  pop     r13
0x14006854f  pop     r12
0x140068551  pop     rdi
0x140068552  pop     rsi
0x140068553  pop     rbp
0x140068554  pop     rbx
0x140068555  retn
```

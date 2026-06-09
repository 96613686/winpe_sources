# Smb2InvalidateSessions

- ea: `0x1400680e4`
- end: `0x140068507`
- name: `Smb2InvalidateSessions`
- size: `1059`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14007667c`
- `0x1400921f0`

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
- `0x140067fc4`
- `0x1400680e4`
- `0x140076fd0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006811b`
- `ntoskrnl!ExAllocatePool2` at `0x14006811b`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400682d4`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400682d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400684c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400684c4`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140068459`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140068459`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006817f`
- `ntoskrnl!ExInitializeRundownProtection` at `0x14006817f`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140068230`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140068230`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400681df`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400681df`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006828b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006839f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068436`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006828b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006839f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140068436`
- `ntoskrnl!RtlEqualSid` at `0x140068212`
- `ntoskrnl!RtlEqualSid` at `0x140068212`

## string_xrefs

- `0x1400682b4`: `Srv2PostToThreadPool`

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
0x1400680e4  push    rbx
0x1400680e6  push    rbp
0x1400680e7  push    rsi
0x1400680e8  push    rdi
0x1400680e9  push    r12
0x1400680eb  push    r13
0x1400680ed  push    r14
0x1400680ef  push    r15
0x1400680f1  sub     rsp, 398h
0x1400680f8  mov     rax, cs:__security_cookie
0x1400680ff  xor     rax, rsp
0x140068102  mov     [rsp+3D8h+var_58], rax
0x14006810a  mov     edx, 8
0x14006810f  mov     r13, rcx
0x140068112  mov     r8d, 7332534Ch
0x140068118  lea     ecx, [rdx+3Ah]
0x14006811b  call    cs:__imp_ExAllocatePool2
0x140068122  nop     dword ptr [rax+rax+00h]
0x140068127  mov     r14, rax
0x14006812a  test    rax, rax
0x14006812d  jnz     short loc_140068139
0x14006812f  mov     eax, 0C000009Ah
0x140068134  jmp     loc_1400684E2
0x140068139  xor     ecx, ecx
0x14006813b  call    Srv2GetInstance
0x140068140  mov     [rsp+3D8h+var_3A0], rax
0x140068145  mov     rsi, rax
0x140068148  test    rax, rax
0x14006814b  jnz     short loc_140068157
0x14006814d  mov     eax, 0C0980005h
0x140068152  jmp     loc_1400684E2
0x140068157  mov     rax, cs:WPP_GLOBAL_Control
0x14006815e  xor     ebx, ebx
0x140068160  xor     r12b, r12b
0x140068163  mov     rbp, 0FFFFF78000000014h
0x14006816d  mov     ecx, [rax+2Ch]
0x140068170  lea     edi, [rbx+1]
0x140068173  test    dil, cl
0x140068176  jz      short loc_14006817C
0x140068178  mov     rbx, [rbp+0]
0x14006817c  mov     rcx, r14; RunRef
0x14006817f  call    cs:__imp_ExInitializeRundownProtection
0x140068186  nop     dword ptr [rax+rax+00h]
0x14006818b  xor     r15d, r15d
0x14006818e  cmp     r15d, [r13+4]
0x140068192  jnb     loc_140068451
0x140068198  mov     rcx, [rsi+0A0h]
0x14006819f  lea     rdi, [r13+18h]
0x1400681a3  mov     eax, r15d
0x1400681a6  imul    rax, 58h ; 'X'
0x1400681aa  add     rdi, rax
0x1400681ad  mov     [rsp+3D8h+var_3A8], rax
0x1400681b2  mov     rdx, [rdi]
0x1400681b5  call    Smb2FindSessionGlobal
0x1400681ba  mov     rbp, rax
0x1400681bd  test    rax, rax
0x1400681c0  jz      loc_1400683B5
0x1400681c6  lea     r8, [rsp+3D8h+Sid1]
0x1400681cb  mov     rcx, rax
0x1400681ce  call    Smb2GetSessionSelfUserSid
0x1400681d3  mov     rcx, [rbp+18h]
0x1400681d7  xor     edx, edx
0x1400681d9  add     rcx, 50h ; 'P'
0x1400681dd  mov     esi, eax
0x1400681df  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400681e6  nop     dword ptr [rax+rax+00h]
0x1400681eb  cmp     qword ptr [rbp+0C8h], 0
0x1400681f3  jnz     loc_140068356
0x1400681f9  test    esi, esi
0x1400681fb  js      loc_1400682FB
0x140068201  mov     rdx, [rsp+3D8h+var_3A8]
0x140068206  lea     rcx, [rsp+3D8h+Sid1]; Sid1
0x14006820b  add     rdx, 28h ; '('
0x14006820f  add     rdx, r13; Sid2
0x140068212  call    cs:__imp_RtlEqualSid
0x140068219  nop     dword ptr [rax+rax+00h]
0x14006821e  test    al, al
0x140068220  jz      loc_1400682FB
0x140068226  mov     rcx, r14; RunRef
0x140068229  mov     [rbp+0C8h], r14
0x140068230  call    cs:__imp_ExAcquireRundownProtection
0x140068237  nop     dword ptr [rax+rax+00h]
0x14006823c  test    al, al
0x14006823e  jz      loc_1400683F3
0x140068244  mov     r12b, 1
0x140068247  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006824e  lea     rax, WPP_GLOBAL_Control
0x140068255  cmp     rcx, rax
0x140068258  jz      short loc_140068281
0x14006825a  mov     eax, [rcx+2Ch]
0x14006825d  test    r12b, al
0x140068260  jz      short loc_140068281
0x140068262  cmp     byte ptr [rcx+29h], 2
0x140068266  jb      short loc_140068281
0x140068268  mov     rax, [rdi]
0x14006826b  mov     r9, rbp
0x14006826e  mov     rcx, [rcx+18h]
0x140068272  mov     [rsp+3D8h+var_3B0], rax
0x140068277  mov     dword ptr [rsp+3D8h+var_3B8], r15d
0x14006827c  call    WPP_SF_qdi
0x140068281  mov     rcx, [rbp+18h]
0x140068285  xor     edx, edx
0x140068287  add     rcx, 50h ; 'P'
0x14006828b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140068292  nop     dword ptr [rax+rax+00h]
0x140068297  mov     rdi, [rbp+18h]
0x14006829b  cmp     dword ptr [rdi+8], 5
0x14006829f  mov     dword ptr [rdi+48h], 0
0x1400682a6  jnz     short loc_1400682C9
0x1400682a8  lea     rcx, [rdi+248h]
0x1400682af  mov     byte ptr [rsp+3D8h+var_3B8], r12b
0x1400682b4  lea     r9, SourceString; "Srv2PostToThreadPool"
0x1400682bb  mov     r8d, 187h
0x1400682c1  mov     dl, r12b
0x1400682c4  call    SRV2_PERF_ENTER_EX
0x1400682c9  mov     rax, [rdi+40h]
0x1400682cd  mov     rsi, [rax+88h]
0x1400682d4  call    cs:__imp_KeGetCurrentNodeNumber
0x1400682db  nop     dword ptr [rax+rax+00h]
0x1400682e0  movzx   ecx, ax
0x1400682e3  mov     r8b, r12b
0x1400682e6  lea     rdx, [rdi+20h]
0x1400682ea  mov     rcx, [rsi+rcx*8+8]
0x1400682ef  call    RfspThreadPoolNodeQueueWorkItem
0x1400682f4  xor     sil, sil
0x1400682f7  xor     eax, eax
0x1400682f9  jmp     short loc_140068335
0x1400682fb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068302  lea     rax, WPP_GLOBAL_Control
0x140068309  mov     sil, 1
0x14006830c  cmp     rcx, rax
0x14006830f  jz      short loc_140068330
0x140068311  mov     eax, [rcx+2Ch]
0x140068314  test    sil, al
0x140068317  jz      short loc_140068330
0x140068319  cmp     byte ptr [rcx+29h], 2
0x14006831d  jb      short loc_140068330
0x14006831f  mov     r9, [rdi]
0x140068322  mov     edx, 14h
0x140068327  mov     rcx, [rcx+18h]
0x14006832b  call    WPP_SF_i
0x140068330  mov     eax, 0C0000022h
0x140068335  mov     rcx, [rsp+3D8h+var_3A8]
0x14006833a  mov     [rcx+r13+24h], eax
0x14006833f  test    sil, sil
0x140068342  jnz     short loc_140068395
0x140068344  mov     rsi, [rsp+3D8h+var_3A0]
0x140068349  mov     edi, 1
0x14006834e  add     r15d, edi
0x140068351  jmp     loc_14006818E
0x140068356  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14006835d  lea     rax, WPP_GLOBAL_Control
0x140068364  cmp     rcx, rax
0x140068367  jz      short loc_140068387
0x140068369  mov     eax, [rcx+2Ch]
0x14006836c  test    al, 1
0x14006836e  jz      short loc_140068387
0x140068370  cmp     byte ptr [rcx+29h], 2
0x140068374  jb      short loc_140068387
0x140068376  mov     r9, [rdi]
0x140068379  mov     edx, 15h
0x14006837e  mov     rcx, [rcx+18h]
0x140068382  call    WPP_SF_i
0x140068387  mov     rax, [rsp+3D8h+var_3A8]
0x14006838c  mov     dword ptr [rax+r13+24h], 0
0x140068395  mov     rcx, [rbp+18h]
0x140068399  xor     edx, edx
0x14006839b  add     rcx, 50h ; 'P'
0x14006839f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400683a6  nop     dword ptr [rax+rax+00h]
0x1400683ab  mov     rcx, rbp
0x1400683ae  call    Smb2DereferenceSession
0x1400683b3  jmp     short loc_140068344
0x1400683b5  mov     rcx, [rsi+0A0h]
0x1400683bc  lea     rax, [rsp+3D8h+var_398]
0x1400683c1  mov     [rsp+3D8h+var_398], rdi
0x1400683c6  mov     rdx, rdi
0x1400683c9  mov     [rsp+3D8h+var_390], r14
0x1400683ce  mov     [rsp+3D8h+var_3B8], rax
0x1400683d3  mov     rcx, [rcx+880h]
0x1400683da  call    RfsHashTableLookupAndProcess
0x1400683df  test    eax, eax
0x1400683e1  movzx   r12d, r12b
0x1400683e5  mov     edi, 1
0x1400683ea  cmovns  r12d, edi
0x1400683ee  jmp     loc_14006834E
0x1400683f3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400683fa  lea     rax, WPP_GLOBAL_Control
0x140068401  mov     edi, 1
0x140068406  cmp     rcx, rax
0x140068409  jz      short loc_14006842C
0x14006840b  mov     eax, [rcx+2Ch]
0x14006840e  test    dil, al
0x140068411  jz      short loc_14006842C
0x140068413  cmp     byte ptr [rcx+29h], 2
0x140068417  jb      short loc_14006842C
0x140068419  mov     rcx, [rcx+18h]
0x14006841d  lea     edx, [rdi+11h]
0x140068420  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x140068427  call    WPP_SF_
0x14006842c  mov     rcx, [rbp+18h]
0x140068430  xor     edx, edx
0x140068432  add     rcx, 50h ; 'P'
0x140068436  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006843d  nop     dword ptr [rax+rax+00h]
0x140068442  mov     rcx, rbp
0x140068445  call    Smb2DereferenceSession
0x14006844a  mov     rsi, [rsp+3D8h+var_3A0]
0x14006844f  jmp     short loc_140068456
0x140068451  test    r12b, r12b
0x140068454  jz      short loc_140068465
0x140068456  mov     rcx, r14; RunRef
0x140068459  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140068460  nop     dword ptr [rax+rax+00h]
0x140068465  mov     rax, cs:WPP_GLOBAL_Control
0x14006846c  mov     ecx, [rax+2Ch]
0x14006846f  test    dil, cl
0x140068472  jz      short loc_1400684BF
0x140068474  mov     r9, 0FFFFF78000000014h
0x14006847e  mov     r9, [r9]
0x140068481  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140068488  lea     rax, WPP_GLOBAL_Control
0x14006848f  cmp     rcx, rax
0x140068492  jz      short loc_1400684BF
0x140068494  mov     eax, [rcx+2Ch]
0x140068497  test    dil, al
0x14006849a  jz      short loc_1400684BF
0x14006849c  cmp     byte ptr [rcx+29h], 2
0x1400684a0  jb      short loc_1400684BF
0x1400684a2  mov     rcx, [rcx+18h]
0x1400684a6  lea     r8, WPP_e84c3921fd4432419c0c9adfbb74e73f_Traceguids
0x1400684ad  sub     r9, rbx
0x1400684b0  mov     [rsp+3D8h+var_3B8], rbx
0x1400684b5  mov     edx, 16h
0x1400684ba  call    WPP_SF_qq
0x1400684bf  xor     edx, edx; Tag
0x1400684c1  mov     rcx, r14; P
0x1400684c4  call    cs:__imp_ExFreePoolWithTag
0x1400684cb  nop     dword ptr [rax+rax+00h]
0x1400684d0  mov     rcx, rsi; Context
0x1400684d3  call    Srv2DereferenceInstance
0x1400684d8  xor     eax, eax
0x1400684da  mov     dword ptr [r13+10h], 0
0x1400684e2  mov     rcx, [rsp+3D8h+var_58]
0x1400684ea  xor     rcx, rsp; StackCookie
0x1400684ed  call    __security_check_cookie
0x1400684f2  add     rsp, 398h
0x1400684f9  pop     r15
0x1400684fb  pop     r14
0x1400684fd  pop     r13
0x1400684ff  pop     r12
0x140068501  pop     rdi
0x140068502  pop     rsi
0x140068503  pop     rbp
0x140068504  pop     rbx
0x140068505  retn
```

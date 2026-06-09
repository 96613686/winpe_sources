# CDVRFileCollection::CClientInfo::SetSids(ulong,void * *,int)

- ea: `0x180068244`
- end: `0x1800684be`
- name: `?SetSids@CClientInfo@CDVRFileCollection@@QEAAJKPEAPEAXH@Z`
- size: `634`
- prototype: `__int64 __fastcall(CDVRFileCollection::CClientInfo *__hidden this, unsigned int, void **, int)`
- caller_count: `5`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180063224`
- `0x180063528`
- `0x180068cdc`
- `0x180068fd0`
- `0x180071cb0`

## callees

- `0x1800017ec`
- `0x180001c00`
- `0x18000256c`
- `0x180064f0c`
- `0x180068244`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006837a`
- `KERNEL32!GetLastError` at `0x1800683e9`
- `KERNEL32!GetLastError` at `0x18006848b`
- `KERNEL32!GetLastError` at `0x18006837a`
- `KERNEL32!GetLastError` at `0x1800683e9`
- `KERNEL32!GetLastError` at `0x18006848b`
- `ADVAPI32!GetLengthSid` at `0x18006839d`
- `ADVAPI32!GetLengthSid` at `0x18006843f`
- `ADVAPI32!GetLengthSid` at `0x18006839d`
- `ADVAPI32!GetLengthSid` at `0x18006843f`
- `ADVAPI32!FreeSid` at `0x1800683cd`
- `ADVAPI32!FreeSid` at `0x180068405`
- `ADVAPI32!FreeSid` at `0x1800683cd`
- `ADVAPI32!FreeSid` at `0x180068405`
- `ADVAPI32!IsValidSid` at `0x180068431`
- `ADVAPI32!IsValidSid` at `0x180068431`
- `ADVAPI32!CopySid` at `0x1800683df`
- `ADVAPI32!CopySid` at `0x180068474`
- `ADVAPI32!CopySid` at `0x1800683df`
- `ADVAPI32!CopySid` at `0x180068474`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180068370`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180068370`

## pseudocode

```c
__int64 __fastcall CDVRFileCollection::CClientInfo::SetSids(
        CDVRFileCollection::CClientInfo *this,
        unsigned int a2,
        void **a3,
        int a4)
{
  unsigned int v9; // esi
  __int64 v10; // r15
  void *v11; // rax
  signed int LastError; // eax
  signed int v13; // ebx
  DWORD LengthSid; // ebx
  void *v15; // rdx
  signed int v16; // eax
  unsigned int i; // ebx
  __int64 v18; // r15
  void *v19; // rcx
  DWORD v20; // r12d
  void *v21; // rdx
  PSID pSourceSid; // [rsp+78h] [rbp-50h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-48h] BYREF

  if ( !a2 && a3 )
    return 2147942487LL;
  if ( !a2 )
    return 0;
  if ( !a3 )
    return 2147942487LL;
  v9 = a4 != 0;
  v10 = v9 + a2;
  v11 = operator new[](saturated_mul(v9 + a2, 8u));
  *((_QWORD *)this + 3) = v11;
  if ( !v11 )
    return 2147942414LL;
  *((_DWORD *)this + 4) = v10;
  memset_0(v11, 0, 8 * v10);
  if ( !a4 )
    goto LABEL_22;
  pSourceSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 768;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSourceSid) )
  {
LABEL_12:
    LastError = GetLastError();
    v13 = LastError;
LABEL_13:
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_33;
  }
  LengthSid = GetLengthSid(pSourceSid);
  **((_QWORD **)this + 3) = operator new[](LengthSid);
  v15 = (void *)**((_QWORD **)this + 3);
  if ( v15 )
  {
    if ( !CopySid(LengthSid, v15, pSourceSid) )
    {
      v16 = GetLastError();
      v13 = v16;
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      goto LABEL_17;
    }
    FreeSid(pSourceSid);
LABEL_22:
    for ( i = 0; ; ++i )
    {
      if ( i >= a2 )
      {
        v13 = 0;
        goto LABEL_33;
      }
      v18 = i;
      v19 = a3[i];
      if ( !v19 || !IsValidSid(v19) )
        break;
      v20 = GetLengthSid(a3[i]);
      *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v9) = operator new[](v20);
      v21 = *(void **)(*((_QWORD *)this + 3) + 8LL * v9);
      if ( !v21 )
      {
        v13 = -2147024882;
        goto LABEL_33;
      }
      if ( !CopySid(v20, v21, a3[i]) )
        goto LABEL_12;
      ++v9;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( a3[v18] )
      goto LABEL_13;
    v13 = -2147024809;
    goto LABEL_33;
  }
  v13 = -2147024882;
LABEL_17:
  FreeSid(pSourceSid);
LABEL_33:
  if ( v13 < 0 )
    CDVRFileCollection::CClientInfo::DeleteSids(this);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180068244  push    rbx
0x180068246  push    rsi
0x180068247  push    rdi
0x180068248  push    r12
0x18006824a  push    r13
0x18006824c  push    r14
0x18006824e  push    r15
0x180068250  sub     rsp, 90h
0x180068257  mov     rax, cs:__security_cookie
0x18006825e  xor     rax, rsp
0x180068261  mov     [rsp+0C8h+var_40], rax
0x180068269  mov     ebx, r9d
0x18006826c  mov     rdi, r8
0x18006826f  mov     r14d, edx
0x180068272  mov     r13, rcx
0x180068275  mov     [rsp+0C8h+var_58], rcx
0x18006827a  test    edx, edx
0x18006827c  jnz     short loc_180068283
0x18006827e  test    r8, r8
0x180068281  jnz     short loc_18006828D
0x180068283  test    r14d, r14d
0x180068286  jz      short loc_1800682BA
0x180068288  test    rdi, rdi
0x18006828b  jnz     short loc_1800682B5
0x18006828d  mov     eax, 80070057h
0x180068292  mov     rcx, [rsp+0C8h+var_40]
0x18006829a  xor     rcx, rsp; StackCookie
0x18006829d  call    __security_check_cookie
0x1800682a2  add     rsp, 90h
0x1800682a9  pop     r15
0x1800682ab  pop     r14
0x1800682ad  pop     r13
0x1800682af  pop     r12
0x1800682b1  pop     rdi
0x1800682b2  pop     rsi
0x1800682b3  pop     rbx
0x1800682b4  retn
0x1800682b5  test    r14d, r14d
0x1800682b8  jnz     short loc_1800682BE
0x1800682ba  xor     eax, eax
0x1800682bc  jmp     short loc_180068292
0x1800682be  xor     esi, esi
0x1800682c0  test    ebx, ebx
0x1800682c2  setnz   sil
0x1800682c6  lea     r15d, [rsi+rdx]
0x1800682ca  mov     r12d, r15d
0x1800682cd  mov     eax, 8
0x1800682d2  mul     r12
0x1800682d5  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800682dc  cmovb   rax, rcx
0x1800682e0  mov     rcx, rax; unsigned __int64
0x1800682e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800682e8  mov     [r13+18h], rax
0x1800682ec  test    rax, rax
0x1800682ef  jnz     short loc_1800682F8
0x1800682f1  mov     eax, 8007000Eh
0x1800682f6  jmp     short loc_180068292
0x1800682f8  mov     [rsp+0C8h+var_68], 0
0x180068300  mov     [r13+10h], r15d
0x180068304  lea     r8, ds:0[r15*8]; Size
0x18006830c  xor     edx, edx; Val
0x18006830e  mov     rcx, rax; void *
0x180068311  call    memset_0
0x180068316  xor     r12d, r12d
0x180068319  test    ebx, ebx
0x18006831b  jz      loc_18006840B
0x180068321  mov     [rsp+0C8h+pSourceSid], r12
0x180068326  mov     dword ptr [rsp+0C8h+pIdentifierAuthority.Value], r12d
0x18006832e  mov     word ptr [rsp+0C8h+pIdentifierAuthority.Value+4], 300h
0x180068338  lea     rax, [rsp+0C8h+pSourceSid]
0x18006833d  mov     [rsp+0C8h+pSid], rax; pSid
0x180068342  mov     [rsp+0C8h+nSubAuthority7], r12d; nSubAuthority7
0x180068347  mov     [rsp+0C8h+nSubAuthority6], r12d; nSubAuthority6
0x18006834c  mov     [rsp+0C8h+nSubAuthority5], r12d; nSubAuthority5
0x180068351  mov     [rsp+0C8h+nSubAuthority4], r12d; nSubAuthority4
0x180068356  mov     [rsp+0C8h+nSubAuthority3], r12d; nSubAuthority3
0x18006835b  mov     [rsp+0C8h+nSubAuthority2], r12d; nSubAuthority2
0x180068360  xor     r9d, r9d; nSubAuthority1
0x180068363  xor     r8d, r8d; nSubAuthority0
0x180068366  mov     dl, 1; nSubAuthorityCount
0x180068368  lea     rcx, [rsp+0C8h+pIdentifierAuthority]; pIdentifierAuthority
0x180068370  call    cs:__imp_AllocateAndInitializeSid
0x180068376  test    eax, eax
0x180068378  jnz     short loc_180068398
0x18006837a  call    cs:__imp_GetLastError
0x180068380  mov     ebx, eax
0x180068382  test    eax, eax
0x180068384  jle     loc_1800684A7
0x18006838a  movzx   ebx, ax
0x18006838d  or      ebx, 80070000h
0x180068393  jmp     loc_1800684A7
0x180068398  mov     rcx, [rsp+0C8h+pSourceSid]; pSid
0x18006839d  call    cs:__imp_GetLengthSid
0x1800683a3  mov     ebx, eax
0x1800683a5  mov     ecx, eax; unsigned __int64
0x1800683a7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800683ac  mov     rcx, [r13+18h]
0x1800683b0  mov     [rcx], rax
0x1800683b3  mov     rcx, [r13+18h]
0x1800683b7  mov     rdx, [rcx]; pDestinationSid
0x1800683ba  test    rdx, rdx
0x1800683bd  jnz     short loc_1800683D8
0x1800683bf  mov     ebx, 8007000Eh
0x1800683c4  mov     [rsp+0C8h+var_68], ebx
0x1800683c8  mov     rcx, [rsp+0C8h+pSourceSid]; pSid
0x1800683cd  call    cs:__imp_FreeSid
0x1800683d3  jmp     loc_1800684AB
0x1800683d8  mov     r8, [rsp+0C8h+pSourceSid]; pSourceSid
0x1800683dd  mov     ecx, ebx; nDestinationSidLength
0x1800683df  call    cs:__imp_CopySid
0x1800683e5  test    eax, eax
0x1800683e7  jnz     short loc_180068400
0x1800683e9  call    cs:__imp_GetLastError
0x1800683ef  mov     ebx, eax
0x1800683f1  test    eax, eax
0x1800683f3  jle     short loc_1800683C4
0x1800683f5  movzx   ebx, ax
0x1800683f8  or      ebx, 80070000h
0x1800683fe  jmp     short loc_1800683C4
0x180068400  mov     rcx, [rsp+0C8h+pSourceSid]; pSid
0x180068405  call    cs:__imp_FreeSid
0x18006840b  mov     [rsp+0C8h+var_64], r12d
0x180068410  mov     [rsp+0C8h+var_60], r12d
0x180068415  mov     ebx, r12d
0x180068418  mov     [rsp+0C8h+var_60], esi
0x18006841c  mov     [rsp+0C8h+var_64], ebx
0x180068420  cmp     ebx, r14d
0x180068423  jnb     short loc_1800684A4
0x180068425  mov     r15d, ebx
0x180068428  mov     rcx, [rdi+r15*8]; pSid
0x18006842c  test    rcx, rcx
0x18006842f  jz      short loc_18006848B
0x180068431  call    cs:__imp_IsValidSid
0x180068437  test    eax, eax
0x180068439  jz      short loc_18006848B
0x18006843b  mov     rcx, [rdi+r15*8]; pSid
0x18006843f  call    cs:__imp_GetLengthSid
0x180068445  mov     r12d, eax
0x180068448  mov     ecx, eax; unsigned __int64
0x18006844a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006844f  mov     edx, esi
0x180068451  mov     rcx, [r13+18h]
0x180068455  mov     [rcx+rdx*8], rax
0x180068459  mov     rcx, [r13+18h]
0x18006845d  mov     rdx, [rcx+rdx*8]; pDestinationSid
0x180068461  test    rdx, rdx
0x180068464  jnz     short loc_18006846D
0x180068466  mov     ebx, 8007000Eh
0x18006846b  jmp     short loc_1800684A7
0x18006846d  mov     r8, [rdi+r15*8]; pSourceSid
0x180068471  mov     ecx, r12d; nDestinationSidLength
0x180068474  call    cs:__imp_CopySid
0x18006847a  xor     r12d, r12d
0x18006847d  test    eax, eax
0x18006847f  jz      loc_18006837A
0x180068485  inc     ebx
0x180068487  inc     esi
0x180068489  jmp     short loc_180068418
0x18006848b  call    cs:__imp_GetLastError
0x180068491  mov     ebx, eax
0x180068493  cmp     [rdi+r15*8], r12
0x180068497  jnz     loc_180068382
0x18006849d  mov     ebx, 80070057h
0x1800684a2  jmp     short loc_1800684A7
0x1800684a4  mov     ebx, r12d
0x1800684a7  mov     [rsp+0C8h+var_68], ebx
0x1800684ab  test    ebx, ebx
0x1800684ad  jns     short loc_1800684B7
0x1800684af  mov     rcx, r13; this
0x1800684b2  call    ?DeleteSids@CClientInfo@CDVRFileCollection@@QEAAXXZ; CDVRFileCollection::CClientInfo::DeleteSids(void)
0x1800684b7  mov     eax, ebx
0x1800684b9  jmp     loc_180068292
0x1800b3c92  push    rbp
0x1800b3c94  sub     rsp, 60h
0x1800b3c98  mov     rbp, rdx
0x1800b3c9b  cmp     dword ptr [rbp+60h], 0
0x1800b3c9f  jge     short loc_1800B3CAB
0x1800b3ca1  mov     rcx, [rbp+70h]; this
0x1800b3ca5  call    ?DeleteSids@CClientInfo@CDVRFileCollection@@QEAAXXZ; CDVRFileCollection::CClientInfo::DeleteSids(void)
0x1800b3caa  nop
0x1800b3cab  add     rsp, 60h
0x1800b3caf  pop     rbp
0x1800b3cb0  retn
```

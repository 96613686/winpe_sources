# CPxeEndpoints::OpenEndpoints(void)

- ea: `0x180003384`
- end: `0x18000391b`
- name: `?OpenEndpoints@CPxeEndpoints@@AEAAKXZ`
- size: `1431`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003eac`

## callees

- `0x180003384`
- `0x180003f34`
- `0x180011a62`
- `0x180011a90`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800033e5`
- `KERNEL32!EnterCriticalSection` at `0x1800033e5`
- `KERNEL32!LeaveCriticalSection` at `0x1800038dc`
- `KERNEL32!LeaveCriticalSection` at `0x1800038dc`
- `WDSSRV!WdsEndpointOpen` at `0x18000345d`
- `WDSSRV!WdsEndpointOpen` at `0x1800034fe`
- `WDSSRV!WdsEndpointOpen` at `0x1800035dc`
- `WDSSRV!WdsEndpointOpen` at `0x180003796`
- `WDSSRV!WdsEndpointOpen` at `0x1800038b3`
- `WDSSRV!WdsEndpointOpen` at `0x18000345d`
- `WDSSRV!WdsEndpointOpen` at `0x1800034fe`
- `WDSSRV!WdsEndpointOpen` at `0x1800035dc`
- `WDSSRV!WdsEndpointOpen` at `0x180003796`
- `WDSSRV!WdsEndpointOpen` at `0x1800038b3`
- `WDSSRV!WdsEndpointClose` at `0x18000348a`
- `WDSSRV!WdsEndpointClose` at `0x18000352b`
- `WDSSRV!WdsEndpointClose` at `0x180003609`
- `WDSSRV!WdsEndpointClose` at `0x1800037c3`
- `WDSSRV!WdsEndpointClose` at `0x18000348a`
- `WDSSRV!WdsEndpointClose` at `0x18000352b`
- `WDSSRV!WdsEndpointClose` at `0x180003609`
- `WDSSRV!WdsEndpointClose` at `0x1800037c3`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x180003646`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000367a`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x180003646`
- `WdsCommonLib!?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z` at `0x18000367a`

## pseudocode

```c
__int64 __fastcall CPxeEndpoints::OpenEndpoints(LPCRITICAL_SECTION lpCriticalSection)
{
  LONG v1; // ebx
  BOOL v2; // r14d
  LONG LockCount; // r12d
  LPCRITICAL_SECTION v5; // r15
  __int64 v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  LONG *p_LockCount; // r15
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  HANDLE *p_LockSemaphore; // r15
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rdx
  __int64 v25; // r8
  ULONG_PTR *p_SpinCount; // r14
  PRTL_CRITICAL_SECTION_DEBUG v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  PRTL_CRITICAL_SECTION_DEBUG v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v36; // [rsp+38h] [rbp-D0h] BYREF
  __int16 v37; // [rsp+44h] [rbp-C4h]
  __int128 v38; // [rsp+458h] [rbp+350h] BYREF
  int v39; // [rsp+468h] [rbp+360h]
  __int128 v40; // [rsp+470h] [rbp+368h] BYREF
  int v41; // [rsp+480h] [rbp+378h]
  __int64 v42; // [rsp+488h] [rbp+380h] BYREF
  int v43; // [rsp+490h] [rbp+388h]
  __int16 v44; // [rsp+494h] [rbp+38Ch]
  int v45; // [rsp+4C0h] [rbp+3B8h]
  int v46; // [rsp+4C8h] [rbp+3C0h]
  int v47; // [rsp+4F8h] [rbp+3F0h]
  __int128 v48; // [rsp+500h] [rbp+3F8h]
  int v49; // [rsp+510h] [rbp+408h]
  int v50; // [rsp+530h] [rbp+428h]
  __int128 v51; // [rsp+538h] [rbp+430h]
  int v52; // [rsp+548h] [rbp+440h]
  int v53; // [rsp+568h] [rbp+460h]
  __int128 v54; // [rsp+570h] [rbp+468h]
  int v55; // [rsp+580h] [rbp+478h]
  int v56; // [rsp+5A0h] [rbp+498h]
  int v57; // [rsp+5A8h] [rbp+4A0h]

  v39 = 0;
  v1 = 0;
  v41 = 0;
  v2 = 0;
  v38 = 0;
  v40 = 0;
  EnterCriticalSection(lpCriticalSection);
  LockCount = lpCriticalSection[4].LockCount;
  if ( LockCount && !HIDWORD(lpCriticalSection[2].SpinCount) )
    v2 = LODWORD(lpCriticalSection[2].SpinCount) == 0;
  v5 = lpCriticalSection + 3;
  if ( LockCount )
  {
    memset_0(&v42, 0, 0x41Cu);
    v42 = 1052;
    v44 = 67;
    if ( !v5->DebugInfo )
    {
      v6 = (unsigned int)WdsEndpointOpen(lpCriticalSection[4].DebugInfo, &v42, 0, 0, &lpCriticalSection[3]);
      if ( (unsigned int)ElValidateWin32_0(v6, v7, v8, 327) )
        goto LABEL_36;
    }
  }
  else if ( v5->DebugInfo )
  {
    v6 = (unsigned int)WdsEndpointClose(v5->DebugInfo);
    if ( (unsigned int)ElValidateWin32_0(v6, v9, v10, 335) )
      goto LABEL_36;
    v5->DebugInfo = 0;
  }
  p_LockCount = &lpCriticalSection[3].LockCount;
  if ( v2 )
  {
    memset_0(&v42, 0, 0x41Cu);
    v42 = 1052;
    v44 = 68;
    if ( !*(_QWORD *)p_LockCount )
    {
      v6 = (unsigned int)WdsEndpointOpen(lpCriticalSection[4].DebugInfo, &v42, 0, 0, &lpCriticalSection[3].LockCount);
      if ( (unsigned int)ElValidateWin32_0(v6, v12, v13, 359) )
        goto LABEL_36;
    }
  }
  else if ( *(_QWORD *)p_LockCount )
  {
    v6 = (unsigned int)WdsEndpointClose(*(_QWORD *)p_LockCount);
    if ( (unsigned int)ElValidateWin32_0(v6, v14, v15, 367) )
      goto LABEL_36;
    *(_QWORD *)p_LockCount = 0;
  }
  p_LockSemaphore = &lpCriticalSection[3].LockSemaphore;
  if ( v2 )
  {
    if ( !*p_LockSemaphore )
    {
      memset_0(&v36, 0, 0x41Cu);
      v36 = 1052;
      v37 = 546;
      memset_0(&v42, 0, 0x70u);
      DebugInfo = lpCriticalSection[4].DebugInfo;
      LODWORD(v42) = 524548;
      v43 = 1;
      v45 = 590084;
      v46 = 0;
      LODWORD(v6) = WdsEndpointOpen(DebugInfo, &v36, 2, &v42, &lpCriticalSection[3].LockSemaphore);
      if ( (unsigned int)ElValidateWin32_0((unsigned int)v6, v18, v19, 401) )
        goto LABEL_36;
    }
  }
  else if ( *p_LockSemaphore )
  {
    LODWORD(v6) = WdsEndpointClose(*p_LockSemaphore);
    if ( (unsigned int)ElValidateWin32_0((unsigned int)v6, v20, v21, 409) )
      goto LABEL_36;
    *p_LockSemaphore = 0;
  }
  LODWORD(v6) = CNetworkAddress::StringToIpAddress(0x17u, L"ff02::1:2", (struct tagWDS_IP_ADDRESS6 *)&v38);
  if ( !(unsigned int)ElValidateWin32_0((unsigned int)v6, v22, v23, 422) )
  {
    v6 = CNetworkAddress::StringToIpAddress(0x17u, L"ff05::1:3", (struct tagWDS_IP_ADDRESS6 *)&v40);
    if ( !(unsigned int)ElValidateWin32_0(v6, v24, v25, 427) )
    {
      p_SpinCount = &lpCriticalSection[3].SpinCount;
      if ( LockCount )
      {
        if ( !*p_SpinCount )
        {
          memset_0(&v36, 0, 0x41Cu);
          v36 = 1052;
          v37 = 547;
          memset_0(&v42, 0, 0x150u);
          v27 = lpCriticalSection[4].DebugInfo;
          v51 = v38;
          v52 = v39;
          LODWORD(v42) = 524548;
          v54 = v40;
          v43 = 1;
          v45 = 590084;
          v46 = 0;
          v47 = 262404;
          LODWORD(v48) = 1;
          v50 = 655624;
          v53 = 655624;
          v55 = v41;
          v56 = 786692;
          v57 = 1;
          v6 = (unsigned int)WdsEndpointOpen(v27, &v36, 6, &v42, &lpCriticalSection[3].SpinCount);
          if ( (unsigned int)ElValidateWin32_0(v6, v28, v29, 473) )
            goto LABEL_36;
        }
      }
      else if ( *p_SpinCount )
      {
        v6 = (unsigned int)WdsEndpointClose(*p_SpinCount);
        if ( (unsigned int)ElValidateWin32_0(v6, v30, v31, 484) )
          goto LABEL_36;
        *p_SpinCount = 0;
      }
      if ( !lpCriticalSection[3].OwningThread )
      {
        memset_0(&v36, 0, 0x41Cu);
        v36 = 1052;
        v37 = 4011;
        memset_0(&v42, 0, 0xE0u);
        v32 = lpCriticalSection[4].DebugInfo;
        v48 = v38;
        v49 = v39;
        LODWORD(v42) = 524548;
        v51 = v40;
        v43 = 1;
        v45 = 721156;
        v46 = 1;
        v47 = 655624;
        v50 = 655624;
        v52 = v41;
        LODWORD(v6) = WdsEndpointOpen(v32, &v36, 4, &v42, &lpCriticalSection[3].OwningThread);
        ElValidateWin32_0((unsigned int)v6, v33, v34, 530);
      }
    }
  }
LABEL_36:
  LOBYTE(v1) = (_DWORD)v6 != 0;
  lpCriticalSection[4].RecursionCount = v1;
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003384  mov     rax, rsp
0x180003387  mov     [rax+10h], rbx
0x18000338b  mov     [rax+18h], rsi
0x18000338f  mov     [rax+20h], rdi
0x180003393  push    rbp
0x180003394  push    r12
0x180003396  push    r13
0x180003398  push    r14
0x18000339a  push    r15
0x18000339c  lea     rbp, [rax-7D8h]
0x1800033a3  sub     rsp, 8B0h
0x1800033aa  mov     rax, cs:__security_cookie
0x1800033b1  xor     rax, rsp
0x1800033b4  mov     [rbp+7D0h+var_30], rax
0x1800033bb  xor     eax, eax
0x1800033bd  xorps   xmm0, xmm0
0x1800033c0  xorps   xmm1, xmm1
0x1800033c3  mov     [rbp+7D0h+var_470], eax
0x1800033c9  xor     ebx, ebx
0x1800033cb  mov     [rbp+7D0h+var_458], eax
0x1800033d1  mov     r14d, ebx
0x1800033d4  mov     rsi, rcx
0x1800033d7  movups  [rbp+7D0h+var_480], xmm0
0x1800033de  movups  [rbp+7D0h+var_468], xmm1
0x1800033e5  call    cs:__imp_EnterCriticalSection
0x1800033ec  nop     dword ptr [rax+rax+00h]
0x1800033f1  mov     r12d, [rsi+0A8h]
0x1800033f8  lea     eax, [rbx+1]
0x1800033fb  test    r12d, r12d
0x1800033fe  jz      short loc_18000340C
0x180003400  cmp     [rsi+74h], ebx
0x180003403  jnz     short loc_18000340C
0x180003405  cmp     [rsi+70h], ebx
0x180003408  cmovz   r14d, eax
0x18000340c  lea     r15, [rsi+78h]
0x180003410  mov     r13d, 41Ch
0x180003416  test    r12d, r12d
0x180003419  jz      short loc_180003482
0x18000341b  mov     r8d, r13d; Size
0x18000341e  lea     rcx, [rbp+7D0h+var_450]; void *
0x180003425  xor     edx, edx; Val
0x180003427  call    memset_0
0x18000342c  mov     eax, 43h ; 'C'
0x180003431  mov     [rbp+7D0h+var_450], r13
0x180003438  mov     [rbp+7D0h+var_444], ax
0x18000343f  cmp     [r15], rbx
0x180003442  jnz     short loc_1800034B0
0x180003444  mov     rcx, [rsi+0A0h]
0x18000344b  lea     rdx, [rbp+7D0h+var_450]
0x180003452  xor     r9d, r9d
0x180003455  mov     [rsp+8D0h+var_8B0], r15
0x18000345a  xor     r8d, r8d
0x18000345d  call    cs:__imp_WdsEndpointOpen
0x180003464  nop     dword ptr [rax+rax+00h]
0x180003469  mov     ecx, eax
0x18000346b  mov     r9d, 147h
0x180003471  mov     edi, eax
0x180003473  call    ElValidateWin32_0
0x180003478  test    eax, eax
0x18000347a  jnz     loc_1800038CE
0x180003480  jmp     short loc_1800034B0
0x180003482  cmp     [r15], rbx
0x180003485  jz      short loc_1800034B0
0x180003487  mov     rcx, [r15]
0x18000348a  call    cs:__imp_WdsEndpointClose
0x180003491  nop     dword ptr [rax+rax+00h]
0x180003496  mov     ecx, eax
0x180003498  mov     r9d, 14Fh
0x18000349e  mov     edi, eax
0x1800034a0  call    ElValidateWin32_0
0x1800034a5  test    eax, eax
0x1800034a7  jnz     loc_1800038CE
0x1800034ad  mov     [r15], rbx
0x1800034b0  lea     r15, [rsi+80h]
0x1800034b7  test    r14d, r14d
0x1800034ba  jz      short loc_180003523
0x1800034bc  mov     r8, r13; Size
0x1800034bf  lea     rcx, [rbp+7D0h+var_450]; void *
0x1800034c6  xor     edx, edx; Val
0x1800034c8  call    memset_0
0x1800034cd  mov     eax, 44h ; 'D'
0x1800034d2  mov     [rbp+7D0h+var_450], r13
0x1800034d9  mov     [rbp+7D0h+var_444], ax
0x1800034e0  cmp     [r15], rbx
0x1800034e3  jnz     short loc_180003551
0x1800034e5  mov     rcx, [rsi+0A0h]
0x1800034ec  lea     rdx, [rbp+7D0h+var_450]
0x1800034f3  xor     r9d, r9d
0x1800034f6  mov     [rsp+8D0h+var_8B0], r15
0x1800034fb  xor     r8d, r8d
0x1800034fe  call    cs:__imp_WdsEndpointOpen
0x180003505  nop     dword ptr [rax+rax+00h]
0x18000350a  mov     ecx, eax
0x18000350c  mov     r9d, 167h
0x180003512  mov     edi, eax
0x180003514  call    ElValidateWin32_0
0x180003519  test    eax, eax
0x18000351b  jnz     loc_1800038CE
0x180003521  jmp     short loc_180003551
0x180003523  cmp     [r15], rbx
0x180003526  jz      short loc_180003551
0x180003528  mov     rcx, [r15]
0x18000352b  call    cs:__imp_WdsEndpointClose
0x180003532  nop     dword ptr [rax+rax+00h]
0x180003537  mov     ecx, eax
0x180003539  mov     r9d, 16Fh
0x18000353f  mov     edi, eax
0x180003541  call    ElValidateWin32_0
0x180003546  test    eax, eax
0x180003548  jnz     loc_1800038CE
0x18000354e  mov     [r15], rbx
0x180003551  lea     r15, [rsi+90h]
0x180003558  test    r14d, r14d
0x18000355b  jz      loc_180003601
0x180003561  cmp     [r15], rbx
0x180003564  jnz     loc_18000362F
0x18000356a  mov     r8, r13; Size
0x18000356d  lea     rcx, [rsp+8D0h+var_8A0]; void *
0x180003572  xor     edx, edx; Val
0x180003574  call    memset_0
0x180003579  xor     edx, edx; Val
0x18000357b  mov     [rsp+8D0h+var_8A0], r13
0x180003580  mov     eax, 222h
0x180003585  lea     rcx, [rbp+7D0h+var_450]; void *
0x18000358c  mov     [rsp+8D0h+var_894], ax
0x180003591  lea     r8d, [rdx+70h]; Size
0x180003595  call    memset_0
0x18000359a  mov     rcx, [rsi+0A0h]
0x1800035a1  lea     r9, [rbp+7D0h+var_450]
0x1800035a8  mov     r8d, 2
0x1800035ae  mov     dword ptr [rbp+7D0h+var_450], 80104h
0x1800035b8  lea     rdx, [rsp+8D0h+var_8A0]
0x1800035bd  mov     [rbp+7D0h+var_448], 1
0x1800035c7  mov     [rbp+7D0h+var_418], 90104h
0x1800035d1  mov     [rbp+7D0h+var_410], ebx
0x1800035d7  mov     [rsp+8D0h+var_8B0], r15
0x1800035dc  call    cs:__imp_WdsEndpointOpen
0x1800035e3  nop     dword ptr [rax+rax+00h]
0x1800035e8  mov     ecx, eax
0x1800035ea  mov     r9d, 191h
0x1800035f0  mov     edi, eax
0x1800035f2  call    ElValidateWin32_0
0x1800035f7  test    eax, eax
0x1800035f9  jnz     loc_1800038CE
0x1800035ff  jmp     short loc_18000362F
0x180003601  cmp     [r15], rbx
0x180003604  jz      short loc_18000362F
0x180003606  mov     rcx, [r15]
0x180003609  call    cs:__imp_WdsEndpointClose
0x180003610  nop     dword ptr [rax+rax+00h]
0x180003615  mov     ecx, eax
0x180003617  mov     r9d, 199h
0x18000361d  mov     edi, eax
0x18000361f  call    ElValidateWin32_0
0x180003624  test    eax, eax
0x180003626  jnz     loc_1800038CE
0x18000362c  mov     [r15], rbx
0x18000362f  mov     r14d, 17h
0x180003635  lea     r8, [rbp+7D0h+var_480]
0x18000363c  mov     ecx, r14d
0x18000363f  lea     rdx, aFf0212; "ff02::1:2"
0x180003646  call    cs:__imp_?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)
0x18000364d  nop     dword ptr [rax+rax+00h]
0x180003652  mov     ecx, eax
0x180003654  mov     r9d, 1A6h
0x18000365a  mov     edi, eax
0x18000365c  call    ElValidateWin32_0
0x180003661  test    eax, eax
0x180003663  jnz     loc_1800038CE
0x180003669  lea     r8, [rbp+7D0h+var_468]
0x180003670  mov     ecx, r14d
0x180003673  lea     rdx, aFf0513; "ff05::1:3"
0x18000367a  call    cs:__imp_?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z; CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)
0x180003681  nop     dword ptr [rax+rax+00h]
0x180003686  mov     ecx, eax
0x180003688  mov     r9d, 1ABh
0x18000368e  mov     edi, eax
0x180003690  call    ElValidateWin32_0
0x180003695  test    eax, eax
0x180003697  jnz     loc_1800038CE
0x18000369d  lea     r14, [rsi+98h]
0x1800036a4  mov     r15d, 0A0108h
0x1800036aa  test    r12d, r12d
0x1800036ad  jz      loc_1800037BB
0x1800036b3  cmp     [r14], rbx
0x1800036b6  jnz     loc_1800037E9
0x1800036bc  mov     r8, r13; Size
0x1800036bf  lea     rcx, [rsp+8D0h+var_8A0]; void *
0x1800036c4  xor     edx, edx; Val
0x1800036c6  call    memset_0
0x1800036cb  mov     eax, 223h
0x1800036d0  mov     [rsp+8D0h+var_8A0], r13
0x1800036d5  xor     edx, edx; Val
0x1800036d7  mov     [rsp+8D0h+var_894], ax
0x1800036dc  mov     r8d, 150h; Size
0x1800036e2  lea     rcx, [rbp+7D0h+var_450]; void *
0x1800036e9  call    memset_0
0x1800036ee  movups  xmm0, [rbp+7D0h+var_480]
0x1800036f5  mov     eax, [rbp+7D0h+var_470]
0x1800036fb  lea     r9, [rbp+7D0h+var_450]
0x180003702  mov     rcx, [rsi+0A0h]
0x180003709  lea     rdx, [rsp+8D0h+var_8A0]
0x18000370e  mov     r12d, 1
0x180003714  movaps  [rbp+7D0h+var_3A0], xmm0
0x18000371b  movups  xmm0, [rbp+7D0h+var_468]
0x180003722  mov     [rbp+7D0h+var_390], eax
0x180003728  mov     eax, [rbp+7D0h+var_458]
0x18000372e  lea     r8d, [r12+5]
0x180003733  mov     dword ptr [rbp+7D0h+var_450], 80104h
0x18000373d  movups  [rbp+7D0h+var_368], xmm0
0x180003744  mov     [rbp+7D0h+var_448], r12d
0x18000374b  mov     [rbp+7D0h+var_418], 90104h
0x180003755  mov     [rbp+7D0h+var_410], ebx
0x18000375b  mov     [rbp+7D0h+var_3E0], 40104h
0x180003765  mov     dword ptr [rbp+7D0h+var_3D8], r12d
0x18000376c  mov     [rbp+7D0h+var_3A8], r15d
0x180003773  mov     [rbp+7D0h+var_370], r15d
0x18000377a  mov     [rbp+7D0h+var_358], eax
0x180003780  mov     [rbp+7D0h+var_338], 0C0104h
0x18000378a  mov     [rbp+7D0h+var_330], r12d
0x180003791  mov     [rsp+8D0h+var_8B0], r14
0x180003796  call    cs:__imp_WdsEndpointOpen
0x18000379d  nop     dword ptr [rax+rax+00h]
0x1800037a2  mov     ecx, eax
0x1800037a4  mov     r9d, 1D9h
0x1800037aa  mov     edi, eax
0x1800037ac  call    ElValidateWin32_0
0x1800037b1  test    eax, eax
0x1800037b3  jnz     loc_1800038CE
0x1800037b9  jmp     short loc_1800037EF
0x1800037bb  cmp     [r14], rbx
0x1800037be  jz      short loc_1800037E9
0x1800037c0  mov     rcx, [r14]
0x1800037c3  call    cs:__imp_WdsEndpointClose
0x1800037ca  nop     dword ptr [rax+rax+00h]
0x1800037cf  mov     ecx, eax
0x1800037d1  mov     r9d, 1E4h
0x1800037d7  mov     edi, eax
0x1800037d9  call    ElValidateWin32_0
0x1800037de  test    eax, eax
0x1800037e0  jnz     loc_1800038CE
0x1800037e6  mov     [r14], rbx
0x1800037e9  mov     r12d, 1
0x1800037ef  lea     r14, [rsi+88h]
0x1800037f6  cmp     [r14], rbx
0x1800037f9  jnz     loc_1800038CE
0x1800037ff  mov     r8, r13; Size
0x180003802  lea     rcx, [rsp+8D0h+var_8A0]; void *
0x180003807  xor     edx, edx; Val
0x180003809  call    memset_0
0x18000380e  mov     eax, 0FABh
0x180003813  mov     [rsp+8D0h+var_8A0], r13
0x180003818  xor     edx, edx; Val
0x18000381a  mov     [rsp+8D0h+var_894], ax
0x18000381f  mov     r8d, 0E0h; Size
0x180003825  lea     rcx, [rbp+7D0h+var_450]; void *
0x18000382c  call    memset_0
0x180003831  movups  xmm0, [rbp+7D0h+var_480]
0x180003838  mov     eax, [rbp+7D0h+var_470]
0x18000383e  lea     r9, [rbp+7D0h+var_450]
0x180003845  mov     rcx, [rsi+0A0h]
0x18000384c  lea     rdx, [rsp+8D0h+var_8A0]
0x180003851  movups  [rbp+7D0h+var_3D8], xmm0
0x180003858  mov     [rbp+7D0h+var_3C8], eax
0x18000385e  mov     r8d, 4
0x180003864  movups  xmm0, [rbp+7D0h+var_468]
0x18000386b  mov     eax, [rbp+7D0h+var_458]
0x180003871  mov     dword ptr [rbp+7D0h+var_450], 80104h
0x18000387b  movaps  [rbp+7D0h+var_3A0], xmm0
0x180003882  mov     [rbp+7D0h+var_448], r12d
0x180003889  mov     [rbp+7D0h+var_418], 0B0104h
0x180003893  mov     [rbp+7D0h+var_410], r12d
0x18000389a  mov     [rbp+7D0h+var_3E0], r15d
0x1800038a1  mov     [rbp+7D0h+var_3A8], r15d
0x1800038a8  mov     [rbp+7D0h+var_390], eax
0x1800038ae  mov     [rsp+8D0h+var_8B0], r14
0x1800038b3  call    cs:__imp_WdsEndpointOpen
0x1800038ba  nop     dword ptr [rax+rax+00h]
0x1800038bf  mov     ecx, eax
0x1800038c1  mov     r9d, 212h
0x1800038c7  mov     edi, eax
0x1800038c9  call    ElValidateWin32_0
0x1800038ce  test    edi, edi
0x1800038d0  mov     rcx, rsi; lpCriticalSection
0x1800038d3  setnz   bl
0x1800038d6  mov     [rsi+0ACh], ebx
0x1800038dc  call    cs:__imp_LeaveCriticalSection
0x1800038e3  nop     dword ptr [rax+rax+00h]
0x1800038e8  mov     eax, edi
0x1800038ea  mov     rcx, [rbp+7D0h+var_30]
0x1800038f1  xor     rcx, rsp; StackCookie
0x1800038f4  call    __security_check_cookie
0x1800038f9  lea     r11, [rsp+8D0h+var_20]
0x180003901  mov     rbx, [r11+38h]
0x180003905  mov     rsi, [r11+40h]
0x180003909  mov     rdi, [r11+48h]
0x18000390d  mov     rsp, r11
0x180003910  pop     r15
0x180003912  pop     r14
0x180003914  pop     r13
  ... truncated ...
```

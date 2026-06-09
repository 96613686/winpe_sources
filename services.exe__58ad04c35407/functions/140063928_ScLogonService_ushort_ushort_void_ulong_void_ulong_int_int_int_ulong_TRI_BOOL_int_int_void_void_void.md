# ScLogonService(ushort *,ushort *,void * *,ulong,void * *,ulong,int,int,int,ulong,_TRI_BOOL,int,int,void * *,void * *,void * *)

- ea: `0x140063928`
- end: `0x140063fc8`
- name: `?ScLogonService@@YAKPEAG0PEAPEAXK1KHHHKW4_TRI_BOOL@@HH111@Z`
- size: `1696`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `4`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400381d4`
- `0x14003ae4c`
- `0x14003c510`
- `0x14006e990`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x140013b0c`
- `0x140022c34`
- `0x1400275b8`
- `0x14002b348`
- `0x140030c3c`
- `0x1400355b8`
- `0x14004b1c0`
- `0x140058030`
- `0x14005b188`
- `0x140062514`
- `0x140063684`
- `0x1400638a0`
- `0x140063928`
- `0x140064994`
- `0x140064a90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140063e27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063f7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063f70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140063f7f`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140063f8d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140063f8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063f61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140063f61`
- `ntdll!RtlFreeHeap` at `0x140063f30`
- `ntdll!RtlFreeHeap` at `0x140063f52`
- `ntdll!RtlFreeHeap` at `0x140063f30`
- `ntdll!RtlFreeHeap` at `0x140063f52`
- `logoncli!NetIsServiceAccount2` at `0x140063a54`
- `logoncli!NetIsServiceAccount2` at `0x140063a54`
- `SspiCli!LogonUserExExW` at `0x140063d45`
- `SspiCli!LogonUserExExW` at `0x140063d45`
- `ext-ms-win-security-chambers-l1-1-1!SetNtlmThreadOptions` at `0x140063c5f`
- `ext-ms-win-security-chambers-l1-1-1!SetNtlmThreadOptions` at `0x140063fa5`
- `ext-ms-win-security-chambers-l1-1-1!SetNtlmThreadOptions` at `0x140063c5f`
- `ext-ms-win-security-chambers-l1-1-1!SetNtlmThreadOptions` at `0x140063fa5`

## string_xrefs

- `0x140063c58`: `services.exe`
- `0x140063f9e`: `services.exe`

## pseudocode

```c
__int64 __fastcall ScLogonService(
        wchar_t *a1,
        wchar_t *a2,
        void **a3,
        unsigned int a4,
        void **a5,
        unsigned int a6,
        int a7,
        int a8,
        int a9,
        unsigned int a10,
        int a11,
        int a12,
        int a13,
        _QWORD *a14,
        void **a15,
        _QWORD *a16)
{
  int v16; // ebx
  int v19; // r13d
  int v20; // r14d
  const wchar_t *v21; // r12
  void *v22; // r15
  __int64 v23; // rax
  unsigned int IsServiceAccount2; // eax
  unsigned int v25; // ebx
  unsigned int v26; // eax
  wchar_t *v27; // rax
  unsigned int v28; // eax
  PRPC_ASYNC_STATE v29; // rcx
  int v30; // edx
  unsigned int v31; // eax
  const wchar_t *v32; // r15
  int v33; // r13d
  int v34; // ebx
  unsigned __int64 v35; // r14
  __int64 v36; // rax
  struct _TOKEN_GROUPS *v37; // rbx
  unsigned int v38; // r12d
  unsigned __int16 *v39; // rdx
  unsigned __int16 *v40; // r8
  DWORD LastError; // ebx
  unsigned int v42; // eax
  unsigned int v43; // ecx
  HANDLE v44; // rax
  HLOCAL v45; // rax
  HANDLE hObject; // [rsp+68h] [rbp-59h] BYREF
  int v48[2]; // [rsp+70h] [rbp-51h] BYREF
  int v49; // [rsp+78h] [rbp-49h] BYREF
  int v50; // [rsp+7Ch] [rbp-45h]
  int v51; // [rsp+80h] [rbp-41h]
  HLOCAL hMem; // [rsp+88h] [rbp-39h] BYREF
  PVOID P; // [rsp+90h] [rbp-31h] BYREF
  HANDLE v54; // [rsp+98h] [rbp-29h] BYREF
  int v55; // [rsp+A0h] [rbp-21h] BYREF
  void *v56; // [rsp+A8h] [rbp-19h] BYREF
  PVOID v57; // [rsp+B0h] [rbp-11h] BYREF
  unsigned __int64 v58; // [rsp+B8h] [rbp-9h] BYREF
  __int64 i; // [rsp+C0h] [rbp-1h]

  v16 = 0;
  v50 = 0;
  v51 = 0;
  v19 = 0;
  v48[0] = 0;
  *a14 = 0;
  v20 = 0;
  v21 = 0;
  v55 = 0;
  v22 = 0;
  v49 = 0;
  v57 = 0;
  *a16 = 0;
  P = 0;
  v56 = 0;
  v54 = 0;
  hObject = 0;
  hMem = 0;
  if ( a15 )
    *a15 = 0;
  if ( (unsigned int)ScIsAccountInNtAuthDomain(a2) )
  {
    if ( !wcsicmp(a2, L"NT AUTHORITY\\SYSTEM") )
      v19 = 1;
    v50 = v19;
    goto LABEL_35;
  }
  if ( !a2 )
    goto LABEL_108;
  if ( !*a2 )
    goto LABEL_108;
  v23 = -1;
  do
    ++v23;
  while ( a2[v23] );
  if ( a2[(unsigned int)v23 - 1] != 36 )
  {
LABEL_108:
    if ( !(unsigned int)ScIsValidAccountName(a2, a1, v48) )
    {
      v25 = 1069;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_SSD(
          WPP_GLOBAL_Control->StubInfo,
          52,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          (_DWORD)a2,
          (__int64)a1,
          45);
      goto LABEL_95;
    }
    v20 = v48[0];
    if ( v48[0] )
      goto LABEL_11;
    v26 = ScFormSecretName(a1, (unsigned __int16 **)&v57);
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->StubInfo,
          (unsigned int)(v20 + 53),
          WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          v26);
      v25 = 1069;
      goto LABEL_93;
    }
    v21 = (const wchar_t *)v57;
LABEL_35:
    v27 = wcsrchr(a2, 0x5Cu);
    *(_QWORD *)v48 = v27;
    if ( !v27 )
    {
      v25 = 1057;
LABEL_93:
      if ( v57 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v57);
      goto LABEL_95;
    }
    *v27 = 0;
    if ( a3 || a5 || a13 )
    {
      v28 = ScBuildServiceTokenGroups(a1, a3, a4, a5, a6, a10, a7, a8, a9, a13, (struct _TOKEN_GROUPS **)&P, &v56);
      if ( v28 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v30 = 55;
LABEL_44:
          WPP_SF_Sd(v29->StubInfo, v30, (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, (_DWORD)a1, v28);
        }
        goto LABEL_45;
      }
    }
    if ( (unsigned __int8)IsSetNtlmThreadOptionsPresent() )
    {
      v31 = SetNtlmThreadOptions("services.exe", 0);
      if ( v31 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 56, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v31);
        }
        goto LABEL_45;
      }
      v51 = 1;
    }
    v32 = 0;
    v33 = v20 != 0 ? 4 : 0;
    if ( v16 )
    {
      v34 = v16 - 1;
      if ( v34 )
      {
        if ( v34 == 1 )
          v32 = L"_SA_{F8262F4C-499B-4770-88B4-A75C91D0D8E9}";
      }
      else
      {
        v32 = L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}";
      }
    }
    else
    {
      v32 = v21;
    }
    v35 = a12 != 0 ? g_NetworkLogonRetryTimeout : 0;
    v36 = *(_QWORD *)v48 + 2LL;
    v58 = v35;
    for ( i = *(_QWORD *)v48 + 2LL; ; v36 = i )
    {
      v37 = (struct _TOKEN_GROUPS *)P;
      v38 = g_NetworkStateChangeStamp;
      if ( (unsigned int)LogonUserExExW(v36, a2, v32, 5, v33, P, &hObject, &hMem, 0, 0, 0) )
        break;
      LastError = GetLastError();
      if ( !LastError )
      {
        v37 = (struct _TOKEN_GROUPS *)P;
        break;
      }
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_Sd(
          WPP_GLOBAL_Control->StubInfo,
          57,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          (_DWORD)a1,
          LastError);
      if ( LastError != 1311 || !v35 || (v42 = ScWaitForNetworkStateChange(v38, &v58)) != 0 && v42 != 258 )
      {
        v43 = 41;
        **(_WORD **)v48 = 92;
        if ( LastError != 1385 )
          v43 = 38;
        ScLogEvent(v43, a1, a2, LastError);
        v25 = 1069;
        goto LABEL_90;
      }
      v35 = v58;
    }
    if ( a8 && (unsigned int)ScAdjustTokenDefaultDacl(hObject, a3, a4) )
    {
      LOBYTE(v28) = GetLastError();
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v30 = 58;
        goto LABEL_44;
      }
    }
    else
    {
      if ( a7 != 1 || (v28 = ScMakeServiceTokenWriteRestricted(a1, hObject, hMem, a4, v37, &v54)) == 0 )
      {
        if ( a15 && !v50 )
          ScLoadUserProfile(hObject, v39, v40, a15);
        v25 = 0;
        if ( a7 )
        {
          v44 = v54;
          v54 = 0;
        }
        else
        {
          v44 = hObject;
          hObject = 0;
        }
        *a14 = v44;
        v45 = hMem;
        hMem = 0;
        *a16 = v45;
        goto LABEL_90;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v30 = 59;
        goto LABEL_44;
      }
    }
LABEL_45:
    v25 = 1069;
LABEL_90:
    **(_WORD **)v48 = 92;
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    v22 = v56;
    goto LABEL_93;
  }
  if ( a11 == 1 )
  {
    v16 = 1;
LABEL_11:
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_SS(
        WPP_GLOBAL_Control->StubInfo,
        54,
        (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
        (_DWORD)a2,
        (__int64)a1);
    goto LABEL_35;
  }
  if ( !a11 )
  {
    v16 = 2;
    goto LABEL_11;
  }
  IsServiceAccount2 = NetIsServiceAccount2(0, a2, &v55, &v49);
  v25 = IsServiceAccount2;
  if ( !IsServiceAccount2 )
  {
    v16 = (v49 == 3) + 1;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_SSD(
      WPP_GLOBAL_Control->StubInfo,
      51,
      (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
      (_DWORD)a2,
      (__int64)a1,
      IsServiceAccount2);
LABEL_95:
  if ( hMem )
    LocalFree(hMem);
  if ( hObject )
    CloseHandle(hObject);
  if ( v54 )
    CloseHandle(v54);
  if ( v22 )
    FreeSid(v22);
  if ( v51 )
    SetNtlmThreadOptions("services.exe", 1);
  return v25;
}

```

## disassembly

```asm
0x140063928  mov     rax, rsp
0x14006392b  mov     [rax+8], rbx
0x14006392f  mov     [rax+20h], r9d
0x140063933  mov     [rax+18h], r8
0x140063937  push    rbp
0x140063938  push    rsi
0x140063939  push    rdi
0x14006393a  push    r12
0x14006393c  push    r13
0x14006393e  push    r14
0x140063940  push    r15
0x140063942  lea     rbp, [rax-3Fh]
0x140063946  sub     rsp, 0C0h
0x14006394d  mov     rax, [rbp+37h+arg_68]
0x140063954  xor     ebx, ebx
0x140063956  mov     rdi, rdx
0x140063959  mov     [rbp+37h+var_7C], ebx
0x14006395c  mov     rsi, rcx
0x14006395f  mov     [rbp+37h+var_78], ebx
0x140063962  mov     r13d, ebx
0x140063965  mov     [rbp+37h+var_88], ebx
0x140063968  mov     [rax], rbx
0x14006396b  mov     r14d, ebx
0x14006396e  mov     rax, [rbp+37h+arg_78]
0x140063975  mov     r12d, ebx
0x140063978  mov     [rbp+37h+var_58], ebx
0x14006397b  mov     r15d, ebx
0x14006397e  mov     [rbp+37h+var_80], ebx
0x140063981  mov     [rbp+37h+var_48], rbx
0x140063985  mov     [rax], rbx
0x140063988  mov     rax, [rbp+37h+arg_70]
0x14006398f  mov     [rbp+37h+P], rbx
0x140063993  mov     [rbp+37h+var_50], rbx
0x140063997  mov     [rbp+37h+var_60], rbx
0x14006399b  mov     [rbp+37h+hObject], rbx
0x14006399f  mov     [rbp+37h+hMem], rbx
0x1400639a3  test    rax, rax
0x1400639a6  jz      short loc_1400639AB
0x1400639a8  mov     [rax], rbx
0x1400639ab  mov     rcx, rdi; unsigned __int16 *
0x1400639ae  call    ?ScIsAccountInNtAuthDomain@@YAHPEBG@Z; ScIsAccountInNtAuthDomain(ushort const *)
0x1400639b3  mov     ecx, 1
0x1400639b8  test    eax, eax
0x1400639ba  jnz     loc_140063B57
0x1400639c0  test    rdi, rdi
0x1400639c3  jz      loc_140063AB8
0x1400639c9  cmp     [rdi], r13w
0x1400639cd  jz      loc_140063AB8
0x1400639d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400639d7  inc     rax
0x1400639da  cmp     [rdi+rax*2], r13w
0x1400639df  jnz     short loc_1400639D7
0x1400639e1  mov     eax, eax
0x1400639e3  cmp     word ptr [rdi+rax*2-2], 24h ; '$'
0x1400639e9  jnz     loc_140063AB8
0x1400639ef  mov     eax, [rbp+37h+arg_50]
0x1400639f5  cmp     eax, ecx
0x1400639f7  jnz     short loc_140063A3E
0x1400639f9  mov     ebx, ecx
0x1400639fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a02  lea     rax, WPP_GLOBAL_Control
0x140063a09  cmp     rcx, rax
0x140063a0c  jz      loc_140063B78
0x140063a12  test    byte ptr [rcx+1Ch], 4
0x140063a16  jz      loc_140063B78
0x140063a1c  mov     rcx, [rcx+10h]
0x140063a20  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063a27  mov     edx, 36h ; '6'
0x140063a2c  mov     [rsp+0F0h+var_D0], rsi
0x140063a31  mov     r9, rdi
0x140063a34  call    WPP_SF_SS
0x140063a39  jmp     loc_140063B78
0x140063a3e  test    eax, eax
0x140063a40  jnz     short loc_140063A47
0x140063a42  lea     ebx, [rax+2]
0x140063a45  jmp     short loc_1400639FB
0x140063a47  lea     r9, [rbp+37h+var_80]
0x140063a4b  mov     rdx, rdi
0x140063a4e  lea     r8, [rbp+37h+var_58]
0x140063a52  xor     ecx, ecx
0x140063a54  call    cs:__imp_NetIsServiceAccount2
0x140063a5a  mov     ebx, eax
0x140063a5c  test    eax, eax
0x140063a5e  jz      short loc_140063AA7
0x140063a60  mov     rcx, cs:WPP_GLOBAL_Control
0x140063a67  lea     rdx, WPP_GLOBAL_Control
0x140063a6e  cmp     rcx, rdx
0x140063a71  jz      loc_140063F58
0x140063a77  test    byte ptr [rcx+1Ch], 1
0x140063a7b  jz      loc_140063F58
0x140063a81  mov     edx, 33h ; '3'
0x140063a86  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140063a8a  mov     rcx, [rcx+10h]
0x140063a8e  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063a95  mov     r9, rdi
0x140063a98  mov     [rsp+0F0h+var_D0], rsi
0x140063a9d  call    WPP_SF_SSD
0x140063aa2  jmp     loc_140063F58
0x140063aa7  cmp     [rbp+37h+var_80], 3
0x140063aab  mov     ebx, r13d
0x140063aae  setz    bl
0x140063ab1  inc     ebx
0x140063ab3  jmp     loc_1400639FB
0x140063ab8  lea     r8, [rbp+37h+var_88]; int *
0x140063abc  mov     rdx, rsi; String2
0x140063abf  mov     rcx, rdi; String1
0x140063ac2  call    ?ScIsValidAccountName@@YAHPEBG0PEAH@Z; ScIsValidAccountName(ushort const *,ushort const *,int *)
0x140063ac7  test    eax, eax
0x140063ac9  jnz     short loc_140063AFA
0x140063acb  mov     ebx, 42Dh
0x140063ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x140063ad7  lea     rdx, WPP_GLOBAL_Control
0x140063ade  cmp     rcx, rdx
0x140063ae1  jz      loc_140063F58
0x140063ae7  test    byte ptr [rcx+1Ch], 1
0x140063aeb  jz      loc_140063F58
0x140063af1  lea     edx, [rax+34h]
0x140063af4  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140063af8  jmp     short loc_140063A8A
0x140063afa  mov     r14d, [rbp+37h+var_88]
0x140063afe  test    r14d, r14d
0x140063b01  jnz     loc_1400639FB
0x140063b07  lea     rdx, [rbp+37h+var_48]; unsigned __int16 **
0x140063b0b  mov     rcx, rsi; unsigned __int16 *
0x140063b0e  call    ?ScFormSecretName@@YAKPEAGPEAPEAG@Z; ScFormSecretName(ushort *,ushort * *)
0x140063b13  test    eax, eax
0x140063b15  jz      short loc_140063B51
0x140063b17  mov     rcx, cs:WPP_GLOBAL_Control
0x140063b1e  lea     rdx, WPP_GLOBAL_Control
0x140063b25  cmp     rcx, rdx
0x140063b28  jz      short loc_140063B47
0x140063b2a  test    byte ptr [rcx+1Ch], 1
0x140063b2e  jz      short loc_140063B47
0x140063b30  mov     rcx, [rcx+10h]
0x140063b34  lea     edx, [r14+35h]
0x140063b38  mov     r9d, eax
0x140063b3b  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063b42  call    WPP_SF_d
0x140063b47  mov     ebx, 42Dh
0x140063b4c  jmp     loc_140063F3A
0x140063b51  mov     r12, [rbp+37h+var_48]
0x140063b55  jmp     short loc_140063B78
0x140063b57  lea     rdx, aNtAuthoritySys; "NT AUTHORITY\\SYSTEM"
0x140063b5e  mov     rcx, rdi; String1
0x140063b61  call    _wcsicmp
0x140063b66  test    eax, eax
0x140063b68  mov     eax, 1
0x140063b6d  cmovz   r13d, eax
0x140063b71  mov     [rbp+37h+var_7C], r13d
0x140063b75  xor     r13d, r13d
0x140063b78  mov     edx, 5Ch ; '\'; Ch
0x140063b7d  mov     rcx, rdi; Str
0x140063b80  call    wcsrchr
0x140063b85  mov     qword ptr [rbp+37h+var_88], rax
0x140063b89  test    rax, rax
0x140063b8c  jnz     short loc_140063B98
0x140063b8e  mov     ebx, 421h
0x140063b93  jmp     loc_140063F3A
0x140063b98  mov     rcx, [rbp+37h+arg_10]
0x140063b9c  mov     r9, [rbp+37h+arg_20]; void **
0x140063ba0  mov     [rax], r13w
0x140063ba4  mov     eax, [rbp+37h+arg_60]
0x140063baa  test    rcx, rcx
0x140063bad  jnz     short loc_140063BBC
0x140063baf  test    r9, r9
0x140063bb2  jnz     short loc_140063BBC
0x140063bb4  test    eax, eax
0x140063bb6  jz      loc_140063C4D
0x140063bbc  mov     r8d, [rbp+37h+arg_18]; unsigned int
0x140063bc0  lea     rdx, [rbp+37h+var_50]
0x140063bc4  mov     [rsp+58h], rdx; void **
0x140063bc9  lea     rdx, [rbp+37h+P]
0x140063bcd  mov     [rsp+0F0h+var_A0], rdx; struct _TOKEN_GROUPS **
0x140063bd2  mov     rdx, rcx; void **
0x140063bd5  mov     [rsp+0F0h+var_A8], eax; int
0x140063bd9  mov     rcx, rsi; unsigned __int16 *
0x140063bdc  mov     eax, [rbp+37h+arg_40]
0x140063be2  mov     [rsp+0F0h+var_B0], eax; int
0x140063be6  mov     eax, [rbp+37h+arg_38]
0x140063be9  mov     [rsp+0F0h+var_B8], eax; int
0x140063bed  mov     eax, [rbp+37h+arg_30]
0x140063bf0  mov     [rsp+0F0h+var_C0], eax; int
0x140063bf4  mov     eax, [rbp+37h+arg_48]
0x140063bfa  mov     dword ptr [rsp+0F0h+var_C8], eax; unsigned int
0x140063bfe  mov     eax, [rbp+37h+arg_28]
0x140063c01  mov     dword ptr [rsp+0F0h+var_D0], eax; unsigned int
0x140063c05  call    ?ScBuildServiceTokenGroups@@YAKPEBGPEAPEAXK1KKHHHHPEAPEAU_TOKEN_GROUPS@@1@Z; ScBuildServiceTokenGroups(ushort const *,void * *,ulong,void * *,ulong,ulong,int,int,int,int,_TOKEN_GROUPS * *,void * *)
0x140063c0a  test    eax, eax
0x140063c0c  jz      short loc_140063C4D
0x140063c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140063c15  lea     rdx, WPP_GLOBAL_Control
0x140063c1c  cmp     rcx, rdx
0x140063c1f  jz      short loc_140063C43
0x140063c21  test    byte ptr [rcx+1Ch], 1
0x140063c25  jz      short loc_140063C43
0x140063c27  mov     edx, 37h ; '7'
0x140063c2c  mov     rcx, [rcx+10h]
0x140063c30  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063c37  mov     r9, rsi
0x140063c3a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140063c3e  call    WPP_SF_Sd
0x140063c43  mov     ebx, 42Dh
0x140063c48  jmp     loc_140063F07
0x140063c4d  call    IsSetNtlmThreadOptionsPresent
0x140063c52  test    al, al
0x140063c54  jz      short loc_140063CA3
0x140063c56  xor     edx, edx
0x140063c58  lea     rcx, aServicesExe; "services.exe"
0x140063c5f  call    cs:__imp_SetNtlmThreadOptions
0x140063c65  test    eax, eax
0x140063c67  jz      short loc_140063C9C
0x140063c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140063c70  lea     rdx, WPP_GLOBAL_Control
0x140063c77  cmp     rcx, rdx
0x140063c7a  jz      short loc_140063C43
0x140063c7c  test    byte ptr [rcx+1Ch], 1
0x140063c80  jz      short loc_140063C43
0x140063c82  mov     rcx, [rcx+10h]
0x140063c86  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063c8d  mov     edx, 38h ; '8'
0x140063c92  mov     r9d, eax
0x140063c95  call    WPP_SF_d
0x140063c9a  jmp     short loc_140063C43
0x140063c9c  mov     [rbp+37h+var_78], 1
0x140063ca3  neg     r14d
0x140063ca6  mov     r15, r13
0x140063ca9  sbb     r13d, r13d
0x140063cac  and     r13d, 4
0x140063cb0  test    ebx, ebx
0x140063cb2  jz      short loc_140063CD0
0x140063cb4  sub     ebx, 1
0x140063cb7  jz      short loc_140063CC7
0x140063cb9  cmp     ebx, 1
0x140063cbc  jnz     short loc_140063CD3
0x140063cbe  lea     r15, aSaF8262f4c499b; "_SA_{F8262F4C-499B-4770-88B4-A75C91D0D8"...
0x140063cc5  jmp     short loc_140063CD3
0x140063cc7  lea     r15, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x140063cce  jmp     short loc_140063CD3
0x140063cd0  mov     r15, r12
0x140063cd3  neg     [rbp+37h+arg_58]
0x140063cd9  sbb     eax, eax
0x140063cdb  and     eax, cs:?g_NetworkLogonRetryTimeout@@3KA; ulong g_NetworkLogonRetryTimeout
0x140063ce1  mov     r14d, eax
0x140063ce4  mov     rax, qword ptr [rbp+37h+var_88]
0x140063ce8  add     rax, 2
0x140063cec  mov     [rbp+37h+var_40], r14
0x140063cf0  mov     [rbp+37h+var_38], rax
0x140063cf4  mov     rbx, [rbp+37h+P]
0x140063cf8  lea     rcx, [rbp+37h+hMem]
0x140063cfc  mov     r12d, cs:?g_NetworkStateChangeStamp@@3KA; ulong g_NetworkStateChangeStamp
0x140063d03  mov     r9d, 5
0x140063d09  mov     [rsp+0F0h+var_A0], 0
0x140063d12  mov     r8, r15
0x140063d15  mov     qword ptr [rsp+0F0h+var_A8], 0
0x140063d1e  mov     rdx, rdi
0x140063d21  mov     qword ptr [rsp+0F0h+var_B0], 0
0x140063d2a  mov     qword ptr [rsp+0F0h+var_B8], rcx
0x140063d2f  lea     rcx, [rbp+37h+hObject]
0x140063d33  mov     qword ptr [rsp+0F0h+var_C0], rcx
0x140063d38  mov     rcx, rax
0x140063d3b  mov     [rsp+0F0h+var_C8], rbx
0x140063d40  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x140063d45  call    cs:__imp_LogonUserExExW
0x140063d4b  test    eax, eax
0x140063d4d  jnz     loc_140063E06
0x140063d53  call    cs:__imp_GetLastError
0x140063d59  mov     ebx, eax
0x140063d5b  test    eax, eax
0x140063d5d  jz      loc_140063E02
0x140063d63  mov     rcx, cs:WPP_GLOBAL_Control
0x140063d6a  lea     rax, WPP_GLOBAL_Control
0x140063d71  cmp     rcx, rax
0x140063d74  jz      short loc_140063D98
0x140063d76  test    byte ptr [rcx+1Ch], 1
0x140063d7a  jz      short loc_140063D98
0x140063d7c  mov     rcx, [rcx+10h]
0x140063d80  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140063d87  mov     edx, 39h ; '9'
0x140063d8c  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x140063d90  mov     r9, rsi
0x140063d93  call    WPP_SF_Sd
0x140063d98  cmp     ebx, 51Fh
0x140063d9e  jnz     short loc_140063DC9
0x140063da0  test    r14, r14
0x140063da3  jz      short loc_140063DC9
0x140063da5  lea     rdx, [rbp+37h+var_40]; unsigned __int64 *
0x140063da9  mov     ecx, r12d; unsigned int
0x140063dac  call    ?ScWaitForNetworkStateChange@@YAKKAEA_K@Z; ScWaitForNetworkStateChange(ulong,unsigned __int64 &)
0x140063db1  test    eax, eax
0x140063db3  jz      short loc_140063DBC
0x140063db5  cmp     eax, 102h
0x140063dba  jnz     short loc_140063DC9
0x140063dbc  mov     r14, [rbp+37h+var_40]
0x140063dc0  mov     rax, [rbp+37h+var_38]
0x140063dc4  jmp     loc_140063CF4
0x140063dc9  mov     rax, qword ptr [rbp+37h+var_88]
0x140063dcd  mov     r14d, 5Ch ; '\'
0x140063dd3  cmp     ebx, 569h
0x140063dd9  mov     r9d, ebx
0x140063ddc  mov     r8, rdi
  ... truncated ...
```

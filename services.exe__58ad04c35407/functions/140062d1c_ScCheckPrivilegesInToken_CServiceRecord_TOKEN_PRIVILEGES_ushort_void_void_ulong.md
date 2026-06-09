# ScCheckPrivilegesInToken(CServiceRecord *,_TOKEN_PRIVILEGES *,ushort *,void *,void *,ulong)

- ea: `0x140062d1c`
- end: `0x14006313e`
- name: `?ScCheckPrivilegesInToken@@YAKPEAVCServiceRecord@@PEAU_TOKEN_PRIVILEGES@@PEAGPEAX3K@Z`
- size: `1058`
- prototype: `unsigned int(struct CServiceRecord *, struct _TOKEN_PRIVILEGES *, unsigned __int16 *, void *, void *, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callers

- `0x1400322dc`
- `0x14003c510`

## callees

- `0x140003e54`
- `0x14000bebc`
- `0x1400188fc`
- `0x14001c000`
- `0x14001c1e0`
- `0x14002178c`
- `0x140029228`
- `0x140030a5c`
- `0x140062d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006309c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140062f2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006309c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140062f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140062fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140062f5a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140062fbb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140062f24`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140062f24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400630dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400630dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400630eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400630eb`
- `ntdll!RtlFreeHeap` at `0x140063108`
- `ntdll!RtlFreeHeap` at `0x140063125`
- `ntdll!RtlFreeHeap` at `0x140063108`
- `ntdll!RtlFreeHeap` at `0x140063125`

## pseudocode

```c
__int64 __fastcall ScCheckPrivilegesInToken(
        struct CServiceRecord *a1,
        struct _TOKEN_PRIVILEGES *a2,
        unsigned __int16 *a3,
        void *a4,
        HANDLE ProcessHandle,
        char a6)
{
  DWORD LastError; // ebx
  struct _TOKEN_PRIVILEGES *v8; // r14
  unsigned __int16 *v12; // rsi
  PRPC_ASYNC_STATE v13; // rcx
  int v14; // edx
  DWORD v15; // eax
  unsigned int v16; // eax
  void *v17; // rdi
  wchar_t *v18; // rdi
  int v19; // edx
  DWORD v20; // eax
  char v22; // [rsp+20h] [rbp-28h]
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF
  wchar_t *String2; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int16 *v25; // [rsp+90h] [rbp+48h] BYREF
  void *v26; // [rsp+98h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+A0h] [rbp+58h] BYREF
  struct _LUID v28; // [rsp+A8h] [rbp+60h] BYREF

  LastError = 0;
  v26 = a2;
  v25 = a3;
  hKey = 0;
  v8 = a2;
  TokenHandle = a4;
  String2 = 0;
  v28 = 0;
  v12 = a3;
  if ( a1 )
  {
    if ( (*((_DWORD *)a1 + 13) & 0x80u) == 0 )
    {
      if ( (a6 & 4) == 0 )
        goto LABEL_62;
      LastError = 1314;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_62;
      v14 = 119;
LABEL_26:
      v22 = LastError;
      goto LABEL_16;
    }
    if ( (a6 & 2) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
        WPP_SF_S(
          WPP_GLOBAL_Control->StubInfo,
          120,
          WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)a1 + 7));
      goto LABEL_62;
    }
    if ( !a3 )
    {
      v15 = CServiceRecord::OpenServiceConfigKey(a1, 0x20019u, 0, &hKey);
      LastError = v15;
      if ( v15 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_62;
        }
        v14 = 121;
        v22 = v15;
LABEL_16:
        WPP_SF_Sd(
          v13->StubInfo,
          v14,
          (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
          *((_QWORD *)a1 + 7),
          v22);
        goto LABEL_62;
      }
      v16 = ScReadPrivileges(hKey, &v25, 0);
      LastError = v16;
      if ( v16 )
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            122,
            (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
            *((_QWORD *)a1 + 7),
            v16);
        }
        v12 = v25;
        goto LABEL_62;
      }
      v12 = v25;
      LastError = 0;
      if ( !v25 )
      {
        LastError = 13;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        {
          goto LABEL_62;
        }
        v14 = (_DWORD)v25 + 123;
        goto LABEL_26;
      }
    }
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
      WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 124, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, *((_QWORD *)a1 + 7));
  }
  if ( !a2 )
  {
    v17 = ProcessHandle;
    if ( !TokenHandle && !OpenProcessToken(ProcessHandle, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        GetProcessId(v17);
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 125, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
      }
      goto LABEL_62;
    }
    LastError = ScGetTokenInformation(TokenHandle, TokenPrivileges, &v26);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        GetProcessId(v17);
        WPP_SF_Dd(WPP_GLOBAL_Control->StubInfo, 126, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids);
      }
      v8 = (struct _TOKEN_PRIVILEGES *)v26;
      goto LABEL_62;
    }
    v8 = (struct _TOKEN_PRIVILEGES *)v26;
    LastError = 0;
  }
  if ( !v12 || !*v12 || !v8 )
  {
    LastError = 87;
    goto LABEL_62;
  }
  v25 = v12;
  while ( 1 )
  {
    if ( !(unsigned int)ScGetToken(&v25, &String2) )
      goto LABEL_53;
    v18 = String2;
    if ( !(unsigned int)ScLookupPrivilegeValue(String2, &v28) )
      break;
    v19 = 0;
    if ( v8->PrivilegeCount )
    {
      while ( v8->Privileges[v19].Luid.LowPart != v28.LowPart || v8->Privileges[v19].Luid.HighPart != v28.HighPart )
      {
        if ( ++v19 >= v8->PrivilegeCount )
          goto LABEL_52;
      }
    }
    else
    {
LABEL_52:
      if ( v19 == v8->PrivilegeCount )
      {
        LastError = 1297;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 2) != 0 )
        {
          WPP_SF_S(WPP_GLOBAL_Control->StubInfo, 128, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids, v18);
        }
        goto LABEL_62;
      }
    }
LABEL_53:
    if ( !*v25 )
      goto LABEL_62;
  }
  v20 = GetLastError();
  LastError = v20;
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_Sd(
      WPP_GLOBAL_Control->StubInfo,
      127,
      (unsigned int)WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids,
      (_DWORD)v18,
      v20);
LABEL_62:
  if ( TokenHandle != a4 )
    CloseHandle(TokenHandle);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v12 != a3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  if ( v8 != a2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  return LastError;
}

```

## disassembly

```asm
0x140062d1c  push    rbp
0x140062d1e  push    rbx
0x140062d1f  push    rsi
0x140062d20  push    rdi
0x140062d21  push    r12
0x140062d23  push    r13
0x140062d25  push    r14
0x140062d27  push    r15
0x140062d29  mov     rbp, rsp
0x140062d2c  sub     rsp, 48h
0x140062d30  xor     ebx, ebx
0x140062d32  mov     [rbp+arg_8], rdx
0x140062d36  mov     [rbp+arg_0], r8
0x140062d3a  mov     r15, rdx
0x140062d3d  mov     [rbp+hKey], rbx
0x140062d41  mov     r14, rdx
0x140062d44  mov     [rbp+TokenHandle], r9
0x140062d48  mov     r13, r9
0x140062d4b  mov     [rbp+String2], rbx
0x140062d4f  mov     r12, r8
0x140062d52  mov     qword ptr [rbp+arg_18.LowPart], rbx
0x140062d56  mov     rdi, rcx
0x140062d59  lea     rdx, WPP_GLOBAL_Control
0x140062d60  mov     rsi, r8
0x140062d63  test    rcx, rcx
0x140062d66  jz      loc_140062F06
0x140062d6c  mov     eax, [rcx+34h]
0x140062d6f  test    al, al
0x140062d71  js      short loc_140062DA6
0x140062d73  test    byte ptr [rbp+arg_28], 4
0x140062d77  jz      loc_1400630D3
0x140062d7d  mov     ebx, 522h
0x140062d82  mov     rcx, cs:WPP_GLOBAL_Control
0x140062d89  cmp     rcx, rdx
0x140062d8c  jz      loc_1400630D3
0x140062d92  test    byte ptr [rcx+1Ch], 1
0x140062d96  jz      loc_1400630D3
0x140062d9c  mov     edx, 77h ; 'w'
0x140062da1  jmp     loc_140062ECB
0x140062da6  test    byte ptr [rbp+arg_28], 2
0x140062daa  jz      short loc_140062DE4
0x140062dac  mov     rcx, cs:WPP_GLOBAL_Control
0x140062db3  cmp     rcx, rdx
0x140062db6  jz      loc_1400630D3
0x140062dbc  test    byte ptr [rcx+1Ch], 2
0x140062dc0  jz      loc_1400630D3
0x140062dc6  mov     r9, [rdi+38h]
0x140062dca  mov     edx, 78h ; 'x'
0x140062dcf  mov     rcx, [rcx+10h]
0x140062dd3  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062dda  call    WPP_SF_S
0x140062ddf  jmp     loc_1400630D3
0x140062de4  test    r12, r12
0x140062de7  jnz     loc_140062EDB
0x140062ded  lea     r9, [rbp+hKey]; HKEY *
0x140062df1  mov     edx, 20019h; unsigned int
0x140062df6  call    ?OpenServiceConfigKey@CServiceRecord@@QEAAKKHPEAPEAUHKEY__@@@Z; CServiceRecord::OpenServiceConfigKey(ulong,int,HKEY__ * *)
0x140062dfb  mov     ebx, eax
0x140062dfd  test    eax, eax
0x140062dff  jz      short loc_140062E44
0x140062e01  mov     rcx, cs:WPP_GLOBAL_Control
0x140062e08  lea     rdx, WPP_GLOBAL_Control
0x140062e0f  cmp     rcx, rdx
0x140062e12  jz      loc_1400630D3
0x140062e18  test    byte ptr [rcx+1Ch], 1
0x140062e1c  jz      loc_1400630D3
0x140062e22  lea     edx, [r12+79h]
0x140062e27  mov     dword ptr [rsp+48h+var_28], eax
0x140062e2b  mov     r9, [rdi+38h]
0x140062e2f  mov     rcx, [rcx+10h]
0x140062e33  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062e3a  call    WPP_SF_Sd
0x140062e3f  jmp     loc_1400630D3
0x140062e44  mov     rcx, [rbp+hKey]; HKEY
0x140062e48  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x140062e4c  xor     r8d, r8d; unsigned int *
0x140062e4f  call    ?ScReadPrivileges@@YAKPEAUHKEY__@@PEAPEAGPEAK@Z; ScReadPrivileges(HKEY__ *,ushort * *,ulong *)
0x140062e54  mov     ebx, eax
0x140062e56  test    eax, eax
0x140062e58  jz      short loc_140062E99
0x140062e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140062e61  lea     rdx, WPP_GLOBAL_Control
0x140062e68  cmp     rcx, rdx
0x140062e6b  jz      short loc_140062E90
0x140062e6d  test    byte ptr [rcx+1Ch], 1
0x140062e71  jz      short loc_140062E90
0x140062e73  mov     r9, [rdi+38h]
0x140062e77  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062e7e  mov     rcx, [rcx+10h]
0x140062e82  mov     edx, 7Ah ; 'z'
0x140062e87  mov     dword ptr [rsp+48h+var_28], eax
0x140062e8b  call    WPP_SF_Sd
0x140062e90  mov     rsi, [rbp+arg_0]
0x140062e94  jmp     loc_1400630D3
0x140062e99  mov     rsi, [rbp+arg_0]
0x140062e9d  xor     ebx, ebx
0x140062e9f  test    rsi, rsi
0x140062ea2  jnz     short loc_140062ED4
0x140062ea4  lea     ebx, [rsi+0Dh]
0x140062ea7  mov     rcx, cs:WPP_GLOBAL_Control
0x140062eae  lea     rdx, WPP_GLOBAL_Control
0x140062eb5  cmp     rcx, rdx
0x140062eb8  jz      loc_1400630D3
0x140062ebe  test    byte ptr [rcx+1Ch], 1
0x140062ec2  jz      loc_1400630D3
0x140062ec8  lea     edx, [rsi+7Bh]
0x140062ecb  mov     dword ptr [rsp+48h+var_28], ebx
0x140062ecf  jmp     loc_140062E2B
0x140062ed4  lea     rdx, WPP_GLOBAL_Control
0x140062edb  mov     rcx, cs:WPP_GLOBAL_Control
0x140062ee2  cmp     rcx, rdx
0x140062ee5  jz      short loc_140062F06
0x140062ee7  test    byte ptr [rcx+1Ch], 4
0x140062eeb  jz      short loc_140062F06
0x140062eed  mov     r9, [rdi+38h]
0x140062ef1  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062ef8  mov     rcx, [rcx+10h]
0x140062efc  mov     edx, 7Ch ; '|'
0x140062f01  call    WPP_SF_S
0x140062f06  test    r15, r15
0x140062f09  jnz     loc_140062FF3
0x140062f0f  mov     rdi, [rbp+ProcessHandle]
0x140062f13  cmp     [rbp+TokenHandle], rbx
0x140062f17  jnz     short loc_140062F87
0x140062f19  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140062f1d  mov     rcx, rdi; ProcessHandle
0x140062f20  lea     edx, [r15+8]; DesiredAccess
0x140062f24  call    cs:__imp_OpenProcessToken
0x140062f2a  test    eax, eax
0x140062f2c  jnz     short loc_140062F87
0x140062f2e  call    cs:__imp_GetLastError
0x140062f34  mov     ebx, eax
0x140062f36  mov     rax, cs:WPP_GLOBAL_Control
0x140062f3d  lea     rdx, WPP_GLOBAL_Control
0x140062f44  cmp     rax, rdx
0x140062f47  jz      loc_1400630D3
0x140062f4d  test    byte ptr [rax+1Ch], 1
0x140062f51  jz      loc_1400630D3
0x140062f57  mov     rcx, rdi; Process
0x140062f5a  call    cs:__imp_GetProcessId
0x140062f60  mov     rcx, cs:WPP_GLOBAL_Control
0x140062f67  lea     edx, [r15+7Dh]
0x140062f6b  mov     r9d, eax
0x140062f6e  mov     dword ptr [rsp+48h+var_28], ebx
0x140062f72  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062f79  mov     rcx, [rcx+10h]
0x140062f7d  call    WPP_SF_Dd
0x140062f82  jmp     loc_1400630D3
0x140062f87  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140062f8b  lea     r8, [rbp+arg_8]; void **
0x140062f8f  mov     edx, 3; TokenInformationClass
0x140062f94  call    ?ScGetTokenInformation@@YAKPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; ScGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x140062f99  mov     ebx, eax
0x140062f9b  test    eax, eax
0x140062f9d  jz      short loc_140062FED
0x140062f9f  mov     rax, cs:WPP_GLOBAL_Control
0x140062fa6  lea     rdx, WPP_GLOBAL_Control
0x140062fad  cmp     rax, rdx
0x140062fb0  jz      short loc_140062FE4
0x140062fb2  test    byte ptr [rax+1Ch], 1
0x140062fb6  jz      short loc_140062FE4
0x140062fb8  mov     rcx, rdi; Process
0x140062fbb  call    cs:__imp_GetProcessId
0x140062fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140062fc8  lea     r8, WPP_a9b8e10de094345130a6b8d864a6a1a6_Traceguids
0x140062fcf  mov     edx, 7Eh ; '~'
0x140062fd4  mov     dword ptr [rsp+48h+var_28], ebx
0x140062fd8  mov     r9d, eax
0x140062fdb  mov     rcx, [rcx+10h]
0x140062fdf  call    WPP_SF_Dd
0x140062fe4  mov     r14, [rbp+arg_8]
0x140062fe8  jmp     loc_1400630D3
0x140062fed  mov     r14, [rbp+arg_8]
0x140062ff1  xor     ebx, ebx
0x140062ff3  test    rsi, rsi
0x140062ff6  jz      loc_1400630CE
0x140062ffc  cmp     [rsi], bx
0x140062fff  jz      loc_1400630CE
0x140063005  test    r14, r14
0x140063008  jz      loc_1400630CE
0x14006300e  mov     [rbp+arg_0], rsi
0x140063012  lea     rdx, [rbp+String2]; unsigned __int16 **
0x140063016  lea     rcx, [rbp+arg_0]; unsigned __int16 **
0x14006301a  call    ?ScGetToken@@YAHPEAPEAG0@Z; ScGetToken(ushort * *,ushort * *)
0x14006301f  test    eax, eax
0x140063021  jz      short loc_140063066
0x140063023  mov     rdi, [rbp+String2]
0x140063027  lea     rdx, [rbp+arg_18]; struct _LUID *
0x14006302b  mov     rcx, rdi; String2
0x14006302e  call    ?ScLookupPrivilegeValue@@YAHPEAGPEAU_LUID@@@Z; ScLookupPrivilegeValue(ushort *,_LUID *)
0x140063033  test    eax, eax
0x140063035  jz      short loc_14006309C
0x140063037  mov     edx, ebx
0x140063039  cmp     [r14], ebx
0x14006303c  jbe     short loc_140063061
0x14006303e  mov     rax, qword ptr [rbp+arg_18.LowPart]
0x140063042  mov     r9d, [rbp+arg_18.HighPart]
0x140063046  mov     ecx, edx
0x140063048  lea     r8, [rcx+rcx*2]
0x14006304c  cmp     [r14+r8*4+4], eax
0x140063051  jnz     short loc_14006305A
0x140063053  cmp     [r14+r8*4+8], r9d
0x140063058  jz      short loc_140063066
0x14006305a  inc     edx
0x14006305c  cmp     edx, [r14]
0x14006305f  jb      short loc_140063046
0x140063061  cmp     edx, [r14]
0x140063064  jz      short loc_140063071
0x140063066  mov     rax, [rbp+arg_0]
0x14006306a  cmp     [rax], bx
0x14006306d  jnz     short loc_140063012
0x14006306f  jmp     short loc_1400630D3
0x140063071  mov     ebx, 511h
0x140063076  mov     rcx, cs:WPP_GLOBAL_Control
0x14006307d  lea     rdx, WPP_GLOBAL_Control
0x140063084  cmp     rcx, rdx
0x140063087  jz      short loc_1400630D3
0x140063089  test    byte ptr [rcx+1Ch], 2
0x14006308d  jz      short loc_1400630D3
0x14006308f  mov     edx, 80h
0x140063094  mov     r9, rdi
0x140063097  jmp     loc_140062DCF
0x14006309c  call    cs:__imp_GetLastError
0x1400630a2  mov     ebx, eax
0x1400630a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400630ab  lea     rdx, WPP_GLOBAL_Control
0x1400630b2  cmp     rcx, rdx
0x1400630b5  jz      short loc_1400630D3
0x1400630b7  test    byte ptr [rcx+1Ch], 1
0x1400630bb  jz      short loc_1400630D3
0x1400630bd  mov     edx, 7Fh
0x1400630c2  mov     dword ptr [rsp+48h+var_28], eax
0x1400630c6  mov     r9, rdi
0x1400630c9  jmp     loc_140062E2F
0x1400630ce  mov     ebx, 57h ; 'W'
0x1400630d3  mov     rcx, [rbp+TokenHandle]; hObject
0x1400630d7  cmp     rcx, r13
0x1400630da  jz      short loc_1400630E2
0x1400630dc  call    cs:__imp_CloseHandle
0x1400630e2  mov     rcx, [rbp+hKey]; hKey
0x1400630e6  test    rcx, rcx
0x1400630e9  jz      short loc_1400630F1
0x1400630eb  call    cs:__imp_RegCloseKey
0x1400630f1  cmp     rsi, r12
0x1400630f4  jz      short loc_14006310E
0x1400630f6  mov     rcx, gs:60h
0x1400630ff  mov     r8, rsi; P
0x140063102  xor     edx, edx; Flags
0x140063104  mov     rcx, [rcx+30h]; HeapHandle
0x140063108  call    cs:__imp_RtlFreeHeap
0x14006310e  cmp     r14, r15
0x140063111  jz      short loc_14006312B
0x140063113  mov     rcx, gs:60h
0x14006311c  mov     r8, r14; P
0x14006311f  xor     edx, edx; Flags
0x140063121  mov     rcx, [rcx+30h]; HeapHandle
0x140063125  call    cs:__imp_RtlFreeHeap
0x14006312b  mov     eax, ebx
0x14006312d  add     rsp, 48h
0x140063131  pop     r15
0x140063133  pop     r14
0x140063135  pop     r13
0x140063137  pop     r12
0x140063139  pop     rdi
0x14006313a  pop     rsi
0x14006313b  pop     rbx
0x14006313c  pop     rbp
0x14006313d  retn
```

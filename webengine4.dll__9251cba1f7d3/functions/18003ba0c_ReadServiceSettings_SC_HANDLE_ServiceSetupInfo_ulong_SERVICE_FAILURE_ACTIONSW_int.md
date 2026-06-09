# ReadServiceSettings(SC_HANDLE__ *,ServiceSetupInfo *,ulong *,_SERVICE_FAILURE_ACTIONSW * *,int *)

- ea: `0x18003ba0c`
- end: `0x18003bcce`
- name: `?ReadServiceSettings@@YAJPEAUSC_HANDLE__@@PEAUServiceSetupInfo@@PEAKPEAPEAU_SERVICE_FAILURE_ACTIONSW@@PEAH@Z`
- size: `706`
- prototype: `__int64 __usercall@<rax>(SC_HANDLE hSCManager@<rcx>, struct ServiceSetupInfo *@<rdx>, unsigned int *@<r8>, struct _SERVICE_FAILURE_ACTIONSW **@<r9>, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18004086c`

## callees

- `0x180007824`
- `0x18003abe4`
- `0x18003ba0c`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18003bac2`
- `KERNEL32!GetLastError` at `0x18003bb33`
- `KERNEL32!GetLastError` at `0x18003bac2`
- `KERNEL32!GetLastError` at `0x18003bb33`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003bc48`
- `ucrtbase_clr0400!_wcsicmp` at `0x18003bc48`
- `ADVAPI32!CloseServiceHandle` at `0x18003bc8c`
- `ADVAPI32!CloseServiceHandle` at `0x18003bc8c`
- `ADVAPI32!OpenServiceW` at `0x18003ba87`
- `ADVAPI32!OpenServiceW` at `0x18003ba87`
- `ADVAPI32!QueryServiceConfigW` at `0x18003bab1`
- `ADVAPI32!QueryServiceConfigW` at `0x18003baf5`
- `ADVAPI32!QueryServiceConfigW` at `0x18003bab1`
- `ADVAPI32!QueryServiceConfigW` at `0x18003baf5`
- `ADVAPI32!QueryServiceConfig2W` at `0x18003bb1c`
- `ADVAPI32!QueryServiceConfig2W` at `0x18003bb7f`
- `ADVAPI32!QueryServiceConfig2W` at `0x18003bb1c`
- `ADVAPI32!QueryServiceConfig2W` at `0x18003bb7f`

## string_xrefs

- `0x18003ba47`: `Reading various service settings for: `
- `0x18003bc5e`: `Reading various service settings for: `
- `0x18003bc72`: `Reading various service settings for: `
- `0x18003ba61`: `ReadServiceSettings`

## pseudocode

```c
__int64 __fastcall ReadServiceSettings(
        SC_HANDLE hSCManager,
        struct ServiceSetupInfo *a2,
        unsigned int *a3,
        struct _SERVICE_FAILURE_ACTIONSW **a4,
        int *a5)
{
  const unsigned __int16 *v5; // rax
  struct _QUERY_SERVICE_CONFIGW *v10; // rdi
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  unsigned int LastWin32Error; // ebx
  struct _QUERY_SERVICE_CONFIGW *v14; // rax
  struct _SERVICE_FAILURE_ACTIONSW *v15; // rax
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  wchar_t v18; // ax
  wchar_t *v19; // rax
  int v20; // ecx
  DWORD pcbBytesNeeded[4]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t String1[520]; // [rsp+40h] [rbp-C0h] BYREF

  v5 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
  pcbBytesNeeded[0] = 0;
  v10 = 0;
  CSetupLogging::Log(1, "ReadServiceSettings", 0, "Reading various service settings for: ", v5);
  *a3 = -1;
  *a4 = 0;
  v11 = OpenServiceW(hSCManager, *((LPCWSTR *)a2 + 3), 1u);
  v12 = v11;
  if ( !v11 )
    goto LABEL_2;
  if ( QueryServiceConfigW(v11, 0, 0, pcbBytesNeeded) )
  {
    LastWin32Error = -2147418113;
    goto LABEL_28;
  }
  if ( GetLastError() != 122 )
    goto LABEL_2;
  v14 = (struct _QUERY_SERVICE_CONFIGW *)MemAlloc(pcbBytesNeeded[0]);
  v10 = v14;
  if ( !v14 )
  {
    LastWin32Error = -2147024882;
    goto LABEL_28;
  }
  if ( QueryServiceConfigW(v12, v14, pcbBytesNeeded[0], pcbBytesNeeded) )
  {
    *a3 = v10->dwStartType;
    if ( QueryServiceConfig2W(v12, 2u, 0, 0, pcbBytesNeeded) )
    {
      LastWin32Error = -2147418113;
      goto LABEL_28;
    }
    if ( GetLastError() != 122 )
      goto LABEL_13;
    v15 = (struct _SERVICE_FAILURE_ACTIONSW *)MemAlloc(pcbBytesNeeded[0]);
    *a4 = v15;
    if ( v15 )
    {
      if ( !QueryServiceConfig2W(v12, 2u, (LPBYTE)v15, pcbBytesNeeded[0], pcbBytesNeeded) )
      {
LABEL_13:
        LastWin32Error = GetLastWin32Error();
        goto LABEL_28;
      }
      v16 = 520;
      v17 = String1;
      do
      {
        if ( v16 == -2147483126 )
          break;
        v18 = *(wchar_t *)((char *)v17 + (char *)&Names::s_wszInstallDirectory - (char *)String1);
        if ( !v18 )
          break;
        *v17++ = v18;
        --v16;
      }
      while ( v16 );
      v19 = v17 - 1;
      if ( v16 )
        v19 = v17;
      *v19 = 0;
      LastWin32Error = v16 == 0 ? 0x8007007A : 0;
      if ( v16 )
      {
        LastWin32Error = StringCchCatW(String1, 0x208u, L"\\");
        if ( !LastWin32Error )
        {
          LastWin32Error = StringCchCatW(String1, 0x208u, L"aspnet_state");
          if ( !LastWin32Error )
          {
            LastWin32Error = StringCchCatW(String1, 0x208u, L".exe");
            if ( !LastWin32Error )
              *a5 = _wcsicmp(String1, v10->lpBinaryPathName) == 0;
          }
        }
      }
    }
    else
    {
      LastWin32Error = -2147024882;
    }
  }
  else
  {
LABEL_2:
    LastWin32Error = GetLastWin32Error();
  }
LABEL_28:
  v20 = 0;
  if ( (_WORD)LastWin32Error != 1060 )
    v20 = LastWin32Error;
  CSetupLogging::Log(
    v20,
    "Reading various service settings for: ",
    0,
    "Reading various service settings for: ",
    *((const unsigned __int16 **)a2 + 3));
  if ( v12 )
    CloseServiceHandle(v12);
  if ( LastWin32Error )
  {
    MemFree(*a4);
    *a4 = 0;
  }
  MemFree(v10);
  return LastWin32Error;
}

```

## disassembly

```asm
0x18003ba0c  push    rbp
0x18003ba0e  push    rbx
0x18003ba0f  push    rsi
0x18003ba10  push    rdi
0x18003ba11  push    r12
0x18003ba13  push    r13
0x18003ba15  push    r14
0x18003ba17  push    r15
0x18003ba19  lea     rbp, [rsp-368h]
0x18003ba21  sub     rsp, 468h
0x18003ba28  mov     rax, cs:__security_cookie
0x18003ba2f  xor     rax, rsp
0x18003ba32  mov     [rbp+3A0h+var_50], rax
0x18003ba39  mov     rax, [rdx+18h]
0x18003ba3d  mov     r14, r9
0x18003ba40  mov     r12, [rbp+3A0h+arg_20]
0x18003ba47  lea     r9, aReadingVarious; "Reading various service settings for: "
0x18003ba4e  and     [rsp+4A0h+pcbBytesNeeded], 0
0x18003ba53  mov     r15, r8
0x18003ba56  mov     r13, rdx
0x18003ba59  mov     [rsp+4A0h+var_480], rax; unsigned __int16 *
0x18003ba5e  mov     rbx, rcx
0x18003ba61  lea     rdx, aReadserviceset; "ReadServiceSettings"
0x18003ba68  xor     edi, edi
0x18003ba6a  xor     r8d, r8d; unsigned int
0x18003ba6d  lea     ecx, [rdi+1]; int
0x18003ba70  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003ba75  or      dword ptr [r15], 0FFFFFFFFh
0x18003ba79  lea     r8d, [rdi+1]; dwDesiredAccess
0x18003ba7d  and     [r14], rdi
0x18003ba80  mov     rcx, rbx; hSCManager
0x18003ba83  mov     rdx, [r13+18h]; lpServiceName
0x18003ba87  call    cs:__imp_OpenServiceW
0x18003ba8d  mov     rsi, rax
0x18003ba90  test    rax, rax
0x18003ba93  jnz     short loc_18003BAA4
0x18003ba95  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003ba9a  mov     ebx, eax
0x18003ba9c  xor     r15d, r15d
0x18003ba9f  jmp     loc_18003BC5A
0x18003baa4  lea     r9, [rsp+4A0h+pcbBytesNeeded]; pcbBytesNeeded
0x18003baa9  xor     r8d, r8d; cbBufSize
0x18003baac  xor     edx, edx; lpServiceConfig
0x18003baae  mov     rcx, rsi; hService
0x18003bab1  call    cs:__imp_QueryServiceConfigW
0x18003bab7  test    eax, eax
0x18003bab9  jz      short loc_18003BAC2
0x18003babb  mov     ebx, 8000FFFFh
0x18003bac0  jmp     short loc_18003BA9C
0x18003bac2  call    cs:__imp_GetLastError
0x18003bac8  cmp     eax, 7Ah ; 'z'
0x18003bacb  jnz     short loc_18003BA95
0x18003bacd  mov     ecx, [rsp+4A0h+pcbBytesNeeded]; unsigned __int64
0x18003bad1  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003bad6  mov     rdi, rax
0x18003bad9  test    rax, rax
0x18003badc  jnz     short loc_18003BAE5
0x18003bade  mov     ebx, 8007000Eh
0x18003bae3  jmp     short loc_18003BA9C
0x18003bae5  mov     r8d, [rsp+4A0h+pcbBytesNeeded]; cbBufSize
0x18003baea  lea     r9, [rsp+4A0h+pcbBytesNeeded]; pcbBytesNeeded
0x18003baef  mov     rdx, rdi; lpServiceConfig
0x18003baf2  mov     rcx, rsi; hService
0x18003baf5  call    cs:__imp_QueryServiceConfigW
0x18003bafb  test    eax, eax
0x18003bafd  jz      short loc_18003BA95
0x18003baff  mov     eax, [rdi+4]
0x18003bb02  xor     r9d, r9d; cbBufSize
0x18003bb05  mov     [r15], eax
0x18003bb08  xor     r8d, r8d; lpBuffer
0x18003bb0b  lea     rax, [rsp+4A0h+pcbBytesNeeded]
0x18003bb10  mov     rcx, rsi; hService
0x18003bb13  mov     [rsp+4A0h+var_480], rax; pcbBytesNeeded
0x18003bb18  lea     edx, [r9+2]; dwInfoLevel
0x18003bb1c  call    cs:__imp_QueryServiceConfig2W
0x18003bb22  xor     r15d, r15d
0x18003bb25  test    eax, eax
0x18003bb27  jz      short loc_18003BB33
0x18003bb29  mov     ebx, 8000FFFFh
0x18003bb2e  jmp     loc_18003BC5A
0x18003bb33  call    cs:__imp_GetLastError
0x18003bb39  cmp     eax, 7Ah ; 'z'
0x18003bb3c  jz      short loc_18003BB4A
0x18003bb3e  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18003bb43  mov     ebx, eax
0x18003bb45  jmp     loc_18003BC5A
0x18003bb4a  mov     ecx, [rsp+4A0h+pcbBytesNeeded]; unsigned __int64
0x18003bb4e  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18003bb53  mov     [r14], rax
0x18003bb56  test    rax, rax
0x18003bb59  jnz     short loc_18003BB65
0x18003bb5b  mov     ebx, 8007000Eh
0x18003bb60  jmp     loc_18003BC5A
0x18003bb65  mov     r9d, [rsp+4A0h+pcbBytesNeeded]; cbBufSize
0x18003bb6a  lea     rcx, [rsp+4A0h+pcbBytesNeeded]
0x18003bb6f  mov     [rsp+4A0h+var_480], rcx; pcbBytesNeeded
0x18003bb74  mov     r8, rax; lpBuffer
0x18003bb77  mov     rcx, rsi; hService
0x18003bb7a  mov     edx, 2; dwInfoLevel
0x18003bb7f  call    cs:__imp_QueryServiceConfig2W
0x18003bb85  test    eax, eax
0x18003bb87  jz      short loc_18003BB3E
0x18003bb89  mov     r9d, 208h
0x18003bb8f  lea     r8, ?s_wszInstallDirectory@Names@@0PAGA; ushort near * Names::s_wszInstallDirectory
0x18003bb96  lea     rax, [rsp+4A0h+String1]
0x18003bb9b  mov     edx, r9d
0x18003bb9e  sub     r8, rax
0x18003bba1  lea     rcx, [rsp+4A0h+String1]
0x18003bba6  lea     rax, [rdx+7FFFFDF6h]
0x18003bbad  test    rax, rax
0x18003bbb0  jz      short loc_18003BBC9
0x18003bbb2  movzx   eax, word ptr [r8+rcx]
0x18003bbb7  test    ax, ax
0x18003bbba  jz      short loc_18003BBC9
0x18003bbbc  mov     [rcx], ax
0x18003bbbf  add     rcx, 2
0x18003bbc3  sub     rdx, 1
0x18003bbc7  jnz     short loc_18003BBA6
0x18003bbc9  test    rdx, rdx
0x18003bbcc  lea     rax, [rcx-2]
0x18003bbd0  cmovnz  rax, rcx
0x18003bbd4  mov     [rax], r15w
0x18003bbd8  mov     rax, rdx
0x18003bbdb  neg     rax
0x18003bbde  sbb     ebx, ebx
0x18003bbe0  not     ebx
0x18003bbe2  and     ebx, 8007007Ah
0x18003bbe8  test    rdx, rdx
0x18003bbeb  jz      short loc_18003BC5A
0x18003bbed  lea     r8, SubBlock; "\\"
0x18003bbf4  mov     rdx, r9; unsigned __int64
0x18003bbf7  lea     rcx, [rsp+4A0h+String1]; unsigned __int16 *
0x18003bbfc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bc01  mov     ebx, eax
0x18003bc03  test    eax, eax
0x18003bc05  jnz     short loc_18003BC5A
0x18003bc07  lea     r8, aAspnetState_0; "aspnet_state"
0x18003bc0e  mov     edx, 208h; unsigned __int64
0x18003bc13  lea     rcx, [rsp+4A0h+String1]; unsigned __int16 *
0x18003bc18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bc1d  mov     ebx, eax
0x18003bc1f  test    eax, eax
0x18003bc21  jnz     short loc_18003BC5A
0x18003bc23  lea     r8, aExe; ".exe"
0x18003bc2a  mov     edx, 208h; unsigned __int64
0x18003bc2f  lea     rcx, [rsp+4A0h+String1]; unsigned __int16 *
0x18003bc34  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003bc39  mov     ebx, eax
0x18003bc3b  test    eax, eax
0x18003bc3d  jnz     short loc_18003BC5A
0x18003bc3f  mov     rdx, [rdi+10h]; String2
0x18003bc43  lea     rcx, [rsp+4A0h+String1]; String1
0x18003bc48  call    cs:__imp__wcsicmp
0x18003bc4e  mov     ecx, r15d
0x18003bc51  test    eax, eax
0x18003bc53  setz    cl
0x18003bc56  mov     [r12], ecx
0x18003bc5a  mov     rax, [r13+18h]
0x18003bc5e  lea     r9, aReadingVarious; "Reading various service settings for: "
0x18003bc65  mov     ecx, r15d
0x18003bc68  mov     [rsp+4A0h+var_480], rax; unsigned __int16 *
0x18003bc6d  cmp     bx, 424h
0x18003bc72  lea     rdx, aReadingVarious; "Reading various service settings for: "
0x18003bc79  cmovnz  ecx, ebx; int
0x18003bc7c  xor     r8d, r8d; unsigned int
0x18003bc7f  call    ?Log@CSetupLogging@@SAXJPEBDI0PEBG@Z; CSetupLogging::Log(long,char const *,uint,char const *,ushort const *)
0x18003bc84  test    rsi, rsi
0x18003bc87  jz      short loc_18003BC92
0x18003bc89  mov     rcx, rsi; hSCObject
0x18003bc8c  call    cs:__imp_CloseServiceHandle
0x18003bc92  test    ebx, ebx
0x18003bc94  jz      short loc_18003BCA1
0x18003bc96  mov     rcx, [r14]; lpMem
0x18003bc99  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003bc9e  mov     [r14], r15
0x18003bca1  mov     rcx, rdi; lpMem
0x18003bca4  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18003bca9  mov     eax, ebx
0x18003bcab  mov     rcx, [rbp+3A0h+var_50]
0x18003bcb2  xor     rcx, rsp; StackCookie
0x18003bcb5  call    __security_check_cookie
0x18003bcba  add     rsp, 468h
0x18003bcc1  pop     r15
0x18003bcc3  pop     r14
0x18003bcc5  pop     r13
0x18003bcc7  pop     r12
0x18003bcc9  pop     rdi
0x18003bcca  pop     rsi
0x18003bccb  pop     rbx
0x18003bccc  pop     rbp
0x18003bccd  retn
```

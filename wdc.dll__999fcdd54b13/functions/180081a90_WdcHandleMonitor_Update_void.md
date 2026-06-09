# WdcHandleMonitor::Update(void)

- ea: `0x180081a90`
- end: `0x180081f71`
- name: `?Update@WdcHandleMonitor@@MEAAJXZ`
- size: `1249`
- prototype: `__int64 __fastcall(WdcHandleMonitor *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x1800150d0`
- `0x180016880`
- `0x180019990`
- `0x180038024`
- `0x18004bcc0`
- `0x1800797bc`
- `0x18007990c`
- `0x180081a90`
- `0x180086010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180081e6c`
- `ntdll!RtlNtStatusToDosError` at `0x180081e6c`
- `ntdll!NtQuerySystemInformation` at `0x180081bb5`
- `ntdll!NtQuerySystemInformation` at `0x180081bb5`
- `KERNEL32!GetCurrentProcessId` at `0x180081ad1`
- `KERNEL32!GetCurrentProcessId` at `0x180081ad1`
- `KERNEL32!CloseHandle` at `0x180081c3c`
- `KERNEL32!CloseHandle` at `0x180081cf5`
- `KERNEL32!CloseHandle` at `0x180081daf`
- `KERNEL32!CloseHandle` at `0x180081f1c`
- `KERNEL32!CloseHandle` at `0x180081f55`
- `KERNEL32!CloseHandle` at `0x180081c3c`
- `KERNEL32!CloseHandle` at `0x180081cf5`
- `KERNEL32!CloseHandle` at `0x180081daf`
- `KERNEL32!CloseHandle` at `0x180081f1c`
- `KERNEL32!CloseHandle` at `0x180081f55`
- `KERNEL32!GetLastError` at `0x180081d61`
- `KERNEL32!GetLastError` at `0x180081d61`
- `KERNEL32!WaitForSingleObject` at `0x180081dd2`
- `KERNEL32!WaitForSingleObject` at `0x180081f05`
- `KERNEL32!WaitForSingleObject` at `0x180081dd2`
- `KERNEL32!WaitForSingleObject` at `0x180081f05`
- `KERNEL32!SetEvent` at `0x180081ef5`
- `KERNEL32!SetEvent` at `0x180081ef5`
- `KERNEL32!OpenProcess` at `0x180081cd6`
- `KERNEL32!OpenProcess` at `0x180081cd6`
- `KERNEL32!DuplicateHandle` at `0x180081d57`
- `KERNEL32!DuplicateHandle` at `0x180081d57`
- `KERNEL32!GetCurrentProcess` at `0x180081d15`
- `KERNEL32!GetCurrentProcess` at `0x180081d1e`
- `KERNEL32!GetCurrentProcess` at `0x180081d2c`
- `KERNEL32!GetCurrentProcess` at `0x180081d15`
- `KERNEL32!GetCurrentProcess` at `0x180081d1e`
- `KERNEL32!GetCurrentProcess` at `0x180081d2c`
- `USER32!PostMessageW` at `0x180081ede`
- `USER32!PostMessageW` at `0x180081ede`
- `USER32!CharLowerW` at `0x180081bf9`
- `USER32!CharLowerW` at `0x180081bf9`
- `OLEAUT32!__imp_SysAllocString` at `0x180081b37`
- `OLEAUT32!__imp_SysAllocString` at `0x180081b37`
- `OLEAUT32!__imp_SysFreeString` at `0x180081b2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180081f42`
- `OLEAUT32!__imp_SysFreeString` at `0x180081b2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180081f42`

## string_xrefs

- `0x180081e50`: `WdcHandleMonitor::Update`

## pseudocode

```c
__int64 __fastcall WdcHandleMonitor::Update(WdcHandleMonitor *this)
{
  signed int v2; // ebx
  OLECHAR *v3; // r12
  _QWORD *v4; // r15
  char *v5; // r13
  WdcLockObject *v6; // rcx
  __int64 v7; // rdi
  int v8; // r14d
  const OLECHAR *v9; // rbx
  BSTR v10; // rax
  WdcLockObject *v11; // rdi
  int v12; // eax
  const char *v13; // rdx
  int v14; // r8d
  __int64 v15; // rcx
  __int64 v16; // r14
  unsigned __int64 v17; // rcx
  int v18; // r11d
  DWORD v19; // edi
  DWORD v20; // eax
  char *v21; // rbx
  char *v22; // rdx
  void *v23; // r14
  HANDLE CurrentProcess; // rbx
  HANDLE v25; // rcx
  HANDLE v26; // r8
  signed int LastError; // eax
  bool v28; // sf
  signed int v29; // eax
  void *v30; // rcx
  unsigned __int16 v31; // di
  signed int v32; // eax
  const char *v33; // rdx
  int v34; // r8d
  char *v35; // rcx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-59h]
  unsigned int v38; // [rsp+40h] [rbp-39h]
  int v39; // [rsp+44h] [rbp-35h] BYREF
  int v40; // [rsp+48h] [rbp-31h] BYREF
  DWORD dwProcessId; // [rsp+4Ch] [rbp-2Dh] BYREF
  int v42; // [rsp+50h] [rbp-29h]
  int v43; // [rsp+54h] [rbp-25h] BYREF
  char *v44; // [rsp+58h] [rbp-21h]
  HANDLE TargetHandle; // [rsp+60h] [rbp-19h] BYREF
  WdcFilter *v46; // [rsp+68h] [rbp-11h]
  WdcLockObject *v47; // [rsp+70h] [rbp-9h]
  HWND hWnd; // [rsp+78h] [rbp-1h]
  __int64 v49; // [rsp+80h] [rbp+7h] BYREF
  __int64 v50; // [rsp+88h] [rbp+Fh]
  ULONG ReturnLength; // [rsp+F0h] [rbp+77h] BYREF
  DWORD CurrentProcessId; // [rsp+F8h] [rbp+7Fh]

  v2 = 0;
  v43 = 0;
  v39 = 0;
  v3 = 0;
  v40 = 0;
  v4 = 0;
  hWnd = 0;
  v47 = 0;
  v46 = 0;
  ReturnLength = 0;
  dwProcessId = 0;
  v44 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v5 = 0;
  TargetHandle = 0;
  WdcLockObject::LockEnter(this, &v43);
LABEL_2:
  while ( 2 )
  {
    v6 = (WdcHandleMonitor *)((char *)this + 9416);
LABEL_3:
    WdcLockObject::LockEnter(v6, &v39);
    v7 = *((_QWORD *)this + 1168);
    v8 = *((unsigned __int16 *)this + 4994);
    if ( v7 )
    {
      v9 = (const OLECHAR *)*((_QWORD *)this + 1169);
      hWnd = (HWND)*((_QWORD *)this + 1168);
      if ( v3 )
      {
        SysFreeString(v3);
        v3 = 0;
      }
      v10 = SysAllocString(v9);
      if ( v9 && !v10 )
      {
        dwDesiredAccess[0] = -2147024882;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mmc\\inline.cpp",
          "WdcAssignString",
          0,
          L"FAILURE: 0x%08x",
          *(_QWORD *)dwDesiredAccess);
LABEL_59:
        dwDesiredAccess[0] = -2147024882;
        v2 = -2147024882;
        WdcDebugMessage(
          "base\\diagnosis\\pdui\\perfmon\\mon\\handle.cpp",
          "WdcHandleMonitor::Update",
          0,
          L"FAILURE: 0x%08x",
          *(_QWORD *)dwDesiredAccess);
        goto LABEL_60;
      }
      v3 = v10;
      v2 = 0;
      v47 = (WdcLockObject *)*((_QWORD *)this + 1163);
    }
    *((_QWORD *)this + 1168) = 0;
    WdcLockObject::LockLeave((WdcHandleMonitor *)((char *)this + 9416), &v39);
    if ( !v7 )
    {
      v31 = (v3 != 0) | 2;
      if ( !v47 )
        v31 = v3 != 0;
      goto LABEL_67;
    }
    (*(void (__fastcall **)(WdcHandleMonitor *, __int64))(*(_QWORD *)this + 48LL))(this, 1);
    v11 = v47;
    if ( !v3 && !v47 )
      continue;
    break;
  }
  while ( 1 )
  {
    v12 = NtQuerySystemInformation(SystemExtendedHandleInformation, v4, ReturnLength, &ReturnLength);
    if ( v12 >= 0 )
    {
      if ( v3 )
        CharLowerW(v3);
      if ( v11 )
      {
        WdcLockObject::LockEnter(v11, &v40);
        v46 = WdcFilter::DuplicateFilter(v11);
        WdcLockObject::LockLeave(v11, &v40);
        if ( !v46 )
          goto LABEL_59;
      }
      if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CloseHandle(v5);
        v5 = 0;
      }
      v42 = -1;
      v15 = 0;
      v38 = 0;
      if ( *v4 )
      {
        while ( 1 )
        {
          v16 = 5 * v15;
          v17 = v4[5 * v15 + 3];
          v50 = v16;
          v2 = ULongLongToULong(v17, &dwProcessId);
          if ( v2 < 0 )
          {
            v2 = 0;
            goto LABEL_55;
          }
          v19 = dwProcessId;
          if ( v18 == dwProcessId )
            goto LABEL_55;
          if ( v42 == dwProcessId )
          {
            v20 = CurrentProcessId;
            v21 = v5;
            v44 = v5;
          }
          else
          {
            v49 = dwProcessId;
            if ( v46 && !(unsigned int)WdcFilter::Match(v46, (struct _PROCESS_KEY *)&v49) )
              goto LABEL_55;
            v20 = CurrentProcessId;
            if ( CurrentProcessId != v19 )
            {
              v44 = (char *)OpenProcess(0x40u, 0, v19);
              v22 = v44;
              if ( !v44 )
                goto LABEL_55;
              if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              {
                CloseHandle(v5);
                v22 = v44;
              }
              v20 = CurrentProcessId;
              v5 = v22;
              v42 = v19;
            }
            v21 = v44;
          }
          v23 = (void *)v4[v16 + 4];
          if ( v20 == v19 )
          {
            CurrentProcess = GetCurrentProcess();
            v25 = GetCurrentProcess();
            v26 = CurrentProcess;
          }
          else
          {
            v26 = GetCurrentProcess();
            v25 = v21;
          }
          if ( !DuplicateHandle(v25, v23, v26, &TargetHandle, 0, 0, 2u) )
            break;
LABEL_50:
          WdcHandleMonitor::AddHandle(this, v19, TargetHandle, HIWORD(v4[v50 + 5]), v3);
          if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          {
            CloseHandle(TargetHandle);
            TargetHandle = 0;
          }
          v30 = (void *)*((_QWORD *)this + 1145);
          v2 = 0;
          if ( v30 && !(_BYTE)v38 && !WaitForSingleObject(v30, 0) )
            goto LABEL_56;
LABEL_55:
          v15 = ++v38;
          if ( (unsigned __int64)v38 >= *v4 )
            goto LABEL_56;
        }
        LastError = GetLastError();
        v28 = LastError < 0;
        if ( LastError )
        {
          if ( LastError > 0 )
          {
            v29 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_47;
          }
        }
        else
        {
          v29 = -2147467259;
LABEL_47:
          v28 = v29 < 0;
        }
        if ( v28 )
        {
          v2 = 0;
          goto LABEL_55;
        }
        goto LABEL_50;
      }
LABEL_56:
      v6 = (WdcHandleMonitor *)((char *)this + 9416);
      if ( v46 )
      {
        WdcDataPortal::Release(v46);
        v46 = 0;
        goto LABEL_2;
      }
      goto LABEL_3;
    }
    if ( v12 != -1073741820 )
      break;
    if ( v4 )
      WdcFree(v4, v13, v14);
    v4 = WdcAlloc(ReturnLength, v13, v14);
    if ( !v4 )
      goto LABEL_59;
  }
  v32 = RtlNtStatusToDosError(v12);
  v2 = 0;
  if ( v32 )
  {
    if ( v32 > 0 )
      v2 = (unsigned __int16)v32 | 0x80070000;
    else
      v2 = v32;
  }
LABEL_60:
  v31 = 0;
LABEL_67:
  WdcLockObject::LockLeave((WdcHandleMonitor *)((char *)this + 9416), &v39);
  WdcLockObject::LockLeave(this, &v43);
  if ( hWnd )
    PostMessageW(hWnd, 0x401u, v31 | (v8 << 16), 0);
  if ( *((_QWORD *)this + 1170) )
  {
    SetEvent(*((HANDLE *)this + 1172));
    WaitForSingleObject(*((HANDLE *)this + 1170), 0xFFFFFFFF);
    v35 = (char *)*((_QWORD *)this + 1170);
    if ( (unsigned __int64)(v35 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle(v35);
      *((_QWORD *)this + 1170) = 0;
    }
  }
  if ( v4 )
    WdcFree(v4, v33, v34);
  if ( v3 )
    SysFreeString(v3);
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180081a90  push    rbp
0x180081a92  push    rbx
0x180081a93  push    rsi
0x180081a94  push    rdi
0x180081a95  push    r12
0x180081a97  push    r13
0x180081a99  push    r14
0x180081a9b  push    r15
0x180081a9d  lea     rbp, [rsp-1Fh]
0x180081aa2  sub     rsp, 98h
0x180081aa9  xor     edi, edi
0x180081aab  mov     rsi, rcx
0x180081aae  mov     ebx, edi
0x180081ab0  mov     [rbp+57h+var_7C], edi
0x180081ab3  mov     [rbp+57h+var_8C], edi
0x180081ab6  mov     r12d, edi
0x180081ab9  mov     [rbp+57h+var_88], edi
0x180081abc  mov     r15d, edi
0x180081abf  mov     [rbp+57h+hWnd], rdi
0x180081ac3  mov     [rbp+57h+var_60], rdi
0x180081ac7  mov     [rbp+57h+var_68], rdi
0x180081acb  mov     [rbp+57h+ReturnLength], edi
0x180081ace  mov     [rbp+57h+dwProcessId], edi
0x180081ad1  call    cs:__imp_GetCurrentProcessId
0x180081ad7  lea     rdx, [rbp+57h+var_7C]; int *
0x180081adb  mov     [rbp+57h+var_78], rdi
0x180081adf  mov     rcx, rsi; this
0x180081ae2  mov     [rbp+57h+arg_18], eax
0x180081ae5  mov     r13d, edi
0x180081ae8  mov     [rbp+57h+TargetHandle], rdi
0x180081aec  mov     [rbp+57h+arg_8], edi
0x180081aef  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180081af4  lea     rcx, [rsi+24C8h]; this
0x180081afb  lea     rdx, [rbp+57h+var_8C]; int *
0x180081aff  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180081b04  mov     rdi, [rsi+2480h]
0x180081b0b  movzx   r14d, word ptr [rsi+2704h]
0x180081b13  test    rdi, rdi
0x180081b16  jz      short loc_180081B5B
0x180081b18  mov     rbx, [rsi+2488h]
0x180081b1f  mov     [rbp+57h+hWnd], rdi
0x180081b23  test    r12, r12
0x180081b26  jz      short loc_180081B34
0x180081b28  mov     rcx, r12; bstrString
0x180081b2b  call    cs:__imp_SysFreeString
0x180081b31  xor     r12d, r12d
0x180081b34  mov     rcx, rbx; psz
0x180081b37  call    cs:__imp_SysAllocString
0x180081b3d  test    rbx, rbx
0x180081b40  jz      short loc_180081B4B
0x180081b42  test    rax, rax
0x180081b45  jz      loc_180081E1C
0x180081b4b  mov     r12, rax
0x180081b4e  mov     rax, [rsi+2458h]
0x180081b55  xor     ebx, ebx
0x180081b57  mov     [rbp+57h+var_60], rax
0x180081b5b  lea     rdx, [rbp+57h+var_8C]; int *
0x180081b5f  mov     qword ptr [rsi+2480h], 0
0x180081b6a  lea     rcx, [rsi+24C8h]; this
0x180081b71  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180081b76  test    rdi, rdi
0x180081b79  jz      loc_180081E89
0x180081b7f  mov     rax, [rsi]
0x180081b82  mov     edx, 1
0x180081b87  mov     rcx, rsi
0x180081b8a  mov     rax, [rax+30h]
0x180081b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b93  mov     rdi, [rbp+57h+var_60]
0x180081b97  test    r12, r12
0x180081b9a  jnz     short loc_180081BA5
0x180081b9c  test    rdi, rdi
0x180081b9f  jz      loc_180081AF4
0x180081ba5  mov     r8d, [rbp+57h+ReturnLength]; SystemInformationLength
0x180081ba9  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180081bad  mov     rdx, r15; SystemInformation
0x180081bb0  mov     ecx, 40h ; '@'; SystemInformationClass
0x180081bb5  call    cs:__imp_NtQuerySystemInformation
0x180081bbb  test    eax, eax
0x180081bbd  jns     short loc_180081BF1
0x180081bbf  cmp     eax, 0C0000004h
0x180081bc4  jnz     loc_180081E6A
0x180081bca  test    r15, r15
0x180081bcd  jz      short loc_180081BD7
0x180081bcf  mov     rcx, r15; void *
0x180081bd2  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x180081bd7  mov     ecx, [rbp+57h+ReturnLength]; dwBytes
0x180081bda  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x180081bdf  mov     r15, rax
0x180081be2  test    rax, rax
0x180081be5  jnz     short loc_180081BA5
0x180081be7  mov     edi, 8007000Eh
0x180081bec  jmp     loc_180081E42
0x180081bf1  test    r12, r12
0x180081bf4  jz      short loc_180081BFF
0x180081bf6  mov     rcx, r12; lpsz
0x180081bf9  call    cs:__imp_CharLowerW
0x180081bff  test    rdi, rdi
0x180081c02  jz      short loc_180081C2F
0x180081c04  lea     rdx, [rbp+57h+var_88]; int *
0x180081c08  mov     rcx, rdi; this
0x180081c0b  call    ?LockEnter@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockEnter(int *)
0x180081c10  mov     rcx, rdi; this
0x180081c13  call    ?DuplicateFilter@WdcFilter@@QEAAPEAV1@XZ; WdcFilter::DuplicateFilter(void)
0x180081c18  lea     rdx, [rbp+57h+var_88]; int *
0x180081c1c  mov     [rbp+57h+var_68], rax
0x180081c20  mov     rcx, rdi; this
0x180081c23  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180081c28  cmp     [rbp+57h+var_68], 0
0x180081c2d  jz      short loc_180081BE7
0x180081c2f  lea     rax, [r13-1]
0x180081c33  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081c37  ja      short loc_180081C45
0x180081c39  mov     rcx, r13; hObject
0x180081c3c  call    cs:__imp_CloseHandle
0x180081c42  xor     r13d, r13d
0x180081c45  or      ecx, 0FFFFFFFFh
0x180081c48  mov     [rbp+57h+var_80], ecx
0x180081c4b  mov     r11d, ecx
0x180081c4e  mov     [rbp+57h+arg_0], ecx
0x180081c51  xor     ecx, ecx
0x180081c53  mov     [rbp+57h+var_90], ecx
0x180081c56  cmp     [r15], rcx
0x180081c59  jbe     loc_180081DF3
0x180081c5f  lea     r14, [rcx+rcx*4]
0x180081c63  mov     rcx, [r15+r14*8+18h]; unsigned __int64
0x180081c68  lea     rdx, [rbp+57h+dwProcessId]; unsigned int *
0x180081c6c  mov     [rbp+57h+var_48], r14
0x180081c70  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180081c75  mov     ebx, eax
0x180081c77  test    eax, eax
0x180081c79  jns     short loc_180081C82
0x180081c7b  xor     ebx, ebx
0x180081c7d  jmp     loc_180081DE0
0x180081c82  mov     edi, [rbp+57h+dwProcessId]
0x180081c85  cmp     r11d, edi
0x180081c88  jz      loc_180081DE0
0x180081c8e  cmp     [rbp+57h+var_80], edi
0x180081c91  jnz     short loc_180081C9F
0x180081c93  mov     eax, [rbp+57h+arg_18]
0x180081c96  mov     rbx, r13
0x180081c99  mov     [rbp+57h+var_78], rbx
0x180081c9d  jmp     short loc_180081D0C
0x180081c9f  mov     rax, [rbp+57h+var_68]
0x180081ca3  mov     [rbp+57h+var_50], rdi
0x180081ca7  test    rax, rax
0x180081caa  jz      short loc_180081CC7
0x180081cac  lea     rdx, [rbp+57h+var_50]; struct _PROCESS_KEY *
0x180081cb0  mov     rcx, rax; this
0x180081cb3  call    ?Match@WdcFilter@@QEAAHPEAU_PROCESS_KEY@@@Z; WdcFilter::Match(_PROCESS_KEY *)
0x180081cb8  test    eax, eax
0x180081cba  jnz     short loc_180081CC7
0x180081cbc  mov     r11d, edi
0x180081cbf  mov     [rbp+57h+arg_0], edi
0x180081cc2  jmp     loc_180081DE0
0x180081cc7  mov     eax, [rbp+57h+arg_18]
0x180081cca  cmp     eax, edi
0x180081ccc  jz      short loc_180081D08
0x180081cce  xor     edx, edx; bInheritHandle
0x180081cd0  mov     r8d, edi; dwProcessId
0x180081cd3  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180081cd6  call    cs:__imp_OpenProcess
0x180081cdc  mov     [rbp+57h+var_78], rax
0x180081ce0  mov     rdx, rax
0x180081ce3  test    rax, rax
0x180081ce6  jz      short loc_180081CBC
0x180081ce8  lea     rcx, [r13-1]
0x180081cec  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180081cf0  ja      short loc_180081CFF
0x180081cf2  mov     rcx, r13; hObject
0x180081cf5  call    cs:__imp_CloseHandle
0x180081cfb  mov     rdx, [rbp+57h+var_78]
0x180081cff  mov     eax, [rbp+57h+arg_18]
0x180081d02  mov     r13, rdx
0x180081d05  mov     [rbp+57h+var_80], edi
0x180081d08  mov     rbx, [rbp+57h+var_78]
0x180081d0c  mov     r14, [r15+r14*8+20h]
0x180081d11  cmp     eax, edi
0x180081d13  jnz     short loc_180081D2C
0x180081d15  call    cs:__imp_GetCurrentProcess
0x180081d1b  mov     rbx, rax
0x180081d1e  call    cs:__imp_GetCurrentProcess
0x180081d24  mov     rcx, rax
0x180081d27  mov     r8, rbx
0x180081d2a  jmp     short loc_180081D38
0x180081d2c  call    cs:__imp_GetCurrentProcess
0x180081d32  mov     r8, rax; hTargetProcessHandle
0x180081d35  mov     rcx, rbx; hSourceProcessHandle
0x180081d38  mov     [rsp+0D0h+dwOptions], 2; dwOptions
0x180081d40  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180081d44  mov     [rsp+0D0h+bInheritHandle], 0; bInheritHandle
0x180081d4c  mov     rdx, r14; hSourceHandle
0x180081d4f  mov     [rsp+0D0h+dwDesiredAccess], 0; dwDesiredAccess
0x180081d57  call    cs:__imp_DuplicateHandle
0x180081d5d  test    eax, eax
0x180081d5f  jnz     short loc_180081D84
0x180081d61  call    cs:__imp_GetLastError
0x180081d67  test    eax, eax
0x180081d69  jz      short loc_180081D77
0x180081d6b  jle     short loc_180081D7E
0x180081d6d  movzx   eax, ax
0x180081d70  or      eax, 80070000h
0x180081d75  jmp     short loc_180081D7C
0x180081d77  mov     eax, 80004005h
0x180081d7c  test    eax, eax
0x180081d7e  jns     short loc_180081D84
0x180081d80  xor     ebx, ebx
0x180081d82  jmp     short loc_180081DDC
0x180081d84  mov     rax, [rbp+57h+var_48]
0x180081d88  mov     edx, edi; unsigned int
0x180081d8a  mov     r8, [rbp+57h+TargetHandle]; void *
0x180081d8e  mov     rcx, rsi; this
0x180081d91  mov     qword ptr [rsp+0D0h+dwDesiredAccess], r12; unsigned __int16 *
0x180081d96  movzx   r9d, word ptr [r15+rax*8+2Eh]; unsigned int
0x180081d9c  call    ?AddHandle@WdcHandleMonitor@@AEAAJKPEAXKPEBG@Z; WdcHandleMonitor::AddHandle(ulong,void *,ulong,ushort const *)
0x180081da1  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180081da5  lea     rax, [rcx-1]
0x180081da9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180081dad  ja      short loc_180081DBD
0x180081daf  call    cs:__imp_CloseHandle
0x180081db5  mov     [rbp+57h+TargetHandle], 0
0x180081dbd  mov     rcx, [rsi+23C8h]; hHandle
0x180081dc4  xor     ebx, ebx
0x180081dc6  test    rcx, rcx
0x180081dc9  jz      short loc_180081DDC
0x180081dcb  cmp     byte ptr [rbp+57h+var_90], bl
0x180081dce  jnz     short loc_180081DDC
0x180081dd0  xor     edx, edx; dwMilliseconds
0x180081dd2  call    cs:__imp_WaitForSingleObject
0x180081dd8  test    eax, eax
0x180081dda  jz      short loc_180081DF3
0x180081ddc  mov     r11d, [rbp+57h+arg_0]
0x180081de0  mov     ecx, [rbp+57h+var_90]
0x180081de3  inc     ecx
0x180081de5  mov     eax, ecx
0x180081de7  mov     [rbp+57h+var_90], ecx
0x180081dea  cmp     rax, [r15]
0x180081ded  jb      loc_180081C5F
0x180081df3  mov     rax, [rbp+57h+var_68]
0x180081df7  lea     rcx, [rsi+24C8h]
0x180081dfe  test    rax, rax
0x180081e01  jz      loc_180081AFB
0x180081e07  mov     rcx, rax; this
0x180081e0a  call    ?Release@WdcDataPortal@@QEAAXXZ; WdcDataPortal::Release(void)
0x180081e0f  mov     [rbp+57h+var_68], 0
0x180081e17  jmp     loc_180081AF4
0x180081e1c  mov     edi, 8007000Eh
0x180081e21  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180081e28  xor     r8d, r8d; int
0x180081e2b  mov     [rsp+0D0h+dwDesiredAccess], edi
0x180081e2f  lea     rdx, aWdcassignstrin; "WdcAssignString"
0x180081e36  lea     rcx, aBaseDiagnosisP_52; "base\\diagnosis\\pdui\\perfmon\\mmc\\in"...
0x180081e3d  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180081e42  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x180081e49  mov     [rsp+0D0h+dwDesiredAccess], edi
0x180081e4d  xor     r8d, r8d; int
0x180081e50  lea     rdx, aWdchandlemonit_3; "WdcHandleMonitor::Update"
0x180081e57  lea     rcx, aBaseDiagnosisP_33; "base\\diagnosis\\pdui\\perfmon\\mon\\ha"...
0x180081e5e  mov     ebx, edi
0x180081e60  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x180081e65  mov     edi, [rbp+57h+arg_8]
0x180081e68  jmp     short loc_180081EA1
0x180081e6a  mov     ecx, eax; Status
0x180081e6c  call    cs:__imp_RtlNtStatusToDosError
0x180081e72  xor     ebx, ebx
0x180081e74  test    eax, eax
0x180081e76  jz      short loc_180081E65
0x180081e78  jg      short loc_180081E7E
0x180081e7a  mov     ebx, eax
0x180081e7c  jmp     short loc_180081E65
0x180081e7e  movzx   ebx, ax
0x180081e81  or      ebx, 80070000h
0x180081e87  jmp     short loc_180081E65
0x180081e89  xor     edx, edx
0x180081e8b  test    r12, r12
0x180081e8e  setnz   dl
0x180081e91  movzx   edi, dx
0x180081e94  or      di, 2
0x180081e98  cmp     [rbp+57h+var_60], 0
0x180081e9d  cmovz   di, dx
0x180081ea1  lea     rdx, [rbp+57h+var_8C]; int *
0x180081ea5  lea     rcx, [rsi+24C8h]; this
0x180081eac  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180081eb1  lea     rdx, [rbp+57h+var_7C]; int *
0x180081eb5  mov     rcx, rsi; this
0x180081eb8  call    ?LockLeave@WdcLockObject@@QEAAXPEAH@Z; WdcLockObject::LockLeave(int *)
0x180081ebd  mov     rcx, [rbp+57h+hWnd]; hWnd
0x180081ec1  test    rcx, rcx
0x180081ec4  jz      short loc_180081EE4
0x180081ec6  mov     r8d, r14d
0x180081ec9  movzx   eax, di
0x180081ecc  shl     r8d, 10h
0x180081ed0  xor     r9d, r9d; lParam
0x180081ed3  or      r8d, eax
0x180081ed6  mov     edx, 401h; Msg
0x180081edb  movsxd  r8, r8d; wParam
0x180081ede  call    cs:__imp_PostMessageW
0x180081ee4  cmp     qword ptr [rsi+2490h], 0
0x180081eec  jz      short loc_180081F2D
0x180081eee  mov     rcx, [rsi+24A0h]; hEvent
0x180081ef5  call    cs:__imp_SetEvent
  ... truncated ...
```

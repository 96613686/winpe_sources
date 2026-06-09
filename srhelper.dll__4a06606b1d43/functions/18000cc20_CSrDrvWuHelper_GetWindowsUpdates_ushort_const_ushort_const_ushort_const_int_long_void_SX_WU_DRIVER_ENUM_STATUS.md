# CSrDrvWuHelper::_GetWindowsUpdates(ushort const *,ushort const *,ushort const *,int,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)

- ea: `0x18000cc20`
- end: `0x18000ce92`
- name: `?_GetWindowsUpdates@CSrDrvWuHelper@@CAJPEBG00HP6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z`
- size: `626`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _TOKEN_PRIVILEGES *, int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *), int, int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *), void *)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update`

## callers

- `0x18000a790`
- `0x18000af70`

## callees

- `0x180003ce0`
- `0x18000408c`
- `0x1800044ac`
- `0x18000a70c`
- `0x18000cc20`
- `0x18000cf14`
- `0x18000d348`
- `0x18000d43c`
- `0x18000ea60`
- `0x18000ef70`
- `0x180014f38`
- `0x180014fc4`
- `0x180015760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ce4c`
- `KERNEL32!CloseHandle` at `0x18000ce4c`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000ce12`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000ce12`
- `ole32!CoTaskMemFree` at `0x18000ce1c`
- `ole32!CoTaskMemFree` at `0x18000ce1c`

## string_xrefs

- `0x18000cc82`: `CSrDrvWuHelper::_GetWindowsUpdates`
- `0x18000cd78`: `%temp%`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetWindowsUpdates(
        const unsigned __int16 *a1,
        struct _TOKEN_PRIVILEGES *a2,
        int (__high *a3)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *),
        int a4,
        int (__high *a5)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *),
        void *a6)
{
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // ecx
  void *v12; // r12
  int v13; // eax
  char *v14; // rbx
  int WindowsUpdates; // edi
  __int16 v16; // ax
  const unsigned __int16 *v17; // r8
  bool v18; // sf
  __int64 v19; // rdx
  __int64 v20; // r8
  int (__high *ReturnLength)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *); // [rsp+30h] [rbp-81h]
  int v23; // [rsp+58h] [rbp-59h] BYREF
  __int16 v24; // [rsp+5Ch] [rbp-55h]
  __int16 v25; // [rsp+5Eh] [rbp-53h]
  unsigned __int16 *v26[2]; // [rsp+90h] [rbp-21h] BYREF
  _OWORD v27[2]; // [rsp+A0h] [rbp-11h] BYREF
  int v28; // [rsp+C0h] [rbp+Fh]
  __int64 v29; // [rsp+C8h] [rbp+17h]
  __int64 v30; // [rsp+D0h] [rbp+1Fh]
  HANDLE TokenHandle; // [rsp+108h] [rbp+57h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+110h] [rbp+5Fh] BYREF

  NewState = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v23, "CSrDrvWuHelper::_GetWindowsUpdates", 791);
  NewState = 0;
  v26[0] = (unsigned __int16 *)qword_18001A620;
  TokenHandle = 0;
  v24 = 798;
  v26[1] = 0;
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v23 = 0;
  v11 = (unsigned int)WPP_GLOBAL_Control;
  v12 = a6;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
  {
    ReturnLength = a3;
    WPP_SF_SSSLqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v10, (_DWORD)a1);
  }
  v13 = SxOpenThreadOrProcessToken(v11, &TokenHandle);
  v14 = (char *)TokenHandle;
  WindowsUpdates = v13;
  v23 = v13;
  v18 = v13 < 0;
  v16 = 810;
  if ( v18 )
    goto LABEL_8;
  v24 = 810;
  WindowsUpdates = SxEnableBackupRestorePrivs(TokenHandle, &NewState);
  v23 = WindowsUpdates;
  v16 = 811;
  if ( WindowsUpdates < 0 )
    goto LABEL_8;
  v24 = 811;
  if ( a4 )
  {
    if ( a3 )
    {
      WindowsUpdates = CBsString::Append((CBsString *)v26, (const unsigned __int16 *)a3);
      v23 = WindowsUpdates;
      v18 = WindowsUpdates < 0;
      v16 = 822;
    }
    else
    {
      WindowsUpdates = CBsString::ExpandEnvironmentStringsW((CBsString *)v26, L"%temp%");
      v23 = WindowsUpdates;
      v18 = WindowsUpdates < 0;
      v16 = 818;
    }
    if ( v18 )
      goto LABEL_8;
    v24 = v16;
  }
  WindowsUpdates = CSxWindowsUpdateEnumerator::Initialize(
                     (CSxWindowsUpdateEnumerator *)v27,
                     a1,
                     v17,
                     v26[0],
                     a4,
                     ReturnLength,
                     v12);
  v23 = WindowsUpdates;
  v16 = 827;
  if ( WindowsUpdates >= 0 )
  {
    v24 = 827;
    WindowsUpdates = CSxWindowsUpdateEnumerator::GetWindowsUpdates((CSxWindowsUpdateEnumerator *)v27);
    v23 = WindowsUpdates;
    v16 = 829;
    if ( WindowsUpdates >= 0 )
    {
      v24 = 829;
      goto LABEL_18;
    }
  }
LABEL_8:
  v25 = v16;
LABEL_18:
  if ( NewState && (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v14, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    WindowsUpdates = v23;
    NewState = 0;
  }
  CSxWindowsUpdateEnumerator::~CSxWindowsUpdateEnumerator((LPVOID *)v27);
  CBsString::_Release((CBsString *)v26);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23, v19, v20);
  return (unsigned int)WindowsUpdates;
}

```

## disassembly

```asm
0x18000cc20  mov     rax, rsp
0x18000cc23  mov     [rax+18h], rbx
0x18000cc27  mov     [rax+20h], rsi
0x18000cc2b  mov     [rax+10h], rdx
0x18000cc2f  push    rbp
0x18000cc30  push    rdi
0x18000cc31  push    r12
0x18000cc33  push    r14
0x18000cc35  push    r15
0x18000cc37  lea     rbp, [rax-4Fh]
0x18000cc3b  sub     rsp, 0D0h
0x18000cc42  mov     r14d, r9d
0x18000cc45  mov     rsi, r8
0x18000cc48  mov     r15, rcx
0x18000cc4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc52  lea     rbx, WPP_GLOBAL_Control
0x18000cc59  cmp     rcx, rbx
0x18000cc5c  jz      short loc_18000CC7C
0x18000cc5e  test    dword ptr [rcx+1Ch], 20000000h
0x18000cc65  jz      short loc_18000CC7C
0x18000cc67  mov     rcx, [rcx+10h]
0x18000cc6b  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000cc72  mov     edx, 22h ; '"'
0x18000cc77  call    WPP_SF_
0x18000cc7c  mov     r8d, 317h; unsigned __int16
0x18000cc82  lea     rdx, aCsrdrvwuhelper_11; "CSrDrvWuHelper::_GetWindowsUpdates"
0x18000cc89  lea     rcx, [rbp+47h+var_A0]; this
0x18000cc8d  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000cc92  lea     rax, qword_18001A620
0x18000cc99  mov     [rbp+47h+NewState], 0
0x18000cca1  mov     [rbp+47h+var_68], rax
0x18000cca5  xorps   xmm0, xmm0
0x18000cca8  mov     eax, 31Eh
0x18000ccad  mov     [rbp+47h+TokenHandle], 0
0x18000ccb5  xorps   xmm1, xmm1
0x18000ccb8  mov     [rbp+47h+var_9C], ax
0x18000ccbc  mov     [rbp+47h+var_60], 0
0x18000ccc4  movdqu  [rbp+47h+var_58], xmm0
0x18000ccc9  mov     [rbp+47h+var_38], 0
0x18000ccd0  movdqu  [rbp+47h+var_48], xmm1
0x18000ccd5  mov     [rbp+47h+var_30], 0
0x18000ccdd  mov     [rbp+47h+var_28], 0
0x18000cce5  mov     [rbp+47h+var_A0], 0
0x18000ccec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ccf3  mov     r12, [rbp+47h+arg_28]
0x18000ccf7  cmp     rcx, rbx
0x18000ccfa  jz      short loc_18000CD20
0x18000ccfc  test    dword ptr [rcx+1Ch], 8000000h
0x18000cd03  jz      short loc_18000CD20
0x18000cd05  mov     rcx, [rcx+10h]
0x18000cd09  mov     r9, r15
0x18000cd0c  mov     [rsp+0F0h+var_B0], r12
0x18000cd11  mov     dword ptr [rsp+0F0h+var_C0], r14d
0x18000cd16  mov     [rsp+0F0h+ReturnLength], rsi; int (__high *)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *)
0x18000cd1b  call    WPP_SF_SSSLqq
0x18000cd20  lea     rdx, [rbp+47h+TokenHandle]; void **
0x18000cd24  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18000cd29  mov     rbx, [rbp+47h+TokenHandle]
0x18000cd2d  mov     edi, eax
0x18000cd2f  mov     [rbp+47h+var_A0], eax
0x18000cd32  test    eax, eax
0x18000cd34  mov     eax, 32Ah
0x18000cd39  jns     short loc_18000CD44
0x18000cd3b  mov     [rbp+47h+var_9A], ax
0x18000cd3f  jmp     loc_18000CDE5
0x18000cd44  lea     rdx, [rbp+47h+NewState]; struct _TOKEN_PRIVILEGES **
0x18000cd48  mov     [rbp+47h+var_9C], ax
0x18000cd4c  mov     rcx, rbx; TokenHandle
0x18000cd4f  call    ?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18000cd54  mov     edi, eax
0x18000cd56  mov     [rbp+47h+var_A0], eax
0x18000cd59  test    eax, eax
0x18000cd5b  mov     eax, 32Bh
0x18000cd60  js      short loc_18000CD3B
0x18000cd62  mov     [rbp+47h+var_9C], ax
0x18000cd66  test    r14d, r14d
0x18000cd69  jz      short loc_18000CD96
0x18000cd6b  lea     rcx, [rbp+47h+var_68]; this
0x18000cd6f  test    rsi, rsi
0x18000cd72  jnz     loc_18000CE79
0x18000cd78  lea     rdx, aTemp; "%temp%"
0x18000cd7f  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18000cd84  mov     edi, eax
0x18000cd86  mov     [rbp+47h+var_A0], eax
0x18000cd89  test    eax, eax
0x18000cd8b  mov     eax, 332h
0x18000cd90  js      short loc_18000CD3B
0x18000cd92  mov     [rbp+47h+var_9C], ax
0x18000cd96  mov     r9, [rbp+47h+var_68]; unsigned __int16 *
0x18000cd9a  lea     rcx, [rbp+47h+var_58]; this
0x18000cd9e  mov     [rsp+0F0h+var_C0], r12; void *
0x18000cda3  mov     rdx, r15; unsigned __int16 *
0x18000cda6  mov     dword ptr [rsp+0F0h+PreviousState], r14d; int
0x18000cdab  call    ?Initialize@CSxWindowsUpdateEnumerator@@QEAAJPEBG00HP6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z; CSxWindowsUpdateEnumerator::Initialize(ushort const *,ushort const *,ushort const *,int,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)
0x18000cdb0  mov     edi, eax
0x18000cdb2  mov     [rbp+47h+var_A0], eax
0x18000cdb5  test    eax, eax
0x18000cdb7  mov     eax, 33Bh
0x18000cdbc  js      loc_18000CD3B
0x18000cdc2  lea     rcx, [rbp+47h+var_58]; this
0x18000cdc6  mov     [rbp+47h+var_9C], ax
0x18000cdca  call    ?GetWindowsUpdates@CSxWindowsUpdateEnumerator@@QEAAJXZ; CSxWindowsUpdateEnumerator::GetWindowsUpdates(void)
0x18000cdcf  mov     edi, eax
0x18000cdd1  mov     [rbp+47h+var_A0], eax
0x18000cdd4  test    eax, eax
0x18000cdd6  mov     eax, 33Dh
0x18000cddb  js      loc_18000CD3B
0x18000cde1  mov     [rbp+47h+var_9C], ax
0x18000cde5  mov     r8, [rbp+47h+NewState]; NewState
0x18000cde9  test    r8, r8
0x18000cdec  jz      short loc_18000CE2D
0x18000cdee  lea     rax, [rbx-1]
0x18000cdf2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cdf6  ja      short loc_18000CE2D
0x18000cdf8  mov     [rsp+0F0h+ReturnLength], 0; ReturnLength
0x18000ce01  xor     r9d, r9d; BufferLength
0x18000ce04  xor     edx, edx; DisableAllPrivileges
0x18000ce06  mov     [rsp+0F0h+PreviousState], 0; PreviousState
0x18000ce0f  mov     rcx, rbx; TokenHandle
0x18000ce12  call    cs:__imp_AdjustTokenPrivileges
0x18000ce18  mov     rcx, [rbp+47h+NewState]; pv
0x18000ce1c  call    cs:__imp_CoTaskMemFree
0x18000ce22  mov     edi, [rbp+47h+var_A0]
0x18000ce25  mov     [rbp+47h+NewState], 0
0x18000ce2d  lea     rcx, [rbp+47h+var_58]; this
0x18000ce31  call    ??1CSxWindowsUpdateEnumerator@@QEAA@XZ; CSxWindowsUpdateEnumerator::~CSxWindowsUpdateEnumerator(void)
0x18000ce36  lea     rcx, [rbp+47h+var_68]; this
0x18000ce3a  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x18000ce3f  lea     rcx, [rbx-1]
0x18000ce43  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000ce47  ja      short loc_18000CE52
0x18000ce49  mov     rcx, rbx; hObject
0x18000ce4c  call    cs:__imp_CloseHandle
0x18000ce52  lea     rcx, [rbp+47h+var_A0]; this
0x18000ce56  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000ce5b  lea     r11, [rsp+0F0h+var_20]
0x18000ce63  mov     eax, edi
0x18000ce65  mov     rbx, [r11+40h]
0x18000ce69  mov     rsi, [r11+48h]
0x18000ce6d  mov     rsp, r11
0x18000ce70  pop     r15
0x18000ce72  pop     r14
0x18000ce74  pop     r12
0x18000ce76  pop     rdi
0x18000ce77  pop     rbp
0x18000ce78  retn
0x18000ce79  mov     rdx, rsi; unsigned __int16 *
0x18000ce7c  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x18000ce81  mov     edi, eax
0x18000ce83  mov     [rbp+47h+var_A0], eax
0x18000ce86  test    eax, eax
0x18000ce88  mov     eax, 336h
0x18000ce8d  jmp     loc_18000CD90
```

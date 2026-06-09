# CSrDrvWuHelper::_GetDrivers(ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)

- ea: `0x18000c6e0`
- end: `0x18000c887`
- name: `?_GetDrivers@CSrDrvWuHelper@@CAJPEBG0P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z`
- size: `423`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, struct _TOKEN_PRIVILEGES *, void *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000a790`
- `0x18000ab80`

## callees

- `0x180003ce0`
- `0x180004c2c`
- `0x18000c6e0`
- `0x18000d030`
- `0x18000d348`
- `0x18000d43c`
- `0x18000ea60`
- `0x18000ef70`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000c85e`
- `KERNEL32!CloseHandle` at `0x18000c85e`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000c836`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000c836`
- `ole32!CoTaskMemFree` at `0x18000c840`
- `ole32!CoTaskMemFree` at `0x18000c840`

## pseudocode

```c
__int64 __fastcall CSrDrvWuHelper::_GetDrivers(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        struct _TOKEN_PRIVILEGES *a3,
        void *a4)
{
  int v6; // edx
  int v7; // r8d
  char *v8; // rbx
  unsigned int v9; // ecx
  int Drivers; // edi
  __int16 v11; // ax
  int v12; // eax
  bool v13; // sf
  const unsigned __int16 *v14; // rdx
  int (__high *v15)(void *, enum _SX_WU_DRIVER_ENUM_STATUS, unsigned __int16 *); // r8
  int v17; // [rsp+40h] [rbp-40h] BYREF
  __int16 v18; // [rsp+44h] [rbp-3Ch]
  __int16 v19; // [rsp+46h] [rbp-3Ah]
  HANDLE TokenHandle; // [rsp+A8h] [rbp+28h] BYREF
  PTOKEN_PRIVILEGES NewState; // [rsp+B0h] [rbp+30h] BYREF

  NewState = a3;
  TokenHandle = a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v17,
    "CSrDrvWuHelper::_GetDrivers",
    0x26Du,
    (unsigned __int16)a4);
  v8 = 0;
  NewState = 0;
  TokenHandle = 0;
  v9 = (unsigned int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    WPP_SF_SSqq(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, (_DWORD)a1);
  v18 = 630;
  if ( a4 )
  {
    v17 = 0;
    v18 = 632;
    v12 = SxOpenThreadOrProcessToken(v9, &TokenHandle);
    v8 = (char *)TokenHandle;
    Drivers = v12;
    v17 = v12;
    v13 = v12 < 0;
    v11 = 634;
    if ( !v13 )
    {
      v18 = 634;
      Drivers = SxEnableBackupRestorePrivs(TokenHandle, &NewState);
      v17 = Drivers;
      v11 = 635;
      if ( Drivers >= 0 )
      {
        v18 = 635;
        Drivers = SxGetDrivers(a1, v14, v15, a4);
        v17 = Drivers;
        v11 = 636;
        if ( Drivers >= 0 )
        {
          v18 = 636;
          goto LABEL_14;
        }
      }
    }
  }
  else
  {
    Drivers = -2147024809;
    v11 = 631;
    v17 = -2147024809;
  }
  v19 = v11;
LABEL_14:
  if ( NewState && (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v8, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    Drivers = v17;
    NewState = 0;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)Drivers;
}

```

## disassembly

```asm
0x18000c6e0  mov     rax, rsp
0x18000c6e3  mov     [rax+8], rbx
0x18000c6e7  mov     [rax+20h], rsi
0x18000c6eb  mov     [rax+18h], r8
0x18000c6ef  mov     [rax+10h], rdx
0x18000c6f3  push    rbp
0x18000c6f4  push    rdi
0x18000c6f5  push    r14
0x18000c6f7  mov     rbp, rsp
0x18000c6fa  sub     rsp, 80h
0x18000c701  mov     rsi, r9
0x18000c704  mov     r14, rcx
0x18000c707  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c70e  lea     rdi, WPP_GLOBAL_Control
0x18000c715  cmp     rcx, rdi
0x18000c718  jz      short loc_18000C738
0x18000c71a  test    dword ptr [rcx+1Ch], 20000000h
0x18000c721  jz      short loc_18000C738
0x18000c723  mov     rcx, [rcx+10h]
0x18000c727  lea     r8, WPP_9d0845b03c1a3f4b05c462c5fbaec349_Traceguids
0x18000c72e  mov     edx, 1Bh
0x18000c733  call    WPP_SF_
0x18000c738  mov     r8d, 26Dh; unsigned __int16
0x18000c73e  lea     rdx, aCsrdrvwuhelper_3; "CSrDrvWuHelper::_GetDrivers"
0x18000c745  lea     rcx, [rbp+var_40]; this
0x18000c749  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000c74e  xor     ebx, ebx
0x18000c750  mov     [rbp+NewState], 0
0x18000c758  mov     [rbp+TokenHandle], rbx
0x18000c75c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c763  cmp     rcx, rdi
0x18000c766  jz      short loc_18000C782
0x18000c768  test    dword ptr [rcx+1Ch], 8000000h
0x18000c76f  jz      short loc_18000C782
0x18000c771  mov     rcx, [rcx+10h]
0x18000c775  mov     r9, r14
0x18000c778  mov     [rsp+80h+var_50], rsi
0x18000c77d  call    WPP_SF_SSqq
0x18000c782  mov     eax, 276h
0x18000c787  mov     [rbp+var_3C], ax
0x18000c78b  test    rsi, rsi
0x18000c78e  jnz     short loc_18000C7A3
0x18000c790  mov     edi, 80070057h
0x18000c795  mov     eax, 277h
0x18000c79a  mov     [rbp+var_40], edi
0x18000c79d  mov     [rbp+var_3A], ax
0x18000c7a1  jmp     short loc_18000C809
0x18000c7a3  mov     eax, 278h
0x18000c7a8  mov     [rbp+var_40], ebx
0x18000c7ab  lea     rdx, [rbp+TokenHandle]; void **
0x18000c7af  mov     [rbp+var_3C], ax
0x18000c7b3  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18000c7b8  mov     rbx, [rbp+TokenHandle]
0x18000c7bc  mov     edi, eax
0x18000c7be  mov     [rbp+var_40], eax
0x18000c7c1  test    eax, eax
0x18000c7c3  mov     eax, 27Ah
0x18000c7c8  js      short loc_18000C79D
0x18000c7ca  lea     rdx, [rbp+NewState]; struct _TOKEN_PRIVILEGES **
0x18000c7ce  mov     [rbp+var_3C], ax
0x18000c7d2  mov     rcx, rbx; TokenHandle
0x18000c7d5  call    ?SxEnableBackupRestorePrivs@@YAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; SxEnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18000c7da  mov     edi, eax
0x18000c7dc  mov     [rbp+var_40], eax
0x18000c7df  test    eax, eax
0x18000c7e1  mov     eax, 27Bh
0x18000c7e6  js      short loc_18000C79D
0x18000c7e8  mov     r9, rsi; void *
0x18000c7eb  mov     [rbp+var_3C], ax
0x18000c7ef  mov     rcx, r14; unsigned __int16 *
0x18000c7f2  call    ?SxGetDrivers@@YAJPEBG0P6AJPEAXW4_SX_WU_DRIVER_ENUM_STATUS@@PEAG@Z1@Z; SxGetDrivers(ushort const *,ushort const *,long (*)(void *,_SX_WU_DRIVER_ENUM_STATUS,ushort *),void *)
0x18000c7f7  mov     edi, eax
0x18000c7f9  mov     [rbp+var_40], eax
0x18000c7fc  test    eax, eax
0x18000c7fe  mov     eax, 27Ch
0x18000c803  js      short loc_18000C79D
0x18000c805  mov     [rbp+var_3C], ax
0x18000c809  mov     r8, [rbp+NewState]; NewState
0x18000c80d  test    r8, r8
0x18000c810  jz      short loc_18000C851
0x18000c812  lea     rax, [rbx-1]
0x18000c816  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000c81a  ja      short loc_18000C851
0x18000c81c  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x18000c825  xor     r9d, r9d; BufferLength
0x18000c828  xor     edx, edx; DisableAllPrivileges
0x18000c82a  mov     [rsp+80h+PreviousState], 0; PreviousState
0x18000c833  mov     rcx, rbx; TokenHandle
0x18000c836  call    cs:__imp_AdjustTokenPrivileges
0x18000c83c  mov     rcx, [rbp+NewState]; pv
0x18000c840  call    cs:__imp_CoTaskMemFree
0x18000c846  mov     edi, [rbp+var_40]
0x18000c849  mov     [rbp+NewState], 0
0x18000c851  lea     rcx, [rbx-1]
0x18000c855  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c859  ja      short loc_18000C864
0x18000c85b  mov     rcx, rbx; hObject
0x18000c85e  call    cs:__imp_CloseHandle
0x18000c864  lea     rcx, [rbp+var_40]; this
0x18000c868  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000c86d  lea     r11, [rsp+80h+var_s0]
0x18000c875  mov     eax, edi
0x18000c877  mov     rbx, [r11+20h]
0x18000c87b  mov     rsi, [r11+38h]
0x18000c87f  mov     rsp, r11
0x18000c882  pop     r14
0x18000c884  pop     rdi
0x18000c885  pop     rbp
0x18000c886  retn
```

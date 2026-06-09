# CSpp::GetInstallationVolumes(ulong *,ushort * * *)

- ea: `0x18000a280`
- end: `0x18000a423`
- name: `?GetInstallationVolumes@CSpp@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `419`
- prototype: `__int64 __fastcall(CSpp *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000a280`
- `0x180016d80`
- `0x180019bb4`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d408`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000a3fe`
- `KERNEL32!CloseHandle` at `0x18000a3fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a3e0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000a3d6`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000a3d6`

## string_xrefs

- `0x18000a2d3`: `CSpp::GetInstallationVolumes`

## pseudocode

```c
__int64 __fastcall CSpp::GetInstallationVolumes(CSpp *this, unsigned int *a2, unsigned __int16 ***a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // rbx
  __int16 v9; // ax
  int Programs; // edi
  int v11; // eax
  CSpp *v12; // rcx
  bool v13; // sf
  PTOKEN_PRIVILEGES v14; // r8
  int v16; // [rsp+30h] [rbp-40h] BYREF
  __int16 v17; // [rsp+34h] [rbp-3Ch]
  __int16 v18; // [rsp+36h] [rbp-3Ah]
  PTOKEN_PRIVILEGES NewState; // [rsp+A8h] [rbp+38h] BYREF
  void *v20; // [rsp+B0h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CSpp::GetInstallationVolumes", 11914, 1);
  v8 = 0;
  NewState = 0;
  v20 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v9 = 11922;
  if ( a2 && (v17 = 11922, v9 = 11923, a3) )
  {
    v16 = 0;
    v17 = 11923;
    v11 = SxOpenThreadOrProcessToken(v7, &v20);
    v8 = (char *)v20;
    Programs = v11;
    v16 = v11;
    v13 = v11 < 0;
    v9 = 11930;
    if ( !v13 )
    {
      v17 = 11930;
      Programs = CSpp::_EnableBackupRestorePrivs(v12, v20, &NewState);
      v16 = Programs;
      v9 = 11931;
      if ( Programs >= 0 )
      {
        v17 = 11931;
        Programs = CSpp::_GetPrograms(this, L"SOFTWARE", 0, 0, a2, a3);
        v16 = Programs;
        v9 = 11933;
        if ( Programs >= 0 )
        {
          v17 = 11933;
          goto LABEL_16;
        }
      }
    }
  }
  else
  {
    Programs = -2147024809;
    v16 = -2147024809;
  }
  v18 = v9;
LABEL_16:
  v14 = NewState;
  if ( NewState && (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    AdjustTokenPrivileges(v8, 0, NewState, 0, 0, 0);
    CoTaskMemFree(NewState);
    Programs = v16;
    NewState = 0;
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16, v6, (__int64)v14);
  return (unsigned int)Programs;
}

```

## disassembly

```asm
0x18000a280  mov     [rsp-28h+arg_0], rbx
0x18000a285  push    rbp
0x18000a286  push    rsi
0x18000a287  push    rdi
0x18000a288  push    r14
0x18000a28a  push    r15
0x18000a28c  mov     rbp, rsp
0x18000a28f  sub     rsp, 70h
0x18000a293  mov     rsi, r8
0x18000a296  mov     r14, rdx
0x18000a299  mov     r15, rcx
0x18000a29c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a3  lea     rax, WPP_GLOBAL_Control
0x18000a2aa  cmp     rcx, rax
0x18000a2ad  jz      short loc_18000A2CD
0x18000a2af  test    dword ptr [rcx+1Ch], 20000000h
0x18000a2b6  jz      short loc_18000A2CD
0x18000a2b8  mov     rcx, [rcx+10h]
0x18000a2bc  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18000a2c3  mov     edx, 0CBh
0x18000a2c8  call    WPP_SF_
0x18000a2cd  mov     r9d, 1; unsigned __int16
0x18000a2d3  lea     rdx, aCsppGetinstall; "CSpp::GetInstallationVolumes"
0x18000a2da  mov     r8d, 2E8Ah; unsigned __int16
0x18000a2e0  lea     rcx, [rbp+var_40]; this
0x18000a2e4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000a2e9  xor     ebx, ebx
0x18000a2eb  mov     [rbp+NewState], 0
0x18000a2f3  mov     [rbp+arg_10], rbx
0x18000a2f7  test    r14, r14
0x18000a2fa  jz      short loc_18000A2FF
0x18000a2fc  mov     [r14], ebx
0x18000a2ff  test    rsi, rsi
0x18000a302  jz      short loc_18000A307
0x18000a304  mov     [rsi], rbx
0x18000a307  mov     eax, 2E92h
0x18000a30c  test    r14, r14
0x18000a30f  jnz     short loc_18000A322
0x18000a311  mov     edi, 80070057h
0x18000a316  mov     [rbp+var_40], edi
0x18000a319  mov     [rbp+var_3A], ax
0x18000a31d  jmp     loc_18000A3A9
0x18000a322  mov     [rbp+var_3C], ax
0x18000a326  mov     eax, 2E93h
0x18000a32b  test    rsi, rsi
0x18000a32e  jz      short loc_18000A311
0x18000a330  lea     rdx, [rbp+arg_10]; void **
0x18000a334  mov     [rbp+var_40], ebx
0x18000a337  mov     [rbp+var_3C], ax
0x18000a33b  call    ?SxOpenThreadOrProcessToken@@YAJKPEAPEAX@Z; SxOpenThreadOrProcessToken(ulong,void * *)
0x18000a340  mov     rbx, [rbp+arg_10]
0x18000a344  mov     edi, eax
0x18000a346  mov     [rbp+var_40], eax
0x18000a349  test    eax, eax
0x18000a34b  mov     eax, 2E9Ah
0x18000a350  js      short loc_18000A319
0x18000a352  lea     r8, [rbp+NewState]; struct _TOKEN_PRIVILEGES **
0x18000a356  mov     [rbp+var_3C], ax
0x18000a35a  mov     rdx, rbx; void *
0x18000a35d  call    ?_EnableBackupRestorePrivs@CSpp@@AEAAJPEAXPEAPEAU_TOKEN_PRIVILEGES@@@Z; CSpp::_EnableBackupRestorePrivs(void *,_TOKEN_PRIVILEGES * *)
0x18000a362  mov     edi, eax
0x18000a364  mov     [rbp+var_40], eax
0x18000a367  test    eax, eax
0x18000a369  mov     eax, 2E9Bh
0x18000a36e  js      short loc_18000A319
0x18000a370  mov     [rsp+70h+ReturnLength], rsi; unsigned __int16 ***
0x18000a375  lea     rdx, aSoftware; "SOFTWARE"
0x18000a37c  xor     r9d, r9d; unsigned __int16 ***
0x18000a37f  mov     [rsp+70h+PreviousState], r14; unsigned int *
0x18000a384  xor     r8d, r8d; unsigned int *
0x18000a387  mov     [rbp+var_3C], ax
0x18000a38b  mov     rcx, r15; this
0x18000a38e  call    ?_GetPrograms@CSpp@@AEAAJPEBGPEAKPEAPEAPEAG12@Z; CSpp::_GetPrograms(ushort const *,ulong *,ushort * * *,ulong *,ushort * * *)
0x18000a393  mov     edi, eax
0x18000a395  mov     [rbp+var_40], eax
0x18000a398  test    eax, eax
0x18000a39a  mov     eax, 2E9Dh
0x18000a39f  js      loc_18000A319
0x18000a3a5  mov     [rbp+var_3C], ax
0x18000a3a9  mov     r8, [rbp+NewState]; NewState
0x18000a3ad  test    r8, r8
0x18000a3b0  jz      short loc_18000A3F1
0x18000a3b2  lea     rax, [rbx-1]
0x18000a3b6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a3ba  ja      short loc_18000A3F1
0x18000a3bc  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x18000a3c5  xor     r9d, r9d; BufferLength
0x18000a3c8  xor     edx, edx; DisableAllPrivileges
0x18000a3ca  mov     [rsp+70h+PreviousState], 0; PreviousState
0x18000a3d3  mov     rcx, rbx; TokenHandle
0x18000a3d6  call    cs:__imp_AdjustTokenPrivileges
0x18000a3dc  mov     rcx, [rbp+NewState]; pv
0x18000a3e0  call    cs:__imp_CoTaskMemFree
0x18000a3e6  mov     edi, [rbp+var_40]
0x18000a3e9  mov     [rbp+NewState], 0
0x18000a3f1  lea     rcx, [rbx-1]
0x18000a3f5  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000a3f9  ja      short loc_18000A404
0x18000a3fb  mov     rcx, rbx; hObject
0x18000a3fe  call    cs:__imp_CloseHandle
0x18000a404  lea     rcx, [rbp+var_40]; this
0x18000a408  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000a40d  mov     rbx, [rsp+70h+arg_0]
0x18000a415  mov     eax, edi
0x18000a417  add     rsp, 70h
0x18000a41b  pop     r15
0x18000a41d  pop     r14
0x18000a41f  pop     rdi
0x18000a420  pop     rsi
0x18000a421  pop     rbp
0x18000a422  retn
```

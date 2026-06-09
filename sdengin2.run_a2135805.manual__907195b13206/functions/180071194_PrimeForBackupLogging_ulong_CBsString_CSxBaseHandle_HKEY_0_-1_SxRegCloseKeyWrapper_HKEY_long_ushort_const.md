# PrimeForBackupLogging(ulong &,CBsString &,CSxBaseHandle<HKEY__ *,0,-1,&SxRegCloseKeyWrapper(HKEY__ *)> &,long,ushort const *)

- ea: `0x180071194`
- end: `0x180071330`
- name: `?PrimeForBackupLogging@@YAXAEAKAEAVCBsString@@AEAV?$CSxBaseHandle@PEAUHKEY__@@$0A@$0?0$1?SxRegCloseKeyWrapper@@YAHPEAU1@@Z@@JPEBG@Z`
- size: `412`
- prototype: `__int64 __fastcall(unsigned int *, struct CBsString *this, PHKEY phkResult, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180027920`
- `0x1800559b0`

## callees

- `0x18007109c`
- `0x180071194`
- `0x18007dfd0`
- `0x180091fb4`
- `0x180098a5c`
- `0x180098ebc`
- `0x1800cf5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800711d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071253`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800711d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071253`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071206`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071282`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071206`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071282`

## pseudocode

```c
__int64 __fastcall PrimeForBackupLogging(
        unsigned int *a1,
        struct CBsString *this,
        PHKEY phkResult,
        unsigned int a4,
        __int64 a5)
{
  HKEY v9; // rcx
  BOOL v10; // edi
  unsigned int v11; // eax
  unsigned int v13[4]; // [rsp+40h] [rbp-98h] BYREF
  _OWORD v14[2]; // [rsp+50h] [rbp-88h] BYREF
  __int128 v15; // [rsp+70h] [rbp-68h] BYREF
  __int128 v16; // [rsp+80h] [rbp-58h]

  if ( (unsigned __int64)*phkResult - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(*phkResult);
    *phkResult = 0;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup\\ScheduleParams\\TargetDevice",
         0,
         0x20019u,
         phkResult) >= 0 )
  {
    SxRegReadDWORD(*phkResult, L"Type", a1, 0);
    SxRegReadString(*phkResult, L"UniqueName", this);
  }
  v9 = *phkResult;
  v10 = 1;
  v13[0] = 1;
  if ( (unsigned __int64)v9 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    RegCloseKey(v9);
    *phkResult = 0;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x20019u,
         phkResult) >= 0 )
    v10 = SxRegReadDWORD(*phkResult, L"ValidSystemImageBackup", v13, 0) != 0;
  v15 = 0;
  v16 = 0;
  SdReadBackupTaskInfo((struct SD_SCHEDULE_CONFIG *)&v15);
  v14[0] = v15;
  v14[1] = v16;
  v11 = IsBackupErrorUnexpected(a4);
  return LogBackupResultTelemetry(a5, a4, v11, *a1, v10, *(_QWORD *)this, v14);
}

```

## disassembly

```asm
0x180071194  push    rbx
0x180071196  push    rbp
0x180071197  push    rsi
0x180071198  push    rdi
0x180071199  push    r14
0x18007119b  push    r15
0x18007119d  sub     rsp, 0A8h
0x1800711a4  mov     rax, cs:__security_cookie
0x1800711ab  xor     rax, rsp
0x1800711ae  mov     [rsp+0D8h+var_48], rax
0x1800711b6  mov     r15, [rsp+0D8h+arg_20]
0x1800711be  mov     rsi, rcx
0x1800711c1  mov     rcx, [r8]; hKey
0x1800711c4  mov     ebp, r9d
0x1800711c7  mov     rbx, r8
0x1800711ca  mov     r14, rdx
0x1800711cd  lea     rax, [rcx-1]
0x1800711d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800711d5  ja      short loc_1800711EA
0x1800711d7  call    cs:__imp_RegCloseKey
0x1800711de  nop     dword ptr [rax+rax+00h]
0x1800711e3  mov     qword ptr [rbx], 0
0x1800711ea  mov     r9d, 20019h; samDesired
0x1800711f0  mov     [rsp+0D8h+phkResult], rbx; phkResult
0x1800711f5  xor     r8d, r8d; ulOptions
0x1800711f8  lea     rdx, c_wszSafedocsDeviceTargetKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800711ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071206  call    cs:__imp_RegOpenKeyExW
0x18007120d  nop     dword ptr [rax+rax+00h]
0x180071212  test    eax, eax
0x180071214  js      short loc_18007123D
0x180071216  mov     rcx, [rbx]; hKey
0x180071219  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x180071220  xor     r9d, r9d; int
0x180071223  mov     r8, rsi; unsigned int *
0x180071226  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18007122b  mov     rcx, [rbx]; hKey
0x18007122e  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x180071235  mov     r8, r14; this
0x180071238  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18007123d  mov     rcx, [rbx]; hKey
0x180071240  mov     edi, 1
0x180071245  mov     [rsp+0D8h+var_98], edi
0x180071249  lea     rax, [rcx-1]
0x18007124d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180071251  ja      short loc_180071266
0x180071253  call    cs:__imp_RegCloseKey
0x18007125a  nop     dword ptr [rax+rax+00h]
0x18007125f  mov     qword ptr [rbx], 0
0x180071266  mov     r9d, 20019h; samDesired
0x18007126c  mov     [rsp+0D8h+phkResult], rbx; phkResult
0x180071271  xor     r8d, r8d; ulOptions
0x180071274  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18007127b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180071282  call    cs:__imp_RegOpenKeyExW
0x180071289  nop     dword ptr [rax+rax+00h]
0x18007128e  test    eax, eax
0x180071290  js      short loc_1800712B1
0x180071292  mov     rcx, [rbx]; hKey
0x180071295  lea     r8, [rsp+0D8h+var_98]; unsigned int *
0x18007129a  xor     r9d, r9d; int
0x18007129d  lea     rdx, c_wszSIBackupValid; "ValidSystemImageBackup"
0x1800712a4  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x1800712a9  xor     edi, edi
0x1800712ab  test    eax, eax
0x1800712ad  setnz   dil
0x1800712b1  xorps   xmm0, xmm0
0x1800712b4  lea     rcx, [rsp+0D8h+var_68]; struct SD_SCHEDULE_CONFIG *
0x1800712b9  movups  [rsp+0D8h+var_68], xmm0
0x1800712be  movups  [rsp+0D8h+var_58], xmm0
0x1800712c6  call    ?SdReadBackupTaskInfo@@YAJPEAUSD_SCHEDULE_CONFIG@@@Z; SdReadBackupTaskInfo(SD_SCHEDULE_CONFIG *)
0x1800712cb  movups  xmm0, [rsp+0D8h+var_68]
0x1800712d0  mov     ecx, ebp; int
0x1800712d2  movups  xmm1, [rsp+0D8h+var_58]
0x1800712da  movaps  [rsp+0D8h+var_88], xmm0
0x1800712df  movaps  [rsp+0D8h+var_78], xmm1
0x1800712e4  call    ?IsBackupErrorUnexpected@@YAHJ@Z; IsBackupErrorUnexpected(long)
0x1800712e9  mov     r9d, [rsi]
0x1800712ec  mov     r8d, eax
0x1800712ef  lea     rax, [rsp+0D8h+var_88]
0x1800712f4  mov     edx, ebp
0x1800712f6  mov     [rsp+0D8h+var_A8], rax
0x1800712fb  mov     rcx, r15
0x1800712fe  mov     rax, [r14]
0x180071301  mov     [rsp+0D8h+var_B0], rax
0x180071306  mov     dword ptr [rsp+0D8h+phkResult], edi
0x18007130a  call    ?LogBackupResultTelemetry@@YAXPEBGJHKH0USD_SCHEDULE_CONFIG@@@Z; LogBackupResultTelemetry(ushort const *,long,int,ulong,int,ushort const *,SD_SCHEDULE_CONFIG)
0x18007130f  mov     rcx, [rsp+0D8h+var_48]
0x180071317  xor     rcx, rsp; StackCookie
0x18007131a  call    __security_check_cookie
0x18007131f  add     rsp, 0A8h
0x180071326  pop     r15
0x180071328  pop     r14
0x18007132a  pop     rdi
0x18007132b  pop     rsi
0x18007132c  pop     rbp
0x18007132d  pop     rbx
0x18007132e  retn
```

# PrimeForBackupLogging(ulong &,CBsString &,CSxBaseHandle<HKEY__ *,0,-1,&SxRegCloseKeyWrapper(HKEY__ *)> &,long,ushort const *)

- ea: `0x18006e484`
- end: `0x18006e607`
- name: `?PrimeForBackupLogging@@YAXAEAKAEAVCBsString@@AEAV?$CSxBaseHandle@PEAUHKEY__@@$0A@$0?0$1?SxRegCloseKeyWrapper@@YAHPEAU1@@Z@@JPEBG@Z`
- size: `387`
- prototype: `__int64 __fastcall(unsigned int *, struct CBsString *this, PHKEY phkResult, int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180026920`
- `0x18005378c`

## callees

- `0x18006e38c`
- `0x18006e484`
- `0x18007ad90`
- `0x18008e078`
- `0x180094758`
- `0x180094b8c`
- `0x1800c9830`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e537`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e537`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e4f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e560`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e4f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e560`

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
0x18006e484  push    rbx
0x18006e486  push    rbp
0x18006e487  push    rsi
0x18006e488  push    rdi
0x18006e489  push    r14
0x18006e48b  push    r15
0x18006e48d  sub     rsp, 0A8h
0x18006e494  mov     rax, cs:__security_cookie
0x18006e49b  xor     rax, rsp
0x18006e49e  mov     [rsp+0D8h+var_48], rax
0x18006e4a6  mov     r15, [rsp+0D8h+arg_20]
0x18006e4ae  mov     rsi, rcx
0x18006e4b1  mov     rcx, [r8]; hKey
0x18006e4b4  mov     ebp, r9d
0x18006e4b7  mov     rbx, r8
0x18006e4ba  mov     r14, rdx
0x18006e4bd  lea     rax, [rcx-1]
0x18006e4c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006e4c5  ja      short loc_18006E4D4
0x18006e4c7  call    cs:__imp_RegCloseKey
0x18006e4cd  mov     qword ptr [rbx], 0
0x18006e4d4  mov     r9d, 20019h; samDesired
0x18006e4da  mov     [rsp+0D8h+phkResult], rbx; phkResult
0x18006e4df  xor     r8d, r8d; ulOptions
0x18006e4e2  lea     rdx, c_wszSafedocsDeviceTargetKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e4e9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e4f0  call    cs:__imp_RegOpenKeyExW
0x18006e4f6  test    eax, eax
0x18006e4f8  js      short loc_18006E521
0x18006e4fa  mov     rcx, [rbx]; hKey
0x18006e4fd  lea     rdx, c_wszSafedocsDeviceType; "Type"
0x18006e504  xor     r9d, r9d; int
0x18006e507  mov     r8, rsi; unsigned int *
0x18006e50a  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18006e50f  mov     rcx, [rbx]; hKey
0x18006e512  lea     rdx, c_wszSafedocsDeviceUniqueName; "UniqueName"
0x18006e519  mov     r8, r14; this
0x18006e51c  call    ?SxRegReadString@@YAJPEAUHKEY__@@PEBGPEAVCBsString@@@Z; SxRegReadString(HKEY__ *,ushort const *,CBsString *)
0x18006e521  mov     rcx, [rbx]; hKey
0x18006e524  mov     edi, 1
0x18006e529  mov     [rsp+0D8h+var_98], edi
0x18006e52d  lea     rax, [rcx-1]
0x18006e531  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006e535  ja      short loc_18006E544
0x18006e537  call    cs:__imp_RegCloseKey
0x18006e53d  mov     qword ptr [rbx], 0
0x18006e544  mov     r9d, 20019h; samDesired
0x18006e54a  mov     [rsp+0D8h+phkResult], rbx; phkResult
0x18006e54f  xor     r8d, r8d; ulOptions
0x18006e552  lea     rdx, c_wszSafedocsUser_Key; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18006e559  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e560  call    cs:__imp_RegOpenKeyExW
0x18006e566  test    eax, eax
0x18006e568  js      short loc_18006E589
0x18006e56a  mov     rcx, [rbx]; hKey
0x18006e56d  lea     r8, [rsp+0D8h+var_98]; unsigned int *
0x18006e572  xor     r9d, r9d; int
0x18006e575  lea     rdx, c_wszSIBackupValid; "ValidSystemImageBackup"
0x18006e57c  call    ?SxRegReadDWORD@@YAJPEAUHKEY__@@PEBGPEAKH@Z; SxRegReadDWORD(HKEY__ *,ushort const *,ulong *,int)
0x18006e581  xor     edi, edi
0x18006e583  test    eax, eax
0x18006e585  setnz   dil
0x18006e589  xorps   xmm0, xmm0
0x18006e58c  lea     rcx, [rsp+0D8h+var_68]; struct SD_SCHEDULE_CONFIG *
0x18006e591  movups  [rsp+0D8h+var_68], xmm0
0x18006e596  movups  [rsp+0D8h+var_58], xmm0
0x18006e59e  call    ?SdReadBackupTaskInfo@@YAJPEAUSD_SCHEDULE_CONFIG@@@Z; SdReadBackupTaskInfo(SD_SCHEDULE_CONFIG *)
0x18006e5a3  movups  xmm0, [rsp+0D8h+var_68]
0x18006e5a8  mov     ecx, ebp; int
0x18006e5aa  movups  xmm1, [rsp+0D8h+var_58]
0x18006e5b2  movaps  [rsp+0D8h+var_88], xmm0
0x18006e5b7  movaps  [rsp+0D8h+var_78], xmm1
0x18006e5bc  call    ?IsBackupErrorUnexpected@@YAHJ@Z; IsBackupErrorUnexpected(long)
0x18006e5c1  mov     r9d, [rsi]
0x18006e5c4  mov     r8d, eax
0x18006e5c7  lea     rax, [rsp+0D8h+var_88]
0x18006e5cc  mov     edx, ebp
0x18006e5ce  mov     [rsp+0D8h+var_A8], rax
0x18006e5d3  mov     rcx, r15
0x18006e5d6  mov     rax, [r14]
0x18006e5d9  mov     [rsp+0D8h+var_B0], rax
0x18006e5de  mov     dword ptr [rsp+0D8h+phkResult], edi
0x18006e5e2  call    ?LogBackupResultTelemetry@@YAXPEBGJHKH0USD_SCHEDULE_CONFIG@@@Z; LogBackupResultTelemetry(ushort const *,long,int,ulong,int,ushort const *,SD_SCHEDULE_CONFIG)
0x18006e5e7  mov     rcx, [rsp+0D8h+var_48]
0x18006e5ef  xor     rcx, rsp; StackCookie
0x18006e5f2  call    __security_check_cookie
0x18006e5f7  add     rsp, 0A8h
0x18006e5fe  pop     r15
0x18006e600  pop     r14
0x18006e602  pop     rdi
0x18006e603  pop     rsi
0x18006e604  pop     rbp
0x18006e605  pop     rbx
0x18006e606  retn
```

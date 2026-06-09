# SetupPlatform::GetSetupPlatformVersion(ushort const *,ulong *,ulong *,ulong *)

- ea: `0x18000ed8c`
- end: `0x18000efd3`
- name: `?GetSetupPlatformVersion@SetupPlatform@@YAJPEBGPEAK11@Z`
- size: `583`
- prototype: `__int64 __fastcall(SetupPlatform *this, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x1800123a0`

## callees

- `0x180003f00`
- `0x180003f10`
- `0x1800047ac`
- `0x180009800`
- `0x18000ed8c`
- `0x180010a40`
- `0x18001301c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eed8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eef0`
- `WDSCORE!CurrentIP` at `0x18000ee05`
- `WDSCORE!CurrentIP` at `0x18000eef8`
- `WDSCORE!CurrentIP` at `0x18000ee05`
- `WDSCORE!CurrentIP` at `0x18000eef8`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ee6b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ef72`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ee6b`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000ef72`

## string_xrefs

- `0x18000ede4`: `SetupPlatform.dll`
- `0x18000ee11`: `SetupPlatform::GetSetupPlatformVersion: Failed to build path to platform binary. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall SetupPlatform::GetSetupPlatformVersion(
        SetupPlatform *this,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v7; // rax
  signed int v8; // esi
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const WCHAR *v13; // rax
  signed int LastError; // eax
  bool v15; // sf
  signed int v16; // eax
  DWORD v17; // edi
  __int64 v18; // rbx
  const char *v19; // rax
  struct tagLOG_PARTIAL_MSG *v20; // rax
  _QWORD v21[2]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD v22[2]; // [rsp+70h] [rbp-10h] BYREF

  if ( !this || !a2 || !a3 )
    return 2147942487LL;
  v21[1] = 0;
  v21[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v7 = RAII::CAutoCleanupBase<unsigned short *>::operator&((__int64)v21);
  v8 = BuildPathHr(this, L"SetupPlatform.dll", v7);
  if ( v8 >= 0 )
  {
    v13 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD *))(v21[0] + 32LL))(v21);
    v22[1] = GetFixedFileInfo(v13);
    v22[0] = &RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable';
    if ( RAII::CAutoCleanupBase<tagVS_FIXEDFILEINFO *>::operator->(v22) )
    {
      *(_DWORD *)a2 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(_QWORD *))(v22[0] + 24LL))(v22) + 10);
      *a3 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(_QWORD *))(v22[0] + 24LL))(v22) + 8);
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError < 0;
      if ( LastError > 0 )
        v15 = 1;
      if ( v15 )
      {
        v16 = GetLastError();
        v8 = v16;
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        v8 = -2147467259;
      }
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = (const char *)(*(__int64 (__fastcall **)(_QWORD *))(v21[0] + 32LL))(v21);
      v20 = ConstructPartialMsgW(
              0x2000000,
              "SetupPlatform::GetSetupPlatformVersion: Failed get file info for [%s]. hr = 0x%x",
              v19,
              v8);
      WdsSetupLogMessageW(
        v20,
        0,
        L"D",
        0,
        97,
        L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
        L"SetupPlatform::GetSetupPlatformVersion",
        v18,
        v17,
        0,
        0);
    }
    v22[0] = &RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable';
    RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(v22);
  }
  else
  {
    v9 = GetLastError();
    v10 = CurrentIP();
    v11 = ConstructPartialMsgW(
            0x2000000,
            "SetupPlatform::GetSetupPlatformVersion: Failed to build path to platform binary. hr = 0x%x",
            v8);
    WdsSetupLogMessageW(
      v11,
      0,
      L"D",
      0,
      89,
      L"base\\ntsetup\\setupplatform\\lib\\static\\setupplatform.cpp",
      L"SetupPlatform::GetSetupPlatformVersion",
      v10,
      v9,
      0,
      0);
  }
  v21[0] = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000ed8c  push    rbp
0x18000ed8e  push    rbx
0x18000ed8f  push    rsi
0x18000ed90  push    rdi
0x18000ed91  push    r12
0x18000ed93  push    r13
0x18000ed95  push    r14
0x18000ed97  mov     rbp, rsp
0x18000ed9a  sub     rsp, 80h
0x18000eda1  mov     rdi, r8
0x18000eda4  mov     r14, rdx
0x18000eda7  mov     rbx, rcx
0x18000edaa  test    rcx, rcx
0x18000edad  jz      loc_18000EFBC
0x18000edb3  test    rdx, rdx
0x18000edb6  jz      loc_18000EFBC
0x18000edbc  test    r8, r8
0x18000edbf  jz      loc_18000EFBC
0x18000edc5  mov     [rbp+var_18], 0
0x18000edcd  lea     r12, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x18000edd4  mov     [rbp+var_20], r12
0x18000edd8  lea     rcx, [rbp+var_20]
0x18000eddc  call    ??I?$CAutoCleanupBase@PEAG@RAII@@UEBAPEBQEAGXZ; RAII::CAutoCleanupBase<ushort *>::operator&(void)
0x18000ede1  mov     r8, rax
0x18000ede4  lea     rdx, aSetupplatformD; "SetupPlatform.dll"
0x18000edeb  mov     rcx, rbx
0x18000edee  call    BuildPathHr
0x18000edf3  mov     esi, eax
0x18000edf5  test    eax, eax
0x18000edf7  jns     loc_18000EE86
0x18000edfd  call    cs:__imp_GetLastError
0x18000ee03  mov     edi, eax
0x18000ee05  call    cs:__imp_CurrentIP
0x18000ee0b  mov     rbx, rax
0x18000ee0e  mov     r8d, esi
0x18000ee11  lea     rdx, aSetupplatformG; "SetupPlatform::GetSetupPlatformVersion:"...
0x18000ee18  mov     ecx, 2000000h; unsigned int
0x18000ee1d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ee22  mov     [rsp+80h+var_30], 0
0x18000ee2a  mov     [rsp+80h+var_38], 0
0x18000ee33  mov     [rsp+80h+var_40], edi
0x18000ee37  mov     [rsp+80h+var_48], rbx
0x18000ee3c  lea     rcx, aSetupplatformG_1; "SetupPlatform::GetSetupPlatformVersion"
0x18000ee43  mov     [rsp+80h+var_50], rcx
0x18000ee48  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x18000ee4f  mov     [rsp+80h+var_58], rcx
0x18000ee54  mov     [rsp+80h+var_60], 59h ; 'Y'
0x18000ee5c  xor     r9d, r9d
0x18000ee5f  lea     r8, aD; "D"
0x18000ee66  xor     edx, edx
0x18000ee68  mov     rcx, rax
0x18000ee6b  call    cs:__imp_WdsSetupLogMessageW
0x18000ee71  nop
0x18000ee72  mov     [rbp+var_20], r12
0x18000ee76  lea     rcx, [rbp+var_20]
0x18000ee7a  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18000ee7f  mov     eax, esi
0x18000ee81  jmp     loc_18000EFC1
0x18000ee86  mov     rax, [rbp+var_20]
0x18000ee8a  lea     rcx, [rbp+var_20]
0x18000ee8e  mov     rax, [rax+20h]
0x18000ee92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee97  mov     rcx, rax; lpwstrFilename
0x18000ee9a  call    GetFixedFileInfo
0x18000ee9f  mov     [rbp+var_8], rax
0x18000eea3  lea     r13, ??_7?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@6B@; const RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::`vftable'
0x18000eeaa  mov     [rbp+var_10], r13
0x18000eeae  lea     rcx, [rbp+var_10]
0x18000eeb2  call    ??C?$CAutoCleanupBase@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEBAQEAUtagVS_FIXEDFILEINFO@@XZ; RAII::CAutoCleanupBase<tagVS_FIXEDFILEINFO *>::operator->(void)
0x18000eeb7  test    rax, rax
0x18000eeba  jnz     loc_18000EF8B
0x18000eec0  call    cs:__imp_GetLastError
0x18000eec6  mov     ebx, 80070000h
0x18000eecb  test    eax, eax
0x18000eecd  jle     short loc_18000EED6
0x18000eecf  movzx   eax, ax
0x18000eed2  or      eax, ebx
0x18000eed4  test    eax, eax
0x18000eed6  jns     short loc_18000EEEB
0x18000eed8  call    cs:__imp_GetLastError
0x18000eede  mov     esi, eax
0x18000eee0  test    eax, eax
0x18000eee2  jle     short loc_18000EEF0
0x18000eee4  movzx   esi, ax
0x18000eee7  or      esi, ebx
0x18000eee9  jmp     short loc_18000EEF0
0x18000eeeb  mov     esi, 80004005h
0x18000eef0  call    cs:__imp_GetLastError
0x18000eef6  mov     edi, eax
0x18000eef8  call    cs:__imp_CurrentIP
0x18000eefe  mov     rbx, rax
0x18000ef01  mov     rcx, [rbp+var_20]
0x18000ef05  mov     rax, [rcx+20h]
0x18000ef09  lea     rcx, [rbp+var_20]
0x18000ef0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef12  mov     r8, rax
0x18000ef15  mov     r9d, esi
0x18000ef18  lea     rdx, aSetupplatformG_0; "SetupPlatform::GetSetupPlatformVersion:"...
0x18000ef1f  mov     ecx, 2000000h; unsigned int
0x18000ef24  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ef29  mov     [rsp+80h+var_30], 0
0x18000ef31  mov     [rsp+80h+var_38], 0
0x18000ef3a  mov     [rsp+80h+var_40], edi
0x18000ef3e  mov     [rsp+80h+var_48], rbx
0x18000ef43  lea     rcx, aSetupplatformG_1; "SetupPlatform::GetSetupPlatformVersion"
0x18000ef4a  mov     [rsp+80h+var_50], rcx
0x18000ef4f  lea     rcx, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x18000ef56  mov     [rsp+80h+var_58], rcx
0x18000ef5b  mov     [rsp+80h+var_60], 61h ; 'a'
0x18000ef63  xor     r9d, r9d
0x18000ef66  lea     r8, aD; "D"
0x18000ef6d  xor     edx, edx
0x18000ef6f  mov     rcx, rax
0x18000ef72  call    cs:__imp_WdsSetupLogMessageW
0x18000ef78  nop
0x18000ef79  mov     [rbp+var_10], r13
0x18000ef7d  lea     rcx, [rbp+var_10]
0x18000ef81  call    ?Release@?$CAutoWdsLibFree@PEAUtagVS_FIXEDFILEINFO@@@RAII@@UEAAXXZ; RAII::CAutoWdsLibFree<tagVS_FIXEDFILEINFO *>::Release(void)
0x18000ef86  jmp     loc_18000EE72
0x18000ef8b  mov     rax, [rbp+var_10]
0x18000ef8f  lea     rcx, [rbp+var_10]
0x18000ef93  mov     rax, [rax+18h]
0x18000ef97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef9c  movzx   ecx, word ptr [rax+0Ah]
0x18000efa0  mov     [r14], ecx
0x18000efa3  mov     rax, [rbp+var_10]
0x18000efa7  lea     rcx, [rbp+var_10]
0x18000efab  mov     rax, [rax+18h]
0x18000efaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb4  movzx   ecx, word ptr [rax+8]
0x18000efb8  mov     [rdi], ecx
0x18000efba  jmp     short loc_18000EF79
0x18000efbc  mov     eax, 80070057h
0x18000efc1  add     rsp, 80h
0x18000efc8  pop     r14
0x18000efca  pop     r13
0x18000efcc  pop     r12
0x18000efce  pop     rdi
0x18000efcf  pop     rsi
0x18000efd0  pop     rbx
0x18000efd1  pop     rbp
0x18000efd2  retn
```

# UxUpdateManager::SetAndModifyShutdownFlags(ulong,ulong *)

- ea: `0x18003dde0`
- end: `0x18003e15f`
- name: `?SetAndModifyShutdownFlags@UxUpdateManager@@UEAAJKPEAK@Z`
- size: `895`
- prototype: `int __fastcall(UxUpdateManager *this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180010890`
- `0x180039510`
- `0x18003dde0`
- `0x18003fc64`
- `0x1800420e0`
- `0x18006ea28`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003e052`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003e0c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003e052`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003e0c1`

## string_xrefs

- `0x18003e132`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18003e14c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x18003e067`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003e0d6`: `C:\__w\1\s\src\orchestrator\core\USOSvc\UxUpdateManager.cpp`
- `0x18003de42`: `EnhancedUpdateAndShutdown`
- `0x18003df47`: `RestartOrShutdownNoCommit`
- `0x18003e03d`: `UpdateAndShutdown`
- `0x18003e044`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x18003e0b3`: `SOFTWARE\Microsoft\WindowsUpdate\CommitStatus`
- `0x18003e0ac`: `NoCommit`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall UxUpdateManager::SetAndModifyShutdownFlags(UxUpdateManager *this, unsigned int a2, unsigned int *a3)
{
  __int64 *System; // rax
  __int64 (__fastcall *v6)(__int64, const wchar_t **, __int64); // rdi
  int *traits_2_unsigned_short; // rax
  __int64 v8; // r8
  const char *v9; // r9
  __int64 v10; // r11
  __int64 v11; // rax
  char v12; // r15
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rdi
  __int64 *v15; // rax
  __int64 (__fastcall *v16)(__int64, const wchar_t **, __int64); // rdi
  int *v17; // rax
  __int64 v18; // r8
  const char *v19; // r9
  __int64 v20; // r11
  __int64 v21; // rax
  UxUpdateManager *v22; // rcx
  char v23; // si
  const char *v24; // r9
  volatile signed __int32 *v25; // rdi
  volatile signed __int32 *v26; // rdi
  unsigned int v27; // eax
  int result; // eax
  unsigned int v29; // eax
  unsigned int lpData; // [rsp+20h] [rbp-78h]
  unsigned int lpDataa; // [rsp+20h] [rbp-78h]
  const wchar_t *v32; // [rsp+30h] [rbp-68h] BYREF
  __int64 v33; // [rsp+38h] [rbp-60h]
  __int64 v34; // [rsp+40h] [rbp-58h] BYREF
  volatile signed __int32 *v35; // [rsp+48h] [rbp-50h]
  __int64 v36; // [rsp+50h] [rbp-48h] BYREF
  volatile signed __int32 *v37; // [rsp+58h] [rbp-40h]
  int Data; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  try
  {
    System = SystemInterface::Service::GetSystem(&v36);
    v6 = *(__int64 (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*System + 40LL))(
                                                                                       *System,
                                                                                       &v34)
                                                                      + 64LL);
    traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                       L"EnhancedUpdateAndShutdown",
                                       &dword_180100DDC,
                                       0);
    if ( traits_2_unsigned_short == &dword_180100DDC
      || (v11 = ((char *)traits_2_unsigned_short - (char *)L"EnhancedUpdateAndShutdown") >> 1, v11 == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v9);
    }
    v32 = L"EnhancedUpdateAndShutdown";
    v33 = v11;
    LOBYTE(v8) = 1;
    v12 = v6(v10, &v32, v8);
    v13 = v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v14 = v37;
    if ( v37 )
    {
      if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = SystemInterface::Service::GetSystem(&v34);
    v16 = *(__int64 (__fastcall **)(__int64, const wchar_t **, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v15 + 40LL))(
                                                                                        *v15,
                                                                                        &v36)
                                                                       + 64LL);
    v17 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                   L"RestartOrShutdownNoCommit",
                   &dword_180100E14,
                   0);
    if ( v17 == &dword_180100E14 || (v21 = ((char *)v17 - (char *)L"RestartOrShutdownNoCommit") >> 1, v21 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xC9,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
        v19);
    v32 = L"RestartOrShutdownNoCommit";
    v33 = v21;
    LOBYTE(v18) = 1;
    v23 = v16(v20, &v32, v18);
    v25 = v37;
    if ( v37 )
    {
      v22 = (UxUpdateManager *)(unsigned int)_InterlockedDecrement(v37 + 2);
      if ( !(_DWORD)v22 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
        if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      }
    }
    v26 = v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    Data = 1;
    if ( v12 && (a2 & 0x48) == 0x48 )
    {
      v27 = RegSetKeyValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus",
              L"UpdateAndShutdown",
              4u,
              &Data,
              4u);
      if ( v27 )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x474,
                 (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                 (const char *)v27,
                 lpData);
      a2 = a2 & 0xFFFFFFF3 | 4;
      *a3 = a2;
    }
    if ( v23 )
    {
      if ( (a2 & 0xC) == 0 )
      {
LABEL_35:
        *a3 = a2;
        return 0;
      }
      if ( (a2 & 0x40) == 0 )
      {
        v29 = RegSetKeyValueW(
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\WindowsUpdate\\CommitStatus",
                L"NoCommit",
                4u,
                &Data,
                4u);
        if ( v29 )
          return wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x485,
                   (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
                   (const char *)v29,
                   lpDataa);
        goto LABEL_35;
      }
    }
    else if ( (a2 & 0xC) == 0 || (a2 & 0x40) == 0 )
    {
      goto LABEL_35;
    }
    UxUpdateManager::PersistRebootStartTimeValues(v22);
    goto LABEL_35;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x492,
             (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\USOSvc\\UxUpdateManager.cpp",
             v24);
  }
  return result;
}

```

## disassembly

```asm
0x18003dde0  mov     [rsp+arg_0], rbx
0x18003dde5  mov     [rsp+arg_8], rsi
0x18003ddea  push    rdi
0x18003ddeb  push    r12
0x18003dded  push    r13
0x18003ddef  push    r14
0x18003ddf1  push    r15
0x18003ddf3  sub     rsp, 70h
0x18003ddf7  mov     rax, cs:__security_cookie
0x18003ddfe  xor     rax, rsp
0x18003de01  mov     [rsp+98h+var_30], rax
0x18003de06  mov     r14, r8
0x18003de09  mov     ebx, edx
0x18003de0b  lea     rcx, [rsp+98h+var_48]
0x18003de10  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003de15  nop
0x18003de16  mov     rcx, [rax]
0x18003de19  mov     rax, [rcx]
0x18003de1c  lea     rdx, [rsp+98h+var_58]
0x18003de21  mov     rax, [rax+28h]
0x18003de25  call    _guard_dispatch_icall
0x18003de2a  nop
0x18003de2b  mov     r11, [rax]
0x18003de2e  mov     rax, [r11]
0x18003de31  mov     rdi, [rax+40h]
0x18003de35  xor     r8d, r8d
0x18003de38  lea     rsi, dword_180100DDC
0x18003de3f  mov     rdx, rsi
0x18003de42  lea     r15, aEnhancedupdate; "EnhancedUpdateAndShutdown"
0x18003de49  mov     rcx, r15
0x18003de4c  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003de51  cmp     rax, rsi
0x18003de54  jz      loc_18003E144
0x18003de5a  sub     rax, r15
0x18003de5d  sar     rax, 1
0x18003de60  or      r12, 0FFFFFFFFFFFFFFFFh
0x18003de64  cmp     rax, r12
0x18003de67  jz      loc_18003E144
0x18003de6d  mov     [rsp+98h+var_68], r15
0x18003de72  mov     [rsp+98h+var_60], rax
0x18003de77  mov     r8b, 1
0x18003de7a  lea     rdx, [rsp+98h+var_68]
0x18003de7f  mov     rcx, r11
0x18003de82  mov     rax, rdi
0x18003de85  call    _guard_dispatch_icall
0x18003de8a  mov     r15b, al
0x18003de8d  mov     rdi, [rsp+98h+var_50]
0x18003de92  test    rdi, rdi
0x18003de95  jz      short loc_18003DECF
0x18003de97  mov     ecx, r12d
0x18003de9a  lock xadd [rdi+8], ecx
0x18003de9f  add     ecx, r12d
0x18003dea2  jnz     short loc_18003DECF
0x18003dea4  mov     rax, [rdi]
0x18003dea7  mov     rcx, rdi
0x18003deaa  mov     rax, [rax]
0x18003dead  call    _guard_dispatch_icall
0x18003deb2  mov     eax, r12d
0x18003deb5  lock xadd [rdi+0Ch], eax
0x18003deba  add     eax, r12d
0x18003debd  jnz     short loc_18003DECF
0x18003debf  mov     rax, [rdi]
0x18003dec2  mov     rcx, rdi
0x18003dec5  mov     rax, [rax+8]
0x18003dec9  call    _guard_dispatch_icall
0x18003dece  nop
0x18003decf  mov     rdi, [rsp+98h+var_40]
0x18003ded4  test    rdi, rdi
0x18003ded7  jz      short loc_18003DF10
0x18003ded9  mov     eax, r12d
0x18003dedc  lock xadd [rdi+8], eax
0x18003dee1  add     eax, r12d
0x18003dee4  jnz     short loc_18003DF10
0x18003dee6  mov     rax, [rdi]
0x18003dee9  mov     rcx, rdi
0x18003deec  mov     rax, [rax]
0x18003deef  call    _guard_dispatch_icall
0x18003def4  mov     eax, r12d
0x18003def7  lock xadd [rdi+0Ch], eax
0x18003defc  add     eax, r12d
0x18003deff  jnz     short loc_18003DF10
0x18003df01  mov     rax, [rdi]
0x18003df04  mov     rcx, rdi
0x18003df07  mov     rax, [rax+8]
0x18003df0b  call    _guard_dispatch_icall
0x18003df10  lea     rcx, [rsp+98h+var_58]
0x18003df15  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18003df1a  nop
0x18003df1b  mov     rcx, [rax]
0x18003df1e  mov     rax, [rcx]
0x18003df21  lea     rdx, [rsp+98h+var_48]
0x18003df26  mov     rax, [rax+28h]
0x18003df2a  call    _guard_dispatch_icall
0x18003df2f  nop
0x18003df30  mov     r11, [rax]
0x18003df33  mov     rax, [r11]
0x18003df36  mov     rdi, [rax+40h]
0x18003df3a  xor     r8d, r8d
0x18003df3d  lea     rsi, dword_180100E14
0x18003df44  mov     rdx, rsi
0x18003df47  lea     r13, aRestartorshutd; "RestartOrShutdownNoCommit"
0x18003df4e  mov     rcx, r13
0x18003df51  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18003df56  cmp     rax, rsi
0x18003df59  jz      loc_18003E12A
0x18003df5f  sub     rax, r13
0x18003df62  sar     rax, 1
0x18003df65  cmp     rax, r12
0x18003df68  jz      loc_18003E12A
0x18003df6e  mov     [rsp+98h+var_68], r13
0x18003df73  mov     [rsp+98h+var_60], rax
0x18003df78  mov     r8b, 1
0x18003df7b  lea     rdx, [rsp+98h+var_68]
0x18003df80  mov     rcx, r11
0x18003df83  mov     rax, rdi
0x18003df86  call    _guard_dispatch_icall
0x18003df8b  mov     sil, al
0x18003df8e  mov     rdi, [rsp+98h+var_40]
0x18003df93  test    rdi, rdi
0x18003df96  jz      short loc_18003DFD0
0x18003df98  mov     ecx, r12d
0x18003df9b  lock xadd [rdi+8], ecx
0x18003dfa0  add     ecx, r12d
0x18003dfa3  jnz     short loc_18003DFD0
0x18003dfa5  mov     rax, [rdi]
0x18003dfa8  mov     rcx, rdi
0x18003dfab  mov     rax, [rax]
0x18003dfae  call    _guard_dispatch_icall
0x18003dfb3  mov     eax, r12d
0x18003dfb6  lock xadd [rdi+0Ch], eax
0x18003dfbb  add     eax, r12d
0x18003dfbe  jnz     short loc_18003DFD0
0x18003dfc0  mov     rax, [rdi]
0x18003dfc3  mov     rcx, rdi
0x18003dfc6  mov     rax, [rax+8]
0x18003dfca  call    _guard_dispatch_icall
0x18003dfcf  nop
0x18003dfd0  mov     rdi, [rsp+98h+var_50]
0x18003dfd5  test    rdi, rdi
0x18003dfd8  jz      short loc_18003E011
0x18003dfda  mov     eax, r12d
0x18003dfdd  lock xadd [rdi+8], eax
0x18003dfe2  add     eax, r12d
0x18003dfe5  jnz     short loc_18003E011
0x18003dfe7  mov     rax, [rdi]
0x18003dfea  mov     rcx, rdi
0x18003dfed  mov     rax, [rax]
0x18003dff0  call    _guard_dispatch_icall
0x18003dff5  mov     eax, r12d
0x18003dff8  lock xadd [rdi+0Ch], eax
0x18003dffd  add     eax, r12d
0x18003e000  jnz     short loc_18003E011
0x18003e002  mov     rax, [rdi]
0x18003e005  mov     rcx, rdi
0x18003e008  mov     rax, [rax+8]
0x18003e00c  call    _guard_dispatch_icall
0x18003e011  mov     [rsp+98h+Data], 1
0x18003e019  test    r15b, r15b
0x18003e01c  jz      short loc_18003E087
0x18003e01e  mov     eax, ebx
0x18003e020  and     eax, 48h
0x18003e023  cmp     al, 48h ; 'H'
0x18003e025  jnz     short loc_18003E087
0x18003e027  mov     edi, 4
0x18003e02c  mov     [rsp+98h+cbData], edi; cbData
0x18003e030  lea     rax, [rsp+98h+Data]
0x18003e035  mov     [rsp+98h+lpData], rax; unsigned int
0x18003e03a  mov     r9d, edi; dwType
0x18003e03d  lea     r8, ValueName; "UpdateAndShutdown"
0x18003e044  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x18003e04b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e052  call    cs:__imp_RegSetKeyValueW
0x18003e058  test    eax, eax
0x18003e05a  jz      short loc_18003E07D
0x18003e05c  mov     rcx, [rsp+98h]; this
0x18003e064  mov     r9d, eax; char *
0x18003e067  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003e06e  mov     edx, 474h; void *
0x18003e073  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e078  jmp     loc_18003E103
0x18003e07d  and     ebx, 0FFFFFFF7h
0x18003e080  or      ebx, edi
0x18003e082  mov     [r14], ebx
0x18003e085  jmp     short loc_18003E08C
0x18003e087  mov     edi, 4
0x18003e08c  test    sil, sil
0x18003e08f  jz      short loc_18003E0E9
0x18003e091  test    bl, 0Ch
0x18003e094  jz      short loc_18003E0F8
0x18003e096  test    bl, 40h
0x18003e099  jnz     short loc_18003E0F3
0x18003e09b  mov     [rsp+98h+cbData], edi; cbData
0x18003e09f  lea     rax, [rsp+98h+Data]
0x18003e0a4  mov     [rsp+98h+lpData], rax; unsigned int
0x18003e0a9  mov     r9d, edi; dwType
0x18003e0ac  lea     r8, aNocommit; "NoCommit"
0x18003e0b3  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\WindowsUpdate\\Com"...
0x18003e0ba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e0c1  call    cs:__imp_RegSetKeyValueW
0x18003e0c7  test    eax, eax
0x18003e0c9  jz      short loc_18003E0F8
0x18003e0cb  mov     rcx, [rsp+98h]; this
0x18003e0d3  mov     r9d, eax; char *
0x18003e0d6  lea     r8, aCW1SSrcOrchest_4; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18003e0dd  mov     edx, 485h; void *
0x18003e0e2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e0e7  jmp     short loc_18003E103
0x18003e0e9  test    bl, 0Ch
0x18003e0ec  jz      short loc_18003E0F8
0x18003e0ee  test    bl, 40h
0x18003e0f1  jz      short loc_18003E0F8
0x18003e0f3  call    ?PersistRebootStartTimeValues@UxUpdateManager@@AEAAXXZ; UxUpdateManager::PersistRebootStartTimeValues(void)
0x18003e0f8  mov     [r14], ebx
0x18003e0fb  xor     eax, eax
0x18003e0fd  jmp     short loc_18003E103
0x18003e0ff  mov     eax, [rsp+98h+Data]
0x18003e103  mov     rcx, [rsp+98h+var_30]
0x18003e108  xor     rcx, rsp; StackCookie
0x18003e10b  call    __security_check_cookie
0x18003e110  lea     r11, [rsp+98h+var_28]
0x18003e115  mov     rbx, [r11+30h]
0x18003e119  mov     rsi, [r11+38h]
0x18003e11d  mov     rsp, r11
0x18003e120  pop     r15
0x18003e122  pop     r14
0x18003e124  pop     r13
0x18003e126  pop     r12
0x18003e128  pop     rdi
0x18003e129  retn
0x18003e12a  mov     rcx, [rsp+98h]; this
0x18003e132  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003e139  mov     edx, 0C9h; void *
0x18003e13e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003e144  mov     rcx, [rsp+98h]; this
0x18003e14c  lea     r8, aCW1SPackagesMi_2; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18003e153  mov     edx, 0C9h; void *
0x18003e158  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```

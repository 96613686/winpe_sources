# Windows::Power::Manager::PreventSystemSleep(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool)

- ea: `0x1800b1a50`
- end: `0x1800b1e44`
- name: `?PreventSystemSleep@Manager@Power@Windows@@UEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `1012`
- prototype: `__int64 __fastcall(Windows::Power::Manager *this)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update`

## callees

- `0x1800112d0`
- `0x180042e00`
- `0x180042e48`
- `0x180063c38`
- `0x18006ea28`
- `0x1800b187c`
- `0x1800b19c8`
- `0x1800b1a50`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1da3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1da3`

## string_xrefs

- `0x1800b1be8`: `TaskClient`
- `0x1800b1cdd`: `USO task`
- `0x1800b1dd3`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`
- `0x1800b1de8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`
- `0x1800b1e1d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`
- `0x1800b1e32`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Power.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Power::Manager::PreventSystemSleep(Windows::Power::Manager *this, HMODULE a2, char a3)
{
  __int64 *DockedPower; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  _QWORD *System; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  void (__fastcall *v16)(__int64, __int64 *, _QWORD *, __int64 *); // r10
  const wchar_t *v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r9
  HMODULE v20; // rax
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  int v23; // eax
  int v24; // eax
  __int64 *v25; // rax
  __int64 v26; // rdx
  void (__fastcall ***v27)(_QWORD, __int64); // rcx
  int v28; // [rsp+20h] [rbp-49h]
  _QWORD v29[3]; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-21h] BYREF
  volatile signed __int32 *v31; // [rsp+50h] [rbp-19h]
  _BYTE v32[8]; // [rsp+58h] [rbp-11h] BYREF
  volatile signed __int32 *v33; // [rsp+60h] [rbp-9h]
  int v34; // [rsp+68h] [rbp-1h] BYREF
  int v35; // [rsp+6Ch] [rbp+3h] BYREF
  __int64 v36[2]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v37; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v29[2] = &Windows::Power::Manager::s_requestLock;
  if ( (unsigned int)mtx_do_lock(&Windows::Power::Manager::s_requestLock) )
    std::_Throw_Cpp_error(5);
  if ( dword_18014D4FC == 0x7FFFFFFF )
  {
    dword_18014D4FC = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( !*((_QWORD *)this + 3) )
  {
    DockedPower = Windows::DockedHelpers::GetDockedPower(v36);
    v7 = *DockedPower;
    *DockedPower = 0;
    v8 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( v36[0] )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36[0] + 16LL))(v36[0]);
  }
  v35 = 0;
  v34 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 40LL))(*((_QWORD *)this + 3), &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
      (const char *)(unsigned int)v9,
      v28);
  v10 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 64LL))(*((_QWORD *)this + 3), &v34);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
      (const char *)(unsigned int)v10,
      v28);
  if ( !v34 || a3 != (v35 != 0) )
  {
    v11 = *((_QWORD *)this + 2);
    if ( v11 )
    {
      v36[0] = 0;
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 8LL))(v11, v36);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2));
      v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
      *((_QWORD *)this + 2) = 0;
      if ( v12 )
        (**v12)(v12, 1);
      if ( v36[0] )
        (**(void (__fastcall ***)(__int64, __int64))v36[0])(v36[0], 1);
    }
    v37 = 0;
    System = (_QWORD *)SystemInterface::Service::GetSystem(v32);
    v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*System + 104LL))(*System, v30);
    v15 = *(_QWORD *)v14;
    v16 = *(void (__fastcall **)(__int64, __int64 *, _QWORD *, __int64 *))(**(_QWORD **)v14 + 16LL);
    v17 = L"PdcActivatorWithNetwork";
    if ( a3 )
      v17 = L"TaskClient";
    v18 = -1;
    do
      ++v18;
    while ( v17[v18] );
    v19 = *((_QWORD *)a2 + 2);
    v20 = a2;
    if ( *((_QWORD *)a2 + 3) > 7u )
      v20 = *(HMODULE *)a2;
    v36[0] = (__int64)v17;
    v36[1] = v18;
    v29[0] = v20;
    v29[1] = v19;
    v16(v15, &v37, v29, v36);
    v21 = v31;
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
    v22 = v33;
    if ( v33 )
    {
      if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
    Windows::Power::Manager::CreatePowerRequest((__int64)this, a2);
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(HMODULE *)a2;
    v23 = (*(__int64 (__fastcall **)(_QWORD, HMODULE, const wchar_t *))(**((_QWORD **)this + 3) + 48LL))(
            *((_QWORD *)this + 3),
            a2,
            L"USO task");
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x44,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
        (const char *)(unsigned int)v23,
        v28);
    if ( a3 )
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 24LL))(*((_QWORD *)this + 3));
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Power.cpp",
          (const char *)(unsigned int)v24,
          v28);
    }
    else
    {
      Windows::Power::Manager::ReleasePDCTask(this);
    }
    v25 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 16LL))(v37, v36);
    v26 = *v25;
    *v25 = 0;
    v27 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v26;
    if ( v27 )
      (**v27)(v27, 1);
    if ( v36[0] )
      (**(void (__fastcall ***)(__int64, __int64))v36[0])(v36[0], 1);
    if ( v37 )
      (**(void (__fastcall ***)(__int64, __int64))v37)(v37, 1);
  }
  if ( !--dword_18014D4FC )
  {
    dword_18014D4F8 = -1;
    ReleaseSRWLockExclusive(&stru_18014D4C0);
  }
}

```

## disassembly

```asm
0x1800b1a50  mov     [rsp-8+arg_10], rbx
0x1800b1a55  push    rbp
0x1800b1a56  push    rsi
0x1800b1a57  push    rdi
0x1800b1a58  push    r12
0x1800b1a5a  push    r13
0x1800b1a5c  push    r14
0x1800b1a5e  push    r15
0x1800b1a60  lea     rbp, [rsp-27h]
0x1800b1a65  sub     rsp, 90h
0x1800b1a6c  mov     rax, cs:__security_cookie
0x1800b1a73  xor     rax, rsp
0x1800b1a76  mov     [rbp+57h+var_38], rax
0x1800b1a7a  mov     r14b, r8b
0x1800b1a7d  mov     rsi, rdx
0x1800b1a80  mov     rbx, rcx
0x1800b1a83  lea     rcx, ?s_requestLock@Manager@Power@Windows@@0Vmutex@std@@A; std::mutex Windows::Power::Manager::s_requestLock
0x1800b1a8a  mov     [rbp+57h+var_80], rcx
0x1800b1a8e  call    mtx_do_lock
0x1800b1a93  xor     r15d, r15d
0x1800b1a96  test    eax, eax
0x1800b1a98  jnz     loc_1800B1DFA
0x1800b1a9e  cmp     cs:dword_18014D4FC, 7FFFFFFFh
0x1800b1aa8  jz      loc_1800B1E05
0x1800b1aae  cmp     [rbx+18h], r15
0x1800b1ab2  jnz     short loc_1800B1AF3
0x1800b1ab4  lea     rcx, [rbp+57h+var_50]
0x1800b1ab8  call    ?GetDockedPower@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedPower@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedPower(void)
0x1800b1abd  mov     rdx, [rax]
0x1800b1ac0  mov     [rax], r15
0x1800b1ac3  mov     rcx, [rbx+18h]
0x1800b1ac7  mov     [rbx+18h], rdx
0x1800b1acb  test    rcx, rcx
0x1800b1ace  jz      short loc_1800B1ADD
0x1800b1ad0  mov     rax, [rcx]
0x1800b1ad3  mov     rax, [rax+10h]
0x1800b1ad7  call    _guard_dispatch_icall
0x1800b1adc  nop
0x1800b1add  mov     rcx, [rbp+57h+var_50]
0x1800b1ae1  test    rcx, rcx
0x1800b1ae4  jz      short loc_1800B1AF3
0x1800b1ae6  mov     rax, [rcx]
0x1800b1ae9  mov     rax, [rax+10h]
0x1800b1aed  call    _guard_dispatch_icall
0x1800b1af2  nop
0x1800b1af3  mov     [rbp+57h+var_54], r15d
0x1800b1af7  mov     [rbp+57h+var_58], r15d
0x1800b1afb  mov     rcx, [rbx+18h]
0x1800b1aff  mov     rax, [rcx]
0x1800b1b02  lea     rdx, [rbp+57h+var_54]
0x1800b1b06  mov     rax, [rax+28h]
0x1800b1b0a  call    _guard_dispatch_icall
0x1800b1b0f  mov     rcx, [rbp+5Fh]; this
0x1800b1b13  test    eax, eax
0x1800b1b15  js      loc_1800B1E1A
0x1800b1b1b  mov     rcx, [rbx+18h]
0x1800b1b1f  mov     rax, [rcx]
0x1800b1b22  lea     rdx, [rbp+57h+var_58]
0x1800b1b26  mov     rax, [rax+40h]
0x1800b1b2a  call    _guard_dispatch_icall
0x1800b1b2f  mov     rcx, [rbp+5Fh]; this
0x1800b1b33  test    eax, eax
0x1800b1b35  js      loc_1800B1E2F
0x1800b1b3b  mov     r13d, 1
0x1800b1b41  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800b1b45  cmp     [rbp+57h+var_58], r15d
0x1800b1b49  jz      short loc_1800B1B5B
0x1800b1b4b  cmp     [rbp+57h+var_54], r15d
0x1800b1b4f  setnz   al
0x1800b1b52  cmp     r14b, al
0x1800b1b55  jz      loc_1800B1D8C
0x1800b1b5b  mov     rcx, [rbx+10h]
0x1800b1b5f  test    rcx, rcx
0x1800b1b62  jz      short loc_1800B1BBC
0x1800b1b64  mov     [rbp+57h+var_50], r15
0x1800b1b68  mov     rax, [rcx]
0x1800b1b6b  lea     rdx, [rbp+57h+var_50]
0x1800b1b6f  mov     rax, [rax+8]
0x1800b1b73  call    _guard_dispatch_icall
0x1800b1b78  nop
0x1800b1b79  mov     rcx, [rbx+10h]
0x1800b1b7d  mov     rax, [rcx]
0x1800b1b80  mov     rax, [rax+18h]
0x1800b1b84  call    _guard_dispatch_icall
0x1800b1b89  mov     rcx, [rbx+10h]
0x1800b1b8d  mov     [rbx+10h], r15
0x1800b1b91  test    rcx, rcx
0x1800b1b94  jz      short loc_1800B1BA5
0x1800b1b96  mov     rax, [rcx]
0x1800b1b99  mov     edx, r13d
0x1800b1b9c  mov     rax, [rax]
0x1800b1b9f  call    _guard_dispatch_icall
0x1800b1ba4  nop
0x1800b1ba5  mov     rcx, [rbp+57h+var_50]
0x1800b1ba9  test    rcx, rcx
0x1800b1bac  jz      short loc_1800B1BBC
0x1800b1bae  mov     rax, [rcx]
0x1800b1bb1  mov     edx, r13d
0x1800b1bb4  mov     rax, [rax]
0x1800b1bb7  call    _guard_dispatch_icall
0x1800b1bbc  mov     [rbp+57h+var_40], r15
0x1800b1bc0  lea     rcx, [rbp+57h+var_68]
0x1800b1bc4  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800b1bc9  nop
0x1800b1bca  mov     rcx, [rax]
0x1800b1bcd  mov     rax, [rcx]
0x1800b1bd0  lea     rdx, [rbp+57h+var_78]
0x1800b1bd4  mov     rax, [rax+68h]
0x1800b1bd8  call    _guard_dispatch_icall
0x1800b1bdd  nop
0x1800b1bde  mov     rcx, [rax]
0x1800b1be1  mov     rax, [rcx]
0x1800b1be4  mov     r10, [rax+10h]
0x1800b1be8  lea     rax, aTaskclient; "TaskClient"
0x1800b1bef  lea     r8, aPdcactivatorwi; "PdcActivatorWithNetwork"
0x1800b1bf6  test    r14b, r14b
0x1800b1bf9  cmovnz  r8, rax
0x1800b1bfd  mov     rdx, r12
0x1800b1c00  inc     rdx
0x1800b1c03  cmp     [r8+rdx*2], r15w
0x1800b1c08  jnz     short loc_1800B1C00
0x1800b1c0a  mov     r9, [rsi+10h]
0x1800b1c0e  mov     rax, rsi
0x1800b1c11  cmp     qword ptr [rsi+18h], 7
0x1800b1c16  jbe     short loc_1800B1C1B
0x1800b1c18  mov     rax, [rsi]
0x1800b1c1b  mov     [rbp+57h+var_50], r8
0x1800b1c1f  mov     [rbp+57h+var_48], rdx
0x1800b1c23  mov     [rbp+57h+var_90], rax
0x1800b1c27  mov     [rbp+57h+var_88], r9
0x1800b1c2b  lea     r9, [rbp+57h+var_50]
0x1800b1c2f  lea     r8, [rbp+57h+var_90]
0x1800b1c33  lea     rdx, [rbp+57h+var_40]
0x1800b1c37  mov     rax, r10
0x1800b1c3a  call    _guard_dispatch_icall
0x1800b1c3f  nop
0x1800b1c40  mov     rdi, [rbp+57h+var_70]
0x1800b1c44  test    rdi, rdi
0x1800b1c47  jz      short loc_1800B1C81
0x1800b1c49  mov     eax, r12d
0x1800b1c4c  lock xadd [rdi+8], eax
0x1800b1c51  add     eax, r12d
0x1800b1c54  jnz     short loc_1800B1C81
0x1800b1c56  mov     rax, [rdi]
0x1800b1c59  mov     rcx, rdi
0x1800b1c5c  mov     rax, [rax]
0x1800b1c5f  call    _guard_dispatch_icall
0x1800b1c64  mov     eax, r12d
0x1800b1c67  lock xadd [rdi+0Ch], eax
0x1800b1c6c  add     eax, r12d
0x1800b1c6f  jnz     short loc_1800B1C81
0x1800b1c71  mov     rax, [rdi]
0x1800b1c74  mov     rcx, rdi
0x1800b1c77  mov     rax, [rax+8]
0x1800b1c7b  call    _guard_dispatch_icall
0x1800b1c80  nop
0x1800b1c81  mov     rdi, [rbp+57h+var_60]
0x1800b1c85  test    rdi, rdi
0x1800b1c88  jz      short loc_1800B1CC1
0x1800b1c8a  mov     eax, r12d
0x1800b1c8d  lock xadd [rdi+8], eax
0x1800b1c92  add     eax, r12d
0x1800b1c95  jnz     short loc_1800B1CC1
0x1800b1c97  mov     rax, [rdi]
0x1800b1c9a  mov     rcx, rdi
0x1800b1c9d  mov     rax, [rax]
0x1800b1ca0  call    _guard_dispatch_icall
0x1800b1ca5  mov     eax, r12d
0x1800b1ca8  lock xadd [rdi+0Ch], eax
0x1800b1cad  add     eax, r12d
0x1800b1cb0  jnz     short loc_1800B1CC1
0x1800b1cb2  mov     rax, [rdi]
0x1800b1cb5  mov     rcx, rdi
0x1800b1cb8  mov     rax, [rax+8]
0x1800b1cbc  call    _guard_dispatch_icall
0x1800b1cc1  mov     rdx, rsi
0x1800b1cc4  mov     rcx, rbx
0x1800b1cc7  call    ?CreatePowerRequest@Manager@Power@Windows@@AEAAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Windows::Power::Manager::CreatePowerRequest(std::wstring &)
0x1800b1ccc  mov     rcx, [rbx+18h]
0x1800b1cd0  mov     rax, [rcx]
0x1800b1cd3  cmp     qword ptr [rsi+18h], 7
0x1800b1cd8  jbe     short loc_1800B1CDD
0x1800b1cda  mov     rsi, [rsi]
0x1800b1cdd  lea     r8, aUsoTask; "USO task"
0x1800b1ce4  mov     rdx, rsi
0x1800b1ce7  mov     rax, [rax+30h]
0x1800b1ceb  call    _guard_dispatch_icall
0x1800b1cf0  mov     rcx, [rbp+5Fh]; this
0x1800b1cf4  test    eax, eax
0x1800b1cf6  js      loc_1800B1DD0
0x1800b1cfc  test    r14b, r14b
0x1800b1cff  jz      short loc_1800B1D1F
0x1800b1d01  mov     rcx, [rbx+18h]
0x1800b1d05  mov     rax, [rcx]
0x1800b1d08  mov     rax, [rax+18h]
0x1800b1d0c  call    _guard_dispatch_icall
0x1800b1d11  mov     rcx, [rbp+5Fh]; this
0x1800b1d15  test    eax, eax
0x1800b1d17  js      loc_1800B1DE5
0x1800b1d1d  jmp     short loc_1800B1D27
0x1800b1d1f  mov     rcx, rbx; this
0x1800b1d22  call    ?ReleasePDCTask@Manager@Power@Windows@@AEAAXXZ; Windows::Power::Manager::ReleasePDCTask(void)
0x1800b1d27  mov     rcx, [rbp+57h+var_40]
0x1800b1d2b  mov     rax, [rcx]
0x1800b1d2e  lea     rdx, [rbp+57h+var_50]
0x1800b1d32  mov     rax, [rax+10h]
0x1800b1d36  call    _guard_dispatch_icall
0x1800b1d3b  mov     rdx, [rax]
0x1800b1d3e  mov     [rax], r15
0x1800b1d41  mov     rcx, [rbx+10h]
0x1800b1d45  mov     [rbx+10h], rdx
0x1800b1d49  test    rcx, rcx
0x1800b1d4c  jz      short loc_1800B1D5C
0x1800b1d4e  mov     rax, [rcx]
0x1800b1d51  mov     edx, r13d
0x1800b1d54  mov     rax, [rax]
0x1800b1d57  call    _guard_dispatch_icall
0x1800b1d5c  mov     rcx, [rbp+57h+var_50]
0x1800b1d60  test    rcx, rcx
0x1800b1d63  jz      short loc_1800B1D74
0x1800b1d65  mov     rax, [rcx]
0x1800b1d68  mov     edx, r13d
0x1800b1d6b  mov     rax, [rax]
0x1800b1d6e  call    _guard_dispatch_icall
0x1800b1d73  nop
0x1800b1d74  mov     rcx, [rbp+57h+var_40]
0x1800b1d78  test    rcx, rcx
0x1800b1d7b  jz      short loc_1800B1D8C
0x1800b1d7d  mov     rax, [rcx]
0x1800b1d80  mov     edx, r13d
0x1800b1d83  mov     rax, [rax]
0x1800b1d86  call    _guard_dispatch_icall
0x1800b1d8b  nop
0x1800b1d8c  sub     cs:dword_18014D4FC, r13d
0x1800b1d93  jnz     short loc_1800B1DA9
0x1800b1d95  mov     cs:dword_18014D4F8, r12d
0x1800b1d9c  lea     rcx, stru_18014D4C0; SRWLock
0x1800b1da3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b1da9  mov     rcx, [rbp+57h+var_38]
0x1800b1dad  xor     rcx, rsp; StackCookie
0x1800b1db0  call    __security_check_cookie
0x1800b1db5  mov     rbx, [rsp+0C0h+arg_10]
0x1800b1dbd  add     rsp, 90h
0x1800b1dc4  pop     r15
0x1800b1dc6  pop     r14
0x1800b1dc8  pop     r13
0x1800b1dca  pop     r12
0x1800b1dcc  pop     rdi
0x1800b1dcd  pop     rsi
0x1800b1dce  pop     rbp
0x1800b1dcf  retn
0x1800b1dd0  mov     r9d, eax; char *
0x1800b1dd3  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b1dda  mov     edx, 44h ; 'D'; void *
0x1800b1ddf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1de5  mov     r9d, eax; char *
0x1800b1de8  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b1def  mov     edx, 39h ; '9'; void *
0x1800b1df4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1dfa  mov     ecx, 5; int
0x1800b1dff  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800b1e05  mov     cs:dword_18014D4FC, 7FFFFFFEh
0x1800b1e0f  mov     ecx, 6; int
0x1800b1e14  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800b1e1a  mov     r9d, eax; char *
0x1800b1e1d  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b1e24  mov     edx, 5Bh ; '['; void *
0x1800b1e29  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b1e2f  mov     r9d, eax; char *
0x1800b1e32  lea     r8, aCW1SSrcOrchest_15; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800b1e39  mov     edx, 5Ch ; '\'; void *
0x1800b1e3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```

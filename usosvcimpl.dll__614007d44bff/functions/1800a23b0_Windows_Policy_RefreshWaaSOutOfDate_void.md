# Windows::Policy::RefreshWaaSOutOfDate(void)

- ea: `0x1800a23b0`
- end: `0x1800a2b7f`
- name: `?RefreshWaaSOutOfDate@Policy@Windows@@AEAAXXZ`
- size: `1999`
- prototype: `void __fastcall(Windows::Policy *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a2f40`
- `0x1800a2f70`
- `0x1800a2f90`

## callees

- `0x1800112d0`
- `0x18001b064`
- `0x18006ea28`
- `0x1800a2320`
- `0x1800a23b0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2466`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2466`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2411`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2610`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2ac3`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2411`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2610`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800a2ac3`

## string_xrefs

- `0x1800a2b30`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x1800a2b44`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x1800a2b58`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x1800a2b6c`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Policy.cpp`
- `0x1800a272e`: `Override out of date value for quality update based on WaaS because it is a managed device.`
- `0x1800a282b`: `Override out of date value for feature update based on WaaS because it is a managed device.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::Policy::RefreshWaaSOutOfDate(Windows::Policy *this)
{
  char v2; // bl
  const char *v3; // r9
  __int64 v4; // rdi
  signed __int64 v5; // rdx
  HRESULT v6; // r14d
  __int64 *System; // rax
  char v8; // r15
  volatile signed __int32 *v9; // rdi
  __int64 *v10; // rax
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  signed __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 *v18; // rax
  _QWORD *v19; // rax
  char v20; // r14
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  int *v23; // rdx
  int v24; // eax
  __int64 *v25; // rax
  _QWORD *v26; // rax
  char v27; // r14
  volatile signed __int32 *v28; // rdi
  volatile signed __int32 *v29; // rdi
  char v30; // r8
  int v31; // ecx
  int ppv; // [rsp+20h] [rbp-C8h]
  __int128 v33; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-98h] BYREF
  volatile signed __int32 *v35; // [rsp+58h] [rbp-90h]
  int v36; // [rsp+60h] [rbp-88h] BYREF
  int v37; // [rsp+64h] [rbp-84h] BYREF
  LPVOID v38; // [rsp+68h] [rbp-80h] BYREF
  int v39; // [rsp+70h] [rbp-78h] BYREF
  __int64 v40; // [rsp+78h] [rbp-70h] BYREF
  int v41; // [rsp+80h] [rbp-68h]
  int v42; // [rsp+88h] [rbp-60h] BYREF
  char v43; // [rsp+8Ch] [rbp-5Ch]
  __int64 v44; // [rsp+90h] [rbp-58h] BYREF
  __int64 v45; // [rsp+98h] [rbp-50h] BYREF
  int v46; // [rsp+A0h] [rbp-48h]
  __int64 v47; // [rsp+A8h] [rbp-40h] BYREF
  __int64 v48; // [rsp+B0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = 0;
  LODWORD(v33) = 0;
  try
  {
    if ( Windows::Policy::DisableAllUnmanagedUpdateServicesWhenWsus(this) )
      return;
    v4 = *((_QWORD *)this + 3) + 864000000000LL;
    *(_QWORD *)&v33 = 0;
    GetSystemTimePreciseAsFileTime(&v33);
    v5 = (unsigned int)v33 + ((unsigned __int64)DWORD1(v33) << 32) - 116444736000000000LL;
    if ( v4 != v5 && v4 >= v5 )
      return;
    v38 = 0;
    v6 = CoCreateInstance(
           &GUID_098ef871_fa9f_46af_8958_c083515d7c9c,
           0,
           1u,
           &GUID_28f36eb8_3990_460a_bda9_3f06f8514de9,
           &v38);
    if ( v6 != -2147221164
      || (System = SystemInterface::Service::GetSystem(&v34),
          v2 = 1,
          LODWORD(v33) = 1,
          v8 = 1,
          !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)*System + 168LL))(
             *System,
             *(_QWORD *)*System)) )
    {
      v8 = 0;
    }
    if ( (v2 & 1) != 0 )
    {
      v9 = v35;
      if ( v35 )
      {
        if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
          if ( !_InterlockedDecrement(v9 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        }
      }
    }
    if ( v8 )
    {
      if ( v38 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
      return;
    }
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A4,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
        (const char *)(unsigned int)v6,
        ppv);
    v44 = 0;
    v37 = 0;
    v36 = 0;
    v40 = 0;
    v41 = 0;
    v10 = SystemInterface::Service::GetSystem((__int64 *)&v33);
    v11 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v10 + 48LL))(*v10, &v34);
    (*(void (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v11 + 72LL))(*v11, &v42);
    v12 = v35;
    if ( v35 )
    {
      if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v13 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    if ( v43 )
    {
      v37 = 1;
      *(_QWORD *)&v33 = 0;
      GetSystemTimePreciseAsFileTime(&v33);
      v14 = (unsigned int)v33 + ((unsigned __int64)DWORD1(v33) << 32) - 36000000000LL * (v42 + 3234576LL);
      v44 = v14 % 10000000 + 10000000 * (v14 / 10000000 + 0x2B6109100LL);
LABEL_34:
      if ( (_DWORD)v40 == 9 )
      {
        *(_QWORD *)&v33 = L"Override out of date value for quality update based on WaaS because it is a managed device.";
        *((_QWORD *)&v33 + 1) = 91;
        SystemInterface::Log<>(&v33);
        *((_BYTE *)this + 17) = 0;
      }
      else if ( v37 && !v36 )
      {
        *((_BYTE *)this + 17) = HIDWORD(v40) == 3;
      }
LABEL_39:
      v47 = 0;
      v37 = 0;
      v36 = 0;
      v45 = 0;
      v46 = 0;
      v16 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v38 + 88LL))(
              v38,
              &v47,
              &v45,
              &v37);
      if ( v16 == -2147024894 )
      {
        *(_QWORD *)&v33 = L"Waas assessor returned file not found, exiting gracefully.";
        *((_QWORD *)&v33 + 1) = 58;
        SystemInterface::Log<>(&v33);
        if ( v38 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
      }
      else
      {
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3E7,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
            (const char *)(unsigned int)v16,
            (int)&v36);
        if ( v16 != 1 )
        {
          if ( (_DWORD)v45 == 9 )
          {
            *(_QWORD *)&v33 = L"Override out of date value for feature update based on WaaS because it is a managed device.";
            *((_QWORD *)&v33 + 1) = 91;
            SystemInterface::Log<>(&v33);
            *((_BYTE *)this + 16) = 0;
          }
          else if ( v37 && !v36 )
          {
            *((_BYTE *)this + 16) = HIDWORD(v40) == 3;
          }
        }
        v48 = 0;
        v39 = 0;
        v17 = (*(__int64 (__fastcall **)(LPVOID, int *, int *, __int64 *))(*(_QWORD *)v38 + 80LL))(
                v38,
                &v36,
                &v39,
                &v48);
        if ( v17 == -2147024894 )
        {
          *(_QWORD *)&v33 = L"Waas assessor returned file not found, exiting gracefully.";
          *((_QWORD *)&v33 + 1) = 58;
          SystemInterface::Log<>(&v33);
          if ( v38 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
        }
        else
        {
          if ( v17 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x400,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
              (const char *)(unsigned int)v17,
              1);
          if ( v17 == 1 )
          {
            v36 = 0;
            v39 = 876000;
          }
          v18 = SystemInterface::Service::GetSystem((__int64 *)&v33);
          v19 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v18 + 48LL))(*v18, &v34);
          v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 144LL))(*v19);
          v21 = v35;
          if ( v35 )
          {
            if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
              if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
            }
          }
          v22 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
          if ( *((_QWORD *)&v33 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          if ( v20 )
          {
            v23 = (int *)((char *)this + 8);
            if ( !*((_BYTE *)this + 12) )
              *((_BYTE *)this + 12) = 1;
            v24 = 0;
          }
          else
          {
            v25 = SystemInterface::Service::GetSystem((__int64 *)&v33);
            v26 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v25 + 48LL))(*v25, &v34);
            v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v26 + 136LL))(*v26);
            v28 = v35;
            if ( v35 )
            {
              if ( _InterlockedExchangeAdd(v35 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
                if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
              }
            }
            v29 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
            if ( *((_QWORD *)&v33 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
                if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
              }
            }
            v23 = (int *)((char *)this + 8);
            v30 = *((_BYTE *)this + 12);
            if ( v27 )
            {
              if ( !v30 )
                *((_BYTE *)this + 12) = 1;
              v24 = 120;
            }
            else
            {
              v31 = v39;
              if ( v36 )
                v31 = -v39;
              v24 = 24 * v31;
              if ( !v30 )
                *((_BYTE *)this + 12) = 1;
            }
          }
          *v23 = v24;
          *(_QWORD *)&v33 = 0;
          GetSystemTimePreciseAsFileTime(&v33);
          *((_QWORD *)this + 3) = ((unsigned __int64)DWORD1(v33) << 32) - 116444736000000000LL + (unsigned int)v33;
          if ( v38 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
        }
      }
      return;
    }
    v15 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64 *, int *))(*(_QWORD *)v38 + 88LL))(
            v38,
            &v44,
            &v40,
            &v37);
    if ( v15 != -2147024894 )
    {
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3C5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
          (const char *)(unsigned int)v15,
          (int)&v36);
      if ( v15 == 1 )
        goto LABEL_39;
      goto LABEL_34;
    }
    *(_QWORD *)&v33 = L"Waas assessor returned file not found, exiting gracefully.";
    *((_QWORD *)&v33 + 1) = 58;
    SystemInterface::Log<>(&v33);
    if ( v38 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v38 + 16LL))(v38);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x41A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Policy.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x1800a23b0  mov     [rsp+arg_8], rbx
0x1800a23b5  mov     [rsp+arg_10], rsi
0x1800a23ba  push    rdi
0x1800a23bb  push    r12
0x1800a23bd  push    r13
0x1800a23bf  push    r14
0x1800a23c1  push    r15
0x1800a23c3  sub     rsp, 0C0h
0x1800a23ca  mov     rax, cs:__security_cookie
0x1800a23d1  xor     rax, rsp
0x1800a23d4  mov     [rsp+0E8h+var_30], rax
0x1800a23dc  mov     rsi, rcx
0x1800a23df  xor     r12d, r12d
0x1800a23e2  mov     ebx, r12d
0x1800a23e5  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x1800a23e9  call    ?DisableAllUnmanagedUpdateServicesWhenWsus@Policy@Windows@@UEAA_NXZ; Windows::Policy::DisableAllUnmanagedUpdateServicesWhenWsus(void)
0x1800a23ee  test    al, al
0x1800a23f0  jnz     loc_1800A2B00
0x1800a23f6  mov     rdi, [rsi+18h]
0x1800a23fa  mov     rcx, 0C92A69C000h
0x1800a2404  add     rdi, rcx
0x1800a2407  mov     [rsp+0E8h+var_A8], r12
0x1800a240c  lea     rcx, [rsp+0E8h+var_A8]
0x1800a2411  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800a2417  mov     eax, dword ptr [rsp+0E8h+var_A8+4]
0x1800a241b  shl     rax, 20h
0x1800a241f  mov     ecx, dword ptr [rsp+0E8h+var_A8]
0x1800a2423  mov     rdx, 0FE624E212AC18000h
0x1800a242d  add     rdx, rax
0x1800a2430  add     rdx, rcx
0x1800a2433  cmp     rdi, rdx
0x1800a2436  jz      short loc_1800A243E
0x1800a2438  jge     loc_1800A2B00
0x1800a243e  mov     [rsp+0E8h+var_80], r12
0x1800a2443  lea     rax, [rsp+0E8h+var_80]
0x1800a2448  mov     [rsp+0E8h+ppv], rax; int
0x1800a244d  lea     r9, _GUID_28f36eb8_3990_460a_bda9_3f06f8514de9; riid
0x1800a2454  mov     r13d, 1
0x1800a245a  mov     r8d, r13d; dwClsContext
0x1800a245d  xor     edx, edx; pUnkOuter
0x1800a245f  lea     rcx, _GUID_098ef871_fa9f_46af_8958_c083515d7c9c; rclsid
0x1800a2466  call    cs:__imp_CoCreateInstance
0x1800a246c  mov     r14d, eax
0x1800a246f  cmp     eax, 80040154h
0x1800a2474  jnz     short loc_1800A24A1
0x1800a2476  lea     rcx, [rsp+0E8h+var_98]
0x1800a247b  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800a2480  nop
0x1800a2481  mov     ebx, r13d
0x1800a2484  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x1800a2488  mov     rcx, [rax]
0x1800a248b  mov     rdx, [rcx]
0x1800a248e  mov     rax, [rdx+0A8h]
0x1800a2495  call    _guard_dispatch_icall
0x1800a249a  test    al, al
0x1800a249c  mov     r15b, r13b
0x1800a249f  jnz     short loc_1800A24A4
0x1800a24a1  mov     r15b, r12b
0x1800a24a4  test    r13b, bl
0x1800a24a7  jz      short loc_1800A24EB
0x1800a24a9  mov     rdi, [rsp+0E8h+var_90]
0x1800a24ae  test    rdi, rdi
0x1800a24b1  jz      short loc_1800A24EB
0x1800a24b3  or      ebx, 0FFFFFFFFh
0x1800a24b6  mov     eax, ebx
0x1800a24b8  lock xadd [rdi+8], eax
0x1800a24bd  add     eax, ebx
0x1800a24bf  jnz     short loc_1800A24EE
0x1800a24c1  mov     rax, [rdi]
0x1800a24c4  mov     rcx, rdi
0x1800a24c7  mov     rax, [rax]
0x1800a24ca  call    _guard_dispatch_icall
0x1800a24cf  mov     eax, ebx
0x1800a24d1  lock xadd [rdi+0Ch], eax
0x1800a24d6  add     eax, ebx
0x1800a24d8  jnz     short loc_1800A24EE
0x1800a24da  mov     rax, [rdi]
0x1800a24dd  mov     rcx, rdi
0x1800a24e0  mov     rax, [rax+8]
0x1800a24e4  call    _guard_dispatch_icall
0x1800a24e9  jmp     short loc_1800A24EE
0x1800a24eb  or      ebx, 0FFFFFFFFh
0x1800a24ee  test    r15b, r15b
0x1800a24f1  jz      short loc_1800A250F
0x1800a24f3  mov     rcx, [rsp+0E8h+var_80]
0x1800a24f8  test    rcx, rcx
0x1800a24fb  jz      short loc_1800A250A
0x1800a24fd  mov     rax, [rcx]
0x1800a2500  mov     rax, [rax+10h]
0x1800a2504  call    _guard_dispatch_icall
0x1800a2509  nop
0x1800a250a  jmp     loc_1800A2B00
0x1800a250f  mov     rcx, [rsp+0E8h]; this
0x1800a2517  test    r14d, r14d
0x1800a251a  js      loc_1800A2B2D
0x1800a2520  mov     [rsp+0E8h+var_58], r12
0x1800a2528  mov     [rsp+0E8h+var_84], r12d
0x1800a252d  mov     [rsp+0E8h+var_88], r12d
0x1800a2532  xor     eax, eax
0x1800a2534  mov     [rsp+0E8h+var_70], rax
0x1800a2539  mov     [rsp+0E8h+var_68], eax
0x1800a2540  lea     rcx, [rsp+0E8h+var_A8]
0x1800a2545  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x1800a254a  nop
0x1800a254b  mov     rcx, [rax]
0x1800a254e  mov     rax, [rcx]
0x1800a2551  lea     rdx, [rsp+0E8h+var_98]
0x1800a2556  mov     rax, [rax+30h]
0x1800a255a  call    _guard_dispatch_icall
0x1800a255f  nop
0x1800a2560  mov     rcx, [rax]
0x1800a2563  mov     rax, [rcx]
0x1800a2566  lea     rdx, [rsp+0E8h+var_60]
0x1800a256e  mov     rax, [rax+48h]
0x1800a2572  call    _guard_dispatch_icall
0x1800a2577  nop
0x1800a2578  mov     rdi, [rsp+0E8h+var_90]
0x1800a257d  test    rdi, rdi
0x1800a2580  jz      short loc_1800A25B6
0x1800a2582  mov     eax, ebx
0x1800a2584  lock xadd [rdi+8], eax
0x1800a2589  add     eax, ebx
0x1800a258b  jnz     short loc_1800A25B6
0x1800a258d  mov     rax, [rdi]
0x1800a2590  mov     rcx, rdi
0x1800a2593  mov     rax, [rax]
0x1800a2596  call    _guard_dispatch_icall
0x1800a259b  mov     eax, ebx
0x1800a259d  lock xadd [rdi+0Ch], eax
0x1800a25a2  add     eax, ebx
0x1800a25a4  jnz     short loc_1800A25B6
0x1800a25a6  mov     rax, [rdi]
0x1800a25a9  mov     rcx, rdi
0x1800a25ac  mov     rax, [rax+8]
0x1800a25b0  call    _guard_dispatch_icall
0x1800a25b5  nop
0x1800a25b6  mov     rdi, [rsp+0E8h+var_A0]
0x1800a25bb  test    rdi, rdi
0x1800a25be  jz      short loc_1800A25F3
0x1800a25c0  mov     eax, ebx
0x1800a25c2  lock xadd [rdi+8], eax
0x1800a25c7  add     eax, ebx
0x1800a25c9  jnz     short loc_1800A25F3
0x1800a25cb  mov     rax, [rdi]
0x1800a25ce  mov     rcx, rdi
0x1800a25d1  mov     rax, [rax]
0x1800a25d4  call    _guard_dispatch_icall
0x1800a25d9  mov     eax, ebx
0x1800a25db  lock xadd [rdi+0Ch], eax
0x1800a25e0  add     eax, ebx
0x1800a25e2  jnz     short loc_1800A25F3
0x1800a25e4  mov     rax, [rdi]
0x1800a25e7  mov     rcx, rdi
0x1800a25ea  mov     rax, [rax+8]
0x1800a25ee  call    _guard_dispatch_icall
0x1800a25f3  cmp     [rsp+0E8h+var_5C], r12b
0x1800a25fb  jz      loc_1800A2696
0x1800a2601  mov     [rsp+0E8h+var_84], r13d
0x1800a2606  mov     [rsp+0E8h+var_A8], r12
0x1800a260b  lea     rcx, [rsp+0E8h+var_A8]
0x1800a2610  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800a2616  movsxd  rax, [rsp+0E8h+var_60]
0x1800a261e  add     rax, 315B10h
0x1800a2624  mov     rcx, 861C46800h
0x1800a262e  imul    rax, rcx
0x1800a2632  mov     r8d, dword ptr [rsp+0E8h+var_A8+4]
0x1800a2637  shl     r8, 20h
0x1800a263b  sub     r8, rax
0x1800a263e  mov     eax, dword ptr [rsp+0E8h+var_A8]
0x1800a2642  add     r8, rax
0x1800a2645  mov     rax, 0D6BF94D5E57A42BDh
0x1800a264f  imul    r8
0x1800a2652  add     rdx, r8
0x1800a2655  sar     rdx, 17h
0x1800a2659  mov     rax, rdx
0x1800a265c  shr     rax, 3Fh
0x1800a2660  add     rdx, rax
0x1800a2663  imul    rax, rdx, 989680h
0x1800a266a  sub     r8, rax
0x1800a266d  mov     rax, 2B6109100h
0x1800a2677  add     rax, rdx
0x1800a267a  imul    rcx, rax, 989680h
0x1800a2681  add     rcx, r8
0x1800a2684  mov     [rsp+0E8h+var_58], rcx
0x1800a268c  mov     edi, 80070002h
0x1800a2691  jmp     loc_1800A2727
0x1800a2696  mov     rcx, [rsp+0E8h+var_80]
0x1800a269b  mov     rax, [rcx]
0x1800a269e  mov     [rsp+0E8h+var_B8], r13d
0x1800a26a3  mov     [rsp+0E8h+var_C0], r13d
0x1800a26a8  lea     rdx, [rsp+0E8h+var_88]
0x1800a26ad  mov     [rsp+0E8h+ppv], rdx; int
0x1800a26b2  lea     r9, [rsp+0E8h+var_84]
0x1800a26b7  lea     r8, [rsp+0E8h+var_70]
0x1800a26bc  lea     rdx, [rsp+0E8h+var_58]
0x1800a26c4  mov     rax, [rax+58h]
0x1800a26c8  call    _guard_dispatch_icall
0x1800a26cd  mov     edi, 80070002h
0x1800a26d2  cmp     eax, edi
0x1800a26d4  jnz     short loc_1800A2712
0x1800a26d6  lea     rax, aWaasAssessorRe; "Waas assessor returned file not found, "...
0x1800a26dd  mov     [rsp+0E8h+var_A8], rax
0x1800a26e2  mov     [rsp+0E8h+var_A0], 3Ah ; ':'
0x1800a26eb  lea     rcx, [rsp+0E8h+var_A8]
0x1800a26f0  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800a26f5  nop
0x1800a26f6  mov     rcx, [rsp+0E8h+var_80]
0x1800a26fb  test    rcx, rcx
0x1800a26fe  jz      short loc_1800A270D
0x1800a2700  mov     rax, [rcx]
0x1800a2703  mov     rax, [rax+10h]
0x1800a2707  call    _guard_dispatch_icall
0x1800a270c  nop
0x1800a270d  jmp     loc_1800A2B00
0x1800a2712  mov     rcx, [rsp+0E8h]; this
0x1800a271a  test    eax, eax
0x1800a271c  js      loc_1800A2B41
0x1800a2722  cmp     eax, r13d
0x1800a2725  jz      short loc_1800A276C
0x1800a2727  cmp     dword ptr [rsp+0E8h+var_70], 9
0x1800a272c  jnz     short loc_1800A2753
0x1800a272e  lea     rax, aOverrideOutOfD_0; "Override out of date value for quality "...
0x1800a2735  mov     [rsp+0E8h+var_A8], rax
0x1800a273a  mov     [rsp+0E8h+var_A0], 5Bh ; '['
0x1800a2743  lea     rcx, [rsp+0E8h+var_A8]
0x1800a2748  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800a274d  mov     [rsi+11h], r12b
0x1800a2751  jmp     short loc_1800A276C
0x1800a2753  cmp     [rsp+0E8h+var_84], r12d
0x1800a2758  jz      short loc_1800A276C
0x1800a275a  cmp     [rsp+0E8h+var_88], r12d
0x1800a275f  jnz     short loc_1800A276C
0x1800a2761  cmp     dword ptr [rsp+0E8h+var_70+4], 3
0x1800a2766  setz    al
0x1800a2769  mov     [rsi+11h], al
0x1800a276c  mov     [rsp+0E8h+var_40], r12
0x1800a2774  mov     [rsp+0E8h+var_84], r12d
0x1800a2779  mov     [rsp+0E8h+var_88], r12d
0x1800a277e  xor     eax, eax
0x1800a2780  mov     [rsp+0E8h+var_50], rax
0x1800a2788  mov     [rsp+0E8h+var_48], eax
0x1800a278f  mov     rcx, [rsp+0E8h+var_80]
0x1800a2794  mov     rax, [rcx]
0x1800a2797  mov     [rsp+0E8h+var_B8], r13d
0x1800a279c  mov     [rsp+0E8h+var_C0], 2
0x1800a27a4  lea     rdx, [rsp+0E8h+var_88]
0x1800a27a9  mov     [rsp+0E8h+ppv], rdx; int
0x1800a27ae  lea     r9, [rsp+0E8h+var_84]
0x1800a27b3  lea     r8, [rsp+0E8h+var_50]
0x1800a27bb  lea     rdx, [rsp+0E8h+var_40]
0x1800a27c3  mov     rax, [rax+58h]
0x1800a27c7  call    _guard_dispatch_icall
0x1800a27cc  cmp     eax, edi
0x1800a27ce  jnz     short loc_1800A280C
0x1800a27d0  lea     rax, aWaasAssessorRe; "Waas assessor returned file not found, "...
0x1800a27d7  mov     [rsp+0E8h+var_A8], rax
0x1800a27dc  mov     [rsp+0E8h+var_A0], 3Ah ; ':'
0x1800a27e5  lea     rcx, [rsp+0E8h+var_A8]
0x1800a27ea  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800a27ef  nop
0x1800a27f0  mov     rcx, [rsp+0E8h+var_80]
0x1800a27f5  test    rcx, rcx
0x1800a27f8  jz      short loc_1800A2807
0x1800a27fa  mov     rax, [rcx]
0x1800a27fd  mov     rax, [rax+10h]
0x1800a2801  call    _guard_dispatch_icall
0x1800a2806  nop
0x1800a2807  jmp     loc_1800A2B00
0x1800a280c  mov     rcx, [rsp+0E8h]; this
0x1800a2814  test    eax, eax
0x1800a2816  js      loc_1800A2B55
0x1800a281c  cmp     eax, r13d
0x1800a281f  jz      short loc_1800A2869
0x1800a2821  cmp     dword ptr [rsp+0E8h+var_50], 9
0x1800a2829  jnz     short loc_1800A2850
0x1800a282b  lea     rax, aOverrideOutOfD; "Override out of date value for feature "...
0x1800a2832  mov     [rsp+0E8h+var_A8], rax
0x1800a2837  mov     [rsp+0E8h+var_A0], 5Bh ; '['
0x1800a2840  lea     rcx, [rsp+0E8h+var_A8]
0x1800a2845  call    ??$Log@$$V@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; SystemInterface::Log<>(std::wstring_view)
0x1800a284a  mov     [rsi+10h], r12b
0x1800a284e  jmp     short loc_1800A2869
0x1800a2850  cmp     [rsp+0E8h+var_84], r12d
0x1800a2855  jz      short loc_1800A2869
0x1800a2857  cmp     [rsp+0E8h+var_88], r12d
0x1800a285c  jnz     short loc_1800A2869
0x1800a285e  cmp     dword ptr [rsp+0E8h+var_70+4], 3
0x1800a2863  setz    al
0x1800a2866  mov     [rsi+10h], al
0x1800a2869  mov     [rsp+0E8h+var_38], r12
0x1800a2871  mov     [rsp+0E8h+var_78], r12d
0x1800a2876  mov     rcx, [rsp+0E8h+var_80]
0x1800a287b  mov     rax, [rcx]
0x1800a287e  mov     dword ptr [rsp+0E8h+ppv], r13d; int
0x1800a2883  lea     r9, [rsp+0E8h+var_38]
0x1800a288b  lea     r8, [rsp+0E8h+var_78]
0x1800a2890  lea     rdx, [rsp+0E8h+var_88]
0x1800a2895  mov     rax, [rax+50h]
0x1800a2899  call    _guard_dispatch_icall
0x1800a289e  cmp     eax, edi
  ... truncated ...
```

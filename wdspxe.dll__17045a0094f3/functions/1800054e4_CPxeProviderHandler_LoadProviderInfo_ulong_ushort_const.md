# CPxeProviderHandler::LoadProviderInfo(ulong,ushort const *)

- ea: `0x1800054e4`
- end: `0x180005858`
- name: `?LoadProviderInfo@CPxeProviderHandler@@AEAAKKPEBG@Z`
- size: `884`
- prototype: `unsigned int(CPxeProviderHandler *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005860`

## callees

- `0x180001ad8`
- `0x1800054e4`
- `0x1800070c8`
- `0x180013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800057ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057c7`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057da`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800057f6`
- `KERNEL32!EnterCriticalSection` at `0x180005714`
- `KERNEL32!EnterCriticalSection` at `0x180005714`
- `KERNEL32!LeaveCriticalSection` at `0x180005797`
- `KERNEL32!LeaveCriticalSection` at `0x180005797`
- `ADVAPI32!RegCloseKey` at `0x180005575`
- `ADVAPI32!RegCloseKey` at `0x18000580f`
- `ADVAPI32!RegCloseKey` at `0x180005828`
- `ADVAPI32!RegCloseKey` at `0x180005575`
- `ADVAPI32!RegCloseKey` at `0x18000580f`
- `ADVAPI32!RegCloseKey` at `0x180005828`
- `ADVAPI32!RegOpenKeyExW` at `0x180005545`
- `ADVAPI32!RegOpenKeyExW` at `0x180005599`
- `ADVAPI32!RegOpenKeyExW` at `0x180005545`
- `ADVAPI32!RegOpenKeyExW` at `0x180005599`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180005651`
- `WdsCommonLib!?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z` at `0x180005651`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800056d5`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800056f6`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800056d5`
- `WdsCommonLib!?DuplicateStringW@@YAKPEBGPEAPEAG@Z` at `0x1800056f6`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800055f9`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180005767`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x1800055f9`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180005767`
- `WdsCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180005619`
- `WdsCommonLib!?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z` at `0x180005619`

## string_xrefs

- `0x180005522`: `System\CurrentControlSet\Services\WDSServer\Providers\WDSPXE\Providers`
- `0x18000560e`: `ProviderDll`

## pseudocode

```c
__int64 __fastcall CPxeProviderHandler::LoadProviderInfo(CPxeProviderHandler *this, int a2, const unsigned __int16 *a3)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int ValueExpSzOrSz; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edx
  unsigned int ValueDword; // eax
  unsigned __int16 **v18; // rax
  unsigned __int16 **v19; // rbx
  unsigned __int16 *v20; // rcx
  unsigned __int16 *v21; // rcx
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  unsigned __int16 *v24; // [rsp+68h] [rbp-18h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-10h] BYREF
  unsigned int v26; // [rsp+C8h] [rbp+48h] BYREF

  v24 = 0;
  v26 = 0;
  phkResult = 0;
  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WDSServer\\Providers\\WDSPXE\\Providers",
         0,
         0x20119u,
         &phkResult);
  v9 = ElValidateWin32_2(v6, v7, v8, 219);
  if ( !v9 )
  {
    v10 = RegOpenKeyExW(phkResult, a3, 0, 0x20119u, &hKey);
    v9 = ElValidateWin32_2(v10, v11, v12, 228);
    if ( v9 )
    {
      CEventLog::Log((CEventLog *)qword_18001CC40, 0xC1070100, 4);
      goto LABEL_26;
    }
    ValueExpSzOrSz = CRegKey::GetValueExpSzOrSz((CRegKey *)&hKey, L"ProviderDll", &v24);
    v9 = ElValidateWin32_2(ValueExpSzOrSz, v14, v15, 245);
    if ( v9 )
    {
      v16 = -1056505599;
LABEL_17:
      CEventLog::Log((CEventLog *)qword_18001CC40, v16, 2);
      goto LABEL_26;
    }
    ValueDword = CRegKey::GetValueDword((CRegKey *)&hKey, L"IsCritical", &v26);
    v9 = ValueDword;
    if ( ValueDword == 2 )
    {
      if ( g_ErrLibTraceFunctionEx )
        g_ErrLibTraceFunctionEx(0x20000u, L"PXE provider [%s]: no %s reg value, assuming FALSE", a3, L"IsCritical");
      v26 = 0;
    }
    else if ( ValueDword )
    {
      v16 = -1056505598;
      goto LABEL_17;
    }
    v18 = (unsigned __int16 **)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v19 = v18;
    if ( v18 )
    {
      v18[4] = 0;
      v18[5] = 0;
      *(_OWORD *)v18 = 0;
      *((_OWORD *)v18 + 1) = 0;
      *(_DWORD *)v18 = 32;
      *((_DWORD *)v18 + 6) = v26;
      v9 = DuplicateStringW(a3, v18 + 1);
      if ( v9 || (v9 = DuplicateStringW(v24, v19 + 2)) != 0 )
      {
        v20 = v19[1];
        if ( v20 )
        {
          operator delete(v20);
          v19[1] = 0;
        }
        v21 = v19[2];
        if ( v21 )
        {
          operator delete(v21);
          v19[2] = 0;
        }
        operator delete(v19);
      }
      else
      {
        *((_DWORD *)v19 + 7) = a2;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
        if ( *((_QWORD *)this + 9) )
        {
          v19[4] = 0;
          v19[5] = (unsigned __int16 *)*((_QWORD *)this + 10);
          *(_QWORD *)(*((_QWORD *)this + 10) + 32LL) = v19;
          *((_QWORD *)this + 10) = v19;
        }
        else
        {
          *((_QWORD *)this + 10) = v19;
          *((_QWORD *)this + 9) = v19;
          v19[4] = 0;
          v19[5] = 0;
        }
        ++*((_DWORD *)this + 32);
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      }
    }
    else
    {
      v9 = 8;
    }
  }
LABEL_26:
  if ( v24 )
  {
    operator delete(v24);
    v24 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
  return v9;
}

```

## disassembly

```asm
0x1800054e4  mov     [rsp-28h+arg_0], rbx
0x1800054e9  mov     [rsp-28h+arg_8], rsi
0x1800054ee  mov     [rsp-28h+arg_10], rdi
0x1800054f3  push    rbp
0x1800054f4  push    r12
0x1800054f6  push    r13
0x1800054f8  push    r14
0x1800054fa  push    r15
0x1800054fc  mov     rbp, rsp
0x1800054ff  sub     rsp, 80h
0x180005506  xor     r12d, r12d
0x180005509  lea     rax, [rbp+var_10]
0x18000550d  mov     r14, r8
0x180005510  mov     [rbp+var_18], r12
0x180005514  mov     r15d, edx
0x180005517  mov     [rbp+arg_18], r12d
0x18000551b  mov     rsi, rcx
0x18000551e  mov     [rbp+var_10], r12
0x180005522  lea     r13, aSystemCurrentc; "System\\CurrentControlSet\\Services\\WD"...
0x180005529  mov     [rbp+hKey], r12
0x18000552d  mov     rdx, r13; lpSubKey
0x180005530  mov     [rsp+80h+phkResult], rax; phkResult
0x180005535  mov     r9d, 20119h; samDesired
0x18000553b  xor     r8d, r8d; ulOptions
0x18000553e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180005545  call    cs:__imp_RegOpenKeyExW
0x18000554c  nop     dword ptr [rax+rax+00h]
0x180005551  mov     ecx, eax
0x180005553  mov     r9d, 0DBh
0x180005559  call    ElValidateWin32_2
0x18000555e  mov     edi, eax
0x180005560  test    eax, eax
0x180005562  jnz     loc_1800057ED
0x180005568  mov     rcx, [rbp+hKey]; hKey
0x18000556c  mov     rbx, [rbp+var_10]
0x180005570  test    rcx, rcx
0x180005573  jz      short loc_180005581
0x180005575  call    cs:__imp_RegCloseKey
0x18000557c  nop     dword ptr [rax+rax+00h]
0x180005581  lea     rax, [rbp+hKey]
0x180005585  mov     r9d, 20119h; samDesired
0x18000558b  xor     r8d, r8d; ulOptions
0x18000558e  mov     [rsp+80h+phkResult], rax; phkResult
0x180005593  mov     rdx, r14; lpSubKey
0x180005596  mov     rcx, rbx; hKey
0x180005599  call    cs:__imp_RegOpenKeyExW
0x1800055a0  nop     dword ptr [rax+rax+00h]
0x1800055a5  mov     ecx, eax
0x1800055a7  mov     r9d, 0E4h
0x1800055ad  call    ElValidateWin32_2
0x1800055b2  mov     edi, eax
0x1800055b4  test    eax, eax
0x1800055b6  jz      short loc_18000560A
0x1800055b8  mov     [rsp+80h+var_30], eax
0x1800055bc  lea     rcx, qword_18001CC40
0x1800055c3  mov     [rsp+80h+var_38], 5
0x1800055cb  mov     r9d, 1
0x1800055d1  mov     [rsp+80h+var_40], r14
0x1800055d6  mov     edx, 0C1070100h
0x1800055db  mov     [rsp+80h+var_48], 1
0x1800055e3  mov     [rsp+80h+var_50], r14
0x1800055e8  mov     [rsp+80h+var_58], 1
0x1800055f0  lea     r8d, [r9+3]
0x1800055f4  mov     [rsp+80h+phkResult], r13
0x1800055f9  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180005600  nop     dword ptr [rax+rax+00h]
0x180005605  jmp     loc_1800057ED
0x18000560a  lea     r8, [rbp+var_18]
0x18000560e  lea     rdx, aProviderdll; "ProviderDll"
0x180005615  lea     rcx, [rbp+hKey]
0x180005619  call    cs:__imp_?GetValueExpSzOrSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueExpSzOrSz(ushort const *,ushort * *)
0x180005620  nop     dword ptr [rax+rax+00h]
0x180005625  mov     ecx, eax
0x180005627  mov     r9d, 0F5h
0x18000562d  call    ElValidateWin32_2
0x180005632  mov     edi, eax
0x180005634  test    eax, eax
0x180005636  jz      short loc_180005642
0x180005638  mov     edx, 0C1070101h
0x18000563d  jmp     loc_180005745
0x180005642  lea     r8, [rbp+arg_18]
0x180005646  lea     rdx, aIscritical; "IsCritical"
0x18000564d  lea     rcx, [rbp+hKey]
0x180005651  call    cs:__imp_?GetValueDword@CRegKey@@QEAAKPEBGPEAK@Z; CRegKey::GetValueDword(ushort const *,ulong *)
0x180005658  nop     dword ptr [rax+rax+00h]
0x18000565d  mov     edi, eax
0x18000565f  cmp     eax, 2
0x180005662  jnz     loc_180005738
0x180005668  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x18000566f  test    rax, rax
0x180005672  jz      short loc_18000568F
0x180005674  lea     r9, aIscritical; "IsCritical"
0x18000567b  mov     r8, r14
0x18000567e  lea     rdx, aPxeProviderSNo; "PXE provider [%s]: no %s reg value, ass"...
0x180005685  mov     ecx, 20000h
0x18000568a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568f  mov     [rbp+arg_18], r12d
0x180005693  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000569a  mov     ecx, 30h ; '0'; unsigned __int64
0x18000569f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800056a4  mov     rbx, rax
0x1800056a7  test    rax, rax
0x1800056aa  jz      loc_1800057E8
0x1800056b0  mov     [rax+20h], r12
0x1800056b4  lea     rdx, [rax+8]
0x1800056b8  mov     [rax+28h], r12
0x1800056bc  xorps   xmm0, xmm0
0x1800056bf  movups  xmmword ptr [rax], xmm0
0x1800056c2  movups  xmmword ptr [rax+10h], xmm0
0x1800056c6  mov     dword ptr [rax], 20h ; ' '
0x1800056cc  mov     ecx, [rbp+arg_18]
0x1800056cf  mov     [rax+18h], ecx
0x1800056d2  mov     rcx, r14
0x1800056d5  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800056dc  nop     dword ptr [rax+rax+00h]
0x1800056e1  mov     edi, eax
0x1800056e3  mov     r14, rbx
0x1800056e6  test    eax, eax
0x1800056e8  jnz     loc_1800057A5
0x1800056ee  mov     rcx, [rbp+var_18]
0x1800056f2  lea     rdx, [rbx+10h]
0x1800056f6  call    cs:__imp_?DuplicateStringW@@YAKPEBGPEAPEAG@Z; DuplicateStringW(ushort const *,ushort * *)
0x1800056fd  nop     dword ptr [rax+rax+00h]
0x180005702  mov     edi, eax
0x180005704  test    eax, eax
0x180005706  jnz     loc_1800057A5
0x18000570c  lea     rcx, [rsi+58h]; lpCriticalSection
0x180005710  mov     [rbx+1Ch], r15d
0x180005714  call    cs:__imp_EnterCriticalSection
0x18000571b  nop     dword ptr [rax+rax+00h]
0x180005720  cmp     [rsi+48h], r12
0x180005724  jnz     short loc_180005775
0x180005726  mov     [rsi+50h], rbx
0x18000572a  mov     [rsi+48h], rbx
0x18000572e  mov     [rbx+20h], r12
0x180005732  mov     [rbx+28h], r12
0x180005736  jmp     short loc_18000578D
0x180005738  test    eax, eax
0x18000573a  jz      loc_180005693
0x180005740  mov     edx, 0C1070102h
0x180005745  mov     dword ptr [rsp+80h+var_50], eax
0x180005749  lea     rcx, qword_18001CC40
0x180005750  mov     r9d, 1
0x180005756  mov     [rsp+80h+var_58], 5
0x18000575e  mov     [rsp+80h+phkResult], r14
0x180005763  lea     r8d, [r9+1]
0x180005767  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000576e  nop     dword ptr [rax+rax+00h]
0x180005773  jmp     short loc_1800057ED
0x180005775  mov     [rbx+20h], r12
0x180005779  mov     rax, [rsi+50h]
0x18000577d  mov     [rbx+28h], rax
0x180005781  mov     rax, [rsi+50h]
0x180005785  mov     [rax+20h], rbx
0x180005789  mov     [rsi+50h], rbx
0x18000578d  inc     dword ptr [rsi+80h]
0x180005793  lea     rcx, [rsi+58h]; lpCriticalSection
0x180005797  call    cs:__imp_LeaveCriticalSection
0x18000579e  nop     dword ptr [rax+rax+00h]
0x1800057a3  jmp     short loc_1800057ED
0x1800057a5  mov     rcx, [r14+8]
0x1800057a9  test    rcx, rcx
0x1800057ac  jz      short loc_1800057BE
0x1800057ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057b5  nop     dword ptr [rax+rax+00h]
0x1800057ba  mov     [r14+8], r12
0x1800057be  mov     rcx, [r14+10h]
0x1800057c2  test    rcx, rcx
0x1800057c5  jz      short loc_1800057D7
0x1800057c7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057ce  nop     dword ptr [rax+rax+00h]
0x1800057d3  mov     [r14+10h], r12
0x1800057d7  mov     rcx, r14
0x1800057da  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057e1  nop     dword ptr [rax+rax+00h]
0x1800057e6  jmp     short loc_1800057ED
0x1800057e8  mov     edi, 8
0x1800057ed  mov     rcx, [rbp+var_18]
0x1800057f1  test    rcx, rcx
0x1800057f4  jz      short loc_180005806
0x1800057f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800057fd  nop     dword ptr [rax+rax+00h]
0x180005802  mov     [rbp+var_18], r12
0x180005806  mov     rcx, [rbp+hKey]; hKey
0x18000580a  test    rcx, rcx
0x18000580d  jz      short loc_18000581F
0x18000580f  call    cs:__imp_RegCloseKey
0x180005816  nop     dword ptr [rax+rax+00h]
0x18000581b  mov     [rbp+hKey], r12
0x18000581f  mov     rcx, [rbp+var_10]; hKey
0x180005823  test    rcx, rcx
0x180005826  jz      short loc_180005834
0x180005828  call    cs:__imp_RegCloseKey
0x18000582f  nop     dword ptr [rax+rax+00h]
0x180005834  lea     r11, [rsp+80h+var_s0]
0x18000583c  mov     eax, edi
0x18000583e  mov     rbx, [r11+30h]
0x180005842  mov     rsi, [r11+38h]
0x180005846  mov     rdi, [r11+40h]
0x18000584a  mov     rsp, r11
0x18000584d  pop     r15
0x18000584f  pop     r14
0x180005851  pop     r13
0x180005853  pop     r12
0x180005855  pop     rbp
0x180005856  retn
```

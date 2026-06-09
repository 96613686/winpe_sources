# DllGetClassObject

- ea: `0x18001b660`
- end: `0x18001b937`
- name: `DllGetClassObject`
- size: `727`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000795c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x1800139a4`
- `0x18001b660`
- `0x1800200a4`
- `0x180096010`

## string_xrefs

- `0x18001b6b7`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\wpnprvsrc.cpp`
- `0x18001b7b0`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\wpnprvsrc.cpp`
- `0x18001b83e`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\wpnprvsrc.cpp`
- `0x18001b8bf`: `onecoreuap\base\diagnosis\platform\notifications\prov\dll\wpnprvsrc.cpp`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rax
  ConnectionProviderFactoryImpl *v11; // rax
  ConnectionProviderFactoryImpl *v12; // rax
  __int64 v13; // rax
  NcbBackgroundTaskFactoryImpl *v14; // rax
  ConnectionProviderFactoryImpl *v15; // rdi
  int v16; // eax
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids);
  }
  if ( !ppv )
  {
    v6 = -2147024809;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\wpnprvsrc.cpp",
      (const char *)0x80070057LL,
      v18);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v6;
    if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_47;
    v8 = 15;
    v9 = 2147942487LL;
    goto LABEL_45;
  }
  *ppv = 0;
  v10 = *(_QWORD *)&CLSID_WindowsPushNotificationConnectionProvider.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_WindowsPushNotificationConnectionProvider.Data1 == *(_QWORD *)&rclsid->Data1 )
    v10 = *(_QWORD *)CLSID_WindowsPushNotificationConnectionProvider.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v10 )
  {
    v11 = (ConnectionProviderFactoryImpl *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
    {
      v12 = ConnectionProviderFactoryImpl::ConnectionProviderFactoryImpl(v11);
LABEL_19:
      v15 = v12;
      goto LABEL_21;
    }
    goto LABEL_20;
  }
  v13 = *(_QWORD *)&CLSID_NcbBackgroundTask.Data1 - *(_QWORD *)&rclsid->Data1;
  if ( *(_QWORD *)&CLSID_NcbBackgroundTask.Data1 == *(_QWORD *)&rclsid->Data1 )
    v13 = *(_QWORD *)CLSID_NcbBackgroundTask.Data4 - *(_QWORD *)rclsid->Data4;
  if ( !v13 )
  {
    v14 = (NcbBackgroundTaskFactoryImpl *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v14 )
    {
      v12 = NcbBackgroundTaskFactoryImpl::NcbBackgroundTaskFactoryImpl(v14);
      goto LABEL_19;
    }
LABEL_20:
    v15 = 0;
LABEL_21:
    if ( v15 )
    {
      v16 = (**(__int64 (__fastcall ***)(ConnectionProviderFactoryImpl *, const IID *const, LPVOID *))v15)(
              v15,
              riid,
              ppv);
      v6 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids,
            (unsigned int)v16);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCD,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\wpnprvsrc.cpp",
          (const char *)v6,
          v18);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids, v6);
      }
      (*(void (__fastcall **)(ConnectionProviderFactoryImpl *))(*(_QWORD *)v15 + 16LL))(v15);
      goto LABEL_46;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids, 0);
    }
    v6 = -2147024882;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\wpnprvsrc.cpp",
      (const char *)0x8007000ELL,
      v18);
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 19;
        v9 = 2147942414LL;
LABEL_45:
        WPP_SF_d(v7[2], v8, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids, v9);
LABEL_46:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    return v6;
  }
  v6 = -2147221231;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids, 2147746065LL);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xC2,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\dll\\wpnprvsrc.cpp",
    (const char *)0x80040111LL,
    v18);
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v8 = 17;
      v9 = 2147746065LL;
      goto LABEL_45;
    }
LABEL_47:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      WPP_SF_d(v7[2], 22, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x18001b660  push    rbx
0x18001b662  push    rbp
0x18001b663  push    rsi
0x18001b664  push    rdi
0x18001b665  push    r14
0x18001b667  push    r15
0x18001b669  sub     rsp, 28h
0x18001b66d  mov     rsi, r8
0x18001b670  mov     rbp, rdx
0x18001b673  mov     rbx, rcx
0x18001b676  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b67d  lea     r14, WPP_GLOBAL_Control
0x18001b684  lea     r15, WPP_1e65670bf05831ad92526e2cbbcbbb18_Traceguids
0x18001b68b  cmp     rcx, r14
0x18001b68e  jz      short loc_18001B6AD
0x18001b690  test    byte ptr [rcx+1Ch], 1
0x18001b694  jz      short loc_18001B6AD
0x18001b696  cmp     byte ptr [rcx+19h], 6
0x18001b69a  jb      short loc_18001B6AD
0x18001b69c  mov     rcx, [rcx+10h]
0x18001b6a0  mov     edx, 0Eh
0x18001b6a5  mov     r8, r15
0x18001b6a8  call    WPP_SF_
0x18001b6ad  test    rsi, rsi
0x18001b6b0  jnz     short loc_18001B6F8
0x18001b6b2  mov     rcx, [rsp+58h]; this
0x18001b6b7  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b6be  mov     ebx, 80070057h
0x18001b6c3  mov     edx, 0B2h; void *
0x18001b6c8  mov     r9d, ebx; char *
0x18001b6cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6d7  cmp     rcx, r14
0x18001b6da  jz      loc_18001B928
0x18001b6e0  test    byte ptr [rcx+1Ch], 80h
0x18001b6e4  jz      loc_18001B903
0x18001b6ea  lea     edx, [rsi+0Fh]
0x18001b6ed  mov     r9d, 80070057h
0x18001b6f3  jmp     loc_18001B8F0
0x18001b6f8  mov     qword ptr [rsi], 0
0x18001b6ff  mov     rax, qword ptr cs:CLSID_WindowsPushNotificationConnectionProvider.Data1
0x18001b706  sub     rax, [rbx]
0x18001b709  jnz     short loc_18001B716
0x18001b70b  mov     rax, qword ptr cs:CLSID_WindowsPushNotificationConnectionProvider.Data4
0x18001b712  sub     rax, [rbx+8]
0x18001b716  test    rax, rax
0x18001b719  jnz     short loc_18001B739
0x18001b71b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b722  lea     ecx, [rax+10h]; unsigned __int64
0x18001b725  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b72a  test    rax, rax
0x18001b72d  jz      short loc_18001B77A
0x18001b72f  mov     rcx, rax; this
0x18001b732  call    ??0ConnectionProviderFactoryImpl@@QEAA@XZ; ConnectionProviderFactoryImpl::ConnectionProviderFactoryImpl(void)
0x18001b737  jmp     short loc_18001B775
0x18001b739  mov     rax, qword ptr cs:CLSID_NcbBackgroundTask.Data1
0x18001b740  sub     rax, [rbx]
0x18001b743  jnz     short loc_18001B750
0x18001b745  mov     rax, qword ptr cs:CLSID_NcbBackgroundTask.Data4
0x18001b74c  sub     rax, [rbx+8]
0x18001b750  test    rax, rax
0x18001b753  jnz     loc_18001B889
0x18001b759  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b760  lea     ecx, [rax+10h]; unsigned __int64
0x18001b763  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b768  test    rax, rax
0x18001b76b  jz      short loc_18001B77A
0x18001b76d  mov     rcx, rax; this
0x18001b770  call    ??0NcbBackgroundTaskFactoryImpl@@QEAA@XZ; NcbBackgroundTaskFactoryImpl::NcbBackgroundTaskFactoryImpl(void)
0x18001b775  mov     rdi, rax
0x18001b778  jmp     short loc_18001B77C
0x18001b77a  xor     edi, edi
0x18001b77c  test    rdi, rdi
0x18001b77f  jnz     short loc_18001B7F3
0x18001b781  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b788  cmp     rcx, r14
0x18001b78b  jz      short loc_18001B7AB
0x18001b78d  test    byte ptr [rcx+1Ch], 1
0x18001b791  jz      short loc_18001B7AB
0x18001b793  cmp     byte ptr [rcx+19h], 2
0x18001b797  jb      short loc_18001B7AB
0x18001b799  mov     rcx, [rcx+10h]
0x18001b79d  lea     edx, [rdi+12h]
0x18001b7a0  xor     r9d, r9d
0x18001b7a3  mov     r8, r15
0x18001b7a6  call    WPP_SF_d
0x18001b7ab  mov     rcx, [rsp+58h]; this
0x18001b7b0  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b7b7  mov     ebx, 8007000Eh
0x18001b7bc  mov     edx, 0C9h; void *
0x18001b7c1  mov     r9d, ebx; char *
0x18001b7c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7d0  cmp     rcx, r14
0x18001b7d3  jz      loc_18001B928
0x18001b7d9  test    byte ptr [rcx+1Ch], 80h
0x18001b7dd  jz      loc_18001B903
0x18001b7e3  mov     edx, 13h
0x18001b7e8  mov     r9d, 8007000Eh
0x18001b7ee  jmp     loc_18001B8F0
0x18001b7f3  mov     rax, [rdi]
0x18001b7f6  mov     r8, rsi
0x18001b7f9  mov     rdx, rbp
0x18001b7fc  mov     rcx, rdi
0x18001b7ff  mov     rax, [rax]
0x18001b802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b807  mov     ebx, eax
0x18001b809  test    eax, eax
0x18001b80b  jns     short loc_18001B878
0x18001b80d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b814  cmp     rcx, r14
0x18001b817  jz      short loc_18001B839
0x18001b819  test    byte ptr [rcx+1Ch], 1
0x18001b81d  jz      short loc_18001B839
0x18001b81f  cmp     byte ptr [rcx+19h], 2
0x18001b823  jb      short loc_18001B839
0x18001b825  mov     rcx, [rcx+10h]
0x18001b829  mov     edx, 14h
0x18001b82e  mov     r9d, eax
0x18001b831  mov     r8, r15
0x18001b834  call    WPP_SF_d
0x18001b839  mov     rcx, [rsp+58h]; this
0x18001b83e  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b845  mov     r9d, ebx; char *
0x18001b848  mov     edx, 0CDh; void *
0x18001b84d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b852  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b859  cmp     rcx, r14
0x18001b85c  jz      short loc_18001B878
0x18001b85e  test    byte ptr [rcx+1Ch], 80h
0x18001b862  jz      short loc_18001B878
0x18001b864  mov     rcx, [rcx+10h]
0x18001b868  mov     edx, 15h
0x18001b86d  mov     r9d, ebx
0x18001b870  mov     r8, r15
0x18001b873  call    WPP_SF_d
0x18001b878  mov     rax, [rdi]
0x18001b87b  mov     rcx, rdi
0x18001b87e  mov     rax, [rax+10h]
0x18001b882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b887  jmp     short loc_18001B8FC
0x18001b889  mov     ebx, 80040111h
0x18001b88e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b895  cmp     rcx, r14
0x18001b898  jz      short loc_18001B8BA
0x18001b89a  test    byte ptr [rcx+1Ch], 1
0x18001b89e  jz      short loc_18001B8BA
0x18001b8a0  cmp     byte ptr [rcx+19h], 2
0x18001b8a4  jb      short loc_18001B8BA
0x18001b8a6  mov     rcx, [rcx+10h]
0x18001b8aa  mov     edx, 10h
0x18001b8af  mov     r9d, ebx
0x18001b8b2  mov     r8, r15
0x18001b8b5  call    WPP_SF_d
0x18001b8ba  mov     rcx, [rsp+58h]; this
0x18001b8bf  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001b8c6  mov     r9d, ebx; char *
0x18001b8c9  mov     edx, 0C2h; void *
0x18001b8ce  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8da  cmp     rcx, r14
0x18001b8dd  jz      short loc_18001B928
0x18001b8df  test    byte ptr [rcx+1Ch], 80h
0x18001b8e3  jz      short loc_18001B903
0x18001b8e5  mov     edx, 11h
0x18001b8ea  mov     r9d, 80040111h
0x18001b8f0  mov     rcx, [rcx+10h]
0x18001b8f4  mov     r8, r15
0x18001b8f7  call    WPP_SF_d
0x18001b8fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b903  cmp     rcx, r14
0x18001b906  jz      short loc_18001B928
0x18001b908  test    byte ptr [rcx+1Ch], 1
0x18001b90c  jz      short loc_18001B928
0x18001b90e  cmp     byte ptr [rcx+19h], 6
0x18001b912  jb      short loc_18001B928
0x18001b914  mov     rcx, [rcx+10h]
0x18001b918  mov     edx, 16h
0x18001b91d  mov     r9d, ebx
0x18001b920  mov     r8, r15
0x18001b923  call    WPP_SF_d
0x18001b928  mov     eax, ebx
0x18001b92a  add     rsp, 28h
0x18001b92e  pop     r15
0x18001b930  pop     r14
0x18001b932  pop     rdi
0x18001b933  pop     rsi
0x18001b934  pop     rbp
0x18001b935  pop     rbx
0x18001b936  retn
```

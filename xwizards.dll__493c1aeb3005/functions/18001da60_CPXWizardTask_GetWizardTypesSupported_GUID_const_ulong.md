# CPXWizardTask::GetWizardTypesSupported(_GUID * const,ulong *)

- ea: `0x18001da60`
- end: `0x18001ddbc`
- name: `?GetWizardTypesSupported@CPXWizardTask@@UEAAJQEAU_GUID@@PEAK@Z`
- size: `860`
- prototype: `__int64 __fastcall(CPXWizardTask *__hidden this, struct _GUID *const Buf1, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004370`
- `0x18000ae04`
- `0x18001da60`
- `0x18001e0b8`
- `0x1800329f6`
- `0x180032a02`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dbc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dc69`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dbc5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dc69`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001db27`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001db3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001db27`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18001db3e`

## pseudocode

```c
__int64 __fastcall CPXWizardTask::GetWizardTypesSupported(CPXWizardTask *this, unsigned __int64 Buf1, unsigned int *a3)
{
  int v3; // r15d
  const IID *v5; // rsi
  unsigned int LastErrorHRESULT; // ebx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v11; // r13d
  int v12; // ebx
  LPVOID v13; // rcx
  __int64 v14; // r12
  CPXWizardTask *v15; // rbx
  __int64 v16; // r14
  __int64 v17; // rcx
  __int64 v18; // rdx
  int v19; // eax
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v21; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int *v22; // [rsp+40h] [rbp-C0h]
  __int128 v23; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  v22 = a3;
  v5 = (const IID *)Buf1;
  if ( a3 )
  {
    if ( Buf1 )
      v5 = (const IID *)(-(__int64)(memcmp_0((const void *)Buf1, &GUID_NULL, 0x10u) != 0) & Buf1);
    *a3 = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      VersionInformation.dwOSVersionInfoSize = 276;
      if ( !GetVersionExW(&VersionInformation) )
      {
        LastErrorHRESULT = GetLastErrorHRESULT();
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
          return LastErrorHRESULT;
        v10 = 39;
LABEL_47:
        WPP_SF_d(v9[2], v10, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, LastErrorHRESULT);
        return LastErrorHRESULT;
      }
    }
    v11 = 0;
    if ( VersionInformation.dwPlatformId < 2
      || VersionInformation.dwPlatformId == 2 && VersionInformation.dwMajorVersion <= 6 )
    {
      v11 = 1;
    }
    if ( v5 )
    {
      ppv = 0;
      LastErrorHRESULT = CoCreateInstance(v5, 0, 0x401u, &IID_IXWizardTaskEvent, &ppv);
      if ( (LastErrorHRESULT & 0x80000000) != 0 )
      {
        if ( LastErrorHRESULT != -2147467262 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            return LastErrorHRESULT;
          v10 = 41;
          goto LABEL_47;
        }
        v21 = 0;
        LastErrorHRESULT = CoCreateInstance(v5, 0, 0x401u, &IID_IXWizardPageEvent, &v21);
        if ( (LastErrorHRESULT & 0x80000000) != 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            return LastErrorHRESULT;
          v10 = 40;
          goto LABEL_47;
        }
        v13 = v21;
        *a3 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      }
      else
      {
        v12 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 96LL))(ppv, a3);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( v12 )
          *a3 = 0;
      }
    }
    LODWORD(ppv) = CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(this);
    LastErrorHRESULT = (unsigned int)ppv;
    if ( (int)ppv >= 0 )
    {
      LODWORD(v14) = 0;
      v15 = this;
      do
      {
        v16 = 4LL * (unsigned int)v14;
        if ( !v11 || *(int *)((char *)qword_18003D0A0 + v16) <= 1024 )
        {
          v17 = *((_QWORD *)v15 + 12);
          v18 = *(unsigned int *)((char *)qword_18003D0A0 + v16);
          v23 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, __int128 *, _QWORD))(*(_QWORD *)v17 + 88LL))(v17, v18, &v23, 0) >= 0 )
            v3 |= *(_DWORD *)((char *)qword_18003D0A0 + v16);
        }
        v14 = (unsigned int)(v14 + 1);
      }
      while ( *((_DWORD *)qword_18003D0A0 + v14) );
      LastErrorHRESULT = (unsigned int)ppv;
      if ( v5 && *v22 )
        v19 = v3 & *v22;
      else
        v19 = v3;
      *v22 = v19;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return LastErrorHRESULT;
      v10 = 43;
    }
    else
    {
      *a3 = 0;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        return LastErrorHRESULT;
      v10 = 42;
    }
    goto LABEL_47;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids, 2147942487LL);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18001da60  mov     [rsp-8+arg_18], rbx
0x18001da65  push    rbp
0x18001da66  push    rsi
0x18001da67  push    rdi
0x18001da68  push    r12
0x18001da6a  push    r13
0x18001da6c  push    r14
0x18001da6e  push    r15
0x18001da70  lea     rbp, [rsp-90h]
0x18001da78  sub     rsp, 190h
0x18001da7f  mov     rax, cs:__security_cookie
0x18001da86  xor     rax, rsp
0x18001da89  mov     [rbp+0C0h+var_40], rax
0x18001da90  xor     r15d, r15d
0x18001da93  mov     [rsp+1C0h+var_180], r8
0x18001da98  mov     rdi, r8
0x18001da9b  mov     rsi, rdx
0x18001da9e  mov     r14, rcx
0x18001daa1  test    r8, r8
0x18001daa4  jnz     short loc_18001DAE3
0x18001daa6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001daad  lea     rax, WPP_GLOBAL_Control
0x18001dab4  cmp     rcx, rax
0x18001dab7  jz      short loc_18001DAD9
0x18001dab9  test    byte ptr [rcx+1Ch], 8
0x18001dabd  jz      short loc_18001DAD9
0x18001dabf  mov     rcx, [rcx+10h]
0x18001dac3  lea     edx, [r8+26h]
0x18001dac7  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001dace  mov     r9d, 80070057h
0x18001dad4  call    WPP_SF_d
0x18001dad9  mov     eax, 80070057h
0x18001dade  jmp     loc_18001DD92
0x18001dae3  test    rsi, rsi
0x18001dae6  jz      short loc_18001DB05
0x18001dae8  mov     r8d, 10h; Size
0x18001daee  lea     rdx, GUID_NULL; Buf2
0x18001daf5  mov     rcx, rsi; Buf1
0x18001daf8  call    memcmp_0
0x18001dafd  neg     eax
0x18001daff  sbb     rcx, rcx
0x18001db02  and     rsi, rcx
0x18001db05  xor     edx, edx; Val
0x18001db07  mov     [rdi], r15d
0x18001db0a  mov     r8d, 118h; Size
0x18001db10  lea     rcx, [rsp+1C0h+VersionInformation.dwMajorVersion]; void *
0x18001db15  call    memset_0
0x18001db1a  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x18001db1f  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18001db27  call    cs:__imp_GetVersionExW
0x18001db2d  test    eax, eax
0x18001db2f  jnz     short loc_18001DB7A
0x18001db31  lea     rcx, [rsp+1C0h+VersionInformation]; lpVersionInformation
0x18001db36  mov     [rsp+1C0h+VersionInformation.dwOSVersionInfoSize], 114h
0x18001db3e  call    cs:__imp_GetVersionExW
0x18001db44  test    eax, eax
0x18001db46  jnz     short loc_18001DB7A
0x18001db48  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x18001db4d  mov     ebx, eax
0x18001db4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db56  lea     rax, WPP_GLOBAL_Control
0x18001db5d  cmp     rcx, rax
0x18001db60  jz      loc_18001DD90
0x18001db66  test    byte ptr [rcx+1Ch], 4
0x18001db6a  jz      loc_18001DD90
0x18001db70  mov     edx, 27h ; '''
0x18001db75  jmp     loc_18001DD7D
0x18001db7a  mov     eax, [rsp+1C0h+VersionInformation.dwPlatformId]
0x18001db7e  mov     r13d, r15d
0x18001db81  mov     ecx, 1
0x18001db86  test    eax, eax
0x18001db88  jz      short loc_18001DB99
0x18001db8a  sub     eax, ecx
0x18001db8c  jz      short loc_18001DB99
0x18001db8e  cmp     eax, ecx
0x18001db90  jnz     short loc_18001DB9C
0x18001db92  cmp     [rsp+1C0h+VersionInformation.dwMajorVersion], 6
0x18001db97  ja      short loc_18001DB9C
0x18001db99  mov     r13d, ecx
0x18001db9c  test    rsi, rsi
0x18001db9f  jz      short loc_18001DBFF
0x18001dba1  lea     rax, [rsp+1C0h+var_190]
0x18001dba6  mov     [rsp+1C0h+var_190], r15
0x18001dbab  mov     r12d, 401h
0x18001dbb1  mov     [rsp+1C0h+ppv], rax; ppv
0x18001dbb6  mov     r8d, r12d; dwClsContext
0x18001dbb9  lea     r9, IID_IXWizardTaskEvent; riid
0x18001dbc0  xor     edx, edx; pUnkOuter
0x18001dbc2  mov     rcx, rsi; rclsid
0x18001dbc5  call    cs:__imp_CoCreateInstance
0x18001dbcb  mov     ebx, eax
0x18001dbcd  test    eax, eax
0x18001dbcf  js      short loc_18001DC43
0x18001dbd1  mov     rcx, [rsp+1C0h+var_190]
0x18001dbd6  mov     rdx, rdi
0x18001dbd9  mov     rax, [rcx]
0x18001dbdc  mov     rax, [rax+60h]
0x18001dbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe5  mov     rcx, [rsp+1C0h+var_190]
0x18001dbea  mov     ebx, eax
0x18001dbec  mov     rdx, [rcx]
0x18001dbef  mov     rax, [rdx+10h]
0x18001dbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf8  test    ebx, ebx
0x18001dbfa  jz      short loc_18001DBFF
0x18001dbfc  mov     [rdi], r15d
0x18001dbff  mov     rcx, r14; this
0x18001dc02  call    ?HrEnsureRegistryInfoModuleLoaded@CPXWizardTask@@AEAAJXZ; CPXWizardTask::HrEnsureRegistryInfoModuleLoaded(void)
0x18001dc07  mov     dword ptr [rsp+1C0h+var_190], eax
0x18001dc0b  mov     ebx, eax
0x18001dc0d  test    eax, eax
0x18001dc0f  jns     loc_18001DCE4
0x18001dc15  mov     [rdi], r15d
0x18001dc18  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc1f  lea     rax, WPP_GLOBAL_Control
0x18001dc26  cmp     rcx, rax
0x18001dc29  jz      loc_18001DD90
0x18001dc2f  test    byte ptr [rcx+1Ch], 4
0x18001dc33  jz      loc_18001DD90
0x18001dc39  mov     edx, 2Ah ; '*'
0x18001dc3e  jmp     loc_18001DD7D
0x18001dc43  cmp     ebx, 80004002h
0x18001dc49  jnz     short loc_18001DCB9
0x18001dc4b  lea     rax, [rsp+1C0h+var_188]
0x18001dc50  mov     [rsp+1C0h+var_188], r15
0x18001dc55  lea     r9, IID_IXWizardPageEvent; riid
0x18001dc5c  mov     [rsp+1C0h+ppv], rax; ppv
0x18001dc61  mov     r8d, r12d; dwClsContext
0x18001dc64  xor     edx, edx; pUnkOuter
0x18001dc66  mov     rcx, rsi; rclsid
0x18001dc69  call    cs:__imp_CoCreateInstance
0x18001dc6f  mov     ebx, eax
0x18001dc71  test    eax, eax
0x18001dc73  js      short loc_18001DC8E
0x18001dc75  mov     rcx, [rsp+1C0h+var_188]
0x18001dc7a  mov     [rdi], r15d
0x18001dc7d  mov     rax, [rcx]
0x18001dc80  mov     rax, [rax+10h]
0x18001dc84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc89  jmp     loc_18001DBFF
0x18001dc8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc95  lea     rax, WPP_GLOBAL_Control
0x18001dc9c  cmp     rcx, rax
0x18001dc9f  jz      loc_18001DD90
0x18001dca5  test    byte ptr [rcx+1Ch], 4
0x18001dca9  jz      loc_18001DD90
0x18001dcaf  mov     edx, 28h ; '('
0x18001dcb4  jmp     loc_18001DD7D
0x18001dcb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dcc0  lea     rax, WPP_GLOBAL_Control
0x18001dcc7  cmp     rcx, rax
0x18001dcca  jz      loc_18001DD90
0x18001dcd0  test    byte ptr [rcx+1Ch], 4
0x18001dcd4  jz      loc_18001DD90
0x18001dcda  mov     edx, 29h ; ')'
0x18001dcdf  jmp     loc_18001DD7D
0x18001dce4  mov     r12d, r15d
0x18001dce7  lea     rdi, qword_18003D0A0
0x18001dcee  mov     rbx, r14
0x18001dcf1  mov     eax, r12d
0x18001dcf4  lea     r14, ds:0[rax*4]
0x18001dcfc  test    r13d, r13d
0x18001dcff  jz      short loc_18001DD0B
0x18001dd01  cmp     dword ptr [r14+rdi], 400h
0x18001dd09  jg      short loc_18001DD37
0x18001dd0b  mov     rcx, [rbx+60h]
0x18001dd0f  lea     r8, [rsp+1C0h+var_178]
0x18001dd14  mov     edx, [r14+rdi]
0x18001dd18  xorps   xmm0, xmm0
0x18001dd1b  movups  [rsp+1C0h+var_178], xmm0
0x18001dd20  xor     r9d, r9d
0x18001dd23  mov     rax, [rcx]
0x18001dd26  mov     rax, [rax+58h]
0x18001dd2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd2f  test    eax, eax
0x18001dd31  js      short loc_18001DD37
0x18001dd33  or      r15d, [r14+rdi]
0x18001dd37  inc     r12d
0x18001dd3a  cmp     dword ptr [rdi+r12*4], 0
0x18001dd3f  jnz     short loc_18001DCF1
0x18001dd41  mov     rdi, [rsp+1C0h+var_180]
0x18001dd46  mov     ebx, dword ptr [rsp+1C0h+var_190]
0x18001dd4a  test    rsi, rsi
0x18001dd4d  jz      short loc_18001DD5A
0x18001dd4f  mov     eax, [rdi]
0x18001dd51  test    eax, eax
0x18001dd53  jz      short loc_18001DD5A
0x18001dd55  and     eax, r15d
0x18001dd58  jmp     short loc_18001DD5D
0x18001dd5a  mov     eax, r15d
0x18001dd5d  mov     [rdi], eax
0x18001dd5f  lea     rax, WPP_GLOBAL_Control
0x18001dd66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dd6d  cmp     rcx, rax
0x18001dd70  jz      short loc_18001DD90
0x18001dd72  test    byte ptr [rcx+1Ch], 10h
0x18001dd76  jz      short loc_18001DD90
0x18001dd78  mov     edx, 2Bh ; '+'
0x18001dd7d  mov     rcx, [rcx+10h]
0x18001dd81  lea     r8, WPP_c5a264895dff3d91b71841da0c1e2aaf_Traceguids
0x18001dd88  mov     r9d, ebx
0x18001dd8b  call    WPP_SF_d
0x18001dd90  mov     eax, ebx
0x18001dd92  mov     rcx, [rbp+0C0h+var_40]
0x18001dd99  xor     rcx, rsp; StackCookie
0x18001dd9c  call    __security_check_cookie
0x18001dda1  mov     rbx, [rsp+1C0h+arg_18]
0x18001dda9  add     rsp, 190h
0x18001ddb0  pop     r15
0x18001ddb2  pop     r14
0x18001ddb4  pop     r13
0x18001ddb6  pop     r12
0x18001ddb8  pop     rdi
0x18001ddb9  pop     rsi
0x18001ddba  pop     rbp
0x18001ddbb  retn
```

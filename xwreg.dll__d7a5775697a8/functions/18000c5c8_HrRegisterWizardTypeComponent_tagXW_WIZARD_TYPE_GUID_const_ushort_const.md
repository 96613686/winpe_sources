# HrRegisterWizardTypeComponent(tagXW_WIZARD_TYPE,_GUID const *,ushort * const)

- ea: `0x18000c5c8`
- end: `0x18000ca66`
- name: `?HrRegisterWizardTypeComponent@@YAJW4tagXW_WIZARD_TYPE@@PEBU_GUID@@QEAG@Z`
- size: `1182`
- prototype: `int __high(enum tagXW_WIZARD_TYPE, const struct _GUID *, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007380`

## callees

- `0x180007820`
- `0x180007a00`
- `0x180007a84`
- `0x1800095a0`
- `0x180009994`
- `0x18000a948`
- `0x18000a9d4`
- `0x18000ace0`
- `0x18000c428`
- `0x18000c5c8`
- `0x18000cd1c`
- `0x18000ce98`
- `0x18000daac`
- `0x18000f010`
- `0x18001230c`
- `0x1800127d6`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c962`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c617`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c617`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c6ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000c6ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c946`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c946`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c76c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c838`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c8be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c76c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c838`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c8be`

## string_xrefs

- `0x18000c760`: `Plug-in Clsid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrRegisterWizardTypeComponent(int a1, const GUID *a2, const WCHAR *a3)
{
  __int64 v6; // r14
  __int64 v7; // rax
  int v8; // eax
  int v9; // r8d
  int v10; // ebx
  LSTATUS v11; // eax
  int v12; // r8d
  int v13; // eax
  BYTE *v14; // r12
  int v15; // r13d
  __int64 v16; // rax
  LSTATUS v17; // eax
  int v18; // ecx
  const BYTE *v19; // r13
  __int64 v20; // rax
  bool v21; // sf
  LSTATUS v22; // eax
  PVOID *v23; // rcx
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v27[32]; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[72]; // [rsp+D0h] [rbp-30h] BYREF

  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(a2, sz, 40);
  SubKey[0] = 0;
  StringCchCopyW(SubKey, 0x47u, L"Software\\Microsoft\\Windows\\CurrentVersion\\XWizards\\");
  StringCchCatW(SubKey, 0x47u, L"Types");
  StringCchCatW(SubKey, 0x47u, L"\\");
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( SubKey[v7] );
  swprintf_sfn(&SubKey[v7], 71 - v7, L"%#0*.*lx");
  CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(v27);
  v8 = CPXWizardRegistryLockedTransaction<3>::HrBackup(v27);
  v10 = v8;
  if ( v8 >= 0 )
  {
    hKey = 0;
    v11 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    v10 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SSLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, v12, (unsigned int)SubKey, (__int64)sz, a1, v10);
    }
    else
    {
      lpData = 0;
      v13 = HrEnsureCOMRegistration(sz, a3, (unsigned __int16 **const)&lpData, 0);
      v10 = v13;
      v14 = lpData;
      v15 = 0;
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_LSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)sz, (__int64)SubKey, v13);
      }
      else
      {
        LOBYTE(v15) = v13 == 0;
        LODWORD(lpData) = v15;
        v16 = -1;
        do
          ++v16;
        while ( sz[v16] );
        v17 = RegSetValueExW(hKey, L"Plug-in Clsid", 0, 1u, (const BYTE *)sz, 2 * v16 + 2);
        v10 = v17;
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0x80070000;
        if ( v10 >= 0 )
        {
          v18 = 0;
          if ( dword_18001D270[0] )
          {
            do
            {
              if ( a1 == dword_18001D270[4 * v18] )
                break;
              ++v18;
            }
            while ( dword_18001D270[4 * v18] );
          }
          v19 = *(const BYTE **)&dword_18001D270[4 * v18 + 2];
          v20 = -1;
          do
            ++v20;
          while ( *(_WORD *)&v19[2 * v20] );
          v10 = RegSetValueExW(hKey, 0, 0, 1u, v19, 2 * v20 + 2);
          v21 = v10 < 0;
          if ( v10 > 0 )
          {
            v10 = (unsigned __int16)v10 | 0x80070000;
            v21 = v10 < 0;
          }
          if ( v21 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_LSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v19, (__int64)SubKey, v10);
          }
          else
          {
            do
              ++v6;
            while ( *(_WORD *)&v14[2 * v6] );
            v22 = RegSetValueExW(hKey, L"File Name", 0, 2u, v14, 2 * v6 + 2);
            v10 = v22;
            if ( v22 > 0 )
              v10 = (unsigned __int16)v22 | 0x80070000;
            if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              WPP_SF_LSSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v14, (__int64)SubKey, v10);
          }
          v15 = (int)lpData;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            10,
            (unsigned int)&WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids,
            (unsigned int)SubKey,
            (__int64)sz,
            v10);
        }
      }
      RegCloseKey(hKey);
      if ( v10 < 0 && v15 )
        HrRegisterOrUnregisterWithCOM((LPCWSTR)v14, 0);
      CoTaskMemFree(v14);
    }
    if ( v10 < 0 )
      CPXWizardRegistryLockedTransaction<3>::HrRestore(v27);
    CPXWizardRegistryLockedTransaction<3>::HrRelease(v27);
    goto LABEL_51;
  }
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_55;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_SSLD(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, v9, (unsigned int)SubKey, (__int64)sz, a1, v8);
LABEL_51:
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x10) != 0 )
    WPP_SF_D(v23[2], 16, &WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids, (unsigned int)v10);
LABEL_55:
  CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(v27);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000c5c8  mov     [rsp-8+arg_18], rbx
0x18000c5cd  push    rbp
0x18000c5ce  push    rsi
0x18000c5cf  push    rdi
0x18000c5d0  push    r12
0x18000c5d2  push    r13
0x18000c5d4  push    r14
0x18000c5d6  push    r15
0x18000c5d8  lea     rbp, [rsp-70h]
0x18000c5dd  sub     rsp, 170h
0x18000c5e4  mov     rax, cs:__security_cookie
0x18000c5eb  xor     rax, rsp
0x18000c5ee  mov     [rbp+0A0h+var_40], rax
0x18000c5f2  mov     rdi, r8
0x18000c5f5  mov     rbx, rdx
0x18000c5f8  mov     r15d, ecx
0x18000c5fb  xor     edx, edx; Val
0x18000c5fd  lea     r8d, [rdx+50h]; Size
0x18000c601  lea     rcx, [rbp+0A0h+sz]; void *
0x18000c605  call    memset_0
0x18000c60a  mov     r8d, 28h ; '('; cchMax
0x18000c610  lea     rdx, [rbp+0A0h+sz]; lpsz
0x18000c614  mov     rcx, rbx; rguid
0x18000c617  call    cs:__imp_StringFromGUID2
0x18000c61d  xor     esi, esi
0x18000c61f  mov     [rbp+0A0h+SubKey], si
0x18000c623  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000c62a  lea     ebx, [rsi+47h]
0x18000c62d  mov     edx, ebx; unsigned __int64
0x18000c62f  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000c633  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c638  lea     r8, aTypes; "Types"
0x18000c63f  mov     edx, ebx; unsigned __int64
0x18000c641  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000c645  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c64a  lea     r8, asc_180016DB4; "\\"
0x18000c651  mov     edx, ebx; unsigned __int64
0x18000c653  lea     rcx, [rbp+0A0h+SubKey]; unsigned __int16 *
0x18000c657  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c65c  lea     rcx, [rbp+0A0h+SubKey]
0x18000c660  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c664  mov     rax, r14
0x18000c667  inc     rax
0x18000c66a  cmp     [rcx+rax*2], si
0x18000c66e  jnz     short loc_18000C667
0x18000c670  sub     rbx, rax
0x18000c673  lea     rcx, [rbp+0A0h+SubKey]
0x18000c677  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000c67b  mov     [rsp+1A0h+samDesired], r15d
0x18000c680  mov     r9d, 8
0x18000c686  mov     [rsp+1A0h+dwOptions], r9d
0x18000c68b  lea     r8, a0Lx; "%#0*.*lx"
0x18000c692  mov     rdx, rbx; unsigned __int64
0x18000c695  call    ?swprintf_sfn@@YAXPEAG_KPEBGZZ; swprintf_sfn(ushort *,unsigned __int64,ushort const *,...)
0x18000c69a  lea     rcx, [rsp+1A0h+var_140]
0x18000c69f  call    ??0?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::CPXWizardRegistryLockedTransaction<3>(void)
0x18000c6a4  nop
0x18000c6a5  lea     rcx, [rsp+1A0h+var_140]
0x18000c6aa  call    ?HrBackup@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJK@Z; CPXWizardRegistryLockedTransaction<3>::HrBackup(ulong)
0x18000c6af  mov     ebx, eax
0x18000c6b1  test    eax, eax
0x18000c6b3  js      loc_18000C9CC
0x18000c6b9  mov     [rsp+1A0h+hKey], rsi
0x18000c6be  mov     [rsp+1A0h+lpdwDisposition], rsi; lpdwDisposition
0x18000c6c3  lea     rax, [rsp+1A0h+hKey]
0x18000c6c8  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18000c6cd  mov     [rsp+1A0h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000c6d2  mov     [rsp+1A0h+samDesired], 20006h; samDesired
0x18000c6da  mov     [rsp+1A0h+dwOptions], esi; dwOptions
0x18000c6de  xor     r9d, r9d; lpClass
0x18000c6e1  xor     r8d, r8d; Reserved
0x18000c6e4  lea     rdx, [rbp+0A0h+SubKey]; lpSubKey
0x18000c6e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c6ef  call    cs:__imp_RegCreateKeyExW
0x18000c6f5  mov     ebx, eax
0x18000c6f7  test    eax, eax
0x18000c6f9  jnz     loc_18000C96A
0x18000c6ff  mov     [rsp+1A0h+lpData], rsi
0x18000c704  xor     r9d, r9d; void *
0x18000c707  lea     r8, [rsp+1A0h+lpData]; unsigned __int16 **
0x18000c70c  mov     rdx, rdi; lpSrc
0x18000c70f  lea     rcx, [rbp+0A0h+sz]; unsigned __int16 *
0x18000c713  call    ?HrEnsureCOMRegistration@@YAJQEAG0QEAPEAGQEAX@Z; HrEnsureCOMRegistration(ushort * const,ushort * const,ushort * * const,void * const)
0x18000c718  mov     ebx, eax
0x18000c71a  mov     r12, [rsp+1A0h+lpData]
0x18000c71f  mov     r13d, esi
0x18000c722  test    eax, eax
0x18000c724  js      loc_18000C901
0x18000c72a  setz    r13b
0x18000c72e  mov     dword ptr [rsp+1A0h+lpData], r13d
0x18000c733  lea     rcx, [rbp+0A0h+sz]
0x18000c737  mov     rax, r14
0x18000c73a  inc     rax
0x18000c73d  cmp     [rcx+rax*2], si
0x18000c741  jnz     short loc_18000C73A
0x18000c743  lea     eax, ds:2[rax*2]
0x18000c74a  mov     [rsp+1A0h+samDesired], eax; cbData
0x18000c74e  lea     rax, [rbp+0A0h+sz]
0x18000c752  mov     qword ptr [rsp+1A0h+dwOptions], rax; lpData
0x18000c757  mov     r9d, 1; dwType
0x18000c75d  xor     r8d, r8d; Reserved
0x18000c760  lea     rdx, aPlugInClsid; "Plug-in Clsid"
0x18000c767  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000c76c  call    cs:__imp_RegSetValueExW
0x18000c772  mov     ebx, eax
0x18000c774  mov     esi, 80070000h
0x18000c779  xor     edx, edx; lpValueName
0x18000c77b  test    eax, eax
0x18000c77d  jle     short loc_18000C784
0x18000c77f  movzx   ebx, ax
0x18000c782  or      ebx, esi
0x18000c784  lea     rdi, WPP_GLOBAL_Control
0x18000c78b  test    ebx, ebx
0x18000c78d  jns     short loc_18000C7D4
0x18000c78f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c796  cmp     rcx, rdi
0x18000c799  jz      loc_18000C941
0x18000c79f  test    byte ptr [rcx+1Ch], 4
0x18000c7a3  jz      loc_18000C941
0x18000c7a9  mov     edx, 0Ah
0x18000c7ae  mov     [rsp+1A0h+samDesired], ebx
0x18000c7b2  lea     rax, [rbp+0A0h+sz]
0x18000c7b6  mov     qword ptr [rsp+1A0h+dwOptions], rax
0x18000c7bb  lea     r9, [rbp+0A0h+SubKey]
0x18000c7bf  lea     r8, WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids
0x18000c7c6  mov     rcx, [rcx+10h]
0x18000c7ca  call    WPP_SF_SSD
0x18000c7cf  jmp     loc_18000C941
0x18000c7d4  mov     ecx, edx
0x18000c7d6  lea     r13, dword_18001D270
0x18000c7dd  cmp     cs:dword_18001D270, edx
0x18000c7e3  jz      short loc_18000C801
0x18000c7e5  movsxd  rax, ecx
0x18000c7e8  add     rax, rax
0x18000c7eb  cmp     r15d, [r13+rax*8+0]
0x18000c7f0  jz      short loc_18000C801
0x18000c7f2  inc     ecx
0x18000c7f4  movsxd  rax, ecx
0x18000c7f7  add     rax, rax
0x18000c7fa  cmp     [r13+rax*8+0], edx
0x18000c7ff  jnz     short loc_18000C7E5
0x18000c801  movsxd  rax, ecx
0x18000c804  add     rax, rax
0x18000c807  mov     r13, [r13+rax*8+8]
0x18000c80c  mov     rax, r14
0x18000c80f  inc     rax
0x18000c812  cmp     [r13+rax*2+0], dx
0x18000c818  jnz     short loc_18000C80F
0x18000c81a  lea     eax, ds:2[rax*2]
0x18000c821  mov     [rsp+1A0h+samDesired], eax; cbData
0x18000c825  mov     qword ptr [rsp+1A0h+dwOptions], r13; lpData
0x18000c82a  mov     r9d, 1; dwType
0x18000c830  xor     r8d, r8d; Reserved
0x18000c833  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000c838  call    cs:__imp_RegSetValueExW
0x18000c83e  mov     ebx, eax
0x18000c840  xor     eax, eax
0x18000c842  test    ebx, ebx
0x18000c844  jle     short loc_18000C84D
0x18000c846  movzx   ebx, bx
0x18000c849  or      ebx, esi
0x18000c84b  test    ebx, ebx
0x18000c84d  jns     short loc_18000C88E
0x18000c84f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c856  cmp     rcx, rdi
0x18000c859  jz      short loc_18000C884
0x18000c85b  test    byte ptr [rcx+1Ch], 4
0x18000c85f  jz      short loc_18000C884
0x18000c861  mov     edx, 0Bh
0x18000c866  mov     dword ptr [rsp+1A0h+lpSecurityAttributes], ebx; char
0x18000c86a  lea     rax, [rbp+0A0h+SubKey]
0x18000c86e  mov     qword ptr [rsp+1A0h+samDesired], rax; __int64
0x18000c873  mov     qword ptr [rsp+1A0h+dwOptions], r13; __int64
0x18000c878  mov     r9d, r15d
0x18000c87b  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c87f  call    WPP_SF_LSSD
0x18000c884  mov     r13d, dword ptr [rsp+1A0h+lpData]
0x18000c889  jmp     loc_18000C941
0x18000c88e  inc     r14
0x18000c891  cmp     [r12+r14*2], ax
0x18000c896  jnz     short loc_18000C88E
0x18000c898  lea     eax, ds:2[r14*2]
0x18000c8a0  mov     [rsp+1A0h+samDesired], eax; cbData
0x18000c8a4  mov     qword ptr [rsp+1A0h+dwOptions], r12; lpData
0x18000c8a9  mov     r9d, 2; dwType
0x18000c8af  xor     r8d, r8d; Reserved
0x18000c8b2  lea     rdx, aFileName_1; "File Name"
0x18000c8b9  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000c8be  call    cs:__imp_RegSetValueExW
0x18000c8c4  mov     ebx, eax
0x18000c8c6  test    eax, eax
0x18000c8c8  jle     short loc_18000C8CF
0x18000c8ca  movzx   ebx, ax
0x18000c8cd  or      ebx, esi
0x18000c8cf  test    ebx, ebx
0x18000c8d1  jns     short loc_18000C884
0x18000c8d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8da  cmp     rcx, rdi
0x18000c8dd  jz      short loc_18000C884
0x18000c8df  test    byte ptr [rcx+1Ch], 4
0x18000c8e3  jz      short loc_18000C884
0x18000c8e5  mov     edx, 0Ch
0x18000c8ea  mov     dword ptr [rsp+1A0h+lpSecurityAttributes], ebx
0x18000c8ee  lea     rax, [rbp+0A0h+SubKey]
0x18000c8f2  mov     qword ptr [rsp+1A0h+samDesired], rax
0x18000c8f7  mov     qword ptr [rsp+1A0h+dwOptions], r12
0x18000c8fc  jmp     loc_18000C878
0x18000c901  lea     rdi, WPP_GLOBAL_Control
0x18000c908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c90f  cmp     rcx, rdi
0x18000c912  jz      short loc_18000C941
0x18000c914  test    byte ptr [rcx+1Ch], 4
0x18000c918  jz      short loc_18000C941
0x18000c91a  mov     edx, 0Dh
0x18000c91f  mov     dword ptr [rsp+1A0h+lpSecurityAttributes], eax; char
0x18000c923  lea     rax, [rbp+0A0h+SubKey]
0x18000c927  mov     qword ptr [rsp+1A0h+samDesired], rax; __int64
0x18000c92c  lea     rax, [rbp+0A0h+sz]
0x18000c930  mov     qword ptr [rsp+1A0h+dwOptions], rax; __int64
0x18000c935  mov     r9d, r15d
0x18000c938  mov     rcx, [rcx+10h]; LoggerHandle
0x18000c93c  call    WPP_SF_LSSD
0x18000c941  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18000c946  call    cs:__imp_RegCloseKey
0x18000c94c  test    ebx, ebx
0x18000c94e  jns     short loc_18000C95F
0x18000c950  test    r13d, r13d
0x18000c953  jz      short loc_18000C95F
0x18000c955  xor     edx, edx; int
0x18000c957  mov     rcx, r12; lpSrc
0x18000c95a  call    ?HrRegisterOrUnregisterWithCOM@@YAJQEAGH@Z; HrRegisterOrUnregisterWithCOM(ushort * const,int)
0x18000c95f  mov     rcx, r12; pv
0x18000c962  call    cs:__imp_CoTaskMemFree
0x18000c968  jmp     short loc_18000C9B2
0x18000c96a  jle     short loc_18000C975
0x18000c96c  movzx   ebx, ax
0x18000c96f  or      ebx, 80070000h
0x18000c975  lea     rdi, WPP_GLOBAL_Control
0x18000c97c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c983  cmp     rcx, rdi
0x18000c986  jz      short loc_18000C9B2
0x18000c988  test    byte ptr [rcx+1Ch], 4
0x18000c98c  jz      short loc_18000C9B2
0x18000c98e  mov     edx, 0Eh
0x18000c993  mov     dword ptr [rsp+1A0h+lpSecurityAttributes], ebx
0x18000c997  mov     [rsp+1A0h+samDesired], r15d
0x18000c99c  lea     rax, [rbp+0A0h+sz]
0x18000c9a0  mov     qword ptr [rsp+1A0h+dwOptions], rax
0x18000c9a5  lea     r9, [rbp+0A0h+SubKey]
0x18000c9a9  mov     rcx, [rcx+10h]
0x18000c9ad  call    WPP_SF_SSLD
0x18000c9b2  test    ebx, ebx
0x18000c9b4  jns     short loc_18000C9C0
0x18000c9b6  lea     rcx, [rsp+1A0h+var_140]
0x18000c9bb  call    ?HrRestore@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRestore(void)
0x18000c9c0  lea     rcx, [rsp+1A0h+var_140]
0x18000c9c5  call    ?HrRelease@?$CPXWizardRegistryLockedTransaction@$02@@QEAAJXZ; CPXWizardRegistryLockedTransaction<3>::HrRelease(void)
0x18000c9ca  jmp     short loc_18000CA09
0x18000c9cc  lea     rdi, WPP_GLOBAL_Control
0x18000c9d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9da  cmp     rcx, rdi
0x18000c9dd  jz      short loc_18000CA33
0x18000c9df  test    byte ptr [rcx+1Ch], 4
0x18000c9e3  jz      short loc_18000CA10
0x18000c9e5  mov     edx, 0Fh
0x18000c9ea  mov     dword ptr [rsp+1A0h+lpSecurityAttributes], eax
0x18000c9ee  mov     [rsp+1A0h+samDesired], r15d
0x18000c9f3  lea     rax, [rbp+0A0h+sz]
0x18000c9f7  mov     qword ptr [rsp+1A0h+dwOptions], rax
0x18000c9fc  lea     r9, [rbp+0A0h+SubKey]
0x18000ca00  mov     rcx, [rcx+10h]
0x18000ca04  call    WPP_SF_SSLD
0x18000ca09  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ca10  cmp     rcx, rdi
0x18000ca13  jz      short loc_18000CA33
0x18000ca15  mov     edx, 10h
0x18000ca1a  test    [rcx+1Ch], dl
0x18000ca1d  jz      short loc_18000CA33
0x18000ca1f  mov     r9d, ebx
0x18000ca22  lea     r8, WPP_c59db8bb72f63a18e3e9f4e39396474c_Traceguids
0x18000ca29  mov     rcx, [rcx+10h]
0x18000ca2d  call    WPP_SF_D
0x18000ca32  nop
0x18000ca33  lea     rcx, [rsp+1A0h+var_140]
0x18000ca38  call    ??1?$CPXWizardRegistryLockedTransaction@$02@@QEAA@XZ; CPXWizardRegistryLockedTransaction<3>::~CPXWizardRegistryLockedTransaction<3>(void)
0x18000ca3d  mov     eax, ebx
0x18000ca3f  mov     rcx, [rbp+0A0h+var_40]
0x18000ca43  xor     rcx, rsp; StackCookie
0x18000ca46  call    __security_check_cookie
0x18000ca4b  mov     rbx, [rsp+1A0h+arg_18]
0x18000ca53  add     rsp, 170h
0x18000ca5a  pop     r15
0x18000ca5c  pop     r14
0x18000ca5e  pop     r13
0x18000ca60  pop     r12
0x18000ca62  pop     rdi
0x18000ca63  pop     rsi
0x18000ca64  pop     rbp
0x18000ca65  retn
```

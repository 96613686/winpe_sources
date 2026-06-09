# MachineId::CreateMachineIdInProc(int,_GUID *)

- ea: `0x180031000`
- end: `0x1800313aa`
- name: `?CreateMachineIdInProc@MachineId@@SAJHPEAU_GUID@@@Z`
- size: `938`
- prototype: `static int(int, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001965c`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180004538`
- `0x180007cc8`
- `0x180011ef8`
- `0x180013f54`
- `0x180030dc8`
- `0x180031000`
- `0x1800313b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003111b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003111b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800310bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031381`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800310cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031381`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031298`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031298`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031323`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180031323`
- `RPCRT4!UuidFromStringW` at `0x18003114f`
- `RPCRT4!UuidFromStringW` at `0x18003114f`
- `RPCRT4!UuidCreate` at `0x1800311c6`
- `RPCRT4!UuidCreate` at `0x1800311c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031370`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031370`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003110d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003110d`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineId` at `0x180031051`
- `ext-ms-win-wer-xbox-l1-1-0!XerGetMachineId` at `0x180031051`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MachineId::CreateMachineIdInProc(int a1, struct _GUID *a2)
{
  signed int MachineId; // ebx
  RPC_WSTR v5; // rcx
  HKEY *phkResult; // rax
  LSTATUS v7; // ebx
  PSECURITY_DESCRIPTOR *v8; // rax
  signed int LastError; // eax
  RPC_STATUS v10; // ebx
  unsigned int v11; // eax
  HKEY *v12; // rax
  LSTATUS v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  LSTATUS v16; // eax
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v19; // [rsp+58h] [rbp-A8h] BYREF
  RPC_WSTR StringUuid[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v21[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey[3]; // [rsp+98h] [rbp-68h] BYREF
  BYTE Data[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[72]; // [rsp+B2h] [rbp-4Eh] BYREF
  int v26; // [rsp+FAh] [rbp-6h]

  v19 = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  hMem = 0;
  if ( (unsigned __int8)IsXerGetMachineIdPresent() )
  {
    MachineId = XerGetMachineId(a2);
    goto LABEL_50;
  }
  v5 = v21;
  StringUuid[0] = v21;
  StringUuid[1] = v21;
  v21[0] = 0;
  if ( !a1 )
  {
    if ( (int)MachineId::QueryMachineId((__int64)StringUuid) >= 0 )
      goto LABEL_17;
    hKey[0] = 0;
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    v7 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\Windows Error Reporting\\SysprepLock",
           0,
           0x101u,
           phkResult);
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    if ( !v7 )
    {
LABEL_17:
      *(_OWORD *)hKey = 0;
      v10 = UuidFromStringW(StringUuid[0], (UUID *)hKey);
      if ( v10 )
      {
        MachineId = v10 | 0x80010000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids,
            (unsigned int)MachineId);
      }
      else
      {
        *a2 = *(struct _GUID *)hKey;
        MachineId = 0;
      }
      if ( StringUuid[0] != v21 )
        operator delete(StringUuid[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_50;
    }
    v5 = StringUuid[0];
  }
  if ( v5 != v21 )
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
  v8 = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&hMem);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)(A;OICI;KR;;;BU)(A;OICI;KR;;;S-1-15-2-1)",
          1u,
          v8,
          0) )
  {
    LastError = GetLastError();
    MachineId = LastError;
    if ( LastError > 0 )
      MachineId = (unsigned __int16)LastError | 0x80070000;
    if ( MachineId >= 0 )
      MachineId = -2147467259;
    goto LABEL_50;
  }
  v11 = UuidCreate(a2);
  MachineId = v11;
  if ( v11 && v11 != 1824 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids, v11);
    if ( MachineId > 0 )
      MachineId = (unsigned __int16)MachineId | 0x80070000;
    goto LABEL_50;
  }
  strcpy((char *)Data, "{");
  tlx::guid_to_string_upper<wchar_t>(v25, a2);
  v26 = 125;
  SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = hMem;
  SecurityAttributes.nLength = 24;
  v12 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v19);
  v13 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\SQMClient",
          0,
          0,
          0,
          0x20106u,
          &SecurityAttributes,
          v12,
          0);
  MachineId = v13;
  if ( !v13 || v13 == 183 )
  {
    v16 = RegSetValueExW(v19, L"MachineID", 0, 1u, Data, 0x4Eu);
    MachineId = v16;
    if ( !v16 )
    {
      MachineId = 0;
      goto LABEL_50;
    }
    if ( v16 > 0 )
      MachineId = (unsigned __int16)v16 | 0x80070000;
    if ( MachineId >= 0 )
      MachineId = -2147467259;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 16;
      goto LABEL_40;
    }
  }
  else
  {
    if ( v13 > 0 )
      MachineId = (unsigned __int16)v13 | 0x80070000;
    if ( MachineId >= 0 )
      MachineId = -2147467259;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 15;
LABEL_40:
      WPP_SF_d(v14[2], v15, WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids, (unsigned int)MachineId);
    }
  }
LABEL_50:
  if ( hMem )
    LocalFree(hMem);
  if ( v19 )
    RegCloseKey(v19);
  return (unsigned int)MachineId;
}

```

## disassembly

```asm
0x180031000  mov     [rsp-8+arg_0], rbx
0x180031005  mov     [rsp-8+arg_10], rdi
0x18003100a  push    rbp
0x18003100b  lea     rbp, [rsp-10h]
0x180031010  sub     rsp, 110h
0x180031017  mov     rax, cs:__security_cookie
0x18003101e  xor     rax, rsp
0x180031021  mov     [rbp+10h+var_10], rax
0x180031025  mov     rdi, rdx
0x180031028  mov     ebx, ecx
0x18003102a  mov     [rsp+110h+var_B8], 0
0x180031033  xorps   xmm0, xmm0
0x180031036  xor     eax, eax
0x180031038  movups  xmmword ptr [rbp+10h+SecurityAttributes.nLength], xmm0
0x18003103c  mov     qword ptr [rbp+10h+SecurityAttributes.bInheritHandle], rax
0x180031040  mov     [rsp+110h+hMem], rax
0x180031045  call    IsXerGetMachineIdPresent
0x18003104a  test    al, al
0x18003104c  jz      short loc_18003105E
0x18003104e  mov     rcx, rdi
0x180031051  call    cs:__imp_XerGetMachineId
0x180031057  mov     ebx, eax
0x180031059  jmp     loc_180031366
0x18003105e  lea     rcx, [rsp+110h+var_A0]
0x180031063  mov     [rsp+110h+StringUuid], rcx
0x180031068  lea     rax, [rsp+110h+var_A0]
0x18003106d  mov     [rsp+110h+var_A8], rax
0x180031072  xor     eax, eax
0x180031074  mov     [rsp+110h+var_A0], ax
0x180031079  test    ebx, ebx
0x18003107b  jnz     short loc_1800310DC
0x18003107d  lea     rcx, [rsp+110h+StringUuid]; __int64
0x180031082  call    ?QueryMachineId@MachineId@@CAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::QueryMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180031087  test    eax, eax
0x180031089  jns     loc_18003113F
0x18003108f  mov     [rbp+10h+hKey], 0
0x180031097  lea     rcx, [rbp+10h+hKey]
0x18003109b  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1800310a0  mov     [rsp+110h+phkResult], rax; phkResult
0x1800310a5  mov     r9d, 101h; samDesired
0x1800310ab  xor     r8d, r8d; ulOptions
0x1800310ae  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\Windows E"...
0x1800310b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800310bc  call    cs:__imp_RegOpenKeyExW
0x1800310c2  mov     ebx, eax
0x1800310c4  mov     rcx, [rbp+10h+hKey]; hKey
0x1800310c8  test    rcx, rcx
0x1800310cb  jz      short loc_1800310D3
0x1800310cd  call    cs:__imp_RegCloseKey
0x1800310d3  test    ebx, ebx
0x1800310d5  jz      short loc_18003113F
0x1800310d7  mov     rcx, [rsp+110h+StringUuid]; void *
0x1800310dc  lea     rax, [rsp+110h+var_A0]
0x1800310e1  cmp     rcx, rax
0x1800310e4  jz      short loc_1800310F2
0x1800310e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800310ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800310f2  lea     rcx, [rsp+110h+hMem]
0x1800310f7  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1800310fc  mov     r8, rax; SecurityDescriptor
0x1800310ff  xor     r9d, r9d; SecurityDescriptorSize
0x180031102  lea     edx, [r9+1]; StringSDRevision
0x180031106  lea     rcx, aDPAOiciKaBaAOi; "D:P(A;OICI;KA;;;BA)(A;OICI;KA;;;SY)(A;O"...
0x18003110d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180031113  test    eax, eax
0x180031115  jnz     loc_1800311C3
0x18003111b  call    cs:__imp_GetLastError
0x180031121  mov     ebx, eax
0x180031123  test    eax, eax
0x180031125  jle     short loc_180031130
0x180031127  movzx   ebx, ax
0x18003112a  or      ebx, 80070000h
0x180031130  mov     eax, 80004005h
0x180031135  test    ebx, ebx
0x180031137  cmovns  ebx, eax
0x18003113a  jmp     loc_180031366
0x18003113f  xorps   xmm0, xmm0
0x180031142  movups  xmmword ptr [rbp+10h+hKey], xmm0
0x180031146  lea     rdx, [rbp+10h+hKey]; Uuid
0x18003114a  mov     rcx, [rsp+110h+StringUuid]; StringUuid
0x18003114f  call    cs:__imp_UuidFromStringW
0x180031155  mov     ebx, eax
0x180031157  test    eax, eax
0x180031159  jz      short loc_1800311B7
0x18003115b  or      ebx, 80010000h
0x180031161  lea     rax, WPP_GLOBAL_Control
0x180031168  mov     rcx, cs:WPP_GLOBAL_Control
0x18003116f  cmp     rcx, rax
0x180031172  jz      short loc_180031193
0x180031174  test    byte ptr [rcx+1Ch], 1
0x180031178  jz      short loc_180031193
0x18003117a  mov     edx, 0Dh
0x18003117f  mov     r9d, ebx
0x180031182  lea     r8, WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids
0x180031189  mov     rcx, [rcx+10h]
0x18003118d  call    WPP_SF_d
0x180031192  nop
0x180031193  lea     rax, [rsp+110h+var_A0]
0x180031198  mov     rcx, [rsp+110h+StringUuid]; void *
0x18003119d  cmp     rcx, rax
0x1800311a0  jz      loc_180031366
0x1800311a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800311ad  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800311b2  jmp     loc_180031366
0x1800311b7  movups  xmm0, xmmword ptr [rbp+10h+hKey]
0x1800311bb  movdqu  xmmword ptr [rdi], xmm0
0x1800311bf  xor     ebx, ebx
0x1800311c1  jmp     short loc_180031193
0x1800311c3  mov     rcx, rdi; Uuid
0x1800311c6  call    cs:__imp_UuidCreate
0x1800311cc  mov     ebx, eax
0x1800311ce  test    eax, eax
0x1800311d0  jz      short loc_180031220
0x1800311d2  cmp     eax, 720h
0x1800311d7  jz      short loc_180031220
0x1800311d9  lea     rax, WPP_GLOBAL_Control
0x1800311e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800311e7  cmp     rcx, rax
0x1800311ea  jz      short loc_18003120A
0x1800311ec  test    byte ptr [rcx+1Ch], 1
0x1800311f0  jz      short loc_18003120A
0x1800311f2  mov     edx, 0Eh
0x1800311f7  mov     r9d, ebx
0x1800311fa  lea     r8, WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids
0x180031201  mov     rcx, [rcx+10h]
0x180031205  call    WPP_SF_d
0x18003120a  test    ebx, ebx
0x18003120c  jle     loc_180031366
0x180031212  movzx   ebx, bx
0x180031215  or      ebx, 80070000h
0x18003121b  jmp     loc_180031366
0x180031220  mov     eax, 7Bh ; '{'
0x180031225  mov     word ptr [rbp+10h+Data], ax
0x180031229  mov     rdx, rdi
0x18003122c  lea     rcx, [rbp+10h+var_5E]
0x180031230  call    ??$guid_to_string_upper@_W@tlx@@YAXPEA_WAEBU_GUID@@_N@Z; tlx::guid_to_string_upper<wchar_t>(wchar_t *,_GUID const &,bool)
0x180031235  mov     [rbp+10h+var_16], 7Dh ; '}'
0x18003123c  mov     [rbp+10h+SecurityAttributes.bInheritHandle], 0
0x180031243  mov     rax, [rsp+110h+hMem]
0x180031248  mov     [rbp+10h+SecurityAttributes.lpSecurityDescriptor], rax
0x18003124c  mov     [rbp+10h+SecurityAttributes.nLength], 18h
0x180031253  lea     rcx, [rsp+110h+var_B8]
0x180031258  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18003125d  mov     [rsp+110h+lpdwDisposition], 0; lpdwDisposition
0x180031266  mov     [rsp+110h+var_D8], rax; phkResult
0x18003126b  lea     rax, [rbp+10h+SecurityAttributes]
0x18003126f  mov     [rsp+110h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180031274  mov     [rsp+110h+samDesired], 20106h; samDesired
0x18003127c  mov     dword ptr [rsp+110h+phkResult], 0; dwOptions
0x180031284  xor     r9d, r9d; lpClass
0x180031287  xor     r8d, r8d; Reserved
0x18003128a  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SQMClient"
0x180031291  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031298  call    cs:__imp_RegCreateKeyExW
0x18003129e  mov     ebx, eax
0x1800312a0  test    eax, eax
0x1800312a2  jz      short loc_1800312FD
0x1800312a4  cmp     eax, 0B7h
0x1800312a9  jz      short loc_1800312FD
0x1800312ab  test    eax, eax
0x1800312ad  jle     short loc_1800312B8
0x1800312af  movzx   ebx, ax
0x1800312b2  or      ebx, 80070000h
0x1800312b8  mov     eax, 80004005h
0x1800312bd  test    ebx, ebx
0x1800312bf  cmovns  ebx, eax
0x1800312c2  lea     rax, WPP_GLOBAL_Control
0x1800312c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312d0  cmp     rcx, rax
0x1800312d3  jz      loc_180031366
0x1800312d9  test    byte ptr [rcx+1Ch], 1
0x1800312dd  jz      loc_180031366
0x1800312e3  mov     edx, 0Fh
0x1800312e8  mov     r9d, ebx
0x1800312eb  lea     r8, WPP_c548adb26bdf3e1146a5f33989df2cf1_Traceguids
0x1800312f2  mov     rcx, [rcx+10h]
0x1800312f6  call    WPP_SF_d
0x1800312fb  jmp     short loc_180031366
0x1800312fd  mov     [rsp+110h+samDesired], 4Eh ; 'N'; cbData
0x180031305  lea     rax, [rbp+10h+Data]
0x180031309  mov     [rsp+110h+phkResult], rax; lpData
0x18003130e  mov     r9d, 1; dwType
0x180031314  xor     r8d, r8d; Reserved
0x180031317  lea     rdx, aMachineid; "MachineID"
0x18003131e  mov     rcx, [rsp+110h+var_B8]; hKey
0x180031323  call    cs:__imp_RegSetValueExW
0x180031329  mov     ebx, eax
0x18003132b  test    eax, eax
0x18003132d  jz      short loc_180031364
0x18003132f  jle     short loc_18003133A
0x180031331  movzx   ebx, ax
0x180031334  or      ebx, 80070000h
0x18003133a  mov     eax, 80004005h
0x18003133f  test    ebx, ebx
0x180031341  cmovns  ebx, eax
0x180031344  lea     rax, WPP_GLOBAL_Control
0x18003134b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031352  cmp     rcx, rax
0x180031355  jz      short loc_180031366
0x180031357  test    byte ptr [rcx+1Ch], 1
0x18003135b  jz      short loc_180031366
0x18003135d  mov     edx, 10h
0x180031362  jmp     short loc_1800312E8
0x180031364  xor     ebx, ebx
0x180031366  mov     rcx, [rsp+110h+hMem]; hMem
0x18003136b  test    rcx, rcx
0x18003136e  jz      short loc_180031377
0x180031370  call    cs:__imp_LocalFree
0x180031376  nop
0x180031377  mov     rcx, [rsp+110h+var_B8]; hKey
0x18003137c  test    rcx, rcx
0x18003137f  jz      short loc_180031387
0x180031381  call    cs:__imp_RegCloseKey
0x180031387  mov     eax, ebx
0x180031389  mov     rcx, [rbp+10h+var_10]
0x18003138d  xor     rcx, rsp; StackCookie
0x180031390  call    __security_check_cookie
0x180031395  lea     r11, [rsp+110h+var_s0]
0x18003139d  mov     rbx, [r11+10h]
0x1800313a1  mov     rdi, [r11+20h]
0x1800313a5  mov     rsp, r11
0x1800313a8  pop     rbp
0x1800313a9  retn
```

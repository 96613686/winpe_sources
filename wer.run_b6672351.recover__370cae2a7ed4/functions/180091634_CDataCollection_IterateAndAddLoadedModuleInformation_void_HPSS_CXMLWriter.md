# CDataCollection::IterateAndAddLoadedModuleInformation(void *,HPSS__ *,CXMLWriter *)

- ea: `0x180091634`
- end: `0x180091938`
- name: `?IterateAndAddLoadedModuleInformation@CDataCollection@@AEAAJPEAXPEAUHPSS__@@PEAVCXMLWriter@@@Z`
- size: `772`
- prototype: `int(CDataCollection *__hidden this, void *, struct HPSS__ *, struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008fe08`

## callees

- `0x180007fd8`
- `0x180008004`
- `0x18001c368`
- `0x180020680`
- `0x18003de9c`
- `0x180053300`
- `0x180053d3c`
- `0x180090050`
- `0x180091634`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800916ae`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18009173a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800916ae`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18009173a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091825`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800916da`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x1800916da`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1800918f8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32NextW` at `0x1800918f8`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800917ef`
- `api-ms-win-core-toolhelp-l1-1-0!Module32FirstW` at `0x1800917ef`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180091758`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180091758`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataCollection::IterateAndAddLoadedModuleInformation(
        CDataCollection *this,
        HANDLE a2,
        struct HPSS__ *a3,
        struct CXMLWriter *a4)
{
  __int64 v7; // rdx
  __int64 v8; // r8
  _BOOL8 v9; // rcx
  DWORD ProcessId; // eax
  int v11; // eax
  unsigned int v12; // ebx
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HANDLE Toolhelp32Snapshot; // rax
  HANDLE v17; // rbx
  DWORD LastError; // eax
  DWORD v19; // eax
  CDataCollection *v20; // rcx
  DWORD v21; // eax
  MODULEENTRY32W *p_me; // rcx
  _OWORD *v23; // rax
  __int64 v24; // rdx
  HANDLE Process; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE hSnapshot; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v28[1088]; // [rsp+30h] [rbp-D0h] BYREF
  MODULEENTRY32W me; // [rsp+470h] [rbp+370h] BYREF

  hSnapshot = 0;
  Process = 0;
  memset_0(&me, 0, sizeof(me));
  v9 = a3 != 0;
  if ( v9 == (a2 != 0) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v9, v7, v8);
  if ( a2 )
  {
    ProcessId = GetProcessId(a2);
LABEL_15:
    Toolhelp32Snapshot = CreateToolhelp32Snapshot(8u, ProcessId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&hSnapshot, Toolhelp32Snapshot);
    v17 = hSnapshot;
    if ( (unsigned __int64)hSnapshot + 1 <= 1 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, LastError);
      }
      v19 = GetLastError();
      v12 = ERROR_HR_FROM_WIN32(v19);
      goto LABEL_28;
    }
    me.dwSize = 1080;
    if ( !Module32FirstW(hSnapshot, &me) )
    {
      v12 = -2147467259;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_28;
      v21 = GetLastError();
      v14 = 135;
      v15 = v21;
      v13 = WPP_GLOBAL_Control;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, v15);
      goto LABEL_28;
    }
    do
    {
      CDataCollection::AddModuleInformation(v20, a2, me.hModule, a4);
      memset_0(v28, 0, 0x438u);
      p_me = &me;
      v23 = v28;
      v24 = 8;
      do
      {
        *(_OWORD *)&p_me->dwSize = *v23;
        *(_OWORD *)&p_me->ProccntUsage = v23[1];
        *(_OWORD *)&p_me->modBaseSize = v23[2];
        *(_OWORD *)p_me->szModule = v23[3];
        *(_OWORD *)&p_me->szModule[8] = v23[4];
        *(_OWORD *)&p_me->szModule[16] = v23[5];
        *(_OWORD *)&p_me->szModule[24] = v23[6];
        *(_OWORD *)&p_me->szModule[32] = v23[7];
        p_me = (MODULEENTRY32W *)((char *)p_me + 128);
        v23 += 8;
        --v24;
      }
      while ( v24 );
      *(_OWORD *)&p_me->dwSize = *v23;
      *(_OWORD *)&p_me->ProccntUsage = v23[1];
      *(_OWORD *)&p_me->modBaseSize = v23[2];
      *(_QWORD *)p_me->szModule = *((_QWORD *)v23 + 6);
      me.dwSize = 1080;
    }
    while ( Module32NextW(v17, &me) );
    v12 = 0;
    goto LABEL_28;
  }
  if ( !a3 )
  {
    a2 = 0;
    ProcessId = 0;
    goto LABEL_15;
  }
  v11 = PssQuerySnapshot(a3, 1, &Process);
  v12 = v11;
  if ( !v11 )
  {
    ProcessId = GetProcessId(Process);
    a2 = Process;
    goto LABEL_15;
  }
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v14 = 133;
    v15 = v12;
    goto LABEL_12;
  }
LABEL_28:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hSnapshot);
  return v12;
}

```

## disassembly

```asm
0x180091634  push    rbp
0x180091636  push    rbx
0x180091637  push    rsi
0x180091638  push    rdi
0x180091639  push    r15
0x18009163b  lea     rbp, [rsp-7C0h]
0x180091643  sub     rsp, 8C0h
0x18009164a  mov     rax, cs:__security_cookie
0x180091651  xor     rax, rsp
0x180091654  mov     [rbp+7E0h+var_30], rax
0x18009165b  mov     rsi, r9
0x18009165e  mov     rbx, r8
0x180091661  mov     rdi, rdx
0x180091664  mov     [rsp+8E0h+hSnapshot], 0
0x18009166d  mov     [rsp+8E0h+Process], 0
0x180091676  mov     r15d, 438h
0x18009167c  mov     r8d, r15d; Size
0x18009167f  xor     edx, edx; Val
0x180091681  lea     rcx, [rbp+7E0h+me]; void *
0x180091688  call    memset_0
0x18009168d  xor     ecx, ecx
0x18009168f  test    rbx, rbx
0x180091692  setnz   cl
0x180091695  xor     eax, eax
0x180091697  test    rdi, rdi
0x18009169a  setnz   al
0x18009169d  cmp     ecx, eax
0x18009169f  jnz     short loc_1800916A6
0x1800916a1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800916a6  test    rdi, rdi
0x1800916a9  jz      short loc_1800916BF
0x1800916ab  mov     rcx, rdi; Process
0x1800916ae  call    cs:__imp_GetProcessId
0x1800916b5  nop     dword ptr [rax+rax+00h]
0x1800916ba  jmp     loc_180091751
0x1800916bf  test    rbx, rbx
0x1800916c2  jz      loc_18009174D
0x1800916c8  mov     r9d, 8
0x1800916ce  lea     r8, [rsp+8E0h+Process]
0x1800916d3  lea     edx, [r9-7]
0x1800916d7  mov     rcx, rbx
0x1800916da  call    cs:__imp_PssQuerySnapshot
0x1800916e1  nop     dword ptr [rax+rax+00h]
0x1800916e6  mov     ebx, eax
0x1800916e8  test    eax, eax
0x1800916ea  jz      short loc_180091735
0x1800916ec  jle     short loc_1800916F7
0x1800916ee  movzx   ebx, ax
0x1800916f1  or      ebx, 80070000h
0x1800916f7  lea     rax, WPP_GLOBAL_Control
0x1800916fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180091705  cmp     rcx, rax
0x180091708  jz      loc_18009190E
0x18009170e  test    byte ptr [rcx+1Ch], 1
0x180091712  jz      loc_18009190E
0x180091718  mov     edx, 85h
0x18009171d  mov     r9d, ebx
0x180091720  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180091727  mov     rcx, [rcx+10h]
0x18009172b  call    WPP_SF_d
0x180091730  jmp     loc_18009190E
0x180091735  mov     rcx, [rsp+8E0h+Process]; Process
0x18009173a  call    cs:__imp_GetProcessId
0x180091741  nop     dword ptr [rax+rax+00h]
0x180091746  mov     rdi, [rsp+8E0h+Process]
0x18009174b  jmp     short loc_180091751
0x18009174d  xor     edi, edi
0x18009174f  xor     eax, eax
0x180091751  mov     edx, eax; th32ProcessID
0x180091753  mov     ecx, 8; dwFlags
0x180091758  call    cs:__imp_CreateToolhelp32Snapshot
0x18009175f  nop     dword ptr [rax+rax+00h]
0x180091764  mov     rdx, rax
0x180091767  lea     rcx, [rsp+8E0h+hSnapshot]
0x18009176c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180091771  mov     rbx, [rsp+8E0h+hSnapshot]
0x180091776  lea     rax, [rbx+1]
0x18009177a  cmp     rax, 1
0x18009177e  ja      short loc_1800917DE
0x180091780  lea     rax, WPP_GLOBAL_Control
0x180091787  mov     rcx, cs:WPP_GLOBAL_Control
0x18009178e  cmp     rcx, rax
0x180091791  jz      short loc_1800917C4
0x180091793  test    byte ptr [rcx+1Ch], 1
0x180091797  jz      short loc_1800917C4
0x180091799  call    cs:__imp_GetLastError
0x1800917a0  nop     dword ptr [rax+rax+00h]
0x1800917a5  mov     edx, 86h
0x1800917aa  mov     r9d, eax
0x1800917ad  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800917b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917bb  mov     rcx, [rcx+10h]
0x1800917bf  call    WPP_SF_d
0x1800917c4  call    cs:__imp_GetLastError
0x1800917cb  nop     dword ptr [rax+rax+00h]
0x1800917d0  mov     ecx, eax; unsigned int
0x1800917d2  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800917d7  mov     ebx, eax
0x1800917d9  jmp     loc_18009190E
0x1800917de  mov     [rbp+7E0h+me.dwSize], r15d
0x1800917e5  lea     rdx, [rbp+7E0h+me]; lpme
0x1800917ec  mov     rcx, rbx; hSnapshot
0x1800917ef  call    cs:__imp_Module32FirstW
0x1800917f6  nop     dword ptr [rax+rax+00h]
0x1800917fb  test    eax, eax
0x1800917fd  jnz     short loc_180091845
0x1800917ff  mov     ebx, 80004005h
0x180091804  lea     rax, WPP_GLOBAL_Control
0x18009180b  mov     rcx, cs:WPP_GLOBAL_Control
0x180091812  cmp     rcx, rax
0x180091815  jz      loc_18009190E
0x18009181b  test    byte ptr [rcx+1Ch], 1
0x18009181f  jz      loc_18009190E
0x180091825  call    cs:__imp_GetLastError
0x18009182c  nop     dword ptr [rax+rax+00h]
0x180091831  mov     edx, 87h
0x180091836  mov     r9d, eax
0x180091839  mov     rcx, cs:WPP_GLOBAL_Control
0x180091840  jmp     loc_180091720
0x180091845  mov     r9, rsi; struct CXMLWriter *
0x180091848  mov     r8, [rbp+7E0h+me.hModule]; HINSTANCE
0x18009184f  mov     rdx, rdi; void *
0x180091852  call    ?AddModuleInformation@CDataCollection@@AEAAJPEAXPEAUHINSTANCE__@@PEAVCXMLWriter@@@Z; CDataCollection::AddModuleInformation(void *,HINSTANCE__ *,CXMLWriter *)
0x180091857  mov     r8, r15; Size
0x18009185a  xor     edx, edx; Val
0x18009185c  lea     rcx, [rsp+8E0h+var_8B0]; void *
0x180091861  call    memset_0
0x180091866  lea     rcx, [rbp+7E0h+me]
0x18009186d  lea     rax, [rsp+8E0h+var_8B0]
0x180091872  mov     edx, 8
0x180091877  movups  xmm0, xmmword ptr [rax]
0x18009187a  movups  xmmword ptr [rcx], xmm0
0x18009187d  movups  xmm1, xmmword ptr [rax+10h]
0x180091881  movups  xmmword ptr [rcx+10h], xmm1
0x180091885  movups  xmm0, xmmword ptr [rax+20h]
0x180091889  movups  xmmword ptr [rcx+20h], xmm0
0x18009188d  movups  xmm1, xmmword ptr [rax+30h]
0x180091891  movups  xmmword ptr [rcx+30h], xmm1
0x180091895  movups  xmm0, xmmword ptr [rax+40h]
0x180091899  movups  xmmword ptr [rcx+40h], xmm0
0x18009189d  movups  xmm1, xmmword ptr [rax+50h]
0x1800918a1  movups  xmmword ptr [rcx+50h], xmm1
0x1800918a5  movups  xmm0, xmmword ptr [rax+60h]
0x1800918a9  movups  xmmword ptr [rcx+60h], xmm0
0x1800918ad  movups  xmm1, xmmword ptr [rax+70h]
0x1800918b1  movups  xmmword ptr [rcx+70h], xmm1
0x1800918b5  lea     rcx, [rcx+80h]
0x1800918bc  lea     rax, [rax+80h]
0x1800918c3  sub     rdx, 1
0x1800918c7  jnz     short loc_180091877
0x1800918c9  movups  xmm0, xmmword ptr [rax]
0x1800918cc  movups  xmmword ptr [rcx], xmm0
0x1800918cf  movups  xmm1, xmmword ptr [rax+10h]
0x1800918d3  movups  xmmword ptr [rcx+10h], xmm1
0x1800918d7  movups  xmm0, xmmword ptr [rax+20h]
0x1800918db  movups  xmmword ptr [rcx+20h], xmm0
0x1800918df  mov     rax, [rax+30h]
0x1800918e3  mov     [rcx+30h], rax
0x1800918e7  mov     [rbp+7E0h+me.dwSize], r15d
0x1800918ee  lea     rdx, [rbp+7E0h+me]; lpme
0x1800918f5  mov     rcx, rbx; hSnapshot
0x1800918f8  call    cs:__imp_Module32NextW
0x1800918ff  nop     dword ptr [rax+rax+00h]
0x180091904  test    eax, eax
0x180091906  jnz     loc_180091845
0x18009190c  xor     ebx, ebx
0x18009190e  lea     rcx, [rsp+8E0h+hSnapshot]
0x180091913  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180091918  mov     eax, ebx
0x18009191a  mov     rcx, [rbp+7E0h+var_30]
0x180091921  xor     rcx, rsp; StackCookie
0x180091924  call    __security_check_cookie
0x180091929  add     rsp, 8C0h
0x180091930  pop     r15
0x180091932  pop     rdi
0x180091933  pop     rsi
0x180091934  pop     rbx
0x180091935  pop     rbp
0x180091936  retn
```

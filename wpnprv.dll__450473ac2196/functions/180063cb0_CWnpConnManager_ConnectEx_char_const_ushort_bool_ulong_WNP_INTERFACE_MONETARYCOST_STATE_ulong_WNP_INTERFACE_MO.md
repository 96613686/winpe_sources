# CWnpConnManager::ConnectEx(char const *,ushort,bool,ulong,_WNP_INTERFACE_MONETARYCOST_STATE,ulong,_WNP_INTERFACE_MONETARYCOST_STATE,ulong,_WNP_INTERFACE_MONETARYCOST_STATE,bool)

- ea: `0x180063cb0`
- end: `0x18006415f`
- name: `?ConnectEx@CWnpConnManager@@UEAAJPEBDG_NKW4_WNP_INTERFACE_MONETARYCOST_STATE@@K2K21@Z`
- size: `1199`
- prototype: `__int64 __fastcall(__int64, const char *, __int64, char, unsigned int, unsigned int, int, int, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180063be0`

## callees

- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001ca78`
- `0x18002fcdc`
- `0x180061360`
- `0x180063cb0`
- `0x1800649fc`
- `0x180064afc`
- `0x180065fb8`
- `0x1800661dc`
- `0x1800665f4`
- `0x180066a00`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063e0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180063e0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063e01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180063e01`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180063da8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180063da8`

## pseudocode

```c
__int64 __fastcall CWnpConnManager::ConnectEx(
        __int64 a1,
        const char *a2,
        __int64 a3,
        char a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        char a11)
{
  PVOID *v14; // rcx
  void *v15; // rsi
  HANDLE ProcessHeap; // rax
  int v17; // eax
  unsigned int v18; // ebx
  PVOID *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-78h]
  int v27; // [rsp+20h] [rbp-78h]
  int v28; // [rsp+28h] [rbp-70h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  unsigned __int16 v30; // [rsp+B0h] [rbp+18h]

  v30 = a3;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      LOBYTE(v26) = *(_BYTE *)(a1 + 212);
      WPP_SF_Lcc(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *(unsigned int *)(a1 + 256));
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 4) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    {
      v26 = a6;
      WPP_SF_dddddd(v14[2], 27, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, a5);
    }
  }
  if ( *(_BYTE *)(a1 + 292) )
  {
    *(_DWORD *)(a1 + 272) = -1;
    if ( CoCreateGuid((GUID *)(a1 + 276)) < 0 )
      *(GUID *)(a1 + 276) = GUID_NULL;
    *(_BYTE *)(a1 + 292) = 0;
  }
  *(_BYTE *)(a1 + 260) = a4;
  *(_BYTE *)(a1 + 250) = a11;
  *(_DWORD *)(a1 + 252) = 0;
  if ( a2 && *a2 )
  {
    v15 = *(void **)(a1 + 240);
    if ( v15 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v15);
      *(_QWORD *)(a1 + 240) = 0;
    }
    v17 = WpnStrCpyA(a2, (char **)(a1 + 240));
    v18 = v17;
    if ( v17 >= 0 )
    {
      v28 = a8;
      v27 = a7;
      CWnpConnManager::UpdateConnectorSelectionPerPolicy(a1, v30, a5, a6);
      *(_DWORD *)(a1 + 208) = -1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v28) = *(_BYTE *)(a1 + 212);
        WPP_SF_dLc(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          *(unsigned int *)(a1 + 256),
          1,
          v28);
      }
      *(_DWORD *)(a1 + 256) = 1;
      CWnpConnManager::DisconnectNonActiveLayers((CWnpConnManager *)a1, 1);
      if ( !*(_BYTE *)(a1 + 212)
        || (v22 = CWnpConnManager::SetUpLongRunningTransport((CWnpConnManager *)a1), v18 = v22, v22 >= 0) )
      {
        v23 = CWnpConnManager::FindAndConnectSingleLayer((CWnpConnManager *)a1);
        v18 = v23;
        if ( v23 >= 0 )
        {
          CWnpConnManager::SetConnectionTakingTooLongTimer((void **)a1);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            LOBYTE(v28) = *(_BYTE *)(a1 + 212);
            WPP_SF_dLc(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              36,
              &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
              *(unsigned int *)(a1 + 256),
              5,
              v28);
          }
          v24 = *(_QWORD *)(a1 + 232);
          *(_DWORD *)(a1 + 256) = 5;
          (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 0, 5, 1);
        }
        else
        {
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v18;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            goto LABEL_58;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
            (unsigned int)v23);
        }
        goto LABEL_57;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          (unsigned int)v22);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)v18,
        v27);
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v20 = 34;
          goto LABEL_25;
        }
LABEL_58:
        if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 4) != 0 && *((_BYTE *)v19 + 25) >= 6u )
          WPP_SF_d(v19[2], 37, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v18);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids,
          (unsigned int)v17);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
        (const char *)v18,
        v26);
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v20 = 31;
LABEL_25:
          v21 = v18;
LABEL_56:
          WPP_SF_d(v19[2], v20, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, v21);
LABEL_57:
          v19 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_58;
        }
        goto LABEL_58;
      }
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v14);
    v18 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids, 2147549183LL);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\trans\\wnpconnmanager.cpp",
      (const char *)0x8000FFFFLL,
      v26);
    v19 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v20 = 29;
        v21 = 2147549183LL;
        goto LABEL_56;
      }
      goto LABEL_58;
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180063cb0  mov     [rsp+arg_10], r8w
0x180063cb6  push    rbx
0x180063cb7  push    rbp
0x180063cb8  push    rsi
0x180063cb9  push    rdi
0x180063cba  push    r12
0x180063cbc  push    r13
0x180063cbe  push    r14
0x180063cc0  push    r15
0x180063cc2  sub     rsp, 58h
0x180063cc6  mov     r14b, r9b
0x180063cc9  mov     rbp, rdx
0x180063ccc  mov     rdi, rcx
0x180063ccf  mov     rcx, cs:WPP_GLOBAL_Control
0x180063cd6  lea     rbx, WPP_GLOBAL_Control
0x180063cdd  mov     r15d, [rsp+98h+arg_48]
0x180063ce5  mov     r12d, [rsp+98h+arg_40]
0x180063ced  mov     r13d, [rsp+98h+arg_38]
0x180063cf5  mov     sil, [rsp+98h+arg_50]
0x180063cfd  cmp     rcx, rbx
0x180063d00  jz      loc_180063D8B
0x180063d06  test    byte ptr [rcx+1Ch], 4
0x180063d0a  jz      short loc_180063D38
0x180063d0c  cmp     byte ptr [rcx+19h], 6
0x180063d10  jb      short loc_180063D38
0x180063d12  mov     al, [rdi+0D4h]
0x180063d18  mov     r9d, [rdi+100h]
0x180063d1f  mov     rcx, [rcx+10h]
0x180063d23  mov     byte ptr [rsp+98h+var_70], sil
0x180063d28  mov     byte ptr [rsp+98h+var_78], al
0x180063d2c  call    WPP_SF_Lcc
0x180063d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180063d38  cmp     rcx, rbx
0x180063d3b  jz      short loc_180063D8B
0x180063d3d  test    byte ptr [rcx+1Ch], 4
0x180063d41  jz      short loc_180063D8B
0x180063d43  cmp     byte ptr [rcx+19h], 5
0x180063d47  jb      short loc_180063D8B
0x180063d49  mov     eax, [rsp+98h+arg_30]
0x180063d50  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180063d57  mov     r9d, [rsp+98h+arg_20]
0x180063d5f  mov     edx, 1Bh
0x180063d64  mov     rcx, [rcx+10h]
0x180063d68  mov     [rsp+98h+var_58], r15d
0x180063d6d  mov     [rsp+98h+var_60], r12d
0x180063d72  mov     [rsp+98h+var_68], r13d
0x180063d77  mov     [rsp+98h+var_70], eax
0x180063d7b  mov     eax, [rsp+98h+arg_28]
0x180063d82  mov     [rsp+98h+var_78], eax; int
0x180063d86  call    WPP_SF_dddddd
0x180063d8b  cmp     byte ptr [rdi+124h], 0
0x180063d92  jz      short loc_180063DC4
0x180063d94  lea     rbx, [rdi+114h]
0x180063d9b  mov     dword ptr [rdi+110h], 0FFFFFFFFh
0x180063da5  mov     rcx, rbx; pguid
0x180063da8  call    cs:__imp_CoCreateGuid
0x180063dae  test    eax, eax
0x180063db0  jns     short loc_180063DBD
0x180063db2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180063db9  movdqu  xmmword ptr [rbx], xmm0
0x180063dbd  mov     byte ptr [rdi+124h], 0
0x180063dc4  mov     [rdi+104h], r14b
0x180063dcb  xor     r14d, r14d
0x180063dce  mov     [rdi+0FAh], sil
0x180063dd5  mov     dword ptr [rdi+0FCh], 0
0x180063ddf  test    rbp, rbp
0x180063de2  jz      loc_180064092
0x180063de8  cmp     [rbp+0], r14b
0x180063dec  jz      loc_180064092
0x180063df2  lea     rbx, [rdi+0F0h]
0x180063df9  mov     rsi, [rbx]
0x180063dfc  test    rsi, rsi
0x180063dff  jz      short loc_180063E18
0x180063e01  call    cs:__imp_GetProcessHeap
0x180063e07  mov     r8, rsi; lpMem
0x180063e0a  xor     edx, edx; dwFlags
0x180063e0c  mov     rcx, rax; hHeap
0x180063e0f  call    cs:__imp_HeapFree
0x180063e15  mov     [rbx], r14
0x180063e18  mov     rdx, rbx; char **
0x180063e1b  mov     rcx, rbp; char *
0x180063e1e  call    ?WpnStrCpyA@@YAJPEBDPEAPEAD@Z; WpnStrCpyA(char const *,char * *)
0x180063e23  mov     ebx, eax
0x180063e25  test    eax, eax
0x180063e27  jns     short loc_180063EA3
0x180063e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e30  lea     rsi, WPP_GLOBAL_Control
0x180063e37  cmp     rcx, rsi
0x180063e3a  jz      short loc_180063E60
0x180063e3c  test    byte ptr [rcx+1Ch], 4
0x180063e40  jz      short loc_180063E60
0x180063e42  cmp     byte ptr [rcx+19h], 2
0x180063e46  jb      short loc_180063E60
0x180063e48  mov     rcx, [rcx+10h]
0x180063e4c  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180063e53  mov     edx, 1Eh
0x180063e58  mov     r9d, eax
0x180063e5b  call    WPP_SF_d
0x180063e60  mov     rcx, [rsp+98h]; this
0x180063e68  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180063e6f  mov     r9d, ebx; char *
0x180063e72  mov     edx, 0AEh; void *
0x180063e77  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063e7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e83  cmp     rcx, rsi
0x180063e86  jz      loc_18006414C
0x180063e8c  test    byte ptr [rcx+1Ch], 80h
0x180063e90  jz      loc_180064123
0x180063e96  mov     edx, 1Fh
0x180063e9b  mov     r9d, ebx
0x180063e9e  jmp     loc_18006410C
0x180063ea3  mov     eax, [rsp+98h+arg_30]
0x180063eaa  mov     rcx, rdi
0x180063ead  mov     r9d, [rsp+98h+arg_28]
0x180063eb5  mov     r8d, [rsp+98h+arg_20]
0x180063ebd  movzx   edx, [rsp+98h+arg_10]
0x180063ec5  mov     [rsp+98h+var_60], r15d
0x180063eca  mov     [rsp+98h+var_68], r12d
0x180063ecf  mov     [rsp+98h+var_70], r13d
0x180063ed4  mov     [rsp+98h+var_78], eax
0x180063ed8  call    ?UpdateConnectorSelectionPerPolicy@CWnpConnManager@@AEAAXGKW4_WNP_INTERFACE_MONETARYCOST_STATE@@K0K0@Z; CWnpConnManager::UpdateConnectorSelectionPerPolicy(ushort,ulong,_WNP_INTERFACE_MONETARYCOST_STATE,ulong,_WNP_INTERFACE_MONETARYCOST_STATE,ulong,_WNP_INTERFACE_MONETARYCOST_STATE)
0x180063edd  mov     dword ptr [rdi+0D0h], 0FFFFFFFFh
0x180063ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x180063eee  lea     rsi, WPP_GLOBAL_Control
0x180063ef5  mov     ebp, 1
0x180063efa  cmp     rcx, rsi
0x180063efd  jz      short loc_180063F33
0x180063eff  test    byte ptr [rcx+1Ch], 4
0x180063f03  jz      short loc_180063F33
0x180063f05  cmp     byte ptr [rcx+19h], 5
0x180063f09  jb      short loc_180063F33
0x180063f0b  mov     al, [rdi+0D4h]
0x180063f11  lea     edx, [rbp+1Fh]
0x180063f14  mov     r9d, [rdi+100h]
0x180063f1b  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180063f22  mov     rcx, [rcx+10h]
0x180063f26  mov     byte ptr [rsp+98h+var_70], al
0x180063f2a  mov     [rsp+98h+var_78], ebp; int
0x180063f2e  call    WPP_SF_dLc
0x180063f33  mov     edx, ebp; int
0x180063f35  mov     [rdi+100h], ebp
0x180063f3b  mov     rcx, rdi; this
0x180063f3e  call    ?DisconnectNonActiveLayers@CWnpConnManager@@AEAAXJ@Z; CWnpConnManager::DisconnectNonActiveLayers(long)
0x180063f43  cmp     [rdi+0D4h], r14b
0x180063f4a  jz      short loc_180063FCA
0x180063f4c  mov     rcx, rdi; this
0x180063f4f  call    ?SetUpLongRunningTransport@CWnpConnManager@@AEAAJXZ; CWnpConnManager::SetUpLongRunningTransport(void)
0x180063f54  mov     ebx, eax
0x180063f56  test    eax, eax
0x180063f58  jns     short loc_180063FCA
0x180063f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063f61  cmp     rcx, rsi
0x180063f64  jz      short loc_180063F8A
0x180063f66  test    byte ptr [rcx+1Ch], 4
0x180063f6a  jz      short loc_180063F8A
0x180063f6c  cmp     byte ptr [rcx+19h], 2
0x180063f70  jb      short loc_180063F8A
0x180063f72  mov     rcx, [rcx+10h]
0x180063f76  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180063f7d  mov     edx, 21h ; '!'
0x180063f82  mov     r9d, eax
0x180063f85  call    WPP_SF_d
0x180063f8a  mov     rcx, [rsp+98h]; this
0x180063f92  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180063f99  mov     r9d, ebx; char *
0x180063f9c  mov     edx, 0CBh; void *
0x180063fa1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063fa6  mov     rcx, cs:WPP_GLOBAL_Control
0x180063fad  cmp     rcx, rsi
0x180063fb0  jz      loc_18006414C
0x180063fb6  test    byte ptr [rcx+1Ch], 80h
0x180063fba  jz      loc_180064123
0x180063fc0  mov     edx, 22h ; '"'
0x180063fc5  jmp     loc_180063E9B
0x180063fca  mov     rcx, rdi; this
0x180063fcd  call    ?FindAndConnectSingleLayer@CWnpConnManager@@AEAAJXZ; CWnpConnManager::FindAndConnectSingleLayer(void)
0x180063fd2  mov     ebx, eax
0x180063fd4  test    eax, eax
0x180063fd6  jns     short loc_180064019
0x180063fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180063fdf  cmp     rcx, rsi
0x180063fe2  jz      loc_18006414C
0x180063fe8  test    byte ptr [rcx+1Ch], 4
0x180063fec  jz      loc_180064123
0x180063ff2  cmp     byte ptr [rcx+19h], 2
0x180063ff6  jb      loc_180064123
0x180063ffc  mov     rcx, [rcx+10h]
0x180064000  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180064007  mov     edx, 23h ; '#'
0x18006400c  mov     r9d, eax
0x18006400f  call    WPP_SF_d
0x180064014  jmp     loc_18006411C
0x180064019  mov     rcx, rdi; this
0x18006401c  call    ?SetConnectionTakingTooLongTimer@CWnpConnManager@@AEAAXKK@Z; CWnpConnManager::SetConnectionTakingTooLongTimer(ulong,ulong)
0x180064021  mov     rcx, cs:WPP_GLOBAL_Control
0x180064028  cmp     rcx, rsi
0x18006402b  jz      short loc_180064067
0x18006402d  test    byte ptr [rcx+1Ch], 4
0x180064031  jz      short loc_180064067
0x180064033  cmp     byte ptr [rcx+19h], 5
0x180064037  jb      short loc_180064067
0x180064039  mov     al, [rdi+0D4h]
0x18006403f  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180064046  mov     r9d, [rdi+100h]
0x18006404d  mov     edx, 24h ; '$'
0x180064052  mov     rcx, [rcx+10h]
0x180064056  mov     byte ptr [rsp+98h+var_70], al
0x18006405a  mov     [rsp+98h+var_78], 5
0x180064062  call    WPP_SF_dLc
0x180064067  mov     rcx, [rdi+0E8h]
0x18006406e  xor     edx, edx
0x180064070  mov     dword ptr [rdi+100h], 5
0x18006407a  mov     r9d, ebp
0x18006407d  mov     rax, [rcx]
0x180064080  lea     r8d, [rdx+5]
0x180064084  mov     rax, [rax+8]
0x180064088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006408d  jmp     loc_18006411C
0x180064092  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180064097  mov     ebx, 8000FFFFh
0x18006409c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640a3  lea     rsi, WPP_GLOBAL_Control
0x1800640aa  cmp     rcx, rsi
0x1800640ad  jz      short loc_1800640D3
0x1800640af  test    byte ptr [rcx+1Ch], 4
0x1800640b3  jz      short loc_1800640D3
0x1800640b5  cmp     byte ptr [rcx+19h], 2
0x1800640b9  jb      short loc_1800640D3
0x1800640bb  mov     rcx, [rcx+10h]
0x1800640bf  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x1800640c6  mov     edx, 1Ch
0x1800640cb  mov     r9d, ebx
0x1800640ce  call    WPP_SF_d
0x1800640d3  mov     rcx, [rsp+98h]; this
0x1800640db  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800640e2  mov     r9d, ebx; char *
0x1800640e5  mov     edx, 0A8h; void *
0x1800640ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800640ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800640f6  cmp     rcx, rsi
0x1800640f9  jz      short loc_18006414C
0x1800640fb  test    byte ptr [rcx+1Ch], 80h
0x1800640ff  jz      short loc_180064123
0x180064101  mov     edx, 1Dh
0x180064106  mov     r9d, 8000FFFFh
0x18006410c  mov     rcx, [rcx+10h]
0x180064110  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x180064117  call    WPP_SF_d
0x18006411c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064123  cmp     rcx, rsi
0x180064126  jz      short loc_18006414C
0x180064128  test    byte ptr [rcx+1Ch], 4
0x18006412c  jz      short loc_18006414C
0x18006412e  cmp     byte ptr [rcx+19h], 6
0x180064132  jb      short loc_18006414C
0x180064134  mov     rcx, [rcx+10h]
0x180064138  lea     r8, WPP_c2695b214f4937d505e61a78da1ced9b_Traceguids
0x18006413f  mov     edx, 25h ; '%'
0x180064144  mov     r9d, ebx
0x180064147  call    WPP_SF_d
0x18006414c  mov     eax, ebx
0x18006414e  add     rsp, 58h
0x180064152  pop     r15
0x180064154  pop     r14
0x180064156  pop     r13
0x180064158  pop     r12
0x18006415a  pop     rdi
0x18006415b  pop     rsi
0x18006415c  pop     rbp
0x18006415d  pop     rbx
0x18006415e  retn
```

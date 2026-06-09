# CPublishWMIOperationEvent::GetFunctionPointers(void)

- ea: `0x180021540`
- end: `0x180021844`
- name: `?GetFunctionPointers@CPublishWMIOperationEvent@@SAJXZ`
- size: `772`
- prototype: `__int64(void)`
- caller_count: `14`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001f5c0`
- `0x18001fa40`
- `0x18001fd90`
- `0x180020610`
- `0x1800207c0`
- `0x180020e44`
- `0x180020f08`
- `0x180020fd0`
- `0x1800214c0`
- `0x180021500`
- `0x180021850`
- `0x180021ba0`
- `0x180021f20`
- `0x180043530`

## callees

- `0x180013564`
- `0x180014120`
- `0x180016730`
- `0x180021540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002166e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800216b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002166e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800216b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002170c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021618`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021634`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021650`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215b8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800215f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021618`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021634`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021650`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002159c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002159c`

## string_xrefs

- `0x180021595`: `ntdll`
- `0x1800215ee`: `EtwEventWrite`
- `0x18002162a`: `EtwEventWriteTransfer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CPublishWMIOperationEvent::GetFunctionPointers(void)
{
  HMODULE ModuleHandleW; // rax
  HMODULE v2; // rbx
  signed int LastError; // eax
  int v4; // ebx
  signed int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  if ( CPublishWMIOperationEvent::m_hAdvAPI32 )
    goto LABEL_2;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, &CPublishWMIOperationEvent::m_csFunctionPointers);
  if ( !CPublishWMIOperationEvent::m_hAdvAPI32 )
  {
    ModuleHandleW = GetModuleHandleW(L"ntdll");
    v2 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      CPublishWMIOperationEvent::m_fEventRegister = (unsigned int (*)(const struct _GUID *, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *), void *, unsigned __int64 *))GetProcAddress(ModuleHandleW, "EtwEventRegister");
      if ( CPublishWMIOperationEvent::m_fEventRegister )
      {
        CPublishWMIOperationEvent::m_fEventUnregister = (unsigned int (*)(unsigned __int64))GetProcAddress(
                                                                                              v2,
                                                                                              "EtwEventUnregister");
        if ( CPublishWMIOperationEvent::m_fEventUnregister )
        {
          CPublishWMIOperationEvent::m_fEventWrite = (unsigned int (*)(unsigned __int64, struct _EVENT_DESCRIPTOR *, unsigned int, struct _EVENT_DATA_DESCRIPTOR *))GetProcAddress(v2, "EtwEventWrite");
          if ( CPublishWMIOperationEvent::m_fEventWrite )
          {
            CPublishWMIOperationEvent::m_fEventActivityIdControl = (unsigned int (*)(unsigned int, struct _GUID *))GetProcAddress(v2, "EtwEventActivityIdControl");
            if ( CPublishWMIOperationEvent::m_fEventActivityIdControl )
            {
              CPublishWMIOperationEvent::m_fEventWriteTransfer = (unsigned int (*)(unsigned __int64, const struct _EVENT_DESCRIPTOR *, const struct _GUID *, const struct _GUID *, unsigned int, struct _EVENT_DATA_DESCRIPTOR *))GetProcAddress(v2, "EtwEventWriteTransfer");
              if ( CPublishWMIOperationEvent::m_fEventWriteTransfer )
              {
                CPublishWMIOperationEvent::m_fEventEnabled = (unsigned __int8 (*)(unsigned __int64, const struct _EVENT_DESCRIPTOR *))GetProcAddress(v2, "EtwEventEnabled");
                if ( CPublishWMIOperationEvent::m_fEventEnabled )
                {
                  CPublishWMIOperationEvent::m_hAdvAPI32 = v2;
                  goto LABEL_14;
                }
              }
            }
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            v4 = LastError;
LABEL_20:
            LeaveCriticalSection(lpCriticalSection);
            return (unsigned int)v4;
          }
          v10 = GetLastError();
          v4 = v10;
          if ( v10 > 0 )
            v4 = (unsigned __int16)v10 | 0x80070000;
          if ( v4 < 0 )
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_20;
          }
          v7 = 25;
        }
        else
        {
          v9 = GetLastError();
          v4 = v9;
          if ( v9 > 0 )
            v4 = (unsigned __int16)v9 | 0x80070000;
          if ( v4 < 0 )
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_20;
          }
          v7 = 24;
        }
      }
      else
      {
        v5 = GetLastError();
        v4 = v5;
        if ( v5 > 0 )
          v4 = (unsigned __int16)v5 | 0x80070000;
        if ( v4 < 0 )
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_20;
        }
        v7 = 23;
      }
    }
    else
    {
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 < 0 )
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_20;
      }
      v7 = 22;
    }
    WPP_SF_D(v6[2], v7, WPP_f6063e9a384b39fc8c4cb2f534a59449_Traceguids, (unsigned int)v4);
    goto LABEL_20;
  }
LABEL_14:
  LeaveCriticalSection(lpCriticalSection);
LABEL_2:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_f6063e9a384b39fc8c4cb2f534a59449_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180021540  push    rbx
0x180021542  sub     rsp, 20h
0x180021546  cmp     cs:?m_hAdvAPI32@CPublishWMIOperationEvent@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CPublishWMIOperationEvent::m_hAdvAPI32
0x18002154e  jz      short loc_180021575
0x180021550  lea     rax, WPP_GLOBAL_Control
0x180021557  mov     rcx, cs:WPP_GLOBAL_Control
0x18002155e  cmp     rcx, rax
0x180021561  jz      short loc_18002156D
0x180021563  test    byte ptr [rcx+1Ch], 1
0x180021567  jnz     loc_180021679
0x18002156d  xor     eax, eax
0x18002156f  add     rsp, 20h
0x180021573  pop     rbx
0x180021574  retn
0x180021575  lea     rdx, ?m_csFunctionPointers@CPublishWMIOperationEvent@@0VCCritSec@@A; struct _RTL_CRITICAL_SECTION *
0x18002157c  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x180021581  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180021586  nop
0x180021587  cmp     cs:?m_hAdvAPI32@CPublishWMIOperationEvent@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CPublishWMIOperationEvent::m_hAdvAPI32
0x18002158f  jnz     loc_180021669
0x180021595  lea     rcx, aNtdll; "ntdll"
0x18002159c  call    cs:__imp_GetModuleHandleW
0x1800215a2  mov     rbx, rax
0x1800215a5  test    rax, rax
0x1800215a8  jz      loc_18002170C
0x1800215ae  lea     rdx, aEtweventregist; "EtwEventRegister"
0x1800215b5  mov     rcx, rax; hModule
0x1800215b8  call    cs:__imp_GetProcAddress
0x1800215be  mov     cs:?m_fEventRegister@CPublishWMIOperationEvent@@0P6AKPEBU_GUID@@P6AX0KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z3PEA_K@ZEA, rax; ulong (*CPublishWMIOperationEvent::m_fEventRegister)(_GUID const *,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *),void *,unsigned __int64 *)
0x1800215c5  test    rax, rax
0x1800215c8  jz      loc_1800216C6
0x1800215ce  lea     rdx, aEtweventunregi; "EtwEventUnregister"
0x1800215d5  mov     rcx, rbx; hModule
0x1800215d8  call    cs:__imp_GetProcAddress
0x1800215de  mov     cs:?m_fEventUnregister@CPublishWMIOperationEvent@@0P6AK_K@ZEA, rax; ulong (*CPublishWMIOperationEvent::m_fEventUnregister)(unsigned __int64)
0x1800215e5  test    rax, rax
0x1800215e8  jz      loc_180021768
0x1800215ee  lea     rdx, aEtweventwrite; "EtwEventWrite"
0x1800215f5  mov     rcx, rbx; hModule
0x1800215f8  call    cs:__imp_GetProcAddress
0x1800215fe  mov     cs:?m_fEventWrite@CPublishWMIOperationEvent@@0P6AK_KPEAU_EVENT_DESCRIPTOR@@KPEAU_EVENT_DATA_DESCRIPTOR@@@ZEA, rax; ulong (*CPublishWMIOperationEvent::m_fEventWrite)(unsigned __int64,_EVENT_DESCRIPTOR *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180021605  test    rax, rax
0x180021608  jz      loc_1800217C1
0x18002160e  lea     rdx, aEtweventactivi; "EtwEventActivityIdControl"
0x180021615  mov     rcx, rbx; hModule
0x180021618  call    cs:__imp_GetProcAddress
0x18002161e  mov     cs:?m_fEventActivityIdControl@CPublishWMIOperationEvent@@2P6AKKPEAU_GUID@@@ZEA, rax; ulong (*CPublishWMIOperationEvent::m_fEventActivityIdControl)(ulong,_GUID *)
0x180021625  test    rax, rax
0x180021628  jz      short loc_1800216A0
0x18002162a  lea     rdx, aEtweventwritet; "EtwEventWriteTransfer"
0x180021631  mov     rcx, rbx; hModule
0x180021634  call    cs:__imp_GetProcAddress
0x18002163a  mov     cs:?m_fEventWriteTransfer@CPublishWMIOperationEvent@@2P6AK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2KPEAU_EVENT_DATA_DESCRIPTOR@@@ZEA, rax; ulong (*CPublishWMIOperationEvent::m_fEventWriteTransfer)(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,ulong,_EVENT_DATA_DESCRIPTOR *)
0x180021641  test    rax, rax
0x180021644  jz      short loc_1800216A0
0x180021646  lea     rdx, aEtweventenable; "EtwEventEnabled"
0x18002164d  mov     rcx, rbx; hModule
0x180021650  call    cs:__imp_GetProcAddress
0x180021656  mov     cs:?m_fEventEnabled@CPublishWMIOperationEvent@@0P6AE_KPEBU_EVENT_DESCRIPTOR@@@ZEA, rax; uchar (*CPublishWMIOperationEvent::m_fEventEnabled)(unsigned __int64,_EVENT_DESCRIPTOR const *)
0x18002165d  test    rax, rax
0x180021660  jz      short loc_1800216A0
0x180021662  mov     cs:?m_hAdvAPI32@CPublishWMIOperationEvent@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * CPublishWMIOperationEvent::m_hAdvAPI32
0x180021669  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18002166e  call    cs:__imp_LeaveCriticalSection
0x180021674  jmp     loc_180021550
0x180021679  cmp     byte ptr [rcx+19h], 2
0x18002167d  jb      loc_18002156D
0x180021683  mov     edx, 1Eh
0x180021688  xor     r9d, r9d
0x18002168b  lea     r8, WPP_f6063e9a384b39fc8c4cb2f534a59449_Traceguids
0x180021692  mov     rcx, [rcx+10h]
0x180021696  call    WPP_SF_D
0x18002169b  jmp     loc_18002156D
0x1800216a0  call    cs:__imp_GetLastError
0x1800216a6  test    eax, eax
0x1800216a8  jle     short loc_1800216B2
0x1800216aa  movzx   eax, ax
0x1800216ad  or      eax, 80070000h
0x1800216b2  mov     ebx, eax
0x1800216b4  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1800216b9  call    cs:__imp_LeaveCriticalSection
0x1800216bf  mov     eax, ebx
0x1800216c1  jmp     loc_18002156F
0x1800216c6  call    cs:__imp_GetLastError
0x1800216cc  mov     ebx, eax
0x1800216ce  test    eax, eax
0x1800216d0  jle     short loc_1800216DB
0x1800216d2  movzx   ebx, ax
0x1800216d5  or      ebx, 80070000h
0x1800216db  test    ebx, ebx
0x1800216dd  js      loc_180021830
0x1800216e3  lea     rax, WPP_GLOBAL_Control
0x1800216ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216f1  cmp     rcx, rax
0x1800216f4  jz      short loc_1800216B4
0x1800216f6  test    byte ptr [rcx+1Ch], 1
0x1800216fa  jz      short loc_1800216B4
0x1800216fc  cmp     byte ptr [rcx+19h], 2
0x180021700  jb      short loc_1800216B4
0x180021702  mov     edx, 17h
0x180021707  jmp     loc_180021818
0x18002170c  call    cs:__imp_GetLastError
0x180021712  mov     ebx, eax
0x180021714  test    eax, eax
0x180021716  jle     short loc_180021721
0x180021718  movzx   ebx, ax
0x18002171b  or      ebx, 80070000h
0x180021721  test    ebx, ebx
0x180021723  jns     short loc_180021733
0x180021725  mov     edx, ebx; int
0x180021727  lea     rcx, qword_18006A9C0; this
0x18002172e  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180021733  lea     rax, WPP_GLOBAL_Control
0x18002173a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021741  cmp     rcx, rax
0x180021744  jz      loc_1800216B4
0x18002174a  test    byte ptr [rcx+1Ch], 1
0x18002174e  jz      loc_1800216B4
0x180021754  cmp     byte ptr [rcx+19h], 2
0x180021758  jb      loc_1800216B4
0x18002175e  mov     edx, 16h
0x180021763  jmp     loc_180021818
0x180021768  call    cs:__imp_GetLastError
0x18002176e  mov     ebx, eax
0x180021770  test    eax, eax
0x180021772  jle     short loc_18002177D
0x180021774  movzx   ebx, ax
0x180021777  or      ebx, 80070000h
0x18002177d  test    ebx, ebx
0x18002177f  jns     short loc_18002178F
0x180021781  mov     edx, ebx; int
0x180021783  lea     rcx, qword_18006A9C0; this
0x18002178a  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002178f  lea     rax, WPP_GLOBAL_Control
0x180021796  mov     rcx, cs:WPP_GLOBAL_Control
0x18002179d  cmp     rcx, rax
0x1800217a0  jz      loc_1800216B4
0x1800217a6  test    byte ptr [rcx+1Ch], 1
0x1800217aa  jz      loc_1800216B4
0x1800217b0  cmp     byte ptr [rcx+19h], 2
0x1800217b4  jb      loc_1800216B4
0x1800217ba  mov     edx, 18h
0x1800217bf  jmp     short loc_180021818
0x1800217c1  call    cs:__imp_GetLastError
0x1800217c7  mov     ebx, eax
0x1800217c9  test    eax, eax
0x1800217cb  jle     short loc_1800217D6
0x1800217cd  movzx   ebx, ax
0x1800217d0  or      ebx, 80070000h
0x1800217d6  test    ebx, ebx
0x1800217d8  jns     short loc_1800217E8
0x1800217da  mov     edx, ebx; int
0x1800217dc  lea     rcx, qword_18006A9C0; this
0x1800217e3  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800217e8  lea     rax, WPP_GLOBAL_Control
0x1800217ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800217f6  cmp     rcx, rax
0x1800217f9  jz      loc_1800216B4
0x1800217ff  test    byte ptr [rcx+1Ch], 1
0x180021803  jz      loc_1800216B4
0x180021809  cmp     byte ptr [rcx+19h], 2
0x18002180d  jb      loc_1800216B4
0x180021813  mov     edx, 19h
0x180021818  mov     r9d, ebx
0x18002181b  lea     r8, WPP_f6063e9a384b39fc8c4cb2f534a59449_Traceguids
0x180021822  mov     rcx, [rcx+10h]
0x180021826  call    WPP_SF_D
0x18002182b  jmp     loc_1800216B4
0x180021830  mov     edx, ebx; int
0x180021832  lea     rcx, qword_18006A9C0; this
0x180021839  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002183e  jmp     loc_1800216E3
```

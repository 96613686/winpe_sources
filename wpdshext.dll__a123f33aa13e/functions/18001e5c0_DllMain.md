# DllMain

- ea: `0x18001e5c0`
- end: `0x18001ea68`
- name: `DllMain`
- size: `1192`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180035404`

## callees

- `0x18001e5c0`
- `0x18001ea70`
- `0x18001eaf8`
- `0x18002e9f0`
- `0x180041ab0`
- `0x18006d490`
- `0x18006ef64`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18001e6d2`
- `KERNEL32!InitializeCriticalSection` at `0x18001e6df`
- `KERNEL32!InitializeCriticalSection` at `0x18001e6ec`
- `KERNEL32!InitializeCriticalSection` at `0x18001e6d2`
- `KERNEL32!InitializeCriticalSection` at `0x18001e6df`
- `KERNEL32!InitializeCriticalSection` at `0x18001e6ec`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9b8`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9c5`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9d2`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9b8`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9c5`
- `KERNEL32!DeleteCriticalSection` at `0x18001e9d2`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001e6c5`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18001e6c5`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e761`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e821`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e97d`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e761`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e821`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e97d`
- `KERNEL32!QueryPerformanceFrequency` at `0x18001e77c`
- `KERNEL32!QueryPerformanceFrequency` at `0x18001e77c`
- `KERNEL32!GetCurrentThreadId` at `0x18001e91f`
- `KERNEL32!GetCurrentThreadId` at `0x18001e91f`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18001e6a2`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18001e6a2`
- `ADVAPI32!UnregisterTraceGuids` at `0x18001e9df`
- `ADVAPI32!UnregisterTraceGuids` at `0x18001e9df`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v5; // r9
  int v6; // eax
  _DWORD *v7; // rcx
  signed int LowPart; // ecx
  signed int v9; // ebx
  PVOID *v10; // rax
  double v11; // xmm1_8
  DWORD CurrentThreadId; // eax
  const unsigned __int16 *CommandName; // rax
  char v14; // cl
  char v15; // r8
  int v16; // [rsp+48h] [rbp-90h]
  int v17; // [rsp+58h] [rbp-80h]
  __int64 v18; // [rsp+70h] [rbp-68h]
  LARGE_INTEGER v19[2]; // [rsp+80h] [rbp-58h] BYREF
  __int128 v20; // [rsp+90h] [rbp-48h]
  LARGE_INTEGER Frequency; // [rsp+A0h] [rbp-38h] BYREF
  char v22; // [rsp+A8h] [rbp-30h]
  LARGE_INTEGER PerformanceCount; // [rsp+F8h] [rbp+20h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_180095AC8 = 0;
      WPP_MAIN_CB = 0;
      qword_180095AD0 = 1;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuidWpdShellExtension;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WppInitUm(hinstDLL, fdwReason, lpvReserved);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids);
      v5 = RegisterTraceGuidsW(
             ETWControlCallback,
             &g_EtwContext,
             &ETWWpdShExtControlGuid,
             1u,
             &TraceGuidReg,
             0,
             0,
             &g_EtwContext);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids, v5);
      g_hInst = hinstDLL;
      DisableThreadLibraryCalls(hinstDLL);
      InitializeCriticalSection(&g_csDllRef);
      InitializeCriticalSection(&g_csGdiPlus);
      InitializeCriticalSection(&g_csDeviceCache);
      v18 = 0;
      v22 = 0;
      *(_OWORD *)&v19[0].LowPart = 0;
      v20 = 0;
      Frequency.QuadPart = 0;
      v6 = 0;
      v7 = WPP_GLOBAL_Control;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
      {
        QueryPerformanceCounter(v19);
        v18 = 1;
        v20 = 0;
        v22 = 1;
        v6 = 1;
        v7 = WPP_GLOBAL_Control;
      }
      PerformanceCount.QuadPart = 0;
      if ( v6 == 1 && (v7[7] & 0x800) != 0 )
      {
        QueryPerformanceCounter(&PerformanceCount);
        LowPart = Frequency.LowPart;
        if ( Frequency.QuadPart
          || QueryPerformanceFrequency(&Frequency) && (LowPart = Frequency.LowPart, Frequency.QuadPart) )
        {
          v9 = PerformanceCount.LowPart - v19[0].LowPart;
          switch ( (int)v18 )
          {
            case 1:
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
                goto LABEL_23;
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, &WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids);
              LowPart = Frequency.LowPart;
              goto LABEL_21;
            case 2:
            case 4:
            case 5:
            case 6:
            case 7:
            case 8:
            case 9:
            case 10:
            case 11:
LABEL_21:
              v10 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_23;
            default:
              v10 = (PVOID *)WPP_GLOBAL_Control;
              if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
              {
LABEL_23:
                if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x800) != 0 )
                {
                  v11 = (double)v9 / (double)LowPart * 1000.0;
                  CurrentThreadId = GetCurrentThreadId();
                  CommandName = CPerfTraceHelper::GetCommandName((CPerfTraceHelper *)CurrentThreadId, v18);
                  WPP_SF_dDSdiddddDS(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v15,
                    (__int64)CommandName,
                    v14,
                    0,
                    (int)v11,
                    v16,
                    SBYTE4(v18),
                    v17,
                    0,
                    (__int64)L"N/A");
                }
                QueryPerformanceCounter(&v19[1]);
                v22 = 0;
              }
              break;
          }
        }
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids);
    DeleteCriticalSection(&g_csDllRef);
    DeleteCriticalSection(&g_csGdiPlus);
    DeleteCriticalSection(&g_csDeviceCache);
    UnregisterTraceGuids(g_EtwContext);
    g_EtwContext = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids);
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x18001e5c0  mov     [rsp+arg_0], rbx
0x18001e5c5  mov     [rsp+arg_8], rsi
0x18001e5ca  push    rdi
0x18001e5cb  push    r14
0x18001e5cd  push    r15
0x18001e5cf  sub     rsp, 0C0h
0x18001e5d6  movaps  [rsp+0D8h+var_28], xmm6
0x18001e5de  mov     rbx, rcx
0x18001e5e1  mov     r14d, 1
0x18001e5e7  test    edx, edx
0x18001e5e9  jz      loc_18001E998
0x18001e5ef  cmp     edx, r14d
0x18001e5f2  jz      short loc_18001E615
0x18001e5f4  mov     eax, r14d
0x18001e5f7  lea     r11, [rsp+0D8h+var_18]
0x18001e5ff  mov     rbx, [r11+20h]
0x18001e603  mov     rsi, [r11+28h]
0x18001e607  movaps  xmm6, xmmword ptr [r11-10h]
0x18001e60c  mov     rsp, r11
0x18001e60f  pop     r15
0x18001e611  pop     r14
0x18001e613  pop     rdi
0x18001e614  retn
0x18001e615  xor     r15d, r15d
0x18001e618  mov     cs:qword_180095AC8, r15
0x18001e61f  mov     cs:WPP_MAIN_CB, r15
0x18001e626  mov     cs:qword_180095AD0, 1
0x18001e631  lea     rax, WPP_ThisDir_CTLGUID_CtlGuidWpdShellExtension
0x18001e638  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18001e63f  lea     rax, WPP_MAIN_CB
0x18001e646  mov     cs:WPP_GLOBAL_Control, rax
0x18001e64d  call    WppInitUm
0x18001e652  lea     rdi, WPP_GLOBAL_Control
0x18001e659  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e660  cmp     rcx, rdi
0x18001e663  jz      short loc_18001E66F
0x18001e665  test    byte ptr [rcx+1Ch], 40h
0x18001e669  jnz     loc_18001E7D1
0x18001e66f  lea     rdx, ?g_EtwContext@@3UEtwContext@@A; RequestContext
0x18001e676  mov     [rsp+0D8h+RegistrationHandle], rdx; RegistrationHandle
0x18001e67b  mov     [rsp+0D8h+MofResourceName], r15; MofResourceName
0x18001e680  mov     [rsp+0D8h+MofImagePath], r15; MofImagePath
0x18001e685  lea     rax, ?TraceGuidReg@@3PAU_TRACE_GUID_REGISTRATION@@A; _TRACE_GUID_REGISTRATION near * TraceGuidReg
0x18001e68c  mov     [rsp+0D8h+TraceGuidReg], rax; TraceGuidReg
0x18001e691  mov     r9d, r14d; GuidCount
0x18001e694  lea     r8, ETWWpdShExtControlGuid; ControlGuid
0x18001e69b  lea     rcx, ?ETWControlCallback@@YAKW4WMIDPREQUESTCODE@@PEAXPEAK1@Z; RequestAddress
0x18001e6a2  call    cs:__imp_RegisterTraceGuidsW
0x18001e6a8  mov     r9d, eax
0x18001e6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6b2  cmp     rcx, rdi
0x18001e6b5  jnz     loc_18001E7EB
0x18001e6bb  mov     cs:g_hInst, rbx
0x18001e6c2  mov     rcx, rbx; hLibModule
0x18001e6c5  call    cs:__imp_DisableThreadLibraryCalls
0x18001e6cb  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e6d2  call    cs:__imp_InitializeCriticalSection
0x18001e6d8  lea     rcx, ?g_csGdiPlus@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e6df  call    cs:__imp_InitializeCriticalSection
0x18001e6e5  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e6ec  call    cs:__imp_InitializeCriticalSection
0x18001e6f2  mov     qword ptr [rsp+0D8h+var_68], r15
0x18001e6f7  mov     qword ptr [rsp+0D8h+var_60], r15
0x18001e6fc  mov     [rsp+0D8h+var_30], r15b
0x18001e704  xorps   xmm0, xmm0
0x18001e707  movdqa  xmmword ptr [rsp+0D8h+var_58], xmm0
0x18001e710  xorps   xmm1, xmm1
0x18001e713  movdqa  [rsp+0D8h+var_48], xmm1
0x18001e71c  mov     qword ptr [rsp+0D8h+Frequency], r15
0x18001e724  mov     eax, r15d
0x18001e727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e72e  test    dword ptr [rcx+1Ch], 800h
0x18001e735  jnz     loc_18001E819
0x18001e73b  mov     qword ptr [rsp+0D8h+PerformanceCount], r15
0x18001e743  cmp     eax, 1
0x18001e746  jnz     loc_18001E98B
0x18001e74c  test    dword ptr [rcx+1Ch], 800h
0x18001e753  jz      loc_18001E98B
0x18001e759  lea     rcx, [rsp+0D8h+PerformanceCount]; lpPerformanceCount
0x18001e761  call    cs:__imp_QueryPerformanceCounter
0x18001e767  mov     rcx, qword ptr [rsp+0D8h+Frequency]
0x18001e76f  test    rcx, rcx
0x18001e772  jnz     short loc_18001E79B
0x18001e774  lea     rcx, [rsp+0D8h+Frequency]; lpFrequency
0x18001e77c  call    cs:__imp_QueryPerformanceFrequency
0x18001e782  test    eax, eax
0x18001e784  jz      loc_18001E98B
0x18001e78a  mov     rcx, qword ptr [rsp+0D8h+Frequency]
0x18001e792  test    rcx, rcx
0x18001e795  jz      loc_18001E98B
0x18001e79b  mov     rbx, qword ptr [rsp+0D8h+PerformanceCount]
0x18001e7a3  mov     rdx, qword ptr [rsp+0D8h+var_58]
0x18001e7ab  sub     rbx, rdx
0x18001e7ae  mov     eax, dword ptr [rsp+0D8h+var_68]
0x18001e7b2  dec     eax; switch 11 cases
0x18001e7b4  cmp     eax, 0Ah
0x18001e7b7  ja      def_18001E7CF; jumptable 000000018001E7CF default case, case 3
0x18001e7bd  lea     r8, __ImageBase
0x18001e7c4  mov     eax, ds:(jpt_18001E7CF - 180000000h)[r8+rax*4]
0x18001e7cc  add     rax, r8
0x18001e7cf  jmp     rax; switch jump
0x18001e7d1  mov     edx, 0Ah
0x18001e7d6  lea     r8, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids
0x18001e7dd  mov     rcx, [rcx+10h]
0x18001e7e1  call    WPP_SF_
0x18001e7e6  jmp     loc_18001E66F
0x18001e7eb  test    byte ptr [rcx+1Ch], 4
0x18001e7ef  jz      loc_18001E6BB
0x18001e7f5  mov     edx, 0Bh
0x18001e7fa  mov     eax, dword ptr cs:?g_EtwContext@@3UEtwContext@@A; EtwContext g_EtwContext
0x18001e800  mov     dword ptr [rsp+0D8h+TraceGuidReg], eax
0x18001e804  lea     r8, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids
0x18001e80b  mov     rcx, [rcx+10h]
0x18001e80f  call    WPP_SF_dd
0x18001e814  jmp     loc_18001E6BB
0x18001e819  lea     rcx, [rsp+0D8h+var_58]; lpPerformanceCount
0x18001e821  call    cs:__imp_QueryPerformanceCounter
0x18001e827  mov     qword ptr [rsp+0D8h+var_68], 1
0x18001e830  mov     qword ptr [rsp+0D8h+var_60], r15
0x18001e835  xorps   xmm0, xmm0
0x18001e838  movdqa  [rsp+0D8h+var_48], xmm0
0x18001e841  mov     [rsp+0D8h+var_30], 1
0x18001e849  mov     eax, r14d
0x18001e84c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e853  jmp     loc_18001E73B
0x18001e858  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018001E7CF case 1
0x18001e85f  cmp     rax, rdi
0x18001e862  jz      short loc_18001E8AF
0x18001e864  test    dword ptr [rax+1Ch], 800h
0x18001e86b  jz      short loc_18001E8AF
0x18001e86d  mov     edx, 7Dh ; '}'
0x18001e872  lea     r8, WPP_ca15e54dda593755eec8c8e0194d7ab1_Traceguids
0x18001e879  mov     rcx, [rax+10h]
0x18001e87d  call    WPP_SF_
0x18001e882  mov     rcx, qword ptr [rsp+0D8h+Frequency]
0x18001e88a  mov     rdx, qword ptr [rsp+0D8h+var_58]
0x18001e892  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018001E7CF cases 2,4-11
0x18001e899  jmp     short loc_18001E8AF
0x18001e89b  mov     rax, cs:WPP_GLOBAL_Control; jumptable 000000018001E7CF default case, case 3
0x18001e8a2  test    dword ptr [rax+1Ch], 1000h
0x18001e8a9  jz      loc_18001E98B
0x18001e8af  mov     r8, qword ptr [rsp+0D8h+var_58+8]
0x18001e8b7  movsd   xmm2, cs:__real@408f400000000000
0x18001e8bf  test    r8, r8
0x18001e8c2  jnz     short loc_18001E8C9
0x18001e8c4  xorps   xmm6, xmm6
0x18001e8c7  jmp     short loc_18001E8E7
0x18001e8c9  sub     rdx, r8
0x18001e8cc  xorps   xmm1, xmm1
0x18001e8cf  cvtsi2sd xmm1, rdx
0x18001e8d4  xorps   xmm0, xmm0
0x18001e8d7  cvtsi2sd xmm0, rcx
0x18001e8dc  divsd   xmm1, xmm0
0x18001e8e0  mulsd   xmm1, xmm2
0x18001e8e4  movaps  xmm6, xmm1
0x18001e8e7  cmp     rax, rdi
0x18001e8ea  jz      loc_18001E975
0x18001e8f0  test    dword ptr [rax+1Ch], 800h
0x18001e8f7  jz      short loc_18001E975
0x18001e8f9  xorps   xmm1, xmm1
0x18001e8fc  cvtsi2sd xmm1, rbx
0x18001e901  xorps   xmm0, xmm0
0x18001e904  cvtsi2sd xmm0, rcx
0x18001e909  divsd   xmm1, xmm0
0x18001e90d  mulsd   xmm1, xmm2
0x18001e911  cvttsd2si rsi, xmm1
0x18001e916  mov     ebx, dword ptr [rsp+0D8h+var_68+4]
0x18001e91a  mov     rdi, qword ptr [rsp+0D8h+var_60]
0x18001e91f  call    cs:__imp_GetCurrentThreadId
0x18001e925  mov     ecx, eax; this
0x18001e927  mov     r8d, dword ptr [rsp+0D8h+var_68]
0x18001e92c  mov     edx, r8d; unsigned int
0x18001e92f  call    ?GetCommandName@CPerfTraceHelper@@QEAAPEBGK@Z; CPerfTraceHelper::GetCommandName(ulong)
0x18001e934  cvttsd2si r9, xmm6
0x18001e939  lea     rdx, aNA; "N/A"
0x18001e940  mov     [rsp+0D8h+var_70], rdx; __int64
0x18001e945  mov     dword ptr [rsp+0D8h+var_78], r15d; char
0x18001e94a  mov     dword ptr [rsp+0D8h+var_88], ebx; char
0x18001e94e  mov     dword ptr [rsp+0D8h+var_98], esi; char
0x18001e952  mov     [rsp+0D8h+RegistrationHandle], rdi; char
0x18001e957  mov     dword ptr [rsp+0D8h+MofResourceName], ecx; char
0x18001e95b  mov     [rsp+0D8h+MofImagePath], rax; __int64
0x18001e960  mov     dword ptr [rsp+0D8h+TraceGuidReg], r8d; char
0x18001e965  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e96c  mov     rcx, [rcx+10h]; LoggerHandle
0x18001e970  call    WPP_SF_dDSdiddddDS
0x18001e975  lea     rcx, [rsp+0D8h+var_58+8]; lpPerformanceCount
0x18001e97d  call    cs:__imp_QueryPerformanceCounter
0x18001e983  mov     [rsp+0D8h+var_30], r15b
0x18001e98b  jmp     loc_18001E5F4
0x18001e990  xor     r14d, r14d
0x18001e993  jmp     loc_18001E5F4
0x18001e998  lea     rdi, WPP_GLOBAL_Control
0x18001e99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9a6  cmp     rcx, rdi
0x18001e9a9  jz      short loc_18001E9B1
0x18001e9ab  test    byte ptr [rcx+1Ch], 40h
0x18001e9af  jnz     short loc_18001EA05
0x18001e9b1  lea     rcx, ?g_csDllRef@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e9b8  call    cs:__imp_DeleteCriticalSection
0x18001e9be  lea     rcx, ?g_csGdiPlus@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e9c5  call    cs:__imp_DeleteCriticalSection
0x18001e9cb  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e9d2  call    cs:__imp_DeleteCriticalSection
0x18001e9d8  mov     rcx, cs:?g_EtwContext@@3UEtwContext@@A; RegistrationHandle
0x18001e9df  call    cs:__imp_UnregisterTraceGuids
0x18001e9e5  xor     r15d, r15d
0x18001e9e8  mov     cs:?g_EtwContext@@3UEtwContext@@A, r15; EtwContext g_EtwContext
0x18001e9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e9f6  cmp     rcx, rdi
0x18001e9f9  jnz     short loc_18001EA1C
0x18001e9fb  call    WppCleanupUm
0x18001ea00  jmp     loc_18001E5F4
0x18001ea05  mov     edx, 0Ch
0x18001ea0a  lea     r8, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids
0x18001ea11  mov     rcx, [rcx+10h]
0x18001ea15  call    WPP_SF_
0x18001ea1a  jmp     short loc_18001E9B1
0x18001ea1c  test    byte ptr [rcx+1Ch], 4
0x18001ea20  jz      short loc_18001E9FB
0x18001ea22  mov     edx, 0Dh
0x18001ea27  lea     r8, WPP_663280d16d963a9d6ef44bf05fd9086d_Traceguids
0x18001ea2e  mov     rcx, [rcx+10h]
0x18001ea32  call    WPP_SF_
0x18001ea37  jmp     short loc_18001E9FB
```

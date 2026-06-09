# ListenerWorkerThreadProc(void *)

- ea: `0x180038060`
- end: `0x18003858d`
- name: `?ListenerWorkerThreadProc@@YAKPEAX@Z`
- size: `1325`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180005610`
- `0x1800063a0`
- `0x180006934`
- `0x180019a20`
- `0x180038060`
- `0x180038fa8`
- `0x180050710`
- `0x1800572d4`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003827f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038394`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038461`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038132`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003827f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038394`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038461`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800381b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038318`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800383d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038582`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800381b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038318`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800383d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038582`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180038425`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180038425`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038358`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038496`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800383ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038496`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180038224`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180038224`

## pseudocode

```c
__int64 __fastcall ListenerWorkerThreadProc(char *Parameter)
{
  int v2; // eax
  DWORD v3; // r15d
  int v4; // esi
  DWORD v5; // edi
  int v6; // esi
  __int64 v7; // rdx
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD LastError; // eax
  DWORD v13; // eax
  DWORD v14; // [rsp+60h] [rbp-79h] BYREF
  __int64 v15; // [rsp+68h] [rbp-71h] BYREF
  HANDLE hHandle[2]; // [rsp+70h] [rbp-69h] BYREF
  int v17; // [rsp+80h] [rbp-59h] BYREF
  char v18[14]; // [rsp+84h] [rbp-55h] BYREF
  __int128 v19; // [rsp+92h] [rbp-47h]
  int v20; // [rsp+A2h] [rbp-37h]
  __int16 v21; // [rsp+A6h] [rbp-33h]
  int v22; // [rsp+A8h] [rbp-31h]
  __int128 v23; // [rsp+ACh] [rbp-2Dh]
  __int128 v24; // [rsp+BCh] [rbp-1Dh]
  __int64 v25; // [rsp+CCh] [rbp-Dh]
  char v26; // [rsp+D4h] [rbp-5h]
  __int16 v27; // [rsp+D5h] [rbp-4h]
  char v28; // [rsp+D7h] [rbp-2h]
  int v29; // [rsp+D8h] [rbp-1h]

  *(_OWORD *)hHandle = 0;
  strcpy(v18, "PROXIMITY_OOB");
  v19 = 0;
  v14 = 0;
  v23 = 0;
  v15 = 0;
  v24 = 0;
  v17 = 6029569;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v25 = 257;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 36, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  v2 = *((_DWORD *)Parameter + 232);
  if ( v2 )
  {
    v3 = 0;
    v4 = 0;
    if ( (v2 & 0x20000) != 0 )
    {
      *((_DWORD *)Parameter + 232) = 524297;
      v5 = 1223;
      goto LABEL_13;
    }
    goto LABEL_8;
  }
  v5 = 0;
  v4 = *((_DWORD *)Parameter + 233);
  v3 = *((_DWORD *)Parameter + 126);
  hHandle[0] = *((HANDLE *)Parameter + 121);
  hHandle[1] = *((HANDLE *)Parameter + 122);
  if ( v4 == 1 )
  {
    *((_DWORD *)Parameter + 232) = 1;
  }
  else
  {
    if ( v4 != 2 )
    {
LABEL_8:
      v5 = 5023;
      goto LABEL_13;
    }
    *((_DWORD *)Parameter + 232) = 65542;
  }
LABEL_13:
  LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
  if ( v5 )
    goto LABEL_17;
  v6 = v4 - 1;
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
    }
    v11 = WaitForMultipleObjectsEx(2u, hHandle, 0, v3, 0);
    v14 = v11;
    if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v11);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    if ( (*((_DWORD *)Parameter + 232) & 0x20000) != 0 || !v14 )
    {
      *((_DWORD *)Parameter + 232) = 524297;
      v5 = 1223;
    }
    else
    {
      if ( v14 == 1 )
      {
        *((_DWORD *)Parameter + 232) = 5;
        goto LABEL_62;
      }
      if ( v14 != 258 )
      {
        LastError = GetLastError();
        *((_DWORD *)Parameter + 232) = 524298;
        v5 = LastError;
        if ( LastError )
          goto LABEL_70;
LABEL_62:
        v13 = WFDAcceptGroupRequestAndOpenSessionLib(
                *((void **)Parameter + 7),
                *((_QWORD *)Parameter + 120),
                *((_DWORD *)Parameter + 103),
                (__int64)(Parameter + 416),
                (__int64)&v17,
                0,
                0,
                (__int64)&v15,
                &v14,
                (__int64)(Parameter + 936),
                (_QWORD *)Parameter + 115);
        v5 = v13;
        if ( v13 )
        {
          if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 105)
            && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v13);
          }
          *((_DWORD *)Parameter + 232) = 524298;
        }
        else
        {
          *((_DWORD *)Parameter + 232) = 262151;
        }
        goto LABEL_70;
      }
      *((_DWORD *)Parameter + 232) = 524296;
      v5 = 1460;
    }
LABEL_70:
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    goto LABEL_17;
  }
  if ( v6 == 1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    if ( (*((_DWORD *)Parameter + 232) & 0x20000) == 0 )
    {
      v9 = WFDStartOpenSessionLib(
             *((void **)Parameter + 7),
             (unsigned __int8 (*)[6])(Parameter + 512),
             Parameter,
             (void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int))OpenSessionCompleteCallback,
             0,
             0,
             (void **)Parameter + 115);
      v5 = v9;
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 105)
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 37, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v9);
        }
        *((_DWORD *)Parameter + 232) = 524298;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    if ( !v5 )
    {
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids);
      }
      v10 = WaitForSingleObject(hHandle[1], 0xFFFFFFFF);
      v14 = v10;
      if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v10);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
      if ( (*((_DWORD *)Parameter + 232) & 0x20000) != 0 )
      {
        v5 = 1223;
        *((_DWORD *)Parameter + 232) = 524297;
      }
      else if ( v14 )
      {
        v5 = GetLastError();
        *((_DWORD *)Parameter + 232) = 524298;
      }
      else
      {
        v5 = *((_DWORD *)Parameter + 238);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 8));
    }
  }
  else
  {
    v5 = 5023;
  }
LABEL_17:
  (*((void (__fastcall **)(_QWORD, char *, _QWORD, _QWORD))Parameter + 10))(
    *(_QWORD *)Parameter,
    Parameter + 936,
    *((_QWORD *)Parameter + 11),
    v5);
  if ( v15 )
    FreeWLMem(v15);
  WFDOobHelperSetPCDiscoverable(0, (struct _WFD_OOB_SESSION_CONTEXT *)Parameter);
  v7 = *(_QWORD *)Parameter;
  *((_DWORD *)Parameter + 17) = 0;
  HtDereferenceHandleWithTag(g_hHandleTable, v7, 0, 1);
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids, v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180038060  push    rbp
0x180038062  push    rbx
0x180038063  push    rsi
0x180038064  push    rdi
0x180038065  push    r12
0x180038067  push    r13
0x180038069  push    r14
0x18003806b  push    r15
0x18003806d  lea     rbp, [rsp-1Fh]
0x180038072  sub     rsp, 0F8h
0x180038079  mov     rax, cs:__security_cookie
0x180038080  xor     rax, rsp
0x180038083  mov     [rbp+57h+var_50], rax
0x180038087  mov     eax, dword ptr cs:aProximityOob+8; "Y_OOB"
0x18003808d  xor     r12d, r12d
0x180038090  xorps   xmm0, xmm0
0x180038093  mov     dword ptr [rbp+57h+var_AC+8], eax
0x180038096  movzx   eax, word ptr cs:aProximityOob+0Ch; "B"
0x18003809d  mov     rbx, rcx
0x1800380a0  movups  xmmword ptr [rbp+57h+hHandle], xmm0
0x1800380a4  mov     word ptr [rbp+57h+var_AC+0Ch], ax
0x1800380a8  xor     eax, eax
0x1800380aa  movsd   xmm0, qword ptr cs:aProximityOob; "PROXIMITY_OOB"
0x1800380b2  movsd   qword ptr [rbp+57h+var_AC], xmm0
0x1800380b7  xorps   xmm0, xmm0
0x1800380ba  movups  [rbp+57h+var_9E], xmm0
0x1800380be  mov     [rbp+57h+var_D0], r12d
0x1800380c2  movups  [rbp+57h+var_84], xmm0
0x1800380c6  mov     [rbp+57h+var_C8], r12
0x1800380ca  movups  [rbp+57h+var_74], xmm0
0x1800380ce  mov     [rbp+57h+var_B0], 5C0101h
0x1800380d5  mov     [rbp+57h+var_8E], eax
0x1800380d8  mov     [rbp+57h+var_8A], ax
0x1800380dc  mov     [rbp+57h+var_88], r12d
0x1800380e0  mov     [rbp+57h+var_64], 101h
0x1800380e8  mov     [rbp+57h+var_5C], r12b
0x1800380ec  mov     [rbp+57h+var_5B], ax
0x1800380f0  mov     [rbp+57h+var_59], al
0x1800380f3  mov     [rbp+57h+var_58], r12d
0x1800380f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380fe  lea     rax, WPP_GLOBAL_Control
0x180038105  cmp     rcx, rax
0x180038108  jz      short loc_18003812B
0x18003810a  cmp     byte ptr [rcx+69h], 4
0x18003810e  jb      short loc_18003812B
0x180038110  test    byte ptr [rcx+6Ch], 2
0x180038114  jz      short loc_18003812B
0x180038116  mov     rcx, [rcx+60h]
0x18003811a  lea     edx, [r12+24h]
0x18003811f  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038126  call    WPP_SF_
0x18003812b  lea     r14, [rbx+8]
0x18003812f  mov     rcx, r14; lpCriticalSection
0x180038132  call    cs:__imp_EnterCriticalSection
0x180038138  mov     eax, [rbx+3A0h]
0x18003813e  mov     r13d, 139Fh
0x180038144  test    eax, eax
0x180038146  jz      short loc_18003816A
0x180038148  mov     r15d, r12d
0x18003814b  mov     esi, r12d
0x18003814e  bt      eax, 11h
0x180038152  jnb     short loc_180038165
0x180038154  mov     dword ptr [rbx+3A0h], 80009h
0x18003815e  mov     edi, 4C7h
0x180038163  jmp     short loc_1800381B2
0x180038165  mov     edi, r13d
0x180038168  jmp     short loc_1800381B2
0x18003816a  mov     rax, [rbx+3C8h]
0x180038171  mov     edi, r12d
0x180038174  mov     esi, [rbx+3A4h]
0x18003817a  mov     ecx, esi
0x18003817c  mov     r15d, [rbx+1F8h]
0x180038183  mov     [rbp+57h+hHandle], rax
0x180038187  mov     rax, [rbx+3D0h]
0x18003818e  mov     [rbp+57h+hHandle+8], rax
0x180038192  sub     ecx, 1
0x180038195  jz      short loc_1800381A8
0x180038197  cmp     ecx, 1
0x18003819a  jnz     short loc_180038165
0x18003819c  mov     dword ptr [rbx+3A0h], 10006h
0x1800381a6  jmp     short loc_1800381B2
0x1800381a8  mov     dword ptr [rbx+3A0h], 1
0x1800381b2  mov     rcx, r14; lpCriticalSection
0x1800381b5  call    cs:__imp_LeaveCriticalSection
0x1800381bb  test    edi, edi
0x1800381bd  jnz     short loc_1800381D4
0x1800381bf  sub     esi, 1
0x1800381c2  jz      loc_1800383DE
0x1800381c8  cmp     esi, 1
0x1800381cb  jz      loc_18003827C
0x1800381d1  mov     edi, r13d
0x1800381d4  lea     r13, WPP_GLOBAL_Control
0x1800381db  mov     r8, [rbx+58h]
0x1800381df  lea     rdx, [rbx+3A8h]
0x1800381e6  mov     rcx, [rbx]
0x1800381e9  mov     r9d, edi
0x1800381ec  mov     rax, [rbx+50h]
0x1800381f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800381f5  mov     rcx, [rbp+57h+var_C8]
0x1800381f9  test    rcx, rcx
0x1800381fc  jz      short loc_180038203
0x1800381fe  call    FreeWLMem
0x180038203  mov     rdx, rbx; struct _WFD_OOB_SESSION_CONTEXT *
0x180038206  xor     ecx, ecx; int
0x180038208  call    ?WFDOobHelperSetPCDiscoverable@@YAKHPEAU_WFD_OOB_SESSION_CONTEXT@@@Z; WFDOobHelperSetPCDiscoverable(int,_WFD_OOB_SESSION_CONTEXT *)
0x18003820d  mov     rdx, [rbx]
0x180038210  mov     r9d, 1
0x180038216  mov     [rbx+44h], r12d
0x18003821a  xor     r8d, r8d
0x18003821d  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180038224  call    cs:__imp_HtDereferenceHandleWithTag
0x18003822a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038231  cmp     rcx, r13
0x180038234  jz      short loc_18003825A
0x180038236  cmp     byte ptr [rcx+69h], 4
0x18003823a  jb      short loc_18003825A
0x18003823c  test    byte ptr [rcx+6Ch], 2
0x180038240  jz      short loc_18003825A
0x180038242  mov     rcx, [rcx+60h]
0x180038246  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x18003824d  mov     edx, 2Bh ; '+'
0x180038252  mov     r9d, edi
0x180038255  call    WPP_SF_d
0x18003825a  mov     eax, edi
0x18003825c  mov     rcx, [rbp+57h+var_50]
0x180038260  xor     rcx, rsp; StackCookie
0x180038263  call    __security_check_cookie
0x180038268  add     rsp, 0F8h
0x18003826f  pop     r15
0x180038271  pop     r14
0x180038273  pop     r13
0x180038275  pop     r12
0x180038277  pop     rdi
0x180038278  pop     rsi
0x180038279  pop     rbx
0x18003827a  pop     rbp
0x18003827b  retn
0x18003827c  mov     rcx, r14; lpCriticalSection
0x18003827f  call    cs:__imp_EnterCriticalSection
0x180038285  mov     r15d, 20000h
0x18003828b  mov     esi, 8000Ah
0x180038290  test    [rbx+3A0h], r15d
0x180038297  jnz     short loc_18003830E
0x180038299  mov     rcx, [rbx+38h]; void *
0x18003829d  lea     rax, [rbx+398h]
0x1800382a4  mov     [rsp+130h+var_100], rax; void **
0x1800382a9  lea     rdx, [rbx+200h]; unsigned __int8 (*)[6]
0x1800382b0  mov     [rsp+130h+var_108], r12; struct _WFD_FIREWALL_CONFIGURATION_PARAMETERS *
0x1800382b5  lea     r9, ?OpenSessionCompleteCallback@@YAXPEAX0U_GUID@@KK@Z; void (*)(void *, void *, struct _GUID *__struct_ptr, unsigned int, unsigned int)
0x1800382bc  mov     r8, rbx; void *
0x1800382bf  mov     qword ptr [rsp+130h+bAlertable], r12; unsigned __int16 *
0x1800382c4  call    ?WFDStartOpenSessionLib@@YAKPEAXPEAY05E0P6AX00U_GUID@@KK@ZPEAGPEBU_WFD_FIREWALL_CONFIGURATION_PARAMETERS@@PEAPEAX@Z; WFDStartOpenSessionLib(void *,uchar (*)[6],void *,void (*)(void *,void *,_GUID,ulong,ulong),ushort *,_WFD_FIREWALL_CONFIGURATION_PARAMETERS const *,void * *)
0x1800382c9  mov     edi, eax
0x1800382cb  test    eax, eax
0x1800382cd  jz      short loc_18003830E
0x1800382cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382d6  lea     r13, WPP_GLOBAL_Control
0x1800382dd  cmp     rcx, r13
0x1800382e0  jz      short loc_180038306
0x1800382e2  cmp     byte ptr [rcx+69h], 1
0x1800382e6  jb      short loc_180038306
0x1800382e8  test    byte ptr [rcx+6Ch], 2
0x1800382ec  jz      short loc_180038306
0x1800382ee  mov     rcx, [rcx+60h]
0x1800382f2  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x1800382f9  mov     edx, 25h ; '%'
0x1800382fe  mov     r9d, eax
0x180038301  call    WPP_SF_d
0x180038306  mov     [rbx+3A0h], esi
0x18003830c  jmp     short loc_180038315
0x18003830e  lea     r13, WPP_GLOBAL_Control
0x180038315  mov     rcx, r14; lpCriticalSection
0x180038318  call    cs:__imp_LeaveCriticalSection
0x18003831e  test    edi, edi
0x180038320  jnz     loc_1800381D4
0x180038326  mov     rcx, cs:WPP_GLOBAL_Control
0x18003832d  cmp     rcx, r13
0x180038330  jz      short loc_180038351
0x180038332  cmp     byte ptr [rcx+69h], 3
0x180038336  jb      short loc_180038351
0x180038338  test    byte ptr [rcx+6Ch], 2
0x18003833c  jz      short loc_180038351
0x18003833e  mov     rcx, [rcx+60h]
0x180038342  lea     edx, [rdi+26h]
0x180038345  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x18003834c  call    WPP_SF_
0x180038351  mov     rcx, [rbp+57h+hHandle+8]; hHandle
0x180038355  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180038358  call    cs:__imp_WaitForSingleObject
0x18003835e  mov     [rbp+57h+var_D0], eax
0x180038361  mov     rcx, cs:WPP_GLOBAL_Control
0x180038368  cmp     rcx, r13
0x18003836b  jz      short loc_180038391
0x18003836d  cmp     byte ptr [rcx+69h], 3
0x180038371  jb      short loc_180038391
0x180038373  test    byte ptr [rcx+6Ch], 2
0x180038377  jz      short loc_180038391
0x180038379  mov     rcx, [rcx+60h]
0x18003837d  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038384  mov     edx, 27h ; '''
0x180038389  mov     r9d, eax
0x18003838c  call    WPP_SF_d
0x180038391  mov     rcx, r14; lpCriticalSection
0x180038394  call    cs:__imp_EnterCriticalSection
0x18003839a  test    [rbx+3A0h], r15d
0x1800383a1  jz      short loc_1800383B4
0x1800383a3  mov     edi, 4C7h
0x1800383a8  mov     dword ptr [rbx+3A0h], 80009h
0x1800383b2  jmp     short loc_1800383D0
0x1800383b4  cmp     [rbp+57h+var_D0], r12d
0x1800383b8  jz      short loc_1800383CA
0x1800383ba  call    cs:__imp_GetLastError
0x1800383c0  mov     edi, eax
0x1800383c2  mov     [rbx+3A0h], esi
0x1800383c8  jmp     short loc_1800383D0
0x1800383ca  mov     edi, [rbx+3B8h]
0x1800383d0  mov     rcx, r14; lpCriticalSection
0x1800383d3  call    cs:__imp_LeaveCriticalSection
0x1800383d9  jmp     loc_1800381D4
0x1800383de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383e5  lea     r13, WPP_GLOBAL_Control
0x1800383ec  cmp     rcx, r13
0x1800383ef  jz      short loc_180038412
0x1800383f1  cmp     byte ptr [rcx+69h], 3
0x1800383f5  jb      short loc_180038412
0x1800383f7  test    byte ptr [rcx+6Ch], 2
0x1800383fb  jz      short loc_180038412
0x1800383fd  mov     rcx, [rcx+60h]
0x180038401  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038408  mov     edx, 28h ; '('
0x18003840d  call    WPP_SF_
0x180038412  xor     r8d, r8d; bWaitAll
0x180038415  mov     [rsp+130h+bAlertable], r12d; bAlertable
0x18003841a  mov     r9d, r15d; dwMilliseconds
0x18003841d  lea     rdx, [rbp+57h+hHandle]; lpHandles
0x180038421  lea     ecx, [r8+2]; nCount
0x180038425  call    cs:__imp_WaitForMultipleObjectsEx
0x18003842b  mov     [rbp+57h+var_D0], eax
0x18003842e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038435  cmp     rcx, r13
0x180038438  jz      short loc_18003845E
0x18003843a  cmp     byte ptr [rcx+69h], 3
0x18003843e  jb      short loc_18003845E
0x180038440  test    byte ptr [rcx+6Ch], 2
0x180038444  jz      short loc_18003845E
0x180038446  mov     rcx, [rcx+60h]
0x18003844a  lea     r8, WPP_6a45f3c8267e3d160d06543ac6d2b2a5_Traceguids
0x180038451  mov     edx, 29h ; ')'
0x180038456  mov     r9d, eax
0x180038459  call    WPP_SF_d
0x18003845e  mov     rcx, r14; lpCriticalSection
0x180038461  call    cs:__imp_EnterCriticalSection
0x180038467  mov     r15d, 20000h
0x18003846d  test    [rbx+3A0h], r15d
0x180038474  jnz     loc_180038570
0x18003847a  mov     eax, [rbp+57h+var_D0]
0x18003847d  test    eax, eax
0x18003847f  jz      loc_180038570
0x180038485  mov     esi, 8000Ah
0x18003848a  sub     eax, 1
0x18003848d  jz      short loc_1800384C1
0x18003848f  cmp     eax, 101h
0x180038494  jz      short loc_1800384AD
0x180038496  call    cs:__imp_GetLastError
0x18003849c  mov     [rbx+3A0h], esi
0x1800384a2  mov     edi, eax
0x1800384a4  test    eax, eax
0x1800384a6  jz      short loc_1800384CB
0x1800384a8  jmp     loc_18003857F
0x1800384ad  mov     dword ptr [rbx+3A0h], 80008h
0x1800384b7  mov     edi, 5B4h
0x1800384bc  jmp     loc_18003857F
0x1800384c1  mov     dword ptr [rbx+3A0h], 5
0x1800384cb  mov     r8d, [rbx+19Ch]
0x1800384d2  lea     rax, [rbx+398h]
0x1800384d9  mov     rdx, [rbx+3C0h]
0x1800384e0  lea     rcx, [rbx+3A8h]
0x1800384e7  mov     [rsp+130h+var_E0], rax
0x1800384ec  lea     r9, [rbx+1A0h]
0x1800384f3  mov     [rsp+130h+var_E8], rcx
0x1800384f8  lea     rax, [rbp+57h+var_D0]
0x1800384fc  mov     rcx, [rbx+38h]
0x180038500  mov     [rsp+130h+var_F0], rax
0x180038505  lea     rax, [rbp+57h+var_C8]
0x180038509  mov     [rsp+130h+var_F8], rax
0x18003850e  lea     rax, [rbp+57h+var_B0]
0x180038512  mov     [rsp+130h+var_100], r12
0x180038517  mov     [rsp+130h+var_108], r12
0x18003851c  mov     qword ptr [rsp+130h+bAlertable], rax
0x180038521  call    ?WFDAcceptGroupRequestAndOpenSessionLib@@YAKPEAX0W4_DOT11_WPS_CONFIG_METHOD@@PEAU_WFD_WPS_INFO@@PEAU_WFD_PAIRING_PARAMETERS@@PEAU_WFD_VERTICAL_PAIRING_INFO@@PEAPEAU4@PEAPEAGPEAKPEAU_GUID@@PEAPEAX@Z; WFDAcceptGroupRequestAndOpenSessionLib(void *,void *,_DOT11_WPS_CONFIG_METHOD,_WFD_WPS_INFO *,_WFD_PAIRING_PARAMETERS *,_WFD_VERTICAL_PAIRING_INFO *,_WFD_VERTICAL_PAIRING_INFO * *,ushort * *,ulong *,_GUID *,void * *)
0x180038526  mov     edi, eax
0x180038528  test    eax, eax
0x18003852a  jz      short loc_180038564
0x18003852c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038533  cmp     rcx, r13
0x180038536  jz      short loc_18003855C
0x180038538  cmp     byte ptr [rcx+69h], 1
0x18003853c  jb      short loc_18003855C
0x18003853e  test    byte ptr [rcx+6Ch], 2
0x180038542  jz      short loc_18003855C
  ... truncated ...
```

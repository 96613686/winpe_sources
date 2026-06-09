# EvaluateWanConnectivity(ulong *)

- ea: `0x180001850`
- end: `0x180001d5f`
- name: `?EvaluateWanConnectivity@@YAHPEAK@Z`
- size: `1295`
- prototype: `__int64 __fastcall(unsigned int *Parameter)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callers

- `0x180001590`

## callees

- `0x180001470`
- `0x180001850`
- `0x180001d70`
- `0x1800030a0`
- `0x180004c20`
- `0x1800082b4`
- `0x180008300`
- `0x1800093b0`
- `0x180009b4c`
- `0x180009f64`
- `0x180009fc0`
- `0x18000a060`
- `0x18000a7a0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001986`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001986`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001a35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001bf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c53`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ac9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001ac9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001871`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001871`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001bdf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001bdf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001b35`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001b35`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001bc9`

## string_xrefs

- `0x180001b2c`: `RasApi32.dll`

## pseudocode

```c
__int64 __fastcall EvaluateWanConnectivity(unsigned int *Parameter)
{
  unsigned __int16 *v2; // rsi
  DWORD TickCount; // r12d
  _WORD *v4; // r14
  const wchar_t *v5; // rdx
  unsigned __int32 v6; // ebx
  __int64 v7; // rax
  __int64 v8; // r9
  _WORD *v9; // r8
  _WORD *v10; // rcx
  int v11; // eax
  int v12; // edx
  int v13; // r8d
  _QWORD *v14; // rcx
  __int32 v15; // eax
  __int64 result; // rax
  unsigned int v17; // edi
  int v18; // r8d
  __int64 v19; // rcx
  const char *v20; // r9
  unsigned __int16 *v21; // rax
  HMODULE Library; // rax
  HMODULE v23; // rdi
  char *v24; // r9
  unsigned int v25; // eax
  unsigned int v26; // [rsp+30h] [rbp-40h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-3Ch] BYREF
  unsigned int dwBytes_4; // [rsp+38h] [rbp-38h] BYREF
  int v29; // [rsp+3Ch] [rbp-34h] BYREF
  _DWORD v30[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+48h] [rbp-28h]
  unsigned int v32; // [rsp+50h] [rbp-20h]
  unsigned int v33; // [rsp+54h] [rbp-1Ch]
  _WORD *v34; // [rsp+58h] [rbp-18h]

  v2 = 0;
  dwBytes_4 = 1222;
  v26 = 0;
  TickCount = GetTickCount();
  if ( Parameter )
    *Parameter = 1222;
  else
    Parameter = &dwBytes_4;
  v4 = HeapAlloc(ghSensHeap, 0, 0x202u);
  if ( !v4 )
  {
    *Parameter = 14;
    return 0;
  }
  v5 = L"WAN Connection";
  v6 = 0;
  v7 = 2147483646;
  v8 = 257;
  v9 = v4;
  do
  {
    if ( !v7 )
      break;
    if ( !*v5 )
      break;
    *v9++ = *v5++;
    --v7;
    --v8;
  }
  while ( v8 );
  v10 = v9 - 1;
  if ( v8 )
    v10 = v9;
  *v10 = 0;
  v11 = IsRasInstalled(&v26, Parameter);
  if ( v11 == 1 )
  {
    if ( !glpfnRasEnumConnections )
    {
      Library = LoadLibraryExW(L"RasApi32.dll", 0, 0);
      v23 = Library;
      if ( Library )
      {
        glpfnRasEnumConnections = (unsigned int (*)(struct tagRASCONNW *, unsigned int *, unsigned int *))GetProcAddress(Library, "RasEnumConnectionsW");
        GetProcAddress(v23, "RasConnectionNotificationW");
        if ( !glpfnRasEnumConnections )
          FreeLibrary(v23);
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_22:
        if ( v26 != 4 || !glpfnRasEnumConnections )
          goto LABEL_13;
        v29 = 0;
        v17 = 603;
        dwBytes = 1388;
        while ( v17 == 603 )
        {
          v21 = (unsigned __int16 *)HeapAlloc(ghSensHeap, 0, dwBytes);
          v2 = v21;
          if ( !v21 )
          {
            HeapFree(ghSensHeap, 0, v4);
            result = 0;
            *Parameter = 14;
            return result;
          }
          *(_DWORD *)v21 = 1388;
          v17 = ((__int64 (__fastcall *)(unsigned __int16 *, unsigned int *, int *))glpfnRasEnumConnections)(
                  v21,
                  &dwBytes,
                  &v29);
          if ( v17 == 603 )
          {
            HeapFree(ghSensHeap, 0, v2);
            v2 = 0;
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids,
                dwBytes);
              v14 = WPP_GLOBAL_Control;
            }
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
          }
        }
        v18 = v29;
        if ( v17 )
        {
          *Parameter = v17;
          v14 = WPP_GLOBAL_Control;
        }
        else if ( v29 )
        {
          v6 = 1;
          if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
            WPP_SF_ddS(v14[2], v12, v29, dwBytes, v29, (__int64)(v2 + 6));
          StringCchCopyW(v4, 0x101u, v2 + 6);
          goto LABEL_30;
        }
        if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
          WPP_SF_dd(v14[2], 16, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids, v17, v18);
LABEL_30:
        HeapFree(ghSensHeap, 0, v2);
        goto LABEL_12;
      }
      v24 = byte_18000DCD0;
      if ( !glpfnRasEnumConnections )
        v24 = "NOT ";
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids, v24);
    }
LABEL_21:
    v14 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  if ( v11 )
    goto LABEL_21;
LABEL_12:
  v14 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
  {
    v19 = v14[2];
    v20 = "TRUE";
    if ( !v6 )
      v20 = "FALSE";
    WPP_SF_sd(v19, v12, v13, (_DWORD)v20, *Parameter);
  }
  if ( _InterlockedExchange(&gdwWANState, v6) != v6 )
  {
    dwBytes_4 = 0;
    v25 = 0;
    v26 = 0;
    if ( v6 )
    {
      GetActiveWanInterfaceStatistics(&dwBytes_4, &v26);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids);
      }
      v25 = v26;
    }
    v30[0] = 0;
    v31 = 0x200000010LL;
    v32 = v25;
    v33 = v25;
    v30[1] = v6;
    v34 = v4;
    UpdateSensCache(3);
    SensFireEvent(v30);
  }
  v15 = 0;
  if ( v6 )
    v15 = TickCount;
  _InterlockedExchange(&gdwLastWANTime, v15);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids,
      TickCount,
      gdwLastWANTime);
  }
  HeapFree(ghSensHeap, 0, v4);
  return v6;
}

```

## disassembly

```asm
0x180001850  push    rbp
0x180001852  push    rsi
0x180001853  push    r12
0x180001855  push    r14
0x180001857  push    r15
0x180001859  mov     rbp, rsp
0x18000185c  sub     rsp, 70h
0x180001860  mov     rax, cs:__security_cookie
0x180001867  xor     rax, rsp
0x18000186a  mov     [rbp+var_10], rax
0x18000186e  mov     r15, rcx
0x180001871  call    cs:__imp_GetTickCount
0x180001877  xor     esi, esi
0x180001879  mov     dword ptr [rbp+dwBytes+4], 4C6h
0x180001880  mov     [rbp+var_40], esi
0x180001883  mov     r12d, eax
0x180001886  test    r15, r15
0x180001889  jz      loc_180001B11
0x18000188f  mov     dword ptr [r15], 4C6h
0x180001896  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x18000189d  xor     edx, edx; dwFlags
0x18000189f  mov     r8d, 202h; dwBytes
0x1800018a5  call    cs:__imp_HeapAlloc
0x1800018ab  mov     r14, rax
0x1800018ae  test    rax, rax
0x1800018b1  jz      loc_180001B9A
0x1800018b7  mov     [rsp+70h+arg_8], rbx
0x1800018bf  lea     rdx, aWanConnection; "WAN Connection"
0x1800018c6  mov     [rsp+70h+arg_18], r13
0x1800018ce  mov     ebx, esi
0x1800018d0  mov     eax, 7FFFFFFEh
0x1800018d5  mov     r9d, 101h
0x1800018db  mov     r8, r14
0x1800018de  xchg    ax, ax
0x1800018e0  test    rax, rax
0x1800018e3  jz      short loc_180001902
0x1800018e5  movzx   ecx, word ptr [rdx]
0x1800018e8  test    cx, cx
0x1800018eb  jz      short loc_180001902
0x1800018ed  mov     [r8], cx
0x1800018f1  add     rdx, 2
0x1800018f5  add     r8, 2
0x1800018f9  dec     rax
0x1800018fc  sub     r9, 1
0x180001900  jnz     short loc_1800018E0
0x180001902  test    r9, r9
0x180001905  mov     [rsp+70h+arg_10], rdi
0x18000190d  lea     rcx, [r8-2]
0x180001911  mov     rdx, r15; unsigned int *
0x180001914  cmovnz  rcx, r8
0x180001918  mov     [rcx], si
0x18000191b  lea     rcx, [rbp+var_40]; unsigned int *
0x18000191f  call    ?IsRasInstalled@@YAHPEAK0@Z; IsRasInstalled(ulong *,ulong *)
0x180001924  lea     r13, WPP_GLOBAL_Control
0x18000192b  cmp     eax, 1
0x18000192e  jz      loc_1800019BF
0x180001934  test    eax, eax
0x180001936  jnz     loc_1800019CC
0x18000193c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001943  cmp     rcx, r13
0x180001946  jnz     loc_180001A42
0x18000194c  mov     eax, ebx
0x18000194e  xchg    eax, cs:?gdwWANState@@3JA; long gdwWANState
0x180001954  cmp     eax, ebx
0x180001956  jnz     loc_180001CD9
0x18000195c  test    ebx, ebx
0x18000195e  mov     eax, esi
0x180001960  cmovnz  eax, r12d
0x180001964  xchg    eax, cs:?gdwLastWANTime@@3JA; long gdwLastWANTime
0x18000196a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001971  cmp     rcx, r13
0x180001974  jnz     loc_180001A7F
0x18000197a  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180001981  mov     r8, r14; lpMem
0x180001984  xor     edx, edx; dwFlags
0x180001986  call    cs:__imp_HeapFree
0x18000198c  mov     eax, ebx
0x18000198e  mov     rdi, [rsp+70h+arg_10]
0x180001996  mov     rbx, [rsp+70h+arg_8]
0x18000199e  mov     r13, [rsp+70h+arg_18]
0x1800019a6  mov     rcx, [rbp+var_10]
0x1800019aa  xor     rcx, rsp; StackCookie
0x1800019ad  call    __security_check_cookie
0x1800019b2  add     rsp, 70h
0x1800019b6  pop     r15
0x1800019b8  pop     r14
0x1800019ba  pop     r12
0x1800019bc  pop     rsi
0x1800019bd  pop     rbp
0x1800019be  retn
0x1800019bf  cmp     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, rbx; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x1800019c6  jz      loc_180001B29
0x1800019cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019d3  cmp     [rbp+var_40], 4
0x1800019d7  jnz     loc_180001943
0x1800019dd  cmp     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, rbx; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x1800019e4  jz      loc_180001943
0x1800019ea  mov     [rbp+var_34], esi
0x1800019ed  mov     edi, 25Bh
0x1800019f2  mov     dword ptr [rbp+dwBytes], 56Ch
0x1800019f9  cmp     edi, 25Bh
0x1800019ff  jz      loc_180001ABC
0x180001a05  mov     r8d, [rbp+var_34]
0x180001a09  test    edi, edi
0x180001a0b  jnz     loc_180001B1A
0x180001a11  test    r8d, r8d
0x180001a14  jnz     loc_180001C67
0x180001a1a  cmp     rcx, r13
0x180001a1d  jz      short loc_180001A29
0x180001a1f  test    byte ptr [rcx+1Ch], 1
0x180001a23  jnz     loc_180001CAD
0x180001a29  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180001a30  mov     r8, rsi; lpMem
0x180001a33  xor     edx, edx; dwFlags
0x180001a35  call    cs:__imp_HeapFree
0x180001a3b  xor     esi, esi
0x180001a3d  jmp     loc_18000193C
0x180001a42  test    byte ptr [rcx+1Ch], 1
0x180001a46  jz      loc_18000194C
0x180001a4c  cmp     byte ptr [rcx+19h], 5
0x180001a50  jb      loc_18000194C
0x180001a56  mov     rcx, [rcx+10h]
0x180001a5a  lea     rax, aFalse; "FALSE"
0x180001a61  test    ebx, ebx
0x180001a63  lea     r9, aTrue; "TRUE"
0x180001a6a  cmovz   r9, rax
0x180001a6e  mov     eax, [r15]
0x180001a71  mov     [rsp+70h+var_50], eax
0x180001a75  call    WPP_SF_sd
0x180001a7a  jmp     loc_18000194C
0x180001a7f  test    byte ptr [rcx+1Ch], 1
0x180001a83  jz      loc_18000197A
0x180001a89  cmp     byte ptr [rcx+19h], 5
0x180001a8d  jb      loc_18000197A
0x180001a93  mov     r10d, cs:?gdwLastWANTime@@3JA; long gdwLastWANTime
0x180001a9a  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001aa1  mov     rcx, [rcx+10h]
0x180001aa5  mov     edx, 13h
0x180001aaa  mov     r9d, r12d
0x180001aad  mov     [rsp+70h+var_50], r10d
0x180001ab2  call    WPP_SF_dd
0x180001ab7  jmp     loc_18000197A
0x180001abc  mov     r8d, dword ptr [rbp+dwBytes]; dwBytes
0x180001ac0  xor     edx, edx; dwFlags
0x180001ac2  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180001ac9  call    cs:__imp_HeapAlloc
0x180001acf  mov     rsi, rax
0x180001ad2  test    rax, rax
0x180001ad5  jz      loc_180001C47
0x180001adb  mov     dword ptr [rax], 56Ch
0x180001ae1  lea     r8, [rbp+var_34]
0x180001ae5  mov     rcx, rax
0x180001ae8  lea     rdx, [rbp+dwBytes]
0x180001aec  mov     rax, cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x180001af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001af8  mov     edi, eax
0x180001afa  cmp     eax, 25Bh
0x180001aff  jz      loc_180001BEA
0x180001b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b0c  jmp     loc_1800019F9
0x180001b11  lea     r15, [rbp+dwBytes+4]
0x180001b15  jmp     loc_180001896
0x180001b1a  mov     [r15], edi
0x180001b1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b24  jmp     loc_180001A1A
0x180001b29  xor     r8d, r8d; dwFlags
0x180001b2c  lea     rcx, LibFileName; "RasApi32.dll"
0x180001b33  xor     edx, edx; hFile
0x180001b35  call    cs:__imp_LoadLibraryExW
0x180001b3b  mov     rdi, rax
0x180001b3e  test    rax, rax
0x180001b41  jnz     short loc_180001BA8
0x180001b43  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b4a  cmp     rcx, r13
0x180001b4d  jz      loc_1800019D3
0x180001b53  test    byte ptr [rcx+1Ch], 1
0x180001b57  jz      loc_1800019D3
0x180001b5d  cmp     byte ptr [rcx+19h], 5
0x180001b61  jb      loc_1800019D3
0x180001b67  cmp     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, rbx; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x180001b6e  lea     rax, aNot; "NOT "
0x180001b75  mov     rcx, [rcx+10h]
0x180001b79  lea     r9, byte_18000DCD0
0x180001b80  cmovz   r9, rax
0x180001b84  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001b8b  mov     edx, 0Ah
0x180001b90  call    WPP_SF_s
0x180001b95  jmp     loc_1800019CC
0x180001b9a  mov     dword ptr [r15], 0Eh
0x180001ba1  xor     eax, eax
0x180001ba3  jmp     loc_1800019A6
0x180001ba8  lea     rdx, ProcName; "RasEnumConnectionsW"
0x180001baf  mov     rcx, rdi; hModule
0x180001bb2  call    cs:__imp_GetProcAddress
0x180001bb8  lea     rdx, aRasconnectionn; "RasConnectionNotificationW"
0x180001bbf  mov     rcx, rdi; hModule
0x180001bc2  mov     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, rax; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x180001bc9  call    cs:__imp_GetProcAddress
0x180001bcf  cmp     cs:?glpfnRasEnumConnections@@3P6AKPEAUtagRASCONNW@@PEAK1@ZEA, rbx; ulong (*glpfnRasEnumConnections)(tagRASCONNW *,ulong *,ulong *)
0x180001bd6  jnz     loc_180001B43
0x180001bdc  mov     rcx, rdi; hLibModule
0x180001bdf  call    cs:__imp_FreeLibrary
0x180001be5  jmp     loc_180001B43
0x180001bea  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180001bf1  mov     r8, rsi; lpMem
0x180001bf4  xor     edx, edx; dwFlags
0x180001bf6  call    cs:__imp_HeapFree
0x180001bfc  xor     esi, esi
0x180001bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c05  cmp     rcx, r13
0x180001c08  jz      loc_1800019F9
0x180001c0e  test    byte ptr [rcx+1Ch], 1
0x180001c12  jz      loc_1800019F9
0x180001c18  cmp     byte ptr [rcx+19h], 5
0x180001c1c  jb      loc_1800019F9
0x180001c22  mov     r9d, dword ptr [rbp+dwBytes]
0x180001c26  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001c2d  mov     rcx, [rcx+10h]
0x180001c31  mov     edx, 0Eh
0x180001c36  call    WPP_SF_d
0x180001c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c42  jmp     loc_1800019F9
0x180001c47  mov     rcx, cs:?ghSensHeap@@3PEAXEA; hHeap
0x180001c4e  mov     r8, r14; lpMem
0x180001c51  xor     edx, edx; dwFlags
0x180001c53  call    cs:__imp_HeapFree
0x180001c59  xor     eax, eax
0x180001c5b  mov     dword ptr [r15], 0Eh
0x180001c62  jmp     loc_18000198E
0x180001c67  mov     ebx, 1
0x180001c6c  cmp     rcx, r13
0x180001c6f  jz      short loc_180001C97
0x180001c71  test    [rcx+1Ch], bl
0x180001c74  jz      short loc_180001C97
0x180001c76  cmp     byte ptr [rcx+19h], 5
0x180001c7a  jb      short loc_180001C97
0x180001c7c  mov     r9d, dword ptr [rbp+dwBytes]
0x180001c80  lea     rax, [rsi+0Ch]
0x180001c84  mov     rcx, [rcx+10h]
0x180001c88  mov     [rsp+70h+var_48], rax
0x180001c8d  mov     [rsp+70h+var_50], r8d
0x180001c92  call    WPP_SF_ddS
0x180001c97  lea     r8, [rsi+0Ch]; unsigned __int16 *
0x180001c9b  mov     edx, 101h; unsigned __int64
0x180001ca0  mov     rcx, r14; unsigned __int16 *
0x180001ca3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180001ca8  jmp     loc_180001A29
0x180001cad  cmp     byte ptr [rcx+19h], 5
0x180001cb1  jb      loc_180001A29
0x180001cb7  mov     rcx, [rcx+10h]
0x180001cbb  mov     edx, 10h
0x180001cc0  mov     [rsp+70h+var_50], r8d
0x180001cc5  mov     r9d, edi
0x180001cc8  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001ccf  call    WPP_SF_dd
0x180001cd4  jmp     loc_180001A29
0x180001cd9  mov     dword ptr [rbp+dwBytes+4], esi
0x180001cdc  mov     eax, esi
0x180001cde  mov     [rbp+var_40], eax
0x180001ce1  test    ebx, ebx
0x180001ce3  jz      short loc_180001D22
0x180001ce5  lea     rdx, [rbp+var_40]; unsigned int *
0x180001ce9  lea     rcx, [rbp+dwBytes+4]; unsigned int *
0x180001ced  call    ?GetActiveWanInterfaceStatistics@@YAHPEAK0@Z; GetActiveWanInterfaceStatistics(ulong *,ulong *)
0x180001cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cf9  cmp     rcx, r13
0x180001cfc  jz      short loc_180001D1F
0x180001cfe  test    byte ptr [rcx+1Ch], 1
0x180001d02  jz      short loc_180001D1F
0x180001d04  cmp     byte ptr [rcx+19h], 4
0x180001d08  jb      short loc_180001D1F
0x180001d0a  mov     rcx, [rcx+10h]
0x180001d0e  lea     r8, WPP_01ff164fadb13b0d381faad4a7ddce15_Traceguids
0x180001d15  mov     edx, 12h
0x180001d1a  call    WPP_SF_
0x180001d1f  mov     eax, [rbp+var_40]
0x180001d22  xorps   xmm0, xmm0
0x180001d25  mov     [rbp+var_30], esi
0x180001d28  movups  [rbp+var_28], xmm0
0x180001d2c  mov     ecx, 3
0x180001d31  mov     dword ptr [rbp+var_28], 10h
0x180001d38  mov     dword ptr [rbp+var_28+4], 2
0x180001d3f  mov     dword ptr [rbp+var_28+8], eax
0x180001d42  mov     dword ptr [rbp+var_28+0Ch], eax
0x180001d45  mov     [rbp+var_2C], ebx
0x180001d48  mov     [rbp+var_18], r14
0x180001d4c  call    ?UpdateSensCache@@YAXW4CACHE_TYPE@@@Z; UpdateSensCache(CACHE_TYPE)
0x180001d51  lea     rcx, [rbp+var_30]; void *
0x180001d55  call    ?SensFireEvent@@YAXPEAX@Z; SensFireEvent(void *)
0x180001d5a  jmp     loc_18000195C
```

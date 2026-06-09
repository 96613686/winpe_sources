# DdeClientTransaction

- ea: `0x1800470a0`
- end: `0x180047727`
- name: `DdeClientTransaction`
- size: `1671`
- prototype: `HDDEDATA __stdcall(LPBYTE pData, DWORD cbData, HCONV hConv, HSZ hszItem, UINT wFmt, UINT wType, DWORD dwTimeout, LPDWORD pdwResult)`
- caller_count: `0`
- callee_count: `21`
- tags: `loader_planting, installer_update`

## callees

- `0x18000ab10`
- `0x18000ae90`
- `0x180046880`
- `0x180046dec`
- `0x1800470a0`
- `0x180047730`
- `0x1800481f4`
- `0x1800482c4`
- `0x180048320`
- `0x1800483d4`
- `0x18005e380`
- `0x180068c40`
- `0x18006ef34`
- `0x18007f094`
- `0x18008f2b0`
- `0x18008fbfc`
- `0x18008fce8`
- `0x18008fd94`
- `0x18008fe28`
- `0x18008febc`
- `0x1800a2010`

## import_xrefs

- `win32u!NtUserSetTimer` at `0x1800474ef`
- `win32u!NtUserSetTimer` at `0x1800474ef`
- `win32u!NtUserKillTimer` at `0x180047550`
- `win32u!NtUserKillTimer` at `0x180047550`
- `ntdll!RtlEnterCriticalSection` at `0x1800470e3`
- `ntdll!RtlEnterCriticalSection` at `0x180047543`
- `ntdll!RtlEnterCriticalSection` at `0x1800470e3`
- `ntdll!RtlEnterCriticalSection` at `0x180047543`
- `ntdll!RtlLeaveCriticalSection` at `0x1800474fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180047706`
- `ntdll!RtlLeaveCriticalSection` at `0x1800474fc`
- `ntdll!RtlLeaveCriticalSection` at `0x180047706`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800471e3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800471e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047262`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047346`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800474ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047262`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047346`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800474ad`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800474a4`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x1800474a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800472a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800472ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800472a0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800472ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800472cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180047302`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800472cd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180047302`

## pseudocode

```c
HDDEDATA __stdcall DdeClientTransaction(
        LPBYTE pData,
        DWORD cbData,
        HCONV hConv,
        HSZ hszItem,
        UINT wFmt,
        UINT wType,
        DWORD dwTimeout,
        LPDWORD pdwResult)
{
  __int64 DataHandle; // rbp
  unsigned int v12; // ecx
  unsigned __int64 v13; // rax
  __int64 v14; // r15
  __int64 v15; // rsi
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned __int16 *v18; // rdi
  void **v19; // r14
  LPBYTE v20; // r12
  unsigned __int64 v21; // rax
  void *v22; // rax
  HGLOBAL v23; // rax
  _WORD *v24; // rax
  _WORD *v25; // rax
  DWORD v26; // edx
  unsigned __int16 v27; // r9
  unsigned __int16 v28; // r8
  void *v29; // rax
  int started; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r12
  __int64 v34; // rdx
  void *Handle; // rax
  void *v36; // rcx
  struct _TEB *v37; // rax
  struct _TEB *v38; // rax
  unsigned __int16 v39; // ax
  unsigned __int8 *v40; // rdx
  unsigned int v41; // edx
  unsigned int v42; // edx
  struct tagMSG Msg; // [rsp+40h] [rbp-68h] BYREF
  unsigned __int16 v46; // [rsp+C8h] [rbp+20h]

  v46 = (unsigned __int16)hszItem;
  memset(&Msg, 0, sizeof(Msg));
  DataHandle = 0;
  RtlEnterCriticalSection(&gcsDDEML);
  v13 = ((unsigned __int64)hConv >> 10) & 0x3FFF;
  if ( (int)v13 >= cHandlesAllocated
    || (v12 = 2 * v13, *((HCONV *)aHandleEntry + 2 * (((unsigned __int64)hConv >> 10) & 0x3FFF)) != hConv)
    || (((unsigned __int64)hConv >> 7) & 7) != 3
    || (_mm_lfence(), (v14 = *((_QWORD *)aHandleEntry + 2 * (((unsigned __int64)hConv >> 10) & 0x3FFF) + 1)) == 0) )
  {
    BestSetLastDDEMLError(v12);
    goto LABEL_110;
  }
  v15 = *(_QWORD *)(v14 + 8);
  if ( dwTimeout == -1 || (NtCurrentTeb()->Win32ClientInfo[0] & 1) == 0 )
  {
    if ( (*(_BYTE *)(v14 + 56) & 1) == 0 )
    {
      v16 = 16394;
      goto LABEL_8;
    }
    if ( wType != 4144 && wType != 4148 && wType != 4152 && wType != 4156 && wType != 8368 )
    {
      if ( wType == 16464 )
        goto LABEL_22;
      if ( wType != 16528 && wType != 32832 )
        goto LABEL_20;
    }
    if ( !hszItem )
    {
LABEL_20:
      v17 = 16390;
LABEL_21:
      SetLastDDEMLError((struct tagCL_INSTANCE_INFO *)v15, v17);
      goto LABEL_105;
    }
LABEL_22:
    v18 = (unsigned __int16 *)LocalAlloc(0x40u, 0x48u);
    if ( !v18 )
    {
      v17 = 16392;
      goto LABEL_21;
    }
    v19 = 0;
    if ( wType == 16464 || wType == 16528 )
    {
      if ( cbData == -1 )
      {
        v20 = pData;
        v21 = ValidateCHandle(pData, 6u, 0xFFFFFFFF);
        v19 = (void **)v21;
        if ( !v21 )
        {
LABEL_30:
          SetLastDDEMLError((struct tagCL_INSTANCE_INFO *)v15, 0x4006u);
          LocalFree(v18);
          goto LABEL_105;
        }
        if ( (*(_DWORD *)(v21 + 8) & 0x100) != 0 )
        {
          if ( wType != 16464 )
            goto LABEL_30;
        }
        else if ( wType == 16464 )
        {
          goto LABEL_30;
        }
        v22 = *(void **)v21;
        if ( ((_DWORD)v19[1] & 0x4001) != 0 )
        {
          v23 = CopyDDEData(v22, wType == 16464);
          *((_QWORD *)v18 + 7) = v23;
          if ( !v23 )
          {
LABEL_44:
            LocalFree(v18);
            SetLastDDEMLError((struct tagCL_INSTANCE_INFO *)v15, 0x4008u);
            goto LABEL_105;
          }
          v24 = GlobalLock(v23);
          if ( !v24 )
          {
            FreeDDEData(*((HGLOBAL *)v18 + 7), 1, 1);
            goto LABEL_44;
          }
          *v24 = 0x2000;
          GlobalUnlock(*((HGLOBAL *)v18 + 7));
        }
        else
        {
          *((_QWORD *)v18 + 7) = v22;
        }
        if ( wType == 16528 )
        {
          v25 = GlobalLock(*((HGLOBAL *)v18 + 7));
          if ( !v25 )
            goto LABEL_30;
          v25[1] = wFmt;
          GlobalUnlock(*((HGLOBAL *)v18 + 7));
        }
      }
      else
      {
        v26 = cbData;
        v20 = pData;
        v27 = wFmt;
        v28 = 0x2000;
        if ( wType != 16528 )
        {
          v27 = 0;
          v28 = 0;
        }
        v29 = AllocAndSetDDEData(pData, v26, v28, v27);
        *((_QWORD *)v18 + 7) = v29;
        if ( !v29 )
          goto LABEL_44;
      }
    }
    else
    {
      v20 = pData;
    }
    *((_QWORD *)v18 + 1) = v14;
    v18[20] = LocalToGlobalAtom(v46);
    v18[21] = wFmt;
    v18[22] = wType;
    switch ( wType )
    {
      case 0x1030u:
      case 0x1034u:
      case 0x1038u:
      case 0x103Cu:
        started = ClStartAdvise((struct tagXACT_INFO *)v18);
        break;
      case 0x20B0u:
        started = ClStartRequest((struct tagXACT_INFO *)v18);
        break;
      case 0x4050u:
        started = ClStartExecute((struct tagXACT_INFO *)v18);
        break;
      case 0x4090u:
        started = ClStartPoke((struct tagXACT_INFO *)v18);
        break;
      default:
        started = ClStartUnadvise((struct tagXACT_INFO *)v18);
        break;
    }
    if ( started )
    {
      if ( v19 && ((_DWORD)v19[1] & 0x4001) == 0 )
      {
        LocalFree(v19);
        v31 = aHandleEntry;
        v32 = iFirstFree;
        v33 = ((unsigned __int64)v20 >> 10) & 0x3FFF;
        v34 = 2LL * (unsigned int)v33;
        iFirstFree = v33;
        *((_QWORD *)aHandleEntry + v34) = 0;
        v31[v34 + 1] = v32;
      }
      if ( dwTimeout == -1 )
      {
        if ( pdwResult )
        {
          Handle = CreateHandle((unsigned __int64)v18, 5u, *(_DWORD *)(v15 + 16) & 0x7F);
          *((_QWORD *)v18 + 3) = Handle;
          *pdwResult = (unsigned int)Handle;
        }
        DataHandle = 1;
      }
      else
      {
        v37 = NtCurrentTeb();
        v37->Win32ClientInfo[0] |= 1uLL;
        *(_WORD *)(v15 + 108) |= 1u;
        v18[24] |= 1u;
        NtUserSetTimer(*(_QWORD *)(v14 + 48), 1, dwTimeout);
        RtlLeaveCriticalSection(&gcsDDEML);
        while ( 1 )
        {
          GetMessageW(&Msg, 0, 0, 0);
          if ( Msg.wParam == 1 && Msg.hwnd == *(HWND *)(v14 + 48) && Msg.message == 275 )
            break;
          if ( !CallMsgFilterW(&Msg, 32769) )
            DispatchMessageWorker(&Msg, 0);
        }
        RtlEnterCriticalSection(&gcsDDEML);
        NtUserKillTimer(*(_QWORD *)(v14 + 48), 1);
        v38 = NtCurrentTeb();
        v38->Win32ClientInfo[0] &= ~1uLL;
        *(_WORD *)(v15 + 108) &= ~1u;
        v39 = v18[24];
        if ( (v39 & 2) != 0 )
        {
          if ( pdwResult )
            *pdwResult = v18[23];
          if ( wType == 8368 && (v40 = (unsigned __int8 *)*((_QWORD *)v18 + 8)) != 0 )
          {
            DataHandle = (__int64)InternalCreateDataHandle(
                                    (struct tagCL_INSTANCE_INFO *)v15,
                                    v40,
                                    0xFFFFFFFF,
                                    0,
                                    0x8000u,
                                    0,
                                    0);
            *((_QWORD *)v18 + 8) = 0;
          }
          else if ( (v18[23] & 0x8000u) == 0 )
          {
            if ( (v18[23] & 0x4000) != 0 )
              v41 = 16385;
            else
              v41 = 16393;
            SetLastDDEMLError((struct tagCL_INSTANCE_INFO *)v15, v41);
          }
          else
          {
            DataHandle = 1;
          }
          (*((void (__fastcall **)(unsigned __int16 *, _QWORD, _QWORD))v18 + 4))(v18, 0, 0);
        }
        else
        {
          v18[24] = v39 & 0xFFFA | 4;
          switch ( wType )
          {
            case 0x1030u:
            case 0x1034u:
            case 0x1038u:
            case 0x103Cu:
              v42 = 0x4000;
              break;
            case 0x20B0u:
              v42 = 16386;
              break;
            case 0x4050u:
              v42 = 16389;
              break;
            case 0x4090u:
              v42 = 16395;
              break;
            default:
              v42 = 16400;
              break;
          }
          SetLastDDEMLError((struct tagCL_INSTANCE_INFO *)v15, v42);
        }
      }
      if ( (*(_WORD *)(v14 + 56) & 0x800) != 0 )
        FreeConversationResources((struct tagCONV_INFO *)v14);
    }
    else
    {
      v36 = (void *)*((_QWORD *)v18 + 7);
      if ( v36 && (!v19 || v36 != *v19) )
        FreeDDEData(v36, 0, 1);
      GlobalDeleteAtom(v18[20]);
      LocalFree(v18);
    }
    goto LABEL_105;
  }
  v16 = 16397;
LABEL_8:
  SetLastDDEMLError(*(struct tagCL_INSTANCE_INFO **)(v14 + 8), v16);
LABEL_105:
  if ( v15 && (*(_DWORD *)(v15 + 56) & 0x800) != 0 && !*(_WORD *)(v15 + 110) )
  {
    DdeUninitialize(*(_DWORD *)(v15 + 16));
    DataHandle = 0;
  }
LABEL_110:
  RtlLeaveCriticalSection(&gcsDDEML);
  return (HDDEDATA)DataHandle;
}

```

## disassembly

```asm
0x1800470a0  mov     rax, rsp
0x1800470a3  mov     [rax+10h], rbx
0x1800470a7  mov     [rax+20h], r9
0x1800470ab  mov     [rax+8], rcx
0x1800470af  push    rbp
0x1800470b0  push    rsi
0x1800470b1  push    rdi
0x1800470b2  push    r12
0x1800470b4  push    r13
0x1800470b6  push    r14
0x1800470b8  push    r15
0x1800470ba  sub     rsp, 70h
0x1800470be  xorps   xmm0, xmm0
0x1800470c1  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800470c8  xor     r13d, r13d
0x1800470cb  mov     rdi, r9
0x1800470ce  movups  xmmword ptr [rax-68h], xmm0
0x1800470d2  mov     ebp, r13d
0x1800470d5  mov     rbx, r8
0x1800470d8  movups  xmmword ptr [rax-58h], xmm0
0x1800470dc  mov     r12d, edx
0x1800470df  movups  xmmword ptr [rax-48h], xmm0
0x1800470e3  call    cs:__imp_RtlEnterCriticalSection
0x1800470e9  mov     rax, rbx
0x1800470ec  shr     rax, 0Ah
0x1800470f0  and     eax, 3FFFh
0x1800470f5  cmp     eax, cs:?cHandlesAllocated@@3HA; int cHandlesAllocated
0x1800470fb  jge     loc_1800476FA
0x180047101  mov     ecx, eax
0x180047103  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x18004710a  add     rcx, rcx
0x18004710d  cmp     [rax+rcx*8], rbx
0x180047111  jnz     loc_1800476FA
0x180047117  shr     rbx, 7
0x18004711b  and     ebx, 7
0x18004711e  cmp     bl, 3
0x180047121  jnz     loc_1800476FA
0x180047127  lfence
0x18004712a  mov     rax, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x180047131  mov     r15, [rax+rcx*8+8]
0x180047136  test    r15, r15
0x180047139  jz      loc_1800476FA
0x18004713f  cmp     [rsp+0A8h+dwTimeout], 0FFFFFFFFh
0x180047147  mov     ebx, 800h
0x18004714c  mov     rsi, [r15+8]
0x180047150  jz      short loc_180047176
0x180047152  mov     rax, gs:30h
0x18004715b  test    byte ptr [rax+800h], 1
0x180047162  jz      short loc_180047176
0x180047164  mov     edx, 400Dh; unsigned int
0x180047169  mov     rcx, rsi; struct tagCL_INSTANCE_INFO *
0x18004716c  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180047171  jmp     loc_1800476DC
0x180047176  test    byte ptr [r15+38h], 1
0x18004717b  jnz     short loc_180047184
0x18004717d  mov     edx, 400Ah
0x180047182  jmp     short loc_180047169
0x180047184  mov     ebx, [rsp+0A8h+wType]
0x18004718b  mov     ecx, 4
0x180047190  mov     eax, ebx
0x180047192  sub     eax, 1030h
0x180047197  jz      short loc_1800471BF
0x180047199  sub     eax, ecx
0x18004719b  jz      short loc_1800471BF
0x18004719d  sub     eax, ecx
0x18004719f  jz      short loc_1800471BF
0x1800471a1  sub     eax, ecx
0x1800471a3  jz      short loc_1800471BF
0x1800471a5  sub     eax, 1074h
0x1800471aa  jz      short loc_1800471BF
0x1800471ac  sub     eax, 1FA0h
0x1800471b1  jz      short loc_1800471DB
0x1800471b3  sub     eax, 40h ; '@'
0x1800471b6  jz      short loc_1800471BF
0x1800471b8  cmp     eax, 3FB0h
0x1800471bd  jnz     short loc_1800471C4
0x1800471bf  test    rdi, rdi
0x1800471c2  jnz     short loc_1800471DB
0x1800471c4  mov     edx, 4006h; unsigned int
0x1800471c9  mov     rcx, rsi; struct tagCL_INSTANCE_INFO *
0x1800471cc  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x1800471d1  mov     ebx, 800h
0x1800471d6  jmp     loc_1800476DC
0x1800471db  mov     edx, 48h ; 'H'; uBytes
0x1800471e0  lea     ecx, [rdx-8]; uFlags
0x1800471e3  call    cs:__imp_LocalAlloc
0x1800471e9  mov     rdi, rax
0x1800471ec  test    rax, rax
0x1800471ef  jnz     short loc_1800471F8
0x1800471f1  mov     edx, 4008h
0x1800471f6  jmp     short loc_1800471C9
0x1800471f8  mov     eax, ebx
0x1800471fa  mov     r14, r13
0x1800471fd  mov     r13d, [rsp+0A8h+wFmt]
0x180047205  sub     eax, 4050h
0x18004720a  jz      short loc_180047215
0x18004720c  cmp     eax, 40h ; '@'
0x18004720f  jnz     loc_18004735E
0x180047215  cmp     r12d, 0FFFFFFFFh
0x180047219  jnz     loc_18004730A
0x18004721f  lea     edx, [r12+7]; unsigned int
0x180047224  or      r8d, 0FFFFFFFFh; unsigned int
0x180047228  mov     r12, [rsp+0A8h+Src]
0x180047230  mov     rcx, r12; void *
0x180047233  call    ?ValidateCHandle@@YA_KPEAXKK@Z; ValidateCHandle(void *,ulong,ulong)
0x180047238  mov     r14, rax
0x18004723b  test    rax, rax
0x18004723e  jz      short loc_180047252
0x180047240  test    dword ptr [rax+8], 100h
0x180047247  mov     ecx, 4050h
0x18004724c  jz      short loc_180047270
0x18004724e  cmp     ebx, ecx
0x180047250  jz      short loc_180047274
0x180047252  mov     edx, 4006h; unsigned int
0x180047257  mov     rcx, rsi; struct tagCL_INSTANCE_INFO *
0x18004725a  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x18004725f  mov     rcx, rdi; hMem
0x180047262  call    cs:__imp_LocalFree
0x180047268  xor     r13d, r13d
0x18004726b  jmp     loc_1800471D1
0x180047270  cmp     ebx, ecx
0x180047272  jz      short loc_180047252
0x180047274  test    dword ptr [r14+8], 4001h
0x18004727c  mov     rax, [rax]
0x18004727f  jz      short loc_1800472D5
0x180047281  xor     edx, edx
0x180047283  cmp     ebx, ecx
0x180047285  mov     rcx, rax; void *
0x180047288  setz    dl; int
0x18004728b  call    ?CopyDDEData@@YAPEAXPEAXH@Z; CopyDDEData(void *,int)
0x180047290  mov     [rdi+38h], rax
0x180047294  test    rax, rax
0x180047297  jz      loc_180047343
0x18004729d  mov     rcx, rax; hMem
0x1800472a0  call    cs:__imp_GlobalLock
0x1800472a6  test    rax, rax
0x1800472a9  jnz     short loc_1800472BF
0x1800472ab  mov     rcx, [rdi+38h]; hMem
0x1800472af  lea     edx, [rax+1]; int
0x1800472b2  mov     r8d, edx; int
0x1800472b5  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x1800472ba  jmp     loc_180047343
0x1800472bf  mov     r8d, 2000h
0x1800472c5  mov     [rax], r8w
0x1800472c9  mov     rcx, [rdi+38h]; hMem
0x1800472cd  call    cs:__imp_GlobalUnlock
0x1800472d3  jmp     short loc_1800472D9
0x1800472d5  mov     [rdi+38h], rax
0x1800472d9  mov     ecx, 4090h
0x1800472de  cmp     ebx, ecx
0x1800472e0  jnz     loc_180047366
0x1800472e6  mov     rcx, [rdi+38h]; hMem
0x1800472ea  call    cs:__imp_GlobalLock
0x1800472f0  test    rax, rax
0x1800472f3  jz      loc_180047252
0x1800472f9  mov     [rax+2], r13w
0x1800472fe  mov     rcx, [rdi+38h]; hMem
0x180047302  call    cs:__imp_GlobalUnlock
0x180047308  jmp     short loc_180047366
0x18004730a  xor     eax, eax
0x18004730c  mov     ecx, 4090h
0x180047311  cmp     ebx, ecx
0x180047313  mov     edx, r12d; unsigned int
0x180047316  mov     r12, [rsp+0A8h+Src]
0x18004731e  movzx   r9d, r13w
0x180047322  mov     r8d, 2000h
0x180047328  cmovnz  r9w, ax; unsigned __int16
0x18004732d  cmovnz  r8w, ax; unsigned __int16
0x180047332  mov     rcx, r12; Src
0x180047335  call    ?AllocAndSetDDEData@@YAPEAXPEAEKGG@Z; AllocAndSetDDEData(uchar *,ulong,ushort,ushort)
0x18004733a  mov     [rdi+38h], rax
0x18004733e  test    rax, rax
0x180047341  jnz     short loc_180047366
0x180047343  mov     rcx, rdi; hMem
0x180047346  call    cs:__imp_LocalFree
0x18004734c  mov     edx, 4008h; unsigned int
0x180047351  mov     rcx, rsi; struct tagCL_INSTANCE_INFO *
0x180047354  call    ?SetLastDDEMLError@@YAXPEAUtagCL_INSTANCE_INFO@@K@Z; SetLastDDEMLError(tagCL_INSTANCE_INFO *,ulong)
0x180047359  jmp     loc_180047268
0x18004735e  mov     r12, [rsp+0A8h+Src]
0x180047366  movzx   ecx, [rsp+0A8h+arg_18]; unsigned __int16
0x18004736e  mov     [rdi+8], r15
0x180047372  call    ?LocalToGlobalAtom@@YAGG@Z; LocalToGlobalAtom(ushort)
0x180047377  mov     [rdi+28h], ax
0x18004737b  mov     eax, ebx
0x18004737d  mov     [rdi+2Ah], r13w
0x180047382  mov     [rdi+2Ch], bx
0x180047386  sub     eax, 1030h
0x18004738b  jz      short loc_1800473E2
0x18004738d  sub     eax, 4
0x180047390  jz      short loc_1800473E2
0x180047392  sub     eax, 4
0x180047395  jz      short loc_1800473E2
0x180047397  sub     eax, 4
0x18004739a  jz      short loc_1800473E2
0x18004739c  sub     eax, 1074h
0x1800473a1  jz      short loc_1800473D8
0x1800473a3  sub     eax, 1FA0h
0x1800473a8  jz      short loc_1800473CE
0x1800473aa  sub     eax, 40h ; '@'
0x1800473ad  jz      short loc_1800473C4
0x1800473af  cmp     eax, 3FB0h
0x1800473b4  jnz     loc_18004747F
0x1800473ba  mov     rcx, rdi; struct tagXACT_INFO *
0x1800473bd  call    ?ClStartUnadvise@@YAHPEAUtagXACT_INFO@@@Z; ClStartUnadvise(tagXACT_INFO *)
0x1800473c2  jmp     short loc_1800473EA
0x1800473c4  mov     rcx, rdi; struct tagXACT_INFO *
0x1800473c7  call    ?ClStartPoke@@YAHPEAUtagXACT_INFO@@@Z; ClStartPoke(tagXACT_INFO *)
0x1800473cc  jmp     short loc_1800473EA
0x1800473ce  mov     rcx, rdi; struct tagXACT_INFO *
0x1800473d1  call    ?ClStartExecute@@YAHPEAUtagXACT_INFO@@@Z; ClStartExecute(tagXACT_INFO *)
0x1800473d6  jmp     short loc_1800473EA
0x1800473d8  mov     rcx, rdi; struct tagXACT_INFO *
0x1800473db  call    ?ClStartRequest@@YAHPEAUtagXACT_INFO@@@Z; ClStartRequest(tagXACT_INFO *)
0x1800473e0  jmp     short loc_1800473EA
0x1800473e2  mov     rcx, rdi; struct tagXACT_INFO *
0x1800473e5  call    ?ClStartAdvise@@YAHPEAUtagXACT_INFO@@@Z; ClStartAdvise(tagXACT_INFO *)
0x1800473ea  xor     r13d, r13d
0x1800473ed  test    eax, eax
0x1800473ef  jz      loc_180047482
0x1800473f5  test    r14, r14
0x1800473f8  jz      short loc_18004743F
0x1800473fa  test    dword ptr [r14+8], 4001h
0x180047402  jnz     short loc_18004743F
0x180047404  mov     rcx, r14; hMem
0x180047407  call    cs:__imp_LocalFree
0x18004740d  mov     rcx, cs:?aHandleEntry@@3PEAUtagCHANDLEENTRY@@EA; tagCHANDLEENTRY * aHandleEntry
0x180047414  movsxd  rax, cs:?iFirstFree@@3HA; int iFirstFree
0x18004741b  shr     r12, 0Ah
0x18004741f  and     r12d, 3FFFh
0x180047426  mov     edx, r12d
0x180047429  add     rdx, rdx
0x18004742c  mov     r8d, r12d
0x18004742f  mov     cs:?iFirstFree@@3HA, r8d; int iFirstFree
0x180047436  mov     [rcx+rdx*8], r13
0x18004743a  mov     [rcx+rdx*8+8], rax
0x18004743f  or      r12d, 0FFFFFFFFh
0x180047443  cmp     [rsp+0A8h+dwTimeout], r12d
0x18004744b  jnz     short loc_1800474B8
0x18004744d  mov     rbx, [rsp+0A8h+pdwResult]
0x180047455  test    rbx, rbx
0x180047458  jz      short loc_180047475
0x18004745a  mov     r8d, [rsi+10h]
0x18004745e  mov     edx, 5; unsigned int
0x180047463  and     r8d, 7Fh; unsigned int
0x180047467  mov     rcx, rdi; unsigned __int64
0x18004746a  call    ?CreateHandle@@YAPEAX_KKK@Z; CreateHandle(unsigned __int64,ulong,ulong)
0x18004746f  mov     [rdi+18h], rax
0x180047473  mov     [rbx], eax
0x180047475  mov     ebp, 1
0x18004747a  jmp     loc_1800476C8
0x18004747f  xor     r13d, r13d
0x180047482  mov     rcx, [rdi+38h]; hMem
0x180047486  test    rcx, rcx
0x180047489  jz      short loc_1800474A0
0x18004748b  test    r14, r14
0x18004748e  jz      short loc_180047495
0x180047490  cmp     rcx, [r14]
0x180047493  jz      short loc_1800474A0
0x180047495  xor     edx, edx; int
0x180047497  lea     r8d, [rdx+1]; int
0x18004749b  call    ?FreeDDEData@@YAXPEAXHH@Z; FreeDDEData(void *,int,int)
0x1800474a0  movzx   ecx, word ptr [rdi+28h]; nAtom
0x1800474a4  call    cs:__imp_GlobalDeleteAtom
0x1800474aa  mov     rcx, rdi; hMem
0x1800474ad  call    cs:__imp_LocalFree
0x1800474b3  jmp     loc_1800471D1
0x1800474b8  mov     rax, gs:30h
0x1800474c1  mov     r14d, 1
0x1800474c7  mov     r8d, [rsp+0A8h+dwTimeout]
0x1800474cf  xor     r9d, r9d
0x1800474d2  mov     edx, r14d
0x1800474d5  mov     [rsp+0A8h+var_88], r13d
0x1800474da  or      [rax+800h], r14
0x1800474e1  or      [rsi+6Ch], r14w
0x1800474e6  or      [rdi+30h], r14w
0x1800474eb  mov     rcx, [r15+30h]
0x1800474ef  call    cs:__imp_NtUserSetTimer
0x1800474f5  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800474fc  call    cs:__imp_RtlLeaveCriticalSection
0x180047502  xor     r9d, r9d; wMsgFilterMax
0x180047505  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x18004750a  xor     r8d, r8d; wMsgFilterMin
0x18004750d  xor     edx, edx; hWnd
0x18004750f  call    GetMessageW
0x180047514  mov     rax, [r15+30h]
0x180047518  cmp     [rsp+0A8h+Msg.wParam], r14
0x18004751d  jnz     loc_1800475D3
0x180047523  cmp     [rsp+0A8h+Msg.hwnd], rax
0x180047528  jnz     loc_1800475D3
0x18004752e  cmp     [rsp+0A8h+Msg.message], 113h
0x180047536  jnz     loc_1800475D3
0x18004753c  lea     rcx, ?gcsDDEML@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180047543  call    cs:__imp_RtlEnterCriticalSection
0x180047549  mov     rcx, [r15+30h]
0x18004754d  mov     rdx, r14
0x180047550  call    cs:__imp_NtUserKillTimer
0x180047556  mov     rax, gs:30h
0x18004755f  mov     ecx, 0FFFEh
0x180047564  and     qword ptr [rax+800h], 0FFFFFFFFFFFFFFFEh
  ... truncated ...
```

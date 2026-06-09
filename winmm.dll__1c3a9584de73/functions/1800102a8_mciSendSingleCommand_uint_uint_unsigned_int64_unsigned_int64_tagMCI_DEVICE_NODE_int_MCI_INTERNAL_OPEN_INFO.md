# mciSendSingleCommand(uint,uint,unsigned __int64,unsigned __int64,tagMCI_DEVICE_NODE *,int,MCI_INTERNAL_OPEN_INFO *)

- ea: `0x1800102a8`
- end: `0x1800104fc`
- name: `?mciSendSingleCommand@@YAKII_K0PEAUtagMCI_DEVICE_NODE@@HPEAUMCI_INTERNAL_OPEN_INFO@@@Z`
- size: `596`
- prototype: `unsigned int __fastcall(MCIDEVICEID mciId, UINT message, DWORD_PTR dwParam1, DWORD_PTR dwParam2, struct tagMCI_DEVICE_NODE *, int, struct MCI_INTERNAL_OPEN_INFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180009bb0`

## callees

- `0x1800039b8`
- `0x180004700`
- `0x180004d90`
- `0x18000b6d4`
- `0x18000f960`
- `0x1800102a8`
- `0x180010c10`
- `0x180014b54`
- `0x180015480`
- `0x180015848`
- `0x180015950`
- `0x1800159c8`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010414`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010414`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104be`
- `WINMMBASE!SendDriverMessage` at `0x18001034f`
- `WINMMBASE!SendDriverMessage` at `0x18001034f`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x18001033d`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x18001033d`

## pseudocode

```c
__int64 __fastcall mciSendSingleCommand(
        __int64 mciId,
        UINT message,
        LPARAM dwParam1,
        DWORD_PTR dwParam2,
        struct tagMCI_DEVICE_NODE *a5,
        int a6,
        struct MCI_INTERNAL_OPEN_INFO *a7)
{
  MCIDEVICEID v10; // r14d
  unsigned int v11; // esi
  DWORD v12; // r8d
  const WCHAR *v13; // rcx
  unsigned int v14; // ebx
  int v15; // ebx
  unsigned int v16; // ecx
  __int64 v17; // rax
  unsigned __int64 v18; // rbp
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rdi

  v10 = mciId;
  switch ( message )
  {
    case 0x803u:
      return (unsigned int)mciOpenDevice((unsigned int)dwParam1, dwParam2, a7);
    case 0x804u:
      if ( GetCurrentThreadId() != *((_QWORD *)a5 + 10) )
      {
        v17 = -1;
        do
          ++v17;
        while ( *(_WORD *)(*(_QWORD *)a5 + 2 * v17) );
        if ( a6 )
        {
          v18 = 2 * v17 + 14;
          v19 = (unsigned __int16 *)winmmAlloc((unsigned int)(2 * v17 + 14));
          v20 = v19;
          if ( !v19 )
            return 264;
          StringCbCopyW(v19, v18, wszClose);
          StringCbCatW(v20, v18, L" ");
          StringCbCatW(v20, v18, *(const unsigned __int16 **)a5);
          v11 = mciSendSystemString(v20, 0, 0, 0);
          HeapFree(hHeap, 0, v20);
        }
        else
        {
          return 303;
        }
        return v11;
      }
      return (unsigned int)mciCloseDevice(v10, (unsigned int)dwParam1, dwParam2);
    case 0x810u:
      v11 = mciSysinfo(mciId, (unsigned int)dwParam1, dwParam2);
      v16 = v11;
      break;
    case 0x811u:
      if ( (dwParam1 & 0x100) != 0 )
      {
        if ( (dwParam1 & 0x400) != 0 )
          v15 = 284;
        else
          v15 = (unsigned int)mciSetBreakKey(mciId, *(unsigned int *)(dwParam2 + 8)) == 0 ? 0xB : 0;
      }
      else
      {
        v15 = 0;
        if ( (dwParam1 & 0x400) != 0 )
          mciSetYieldProc(mciId, 0, 0);
        else
          v15 = 273;
      }
      v11 = v15;
      v16 = v15;
      break;
    case 0x812u:
      v12 = ((dwParam1 & 2) == 0) | 0x10000;
      if ( (dwParam1 & 0x100) != 0 )
        v13 = *(const WCHAR **)(dwParam2 + 8);
      else
        v13 = L".Default";
      v14 = !PlaySoundW(v13, 0, v12) ? 0x106 : 0;
      HandleNotify(v14, v10, dwParam1, dwParam2);
      return v14;
    default:
      if ( (dwParam1 & 2) != 0 && *((unsigned int (**)(unsigned int, unsigned int))a5 + 5) == mciBreakKeyYieldProc )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids);
        }
        GetKeyState(*((_DWORD *)a5 + 12));
      }
      return (unsigned int)SendDriverMessage(*((HDRVR *)a5 + 12), message, dwParam1, dwParam2);
  }
  HandleNotify(v16, v10, dwParam1, dwParam2);
  return v11;
}

```

## disassembly

```asm
0x1800102a8  push    rbx
0x1800102aa  push    rbp
0x1800102ab  push    rsi
0x1800102ac  push    rdi
0x1800102ad  push    r14
0x1800102af  sub     rsp, 20h
0x1800102b3  mov     eax, edx
0x1800102b5  mov     rbp, r9
0x1800102b8  mov     rdi, r8
0x1800102bb  mov     esi, edx
0x1800102bd  mov     r14d, ecx
0x1800102c0  sub     eax, 803h
0x1800102c5  jz      loc_1800104DB
0x1800102cb  sub     eax, 1
0x1800102ce  jz      loc_180010414
0x1800102d4  sub     eax, 0Ch
0x1800102d7  jz      loc_1800103F3
0x1800102dd  sub     eax, 1
0x1800102e0  jz      loc_1800103AA
0x1800102e6  cmp     eax, 1
0x1800102e9  jz      short loc_18001035D
0x1800102eb  mov     rbx, [rsp+48h+arg_20]
0x1800102f0  test    dil, 2
0x1800102f4  jz      short loc_180010343
0x1800102f6  lea     rax, ?mciBreakKeyYieldProc@@YAIIK@Z; mciBreakKeyYieldProc(uint,ulong)
0x1800102fd  cmp     [rbx+28h], rax
0x180010301  jnz     short loc_180010343
0x180010303  mov     rcx, cs:WPP_GLOBAL_Control
0x18001030a  lea     rax, WPP_GLOBAL_Control
0x180010311  cmp     rcx, rax
0x180010314  jz      short loc_18001033A
0x180010316  test    dword ptr [rcx+1Ch], 400000h
0x18001031d  jz      short loc_18001033A
0x18001031f  cmp     byte ptr [rcx+19h], 5
0x180010323  jb      short loc_18001033A
0x180010325  mov     rcx, [rcx+10h]
0x180010329  lea     r8, WPP_c925325bbcf0336105c06c8e14f965b6_Traceguids
0x180010330  mov     edx, 0Dh
0x180010335  call    WPP_SF_
0x18001033a  mov     ecx, [rbx+30h]; nVirtKey
0x18001033d  call    cs:__imp_GetKeyState
0x180010343  mov     rcx, [rbx+60h]; hDriver
0x180010347  mov     r9, rbp; lParam2
0x18001034a  mov     r8, rdi; lParam1
0x18001034d  mov     edx, esi; message
0x18001034f  call    cs:__imp_SendDriverMessage
0x180010355  mov     rsi, rax
0x180010358  jmp     loc_1800104EF
0x18001035d  shr     r8, 1
0x180010360  not     r8d
0x180010363  and     r8d, 1
0x180010367  bts     r8d, 10h; fdwSound
0x18001036c  bt      rdi, 8
0x180010371  jnb     short loc_180010379
0x180010373  mov     rcx, [r9+8]
0x180010377  jmp     short loc_180010380
0x180010379  lea     rcx, pszSound; ".Default"
0x180010380  xor     edx, edx; hmod
0x180010382  call    PlaySoundW
0x180010387  neg     eax
0x180010389  mov     r8d, edi; unsigned int
0x18001038c  mov     r9, rbp; unsigned __int64
0x18001038f  mov     edx, r14d; unsigned int
0x180010392  sbb     ebx, ebx
0x180010394  not     ebx
0x180010396  and     ebx, 106h
0x18001039c  mov     ecx, ebx; unsigned int
0x18001039e  call    ?HandleNotify@@YAXKIK_K@Z; HandleNotify(ulong,uint,ulong,unsigned __int64)
0x1800103a3  mov     esi, ebx
0x1800103a5  jmp     loc_1800104EF
0x1800103aa  mov     eax, edi
0x1800103ac  and     eax, 400h
0x1800103b1  bt      edi, 8
0x1800103b5  jnb     short loc_1800103D6
0x1800103b7  test    eax, eax
0x1800103b9  jz      short loc_1800103C2
0x1800103bb  mov     ebx, 11Ch
0x1800103c0  jmp     short loc_1800103ED
0x1800103c2  mov     edx, [r9+8]
0x1800103c6  call    mciSetBreakKey
0x1800103cb  neg     eax
0x1800103cd  sbb     ebx, ebx
0x1800103cf  not     ebx
0x1800103d1  and     ebx, 0Bh
0x1800103d4  jmp     short loc_1800103ED
0x1800103d6  xor     ebx, ebx
0x1800103d8  test    eax, eax
0x1800103da  jz      short loc_1800103E8
0x1800103dc  xor     r8d, r8d; dwYieldData
0x1800103df  xor     edx, edx; fpYieldProc
0x1800103e1  call    mciSetYieldProc
0x1800103e6  jmp     short loc_1800103ED
0x1800103e8  mov     ebx, 111h
0x1800103ed  mov     esi, ebx
0x1800103ef  mov     ecx, ebx
0x1800103f1  jmp     short loc_180010401
0x1800103f3  mov     r8, rbp
0x1800103f6  mov     edx, edi
0x1800103f8  call    mciSysinfo
0x1800103fd  mov     esi, eax
0x1800103ff  mov     ecx, eax; unsigned int
0x180010401  mov     edx, r14d; unsigned int
0x180010404  mov     r8d, edi; unsigned int
0x180010407  mov     r9, rbp; unsigned __int64
0x18001040a  call    ?HandleNotify@@YAXKIK_K@Z; HandleNotify(ulong,uint,ulong,unsigned __int64)
0x18001040f  jmp     loc_1800104EF
0x180010414  call    cs:__imp_GetCurrentThreadId
0x18001041a  mov     rsi, [rsp+48h+arg_20]
0x18001041f  mov     eax, eax
0x180010421  cmp     rax, [rsi+50h]
0x180010425  jz      loc_1800104C6
0x18001042b  mov     rcx, [rsi]
0x18001042e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180010432  xor     ebx, ebx
0x180010434  inc     rax
0x180010437  cmp     [rcx+rax*2], bx
0x18001043b  jnz     short loc_180010434
0x18001043d  cmp     [rsp+48h+arg_28], ebx
0x180010441  jnz     short loc_18001044D
0x180010443  mov     esi, 12Fh
0x180010448  jmp     loc_1800104EF
0x18001044d  lea     rbp, ds:0Eh[rax*2]
0x180010455  mov     ecx, ebp; Size
0x180010457  call    winmmAlloc
0x18001045c  mov     rdi, rax
0x18001045f  test    rax, rax
0x180010462  jnz     short loc_18001046E
0x180010464  mov     eax, 108h
0x180010469  jmp     loc_1800104F1
0x18001046e  lea     r8, ?wszClose@@3PAGA; "close"
0x180010475  mov     rdx, rbp; unsigned __int64
0x180010478  mov     rcx, rdi; unsigned __int16 *
0x18001047b  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180010480  lea     r8, asc_18001D9D0; " "
0x180010487  mov     rdx, rbp; unsigned __int64
0x18001048a  mov     rcx, rdi; unsigned __int16 *
0x18001048d  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180010492  mov     r8, [rsi]; unsigned __int16 *
0x180010495  mov     rdx, rbp; unsigned __int64
0x180010498  mov     rcx, rdi; unsigned __int16 *
0x18001049b  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x1800104a0  xor     r9d, r9d; unsigned int
0x1800104a3  xor     r8d, r8d; unsigned __int16 *
0x1800104a6  xor     edx, edx; unsigned int
0x1800104a8  mov     rcx, rdi; unsigned __int16 *
0x1800104ab  call    ?mciSendSystemString@@YAKPEBGKPEAGI@Z; mciSendSystemString(ushort const *,ulong,ushort *,uint)
0x1800104b0  mov     rcx, cs:hHeap; hHeap
0x1800104b7  mov     r8, rdi; lpMem
0x1800104ba  xor     edx, edx; dwFlags
0x1800104bc  mov     esi, eax
0x1800104be  call    cs:__imp_HeapFree
0x1800104c4  jmp     short loc_1800104EF
0x1800104c6  mov     edx, edi; dwParam1
0x1800104c8  mov     r9d, 1
0x1800104ce  mov     r8, rbp; dwParam2
0x1800104d1  mov     ecx, r14d; mciId
0x1800104d4  call    mciCloseDevice
0x1800104d9  jmp     short loc_1800104ED
0x1800104db  mov     r8, [rsp+48h+arg_30]
0x1800104e3  mov     ecx, edi
0x1800104e5  mov     rdx, rbp
0x1800104e8  call    mciOpenDevice
0x1800104ed  mov     esi, eax
0x1800104ef  mov     eax, esi
0x1800104f1  add     rsp, 20h
0x1800104f5  pop     r14
0x1800104f7  pop     rdi
0x1800104f8  pop     rsi
0x1800104f9  pop     rbp
0x1800104fa  pop     rbx
0x1800104fb  retn
```

# CompatibilityAdapter::EnqueJobStatus(_TASK_STATE,ushort const *,ulong)

- ea: `0x180007654`
- end: `0x1800078ff`
- name: `?EnqueJobStatus@CompatibilityAdapter@@QEAAJW4_TASK_STATE@@PEBGK@Z`
- size: `683`
- prototype: `int(CompatibilityAdapter *__hidden this, enum _TASK_STATE, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180013a80`

## callees

- `0x1800040c0`
- `0x180007654`
- `0x180007908`
- `0x180007948`
- `0x180007988`
- `0x180007994`
- `0x180007ce8`
- `0x18001073c`
- `0x180011908`
- `0x1800139fc`
- `0x1800146d0`
- `0x180030700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800077fa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007858`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007858`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078cb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800078cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007899`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007899`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000777e`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000777e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000786f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000786f`

## string_xrefs

- `0x180007868`: `Failed to signal the monitoring thread to update file\n`
- `0x1800076dc`: `TASK_STATE_UNKNOWN`
- `0x1800076d3`: `TASK_STATE_DISABLED`
- `0x1800076ca`: `TASK_STATE_QUEUED`
- `0x1800076c1`: `TASK_STATE_READY`
- `0x1800076b8`: `TASK_STATE_RUNNING`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CompatibilityAdapter::EnqueJobStatus(
        CompatibilityAdapter *this,
        enum _TASK_STATE a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 result; // rax
  const char *v9; // rax
  unsigned int v10; // ebx
  _DWORD *v11; // rax
  _DWORD *v12; // rdi
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  void *v19; // rbx
  signed int LastError; // eax
  unsigned __int64 v21; // [rsp+30h] [rbp-30h] BYREF
  void *Block; // [rsp+38h] [rbp-28h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-18h] BYREF

  if ( !a3 )
    return 2147942487LL;
  if ( a2 )
  {
    switch ( a2 )
    {
      case TASK_STATE_DISABLED:
        v9 = "TASK_STATE_DISABLED";
        break;
      case TASK_STATE_QUEUED:
        v9 = "TASK_STATE_QUEUED";
        break;
      case TASK_STATE_READY:
        v9 = "TASK_STATE_READY";
        break;
      case TASK_STATE_RUNNING:
        v9 = "TASK_STATE_RUNNING";
        break;
      default:
        v9 = "Unknown";
        break;
    }
  }
  else
  {
    v9 = "TASK_STATE_UNKNOWN";
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_SsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)&WPP_GLOBAL_Control,
      (_DWORD)a3,
      (_DWORD)a3,
      (__int64)v9,
      a4);
  }
  v21 = 0;
  result = StringCchLengthW(a3, 0x104u, &v21);
  v10 = result;
  if ( (int)result >= 0 )
  {
    v11 = operator new(0x28u);
    v12 = v11;
    Block = v11;
    if ( !v11 )
      return 2147942414LL;
    *v11 = a2;
    v11[4] = a4;
    if ( a2 == TASK_STATE_RUNNING )
    {
      FileTime = GetLocalTimeAsFileTime();
      SystemTime = 0;
      FileTimeToSystemTime(&FileTime, &SystemTime);
      *(struct _SYSTEMTIME *)(v12 + 5) = SystemTime;
    }
    v13 = v21 + 1;
    v14 = (unsigned __int16 *)operator new[](saturated_mul(v21 + 1, 2u));
    *((_QWORD *)v12 + 1) = v14;
    if ( !v14 )
    {
      v10 = -2147024882;
LABEL_27:
      operator delete(v12);
      return v10;
    }
    if ( (int)StringCchCopyW(v14, v13, a3) < 0 )
    {
      operator delete(*((void **)v12 + 1));
      goto LABEL_27;
    }
    FileTime = (FILETIME)((char *)this + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v15 = *((_QWORD *)this + 8);
    v17 = std::_List_buy<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::_Buynode<JOB_STATE_CHANGE_INFO * const &>(
            v16,
            v15,
            *(_QWORD *)(v15 + 8),
            &Block);
    v18 = *((_QWORD *)this + 9);
    if ( v18 == 0xAAAAAAAAAAAAAA9LL )
      std::_Xlength_error("list<T> too long");
    *((_QWORD *)this + 9) = v18 + 1;
    *(_QWORD *)(v15 + 8) = v17;
    **(_QWORD **)(v17 + 8) = v17;
    if ( !SetEvent(*((HANDLE *)this + 11)) )
    {
      OutputDebugStringW(L"Failed to signal the monitoring thread to update file\n");
      std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front((char *)this + 64);
      v19 = Block;
      operator delete(*((void **)Block + 1));
      operator delete(v19);
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      return v10;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180007654  mov     [rsp-28h+arg_8], rbx
0x180007659  mov     [rsp-28h+arg_18], rsi
0x18000765e  push    rbp
0x18000765f  push    rdi
0x180007660  push    r13
0x180007662  push    r14
0x180007664  push    r15
0x180007666  mov     rbp, rsp
0x180007669  sub     rsp, 60h
0x18000766d  mov     rax, cs:__security_cookie
0x180007674  xor     rax, rsp
0x180007677  mov     [rbp+var_8], rax
0x18000767b  mov     r15d, r9d
0x18000767e  mov     r14, r8
0x180007681  mov     esi, edx
0x180007683  mov     r13, rcx
0x180007686  test    r8, r8
0x180007689  jnz     short loc_180007695
0x18000768b  mov     eax, 80070057h
0x180007690  jmp     loc_1800078D9
0x180007695  mov     ecx, esi
0x180007697  test    esi, esi
0x180007699  jz      short loc_1800076DC
0x18000769b  sub     ecx, 1
0x18000769e  jz      short loc_1800076D3
0x1800076a0  sub     ecx, 1
0x1800076a3  jz      short loc_1800076CA
0x1800076a5  sub     ecx, 1
0x1800076a8  jz      short loc_1800076C1
0x1800076aa  cmp     ecx, 1
0x1800076ad  jz      short loc_1800076B8
0x1800076af  lea     rax, aUnknown; "Unknown"
0x1800076b6  jmp     short loc_1800076E3
0x1800076b8  lea     rax, aTaskStateRunni; "TASK_STATE_RUNNING"
0x1800076bf  jmp     short loc_1800076E3
0x1800076c1  lea     rax, aTaskStateReady; "TASK_STATE_READY"
0x1800076c8  jmp     short loc_1800076E3
0x1800076ca  lea     rax, aTaskStateQueue; "TASK_STATE_QUEUED"
0x1800076d1  jmp     short loc_1800076E3
0x1800076d3  lea     rax, aTaskStateDisab; "TASK_STATE_DISABLED"
0x1800076da  jmp     short loc_1800076E3
0x1800076dc  lea     rax, aTaskStateUnkno; "TASK_STATE_UNKNOWN"
0x1800076e3  lea     rdx, WPP_GLOBAL_Control
0x1800076ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076f1  cmp     rcx, rdx
0x1800076f4  jz      short loc_180007718
0x1800076f6  test    byte ptr [rcx+1Ch], 2
0x1800076fa  jz      short loc_180007718
0x1800076fc  cmp     byte ptr [rcx+19h], 4
0x180007700  jb      short loc_180007718
0x180007702  mov     [rsp+60h+var_38], r15d
0x180007707  mov     [rsp+60h+var_40], rax
0x18000770c  mov     r9, r14
0x18000770f  mov     rcx, [rcx+10h]
0x180007713  call    WPP_SF_SsD
0x180007718  mov     [rbp+var_30], 0
0x180007720  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180007724  mov     edx, 104h; unsigned __int64
0x180007729  mov     rcx, r14; unsigned __int16 *
0x18000772c  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180007731  mov     ebx, eax
0x180007733  test    eax, eax
0x180007735  js      loc_1800078D9
0x18000773b  mov     ecx, 28h ; '('; Size
0x180007740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007745  mov     rdi, rax
0x180007748  mov     [rbp+Block], rax
0x18000774c  test    rax, rax
0x18000774f  jnz     short loc_18000775B
0x180007751  mov     eax, 8007000Eh
0x180007756  jmp     loc_1800078D9
0x18000775b  mov     [rax], esi
0x18000775d  mov     [rax+10h], r15d
0x180007761  cmp     esi, 4
0x180007764  jnz     short loc_180007793
0x180007766  call    ?GetLocalTimeAsFileTime@@YA?AU_FILETIME@@XZ; GetLocalTimeAsFileTime(void)
0x18000776b  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18000776f  xorps   xmm0, xmm0
0x180007772  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180007776  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x18000777a  lea     rcx, [rbp+FileTime]; lpFileTime
0x18000777e  call    cs:__imp_FileTimeToSystemTime
0x180007785  nop     dword ptr [rax+rax+00h]
0x18000778a  movups  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x18000778e  movdqu  xmmword ptr [rdi+14h], xmm0
0x180007793  mov     rsi, [rbp+var_30]
0x180007797  inc     rsi
0x18000779a  mov     eax, 2
0x18000779f  mul     rsi
0x1800077a2  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800077a9  cmovb   rax, rcx
0x1800077ad  mov     rcx, rax; unsigned __int64
0x1800077b0  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800077b5  mov     [rdi+8], rax
0x1800077b9  test    rax, rax
0x1800077bc  jnz     short loc_1800077C5
0x1800077be  mov     ebx, 8007000Eh
0x1800077c3  jmp     short loc_1800077E0
0x1800077c5  mov     r8, r14; unsigned __int16 *
0x1800077c8  mov     rdx, rsi; unsigned __int64
0x1800077cb  mov     rcx, rax; unsigned __int16 *
0x1800077ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800077d3  test    eax, eax
0x1800077d5  jns     short loc_1800077EF
0x1800077d7  mov     rcx, [rdi+8]; Block
0x1800077db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800077e0  mov     rcx, rdi; Block
0x1800077e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800077e8  mov     eax, ebx
0x1800077ea  jmp     loc_1800078D9
0x1800077ef  lea     rdi, [r13+18h]
0x1800077f3  mov     qword ptr [rbp+FileTime.dwLowDateTime], rdi
0x1800077f7  mov     rcx, rdi; lpCriticalSection
0x1800077fa  call    cs:__imp_EnterCriticalSection
0x180007801  nop     dword ptr [rax+rax+00h]
0x180007806  nop
0x180007807  mov     rsi, [r13+40h]
0x18000780b  lea     r9, [rbp+Block]
0x18000780f  mov     r8, [rsi+8]
0x180007813  mov     rdx, rsi
0x180007816  call    ??$_Buynode@AEBQEAUJOB_STATE_CHANGE_INFO@@@?$_List_buy@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAPEAU?$_List_node@PEAUJOB_STATE_CHANGE_INFO@@PEAX@1@PEAU21@0AEBQEAUJOB_STATE_CHANGE_INFO@@@Z; std::_List_buy<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::_Buynode<JOB_STATE_CHANGE_INFO * const &>(std::_List_node<JOB_STATE_CHANGE_INFO *,void *> *,std::_List_node<JOB_STATE_CHANGE_INFO *,void *> *,JOB_STATE_CHANGE_INFO * const &)
0x18000781b  mov     rdx, rax
0x18000781e  mov     rax, [r13+48h]
0x180007822  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000782c  sub     rcx, rax
0x18000782f  cmp     rcx, 1
0x180007833  jnb     short loc_180007842
0x180007835  lea     rcx, aListTTooLong; "list<T> too long"
0x18000783c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180007842  inc     rax
0x180007845  mov     [r13+48h], rax
0x180007849  mov     [rsi+8], rdx
0x18000784d  mov     rax, [rdx+8]
0x180007851  mov     [rax], rdx
0x180007854  mov     rcx, [r13+58h]; hEvent
0x180007858  call    cs:__imp_SetEvent
0x18000785f  nop     dword ptr [rax+rax+00h]
0x180007864  test    eax, eax
0x180007866  jnz     short loc_1800078C8
0x180007868  lea     rcx, aFailedToSignal_0; "Failed to signal the monitoring thread "...
0x18000786f  call    cs:__imp_OutputDebugStringW
0x180007876  nop     dword ptr [rax+rax+00h]
0x18000787b  lea     rcx, [r13+40h]
0x18000787f  call    ?pop_front@?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAXXZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front(void)
0x180007884  mov     rbx, [rbp+Block]
0x180007888  mov     rcx, [rbx+8]; Block
0x18000788c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007891  mov     rcx, rbx; Block
0x180007894  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007899  call    cs:__imp_GetLastError
0x1800078a0  nop     dword ptr [rax+rax+00h]
0x1800078a5  mov     ebx, eax
0x1800078a7  test    eax, eax
0x1800078a9  jle     short loc_1800078B4
0x1800078ab  movzx   ebx, ax
0x1800078ae  or      ebx, 80070000h
0x1800078b4  mov     rcx, rdi; lpCriticalSection
0x1800078b7  call    cs:__imp_LeaveCriticalSection
0x1800078be  nop     dword ptr [rax+rax+00h]
0x1800078c3  jmp     loc_1800077E8
0x1800078c8  mov     rcx, rdi; lpCriticalSection
0x1800078cb  call    cs:__imp_LeaveCriticalSection
0x1800078d2  nop     dword ptr [rax+rax+00h]
0x1800078d7  xor     eax, eax
0x1800078d9  mov     rcx, [rbp+var_8]
0x1800078dd  xor     rcx, rsp; StackCookie
0x1800078e0  call    __security_check_cookie
0x1800078e5  lea     r11, [rsp+60h+var_s0]
0x1800078ea  mov     rbx, [r11+38h]
0x1800078ee  mov     rsi, [r11+48h]
0x1800078f2  mov     rsp, r11
0x1800078f5  pop     r15
0x1800078f7  pop     r14
0x1800078f9  pop     r13
0x1800078fb  pop     rdi
0x1800078fc  pop     rbp
0x1800078fd  retn
```

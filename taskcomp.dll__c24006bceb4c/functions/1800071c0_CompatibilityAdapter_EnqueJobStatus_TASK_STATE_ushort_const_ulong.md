# CompatibilityAdapter::EnqueJobStatus(_TASK_STATE,ushort const *,ulong)

- ea: `0x1800071c0`
- end: `0x180007440`
- name: `?EnqueJobStatus@CompatibilityAdapter@@QEAAJW4_TASK_STATE@@PEBGK@Z`
- size: `640`
- prototype: `__int64 __fastcall(CompatibilityAdapter *this, enum _TASK_STATE, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x180012ea0`

## callees

- `0x180003ef0`
- `0x1800071c0`
- `0x180007448`
- `0x180007488`
- `0x1800074c8`
- `0x1800074d4`
- `0x180007828`
- `0x18000fd68`
- `0x180010eb8`
- `0x180012e24`
- `0x180013aa8`
- `0x18002e5b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007360`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007360`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073b8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800073b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007413`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007413`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073ed`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800072ea`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800072ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800073c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800073c9`

## string_xrefs

- `0x1800073c2`: `Failed to signal the monitoring thread to update file\n`
- `0x180007248`: `TASK_STATE_UNKNOWN`
- `0x18000723f`: `TASK_STATE_DISABLED`
- `0x180007236`: `TASK_STATE_QUEUED`
- `0x18000722d`: `TASK_STATE_READY`
- `0x180007224`: `TASK_STATE_RUNNING`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800071c0  mov     [rsp-28h+arg_8], rbx
0x1800071c5  mov     [rsp-28h+arg_18], rsi
0x1800071ca  push    rbp
0x1800071cb  push    rdi
0x1800071cc  push    r13
0x1800071ce  push    r14
0x1800071d0  push    r15
0x1800071d2  mov     rbp, rsp
0x1800071d5  sub     rsp, 60h
0x1800071d9  mov     rax, cs:__security_cookie
0x1800071e0  xor     rax, rsp
0x1800071e3  mov     [rbp+var_8], rax
0x1800071e7  mov     r15d, r9d
0x1800071ea  mov     r14, r8
0x1800071ed  mov     esi, edx
0x1800071ef  mov     r13, rcx
0x1800071f2  test    r8, r8
0x1800071f5  jnz     short loc_180007201
0x1800071f7  mov     eax, 80070057h
0x1800071fc  jmp     loc_18000741B
0x180007201  mov     ecx, esi
0x180007203  test    esi, esi
0x180007205  jz      short loc_180007248
0x180007207  sub     ecx, 1
0x18000720a  jz      short loc_18000723F
0x18000720c  sub     ecx, 1
0x18000720f  jz      short loc_180007236
0x180007211  sub     ecx, 1
0x180007214  jz      short loc_18000722D
0x180007216  cmp     ecx, 1
0x180007219  jz      short loc_180007224
0x18000721b  lea     rax, aUnknown; "Unknown"
0x180007222  jmp     short loc_18000724F
0x180007224  lea     rax, aTaskStateRunni; "TASK_STATE_RUNNING"
0x18000722b  jmp     short loc_18000724F
0x18000722d  lea     rax, aTaskStateReady; "TASK_STATE_READY"
0x180007234  jmp     short loc_18000724F
0x180007236  lea     rax, aTaskStateQueue; "TASK_STATE_QUEUED"
0x18000723d  jmp     short loc_18000724F
0x18000723f  lea     rax, aTaskStateDisab; "TASK_STATE_DISABLED"
0x180007246  jmp     short loc_18000724F
0x180007248  lea     rax, aTaskStateUnkno; "TASK_STATE_UNKNOWN"
0x18000724f  lea     rdx, WPP_GLOBAL_Control
0x180007256  mov     rcx, cs:WPP_GLOBAL_Control
0x18000725d  cmp     rcx, rdx
0x180007260  jz      short loc_180007284
0x180007262  test    byte ptr [rcx+1Ch], 2
0x180007266  jz      short loc_180007284
0x180007268  cmp     byte ptr [rcx+19h], 4
0x18000726c  jb      short loc_180007284
0x18000726e  mov     [rsp+60h+var_38], r15d
0x180007273  mov     [rsp+60h+var_40], rax
0x180007278  mov     r9, r14
0x18000727b  mov     rcx, [rcx+10h]
0x18000727f  call    WPP_SF_SsD
0x180007284  mov     [rbp+var_30], 0
0x18000728c  lea     r8, [rbp+var_30]; unsigned __int64 *
0x180007290  mov     edx, 104h; unsigned __int64
0x180007295  mov     rcx, r14; unsigned __int16 *
0x180007298  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000729d  mov     ebx, eax
0x18000729f  test    eax, eax
0x1800072a1  js      loc_18000741B
0x1800072a7  mov     ecx, 28h ; '('; Size
0x1800072ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800072b1  mov     rdi, rax
0x1800072b4  mov     [rbp+Block], rax
0x1800072b8  test    rax, rax
0x1800072bb  jnz     short loc_1800072C7
0x1800072bd  mov     eax, 8007000Eh
0x1800072c2  jmp     loc_18000741B
0x1800072c7  mov     [rax], esi
0x1800072c9  mov     [rax+10h], r15d
0x1800072cd  cmp     esi, 4
0x1800072d0  jnz     short loc_1800072F9
0x1800072d2  call    ?GetLocalTimeAsFileTime@@YA?AU_FILETIME@@XZ; GetLocalTimeAsFileTime(void)
0x1800072d7  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x1800072db  xorps   xmm0, xmm0
0x1800072de  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800072e2  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x1800072e6  lea     rcx, [rbp+FileTime]; lpFileTime
0x1800072ea  call    cs:__imp_FileTimeToSystemTime
0x1800072f0  movups  xmm0, xmmword ptr [rbp+SystemTime.wYear]
0x1800072f4  movdqu  xmmword ptr [rdi+14h], xmm0
0x1800072f9  mov     rsi, [rbp+var_30]
0x1800072fd  inc     rsi
0x180007300  mov     eax, 2
0x180007305  mul     rsi
0x180007308  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000730f  cmovb   rax, rcx
0x180007313  mov     rcx, rax; unsigned __int64
0x180007316  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000731b  mov     [rdi+8], rax
0x18000731f  test    rax, rax
0x180007322  jnz     short loc_18000732B
0x180007324  mov     ebx, 8007000Eh
0x180007329  jmp     short loc_180007346
0x18000732b  mov     r8, r14; unsigned __int16 *
0x18000732e  mov     rdx, rsi; unsigned __int64
0x180007331  mov     rcx, rax; unsigned __int16 *
0x180007334  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007339  test    eax, eax
0x18000733b  jns     short loc_180007355
0x18000733d  mov     rcx, [rdi+8]; Block
0x180007341  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007346  mov     rcx, rdi; Block
0x180007349  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000734e  mov     eax, ebx
0x180007350  jmp     loc_18000741B
0x180007355  lea     rdi, [r13+18h]
0x180007359  mov     qword ptr [rbp+FileTime.dwLowDateTime], rdi
0x18000735d  mov     rcx, rdi; lpCriticalSection
0x180007360  call    cs:__imp_EnterCriticalSection
0x180007366  nop
0x180007367  mov     rsi, [r13+40h]
0x18000736b  lea     r9, [rbp+Block]
0x18000736f  mov     r8, [rsi+8]
0x180007373  mov     rdx, rsi
0x180007376  call    ??$_Buynode@AEBQEAUJOB_STATE_CHANGE_INFO@@@?$_List_buy@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAPEAU?$_List_node@PEAUJOB_STATE_CHANGE_INFO@@PEAX@1@PEAU21@0AEBQEAUJOB_STATE_CHANGE_INFO@@@Z; std::_List_buy<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::_Buynode<JOB_STATE_CHANGE_INFO * const &>(std::_List_node<JOB_STATE_CHANGE_INFO *,void *> *,std::_List_node<JOB_STATE_CHANGE_INFO *,void *> *,JOB_STATE_CHANGE_INFO * const &)
0x18000737b  mov     rdx, rax
0x18000737e  mov     rax, [r13+48h]
0x180007382  mov     rcx, 0AAAAAAAAAAAAAA9h
0x18000738c  sub     rcx, rax
0x18000738f  cmp     rcx, 1
0x180007393  jnb     short loc_1800073A2
0x180007395  lea     rcx, aListTTooLong; "list<T> too long"
0x18000739c  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800073a2  inc     rax
0x1800073a5  mov     [r13+48h], rax
0x1800073a9  mov     [rsi+8], rdx
0x1800073ad  mov     rax, [rdx+8]
0x1800073b1  mov     [rax], rdx
0x1800073b4  mov     rcx, [r13+58h]; hEvent
0x1800073b8  call    cs:__imp_SetEvent
0x1800073be  test    eax, eax
0x1800073c0  jnz     short loc_180007410
0x1800073c2  lea     rcx, aFailedToSignal_0; "Failed to signal the monitoring thread "...
0x1800073c9  call    cs:__imp_OutputDebugStringW
0x1800073cf  lea     rcx, [r13+40h]
0x1800073d3  call    ?pop_front@?$list@PEAUJOB_STATE_CHANGE_INFO@@V?$t_allocator@PEAUJOB_STATE_CHANGE_INFO@@@@@std@@QEAAXXZ; std::list<JOB_STATE_CHANGE_INFO *,t_allocator<JOB_STATE_CHANGE_INFO *>>::pop_front(void)
0x1800073d8  mov     rbx, [rbp+Block]
0x1800073dc  mov     rcx, [rbx+8]; Block
0x1800073e0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073e5  mov     rcx, rbx; Block
0x1800073e8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073ed  call    cs:__imp_GetLastError
0x1800073f3  mov     ebx, eax
0x1800073f5  test    eax, eax
0x1800073f7  jle     short loc_180007402
0x1800073f9  movzx   ebx, ax
0x1800073fc  or      ebx, 80070000h
0x180007402  mov     rcx, rdi; lpCriticalSection
0x180007405  call    cs:__imp_LeaveCriticalSection
0x18000740b  jmp     loc_18000734E
0x180007410  mov     rcx, rdi; lpCriticalSection
0x180007413  call    cs:__imp_LeaveCriticalSection
0x180007419  xor     eax, eax
0x18000741b  mov     rcx, [rbp+var_8]
0x18000741f  xor     rcx, rsp; StackCookie
0x180007422  call    __security_check_cookie
0x180007427  lea     r11, [rsp+60h+var_s0]
0x18000742c  mov     rbx, [r11+38h]
0x180007430  mov     rsi, [r11+48h]
0x180007434  mov     rsp, r11
0x180007437  pop     r15
0x180007439  pop     r14
0x18000743b  pop     r13
0x18000743d  pop     rdi
0x18000743e  pop     rbp
0x18000743f  retn
```

# TaskLock::TaskLock(ushort const *)

- ea: `0x18000635c`
- end: `0x1800064b4`
- name: `??0TaskLock@@QEAA@PEBG@Z`
- size: `344`
- prototype: `TaskLock *__fastcall(TaskLock *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004820`
- `0x180010750`
- `0x180010bd0`
- `0x180012560`
- `0x180012ea0`
- `0x180015280`

## callees

- `0x1800031a0`
- `0x180003ef0`
- `0x18000635c`
- `0x1800064bc`
- `0x18000fcd4`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18000639e`
- `msvcrt!_wcsupr` at `0x18000639e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006418`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006418`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800063c1`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800063c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006471`

## string_xrefs

- `0x18000637a`: `Local\TASKSCHED_`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
TaskLock *__fastcall TaskLock::TaskLock(TaskLock *this, const unsigned __int16 *a2)
{
  unsigned int v3; // r11d
  const unsigned __int16 *v4; // r10
  HANDLE Semaphore; // rax
  char v6; // al
  int v7; // edx
  int v8; // r8d
  char LastError; // al

  *((_QWORD *)this + 65) = 0;
  StringCchCopyW((unsigned __int16 *)this, 0x104u, L"Local\\TASKSCHED_");
  StringCchCatW((unsigned __int16 *)this, v3, v4);
  _wcsupr((wchar_t *)this + 6);
  Semaphore = CreateSemaphoreExW(0, 1, 1, (LPCWSTR)this, 0, 0x1F0003u);
  *((_QWORD *)this + 65) = Semaphore;
  if ( Semaphore )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        (unsigned int)WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids,
        (_DWORD)this,
        (char)Semaphore);
    }
    v6 = WaitForSingleObject(*((HANDLE *)this + 65), 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v8, (_DWORD)this, *((_DWORD *)this + 130), v6);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_SD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids,
      (_DWORD)this,
      LastError);
  }
  return this;
}

```

## disassembly

```asm
0x18000635c  mov     [rsp+arg_0], rbx
0x180006361  push    rdi
0x180006362  sub     rsp, 30h
0x180006366  mov     r10, rdx
0x180006369  mov     qword ptr [rcx+208h], 0
0x180006374  mov     r11d, 104h
0x18000637a  lea     r8, aLocalTasksched; "Local\\TASKSCHED_"
0x180006381  mov     edx, r11d; unsigned __int64
0x180006384  mov     rbx, rcx
0x180006387  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000638c  mov     r8, r10; unsigned __int16 *
0x18000638f  mov     edx, r11d; unsigned __int64
0x180006392  mov     rcx, rbx; unsigned __int16 *
0x180006395  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000639a  lea     rcx, [rbx+0Ch]; String
0x18000639e  call    cs:__imp__wcsupr
0x1800063a4  mov     edx, 1; lInitialCount
0x1800063a9  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800063b1  mov     r8d, edx; lMaximumCount
0x1800063b4  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800063bc  mov     r9, rbx; lpName
0x1800063bf  xor     ecx, ecx; lpSemaphoreAttributes
0x1800063c1  call    cs:__imp_CreateSemaphoreExW
0x1800063c7  mov     [rbx+208h], rax
0x1800063ce  test    rax, rax
0x1800063d1  jz      short loc_180006452
0x1800063d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800063da  lea     rdi, WPP_GLOBAL_Control
0x1800063e1  cmp     rcx, rdi
0x1800063e4  jz      short loc_18000640E
0x1800063e6  test    byte ptr [rcx+1Ch], 2
0x1800063ea  jz      short loc_18000640E
0x1800063ec  cmp     byte ptr [rcx+19h], 4
0x1800063f0  jb      short loc_18000640E
0x1800063f2  mov     rcx, [rcx+10h]
0x1800063f6  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x1800063fd  mov     edx, 0Ah
0x180006402  mov     [rsp+38h+dwFlags], eax
0x180006406  mov     r9, rbx
0x180006409  call    WPP_SF_SD
0x18000640e  mov     rcx, [rbx+208h]; hHandle
0x180006415  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006418  call    cs:__imp_WaitForSingleObject
0x18000641e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006425  cmp     rcx, rdi
0x180006428  jz      short loc_1800064A6
0x18000642a  test    byte ptr [rcx+1Ch], 2
0x18000642e  jz      short loc_1800064A6
0x180006430  cmp     byte ptr [rcx+19h], 4
0x180006434  jb      short loc_1800064A6
0x180006436  mov     rcx, [rcx+10h]
0x18000643a  mov     r9, rbx
0x18000643d  mov     [rsp+38h+dwDesiredAccess], eax
0x180006441  mov     eax, [rbx+208h]
0x180006447  mov     [rsp+38h+dwFlags], eax
0x18000644b  call    WPP_SF_SDd
0x180006450  jmp     short loc_1800064A6
0x180006452  mov     rax, cs:WPP_GLOBAL_Control
0x180006459  lea     rdi, WPP_GLOBAL_Control
0x180006460  cmp     rax, rdi
0x180006463  jz      short loc_1800064A6
0x180006465  test    byte ptr [rax+1Ch], 2
0x180006469  jz      short loc_1800064A6
0x18000646b  cmp     byte ptr [rax+19h], 2
0x18000646f  jb      short loc_1800064A6
0x180006471  call    cs:__imp_GetLastError
0x180006477  test    eax, eax
0x180006479  jle     short loc_180006483
0x18000647b  movzx   eax, ax
0x18000647e  or      eax, 80070000h
0x180006483  mov     rcx, cs:WPP_GLOBAL_Control
0x18000648a  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x180006491  mov     edx, 0Ch
0x180006496  mov     [rsp+38h+dwFlags], eax
0x18000649a  mov     r9, rbx
0x18000649d  mov     rcx, [rcx+10h]
0x1800064a1  call    WPP_SF_SD
0x1800064a6  mov     rax, rbx
0x1800064a9  mov     rbx, [rsp+38h+arg_0]
0x1800064ae  add     rsp, 30h
0x1800064b2  pop     rdi
0x1800064b3  retn
```

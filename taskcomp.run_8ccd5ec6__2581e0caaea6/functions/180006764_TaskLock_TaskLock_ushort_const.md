# TaskLock::TaskLock(ushort const *)

- ea: `0x180006764`
- end: `0x1800068dd`
- name: `??0TaskLock@@QEAA@PEBG@Z`
- size: `377`
- prototype: `TaskLock *__fastcall(TaskLock *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180004a40`
- `0x1800111e0`
- `0x180011600`
- `0x1800130c0`
- `0x180013a80`
- `0x180016040`

## callees

- `0x180003320`
- `0x1800040c0`
- `0x180006764`
- `0x1800068e4`
- `0x1800106a0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x1800067a6`
- `msvcrt!_wcsupr` at `0x1800067a6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006830`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006830`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800067cf`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x1800067cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006893`

## string_xrefs

- `0x180006782`: `Local\TASKSCHED_`

## pseudocode

```c
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
0x180006764  mov     [rsp+arg_0], rbx
0x180006769  push    rdi
0x18000676a  sub     rsp, 30h
0x18000676e  mov     r10, rdx
0x180006771  mov     qword ptr [rcx+208h], 0
0x18000677c  mov     r11d, 104h
0x180006782  lea     r8, aLocalTasksched; "Local\\TASKSCHED_"
0x180006789  mov     edx, r11d; unsigned __int64
0x18000678c  mov     rbx, rcx
0x18000678f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006794  mov     r8, r10; unsigned __int16 *
0x180006797  mov     edx, r11d; unsigned __int64
0x18000679a  mov     rcx, rbx; unsigned __int16 *
0x18000679d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067a2  lea     rcx, [rbx+0Ch]; String
0x1800067a6  call    cs:__imp__wcsupr
0x1800067ad  nop     dword ptr [rax+rax+00h]
0x1800067b2  mov     edx, 1; lInitialCount
0x1800067b7  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x1800067bf  mov     r8d, edx; lMaximumCount
0x1800067c2  mov     [rsp+38h+dwFlags], 0; dwFlags
0x1800067ca  mov     r9, rbx; lpName
0x1800067cd  xor     ecx, ecx; lpSemaphoreAttributes
0x1800067cf  call    cs:__imp_CreateSemaphoreExW
0x1800067d6  nop     dword ptr [rax+rax+00h]
0x1800067db  mov     [rbx+208h], rax
0x1800067e2  test    rax, rax
0x1800067e5  jz      loc_180006874
0x1800067eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067f2  lea     rdi, WPP_GLOBAL_Control
0x1800067f9  cmp     rcx, rdi
0x1800067fc  jz      short loc_180006826
0x1800067fe  test    byte ptr [rcx+1Ch], 2
0x180006802  jz      short loc_180006826
0x180006804  cmp     byte ptr [rcx+19h], 4
0x180006808  jb      short loc_180006826
0x18000680a  mov     rcx, [rcx+10h]
0x18000680e  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x180006815  mov     edx, 0Ah
0x18000681a  mov     [rsp+38h+dwFlags], eax
0x18000681e  mov     r9, rbx
0x180006821  call    WPP_SF_SD
0x180006826  mov     rcx, [rbx+208h]; hHandle
0x18000682d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180006830  call    cs:__imp_WaitForSingleObject
0x180006837  nop     dword ptr [rax+rax+00h]
0x18000683c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006843  cmp     rcx, rdi
0x180006846  jz      loc_1800068CE
0x18000684c  test    byte ptr [rcx+1Ch], 2
0x180006850  jz      short loc_1800068CE
0x180006852  cmp     byte ptr [rcx+19h], 4
0x180006856  jb      short loc_1800068CE
0x180006858  mov     rcx, [rcx+10h]
0x18000685c  mov     r9, rbx
0x18000685f  mov     [rsp+38h+dwDesiredAccess], eax
0x180006863  mov     eax, [rbx+208h]
0x180006869  mov     [rsp+38h+dwFlags], eax
0x18000686d  call    WPP_SF_SDd
0x180006872  jmp     short loc_1800068CE
0x180006874  mov     rax, cs:WPP_GLOBAL_Control
0x18000687b  lea     rdi, WPP_GLOBAL_Control
0x180006882  cmp     rax, rdi
0x180006885  jz      short loc_1800068CE
0x180006887  test    byte ptr [rax+1Ch], 2
0x18000688b  jz      short loc_1800068CE
0x18000688d  cmp     byte ptr [rax+19h], 2
0x180006891  jb      short loc_1800068CE
0x180006893  call    cs:__imp_GetLastError
0x18000689a  nop     dword ptr [rax+rax+00h]
0x18000689f  test    eax, eax
0x1800068a1  jle     short loc_1800068AB
0x1800068a3  movzx   eax, ax
0x1800068a6  or      eax, 80070000h
0x1800068ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068b2  lea     r8, WPP_074089b8976f3c6b31fe3e9d061e666a_Traceguids
0x1800068b9  mov     edx, 0Ch
0x1800068be  mov     [rsp+38h+dwFlags], eax
0x1800068c2  mov     r9, rbx
0x1800068c5  mov     rcx, [rcx+10h]
0x1800068c9  call    WPP_SF_SD
0x1800068ce  mov     rax, rbx
0x1800068d1  mov     rbx, [rsp+38h+arg_0]
0x1800068d6  add     rsp, 30h
0x1800068da  pop     rdi
0x1800068db  retn
```

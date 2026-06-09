# SqlEngineConfiguration::GetNumErrorLogs(int)

- ea: `0x1004219e0`
- end: `0x100421c36`
- name: `?GetNumErrorLogs@SqlEngineConfiguration@@UEAAHH@Z`
- size: `598`
- prototype: `__int64 __fastcall(SqlEngineConfiguration *__hidden this, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x1004012e0`
- `0x100401580`
- `0x100401800`
- `0x1004019a0`
- `0x1004021d0`
- `0x1004219e0`
- `0x1004476c0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421a75`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421acb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421a75`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421acb`
- `sqldk!SystemThread_TlsOffset` at `0x100421a5c`
- `sqldk!SystemThread_TlsOffset` at `0x100421ab0`
- `sqldk!SystemThread_TlsIndex` at `0x100421a53`
- `sqldk!SystemThread_TlsIndex` at `0x100421aa7`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100421b90`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100421b90`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100421a92`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100421a92`
- `api-ms-win-crt-convert-l1-1-0!_strtol_l` at `0x100421ba7`
- `api-ms-win-crt-convert-l1-1-0!_strtol_l` at `0x100421ba7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SqlEngineConfiguration::GetNumErrorLogs(SqlEngineConfiguration *this, unsigned int a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rdx
  int v9; // eax
  __crt_locale_pointers *DefaultLocale; // rax
  int v12; // [rsp+38h] [rbp-69h] BYREF
  HKEY v13; // [rsp+40h] [rbp-61h] BYREF
  DWORD cbData[2]; // [rsp+48h] [rbp-59h] BYREF
  char *EndPtr; // [rsp+50h] [rbp-51h] BYREF
  int v16; // [rsp+58h] [rbp-49h] BYREF
  __int64 v17; // [rsp+60h] [rbp-41h]
  int v18; // [rsp+68h] [rbp-39h] BYREF
  int v19; // [rsp+6Ch] [rbp-35h]
  __int64 v20; // [rsp+70h] [rbp-31h]
  int v21; // [rsp+78h] [rbp-29h] BYREF
  __int64 v22; // [rsp+80h] [rbp-21h]
  __int64 v23; // [rsp+88h] [rbp-19h]
  __int64 v24; // [rsp+90h] [rbp-11h]
  __int64 v25; // [rsp+98h] [rbp-9h]
  bool v26; // [rsp+A8h] [rbp+7h]
  __int64 v27; // [rsp+B8h] [rbp+17h]
  CHAR String[31]; // [rsp+C0h] [rbp+1Fh] BYREF
  char v29; // [rsp+DFh] [rbp+3Eh]

  v27 = -2;
  Worker::TaskAutoOnFlags::TaskAutoOnFlags(&v16, 1);
  *(_QWORD *)cbData = &v18;
  v21 = 536871530;
  v22 = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  v6 = *(_QWORD *)(v5 + 600);
  if ( v6 )
    v26 = (unsigned int)SOS_Task::PushWait(v6, &v21) == 0;
  v7 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v8 = *(_QWORD *)(v7 + 256);
  if ( !v8 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v8 = *(_QWORD *)(v7 + 256);
  }
  v20 = v8;
  v19 = (*(_DWORD *)(v8 + 800) >> 11) & 1;
  if ( v19 || (*(_BYTE *)(v8 + 800) & 4) == 0 )
  {
    v18 = 1;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 608) + 8LL))(*(_QWORD *)(v8 + 608));
  }
  else
  {
    v18 = 0;
  }
  v13 = 0;
  v9 = (*(__int64 (__fastcall **)(SqlEngineConfiguration *))(*(_QWORD *)this + 272LL))(this);
  if ( !(unsigned int)IniRegOpenKeyExW(-2147483646, v9, 0, 131097, &v13) )
  {
    cbData[0] = 32;
    if ( !(unsigned int)IniRegQueryValueExA((int)v13, (int)"NumErrorLogs", 0, (int)&v12, String, cbData) )
    {
      if ( v12 == 1 )
      {
        v29 = 0;
        DefaultLocale = GetDefaultLocale();
        a2 = _strtol_l(String, &EndPtr, 10, DefaultLocale);
      }
      else if ( v12 == 4 )
      {
        a2 = *(_DWORD *)String;
      }
    }
  }
  if ( v13 )
    IniRegCloseKey(v13);
  EndPtr = (char *)&v18;
  if ( v18 )
  {
    if ( v19 )
      *(_DWORD *)(v20 + 800) |= 0x800u;
    else
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(v20 + 608) + 16LL))(
        *(_QWORD *)(v20 + 608),
        v20,
        1);
  }
  SOS_ExternalAutoWait::~SOS_ExternalAutoWait((SOS_ExternalAutoWait *)&v21);
  *(_DWORD *)(v17 + 616) &= ~v16;
  return a2;
}

```

## disassembly

```asm
0x1004219e0  mov     rax, rsp
0x1004219e3  push    rbp
0x1004219e4  push    rdi
0x1004219e5  push    r14
0x1004219e7  lea     rbp, [rax-5Fh]
0x1004219eb  sub     rsp, 0E0h
0x1004219f2  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x1004219fa  mov     [rax+10h], rbx
0x1004219fe  mov     [rax+18h], rsi
0x100421a02  mov     rax, cs:__security_cookie
0x100421a09  xor     rax, rsp
0x100421a0c  mov     [rbp+57h+var_18], rax
0x100421a10  mov     ebx, edx
0x100421a12  mov     rsi, rcx
0x100421a15  mov     edx, 1
0x100421a1a  lea     rcx, [rbp+57h+var_A0]
0x100421a1e  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100421a23  nop
0x100421a24  lea     rax, [rbp+57h+var_90]
0x100421a28  mov     qword ptr [rbp+57h+cbData], rax
0x100421a2c  mov     [rbp+57h+var_80], 2000026Ah
0x100421a33  xor     r14d, r14d
0x100421a36  mov     [rbp+57h+var_78], r14
0x100421a3a  mov     [rbp+57h+var_68], r14
0x100421a3e  mov     [rbp+57h+var_70], r14
0x100421a42  mov     [rbp+57h+var_60], r14
0x100421a46  mov     [rbp+57h+var_50], r14b
0x100421a4a  mov     rdx, gs:58h
0x100421a53  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100421a5a  mov     ecx, [rax]
0x100421a5c  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100421a63  mov     edi, [rax]
0x100421a65  add     rdi, [rdx+rcx*8]
0x100421a69  mov     rcx, [rdi+100h]
0x100421a70  test    rcx, rcx
0x100421a73  jnz     short loc_100421A82
0x100421a75  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100421a7b  mov     rcx, [rdi+100h]
0x100421a82  mov     rcx, [rcx+258h]
0x100421a89  test    rcx, rcx
0x100421a8c  jz      short loc_100421A9E
0x100421a8e  lea     rdx, [rbp+57h+var_80]
0x100421a92  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100421a98  test    eax, eax
0x100421a9a  setz    [rbp+57h+var_50]
0x100421a9e  mov     rdx, gs:58h
0x100421aa7  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100421aae  mov     ecx, [rax]
0x100421ab0  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100421ab7  mov     edi, [rax]
0x100421ab9  add     rdi, [rdx+rcx*8]
0x100421abd  mov     rdx, [rdi+100h]
0x100421ac4  test    rdx, rdx
0x100421ac7  jnz     short loc_100421AD8
0x100421ac9  xor     ecx, ecx
0x100421acb  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100421ad1  mov     rdx, [rdi+100h]
0x100421ad8  mov     [rbp+57h+var_88], rdx
0x100421adc  mov     eax, [rdx+320h]
0x100421ae2  shr     eax, 0Bh
0x100421ae5  and     eax, 1
0x100421ae8  mov     [rbp+57h+var_8C], eax
0x100421aeb  jnz     short loc_100421AFC
0x100421aed  test    byte ptr [rdx+320h], 4
0x100421af4  jz      short loc_100421AFC
0x100421af6  mov     [rbp+57h+var_90], r14d
0x100421afa  jmp     short loc_100421B11
0x100421afc  mov     [rbp+57h+var_90], 1
0x100421b03  mov     rcx, [rdx+260h]
0x100421b0a  mov     rax, [rcx]
0x100421b0d  call    qword ptr [rax+8]
0x100421b10  nop
0x100421b11  mov     [rbp+57h+var_B8], r14
0x100421b15  mov     rax, [rsi]
0x100421b18  mov     rcx, rsi
0x100421b1b  call    qword ptr [rax+110h]
0x100421b21  mov     rdx, rax; int
0x100421b24  lea     rax, [rbp+57h+var_B8]
0x100421b28  mov     [rsp+0F0h+var_D0], rax; PHKEY
0x100421b2d  mov     r9d, 20019h; int
0x100421b33  xor     r8d, r8d; int
0x100421b36  mov     rcx, 0FFFFFFFF80000002h; int
0x100421b3d  call    IniRegOpenKeyExW
0x100421b42  test    eax, eax
0x100421b44  jnz     short loc_100421BAF
0x100421b46  mov     [rbp+57h+cbData], 20h ; ' '
0x100421b4d  lea     rax, [rbp+57h+cbData]
0x100421b51  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x100421b56  lea     rax, [rbp+57h+String]
0x100421b5a  mov     [rsp+0F0h+var_D0], rax; LPSTR
0x100421b5f  lea     r9, [rbp+57h+var_C0]; int
0x100421b63  xor     r8d, r8d; int
0x100421b66  lea     rdx, aNumerrorlogs; "NumErrorLogs"
0x100421b6d  mov     rcx, [rbp+57h+var_B8]; int
0x100421b71  call    IniRegQueryValueExA
0x100421b76  test    eax, eax
0x100421b78  jnz     short loc_100421BAF
0x100421b7a  mov     eax, [rbp+57h+var_C0]
0x100421b7d  sub     eax, 1
0x100421b80  jz      short loc_100421B8C
0x100421b82  cmp     eax, 3
0x100421b85  jnz     short loc_100421BAF
0x100421b87  mov     ebx, dword ptr [rbp+57h+String]
0x100421b8a  jmp     short loc_100421BAF
0x100421b8c  mov     [rbp+57h+var_19], 0
0x100421b90  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100421b96  mov     r9, rax; Locale
0x100421b99  mov     r8d, 0Ah; Radix
0x100421b9f  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x100421ba3  lea     rcx, [rbp+57h+String]; String
0x100421ba7  call    cs:__imp__strtol_l
0x100421bad  mov     ebx, eax
0x100421baf  mov     rcx, [rbp+57h+var_B8]
0x100421bb3  test    rcx, rcx
0x100421bb6  jz      short loc_100421BBE
0x100421bb8  call    IniRegCloseKey
0x100421bbd  nop
0x100421bbe  lea     rax, [rbp+57h+var_90]
0x100421bc2  mov     [rbp+57h+EndPtr], rax
0x100421bc6  cmp     [rbp+57h+var_90], 0
0x100421bca  jz      short loc_100421BF7
0x100421bcc  mov     rdx, [rbp+57h+var_88]
0x100421bd0  mov     rcx, [rdx+260h]
0x100421bd7  cmp     [rbp+57h+var_8C], 0
0x100421bdb  jz      short loc_100421BE9
0x100421bdd  or      dword ptr [rdx+320h], 800h
0x100421be7  jmp     short loc_100421BF7
0x100421be9  mov     r9, [rcx]
0x100421bec  mov     r8d, 1
0x100421bf2  call    qword ptr [r9+10h]
0x100421bf6  nop
0x100421bf7  lea     rcx, [rbp+57h+var_80]; this
0x100421bfb  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x100421c00  nop
0x100421c01  mov     rdx, [rbp+57h+var_98]
0x100421c05  mov     ecx, [rbp+57h+var_A0]
0x100421c08  not     ecx
0x100421c0a  and     [rdx+268h], ecx
0x100421c10  mov     eax, ebx
0x100421c12  mov     rcx, [rbp+57h+var_18]
0x100421c16  xor     rcx, rsp; StackCookie
0x100421c19  call    __security_check_cookie
0x100421c1e  lea     r11, [rsp+0F0h+var_10]
0x100421c26  mov     rbx, [r11+28h]
0x100421c2a  mov     rsi, [r11+30h]
0x100421c2e  mov     rsp, r11
0x100421c31  pop     r14
0x100421c33  pop     rdi
0x100421c34  pop     rbp
0x100421c35  retn
```

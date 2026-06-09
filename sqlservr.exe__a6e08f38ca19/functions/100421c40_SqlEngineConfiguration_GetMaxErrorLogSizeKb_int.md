# SqlEngineConfiguration::GetMaxErrorLogSizeKb(int)

- ea: `0x100421c40`
- end: `0x100421e96`
- name: `?GetMaxErrorLogSizeKb@SqlEngineConfiguration@@UEAAHH@Z`
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
- `0x100421c40`
- `0x1004476c0`

## import_xrefs

- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421cd5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421d2b`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421cd5`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100421d2b`
- `sqldk!SystemThread_TlsOffset` at `0x100421cbc`
- `sqldk!SystemThread_TlsOffset` at `0x100421d10`
- `sqldk!SystemThread_TlsIndex` at `0x100421cb3`
- `sqldk!SystemThread_TlsIndex` at `0x100421d07`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100421df0`
- `sqldk!?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ` at `0x100421df0`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100421cf2`
- `sqldk!?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z` at `0x100421cf2`
- `api-ms-win-crt-convert-l1-1-0!_strtol_l` at `0x100421e07`
- `api-ms-win-crt-convert-l1-1-0!_strtol_l` at `0x100421e07`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SqlEngineConfiguration::GetMaxErrorLogSizeKb(SqlEngineConfiguration *this, unsigned int a2)
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
    if ( !(unsigned int)IniRegQueryValueExA((int)v13, (int)"ErrorLogSizeInKb", 0, (int)&v12, String, cbData) )
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
0x100421c40  mov     rax, rsp
0x100421c43  push    rbp
0x100421c44  push    rdi
0x100421c45  push    r14
0x100421c47  lea     rbp, [rax-5Fh]
0x100421c4b  sub     rsp, 0E0h
0x100421c52  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFEh
0x100421c5a  mov     [rax+10h], rbx
0x100421c5e  mov     [rax+18h], rsi
0x100421c62  mov     rax, cs:__security_cookie
0x100421c69  xor     rax, rsp
0x100421c6c  mov     [rbp+57h+var_18], rax
0x100421c70  mov     ebx, edx
0x100421c72  mov     rsi, rcx
0x100421c75  mov     edx, 1
0x100421c7a  lea     rcx, [rbp+57h+var_A0]
0x100421c7e  call    ??0TaskAutoOnFlags@Worker@@QEAA@W4TASK_FLAGS@@@Z; Worker::TaskAutoOnFlags::TaskAutoOnFlags(TASK_FLAGS)
0x100421c83  nop
0x100421c84  lea     rax, [rbp+57h+var_90]
0x100421c88  mov     qword ptr [rbp+57h+cbData], rax
0x100421c8c  mov     [rbp+57h+var_80], 2000026Ah
0x100421c93  xor     r14d, r14d
0x100421c96  mov     [rbp+57h+var_78], r14
0x100421c9a  mov     [rbp+57h+var_68], r14
0x100421c9e  mov     [rbp+57h+var_70], r14
0x100421ca2  mov     [rbp+57h+var_60], r14
0x100421ca6  mov     [rbp+57h+var_50], r14b
0x100421caa  mov     rdx, gs:58h
0x100421cb3  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100421cba  mov     ecx, [rax]
0x100421cbc  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100421cc3  mov     edi, [rax]
0x100421cc5  add     rdi, [rdx+rcx*8]
0x100421cc9  mov     rcx, [rdi+100h]
0x100421cd0  test    rcx, rcx
0x100421cd3  jnz     short loc_100421CE2
0x100421cd5  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100421cdb  mov     rcx, [rdi+100h]
0x100421ce2  mov     rcx, [rcx+258h]
0x100421ce9  test    rcx, rcx
0x100421cec  jz      short loc_100421CFE
0x100421cee  lea     rdx, [rbp+57h+var_80]
0x100421cf2  call    cs:__imp_?PushWait@SOS_Task@@AEAA?AW4SOS_RESULT@@PEAVSOS_ExternalAutoWait@@@Z; SOS_Task::PushWait(SOS_ExternalAutoWait *)
0x100421cf8  test    eax, eax
0x100421cfa  setz    [rbp+57h+var_50]
0x100421cfe  mov     rdx, gs:58h
0x100421d07  mov     rax, cs:__imp_SystemThread_TlsIndex
0x100421d0e  mov     ecx, [rax]
0x100421d10  mov     rax, cs:__imp_SystemThread_TlsOffset
0x100421d17  mov     edi, [rax]
0x100421d19  add     rdi, [rdx+rcx*8]
0x100421d1d  mov     rdx, [rdi+100h]
0x100421d24  test    rdx, rdx
0x100421d27  jnz     short loc_100421D38
0x100421d29  xor     ecx, ecx
0x100421d2b  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x100421d31  mov     rdx, [rdi+100h]
0x100421d38  mov     [rbp+57h+var_88], rdx
0x100421d3c  mov     eax, [rdx+320h]
0x100421d42  shr     eax, 0Bh
0x100421d45  and     eax, 1
0x100421d48  mov     [rbp+57h+var_8C], eax
0x100421d4b  jnz     short loc_100421D5C
0x100421d4d  test    byte ptr [rdx+320h], 4
0x100421d54  jz      short loc_100421D5C
0x100421d56  mov     [rbp+57h+var_90], r14d
0x100421d5a  jmp     short loc_100421D71
0x100421d5c  mov     [rbp+57h+var_90], 1
0x100421d63  mov     rcx, [rdx+260h]
0x100421d6a  mov     rax, [rcx]
0x100421d6d  call    qword ptr [rax+8]
0x100421d70  nop
0x100421d71  mov     [rbp+57h+var_B8], r14
0x100421d75  mov     rax, [rsi]
0x100421d78  mov     rcx, rsi
0x100421d7b  call    qword ptr [rax+110h]
0x100421d81  mov     rdx, rax; int
0x100421d84  lea     rax, [rbp+57h+var_B8]
0x100421d88  mov     [rsp+0F0h+var_D0], rax; PHKEY
0x100421d8d  mov     r9d, 20019h; int
0x100421d93  xor     r8d, r8d; int
0x100421d96  mov     rcx, 0FFFFFFFF80000002h; int
0x100421d9d  call    IniRegOpenKeyExW
0x100421da2  test    eax, eax
0x100421da4  jnz     short loc_100421E0F
0x100421da6  mov     [rbp+57h+cbData], 20h ; ' '
0x100421dad  lea     rax, [rbp+57h+cbData]
0x100421db1  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x100421db6  lea     rax, [rbp+57h+String]
0x100421dba  mov     [rsp+0F0h+var_D0], rax; LPSTR
0x100421dbf  lea     r9, [rbp+57h+var_C0]; int
0x100421dc3  xor     r8d, r8d; int
0x100421dc6  lea     rdx, aErrorlogsizein; "ErrorLogSizeInKb"
0x100421dcd  mov     rcx, [rbp+57h+var_B8]; int
0x100421dd1  call    IniRegQueryValueExA
0x100421dd6  test    eax, eax
0x100421dd8  jnz     short loc_100421E0F
0x100421dda  mov     eax, [rbp+57h+var_C0]
0x100421ddd  sub     eax, 1
0x100421de0  jz      short loc_100421DEC
0x100421de2  cmp     eax, 3
0x100421de5  jnz     short loc_100421E0F
0x100421de7  mov     ebx, dword ptr [rbp+57h+String]
0x100421dea  jmp     short loc_100421E0F
0x100421dec  mov     [rbp+57h+var_19], 0
0x100421df0  call    cs:__imp_?GetDefaultLocale@@YAPEAU__crt_locale_pointers@@XZ; GetDefaultLocale(void)
0x100421df6  mov     r9, rax; Locale
0x100421df9  mov     r8d, 0Ah; Radix
0x100421dff  lea     rdx, [rbp+57h+EndPtr]; EndPtr
0x100421e03  lea     rcx, [rbp+57h+String]; String
0x100421e07  call    cs:__imp__strtol_l
0x100421e0d  mov     ebx, eax
0x100421e0f  mov     rcx, [rbp+57h+var_B8]
0x100421e13  test    rcx, rcx
0x100421e16  jz      short loc_100421E1E
0x100421e18  call    IniRegCloseKey
0x100421e1d  nop
0x100421e1e  lea     rax, [rbp+57h+var_90]
0x100421e22  mov     [rbp+57h+EndPtr], rax
0x100421e26  cmp     [rbp+57h+var_90], 0
0x100421e2a  jz      short loc_100421E57
0x100421e2c  mov     rdx, [rbp+57h+var_88]
0x100421e30  mov     rcx, [rdx+260h]
0x100421e37  cmp     [rbp+57h+var_8C], 0
0x100421e3b  jz      short loc_100421E49
0x100421e3d  or      dword ptr [rdx+320h], 800h
0x100421e47  jmp     short loc_100421E57
0x100421e49  mov     r9, [rcx]
0x100421e4c  mov     r8d, 1
0x100421e52  call    qword ptr [r9+10h]
0x100421e56  nop
0x100421e57  lea     rcx, [rbp+57h+var_80]; this
0x100421e5b  call    ??1SOS_ExternalAutoWait@@QEAA@XZ; SOS_ExternalAutoWait::~SOS_ExternalAutoWait(void)
0x100421e60  nop
0x100421e61  mov     rdx, [rbp+57h+var_98]
0x100421e65  mov     ecx, [rbp+57h+var_A0]
0x100421e68  not     ecx
0x100421e6a  and     [rdx+268h], ecx
0x100421e70  mov     eax, ebx
0x100421e72  mov     rcx, [rbp+57h+var_18]
0x100421e76  xor     rcx, rsp; StackCookie
0x100421e79  call    __security_check_cookie
0x100421e7e  lea     r11, [rsp+0F0h+var_10]
0x100421e86  mov     rbx, [r11+28h]
0x100421e8a  mov     rsi, [r11+30h]
0x100421e8e  mov     rsp, r11
0x100421e91  pop     r14
0x100421e93  pop     rdi
0x100421e94  pop     rbp
0x100421e95  retn
```

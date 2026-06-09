# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong)

- ea: `0x18001f600`
- end: `0x18001f75b`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2K@Z`
- size: `347`
- prototype: `unsigned int(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800057b0`
- `0x180006650`
- `0x18000c650`

## callees

- `0x180007460`
- `0x18001f600`
- `0x18001f870`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x18001f6a8`
- `ntdll!EtwEventActivityIdControl` at `0x18001f6da`
- `ntdll!EtwEventActivityIdControl` at `0x18001f6a8`
- `ntdll!EtwEventActivityIdControl` at `0x18001f6da`
- `ntdll!EtwEventWrite` at `0x18001f6bb`
- `ntdll!EtwEventWrite` at `0x18001f6bb`
- `ntdll!EtwEventEnabled` at `0x18001f64d`
- `ntdll!EtwEventEnabled` at `0x18001f64d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f698`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f698`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6e3`

## string_xrefs

- `0x18001f6fe`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x18001f740`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        char *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        signed int a6)
{
  unsigned int v6; // eax
  __int64 v11; // rcx
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  int v13; // eax
  int v14; // edi
  EventManager *v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // r8d
  unsigned int v19; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v20[3]; // [rsp+28h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-39h] BYREF
  const struct _GUID *v22; // [rsp+50h] [rbp-29h]
  __int64 v23; // [rsp+58h] [rbp-21h]
  struct _EVENT_DATA_DESCRIPTOR v24; // [rsp+60h] [rbp-19h] BYREF
  unsigned int *v25; // [rsp+70h] [rbp-9h]
  __int64 v26; // [rsp+78h] [rbp-1h]

  v6 = a6;
  if ( a6 > 0 )
    v6 = (unsigned __int16)a6 | 0x80070000;
  v11 = *(_QWORD *)a1;
  v19 = v6;
  if ( v11 )
  {
    if ( !(unsigned __int8)EtwEventEnabled(v11, a2) )
      goto LABEL_6;
    CreateDataDescriptor(&v21, a3);
    v22 = a4;
    v23 = 16;
    CreateDataDescriptor(&v24, a5);
    v25 = &v19;
    v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    v26 = 4;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    EtwEventActivityIdControl(2, a4);
    v13 = EtwEventWrite(*(_QWORD *)a1, a2, 4, &v21);
    v20[0] = 0;
    v20[1] = 0;
    v14 = v13;
    EtwEventActivityIdControl(2, v20);
    LeaveCriticalSection(v12);
    if ( v14 )
    {
      EventManager::LogIt(v15, L"EventWrite error", v14);
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
LABEL_6:
      v14 = 0;
    }
  }
  else
  {
    v14 = 1;
  }
  v16 = (unsigned __int16)v14;
  if ( v14 >= 0 )
    v16 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v16);
  return v17;
}

```

## disassembly

```asm
0x18001f600  push    rbp
0x18001f602  push    rbx
0x18001f603  push    rsi
0x18001f604  push    rdi
0x18001f605  push    r14
0x18001f607  push    r15
0x18001f609  lea     rbp, [rsp-1Fh]
0x18001f60e  sub     rsp, 98h
0x18001f615  mov     rax, cs:__security_cookie
0x18001f61c  xor     rax, rsp
0x18001f61f  mov     [rbp+47h+var_40], rax
0x18001f623  mov     eax, [rbp+47h+arg_28]
0x18001f626  mov     r14, r9
0x18001f629  mov     r15, [rbp+47h+arg_20]
0x18001f62d  mov     rbx, r8
0x18001f630  mov     rsi, rdx
0x18001f633  mov     rdi, rcx
0x18001f636  test    eax, eax
0x18001f638  jg      loc_18001F729
0x18001f63e  mov     rcx, [rcx]
0x18001f641  mov     [rbp+47h+var_A0], eax
0x18001f644  test    rcx, rcx
0x18001f647  jz      loc_18001F736
0x18001f64d  call    cs:__imp_EtwEventEnabled
0x18001f653  test    al, al
0x18001f655  jz      loc_18001F6ED
0x18001f65b  mov     rdx, rbx; unsigned __int16 *
0x18001f65e  lea     rcx, [rbp+47h+var_80]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f662  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f667  mov     rdx, r15; unsigned __int16 *
0x18001f66a  mov     [rbp+47h+var_70], r14
0x18001f66e  lea     rcx, [rbp+47h+var_60]; struct _EVENT_DATA_DESCRIPTOR *
0x18001f672  mov     [rbp+47h+var_68], 10h
0x18001f67a  call    ?CreateDataDescriptor@@YAXAEAU_EVENT_DATA_DESCRIPTOR@@PEBG@Z; CreateDataDescriptor(_EVENT_DATA_DESCRIPTOR &,ushort const *)
0x18001f67f  lea     rcx, [rbp+47h+var_A0]
0x18001f683  mov     r15d, 4
0x18001f689  mov     [rbp+47h+var_50], rcx
0x18001f68d  lea     rbx, [rdi+8]
0x18001f691  mov     rcx, rbx; lpCriticalSection
0x18001f694  mov     [rbp+47h+var_48], r15
0x18001f698  call    cs:__imp_EnterCriticalSection
0x18001f69e  mov     rdx, r14
0x18001f6a1  lea     r14d, [r15-2]
0x18001f6a5  mov     ecx, r14d
0x18001f6a8  call    cs:__imp_EtwEventActivityIdControl
0x18001f6ae  mov     rcx, [rdi]
0x18001f6b1  lea     r9, [rbp+47h+var_80]
0x18001f6b5  mov     r8d, r15d
0x18001f6b8  mov     rdx, rsi
0x18001f6bb  call    cs:__imp_EtwEventWrite
0x18001f6c1  lea     rdx, [rbp+47h+var_98]
0x18001f6c5  mov     [rbp+47h+var_98], 0
0x18001f6cd  mov     ecx, r14d
0x18001f6d0  mov     [rbp+47h+var_90], 0
0x18001f6d8  mov     edi, eax
0x18001f6da  call    cs:__imp_EtwEventActivityIdControl
0x18001f6e0  mov     rcx, rbx; lpCriticalSection
0x18001f6e3  call    cs:__imp_LeaveCriticalSection
0x18001f6e9  test    edi, edi
0x18001f6eb  jnz     short loc_18001F73D
0x18001f6ed  xor     edi, edi
0x18001f6ef  xor     ecx, ecx
0x18001f6f1  movzx   r8d, di
0x18001f6f5  test    edi, edi
0x18001f6f7  mov     rdx, rsi
0x18001f6fa  cmovns  r8d, ecx
0x18001f6fe  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18001f705  call    TaskEventTrace
0x18001f70a  mov     eax, r8d
0x18001f70d  mov     rcx, [rbp+47h+var_40]
0x18001f711  xor     rcx, rsp; StackCookie
0x18001f714  call    __security_check_cookie
0x18001f719  add     rsp, 98h
0x18001f720  pop     r15
0x18001f722  pop     r14
0x18001f724  pop     rdi
0x18001f725  pop     rsi
0x18001f726  pop     rbx
0x18001f727  pop     rbp
0x18001f728  retn
0x18001f729  movzx   eax, ax
0x18001f72c  or      eax, 80070000h
0x18001f731  jmp     loc_18001F63E
0x18001f736  mov     edi, 1
0x18001f73b  jmp     short loc_18001F6EF
0x18001f73d  mov     r8d, edi; unsigned int
0x18001f740  lea     rdx, aEventwriteErro; "EventWrite error"
0x18001f747  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x18001f74c  test    edi, edi
0x18001f74e  jle     short loc_18001F6EF
0x18001f750  movzx   edi, di
0x18001f753  or      edi, 80070000h
0x18001f759  jmp     short loc_18001F6EF
```

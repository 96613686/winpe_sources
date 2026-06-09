# ReportTaskEvent(void *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong)

- ea: `0x180020144`
- end: `0x180020320`
- name: `?ReportTaskEvent@@YAKPEAXPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@2KK@Z`
- size: `476`
- prototype: `unsigned int __fastcall(void *, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800057b0`
- `0x18000c650`

## callees

- `0x180007460`
- `0x180020144`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180020247`
- `ntdll!EtwEventActivityIdControl` at `0x180020276`
- `ntdll!EtwEventActivityIdControl` at `0x180020247`
- `ntdll!EtwEventActivityIdControl` at `0x180020276`
- `ntdll!EtwEventWrite` at `0x18002025d`
- `ntdll!EtwEventWrite` at `0x18002025d`
- `ntdll!EtwEventEnabled` at `0x18002019c`
- `ntdll!EtwEventEnabled` at `0x18002019c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020239`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020239`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002027f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002027f`

## string_xrefs

- `0x180020295`: `ReportTaskEvent(0x%x) --> ret=%d`
- `0x1800202e3`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall ReportTaskEvent(
        char *a1,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        signed int a6,
        unsigned int a7)
{
  unsigned int v8; // edx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  struct _RTL_CRITICAL_SECTION *v15; // rbx
  int v16; // eax
  int v17; // edi
  EventManager *v18; // rcx
  __int64 v19; // r8
  unsigned int v20; // r8d
  unsigned int v22; // [rsp+20h] [rbp-61h] BYREF
  unsigned int v23; // [rsp+28h] [rbp-59h] BYREF
  _QWORD v24[2]; // [rsp+30h] [rbp-51h] BYREF
  int *v25; // [rsp+40h] [rbp-41h] BYREF
  __int64 v26; // [rsp+48h] [rbp-39h]
  const struct _GUID *v27; // [rsp+50h] [rbp-31h]
  __int64 v28; // [rsp+58h] [rbp-29h]
  int *v29; // [rsp+60h] [rbp-21h]
  __int64 v30; // [rsp+68h] [rbp-19h]
  unsigned int *v31; // [rsp+70h] [rbp-11h]
  __int64 v32; // [rsp+78h] [rbp-9h]
  unsigned int *v33; // [rsp+80h] [rbp-1h]
  __int64 v34; // [rsp+88h] [rbp+7h]

  v8 = a6;
  if ( a6 > 0 )
    v8 = (unsigned __int16)a6 | 0x80070000;
  v12 = *(_QWORD *)a1;
  v23 = a7;
  v22 = v8;
  if ( v12 )
  {
    if ( !(unsigned __int8)EtwEventEnabled(v12, a2) )
      goto LABEL_14;
    v13 = -1;
    if ( a3 )
    {
      v25 = (int *)a3;
      v14 = -1;
      do
        ++v14;
      while ( a3[v14] );
      v26 = (unsigned int)(2 * v14 + 2);
    }
    else
    {
      v25 = &dword_1800405F4;
      v26 = 2;
    }
    v27 = a4;
    v28 = 16;
    if ( a5 )
    {
      v29 = (int *)a5;
      do
        ++v13;
      while ( a5[v13] );
      v30 = (unsigned int)(2 * v13 + 2);
    }
    else
    {
      v29 = &dword_1800405F4;
      v30 = 2;
    }
    v32 = 4;
    v31 = &v22;
    v15 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
    v34 = 4;
    v33 = &v23;
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    EtwEventActivityIdControl(2, a4);
    v16 = EtwEventWrite(*(_QWORD *)a1, a2, 5, &v25);
    v24[0] = 0;
    v24[1] = 0;
    v17 = v16;
    EtwEventActivityIdControl(2, v24);
    LeaveCriticalSection(v15);
    if ( v17 )
    {
      EventManager::LogIt(v18, L"EventWrite error", v17);
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
LABEL_14:
      v17 = 0;
    }
  }
  else
  {
    v17 = 1;
  }
  v19 = (unsigned __int16)v17;
  if ( v17 >= 0 )
    v19 = 0;
  TaskEventTrace(L"ReportTaskEvent(0x%x) --> ret=%d", a2, v19);
  return v20;
}

```

## disassembly

```asm
0x180020144  mov     [rsp-8+arg_10], rbx
0x180020149  push    rbp
0x18002014a  push    rsi
0x18002014b  push    rdi
0x18002014c  push    r14
0x18002014e  push    r15
0x180020150  lea     rbp, [rsp-1Fh]
0x180020155  sub     rsp, 0A0h
0x18002015c  mov     rax, cs:__security_cookie
0x180020163  xor     rax, rsp
0x180020166  mov     [rbp+3Fh+var_30], rax
0x18002016a  mov     rsi, rdx
0x18002016d  xor     r15d, r15d
0x180020170  mov     edx, [rbp+3Fh+arg_28]
0x180020173  mov     r14, r9
0x180020176  mov     rbx, r8
0x180020179  mov     rdi, rcx
0x18002017c  test    edx, edx
0x18002017e  jg      loc_1800202D2
0x180020184  mov     rcx, [rcx]
0x180020187  mov     eax, [rbp+3Fh+arg_30]
0x18002018a  mov     [rbp+3Fh+var_98], eax
0x18002018d  mov     [rbp+3Fh+var_A0], edx
0x180020190  test    rcx, rcx
0x180020193  jz      loc_1800202CB
0x180020199  mov     rdx, rsi
0x18002019c  call    cs:__imp_EtwEventEnabled
0x1800201a2  test    al, al
0x1800201a4  jz      loc_180020289
0x1800201aa  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800201ae  lea     rdx, dword_1800405F4
0x1800201b5  test    rbx, rbx
0x1800201b8  jz      loc_1800202FE
0x1800201be  mov     [rbp+3Fh+var_80], rbx
0x1800201c2  mov     rax, rcx
0x1800201c5  inc     rax
0x1800201c8  cmp     [rbx+rax*2], r15w
0x1800201cd  jnz     short loc_1800201C5
0x1800201cf  lea     eax, ds:2[rax*2]
0x1800201d6  mov     dword ptr [rbp+3Fh+var_78+4], r15d
0x1800201da  mov     dword ptr [rbp+3Fh+var_78], eax
0x1800201dd  mov     rax, [rbp+3Fh+arg_20]
0x1800201e1  mov     [rbp+3Fh+var_70], r14
0x1800201e5  mov     [rbp+3Fh+var_68], 10h
0x1800201ed  test    rax, rax
0x1800201f0  jz      loc_18002030F
0x1800201f6  mov     [rbp+3Fh+var_60], rax
0x1800201fa  inc     rcx
0x1800201fd  cmp     [rax+rcx*2], r15w
0x180020202  jnz     short loc_1800201FA
0x180020204  lea     eax, ds:2[rcx*2]
0x18002020b  mov     dword ptr [rbp+3Fh+var_58+4], r15d
0x18002020f  mov     dword ptr [rbp+3Fh+var_58], eax
0x180020212  lea     rax, [rbp+3Fh+var_A0]
0x180020216  mov     [rbp+3Fh+var_48], 4
0x18002021e  mov     [rbp+3Fh+var_50], rax
0x180020222  lea     rbx, [rdi+8]
0x180020226  lea     rax, [rbp+3Fh+var_98]
0x18002022a  mov     [rbp+3Fh+var_38], 4
0x180020232  mov     rcx, rbx; lpCriticalSection
0x180020235  mov     [rbp+3Fh+var_40], rax
0x180020239  call    cs:__imp_EnterCriticalSection
0x18002023f  mov     rdx, r14
0x180020242  mov     ecx, 2
0x180020247  call    cs:__imp_EtwEventActivityIdControl
0x18002024d  mov     rcx, [rdi]
0x180020250  lea     r9, [rbp+3Fh+var_80]
0x180020254  mov     r8d, 5
0x18002025a  mov     rdx, rsi
0x18002025d  call    cs:__imp_EtwEventWrite
0x180020263  lea     rdx, [rbp+3Fh+var_90]
0x180020267  mov     [rbp+3Fh+var_90], r15
0x18002026b  mov     ecx, 2
0x180020270  mov     [rbp+3Fh+var_88], r15
0x180020274  mov     edi, eax
0x180020276  call    cs:__imp_EtwEventActivityIdControl
0x18002027c  mov     rcx, rbx; lpCriticalSection
0x18002027f  call    cs:__imp_LeaveCriticalSection
0x180020285  test    edi, edi
0x180020287  jnz     short loc_1800202E0
0x180020289  mov     edi, r15d
0x18002028c  test    edi, edi
0x18002028e  movzx   r8d, di
0x180020292  mov     rdx, rsi
0x180020295  lea     rcx, aReporttaskeven; "ReportTaskEvent(0x%x) --> ret=%d"
0x18002029c  cmovns  r8d, r15d
0x1800202a0  call    TaskEventTrace
0x1800202a5  mov     eax, r8d
0x1800202a8  mov     rcx, [rbp+3Fh+var_30]
0x1800202ac  xor     rcx, rsp; StackCookie
0x1800202af  call    __security_check_cookie
0x1800202b4  mov     rbx, [rsp+0C0h+arg_10]
0x1800202bc  add     rsp, 0A0h
0x1800202c3  pop     r15
0x1800202c5  pop     r14
0x1800202c7  pop     rdi
0x1800202c8  pop     rsi
0x1800202c9  pop     rbp
0x1800202ca  retn
0x1800202cb  mov     edi, 1
0x1800202d0  jmp     short loc_18002028C
0x1800202d2  movzx   edx, dx
0x1800202d5  or      edx, 80070000h
0x1800202db  jmp     loc_180020184
0x1800202e0  mov     r8d, edi; unsigned int
0x1800202e3  lea     rdx, aEventwriteErro; "EventWrite error"
0x1800202ea  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x1800202ef  test    edi, edi
0x1800202f1  jle     short loc_18002028C
0x1800202f3  movzx   edi, di
0x1800202f6  or      edi, 80070000h
0x1800202fc  jmp     short loc_18002028C
0x1800202fe  mov     [rbp+3Fh+var_80], rdx
0x180020302  mov     [rbp+3Fh+var_78], 2
0x18002030a  jmp     loc_1800201DD
0x18002030f  mov     [rbp+3Fh+var_60], rdx
0x180020313  mov     [rbp+3Fh+var_58], 2
0x18002031b  jmp     loc_180020212
```

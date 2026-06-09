# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ulong,ulong,void *,_GUID const *)

- ea: `0x180004c6c`
- end: `0x180004e08`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@1KKPEAX2@Z`
- size: `412`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const struct _GUID *, const unsigned __int16 *, char, char, void *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800057b0`
- `0x18000c650`

## callees

- `0x180004c6c`
- `0x1800207e8`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180004d55`
- `ntdll!EtwEventActivityIdControl` at `0x180004d84`
- `ntdll!EtwEventActivityIdControl` at `0x180004d55`
- `ntdll!EtwEventActivityIdControl` at `0x180004d84`
- `ntdll!EtwEventWrite` at `0x180004d6b`
- `ntdll!EtwEventWrite` at `0x180004d6b`
- `ntdll!EtwEventEnabled` at `0x180004cad`
- `ntdll!EtwEventEnabled` at `0x180004cad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004d47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004d8e`

## string_xrefs

- `0x180004dc7`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned __int16 *a5,
        char a6,
        char a7)
{
  __int64 v8; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  signed int v14; // eax
  signed int v15; // edi
  EventManager *v16; // rcx
  _QWORD v18[2]; // [rsp+20h] [rbp-61h] BYREF
  int *v19; // [rsp+30h] [rbp-51h] BYREF
  __int64 v20; // [rsp+38h] [rbp-49h]
  const struct _GUID *v21; // [rsp+40h] [rbp-41h]
  __int64 v22; // [rsp+48h] [rbp-39h]
  int *v23; // [rsp+50h] [rbp-31h]
  __int64 v24; // [rsp+58h] [rbp-29h]
  char *v25; // [rsp+60h] [rbp-21h]
  __int64 v26; // [rsp+68h] [rbp-19h]
  char *v27; // [rsp+70h] [rbp-11h]
  __int64 v28; // [rsp+78h] [rbp-9h]

  v8 = *(_QWORD *)this;
  if ( !v8 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v8, a2) )
    return 0;
  v12 = -1;
  if ( a3 )
  {
    v19 = (int *)a3;
    v13 = -1;
    do
      ++v13;
    while ( a3[v13] );
    v20 = (unsigned int)(2 * v13 + 2);
  }
  else
  {
    v19 = &dword_1800405F4;
    v20 = 2;
  }
  v21 = a4;
  v22 = 16;
  if ( a5 )
  {
    v23 = (int *)a5;
    do
      ++v12;
    while ( a5[v12] );
    v24 = (unsigned int)(2 * v12 + 2);
  }
  else
  {
    v23 = &dword_1800405F4;
    v24 = 2;
  }
  v26 = 4;
  v25 = &a6;
  v28 = 4;
  v27 = &a7;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a4);
  v14 = EtwEventWrite(*(_QWORD *)this, a2, 5, &v19);
  v18[0] = 0;
  v18[1] = 0;
  v15 = v14;
  EtwEventActivityIdControl(2, v18);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !v15 )
    return 0;
  EventManager::LogIt(v16, L"EventWrite error", v15);
  if ( v15 > 0 )
    return (unsigned __int16)v15 | 0x80070000;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180004c6c  mov     [rsp-8+arg_10], rbx
0x180004c71  push    rbp
0x180004c72  push    rsi
0x180004c73  push    rdi
0x180004c74  push    r14
0x180004c76  push    r15
0x180004c78  lea     rbp, [rsp-0Fh]
0x180004c7d  sub     rsp, 90h
0x180004c84  mov     rax, cs:__security_cookie
0x180004c8b  xor     rax, rsp
0x180004c8e  mov     [rbp+2Fh+var_30], rax
0x180004c92  mov     r14, rcx
0x180004c95  xor     r15d, r15d
0x180004c98  mov     rcx, [rcx]
0x180004c9b  mov     rdi, r9
0x180004c9e  mov     rbx, r8
0x180004ca1  mov     rsi, rdx
0x180004ca4  test    rcx, rcx
0x180004ca7  jz      loc_180004DBD
0x180004cad  call    cs:__imp_EtwEventEnabled
0x180004cb3  test    al, al
0x180004cb5  jz      loc_180004D98
0x180004cbb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180004cbf  lea     rdx, dword_1800405F4
0x180004cc6  test    rbx, rbx
0x180004cc9  jz      loc_180004DE6
0x180004ccf  mov     [rbp+2Fh+var_80], rbx
0x180004cd3  mov     rax, rcx
0x180004cd6  inc     rax
0x180004cd9  cmp     [rbx+rax*2], r15w
0x180004cde  jnz     short loc_180004CD6
0x180004ce0  lea     eax, ds:2[rax*2]
0x180004ce7  mov     dword ptr [rbp+2Fh+var_78+4], r15d
0x180004ceb  mov     dword ptr [rbp+2Fh+var_78], eax
0x180004cee  mov     rax, [rbp+2Fh+arg_20]
0x180004cf2  mov     [rbp+2Fh+var_70], rdi
0x180004cf6  mov     [rbp+2Fh+var_68], 10h
0x180004cfe  test    rax, rax
0x180004d01  jz      loc_180004DF7
0x180004d07  mov     [rbp+2Fh+var_60], rax
0x180004d0b  inc     rcx
0x180004d0e  cmp     [rax+rcx*2], r15w
0x180004d13  jnz     short loc_180004D0B
0x180004d15  lea     eax, ds:2[rcx*2]
0x180004d1c  mov     dword ptr [rbp+2Fh+var_58+4], r15d
0x180004d20  mov     dword ptr [rbp+2Fh+var_58], eax
0x180004d23  lea     rax, [rbp+2Fh+arg_28]
0x180004d27  mov     [rbp+2Fh+var_48], 4
0x180004d2f  mov     [rbp+2Fh+var_50], rax
0x180004d33  lea     rcx, [r14+8]; lpCriticalSection
0x180004d37  lea     rax, [rbp+2Fh+arg_30]
0x180004d3b  mov     [rbp+2Fh+var_38], 4
0x180004d43  mov     [rbp+2Fh+var_40], rax
0x180004d47  call    cs:__imp_EnterCriticalSection
0x180004d4d  mov     rdx, rdi
0x180004d50  mov     ecx, 2
0x180004d55  call    cs:__imp_EtwEventActivityIdControl
0x180004d5b  mov     rcx, [r14]
0x180004d5e  lea     r9, [rbp+2Fh+var_80]
0x180004d62  mov     r8d, 5
0x180004d68  mov     rdx, rsi
0x180004d6b  call    cs:__imp_EtwEventWrite
0x180004d71  lea     rdx, [rbp+2Fh+var_90]
0x180004d75  mov     [rbp+2Fh+var_90], r15
0x180004d79  mov     ecx, 2
0x180004d7e  mov     [rbp+2Fh+var_88], r15
0x180004d82  mov     edi, eax
0x180004d84  call    cs:__imp_EtwEventActivityIdControl
0x180004d8a  lea     rcx, [r14+8]; lpCriticalSection
0x180004d8e  call    cs:__imp_LeaveCriticalSection
0x180004d94  test    edi, edi
0x180004d96  jnz     short loc_180004DC4
0x180004d98  xor     eax, eax
0x180004d9a  mov     rcx, [rbp+2Fh+var_30]
0x180004d9e  xor     rcx, rsp; StackCookie
0x180004da1  call    __security_check_cookie
0x180004da6  mov     rbx, [rsp+0B0h+arg_10]
0x180004dae  add     rsp, 90h
0x180004db5  pop     r15
0x180004db7  pop     r14
0x180004db9  pop     rdi
0x180004dba  pop     rsi
0x180004dbb  pop     rbp
0x180004dbc  retn
0x180004dbd  mov     eax, 1
0x180004dc2  jmp     short loc_180004D9A
0x180004dc4  mov     r8d, edi; unsigned int
0x180004dc7  lea     rdx, aEventwriteErro; "EventWrite error"
0x180004dce  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180004dd3  test    edi, edi
0x180004dd5  jg      short loc_180004DDB
0x180004dd7  mov     eax, edi
0x180004dd9  jmp     short loc_180004D9A
0x180004ddb  movzx   edi, di
0x180004dde  or      edi, 80070000h
0x180004de4  jmp     short loc_180004DD7
0x180004de6  mov     [rbp+2Fh+var_80], rdx
0x180004dea  mov     [rbp+2Fh+var_78], 2
0x180004df2  jmp     loc_180004CEE
0x180004df7  mov     [rbp+2Fh+var_60], rdx
0x180004dfb  mov     [rbp+2Fh+var_58], 2
0x180004e03  jmp     loc_180004D23
```

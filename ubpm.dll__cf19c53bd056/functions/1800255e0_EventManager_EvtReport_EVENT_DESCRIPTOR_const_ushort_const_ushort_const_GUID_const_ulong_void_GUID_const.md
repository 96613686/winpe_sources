# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,ulong,void *,_GUID const *)

- ea: `0x1800255e0`
- end: `0x180025764`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@KPEAX2@Z`
- size: `388`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, char, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006650`

## callees

- `0x1800207e8`
- `0x1800255e0`
- `0x18003d810`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800256b9`
- `ntdll!EtwEventActivityIdControl` at `0x1800256e9`
- `ntdll!EtwEventActivityIdControl` at `0x1800256b9`
- `ntdll!EtwEventActivityIdControl` at `0x1800256e9`
- `ntdll!EtwEventWrite` at `0x1800256d0`
- `ntdll!EtwEventWrite` at `0x1800256d0`
- `ntdll!EtwEventEnabled` at `0x180025626`
- `ntdll!EtwEventEnabled` at `0x180025626`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800256ad`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800256ad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256f3`

## string_xrefs

- `0x180025747`: `EventWrite error`

## pseudocode

```c
__int64 __fastcall EventManager::EvtReport(
        EventManager *this,
        const struct _EVENT_DESCRIPTOR *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        const struct _GUID *a5,
        char a6)
{
  __int64 v7; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  signed int v12; // eax
  signed int v13; // edi
  EventManager *v14; // rcx
  _QWORD v16[2]; // [rsp+20h] [rbp-59h] BYREF
  int *v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h]
  int *v19; // [rsp+40h] [rbp-39h]
  __int64 v20; // [rsp+48h] [rbp-31h]
  const struct _GUID *v21; // [rsp+50h] [rbp-29h]
  __int64 v22; // [rsp+58h] [rbp-21h]
  char *v23; // [rsp+60h] [rbp-19h]
  __int64 v24; // [rsp+68h] [rbp-11h]

  v7 = *(_QWORD *)this;
  if ( !v7 )
    return 1;
  if ( !(unsigned __int8)EtwEventEnabled(v7, ACTION_START) )
    return 0;
  v10 = -1;
  if ( a3 )
  {
    v17 = (int *)a3;
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v18 = (unsigned int)(2 * v11 + 2);
  }
  else
  {
    v17 = &dword_1800405F4;
    v18 = 2;
  }
  if ( a4 )
  {
    v19 = (int *)a4;
    do
      ++v10;
    while ( a4[v10] );
    v20 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v19 = &dword_1800405F4;
    v20 = 2;
  }
  v21 = a5;
  v23 = &a6;
  v24 = 4;
  v22 = 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  EtwEventActivityIdControl(2, a5);
  v12 = EtwEventWrite(*(_QWORD *)this, ACTION_START, 4, &v17);
  v16[0] = 0;
  v16[1] = 0;
  v13 = v12;
  EtwEventActivityIdControl(2, v16);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( !v13 )
    return 0;
  EventManager::LogIt(v14, L"EventWrite error", v13);
  if ( v13 > 0 )
    return (unsigned __int16)v13 | 0x80070000;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800255e0  push    rbp
0x1800255e2  push    rbx
0x1800255e3  push    rsi
0x1800255e4  push    rdi
0x1800255e5  push    r14
0x1800255e7  push    r15
0x1800255e9  lea     rbp, [rsp-0Fh]
0x1800255ee  sub     rsp, 88h
0x1800255f5  mov     rax, cs:__security_cookie
0x1800255fc  xor     rax, rsp
0x1800255ff  mov     [rbp+37h+var_40], rax
0x180025603  mov     r14, [rbp+37h+arg_20]
0x180025607  mov     rsi, rcx
0x18002560a  mov     rcx, [rcx]
0x18002560d  xor     r15d, r15d
0x180025610  mov     rdi, r9
0x180025613  mov     rbx, r8
0x180025616  test    rcx, rcx
0x180025619  jz      loc_18002571B
0x18002561f  lea     rdx, ACTION_START
0x180025626  call    cs:__imp_EtwEventEnabled
0x18002562c  test    al, al
0x18002562e  jz      loc_1800256FD
0x180025634  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180025638  lea     rdx, dword_1800405F4
0x18002563f  test    rbx, rbx
0x180025642  jz      loc_180025722
0x180025648  mov     [rbp+37h+var_80], rbx
0x18002564c  mov     rax, rcx
0x18002564f  inc     rax
0x180025652  cmp     [rbx+rax*2], r15w
0x180025657  jnz     short loc_18002564F
0x180025659  lea     eax, ds:2[rax*2]
0x180025660  mov     dword ptr [rbp+37h+var_78+4], r15d
0x180025664  mov     dword ptr [rbp+37h+var_78], eax
0x180025667  test    rdi, rdi
0x18002566a  jz      loc_180025733
0x180025670  mov     [rbp+37h+var_70], rdi
0x180025674  inc     rcx
0x180025677  cmp     [rdi+rcx*2], r15w
0x18002567c  jnz     short loc_180025674
0x18002567e  lea     eax, ds:2[rcx*2]
0x180025685  mov     dword ptr [rbp+37h+var_68+4], r15d
0x180025689  mov     dword ptr [rbp+37h+var_68], eax
0x18002568c  lea     rax, [rbp+37h+arg_28]
0x180025690  mov     [rbp+37h+var_60], r14
0x180025694  mov     edi, 4
0x180025699  mov     [rbp+37h+var_50], rax
0x18002569d  lea     rcx, [rsi+8]; lpCriticalSection
0x1800256a1  mov     [rbp+37h+var_48], rdi
0x1800256a5  mov     [rbp+37h+var_58], 10h
0x1800256ad  call    cs:__imp_EnterCriticalSection
0x1800256b3  mov     rdx, r14
0x1800256b6  lea     ecx, [rdi-2]
0x1800256b9  call    cs:__imp_EtwEventActivityIdControl
0x1800256bf  mov     rcx, [rsi]
0x1800256c2  lea     r9, [rbp+37h+var_80]
0x1800256c6  mov     r8d, edi
0x1800256c9  lea     rdx, ACTION_START
0x1800256d0  call    cs:__imp_EtwEventWrite
0x1800256d6  lea     rdx, [rbp+37h+var_90]
0x1800256da  mov     [rbp+37h+var_90], r15
0x1800256de  mov     ecx, 2
0x1800256e3  mov     [rbp+37h+var_88], r15
0x1800256e7  mov     edi, eax
0x1800256e9  call    cs:__imp_EtwEventActivityIdControl
0x1800256ef  lea     rcx, [rsi+8]; lpCriticalSection
0x1800256f3  call    cs:__imp_LeaveCriticalSection
0x1800256f9  test    edi, edi
0x1800256fb  jnz     short loc_180025744
0x1800256fd  xor     eax, eax
0x1800256ff  mov     rcx, [rbp+37h+var_40]
0x180025703  xor     rcx, rsp; StackCookie
0x180025706  call    __security_check_cookie
0x18002570b  add     rsp, 88h
0x180025712  pop     r15
0x180025714  pop     r14
0x180025716  pop     rdi
0x180025717  pop     rsi
0x180025718  pop     rbx
0x180025719  pop     rbp
0x18002571a  retn
0x18002571b  mov     eax, 1
0x180025720  jmp     short loc_1800256FF
0x180025722  mov     [rbp+37h+var_80], rdx
0x180025726  mov     [rbp+37h+var_78], 2
0x18002572e  jmp     loc_180025667
0x180025733  mov     [rbp+37h+var_70], rdx
0x180025737  mov     [rbp+37h+var_68], 2
0x18002573f  jmp     loc_18002568C
0x180025744  mov     r8d, edi; unsigned int
0x180025747  lea     rdx, aEventwriteErro; "EventWrite error"
0x18002574e  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180025753  test    edi, edi
0x180025755  jle     short loc_180025760
0x180025757  movzx   edi, di
0x18002575a  or      edi, 80070000h
0x180025760  mov     eax, edi
0x180025762  jmp     short loc_1800256FF
```

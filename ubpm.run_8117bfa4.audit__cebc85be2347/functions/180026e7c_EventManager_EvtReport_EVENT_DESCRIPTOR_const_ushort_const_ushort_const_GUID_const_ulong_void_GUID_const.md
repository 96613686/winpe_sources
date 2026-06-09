# EventManager::EvtReport(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,_GUID const *,ulong,void *,_GUID const *)

- ea: `0x180026e7c`
- end: `0x180027025`
- name: `?EvtReport@EventManager@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEBG1PEBU_GUID@@KPEAX2@Z`
- size: `425`
- prototype: `__int64 __fastcall(EventManager *__hidden this, const struct _EVENT_DESCRIPTOR *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, char, void *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007000`

## callees

- `0x18001d0ec`
- `0x180026e7c`
- `0x180040260`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180026f61`
- `ntdll!EtwEventActivityIdControl` at `0x180026f9d`
- `ntdll!EtwEventActivityIdControl` at `0x180026f61`
- `ntdll!EtwEventActivityIdControl` at `0x180026f9d`
- `ntdll!EtwEventWrite` at `0x180026f7e`
- `ntdll!EtwEventWrite` at `0x180026f7e`
- `ntdll!EtwEventEnabled` at `0x180026ec2`
- `ntdll!EtwEventEnabled` at `0x180026ec2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026f4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026f4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026fad`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026fad`

## string_xrefs

- `0x180027008`: `EventWrite error`

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
  __int64 *v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h]
  __int64 *v19; // [rsp+40h] [rbp-39h]
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
    v17 = (__int64 *)a3;
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v18 = (unsigned int)(2 * v11 + 2);
  }
  else
  {
    v17 = &qword_1800439C0;
    v18 = 2;
  }
  if ( a4 )
  {
    v19 = (__int64 *)a4;
    do
      ++v10;
    while ( a4[v10] );
    v20 = (unsigned int)(2 * v10 + 2);
  }
  else
  {
    v19 = &qword_1800439C0;
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
0x180026e7c  push    rbp
0x180026e7e  push    rbx
0x180026e7f  push    rsi
0x180026e80  push    rdi
0x180026e81  push    r14
0x180026e83  push    r15
0x180026e85  lea     rbp, [rsp-0Fh]
0x180026e8a  sub     rsp, 88h
0x180026e91  mov     rax, cs:__security_cookie
0x180026e98  xor     rax, rsp
0x180026e9b  mov     [rbp+37h+var_40], rax
0x180026e9f  mov     r14, [rbp+37h+arg_20]
0x180026ea3  mov     rsi, rcx
0x180026ea6  mov     rcx, [rcx]
0x180026ea9  xor     r15d, r15d
0x180026eac  mov     rdi, r9
0x180026eaf  mov     rbx, r8
0x180026eb2  test    rcx, rcx
0x180026eb5  jz      loc_180026FDC
0x180026ebb  lea     rdx, ACTION_START
0x180026ec2  call    cs:__imp_EtwEventEnabled
0x180026ec9  nop     dword ptr [rax+rax+00h]
0x180026ece  test    al, al
0x180026ed0  jz      loc_180026FBD
0x180026ed6  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180026eda  lea     rdx, qword_1800439C0
0x180026ee1  test    rbx, rbx
0x180026ee4  jz      loc_180026FE3
0x180026eea  mov     [rbp+37h+var_80], rbx
0x180026eee  mov     rax, rcx
0x180026ef1  inc     rax
0x180026ef4  cmp     [rbx+rax*2], r15w
0x180026ef9  jnz     short loc_180026EF1
0x180026efb  lea     eax, ds:2[rax*2]
0x180026f02  mov     dword ptr [rbp+37h+var_78+4], r15d
0x180026f06  mov     dword ptr [rbp+37h+var_78], eax
0x180026f09  test    rdi, rdi
0x180026f0c  jz      loc_180026FF4
0x180026f12  mov     [rbp+37h+var_70], rdi
0x180026f16  inc     rcx
0x180026f19  cmp     [rdi+rcx*2], r15w
0x180026f1e  jnz     short loc_180026F16
0x180026f20  lea     eax, ds:2[rcx*2]
0x180026f27  mov     dword ptr [rbp+37h+var_68+4], r15d
0x180026f2b  mov     dword ptr [rbp+37h+var_68], eax
0x180026f2e  lea     rax, [rbp+37h+arg_28]
0x180026f32  mov     [rbp+37h+var_60], r14
0x180026f36  mov     edi, 4
0x180026f3b  mov     [rbp+37h+var_50], rax
0x180026f3f  lea     rcx, [rsi+8]; lpCriticalSection
0x180026f43  mov     [rbp+37h+var_48], rdi
0x180026f47  mov     [rbp+37h+var_58], 10h
0x180026f4f  call    cs:__imp_EnterCriticalSection
0x180026f56  nop     dword ptr [rax+rax+00h]
0x180026f5b  mov     rdx, r14
0x180026f5e  lea     ecx, [rdi-2]
0x180026f61  call    cs:__imp_EtwEventActivityIdControl
0x180026f68  nop     dword ptr [rax+rax+00h]
0x180026f6d  mov     rcx, [rsi]
0x180026f70  lea     r9, [rbp+37h+var_80]
0x180026f74  mov     r8d, edi
0x180026f77  lea     rdx, ACTION_START
0x180026f7e  call    cs:__imp_EtwEventWrite
0x180026f85  nop     dword ptr [rax+rax+00h]
0x180026f8a  lea     rdx, [rbp+37h+var_90]
0x180026f8e  mov     [rbp+37h+var_90], r15
0x180026f92  mov     ecx, 2
0x180026f97  mov     [rbp+37h+var_88], r15
0x180026f9b  mov     edi, eax
0x180026f9d  call    cs:__imp_EtwEventActivityIdControl
0x180026fa4  nop     dword ptr [rax+rax+00h]
0x180026fa9  lea     rcx, [rsi+8]; lpCriticalSection
0x180026fad  call    cs:__imp_LeaveCriticalSection
0x180026fb4  nop     dword ptr [rax+rax+00h]
0x180026fb9  test    edi, edi
0x180026fbb  jnz     short loc_180027005
0x180026fbd  xor     eax, eax
0x180026fbf  mov     rcx, [rbp+37h+var_40]
0x180026fc3  xor     rcx, rsp; StackCookie
0x180026fc6  call    __security_check_cookie
0x180026fcb  add     rsp, 88h
0x180026fd2  pop     r15
0x180026fd4  pop     r14
0x180026fd6  pop     rdi
0x180026fd7  pop     rsi
0x180026fd8  pop     rbx
0x180026fd9  pop     rbp
0x180026fda  retn
0x180026fdc  mov     eax, 1
0x180026fe1  jmp     short loc_180026FBF
0x180026fe3  mov     [rbp+37h+var_80], rdx
0x180026fe7  mov     [rbp+37h+var_78], 2
0x180026fef  jmp     loc_180026F09
0x180026ff4  mov     [rbp+37h+var_70], rdx
0x180026ff8  mov     [rbp+37h+var_68], 2
0x180027000  jmp     loc_180026F2E
0x180027005  mov     r8d, edi; unsigned int
0x180027008  lea     rdx, aEventwriteErro; "EventWrite error"
0x18002700f  call    ?LogIt@EventManager@@AEAAKPEBGK@Z; EventManager::LogIt(ushort const *,ulong)
0x180027014  test    edi, edi
0x180027016  jle     short loc_180027021
0x180027018  movzx   edi, di
0x18002701b  or      edi, 80070000h
0x180027021  mov     eax, edi
0x180027023  jmp     short loc_180026FBF
```

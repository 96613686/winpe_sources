# WldpLogCanExecute(_GUID const &,WLDP_EXECUTION_EVALUATION_OPTIONS,ushort const *,_WLDP_SUBJECT_TYPE,WLDP_EXECUTION_POLICY,_GUID const &)

- ea: `0x1800213bc`
- end: `0x1800214fd`
- name: `?WldpLogCanExecute@@YAXAEBU_GUID@@W4WLDP_EXECUTION_EVALUATION_OPTIONS@@PEBGW4_WLDP_SUBJECT_TYPE@@W4WLDP_EXECUTION_POLICY@@0@Z`
- size: `321`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002e5f0`
- `0x18002e8b0`
- `0x18002ecc0`
- `0x18002f2f0`

## callees

- `0x1800213bc`
- `0x180021ec0`
- `0x18002f8dc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800214d7`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800214d7`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002141c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18002141c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800214cd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800214cd`

## pseudocode

```c
int __fastcall WldpLogCanExecute(__int64 a1, size_t a2, const wchar_t *a3, int a4, int a5, LPCGUID ActivityId)
{
  const GUID *v8; // rdi
  int v9; // eax
  int result; // eax
  bool v11; // sf
  const EVENT_DESCRIPTOR *v12; // rdx
  int v13; // [rsp+38h] [rbp-49h] BYREF
  ULONGLONG RegHandle; // [rsp+40h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+48h] [rbp-39h] BYREF
  int *v16; // [rsp+58h] [rbp-29h]
  __int64 v17; // [rsp+60h] [rbp-21h]
  __int64 v18; // [rsp+68h] [rbp-19h]
  int v19; // [rsp+70h] [rbp-11h]
  int v20; // [rsp+74h] [rbp-Dh]
  int *v21; // [rsp+78h] [rbp-9h]
  __int64 v22; // [rsp+80h] [rbp-1h]
  __int64 v23; // [rsp+88h] [rbp+7h]
  __int64 v24; // [rsp+90h] [rbp+Fh]
  int *v25; // [rsp+98h] [rbp+17h]
  __int64 v26; // [rsp+A0h] [rbp+1Fh]
  int v27; // [rsp+E0h] [rbp+5Fh] BYREF
  int v28; // [rsp+F0h] [rbp+6Fh] BYREF

  v28 = a4;
  v27 = a2;
  v8 = ActivityId;
  RegHandle = 0;
  if ( a3 )
    v9 = wcsnlen_s(a3, a2);
  else
    v9 = 0;
  v13 = v9;
  result = EventRegister(&SrpEventProviderId, 0, 0, &RegHandle);
  v11 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v11 = result < 0;
  }
  if ( !v11 )
  {
    UserData.Ptr = (ULONGLONG)&a5;
    *(_QWORD *)&UserData.Size = 4;
    v16 = &v13;
    v17 = 4;
    v18 = (unsigned __int64)a3 & -(__int64)(v13 != 0);
    v19 = 2 * v13;
    v20 = 0;
    v21 = &v27;
    v22 = 4;
    v23 = a1;
    v24 = 16;
    v25 = &v28;
    v26 = 4;
    v12 = (const EVENT_DESCRIPTOR *)WldpCanExecuteFailed;
    if ( a5 )
      v12 = &WldpCanExecutePassed;
    EventWriteTransfer(RegHandle, v12, v8, 0, 6u, &UserData);
    return EventUnregister(RegHandle);
  }
  return result;
}

```

## disassembly

```asm
0x1800213bc  mov     rax, rsp
0x1800213bf  mov     [rax+8], rbx
0x1800213c3  mov     [rax+20h], r9d
0x1800213c7  mov     [rax+10h], edx
0x1800213ca  push    rbp
0x1800213cb  push    rsi
0x1800213cc  push    rdi
0x1800213cd  lea     rbp, [rax-4Fh]
0x1800213d1  sub     rsp, 0B0h
0x1800213d8  mov     rax, cs:__security_cookie
0x1800213df  xor     rax, rsp
0x1800213e2  mov     [rbp+47h+var_20], rax
0x1800213e6  mov     rbx, r8
0x1800213e9  mov     rsi, rcx
0x1800213ec  mov     rdi, [rbp+47h+ActivityId]
0x1800213f0  mov     [rbp+47h+RegHandle], 0
0x1800213f8  test    r8, r8
0x1800213fb  jnz     short loc_180021401
0x1800213fd  xor     eax, eax
0x1800213ff  jmp     short loc_180021409
0x180021401  mov     rcx, rbx; Source
0x180021404  call    wcsnlen_s
0x180021409  mov     [rbp+47h+var_90], eax
0x18002140c  lea     r9, [rbp+47h+RegHandle]; RegHandle
0x180021410  xor     r8d, r8d; CallbackContext
0x180021413  xor     edx, edx; EnableCallback
0x180021415  lea     rcx, SrpEventProviderId; ProviderId
0x18002141c  call    cs:__imp_EventRegister
0x180021422  test    eax, eax
0x180021424  jle     short loc_180021430
0x180021426  movzx   eax, ax
0x180021429  or      eax, 80070000h
0x18002142e  test    eax, eax
0x180021430  js      loc_1800214DE
0x180021436  lea     rax, [rbp+47h+arg_20]
0x18002143a  mov     [rbp+47h+UserData.Ptr], rax
0x18002143e  mov     qword ptr [rbp+47h+UserData.Size], 4
0x180021446  lea     rax, [rbp+47h+var_90]
0x18002144a  mov     [rbp+47h+var_70], rax
0x18002144e  mov     [rbp+47h+var_68], 4
0x180021456  mov     eax, [rbp+47h+var_90]
0x180021459  lea     edx, [rax+rax]
0x18002145c  neg     eax
0x18002145e  sbb     rcx, rcx
0x180021461  and     rcx, rbx
0x180021464  mov     [rbp+47h+var_60], rcx
0x180021468  mov     [rbp+47h+var_58], edx
0x18002146b  mov     [rbp+47h+var_54], 0
0x180021472  lea     rax, [rbp+47h+arg_8]
0x180021476  mov     [rbp+47h+var_50], rax
0x18002147a  mov     [rbp+47h+var_48], 4
0x180021482  mov     [rbp+47h+var_40], rsi
0x180021486  mov     [rbp+47h+var_38], 10h
0x18002148e  lea     rax, [rbp+47h+arg_18]
0x180021492  mov     [rbp+47h+var_30], rax
0x180021496  mov     [rbp+47h+var_28], 4
0x18002149e  lea     rax, [rbp+47h+UserData]
0x1800214a2  xor     r9d, r9d; RelatedActivityId
0x1800214a5  mov     r8, rdi; ActivityId
0x1800214a8  mov     rcx, [rbp+47h+RegHandle]; RegHandle
0x1800214ac  mov     [rsp+28h], rax; UserData
0x1800214b1  mov     [rsp+0C0h+UserDataCount], 6; UserDataCount
0x1800214b9  cmp     [rbp+47h+arg_20], r9d
0x1800214bd  lea     rdx, WldpCanExecuteFailed
0x1800214c4  jz      short loc_1800214CD
0x1800214c6  lea     rdx, WldpCanExecutePassed; EventDescriptor
0x1800214cd  call    cs:__imp_EventWriteTransfer
0x1800214d3  mov     rcx, [rbp+47h+RegHandle]; RegHandle
0x1800214d7  call    cs:__imp_EventUnregister
0x1800214dd  nop
0x1800214de  mov     rcx, [rbp+47h+var_20]
0x1800214e2  xor     rcx, rsp; StackCookie
0x1800214e5  call    __security_check_cookie
0x1800214ea  mov     rbx, [rsp+0C0h+arg_0]
0x1800214f2  add     rsp, 0B0h
0x1800214f9  pop     rdi
0x1800214fa  pop     rsi
0x1800214fb  pop     rbp
0x1800214fc  retn
```

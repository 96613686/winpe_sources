# _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapperArray<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)

- ea: `0x180002c90`
- end: `0x180002d96`
- name: `??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperArray@$03@@U2@U2@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperArray@$03@@44AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180023944`
- `0x180025388`

## callees

- `0x180001010`
- `0x1800050f0`

## pseudocode

```c
ULONG __fastcall _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapperArray<4>,_tlgWrapBuffer<_UNICODE_STRING>>(
        __int64 a1,
        unsigned __int8 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6,
        __int64 *a7,
        __int64 *a8,
        unsigned __int16 **a9)
{
  int v9; // ecx
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+30h] [rbp-91h] BYREF
  __int64 v12; // [rsp+50h] [rbp-71h]
  __int64 v13; // [rsp+58h] [rbp-69h]
  __int64 *v14; // [rsp+60h] [rbp-61h]
  __int64 v15; // [rsp+68h] [rbp-59h]
  __int64 v16; // [rsp+70h] [rbp-51h]
  int v17; // [rsp+78h] [rbp-49h]
  int v18; // [rsp+7Ch] [rbp-45h]
  __int64 *v19; // [rsp+80h] [rbp-41h]
  __int64 v20; // [rsp+88h] [rbp-39h]
  __int64 v21; // [rsp+90h] [rbp-31h]
  int v22; // [rsp+98h] [rbp-29h]
  int v23; // [rsp+9Ch] [rbp-25h]
  __int64 *v24; // [rsp+A0h] [rbp-21h]
  __int64 v25; // [rsp+A8h] [rbp-19h]
  __int64 v26; // [rsp+B0h] [rbp-11h]
  int v27; // [rsp+B8h] [rbp-9h]
  int v28; // [rsp+BCh] [rbp-5h]
  _DWORD *v29; // [rsp+C0h] [rbp-1h]
  __int64 v30; // [rsp+C8h] [rbp+7h]
  __int64 v31; // [rsp+D0h] [rbp+Fh]
  _DWORD v32[2]; // [rsp+D8h] [rbp+17h] BYREF

  v30 = 2;
  v29 = v32;
  v9 = **a9;
  v31 = *((_QWORD *)*a9 + 1);
  v32[0] = v9;
  v32[1] = 0;
  v25 = 2;
  v28 = 0;
  v26 = *a8;
  v27 = 4 * *((unsigned __int16 *)a8 + 4);
  v24 = a8 + 1;
  v20 = 2;
  v23 = 0;
  v15 = 2;
  v21 = *a7;
  v22 = 4 * *((unsigned __int16 *)a7 + 4);
  v19 = a7 + 1;
  v18 = 0;
  v13 = 8;
  v16 = *a6;
  v17 = 4 * *((unsigned __int16 *)a6 + 4);
  v12 = a5;
  v14 = a6 + 1;
  return tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180040010, a2, 0, 0, 0xBu, &v11);
}

```

## disassembly

```asm
0x180002c90  push    rbp
0x180002c92  lea     rbp, [rsp-2Fh]
0x180002c97  sub     rsp, 0F0h
0x180002c9e  mov     rax, cs:__security_cookie
0x180002ca5  xor     rax, rsp
0x180002ca8  mov     [rbp+2Fh+var_10], rax
0x180002cac  xor     r9d, r9d
0x180002caf  mov     [rbp+2Fh+var_28], 2
0x180002cb7  lea     rax, [rbp+2Fh+var_18]
0x180002cbb  xor     r8d, r8d
0x180002cbe  mov     [rbp+2Fh+var_30], rax
0x180002cc2  mov     rax, [rbp+2Fh+arg_40]
0x180002cc6  mov     rax, [rax]
0x180002cc9  movzx   ecx, word ptr [rax]
0x180002ccc  mov     rax, [rax+8]
0x180002cd0  mov     [rbp+2Fh+var_20], rax
0x180002cd4  mov     rax, [rbp+2Fh+arg_38]
0x180002cd8  mov     [rbp+2Fh+var_18], ecx
0x180002cdb  mov     [rbp+2Fh+var_14], r9d
0x180002cdf  mov     [rbp+2Fh+var_48], 2
0x180002ce7  lea     rcx, [rax+8]
0x180002ceb  mov     [rbp+2Fh+var_34], r9d
0x180002cef  mov     rax, [rax]
0x180002cf2  mov     [rbp+2Fh+var_40], rax
0x180002cf6  movzx   eax, word ptr [rcx]
0x180002cf9  shl     eax, 2
0x180002cfc  mov     [rbp+2Fh+var_38], eax
0x180002cff  mov     rax, [rbp+2Fh+arg_30]
0x180002d03  mov     [rbp+2Fh+var_50], rcx
0x180002d07  mov     [rbp+2Fh+var_68], 2
0x180002d0f  mov     [rbp+2Fh+var_54], r9d
0x180002d13  lea     rcx, [rax+8]
0x180002d17  mov     [rbp+2Fh+var_88], 2
0x180002d1f  mov     rax, [rax]
0x180002d22  mov     [rbp+2Fh+var_60], rax
0x180002d26  movzx   eax, word ptr [rcx]
0x180002d29  shl     eax, 2
0x180002d2c  mov     [rbp+2Fh+var_58], eax
0x180002d2f  mov     rax, [rbp+2Fh+arg_28]
0x180002d33  mov     [rbp+2Fh+var_70], rcx
0x180002d37  mov     [rbp+2Fh+var_74], r9d
0x180002d3b  mov     [rbp+2Fh+var_98], 8
0x180002d43  lea     rcx, [rax+8]
0x180002d47  mov     rax, [rax]
0x180002d4a  mov     [rbp+2Fh+var_80], rax
0x180002d4e  movzx   eax, word ptr [rcx]
0x180002d51  shl     eax, 2
0x180002d54  mov     [rbp+2Fh+var_78], eax
0x180002d57  mov     rax, [rbp+2Fh+arg_20]
0x180002d5b  mov     [rbp+2Fh+var_A0], rax
0x180002d5f  lea     rax, [rsp+0F0h+var_C0]
0x180002d64  mov     [rbp+2Fh+var_90], rcx
0x180002d68  lea     rcx, dword_180040010
0x180002d6f  mov     [rsp+0F0h+var_C8], rax
0x180002d74  mov     [rsp+0F0h+var_D0], 0Bh
0x180002d7c  call    _tlgWriteTransfer_EventWriteTransfer
0x180002d81  mov     rcx, [rbp+2Fh+var_10]
0x180002d85  xor     rcx, rsp; StackCookie
0x180002d88  call    __security_check_cookie
0x180002d8d  add     rsp, 0F0h
0x180002d94  pop     rbp
0x180002d95  retn
```

# UdfQuickGrowSession

- ea: `0x14003d0c4`
- end: `0x14003d18b`
- name: `UdfQuickGrowSession`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140017c08`

## callees

- `0x14001bc30`
- `0x14003d0c4`
- `0x14004c1b4`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003d13b`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003d13b`

## pseudocode

```c
__int64 __fastcall UdfQuickGrowSession(struct _DEVICE_OBJECT *a1, char a2)
{
  __int64 result; // rax
  union _LARGE_INTEGER v4; // [rsp+30h] [rbp-50h]
  union _LARGE_INTEGER v5; // [rsp+30h] [rbp-50h]
  __int64 v6; // [rsp+38h] [rbp-48h]
  __int64 v7; // [rsp+38h] [rbp-48h]
  size_t v8; // [rsp+40h] [rbp-40h]
  size_t v9; // [rsp+40h] [rbp-40h]
  __int64 v10; // [rsp+48h] [rbp-38h]
  __int64 v11; // [rsp+48h] [rbp-38h]
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp-30h] BYREF
  __int128 v13; // [rsp+58h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-18h] BYREF
  __int16 v15; // [rsp+70h] [rbp-10h]
  char v16; // [rsp+72h] [rbp-Eh]
  char v17; // [rsp+73h] [rbp-Dh]

  v17 = a2;
  v13 = 0;
  LOWORD(v13) = 4356;
  Interval.QuadPart = -10000000;
  v14 = 134218240;
  v15 = 76;
  v16 = 0;
  result = UdfSendSptCdb(a1, (unsigned __int8 *)&v13, &v14, 0xCu, 0, 0xF0u, v4, v6, v8, v10);
  if ( (int)result >= 0 )
  {
    KeDelayExecutionThread(0, 0, &Interval);
    v13 = 0;
    return UdfSendSptCdb(a1, (unsigned __int8 *)&v13, 0, 0, 0, 0xAu, v5, v7, v9, v11);
  }
  return result;
}

```

## disassembly

```asm
0x14003d0c4  mov     [rsp-8+arg_8], rbx
0x14003d0c9  push    rbp
0x14003d0ca  mov     rbp, rsp
0x14003d0cd  sub     rsp, 80h
0x14003d0d4  mov     rax, cs:__security_cookie
0x14003d0db  xor     rax, rsp
0x14003d0de  mov     [rbp+var_8], rax
0x14003d0e2  xorps   xmm0, xmm0
0x14003d0e5  mov     [rbp+var_D], dl
0x14003d0e8  movups  [rbp+var_28], xmm0
0x14003d0ec  mov     [rsp+80h+var_58], 0F0h
0x14003d0f4  lea     r8, [rbp+var_18]
0x14003d0f8  mov     r9d, 0Ch
0x14003d0fe  mov     word ptr [rbp+var_28], 1104h
0x14003d104  lea     rdx, [rbp+var_28]
0x14003d108  mov     qword ptr [rbp+Interval], 0FFFFFFFFFF676980h
0x14003d110  mov     rbx, rcx
0x14003d113  mov     [rbp+var_18], 8000200h
0x14003d11b  mov     [rbp+var_10], 4Ch ; 'L'
0x14003d121  mov     [rbp+var_E], 0
0x14003d125  mov     [rsp+80h+var_60], 0
0x14003d12a  call    UdfSendSptCdb
0x14003d12f  test    eax, eax
0x14003d131  js      short loc_14003D16D
0x14003d133  lea     r8, [rbp+Interval]; Interval
0x14003d137  xor     edx, edx; Alertable
0x14003d139  xor     ecx, ecx; WaitMode
0x14003d13b  call    cs:__imp_KeDelayExecutionThread
0x14003d142  nop     dword ptr [rax+rax+00h]
0x14003d147  xorps   xmm0, xmm0
0x14003d14a  mov     [rsp+80h+var_58], 0Ah
0x14003d152  xor     r9d, r9d
0x14003d155  mov     [rsp+80h+var_60], 0
0x14003d15a  xor     r8d, r8d
0x14003d15d  lea     rdx, [rbp+var_28]
0x14003d161  mov     rcx, rbx
0x14003d164  movups  [rbp+var_28], xmm0
0x14003d168  call    UdfSendSptCdb
0x14003d16d  mov     rcx, [rbp+var_8]
0x14003d171  xor     rcx, rsp; StackCookie
0x14003d174  call    __security_check_cookie
0x14003d179  mov     rbx, [rsp+80h+arg_8]
0x14003d181  add     rsp, 80h
0x14003d188  pop     rbp
0x14003d189  retn
```

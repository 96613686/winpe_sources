# UmpoTraceSmartPresencePrediction

- ea: `0x180009f14`
- end: `0x180009fbe`
- name: `UmpoTraceSmartPresencePrediction`
- size: `170`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800092a4`
- `0x180009390`

## callees

- `0x180009f14`
- `0x18000c04c`
- `0x18000d6cc`
- `0x180010070`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180009fa3`
- `ntdll!EtwEventWrite` at `0x180009fa3`

## pseudocode

```c
__int64 __fastcall UmpoTraceSmartPresencePrediction(__int64 a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v5; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v6[2]; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+48h] [rbp-38h] BYREF
  __int64 *v8; // [rsp+68h] [rbp-18h]
  __int64 v9; // [rsp+70h] [rbp-10h]
  __int64 v10; // [rsp+90h] [rbp+10h] BYREF

  v10 = a1;
  if ( (unsigned int)dword_180024190 > 5 && tlgKeywordOn() )
  {
    v5 = v10;
    v8 = &v5;
    v9 = 8;
    tlgWriteTransfer_EventWriteTransfer(v1, (unsigned __int8 *)&unk_18001F8E0, v2, v3, 3u, &v7);
  }
  v6[0] = &v10;
  v6[1] = 8;
  return EtwEventWrite(UmpoProviderHandle, UMPO_EVT_SMART_USER_PRESENCE_PREDICTION, 1, v6);
}

```

## disassembly

```asm
0x180009f14  mov     [rsp-8+arg_0], rcx
0x180009f19  push    rbp
0x180009f1a  mov     rbp, rsp
0x180009f1d  sub     rsp, 80h
0x180009f24  mov     rax, cs:__security_cookie
0x180009f2b  xor     rax, rsp
0x180009f2e  mov     [rbp+var_8], rax
0x180009f32  mov     eax, cs:dword_180024190
0x180009f38  cmp     eax, 5
0x180009f3b  jbe     short loc_180009F7B
0x180009f3d  call    _tlgKeywordOn
0x180009f42  test    al, al
0x180009f44  jz      short loc_180009F7B
0x180009f46  mov     rax, [rbp+arg_0]
0x180009f4a  lea     rdx, unk_18001F8E0; int
0x180009f51  mov     [rbp+var_50], rax
0x180009f55  lea     rax, [rbp+var_50]
0x180009f59  mov     [rbp+var_18], rax
0x180009f5d  lea     rax, [rbp+var_38]
0x180009f61  mov     [rsp+80h+var_58], rax; __int64
0x180009f66  mov     [rsp+80h+var_60], 3; ULONG
0x180009f6e  mov     [rbp+var_10], 8
0x180009f76  call    _tlgWriteTransfer_EventWriteTransfer
0x180009f7b  mov     rcx, cs:UmpoProviderHandle
0x180009f82  lea     rax, [rbp+arg_0]
0x180009f86  lea     r9, [rbp+var_48]
0x180009f8a  mov     [rbp+var_48], rax
0x180009f8e  mov     r8d, 1
0x180009f94  mov     [rbp+var_40], 8
0x180009f9c  lea     rdx, UMPO_EVT_SMART_USER_PRESENCE_PREDICTION
0x180009fa3  call    cs:__imp_EtwEventWrite
0x180009fa9  mov     rcx, [rbp+var_8]
0x180009fad  xor     rcx, rsp; StackCookie
0x180009fb0  call    __security_check_cookie
0x180009fb5  add     rsp, 80h
0x180009fbc  pop     rbp
0x180009fbd  retn
```

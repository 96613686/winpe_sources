# ScExtpUnregisterTrigger(_SERVICE_TRIGGER_SUBSCRIPTION *,int)

- ea: `0x14000fe9c`
- end: `0x14000ff87`
- name: `?ScExtpUnregisterTrigger@@YAXPEAU_SERVICE_TRIGGER_SUBSCRIPTION@@H@Z`
- size: `235`
- prototype: `void __fastcall(struct _SERVICE_TRIGGER_SUBSCRIPTION *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000f87c`
- `0x14000fe34`

## callees

- `0x14000fe9c`
- `0x1400575b0`

## import_xrefs

- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000feeb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000ff65`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000feeb`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x14000ff65`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x14000ff7c`
- `EventAggregation!BriDeleteBrokeredEvent` at `0x14000ff7c`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x14000ff4e`
- `EventAggregation!EaDeleteAggregatedEvent` at `0x14000ff4e`
- `EventAggregation!EADeleteAggregateEvent` at `0x14000ff18`
- `EventAggregation!EADeleteAggregateEvent` at `0x14000ff18`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x14000ff31`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x14000ff31`

## pseudocode

```c
void __fastcall ScExtpUnregisterTrigger(struct _SERVICE_TRIGGER_SUBSCRIPTION *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  int v4; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // [rsp+20h] [rbp-28h] BYREF
  __int128 Source2; // [rsp+28h] [rbp-20h] BYREF

  v3 = *((_DWORD *)a1 + 8) == 3;
  Source2 = 0;
  v4 = a2;
  v8 = 0;
  if ( !v3 )
  {
    v6 = *((_QWORD *)a1 + 3);
    if ( v6 )
      EADeleteAggregateEvent(v6, a2, a3);
  }
  switch ( *((_DWORD *)a1 + 8) )
  {
    case 1:
      if ( *((_QWORD *)a1 + 5) )
        DabUnregisterTriggerConsumer((char *)a1 + 40, 1);
      break;
    case 2:
      if ( RtlCompareMemory((char *)a1 + 40, &Source2, 0x10u) != 16 && RtlCompareMemory((char *)a1 + 56, &v8, 8u) != 8 )
        BriDeleteBrokeredEvent((char *)a1 + 56, v4 != 0);
      break;
    case 3:
      v7 = *((_QWORD *)a1 + 3);
      if ( v7 )
        EaDeleteAggregatedEvent(v7, v4 != 0);
      break;
  }
}

```

## disassembly

```asm
0x14000fe9c  mov     [rsp+arg_8], rbx
0x14000fea1  push    rdi
0x14000fea2  sub     rsp, 40h
0x14000fea6  mov     rax, cs:__security_cookie
0x14000fead  xor     rax, rsp
0x14000feb0  mov     [rsp+48h+var_10], rax
0x14000feb5  cmp     dword ptr [rcx+20h], 3
0x14000feb9  xorps   xmm0, xmm0
0x14000febc  movups  [rsp+48h+Source2], xmm0
0x14000fec1  mov     edi, edx
0x14000fec3  mov     [rsp+48h+var_28], 0
0x14000fecc  mov     rbx, rcx
0x14000fecf  jnz     short loc_14000FF0F
0x14000fed1  mov     ecx, [rbx+20h]
0x14000fed4  sub     ecx, 1
0x14000fed7  jz      short loc_14000FF20
0x14000fed9  sub     ecx, 1
0x14000fedc  jnz     short loc_14000FF39
0x14000fede  lea     r8d, [rcx+10h]; Length
0x14000fee2  lea     rcx, [rbx+28h]; Source1
0x14000fee6  lea     rdx, [rsp+48h+Source2]; Source2
0x14000feeb  call    cs:__imp_RtlCompareMemory
0x14000fef1  cmp     rax, 10h
0x14000fef5  jnz     short loc_14000FF56
0x14000fef7  mov     rcx, [rsp+48h+var_10]
0x14000fefc  xor     rcx, rsp; StackCookie
0x14000feff  call    __security_check_cookie
0x14000ff04  mov     rbx, [rsp+48h+arg_8]
0x14000ff09  add     rsp, 40h
0x14000ff0d  pop     rdi
0x14000ff0e  retn
0x14000ff0f  mov     rcx, [rcx+18h]
0x14000ff13  test    rcx, rcx
0x14000ff16  jz      short loc_14000FED1
0x14000ff18  call    cs:__imp_EADeleteAggregateEvent
0x14000ff1e  jmp     short loc_14000FED1
0x14000ff20  lea     rcx, [rbx+28h]
0x14000ff24  cmp     qword ptr [rcx], 0
0x14000ff28  jz      short loc_14000FEF7
0x14000ff2a  xor     r8d, r8d
0x14000ff2d  lea     edx, [r8+1]
0x14000ff31  call    cs:__imp_DabUnregisterTriggerConsumer
0x14000ff37  jmp     short loc_14000FEF7
0x14000ff39  cmp     ecx, 1
0x14000ff3c  jnz     short loc_14000FEF7
0x14000ff3e  mov     rcx, [rbx+18h]
0x14000ff42  test    rcx, rcx
0x14000ff45  jz      short loc_14000FEF7
0x14000ff47  xor     edx, edx
0x14000ff49  test    edi, edi
0x14000ff4b  setnz   dl
0x14000ff4e  call    cs:__imp_EaDeleteAggregatedEvent
0x14000ff54  jmp     short loc_14000FEF7
0x14000ff56  mov     r8d, 8; Length
0x14000ff5c  lea     rdx, [rsp+48h+var_28]; Source2
0x14000ff61  lea     rcx, [rbx+38h]; Source1
0x14000ff65  call    cs:__imp_RtlCompareMemory
0x14000ff6b  cmp     rax, 8
0x14000ff6f  jz      short loc_14000FEF7
0x14000ff71  xor     edx, edx
0x14000ff73  lea     rcx, [rbx+38h]
0x14000ff77  test    edi, edi
0x14000ff79  setnz   dl
0x14000ff7c  call    cs:__imp_BriDeleteBrokeredEvent
0x14000ff82  jmp     loc_14000FEF7
```

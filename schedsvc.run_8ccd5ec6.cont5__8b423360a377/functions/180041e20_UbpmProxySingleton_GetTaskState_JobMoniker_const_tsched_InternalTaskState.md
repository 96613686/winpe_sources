# UbpmProxySingleton::GetTaskState(JobMoniker const &,tsched::InternalTaskState &)

- ea: `0x180041e20`
- end: `0x180041fdf`
- name: `?GetTaskState@UbpmProxySingleton@@UEAAJAEBVJobMoniker@@AEAW4InternalTaskState@tsched@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(UbpmProxySingleton *__hidden this, const struct JobMoniker *, enum tsched::InternalTaskState *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180041e20`
- `0x180059140`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x180041ed6`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x180041ed6`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180041fc2`
- `UBPM!UbpmCloseTriggerConsumer` at `0x180041fc2`
- `UBPM!UbpmApiBufferFree` at `0x180041fa3`
- `UBPM!UbpmApiBufferFree` at `0x180041fa3`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180041e5d`
- `UBPM!UbpmOpenTriggerConsumer` at `0x180041e5d`

## pseudocode

```c
__int64 __fastcall UbpmProxySingleton::GetTaskState(
        UbpmProxySingleton *this,
        const struct JobMoniker *a2,
        enum tsched::InternalTaskState *a3)
{
  __int64 *v3; // rax
  __int64 v6; // rdx
  int v7; // eax
  signed int v8; // ebx
  int v9; // eax
  __int64 v10; // rdx
  unsigned int i; // r9d
  __int64 v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+68h] [rbp+20h] BYREF

  v3 = (__int64 *)*((_QWORD *)a2 + 2);
  v14 = 0;
  v13 = 0;
  if ( v3 )
    v6 = *v3;
  else
    v6 = 0;
  v7 = UbpmOpenTriggerConsumer(a2, v6, &v14);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v8 >> 31) & 0xFFFFFFFE) + 4 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
      *((_QWORD *)a2 + 3),
      v8);
  }
  if ( v8 < 0 )
    goto LABEL_30;
  v9 = UbpmTriggerConsumerQueryStatus(v14, &v13);
  v8 = v9;
  if ( v9 > 0 )
    v8 = (unsigned __int16)v9 | 0x80070000;
  v10 = v13;
  if ( v8 >= 0 )
  {
    if ( !v13 )
    {
      v8 = -2147418113;
      goto LABEL_31;
    }
    *(_DWORD *)a3 = 0;
    for ( i = 0; i < *(_DWORD *)(v10 + 28); ++i )
    {
      switch ( *(_BYTE *)(56LL * i + *(_QWORD *)(v10 + 32) + 32) )
      {
        case 1:
          *(_DWORD *)a3 = 2;
          goto LABEL_31;
        case 2:
          if ( *(_DWORD *)a3 != 1 )
            *(_DWORD *)a3 = 0;
          break;
        case 3:
          *(_DWORD *)a3 = 1;
          break;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids,
        *((_QWORD *)a2 + 3),
        *(_DWORD *)a3);
LABEL_30:
      v10 = v13;
    }
  }
LABEL_31:
  if ( v10 )
  {
    UbpmApiBufferFree(v10);
    v13 = 0;
  }
  if ( v14 )
    UbpmCloseTriggerConsumer();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180041e20  mov     [rsp+arg_0], rbx
0x180041e25  push    rsi
0x180041e26  push    rdi
0x180041e27  push    r12
0x180041e29  sub     rsp, 30h
0x180041e2d  mov     rax, [rdx+10h]
0x180041e31  mov     rdi, r8
0x180041e34  mov     [rsp+48h+arg_18], 0
0x180041e3d  mov     rsi, rdx
0x180041e40  mov     [rsp+48h+arg_8], 0
0x180041e49  test    rax, rax
0x180041e4c  jz      short loc_180041E53
0x180041e4e  mov     rdx, [rax]
0x180041e51  jmp     short loc_180041E55
0x180041e53  xor     edx, edx
0x180041e55  lea     r8, [rsp+48h+arg_18]
0x180041e5a  mov     rcx, rsi
0x180041e5d  call    cs:__imp_UbpmOpenTriggerConsumer
0x180041e64  nop     dword ptr [rax+rax+00h]
0x180041e69  mov     ebx, eax
0x180041e6b  test    eax, eax
0x180041e6d  jle     short loc_180041E78
0x180041e6f  movzx   ebx, ax
0x180041e72  or      ebx, 80070000h
0x180041e78  mov     rcx, cs:WPP_GLOBAL_Control
0x180041e7f  lea     r12, WPP_GLOBAL_Control
0x180041e86  cmp     rcx, r12
0x180041e89  jz      short loc_180041EC4
0x180041e8b  test    dword ptr [rcx+1Ch], 100h
0x180041e92  jz      short loc_180041EC4
0x180041e94  movzx   eax, byte ptr [rcx+19h]
0x180041e98  mov     edx, ebx
0x180041e9a  sar     edx, 1Fh
0x180041e9d  and     edx, 0FFFFFFFEh
0x180041ea0  add     edx, 4
0x180041ea3  cmp     eax, edx
0x180041ea5  jb      short loc_180041EC4
0x180041ea7  mov     r9, [rsi+18h]
0x180041eab  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x180041eb2  mov     rcx, [rcx+10h]
0x180041eb6  mov     edx, 0Ah
0x180041ebb  mov     [rsp+48h+var_28], ebx
0x180041ebf  call    WPP_SF_Sd
0x180041ec4  test    ebx, ebx
0x180041ec6  js      loc_180041F96
0x180041ecc  mov     rcx, [rsp+48h+arg_18]
0x180041ed1  lea     rdx, [rsp+48h+arg_8]
0x180041ed6  call    cs:__imp_UbpmTriggerConsumerQueryStatus
0x180041edd  nop     dword ptr [rax+rax+00h]
0x180041ee2  mov     ebx, eax
0x180041ee4  test    eax, eax
0x180041ee6  jle     short loc_180041EF1
0x180041ee8  movzx   ebx, ax
0x180041eeb  or      ebx, 80070000h
0x180041ef1  mov     rdx, [rsp+48h+arg_8]
0x180041ef6  test    ebx, ebx
0x180041ef8  js      loc_180041F9B
0x180041efe  test    rdx, rdx
0x180041f01  jnz     short loc_180041F0D
0x180041f03  mov     ebx, 8000FFFFh
0x180041f08  jmp     loc_180041F9B
0x180041f0d  mov     dword ptr [rdi], 0
0x180041f13  xor     r9d, r9d
0x180041f16  cmp     r9d, [rdx+1Ch]
0x180041f1a  jnb     short loc_180041F5C
0x180041f1c  mov     eax, r9d
0x180041f1f  imul    rcx, rax, 38h ; '8'
0x180041f23  mov     rax, [rdx+20h]
0x180041f27  movzx   r8d, byte ptr [rcx+rax+20h]
0x180041f2d  sub     r8d, 1
0x180041f31  jz      short loc_180041F54
0x180041f33  sub     r8d, 1
0x180041f37  jz      short loc_180041F44
0x180041f39  cmp     r8d, 1
0x180041f3d  jnz     short loc_180041F4F
0x180041f3f  mov     [rdi], r8d
0x180041f42  jmp     short loc_180041F4F
0x180041f44  cmp     dword ptr [rdi], 1
0x180041f47  jz      short loc_180041F4F
0x180041f49  mov     dword ptr [rdi], 0
0x180041f4f  inc     r9d
0x180041f52  jmp     short loc_180041F16
0x180041f54  mov     dword ptr [rdi], 2
0x180041f5a  jmp     short loc_180041F9B
0x180041f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f63  cmp     rcx, r12
0x180041f66  jz      short loc_180041F9B
0x180041f68  test    dword ptr [rcx+1Ch], 100h
0x180041f6f  jz      short loc_180041F9B
0x180041f71  cmp     byte ptr [rcx+19h], 4
0x180041f75  jb      short loc_180041F9B
0x180041f77  mov     eax, [rdi]
0x180041f79  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x180041f80  mov     r9, [rsi+18h]
0x180041f84  mov     edx, 1Ah
0x180041f89  mov     rcx, [rcx+10h]
0x180041f8d  mov     [rsp+48h+var_28], eax
0x180041f91  call    WPP_SF_Sd
0x180041f96  mov     rdx, [rsp+48h+arg_8]
0x180041f9b  test    rdx, rdx
0x180041f9e  jz      short loc_180041FB8
0x180041fa0  mov     rcx, rdx
0x180041fa3  call    cs:__imp_UbpmApiBufferFree
0x180041faa  nop     dword ptr [rax+rax+00h]
0x180041faf  mov     [rsp+48h+arg_8], 0
0x180041fb8  mov     rcx, [rsp+48h+arg_18]
0x180041fbd  test    rcx, rcx
0x180041fc0  jz      short loc_180041FCE
0x180041fc2  call    cs:__imp_UbpmCloseTriggerConsumer
0x180041fc9  nop     dword ptr [rax+rax+00h]
0x180041fce  mov     eax, ebx
0x180041fd0  mov     rbx, [rsp+48h+arg_0]
0x180041fd5  add     rsp, 30h
0x180041fd9  pop     r12
0x180041fdb  pop     rdi
0x180041fdc  pop     rsi
0x180041fdd  retn
```

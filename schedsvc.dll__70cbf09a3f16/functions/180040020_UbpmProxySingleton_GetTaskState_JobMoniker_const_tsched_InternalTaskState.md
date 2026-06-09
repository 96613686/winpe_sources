# UbpmProxySingleton::GetTaskState(JobMoniker const &,tsched::InternalTaskState &)

- ea: `0x180040020`
- end: `0x1800401c6`
- name: `?GetTaskState@UbpmProxySingleton@@UEAAJAEBVJobMoniker@@AEAW4InternalTaskState@tsched@@@Z`
- size: `422`
- prototype: `__int64 __fastcall(UbpmProxySingleton *__hidden this, const struct JobMoniker *, enum tsched::InternalTaskState *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180040020`
- `0x180056794`

## import_xrefs

- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x1800400d0`
- `UBPM!UbpmTriggerConsumerQueryStatus` at `0x1800400d0`
- `UBPM!UbpmCloseTriggerConsumer` at `0x1800401b0`
- `UBPM!UbpmCloseTriggerConsumer` at `0x1800401b0`
- `UBPM!UbpmApiBufferFree` at `0x180040197`
- `UBPM!UbpmApiBufferFree` at `0x180040197`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004005d`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18004005d`

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
    UbpmApiBufferFree(v10, v10);
    v13 = 0;
  }
  if ( v14 )
    UbpmCloseTriggerConsumer();
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180040020  mov     [rsp+arg_0], rbx
0x180040025  push    rsi
0x180040026  push    rdi
0x180040027  push    r12
0x180040029  sub     rsp, 30h
0x18004002d  mov     rax, [rdx+10h]
0x180040031  mov     rdi, r8
0x180040034  mov     [rsp+48h+arg_18], 0
0x18004003d  mov     rsi, rdx
0x180040040  mov     [rsp+48h+arg_8], 0
0x180040049  test    rax, rax
0x18004004c  jz      short loc_180040053
0x18004004e  mov     rdx, [rax]
0x180040051  jmp     short loc_180040055
0x180040053  xor     edx, edx
0x180040055  lea     r8, [rsp+48h+arg_18]
0x18004005a  mov     rcx, rsi
0x18004005d  call    cs:__imp_UbpmOpenTriggerConsumer
0x180040063  mov     ebx, eax
0x180040065  test    eax, eax
0x180040067  jle     short loc_180040072
0x180040069  movzx   ebx, ax
0x18004006c  or      ebx, 80070000h
0x180040072  mov     rcx, cs:WPP_GLOBAL_Control
0x180040079  lea     r12, WPP_GLOBAL_Control
0x180040080  cmp     rcx, r12
0x180040083  jz      short loc_1800400BE
0x180040085  test    dword ptr [rcx+1Ch], 100h
0x18004008c  jz      short loc_1800400BE
0x18004008e  movzx   eax, byte ptr [rcx+19h]
0x180040092  mov     edx, ebx
0x180040094  sar     edx, 1Fh
0x180040097  and     edx, 0FFFFFFFEh
0x18004009a  add     edx, 4
0x18004009d  cmp     eax, edx
0x18004009f  jb      short loc_1800400BE
0x1800400a1  mov     r9, [rsi+18h]
0x1800400a5  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x1800400ac  mov     rcx, [rcx+10h]
0x1800400b0  mov     edx, 0Ah
0x1800400b5  mov     [rsp+48h+var_28], ebx
0x1800400b9  call    WPP_SF_Sd
0x1800400be  test    ebx, ebx
0x1800400c0  js      loc_18004018A
0x1800400c6  mov     rcx, [rsp+48h+arg_18]
0x1800400cb  lea     rdx, [rsp+48h+arg_8]
0x1800400d0  call    cs:__imp_UbpmTriggerConsumerQueryStatus
0x1800400d6  mov     ebx, eax
0x1800400d8  test    eax, eax
0x1800400da  jle     short loc_1800400E5
0x1800400dc  movzx   ebx, ax
0x1800400df  or      ebx, 80070000h
0x1800400e5  mov     rdx, [rsp+48h+arg_8]
0x1800400ea  test    ebx, ebx
0x1800400ec  js      loc_18004018F
0x1800400f2  test    rdx, rdx
0x1800400f5  jnz     short loc_180040101
0x1800400f7  mov     ebx, 8000FFFFh
0x1800400fc  jmp     loc_18004018F
0x180040101  mov     dword ptr [rdi], 0
0x180040107  xor     r9d, r9d
0x18004010a  cmp     r9d, [rdx+1Ch]
0x18004010e  jnb     short loc_180040150
0x180040110  mov     eax, r9d
0x180040113  imul    rcx, rax, 38h ; '8'
0x180040117  mov     rax, [rdx+20h]
0x18004011b  movzx   r8d, byte ptr [rcx+rax+20h]
0x180040121  sub     r8d, 1
0x180040125  jz      short loc_180040148
0x180040127  sub     r8d, 1
0x18004012b  jz      short loc_180040138
0x18004012d  cmp     r8d, 1
0x180040131  jnz     short loc_180040143
0x180040133  mov     [rdi], r8d
0x180040136  jmp     short loc_180040143
0x180040138  cmp     dword ptr [rdi], 1
0x18004013b  jz      short loc_180040143
0x18004013d  mov     dword ptr [rdi], 0
0x180040143  inc     r9d
0x180040146  jmp     short loc_18004010A
0x180040148  mov     dword ptr [rdi], 2
0x18004014e  jmp     short loc_18004018F
0x180040150  mov     rcx, cs:WPP_GLOBAL_Control
0x180040157  cmp     rcx, r12
0x18004015a  jz      short loc_18004018F
0x18004015c  test    dword ptr [rcx+1Ch], 100h
0x180040163  jz      short loc_18004018F
0x180040165  cmp     byte ptr [rcx+19h], 4
0x180040169  jb      short loc_18004018F
0x18004016b  mov     eax, [rdi]
0x18004016d  lea     r8, WPP_ffeb42fce81a3445f9740a981b62c86a_Traceguids
0x180040174  mov     r9, [rsi+18h]
0x180040178  mov     edx, 1Ah
0x18004017d  mov     rcx, [rcx+10h]
0x180040181  mov     [rsp+48h+var_28], eax
0x180040185  call    WPP_SF_Sd
0x18004018a  mov     rdx, [rsp+48h+arg_8]
0x18004018f  test    rdx, rdx
0x180040192  jz      short loc_1800401A6
0x180040194  mov     rcx, rdx
0x180040197  call    cs:__imp_UbpmApiBufferFree
0x18004019d  mov     [rsp+48h+arg_8], 0
0x1800401a6  mov     rcx, [rsp+48h+arg_18]
0x1800401ab  test    rcx, rcx
0x1800401ae  jz      short loc_1800401B6
0x1800401b0  call    cs:__imp_UbpmCloseTriggerConsumer
0x1800401b6  mov     eax, ebx
0x1800401b8  mov     rbx, [rsp+48h+arg_0]
0x1800401bd  add     rsp, 30h
0x1800401c1  pop     r12
0x1800401c3  pop     rdi
0x1800401c4  pop     rsi
0x1800401c5  retn
```

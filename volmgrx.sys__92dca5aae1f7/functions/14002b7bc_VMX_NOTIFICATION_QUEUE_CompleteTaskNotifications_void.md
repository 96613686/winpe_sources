# VMX_NOTIFICATION_QUEUE::CompleteTaskNotifications(void)

- ea: `0x14002b7bc`
- end: `0x14002b95c`
- name: `?CompleteTaskNotifications@VMX_NOTIFICATION_QUEUE@@QEAAXXZ`
- size: `416`
- prototype: `void __fastcall(VMX_NOTIFICATION_QUEUE *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400314e8`

## callees

- `0x1400099d8`
- `0x14001b35c`
- `0x140029204`
- `0x14002b7bc`
- `0x14002d44c`
- `0x14002d864`
- `0x14005afa8`
- `0x14005b080`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14002b922`
- `ntoskrnl!IofCompleteRequest` at `0x14002b922`

## pseudocode

```c
void __fastcall VMX_NOTIFICATION_QUEUE::CompleteTaskNotifications(VMX_NOTIFICATION_QUEUE *this)
{
  struct VMX_USER_ENTRY **v1; // rsi
  char *v3; // rbx
  char *i; // rdx
  int v5; // ecx
  char *v6; // rcx
  char **v7; // rdx
  struct VMX_NOTIFICATION_ENTRY *v8; // r15
  struct VMX_NOTIFICATION_ENTRY *v9; // rax
  char v10; // r14
  struct VMX_USER_ENTRY *v11; // rbx
  struct _IRP *NotificationsIrp; // rax
  VMX_NOTIFICATION_QUEUE *v13; // rcx
  IRP *v14; // rbp
  struct VMX_NOTIFICATION_ENTRY *v15; // rax
  int v16; // eax

  v1 = (struct VMX_USER_ENTRY **)((char *)this + 40);
  if ( *v1 != (struct VMX_USER_ENTRY *)v1 )
  {
    VMX_NOTIFICATION_QUEUE::AddTaskNotification((__int64)this, 4, 0, 0);
    VMX_NOTIFICATION_QUEUE::CompactNotificationBuffer(this);
    v3 = (char *)this + 8;
    for ( i = (char *)*((_QWORD *)this + 1); i != v3; i = *(char **)i )
    {
      v5 = (*(_DWORD *)this)++;
      *((_DWORD *)i + 4) = v5;
      if ( *(_DWORD *)this == -1 )
      {
        VMX_NOTIFICATION_QUEUE::ResetNotificationQueue(this);
        break;
      }
    }
    v6 = (char *)this + 24;
    if ( *(VMX_NOTIFICATION_QUEUE **)(*((_QWORD *)this + 3) + 8LL) != (VMX_NOTIFICATION_QUEUE *)((char *)this + 24)
      || (v7 = (char **)*((_QWORD *)this + 4), *v7 != v6)
      || (v8 = *(struct VMX_NOTIFICATION_ENTRY **)v3, *(char **)(*(_QWORD *)v3 + 8LL) != v3)
      || **((char ***)this + 2) != v3
      || (*v7 = v3,
          *((_QWORD *)this + 4) = *((_QWORD *)this + 2),
          **((_QWORD **)this + 2) = v6,
          *((_QWORD *)this + 2) = v7,
          v9 = *(struct VMX_NOTIFICATION_ENTRY **)v3,
          *(char **)(*(_QWORD *)v3 + 8LL) != v3)
      || *v7 != v3 )
    {
      __fastfail(3u);
    }
    *v7 = (char *)v9;
    v10 = 0;
    *((_QWORD *)v9 + 1) = v7;
    *((_QWORD *)this + 2) = (char *)this + 8;
    *(_QWORD *)v3 = v3;
    v11 = *v1;
    if ( *v1 != (struct VMX_USER_ENTRY *)v1 )
    {
      do
      {
        NotificationsIrp = VmxpDequeueGetNotificationsIrp(v11);
        v14 = NotificationsIrp;
        if ( NotificationsIrp )
        {
          v15 = VMX_NOTIFICATION_QUEUE::SetNotificationIoOutput(v13, NotificationsIrp, v8);
          if ( v15 )
          {
            v10 = 1;
            *((_DWORD *)v11 + 8) = *((_DWORD *)v15 + 4);
            *((_QWORD *)v11 + 6) = MEMORY[0xFFFFF78000000014];
            v16 = 0;
          }
          else
          {
            if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x400) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                14,
                WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids,
                2147483653LL);
            }
            v16 = -2147483643;
          }
          v14->IoStatus.Status = v16;
          IofCompleteRequest(v14, 0);
        }
        v11 = *(struct VMX_USER_ENTRY **)v11;
      }
      while ( v11 != (struct VMX_USER_ENTRY *)v1 );
      if ( v10 )
        VMX_NOTIFICATION_QUEUE::CleanNotificationQueue(this);
    }
  }
}

```

## disassembly

```asm
0x14002b7bc  push    rbx
0x14002b7be  push    rbp
0x14002b7bf  push    rsi
0x14002b7c0  push    rdi
0x14002b7c1  push    r14
0x14002b7c3  push    r15
0x14002b7c5  sub     rsp, 28h
0x14002b7c9  lea     rsi, [rcx+28h]
0x14002b7cd  mov     rdi, rcx
0x14002b7d0  cmp     [rsi], rsi
0x14002b7d3  jz      loc_14002B947
0x14002b7d9  xor     r9d, r9d
0x14002b7dc  xor     r8d, r8d
0x14002b7df  lea     edx, [r9+4]
0x14002b7e3  call    ?AddTaskNotification@VMX_NOTIFICATION_QUEUE@@QEAAXW4_VM_NOTIFICATION_EVENT@@PEAVVMX_RECORD@@PEAU_GUID@@@Z; VMX_NOTIFICATION_QUEUE::AddTaskNotification(_VM_NOTIFICATION_EVENT,VMX_RECORD *,_GUID *)
0x14002b7e8  mov     rcx, rdi; this
0x14002b7eb  call    ?CompactNotificationBuffer@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::CompactNotificationBuffer(void)
0x14002b7f0  lea     rbx, [rdi+8]
0x14002b7f4  mov     rdx, [rbx]
0x14002b7f7  cmp     rdx, rbx
0x14002b7fa  jz      short loc_14002B818
0x14002b7fc  mov     ecx, [rdi]
0x14002b7fe  lea     eax, [rcx+1]
0x14002b801  mov     [rdi], eax
0x14002b803  mov     [rdx+10h], ecx
0x14002b806  cmp     dword ptr [rdi], 0FFFFFFFFh
0x14002b809  jz      short loc_14002B810
0x14002b80b  mov     rdx, [rdx]
0x14002b80e  jmp     short loc_14002B7F7
0x14002b810  mov     rcx, rdi; this
0x14002b813  call    ?ResetNotificationQueue@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::ResetNotificationQueue(void)
0x14002b818  lea     rcx, [rdi+18h]
0x14002b81c  mov     rax, [rcx]
0x14002b81f  cmp     [rax+8], rcx
0x14002b823  jnz     loc_14002B955
0x14002b829  mov     rdx, [rcx+8]
0x14002b82d  cmp     [rdx], rcx
0x14002b830  jnz     loc_14002B955
0x14002b836  mov     r15, [rbx]
0x14002b839  cmp     [r15+8], rbx
0x14002b83d  jnz     loc_14002B955
0x14002b843  mov     rax, [rbx+8]
0x14002b847  cmp     [rax], rbx
0x14002b84a  jnz     loc_14002B955
0x14002b850  mov     [rdx], rbx
0x14002b853  mov     rax, [rbx+8]
0x14002b857  mov     [rcx+8], rax
0x14002b85b  mov     rax, [rbx+8]
0x14002b85f  mov     [rax], rcx
0x14002b862  mov     [rbx+8], rdx
0x14002b866  mov     rax, [rbx]
0x14002b869  cmp     [rax+8], rbx
0x14002b86d  jnz     loc_14002B955
0x14002b873  cmp     [rdx], rbx
0x14002b876  jnz     loc_14002B955
0x14002b87c  mov     [rdx], rax
0x14002b87f  xor     r14b, r14b
0x14002b882  mov     [rax+8], rdx
0x14002b886  mov     [rbx+8], rbx
0x14002b88a  mov     [rbx], rbx
0x14002b88d  mov     rbx, [rsi]
0x14002b890  cmp     rbx, rsi
0x14002b893  jz      loc_14002B947
0x14002b899  mov     rcx, rbx; struct VMX_USER_ENTRY *
0x14002b89c  call    ?VmxpDequeueGetNotificationsIrp@@YAPEAU_IRP@@PEAVVMX_USER_ENTRY@@@Z; VmxpDequeueGetNotificationsIrp(VMX_USER_ENTRY *)
0x14002b8a1  mov     rbp, rax
0x14002b8a4  test    rax, rax
0x14002b8a7  jz      loc_14002B92E
0x14002b8ad  mov     r8, r15; struct VMX_NOTIFICATION_ENTRY *
0x14002b8b0  mov     rdx, rax; struct _IRP *
0x14002b8b3  call    ?SetNotificationIoOutput@VMX_NOTIFICATION_QUEUE@@QEAAPEAVVMX_NOTIFICATION_ENTRY@@PEAU_IRP@@PEAV2@@Z; VMX_NOTIFICATION_QUEUE::SetNotificationIoOutput(_IRP *,VMX_NOTIFICATION_ENTRY *)
0x14002b8b8  test    rax, rax
0x14002b8bb  jnz     short loc_14002B901
0x14002b8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b8c4  lea     rax, WPP_GLOBAL_Control
0x14002b8cb  cmp     rcx, rax
0x14002b8ce  jz      short loc_14002B8FA
0x14002b8d0  test    dword ptr [rcx+2Ch], 400h
0x14002b8d7  jz      short loc_14002B8FA
0x14002b8d9  cmp     byte ptr [rcx+29h], 3
0x14002b8dd  jb      short loc_14002B8FA
0x14002b8df  mov     rcx, [rcx+18h]
0x14002b8e3  lea     r8, WPP_ff83fa8e29b93af5710e31e1bccf8937_Traceguids
0x14002b8ea  mov     edx, 0Eh
0x14002b8ef  mov     r9d, 80000005h
0x14002b8f5  call    WPP_SF_d
0x14002b8fa  mov     eax, 80000005h
0x14002b8ff  jmp     short loc_14002B91A
0x14002b901  mov     eax, [rax+10h]
0x14002b904  mov     r14b, 1
0x14002b907  mov     [rbx+20h], eax
0x14002b90a  mov     rax, ds:0FFFFF78000000014h
0x14002b914  mov     [rbx+30h], rax
0x14002b918  xor     eax, eax
0x14002b91a  xor     edx, edx; PriorityBoost
0x14002b91c  mov     [rbp+30h], eax
0x14002b91f  mov     rcx, rbp; Irp
0x14002b922  call    cs:__imp_IofCompleteRequest
0x14002b929  nop     dword ptr [rax+rax+00h]
0x14002b92e  mov     rbx, [rbx]
0x14002b931  cmp     rbx, rsi
0x14002b934  jnz     loc_14002B899
0x14002b93a  test    r14b, r14b
0x14002b93d  jz      short loc_14002B947
0x14002b93f  mov     rcx, rdi; this
0x14002b942  call    ?CleanNotificationQueue@VMX_NOTIFICATION_QUEUE@@QEAAXXZ; VMX_NOTIFICATION_QUEUE::CleanNotificationQueue(void)
0x14002b947  add     rsp, 28h
0x14002b94b  pop     r15
0x14002b94d  pop     r14
0x14002b94f  pop     rdi
0x14002b950  pop     rsi
0x14002b951  pop     rbp
0x14002b952  pop     rbx
0x14002b953  retn
0x14002b955  mov     ecx, 3
0x14002b95a  int     29h; Win8: RtlFailFast(ecx)
```

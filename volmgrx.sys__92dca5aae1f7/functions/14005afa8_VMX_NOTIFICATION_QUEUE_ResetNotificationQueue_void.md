# VMX_NOTIFICATION_QUEUE::ResetNotificationQueue(void)

- ea: `0x14005afa8`
- end: `0x14005b079`
- name: `?ResetNotificationQueue@VMX_NOTIFICATION_QUEUE@@QEAAXXZ`
- size: `209`
- prototype: `void __fastcall(VMX_NOTIFICATION_QUEUE *this, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002b7bc`
- `0x14002d44c`
- `0x14002fbf4`

## callees

- `0x14001b30c`
- `0x14001b35c`
- `0x14005afa8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14005b041`
- `ntoskrnl!IofCompleteRequest` at `0x14005b041`

## pseudocode

```c
void __fastcall VMX_NOTIFICATION_QUEUE::ResetNotificationQueue(VMX_NOTIFICATION_QUEUE *this, unsigned int a2)
{
  VMX_NOTIFICATION_ENTRY **v3; // rbx
  VMX_NOTIFICATION_ENTRY *v4; // rcx
  VMX_NOTIFICATION_ENTRY *v5; // rax
  VMX_NOTIFICATION_ENTRY **v6; // rbx
  VMX_NOTIFICATION_ENTRY *v7; // rcx
  VMX_NOTIFICATION_ENTRY *v8; // rax
  struct VMX_USER_ENTRY **v9; // rdi
  struct VMX_USER_ENTRY *i; // rbx
  struct _IRP *NotificationsIrp; // rax

  v3 = (VMX_NOTIFICATION_ENTRY **)((char *)this + 8);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == (VMX_NOTIFICATION_ENTRY *)v3 )
      break;
    if ( *((VMX_NOTIFICATION_ENTRY ***)v4 + 1) != v3
      || (v5 = *(VMX_NOTIFICATION_ENTRY **)v4, *(VMX_NOTIFICATION_ENTRY **)(*(_QWORD *)v4 + 8LL) != v4) )
    {
LABEL_13:
      __fastfail(3u);
    }
    *v3 = v5;
    *((_QWORD *)v5 + 1) = v3;
    if ( v4 )
      VMX_NOTIFICATION_ENTRY::`scalar deleting destructor'(v4, a2);
  }
  v6 = (VMX_NOTIFICATION_ENTRY **)((char *)this + 24);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == (VMX_NOTIFICATION_ENTRY *)v6 )
      break;
    if ( *((VMX_NOTIFICATION_ENTRY ***)v7 + 1) != v6 )
      goto LABEL_13;
    v8 = *(VMX_NOTIFICATION_ENTRY **)v7;
    if ( *(VMX_NOTIFICATION_ENTRY **)(*(_QWORD *)v7 + 8LL) != v7 )
      goto LABEL_13;
    *v6 = v8;
    *((_QWORD *)v8 + 1) = v6;
    if ( v7 )
      VMX_NOTIFICATION_ENTRY::`scalar deleting destructor'(v7, a2);
  }
  *(_QWORD *)this = 1;
  v9 = (struct VMX_USER_ENTRY **)((char *)this + 40);
  for ( i = *v9; i != (struct VMX_USER_ENTRY *)v9; i = *(struct VMX_USER_ENTRY **)i )
  {
    NotificationsIrp = VmxpDequeueGetNotificationsIrp(i);
    if ( NotificationsIrp )
    {
      NotificationsIrp->IoStatus.Status = -1073741670;
      IofCompleteRequest(NotificationsIrp, 0);
      *((_BYTE *)i + 56) = 0;
      *((_QWORD *)i + 6) = MEMORY[0xFFFFF78000000014];
    }
    else
    {
      *((_BYTE *)i + 56) = 1;
    }
  }
}

```

## disassembly

```asm
0x14005afa8  mov     [rsp+arg_0], rbx
0x14005afad  push    rdi
0x14005afae  sub     rsp, 20h
0x14005afb2  mov     rdi, rcx
0x14005afb5  lea     rbx, [rcx+8]
0x14005afb9  mov     rcx, [rbx]; this
0x14005afbc  cmp     rcx, rbx
0x14005afbf  jz      short loc_14005AFE3
0x14005afc1  cmp     [rcx+8], rbx
0x14005afc5  jnz     short loc_14005B011
0x14005afc7  mov     rax, [rcx]
0x14005afca  cmp     [rax+8], rcx
0x14005afce  jnz     short loc_14005B011
0x14005afd0  mov     [rbx], rax
0x14005afd3  mov     [rax+8], rbx
0x14005afd7  test    rcx, rcx
0x14005afda  jz      short loc_14005AFB9
0x14005afdc  call    ??_GVMX_NOTIFICATION_ENTRY@@QEAAPEAXI@Z; VMX_NOTIFICATION_ENTRY::`scalar deleting destructor'(uint)
0x14005afe1  jmp     short loc_14005AFB9
0x14005afe3  lea     rbx, [rdi+18h]
0x14005afe7  mov     rcx, [rbx]; this
0x14005afea  cmp     rcx, rbx
0x14005afed  jz      short loc_14005B018
0x14005afef  cmp     [rcx+8], rbx
0x14005aff3  jnz     short loc_14005B011
0x14005aff5  mov     rax, [rcx]
0x14005aff8  cmp     [rax+8], rcx
0x14005affc  jnz     short loc_14005B011
0x14005affe  mov     [rbx], rax
0x14005b001  mov     [rax+8], rbx
0x14005b005  test    rcx, rcx
0x14005b008  jz      short loc_14005AFE7
0x14005b00a  call    ??_GVMX_NOTIFICATION_ENTRY@@QEAAPEAXI@Z; VMX_NOTIFICATION_ENTRY::`scalar deleting destructor'(uint)
0x14005b00f  jmp     short loc_14005AFE7
0x14005b011  mov     ecx, 3
0x14005b016  int     29h; Win8: RtlFailFast(ecx)
0x14005b018  mov     qword ptr [rdi], 1
0x14005b01f  add     rdi, 28h ; '('
0x14005b023  mov     rbx, [rdi]
0x14005b026  jmp     short loc_14005B068
0x14005b028  mov     rcx, rbx; struct VMX_USER_ENTRY *
0x14005b02b  call    ?VmxpDequeueGetNotificationsIrp@@YAPEAU_IRP@@PEAVVMX_USER_ENTRY@@@Z; VmxpDequeueGetNotificationsIrp(VMX_USER_ENTRY *)
0x14005b030  test    rax, rax
0x14005b033  jz      short loc_14005B061
0x14005b035  xor     edx, edx; PriorityBoost
0x14005b037  mov     dword ptr [rax+30h], 0C000009Ah
0x14005b03e  mov     rcx, rax; Irp
0x14005b041  call    cs:__imp_IofCompleteRequest
0x14005b048  nop     dword ptr [rax+rax+00h]
0x14005b04d  mov     byte ptr [rbx+38h], 0
0x14005b051  mov     rax, ds:0FFFFF78000000014h
0x14005b05b  mov     [rbx+30h], rax
0x14005b05f  jmp     short loc_14005B065
0x14005b061  mov     byte ptr [rbx+38h], 1
0x14005b065  mov     rbx, [rbx]
0x14005b068  cmp     rbx, rdi
0x14005b06b  jnz     short loc_14005B028
0x14005b06d  mov     rbx, [rsp+28h+arg_0]
0x14005b072  add     rsp, 20h
0x14005b076  pop     rdi
0x14005b077  retn
```

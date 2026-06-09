# USBVideoWorkItemHandler

- ea: `0x140021340`
- end: `0x14002149c`
- name: `USBVideoWorkItemHandler`
- size: `348`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x14001ab4c`
- `0x14001b15c`
- `0x14001f4f4`
- `0x14001fc3c`
- `0x140021340`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002147f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002147f`
- `ntoskrnl!IoFreeWorkItem` at `0x14002144b`
- `ntoskrnl!IoFreeWorkItem` at `0x14002144b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002145f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002145f`

## pseudocode

```c
void __fastcall USBVideoWorkItemHandler(PDEVICE_OBJECT DeviceObject, _QWORD *Context, __int64 a3)
{
  struct _IO_REMOVE_LOCK *v3; // rdi
  _QWORD *v4; // rbx
  char v5; // al
  int v6; // eax
  PDEVICE_OBJECT v7; // rcx
  __int64 v8; // rdx

  v3 = (struct _IO_REMOVE_LOCK *)Context[1];
  v4 = Context;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v3);
  if ( *((_DWORD *)v4 + 4) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v3);
  }
  else
  {
    v5 = *((_BYTE *)v4 + 22);
    if ( v5 == 2 )
    {
      LOBYTE(a3) = *((_BYTE *)v4 + 21);
      LOBYTE(Context) = *((_BYTE *)v4 + 20);
      v6 = Method2StillImageTriggerHandler(v4[1], (_DWORD)Context, a3, *((_DWORD *)v4 + 6), 0);
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v8 = 109;
LABEL_15:
          WPP_SF_qD(v7->AttachedDevice, v8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v3, v6);
        }
      }
    }
    else if ( v5 == 3 )
    {
      LOBYTE(a3) = *((_BYTE *)v4 + 21);
      LOBYTE(Context) = *((_BYTE *)v4 + 20);
      v6 = Method3StillImageTriggerHandler(v4[1], Context, a3);
      if ( v6 < 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          v8 = 110;
          goto LABEL_15;
        }
      }
    }
  }
  IoFreeWorkItem((PIO_WORKITEM)*v4);
  ExFreePoolWithTag(v4, 0x56425355u);
  IoReleaseRemoveLockEx(v3 + 24, USBVideoWorkItemHandler, 0x20u);
}

```

## disassembly

```asm
0x140021340  mov     [rsp+arg_0], rbx
0x140021345  mov     [rsp+arg_8], rsi
0x14002134a  push    rdi
0x14002134b  sub     rsp, 30h
0x14002134f  mov     rdi, [rdx+8]
0x140021353  mov     rbx, rdx
0x140021356  mov     rcx, cs:WPP_GLOBAL_Control
0x14002135d  lea     rsi, WPP_GLOBAL_Control
0x140021364  cmp     rcx, rsi
0x140021367  jz      short loc_140021387
0x140021369  cmp     byte ptr [rcx+29h], 5
0x14002136d  jb      short loc_140021387
0x14002136f  mov     rcx, [rcx+18h]
0x140021373  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002137a  mov     edx, 6Ch ; 'l'
0x14002137f  mov     r9, rdi
0x140021382  call    WPP_SF_q
0x140021387  cmp     dword ptr [rbx+10h], 0
0x14002138b  jnz     loc_14002141E
0x140021391  mov     al, [rbx+16h]
0x140021394  cmp     al, 2
0x140021396  jnz     short loc_1400213D6
0x140021398  mov     r9d, [rbx+18h]
0x14002139c  mov     r8b, [rbx+15h]
0x1400213a0  mov     dl, [rbx+14h]
0x1400213a3  mov     rcx, [rbx+8]
0x1400213a7  mov     [rsp+38h+var_18], 0
0x1400213b0  call    Method2StillImageTriggerHandler
0x1400213b5  test    eax, eax
0x1400213b7  jns     loc_140021448
0x1400213bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213c4  cmp     rcx, rsi
0x1400213c7  jz      short loc_140021448
0x1400213c9  cmp     byte ptr [rcx+29h], 3
0x1400213cd  jb      short loc_140021448
0x1400213cf  mov     edx, 6Dh ; 'm'
0x1400213d4  jmp     short loc_140021405
0x1400213d6  cmp     al, 3
0x1400213d8  jnz     short loc_140021448
0x1400213da  mov     r8b, [rbx+15h]
0x1400213de  mov     dl, [rbx+14h]
0x1400213e1  mov     rcx, [rbx+8]
0x1400213e5  call    Method3StillImageTriggerHandler
0x1400213ea  test    eax, eax
0x1400213ec  jns     short loc_140021448
0x1400213ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213f5  cmp     rcx, rsi
0x1400213f8  jz      short loc_140021448
0x1400213fa  cmp     byte ptr [rcx+29h], 3
0x1400213fe  jb      short loc_140021448
0x140021400  mov     edx, 6Eh ; 'n'
0x140021405  mov     rcx, [rcx+18h]
0x140021409  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140021410  mov     r9, rdi
0x140021413  mov     dword ptr [rsp+38h+var_18], eax
0x140021417  call    WPP_SF_qD
0x14002141c  jmp     short loc_140021448
0x14002141e  mov     rcx, cs:WPP_GLOBAL_Control
0x140021425  cmp     rcx, rsi
0x140021428  jz      short loc_140021448
0x14002142a  cmp     byte ptr [rcx+29h], 2
0x14002142e  jb      short loc_140021448
0x140021430  mov     rcx, [rcx+18h]
0x140021434  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002143b  mov     edx, 6Fh ; 'o'
0x140021440  mov     r9, rdi
0x140021443  call    WPP_SF_q
0x140021448  mov     rcx, [rbx]; IoWorkItem
0x14002144b  call    cs:__imp_IoFreeWorkItem
0x140021452  nop     dword ptr [rax+rax+00h]
0x140021457  mov     edx, 56425355h; Tag
0x14002145c  mov     rcx, rbx; P
0x14002145f  call    cs:__imp_ExFreePoolWithTag
0x140021466  nop     dword ptr [rax+rax+00h]
0x14002146b  lea     rcx, [rdi+300h]; RemoveLock
0x140021472  mov     r8d, 20h ; ' '; RemlockSize
0x140021478  lea     rdx, USBVideoWorkItemHandler; Tag
0x14002147f  call    cs:__imp_IoReleaseRemoveLockEx
0x140021486  nop     dword ptr [rax+rax+00h]
0x14002148b  mov     rbx, [rsp+38h+arg_0]
0x140021490  mov     rsi, [rsp+38h+arg_8]
0x140021495  add     rsp, 30h
0x140021499  pop     rdi
0x14002149a  retn
```

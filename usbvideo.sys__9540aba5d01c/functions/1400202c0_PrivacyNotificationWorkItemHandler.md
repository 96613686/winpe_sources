# PrivacyNotificationWorkItemHandler

- ea: `0x1400202c0`
- end: `0x1400204c5`
- name: `PrivacyNotificationWorkItemHandler`
- size: `517`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x140004bac`
- `0x14001b15c`
- `0x14001d0cc`
- `0x1400202c0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020406`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020486`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020406`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140020486`
- `ntoskrnl!IoFreeWorkItem` at `0x1400203d2`
- `ntoskrnl!IoFreeWorkItem` at `0x14002044d`
- `ntoskrnl!IoFreeWorkItem` at `0x1400203d2`
- `ntoskrnl!IoFreeWorkItem` at `0x14002044d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020461`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400203e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020461`
- `ks!KsGetNextSibling` at `0x140020395`
- `ks!KsGetNextSibling` at `0x1400203ac`
- `ks!KsGetNextSibling` at `0x140020395`
- `ks!KsGetNextSibling` at `0x1400203ac`
- `ks!KsGenerateEvents` at `0x140020386`
- `ks!KsGenerateEvents` at `0x140020386`
- `ks!KsGetFirstChild` at `0x14002033b`
- `ks!KsGetFirstChild` at `0x14002034c`
- `ks!KsGetFirstChild` at `0x14002033b`
- `ks!KsGetFirstChild` at `0x14002034c`
- `ks!KsReleaseDevice` at `0x1400203c3`
- `ks!KsReleaseDevice` at `0x1400203c3`
- `ks!KsAcquireDevice` at `0x1400202fb`
- `ks!KsAcquireDevice` at `0x1400202fb`

## pseudocode

```c
void __fastcall PrivacyNotificationWorkItemHandler(PDEVICE_OBJECT DeviceObject, PIO_WORKITEM *Context)
{
  PIO_WORKITEM v3; // rsi
  struct _KSDEVICE *v4; // rbp
  PVOID i; // rax
  PVOID j; // rax
  void *v7; // r14
  void *v8; // rdi
  struct _IO_REMOVE_LOCK *v9; // rsi

  if ( Context )
  {
    v3 = Context[1];
    if ( v3 )
    {
      v4 = (struct _KSDEVICE *)*((_QWORD *)v3 + 3);
      if ( v4 )
      {
        KsAcquireDevice(*((PKSDEVICE *)v3 + 3));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v3);
        for ( i = KsGetFirstChild(v4); ; i = KsGetNextSibling(v8) )
        {
          v8 = i;
          if ( !i )
            break;
          for ( j = KsGetFirstChild(i); ; j = KsGetNextSibling(v7) )
          {
            v7 = j;
            if ( !j )
              break;
            KsGenerateEvents(j, &PROPSETID_VIDCAP_CAMERACONTROL, 8u, 0, 0, 0, 0);
          }
        }
        KsReleaseDevice(v4);
        IoFreeWorkItem(*Context);
        ExFreePoolWithTag(Context, 0x56425355u);
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)v3 + 24, PrivacyNotificationWorkItemHandler, 0x20u);
        return;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids, v3, Context);
    v9 = (struct _IO_REMOVE_LOCK *)Context[1];
    IoFreeWorkItem(*Context);
    ExFreePoolWithTag(Context, 0x56425355u);
    if ( v9 )
      IoReleaseRemoveLockEx(v9 + 24, PrivacyNotificationWorkItemHandler, 0x20u);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids);
}

```

## disassembly

```asm
0x1400202c0  push    rbx
0x1400202c2  push    rbp
0x1400202c3  push    rsi
0x1400202c4  push    rdi
0x1400202c5  push    r14
0x1400202c7  sub     rsp, 40h
0x1400202cb  lea     rdi, WPP_GLOBAL_Control
0x1400202d2  mov     rbx, rdx
0x1400202d5  test    rdx, rdx
0x1400202d8  jz      loc_140020492
0x1400202de  mov     rsi, [rdx+8]
0x1400202e2  test    rsi, rsi
0x1400202e5  jz      loc_140020417
0x1400202eb  mov     rbp, [rsi+18h]
0x1400202ef  test    rbp, rbp
0x1400202f2  jz      loc_140020417
0x1400202f8  mov     rcx, rbp; Device
0x1400202fb  call    cs:__imp_KsAcquireDevice
0x140020302  nop     dword ptr [rax+rax+00h]
0x140020307  mov     rcx, cs:WPP_GLOBAL_Control
0x14002030e  lea     rdi, WPP_GLOBAL_Control
0x140020315  cmp     rcx, rdi
0x140020318  jz      short loc_140020338
0x14002031a  cmp     byte ptr [rcx+29h], 4
0x14002031e  jb      short loc_140020338
0x140020320  mov     rcx, [rcx+18h]
0x140020324  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x14002032b  mov     edx, 50h ; 'P'
0x140020330  mov     r9, rsi
0x140020333  call    WPP_SF_q
0x140020338  mov     rcx, rbp; Object
0x14002033b  call    cs:__imp_KsGetFirstChild
0x140020342  nop     dword ptr [rax+rax+00h]
0x140020347  jmp     short loc_1400203B8
0x140020349  mov     rcx, rdi; Object
0x14002034c  call    cs:__imp_KsGetFirstChild
0x140020353  nop     dword ptr [rax+rax+00h]
0x140020358  jmp     short loc_1400203A1
0x14002035a  xor     r9d, r9d; DataSize
0x14002035d  mov     [rsp+68h+CallBackContext], 0; CallBackContext
0x140020366  mov     [rsp+68h+CallBack], 0; CallBack
0x14002036f  lea     rdx, PROPSETID_VIDCAP_CAMERACONTROL; EventSet
0x140020376  mov     rcx, r14; Object
0x140020379  mov     [rsp+68h+Data], 0; Data
0x140020382  lea     r8d, [r9+8]; EventId
0x140020386  call    cs:__imp_KsGenerateEvents
0x14002038d  nop     dword ptr [rax+rax+00h]
0x140020392  mov     rcx, r14; Object
0x140020395  call    cs:__imp_KsGetNextSibling
0x14002039c  nop     dword ptr [rax+rax+00h]
0x1400203a1  mov     r14, rax
0x1400203a4  test    rax, rax
0x1400203a7  jnz     short loc_14002035A
0x1400203a9  mov     rcx, rdi; Object
0x1400203ac  call    cs:__imp_KsGetNextSibling
0x1400203b3  nop     dword ptr [rax+rax+00h]
0x1400203b8  mov     rdi, rax
0x1400203bb  test    rax, rax
0x1400203be  jnz     short loc_140020349
0x1400203c0  mov     rcx, rbp; Device
0x1400203c3  call    cs:__imp_KsReleaseDevice
0x1400203ca  nop     dword ptr [rax+rax+00h]
0x1400203cf  mov     rcx, [rbx]; IoWorkItem
0x1400203d2  call    cs:__imp_IoFreeWorkItem
0x1400203d9  nop     dword ptr [rax+rax+00h]
0x1400203de  mov     edx, 56425355h; Tag
0x1400203e3  mov     rcx, rbx; P
0x1400203e6  call    cs:__imp_ExFreePoolWithTag
0x1400203ed  nop     dword ptr [rax+rax+00h]
0x1400203f2  lea     rcx, [rsi+300h]; RemoveLock
0x1400203f9  mov     r8d, 20h ; ' '; RemlockSize
0x1400203ff  lea     rdx, PrivacyNotificationWorkItemHandler; Tag
0x140020406  call    cs:__imp_IoReleaseRemoveLockEx
0x14002040d  nop     dword ptr [rax+rax+00h]
0x140020412  jmp     loc_1400204B9
0x140020417  mov     rcx, cs:WPP_GLOBAL_Control
0x14002041e  cmp     rcx, rdi
0x140020421  jz      short loc_140020446
0x140020423  cmp     byte ptr [rcx+29h], 2
0x140020427  jb      short loc_140020446
0x140020429  mov     rcx, [rcx+18h]
0x14002042d  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x140020434  mov     edx, 51h ; 'Q'
0x140020439  mov     [rsp+68h+Data], rbx
0x14002043e  mov     r9, rsi
0x140020441  call    WPP_SF_qq
0x140020446  mov     rcx, [rbx]; IoWorkItem
0x140020449  mov     rsi, [rbx+8]
0x14002044d  call    cs:__imp_IoFreeWorkItem
0x140020454  nop     dword ptr [rax+rax+00h]
0x140020459  mov     edx, 56425355h; Tag
0x14002045e  mov     rcx, rbx; P
0x140020461  call    cs:__imp_ExFreePoolWithTag
0x140020468  nop     dword ptr [rax+rax+00h]
0x14002046d  test    rsi, rsi
0x140020470  jz      short loc_140020492
0x140020472  lea     rcx, [rsi+300h]; RemoveLock
0x140020479  mov     r8d, 20h ; ' '; RemlockSize
0x14002047f  lea     rdx, PrivacyNotificationWorkItemHandler; Tag
0x140020486  call    cs:__imp_IoReleaseRemoveLockEx
0x14002048d  nop     dword ptr [rax+rax+00h]
0x140020492  mov     rcx, cs:WPP_GLOBAL_Control
0x140020499  cmp     rcx, rdi
0x14002049c  jz      short loc_1400204B9
0x14002049e  cmp     byte ptr [rcx+29h], 2
0x1400204a2  jb      short loc_1400204B9
0x1400204a4  mov     rcx, [rcx+18h]
0x1400204a8  lea     r8, WPP_b11e537a527d30190cd6733beb5dc248_Traceguids
0x1400204af  mov     edx, 52h ; 'R'
0x1400204b4  call    WPP_SF_
0x1400204b9  add     rsp, 40h
0x1400204bd  pop     r14
0x1400204bf  pop     rdi
0x1400204c0  pop     rsi
0x1400204c1  pop     rbp
0x1400204c2  pop     rbx
0x1400204c3  retn
```

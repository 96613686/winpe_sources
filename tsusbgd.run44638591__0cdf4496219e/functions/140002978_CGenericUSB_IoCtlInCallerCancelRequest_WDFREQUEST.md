# CGenericUSB::IoCtlInCallerCancelRequest(WDFREQUEST__ *)

- ea: `0x140002978`
- end: `0x140002c58`
- name: `?IoCtlInCallerCancelRequest@CGenericUSB@@AEAAXPEAUWDFREQUEST__@@@Z`
- size: `736`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140003e20`

## callees

- `0x140001ac0`
- `0x140002978`
- `0x140003934`
- `0x140006370`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140002a83`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140002a83`
- `ntoskrnl!IoFileObjectType` at `0x140002a53`
- `ntoskrnl!ObfDereferenceObject` at `0x140002c14`
- `ntoskrnl!ObfDereferenceObject` at `0x140002c14`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlInCallerCancelRequest(CGenericUSB *this, struct WDFREQUEST__ *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  PDEVICE_OBJECT v6; // rcx
  unsigned __int16 v7; // dx
  __int64 *v8; // rdi
  __int64 v9; // r14
  __int64 **i; // rbx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  PVOID Object; // [rsp+80h] [rbp+18h] BYREF
  __int64 v13; // [rsp+88h] [rbp+20h] BYREF

  v11[0] = 0;
  v13 = 0;
  Object = 0;
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[101].Flink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    off_140009018);
  Object = 0;
  v4 = ((__int64 (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, __int64, __int64 *, _QWORD *))WPP_MAIN_CB.Queue.ListEntry.Flink[134].Blink)(
         WPP_MAIN_CB.Queue.ListEntry.Blink,
         a2,
         16,
         &v13,
         v11);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = ObReferenceObjectByHandle(*(HANDLE *)v13, 0, (POBJECT_TYPE)IoFileObjectType, 1, &Object, 0);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v8 = 0;
      v9 = *(_QWORD *)(v13 + 8);
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Flink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *((_QWORD *)this + 10));
      for ( i = (__int64 **)*((_QWORD *)this + 8); i != (__int64 **)((char *)this + 64); i = (__int64 **)*i )
      {
        if ( i[3] == Object
          && *(_QWORD *)(((__int64 (__fastcall *)(struct _LIST_ENTRY *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[142].Blink)(
                           WPP_MAIN_CB.Queue.ListEntry.Blink,
                           i[2])
                       + 72) == v9 )
        {
          v8 = i[2];
          ((void (__fastcall *)(struct _LIST_ENTRY *, __int64 *, _QWORD, __int64, const char *))WPP_MAIN_CB.Queue.ListEntry.Flink[102].Blink)(
            WPP_MAIN_CB.Queue.ListEntry.Blink,
            v8,
            0,
            473,
            "termsrv\\devices\\urbdr\\genericusbdriver\\ioctl.cpp");
          break;
        }
      }
      ((void (__fastcall *)(struct _LIST_ENTRY *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[158].Blink)(
        WPP_MAIN_CB.Queue.ListEntry.Blink,
        *((_QWORD *)this + 10));
      if ( v8 )
      {
        ((void (__fastcall *)(struct _LIST_ENTRY *, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[129].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v8);
        ((void (__fastcall *)(struct _LIST_ENTRY *, __int64 *, _QWORD, __int64, const char *))WPP_MAIN_CB.Queue.ListEntry.Flink[103].Flink)(
          WPP_MAIN_CB.Queue.ListEntry.Blink,
          v8,
          0,
          503,
          "termsrv\\devices\\urbdr\\genericusbdriver\\ioctl.cpp");
        v5 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids);
        v5 = -1073741275;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v7 = 18;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v7 = 17;
LABEL_5:
      WPP_SF_d((__int64)v6->AttachedDevice, v7, (__int64)WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids, v4);
    }
  }
  if ( Object )
    ObfDereferenceObject(Object);
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD))WPP_MAIN_CB.Queue.ListEntry.Flink[131].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    v5);
}

```

## disassembly

```asm
0x140002978  mov     rax, rsp
0x14000297b  mov     [rax+8], rbx
0x14000297f  mov     [rax+10h], rbp
0x140002983  push    rsi
0x140002984  push    rdi
0x140002985  push    r13
0x140002987  push    r14
0x140002989  push    r15
0x14000298b  sub     rsp, 40h
0x14000298f  mov     r8, cs:off_140009018
0x140002996  mov     rbp, rcx
0x140002999  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x1400029a0  mov     r15, rdx
0x1400029a3  mov     qword ptr [rax-38h], 0
0x1400029ab  mov     qword ptr [rax+20h], 0
0x1400029b3  mov     qword ptr [rax+18h], 0
0x1400029bb  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400029c2  mov     rax, [rax+650h]
0x1400029c9  call    _guard_dispatch_icall
0x1400029ce  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x1400029d5  lea     rcx, [rsp+68h+var_38]
0x1400029da  mov     [rsp+68h+arg_10], 0
0x1400029e6  lea     r9, [rsp+68h+arg_18]
0x1400029ee  mov     [rsp+68h+Object], rcx
0x1400029f3  mov     r8d, 10h
0x1400029f9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002a00  mov     rdx, r15
0x140002a03  mov     rax, [rax+868h]
0x140002a0a  call    _guard_dispatch_icall
0x140002a0f  mov     ebx, eax
0x140002a11  test    eax, eax
0x140002a13  jns     short loc_140002A53
0x140002a15  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a1c  lea     rdx, WPP_GLOBAL_Control
0x140002a23  cmp     rcx, rdx
0x140002a26  jz      loc_140002C07
0x140002a2c  cmp     byte ptr [rcx+29h], 2
0x140002a30  jb      loc_140002C07
0x140002a36  mov     edx, 11h
0x140002a3b  mov     rcx, [rcx+18h]
0x140002a3f  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002a46  mov     r9d, eax
0x140002a49  call    WPP_SF_d
0x140002a4e  jmp     loc_140002C07
0x140002a53  mov     r8, cs:__imp_IoFileObjectType
0x140002a5a  lea     rax, [rsp+68h+arg_10]
0x140002a62  mov     rcx, [rsp+68h+arg_18]
0x140002a6a  mov     r9b, 1; AccessMode
0x140002a6d  mov     [rsp+68h+HandleInformation], 0; HandleInformation
0x140002a76  xor     edx, edx; DesiredAccess
0x140002a78  mov     [rsp+68h+Object], rax; Object
0x140002a7d  mov     r8, [r8]; ObjectType
0x140002a80  mov     rcx, [rcx]; Handle
0x140002a83  call    cs:__imp_ObReferenceObjectByHandle
0x140002a8a  nop     dword ptr [rax+rax+00h]
0x140002a8f  mov     ebx, eax
0x140002a91  test    eax, eax
0x140002a93  jns     short loc_140002AC0
0x140002a95  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a9c  lea     rdx, WPP_GLOBAL_Control
0x140002aa3  cmp     rcx, rdx
0x140002aa6  jz      loc_140002C07
0x140002aac  cmp     byte ptr [rcx+29h], 2
0x140002ab0  jb      loc_140002C07
0x140002ab6  mov     edx, 12h
0x140002abb  jmp     loc_140002A3B
0x140002ac0  mov     rax, [rsp+68h+arg_18]
0x140002ac8  xor     edi, edi
0x140002aca  mov     rdx, [rbp+50h]
0x140002ace  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002ad5  mov     r14, [rax+8]
0x140002ad9  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002ae0  mov     rax, [rax+9E0h]
0x140002ae7  call    _guard_dispatch_icall
0x140002aec  lea     rsi, [rbp+40h]
0x140002af0  mov     rbx, [rsi]
0x140002af3  lea     r13, aTermsrvDevices; "termsrv\\devices\\urbdr\\genericusbdriv"...
0x140002afa  jmp     short loc_140002B31
0x140002afc  mov     rax, [rsp+68h+arg_10]
0x140002b04  cmp     [rbx+18h], rax
0x140002b08  jnz     short loc_140002B2E
0x140002b0a  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002b11  mov     rdx, [rbx+10h]
0x140002b15  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002b1c  mov     rax, [rax+8E8h]
0x140002b23  call    _guard_dispatch_icall
0x140002b28  cmp     [rax+48h], r14
0x140002b2c  jz      short loc_140002B38
0x140002b2e  mov     rbx, [rbx]
0x140002b31  cmp     rbx, rsi
0x140002b34  jnz     short loc_140002AFC
0x140002b36  jmp     short loc_140002B67
0x140002b38  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002b3f  mov     r9d, 1D9h
0x140002b45  mov     rdi, [rbx+10h]
0x140002b49  xor     r8d, r8d
0x140002b4c  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002b53  mov     rdx, rdi
0x140002b56  mov     [rsp+68h+Object], r13
0x140002b5b  mov     rax, [rax+668h]
0x140002b62  call    _guard_dispatch_icall
0x140002b67  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002b6e  mov     rdx, [rbp+50h]
0x140002b72  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002b79  mov     rax, [rax+9E8h]
0x140002b80  call    _guard_dispatch_icall
0x140002b85  test    rdi, rdi
0x140002b88  jnz     short loc_140002BBD
0x140002b8a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b91  lea     rdx, WPP_GLOBAL_Control
0x140002b98  cmp     rcx, rdx
0x140002b9b  jz      short loc_140002BB6
0x140002b9d  cmp     byte ptr [rcx+29h], 5
0x140002ba1  jb      short loc_140002BB6
0x140002ba3  mov     rcx, [rcx+18h]
0x140002ba7  lea     edx, [rdi+13h]
0x140002baa  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140002bb1  call    WPP_SF_
0x140002bb6  mov     ebx, 0C0000225h
0x140002bbb  jmp     short loc_140002C07
0x140002bbd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002bc4  mov     rdx, rdi
0x140002bc7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002bce  mov     rax, [rax+810h]
0x140002bd5  call    _guard_dispatch_icall
0x140002bda  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002be1  mov     r9d, 1F7h
0x140002be7  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002bee  xor     r8d, r8d
0x140002bf1  mov     rdx, rdi
0x140002bf4  mov     [rsp+68h+Object], r13
0x140002bf9  mov     rax, [rax+670h]
0x140002c00  call    _guard_dispatch_icall
0x140002c05  xor     ebx, ebx
0x140002c07  mov     rcx, [rsp+68h+arg_10]; Object
0x140002c0f  test    rcx, rcx
0x140002c12  jz      short loc_140002C20
0x140002c14  call    cs:__imp_ObfDereferenceObject
0x140002c1b  nop     dword ptr [rax+rax+00h]
0x140002c20  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140002c27  mov     r8d, ebx
0x140002c2a  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140002c31  mov     rdx, r15
0x140002c34  mov     rax, [rax+838h]
0x140002c3b  call    _guard_dispatch_icall
0x140002c40  mov     rbx, [rsp+68h+arg_0]
0x140002c45  mov     rbp, [rsp+68h+arg_8]
0x140002c4a  add     rsp, 40h
0x140002c4e  pop     r15
0x140002c50  pop     r14
0x140002c52  pop     r13
0x140002c54  pop     rdi
0x140002c55  pop     rsi
0x140002c56  retn
```

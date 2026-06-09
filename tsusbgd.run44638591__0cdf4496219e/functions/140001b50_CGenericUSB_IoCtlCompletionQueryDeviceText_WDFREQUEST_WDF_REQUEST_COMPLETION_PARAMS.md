# CGenericUSB::IoCtlCompletionQueryDeviceText(WDFREQUEST__ *,_WDF_REQUEST_COMPLETION_PARAMS *)

- ea: `0x140001b50`
- end: `0x140001d07`
- name: `?IoCtlCompletionQueryDeviceText@CGenericUSB@@QEAAXPEAUWDFREQUEST__@@PEAU_WDF_REQUEST_COMPLETION_PARAMS@@@Z`
- size: `439`
- prototype: `void __fastcall(CGenericUSB *__hidden this, struct WDFREQUEST__ *, struct _WDF_REQUEST_COMPLETION_PARAMS *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140003bd0`

## callees

- `0x140001ac0`
- `0x140001b50`
- `0x140003a10`
- `0x1400040c4`
- `0x140006370`
- `0x140006a80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140001cca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140001cca`

## pseudocode

```c
void __fastcall CGenericUSB::IoCtlCompletionQueryDeviceText(
        CGenericUSB *this,
        struct WDFREQUEST__ *a2,
        struct _WDF_REQUEST_COMPLETION_PARAMS *a3)
{
  NTSTATUS Status; // ebx
  size_t v4; // rsi
  void *Information; // rdi
  size_t v7; // rbx
  __int64 v8; // r8
  CGenericUSB *v9; // [rsp+50h] [rbp+8h] BYREF
  size_t pcchLength; // [rsp+60h] [rbp+18h] BYREF
  __int64 v11; // [rsp+68h] [rbp+20h] BYREF

  v9 = this;
  Status = a3->IoStatus.Status;
  v4 = 0;
  v11 = 0;
  v9 = 0;
  if ( Status >= 0 )
  {
    Information = (void *)a3->IoStatus.Information;
    pcchLength = 0;
    if ( Information && RtlStringLengthWorkerW((STRSAFE_PCNZWCH)Information, (size_t)a2, &pcchLength) >= 0 )
    {
      v7 = 2 * pcchLength + 2;
      v4 = 2 * pcchLength + 4;
      if ( ((int (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, size_t, CGenericUSB **, __int64 *))WPP_MAIN_CB.Queue.ListEntry.Flink[135].Flink)(
             WPP_MAIN_CB.Queue.ListEntry.Blink,
             a2,
             v4,
             &v9,
             &v11) >= 0 )
      {
        if ( v7 <= 0xFFFF )
        {
          *(_WORD *)v9 = v7 >> 1;
          memmove((char *)v9 + 2, Information, v7);
          Status = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 28, v8, v7);
          Status = -1073741595;
          v4 = 0;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 27, v8, v11);
        Status = -1073741789;
      }
    }
    else
    {
      Status = -1073741808;
      if ( !Information )
        goto LABEL_20;
    }
    ExFreePoolWithTag(Information, 0);
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids,
      (unsigned int)Status);
LABEL_20:
  ((void (__fastcall *)(struct _LIST_ENTRY *, struct WDFREQUEST__ *, _QWORD, size_t))WPP_MAIN_CB.Queue.ListEntry.Flink[132].Blink)(
    WPP_MAIN_CB.Queue.ListEntry.Blink,
    a2,
    (unsigned int)Status,
    v4);
}

```

## disassembly

```asm
0x140001b50  mov     rax, rsp
0x140001b53  mov     [rax+10h], rbx
0x140001b57  mov     [rax+8], rcx
0x140001b5b  push    rbp
0x140001b5c  push    rsi
0x140001b5d  push    rdi
0x140001b5e  sub     rsp, 30h
0x140001b62  mov     ebx, [r8+8]
0x140001b66  xor     esi, esi
0x140001b68  mov     qword ptr [rax+20h], 0
0x140001b70  mov     rbp, rdx
0x140001b73  mov     qword ptr [rax+8], 0
0x140001b7b  test    ebx, ebx
0x140001b7d  jns     short loc_140001BBB
0x140001b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b86  lea     rax, WPP_GLOBAL_Control
0x140001b8d  cmp     rcx, rax
0x140001b90  jz      loc_140001CD6
0x140001b96  cmp     byte ptr [rcx+29h], 2
0x140001b9a  jb      loc_140001CD6
0x140001ba0  mov     rcx, [rcx+18h]
0x140001ba4  lea     edx, [rsi+1Ah]
0x140001ba7  mov     r9d, ebx
0x140001baa  lea     r8, WPP_ca57f73ceebe3acc2e782e1f2e089c12_Traceguids
0x140001bb1  call    WPP_SF_d
0x140001bb6  jmp     loc_140001CD6
0x140001bbb  mov     rdi, [r8+10h]
0x140001bbf  mov     [rsp+48h+pcchLength], rsi
0x140001bc4  test    rdi, rdi
0x140001bc7  jz      loc_140001CBB
0x140001bcd  lea     r8, [rsp+48h+pcchLength]; pcchLength
0x140001bd2  mov     rcx, rdi; psz
0x140001bd5  call    RtlStringLengthWorkerW
0x140001bda  test    eax, eax
0x140001bdc  js      loc_140001CBB
0x140001be2  mov     rax, [rsp+48h+pcchLength]
0x140001be7  lea     rcx, [rsp+48h+arg_18]
0x140001bec  mov     [rsp+48h+var_28], rcx
0x140001bf1  lea     r9, [rsp+48h+arg_0]
0x140001bf6  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001bfd  mov     rdx, rbp
0x140001c00  lea     rbx, ds:2[rax*2]
0x140001c08  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001c0f  lea     rsi, [rbx+2]
0x140001c13  mov     r8, rsi
0x140001c16  mov     rax, [rax+870h]
0x140001c1d  call    _guard_dispatch_icall
0x140001c22  test    eax, eax
0x140001c24  jns     short loc_140001C59
0x140001c26  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c2d  lea     rax, WPP_GLOBAL_Control
0x140001c34  cmp     rcx, rax
0x140001c37  jz      short loc_140001C52
0x140001c39  cmp     byte ptr [rcx+29h], 2
0x140001c3d  jb      short loc_140001C52
0x140001c3f  mov     r9, [rsp+48h+arg_18]
0x140001c44  mov     edx, 1Bh
0x140001c49  mov     rcx, [rcx+18h]
0x140001c4d  call    WPP_SF_i
0x140001c52  mov     ebx, 0C0000023h
0x140001c57  jmp     short loc_140001CC5
0x140001c59  cmp     rbx, 0FFFFh
0x140001c60  jbe     short loc_140001C95
0x140001c62  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c69  lea     rax, WPP_GLOBAL_Control
0x140001c70  cmp     rcx, rax
0x140001c73  jz      short loc_140001C8C
0x140001c75  cmp     byte ptr [rcx+29h], 2
0x140001c79  jb      short loc_140001C8C
0x140001c7b  mov     rcx, [rcx+18h]
0x140001c7f  mov     edx, 1Ch
0x140001c84  mov     r9, rbx
0x140001c87  call    WPP_SF_i
0x140001c8c  mov     ebx, 0C00000E5h
0x140001c91  xor     esi, esi
0x140001c93  jmp     short loc_140001CC5
0x140001c95  mov     rax, [rsp+48h+arg_0]
0x140001c9a  mov     rcx, rbx
0x140001c9d  shr     rcx, 1
0x140001ca0  mov     r8, rbx; Size
0x140001ca3  mov     rdx, rdi; Src
0x140001ca6  mov     [rax], cx
0x140001ca9  mov     rcx, [rsp+48h+arg_0]
0x140001cae  add     rcx, 2; void *
0x140001cb2  call    memmove
0x140001cb7  xor     ebx, ebx
0x140001cb9  jmp     short loc_140001CC5
0x140001cbb  mov     ebx, 0C0000010h
0x140001cc0  test    rdi, rdi
0x140001cc3  jz      short loc_140001CD6
0x140001cc5  xor     edx, edx; Tag
0x140001cc7  mov     rcx, rdi; P
0x140001cca  call    cs:__imp_ExFreePoolWithTag
0x140001cd1  nop     dword ptr [rax+rax+00h]
0x140001cd6  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue
0x140001cdd  mov     r9, rsi
0x140001ce0  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+8
0x140001ce7  mov     r8d, ebx
0x140001cea  mov     rdx, rbp
0x140001ced  mov     rax, [rax+848h]
0x140001cf4  call    _guard_dispatch_icall
0x140001cf9  mov     rbx, [rsp+48h+arg_8]
0x140001cfe  add     rsp, 30h
0x140001d02  pop     rdi
0x140001d03  pop     rsi
0x140001d04  pop     rbp
0x140001d05  retn
```

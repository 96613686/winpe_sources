# TiClose

- ea: `0x14000ae50`
- end: `0x14000af14`
- name: `TiClose`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000173c`
- `0x140001c34`
- `0x14000ae50`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14000aed8`
- `ntoskrnl!IofCompleteRequest` at `0x14000aed8`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aeb6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000aeb6`

## pseudocode

```c
__int64 __fastcall TiClose(__int64 a1, IRP *a2, int a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  int v7; // edx
  int v8; // r8d

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      20,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  if ( *(_DWORD *)(a1 + 72) != 56 )
    return PtClose(a1, a2, a3);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  ObfDereferenceObject(*(PVOID *)CurrentStackLocation->FileObject->FsContext2);
  CurrentStackLocation->FileObject->FsContext2 = 0;
  a2->IoStatus.Status = 0;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      v8,
      21,
      (__int64)WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x14000ae50  push    rbx
0x14000ae52  push    rbp
0x14000ae53  push    rsi
0x14000ae54  push    rdi
0x14000ae55  sub     rsp, 38h
0x14000ae59  mov     rdi, rdx
0x14000ae5c  mov     rbx, rcx
0x14000ae5f  lea     rbp, WPP_RECORDER_INITIALIZED
0x14000ae66  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000ae6d  lea     rsi, WPP_9f0bd9f93e9b3ad27925ce7a704f5ec0_Traceguids
0x14000ae74  jz      short loc_14000AE91
0x14000ae76  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae7d  mov     r9d, 14h
0x14000ae83  mov     [rsp+58h+var_38], rsi
0x14000ae88  mov     rcx, [rcx+40h]
0x14000ae8c  call    WPP_RECORDER_SF_s
0x14000ae91  cmp     dword ptr [rbx+48h], 38h ; '8'
0x14000ae95  jz      short loc_14000AEA4
0x14000ae97  mov     rdx, rdi
0x14000ae9a  mov     rcx, rbx
0x14000ae9d  call    PtClose
0x14000aea2  jmp     short loc_14000AF0A
0x14000aea4  mov     rbx, [rdi+0B8h]
0x14000aeab  mov     rax, [rbx+30h]
0x14000aeaf  mov     rcx, [rax+20h]
0x14000aeb3  mov     rcx, [rcx]; Object
0x14000aeb6  call    cs:__imp_ObfDereferenceObject
0x14000aebd  nop     dword ptr [rax+rax+00h]
0x14000aec2  mov     rax, [rbx+30h]
0x14000aec6  xor     ecx, ecx
0x14000aec8  xor     edx, edx; PriorityBoost
0x14000aeca  mov     [rax+20h], rcx
0x14000aece  mov     [rdi+30h], ecx
0x14000aed1  mov     [rdi+38h], rcx
0x14000aed5  mov     rcx, rdi; Irp
0x14000aed8  call    cs:__imp_IofCompleteRequest
0x14000aedf  nop     dword ptr [rax+rax+00h]
0x14000aee4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14000aeeb  jz      short loc_14000AF08
0x14000aeed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aef4  mov     r9d, 15h
0x14000aefa  mov     [rsp+58h+var_38], rsi
0x14000aeff  mov     rcx, [rcx+40h]
0x14000af03  call    WPP_RECORDER_SF_s
0x14000af08  xor     eax, eax
0x14000af0a  add     rsp, 38h
0x14000af0e  pop     rdi
0x14000af0f  pop     rsi
0x14000af10  pop     rbp
0x14000af11  pop     rbx
0x14000af12  retn
```

# HUBPDO_EvtDeviceWdmIrpQueryDeviceTextPreprocess

- ea: `0x1400178bc`
- end: `0x140017bd9`
- name: `HUBPDO_EvtDeviceWdmIrpQueryDeviceTextPreprocess`
- size: `797`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140016160`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x1400178bc`
- `0x140019178`
- `0x14001cc5c`
- `0x1400336a8`
- `0x140045570`
- `0x140045640`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140017a9b`
- `ntoskrnl!KeClearEvent` at `0x140017af7`
- `ntoskrnl!KeClearEvent` at `0x140017a9b`
- `ntoskrnl!KeClearEvent` at `0x140017af7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400179f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017a7e`
- `ntoskrnl!IofCompleteRequest` at `0x140017bb3`
- `ntoskrnl!IofCompleteRequest` at `0x140017bb3`
- `ntoskrnl!ExAllocatePool2` at `0x140017928`
- `ntoskrnl!ExAllocatePool2` at `0x140017b57`
- `ntoskrnl!ExAllocatePool2` at `0x140017928`
- `ntoskrnl!ExAllocatePool2` at `0x140017b57`

## pseudocode

```c
__int64 __fastcall HUBPDO_EvtDeviceWdmIrpQueryDeviceTextPreprocess(__int64 a1, IRP *a2)
{
  __int64 v3; // rax
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  __int64 v5; // rsi
  unsigned int Length; // eax
  int v7; // edx
  wchar_t *Pool2; // rbx
  int v9; // r9d
  NTSTATUS v10; // ebp
  int v11; // edx
  unsigned __int16 Size; // r14
  void *v13; // rcx
  struct _KEVENT *v14; // r13
  unsigned __int8 *v15; // rax
  __int64 v16; // rbp
  wchar_t *v17; // rax

  v3 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_14006B1D0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = *(_QWORD *)(v3 + 24);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length == 1 )
  {
    Pool2 = (wchar_t *)ExAllocatePool2(64, 42, 1681082453);
    if ( !Pool2 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_6:
        v10 = -1073741670;
        goto LABEL_30;
      }
      v9 = 53;
LABEL_5:
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v5 + 8) + 1432LL),
        v7,
        5,
        v9,
        (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids);
      goto LABEL_6;
    }
    v10 = RtlStringCbPrintfW(
            Pool2,
            0x2Au,
            L"Port_#%04d.Hub_#%04d",
            *(unsigned __int16 *)(*(_QWORD *)(v5 + 8) + 200LL),
            *(_DWORD *)(*(_QWORD *)v5 + 96LL));
    if ( v10 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v11) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(*(_QWORD *)(v5 + 8) + 1432LL),
          v11,
          5,
          54,
          (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
          v10);
      }
      ExFreePoolWithTag(Pool2, 0x64334855u);
      goto LABEL_30;
    }
LABEL_29:
    v10 = 0;
    a2->IoStatus.Information = (unsigned __int64)Pool2;
    goto LABEL_30;
  }
  v10 = -1073741637;
  if ( !Length && *(_BYTE *)(v5 + 2011) && (*(_DWORD *)(v5 + 1652) & 1) == 0 )
  {
    a2->IoStatus.Information = 0;
    Size = CurrentStackLocation->Parameters.QueryInterface.Size;
    if ( !Size || !(unsigned __int8)HUBPDO_IsLanguageSupported(v5, Size) )
      Size = 1033;
    if ( Size == *(_WORD *)(v5 + 2048) )
    {
      v14 = (struct _KEVENT *)(v5 + 480);
    }
    else
    {
      v13 = *(void **)(v5 + 2040);
      *(_WORD *)(v5 + 2048) = Size;
      if ( v13 )
        ExFreePoolWithTag(v13, 0x64334855u);
      v14 = (struct _KEVENT *)(v5 + 480);
      *(_QWORD *)(v5 + 2040) = 0;
      KeClearEvent((PRKEVENT)(v5 + 480));
      HUBSM_AddEvent(v5 + 512, 4087);
      HUBMISC_WaitForSignal((PVOID)(v5 + 480));
    }
    v15 = *(unsigned __int8 **)(v5 + 2040);
    if ( v15
      || Size != 1033
      && (*(_WORD *)(v5 + 2048) = 1033,
          KeClearEvent(v14),
          HUBSM_AddEvent(v5 + 512, 4087),
          HUBMISC_WaitForSignal(v14),
          (v15 = *(unsigned __int8 **)(v5 + 2040)) != 0) )
    {
      v16 = (unsigned __int16)((((unsigned __int64)*v15 - 2) >> 1) + 1);
      v17 = (wchar_t *)ExAllocatePool2(64, 2 * v16, 1681082453);
      Pool2 = v17;
      if ( !v17 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_6;
        v9 = 55;
        goto LABEL_5;
      }
      memmove(v17, (const void *)(*(_QWORD *)(v5 + 2040) + 2LL), 2 * v16 - 2);
      Pool2[v16 - 1] = 0;
      goto LABEL_29;
    }
  }
LABEL_30:
  a2->IoStatus.Status = v10;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400178bc  mov     [rsp+arg_8], rbx
0x1400178c1  mov     [rsp+arg_10], rbp
0x1400178c6  mov     [rsp+arg_0], rcx
0x1400178cb  push    rsi
0x1400178cc  push    rdi
0x1400178cd  push    r13
0x1400178cf  push    r14
0x1400178d1  push    r15
0x1400178d3  sub     rsp, 30h
0x1400178d7  mov     rax, cs:WdfFunctions_01015
0x1400178de  mov     r15, rdx
0x1400178e1  mov     r8, cs:off_14006B1D0
0x1400178e8  mov     rdx, rcx
0x1400178eb  mov     rcx, cs:WdfDriverGlobals
0x1400178f2  mov     rax, [rax+650h]
0x1400178f9  call    _guard_dispatch_icall
0x1400178fe  mov     r14, [r15+0B8h]
0x140017905  mov     ecx, 1
0x14001790a  mov     rsi, [rax+18h]
0x14001790e  mov     eax, [r14+8]
0x140017912  cmp     eax, ecx
0x140017914  jnz     loc_140017A07
0x14001791a  lea     ebp, [rcx+29h]
0x14001791d  mov     r8d, 64334855h
0x140017923  mov     edx, ebp
0x140017925  lea     ecx, [rbp+16h]
0x140017928  call    cs:__imp_ExAllocatePool2
0x14001792f  nop     dword ptr [rax+rax+00h]
0x140017934  xor     edi, edi
0x140017936  mov     rbx, rax
0x140017939  test    rax, rax
0x14001793c  jnz     short loc_140017980
0x14001793e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017945  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001794c  jz      short loc_140017976
0x14001794e  lea     r9d, [rbp+0Bh]
0x140017952  mov     rcx, [rsi+8]
0x140017956  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x14001795d  mov     r8d, 5
0x140017963  mov     [rsp+58h+var_38], rax
0x140017968  mov     dl, 2
0x14001796a  mov     rcx, [rcx+598h]
0x140017971  call    WPP_RECORDER_SF_
0x140017976  mov     ebp, 0C000009Ah
0x14001797b  jmp     loc_140017BAA
0x140017980  mov     rax, [rsi+8]
0x140017984  lea     r8, aPort04dHub04d; "Port_#%04d.Hub_#%04d"
0x14001798b  mov     rcx, [rsi]
0x14001798e  mov     rdx, rbp; cbDest
0x140017991  movzx   r9d, word ptr [rax+0C8h]
0x140017999  mov     eax, [rcx+60h]
0x14001799c  mov     rcx, rbx; pszDest
0x14001799f  mov     dword ptr [rsp+58h+var_38], eax
0x1400179a3  call    RtlStringCbPrintfW
0x1400179a8  mov     ebp, eax
0x1400179aa  test    eax, eax
0x1400179ac  jns     loc_140017BA4
0x1400179b2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400179b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400179c0  jz      short loc_1400179EE
0x1400179c2  mov     rcx, [rsi+8]
0x1400179c6  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x1400179cd  mov     r9d, 36h ; '6'
0x1400179d3  mov     [rsp+58h+var_30], ebp
0x1400179d7  mov     dl, 2
0x1400179d9  mov     [rsp+58h+var_38], rax
0x1400179de  mov     rcx, [rcx+598h]
0x1400179e5  lea     r8d, [r9-31h]
0x1400179e9  call    WPP_RECORDER_SF_d
0x1400179ee  mov     edx, 64334855h; Tag
0x1400179f3  mov     rcx, rbx; P
0x1400179f6  call    cs:__imp_ExFreePoolWithTag
0x1400179fd  nop     dword ptr [rax+rax+00h]
0x140017a02  jmp     loc_140017BAA
0x140017a07  xor     edi, edi
0x140017a09  mov     ebp, 0C00000BBh
0x140017a0e  test    eax, eax
0x140017a10  jnz     loc_140017BAA
0x140017a16  cmp     [rsi+7DBh], dil
0x140017a1d  jz      loc_140017BAA
0x140017a23  mov     eax, [rsi+674h]
0x140017a29  test    cl, al
0x140017a2b  jnz     loc_140017BAA
0x140017a31  mov     [r15+38h], rdi
0x140017a35  movzx   r14d, word ptr [r14+10h]
0x140017a3a  test    r14w, r14w
0x140017a3e  jz      short loc_140017A50
0x140017a40  movzx   edx, r14w
0x140017a44  mov     rcx, rsi
0x140017a47  call    HUBPDO_IsLanguageSupported
0x140017a4c  test    al, al
0x140017a4e  jnz     short loc_140017A56
0x140017a50  mov     r14d, 409h
0x140017a56  mov     ebx, 0FF7h
0x140017a5b  cmp     r14w, [rsi+800h]
0x140017a63  jz      short loc_140017ACB
0x140017a65  mov     rcx, [rsi+7F8h]; P
0x140017a6c  mov     [rsi+800h], r14w
0x140017a74  test    rcx, rcx
0x140017a77  jz      short loc_140017A8A
0x140017a79  mov     edx, 64334855h; Tag
0x140017a7e  call    cs:__imp_ExFreePoolWithTag
0x140017a85  nop     dword ptr [rax+rax+00h]
0x140017a8a  lea     r13, [rsi+1E0h]
0x140017a91  mov     [rsi+7F8h], rdi
0x140017a98  mov     rcx, r13; Event
0x140017a9b  call    cs:__imp_KeClearEvent
0x140017aa2  nop     dword ptr [rax+rax+00h]
0x140017aa7  lea     rcx, [rsi+200h]
0x140017aae  mov     edx, ebx
0x140017ab0  call    HUBSM_AddEvent
0x140017ab5  mov     r8, [rsp+58h+arg_0]
0x140017aba  lea     rdx, aQueryDeviceTex; "Query device text"
0x140017ac1  mov     rcx, r13; Object
0x140017ac4  call    HUBMISC_WaitForSignal
0x140017ac9  jmp     short loc_140017AD2
0x140017acb  lea     r13, [rsi+1E0h]
0x140017ad2  mov     rax, [rsi+7F8h]
0x140017ad9  test    rax, rax
0x140017adc  jnz     short loc_140017B31
0x140017ade  mov     eax, 409h
0x140017ae3  cmp     r14w, ax
0x140017ae7  jz      loc_140017BAA
0x140017aed  mov     rcx, r13; Event
0x140017af0  mov     [rsi+800h], ax
0x140017af7  call    cs:__imp_KeClearEvent
0x140017afe  nop     dword ptr [rax+rax+00h]
0x140017b03  mov     edx, ebx
0x140017b05  lea     rcx, [rsi+200h]
0x140017b0c  call    HUBSM_AddEvent
0x140017b11  mov     r8, [rsp+58h+arg_0]
0x140017b16  lea     rdx, aQueryDeviceTex; "Query device text"
0x140017b1d  mov     rcx, r13; Object
0x140017b20  call    HUBMISC_WaitForSignal
0x140017b25  mov     rax, [rsi+7F8h]
0x140017b2c  test    rax, rax
0x140017b2f  jz      short loc_140017BAA
0x140017b31  movzx   eax, byte ptr [rax]
0x140017b34  mov     r8d, 64334855h
0x140017b3a  sub     rax, 2
0x140017b3e  mov     ecx, 40h ; '@'
0x140017b43  shr     rax, 1
0x140017b46  inc     ax
0x140017b49  movzx   ebp, ax
0x140017b4c  lea     r14, ds:0[rbp*2]
0x140017b54  mov     rdx, r14
0x140017b57  call    cs:__imp_ExAllocatePool2
0x140017b5e  nop     dword ptr [rax+rax+00h]
0x140017b63  mov     rbx, rax
0x140017b66  test    rax, rax
0x140017b69  jnz     short loc_140017B88
0x140017b6b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140017b72  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140017b79  jz      loc_140017976
0x140017b7f  lea     r9d, [rbx+37h]
0x140017b83  jmp     loc_140017952
0x140017b88  mov     rdx, [rsi+7F8h]
0x140017b8f  lea     r8, [r14-2]; Size
0x140017b93  add     rdx, 2; Src
0x140017b97  mov     rcx, rbx; void *
0x140017b9a  call    memmove
0x140017b9f  mov     [rbx+rbp*2-2], di
0x140017ba4  mov     ebp, edi
0x140017ba6  mov     [r15+38h], rbx
0x140017baa  xor     edx, edx; PriorityBoost
0x140017bac  mov     [r15+30h], ebp
0x140017bb0  mov     rcx, r15; Irp
0x140017bb3  call    cs:__imp_IofCompleteRequest
0x140017bba  nop     dword ptr [rax+rax+00h]
0x140017bbf  mov     rbx, [rsp+58h+arg_8]
0x140017bc4  mov     eax, ebp
0x140017bc6  mov     rbp, [rsp+58h+arg_10]
0x140017bcb  add     rsp, 30h
0x140017bcf  pop     r15
0x140017bd1  pop     r14
0x140017bd3  pop     r13
0x140017bd5  pop     rdi
0x140017bd6  pop     rsi
0x140017bd7  retn
```

# TmRegisterProtocolAddressInformation

- ea: `0x140018888`
- end: `0x140018b05`
- name: `TmRegisterProtocolAddressInformation`
- size: `637`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140018370`

## callees

- `0x140002940`
- `0x140018888`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400188d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400188f6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400188d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400188f6`
- `ntoskrnl!KeReleaseMutex` at `0x140018aac`
- `ntoskrnl!KeReleaseMutex` at `0x140018abd`
- `ntoskrnl!KeReleaseMutex` at `0x140022a5f`
- `ntoskrnl!KeReleaseMutex` at `0x140022a78`
- `ntoskrnl!KeReleaseMutex` at `0x140018aac`
- `ntoskrnl!KeReleaseMutex` at `0x140018abd`
- `ntoskrnl!KeReleaseMutex` at `0x140022a5f`
- `ntoskrnl!KeReleaseMutex` at `0x140022a78`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018adc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018adc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022a9b`
- `ntoskrnl!ObfReferenceObject` at `0x140018a03`
- `ntoskrnl!ObfReferenceObject` at `0x140018a03`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140018992`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140018992`
- `ntoskrnl!KeInitializeMutex` at `0x1400189d8`
- `ntoskrnl!KeInitializeMutex` at `0x1400189d8`
- `ntoskrnl!RtlCompareMemory` at `0x140018a78`
- `ntoskrnl!RtlCompareMemory` at `0x140018a78`

## pseudocode

```c
__int64 __fastcall TmRegisterProtocolAddressInformation(char *Object, _QWORD *a2, int a3, __int64 a4)
{
  __int64 p_SystemArgument1; // rdi
  char v8; // r14
  int v9; // ebx
  struct _KMUTANT *v10; // r13
  struct _DEVICE_OBJECT *i; // rdx
  char *v12; // rcx
  PVOID PoolWithQuotaTag; // rax
  char *v14; // rsi
  char **v15; // rcx
  _QWORD *CurrentIrp; // rdx

  p_SystemArgument1 = 0;
  v8 = 0;
  v9 = 0;
  v10 = (struct _KMUTANT *)(Object + 40);
  KeWaitForSingleObject(Object + 40, Executive, 0, 0, 0);
  KeWaitForSingleObject(&WPP_MAIN_CB.DeviceExtension, Executive, 0, 0, 0);
  if ( *((_DWORD *)Object + 7) == 2 )
  {
    if ( TmpAllProtocolsStaticInfoLength + a3 < (unsigned int)TmpAllProtocolsStaticInfoLength
      || (unsigned int)TmpAllProtocolsStaticInfoLength > 0x7FFFFFFF )
    {
      goto LABEL_20;
    }
    for ( i = (struct _DEVICE_OBJECT *)WPP_MAIN_CB.Queue.Wcb.DeviceObject;
          i != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject;
          i = *(struct _DEVICE_OBJECT **)&i->Type )
    {
      p_SystemArgument1 = (__int64)&i[-1].Dpc.SystemArgument1;
      v12 = (char *)i[-1].Dpc.SystemArgument2 - *a2;
      if ( !v12 )
        v12 = (char *)(*(_QWORD *)(p_SystemArgument1 + 16) - a2[1]);
      if ( !v12 )
      {
        v9 = -1072103409;
        goto LABEL_21;
      }
    }
    v8 = 1;
    PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)520, 0x88u, 0x72506D54u);
    p_SystemArgument1 = (__int64)PoolWithQuotaTag;
    if ( PoolWithQuotaTag )
    {
      memset(PoolWithQuotaTag, 0, 0x88u);
      *(_DWORD *)p_SystemArgument1 = -1341456379;
      *(_DWORD *)(p_SystemArgument1 + 4) = 1;
      *(_OWORD *)(p_SystemArgument1 + 8) = *(_OWORD *)a2;
      KeInitializeMutex((PRKMUTEX)(p_SystemArgument1 + 24), 0);
      *(_DWORD *)(p_SystemArgument1 + 120) = a3;
      if ( a3 )
        *(_QWORD *)(p_SystemArgument1 + 128) = a4;
      *(_QWORD *)(p_SystemArgument1 + 112) = Object;
      ObfReferenceObject(Object);
      v14 = Object + 312;
      v15 = (char **)*((_QWORD *)v14 + 1);
      if ( *v15 != v14
        || (*(_QWORD *)(p_SystemArgument1 + 80) = v14,
            *(_QWORD *)(p_SystemArgument1 + 88) = v15,
            *v15 = (char *)(p_SystemArgument1 + 80),
            *((_QWORD *)v14 + 1) = p_SystemArgument1 + 80,
            CurrentIrp = WPP_MAIN_CB.Queue.Wcb.CurrentIrp,
            *(struct _DEVICE_OBJECT **)WPP_MAIN_CB.Queue.Wcb.CurrentIrp != (struct _DEVICE_OBJECT *)&WPP_MAIN_CB.Queue.Wcb.DeviceObject) )
      {
        __fastfail(3u);
      }
      *(_QWORD *)(p_SystemArgument1 + 96) = &WPP_MAIN_CB.Queue.Wcb.DeviceObject;
      *(_QWORD *)(p_SystemArgument1 + 104) = CurrentIrp;
      *CurrentIrp = p_SystemArgument1 + 96;
      WPP_MAIN_CB.Queue.Wcb.CurrentIrp = (PVOID)(p_SystemArgument1 + 96);
      ++LODWORD(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
      TmpAllProtocolsStaticInfoLength += a3;
      if ( RtlCompareMemory((const void *)(p_SystemArgument1 + 8), &TmpPromotingProtocolId, 0x10u) == 16 )
        TmpPromotingProtocolRegistered = p_SystemArgument1;
    }
    else
    {
LABEL_20:
      v9 = -1073741670;
    }
  }
  else
  {
    v9 = -1073741823;
  }
LABEL_21:
  KeReleaseMutex((PRKMUTEX)&WPP_MAIN_CB.DeviceExtension, 0);
  KeReleaseMutex(v10, 0);
  if ( v9 < 0 && v8 && p_SystemArgument1 )
    ExFreePoolWithTag((PVOID)p_SystemArgument1, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140018888  mov     rax, rsp
0x14001888b  mov     [rax+10h], rbx
0x14001888f  mov     [rax+18h], rsi
0x140018893  mov     [rax+20h], r9
0x140018897  mov     [rax+8], rcx
0x14001889b  push    rdi
0x14001889c  push    r12
0x14001889e  push    r13
0x1400188a0  push    r14
0x1400188a2  push    r15
0x1400188a4  sub     rsp, 50h
0x1400188a8  mov     r12d, r8d
0x1400188ab  mov     r15, rdx
0x1400188ae  mov     rsi, rcx
0x1400188b1  xor     edi, edi
0x1400188b3  mov     [rax-40h], rdi
0x1400188b7  xor     r14b, r14b
0x1400188ba  mov     [rax-48h], r14b
0x1400188be  xor     ebx, ebx
0x1400188c0  mov     [rax-44h], ebx
0x1400188c3  lea     r13, [rcx+28h]
0x1400188c7  mov     [rax-58h], rbx
0x1400188cb  xor     r9d, r9d; Alertable
0x1400188ce  xor     r8d, r8d; WaitMode
0x1400188d1  xor     edx, edx; WaitReason
0x1400188d3  mov     rcx, r13; Object
0x1400188d6  call    cs:__imp_KeWaitForSingleObject
0x1400188dd  nop     dword ptr [rax+rax+00h]
0x1400188e2  mov     [rsp+78h+Timeout], rbx; Timeout
0x1400188e7  xor     r9d, r9d; Alertable
0x1400188ea  xor     r8d, r8d; WaitMode
0x1400188ed  xor     edx, edx; WaitReason
0x1400188ef  lea     rcx, WPP_MAIN_CB.DeviceExtension; Object
0x1400188f6  call    cs:__imp_KeWaitForSingleObject
0x1400188fd  nop     dword ptr [rax+rax+00h]
0x140018902  cmp     dword ptr [rsi+1Ch], 2
0x140018906  jz      short loc_140018912
0x140018908  mov     ebx, 0C0000001h
0x14001890d  jmp     loc_140018A9F
0x140018912  mov     ecx, cs:TmpAllProtocolsStaticInfoLength
0x140018918  lea     eax, [rcx+r12]
0x14001891c  cmp     eax, ecx
0x14001891e  jb      loc_140018A9A
0x140018924  cmp     ecx, 7FFFFFFFh
0x14001892a  ja      loc_140018A9A
0x140018930  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140018937  lea     rax, WPP_MAIN_CB.Queue+30h
0x14001893e  cmp     rdx, rax
0x140018941  jz      short loc_140018977
0x140018943  lea     rdi, [rdx-60h]
0x140018947  mov     [rsp+78h+var_40], rdi
0x14001894c  mov     rcx, [rdi+8]
0x140018950  mov     rax, [r15]
0x140018953  sub     rcx, rax
0x140018956  jnz     short loc_140018963
0x140018958  mov     rcx, [rdi+10h]
0x14001895c  mov     rax, [r15+8]
0x140018960  sub     rcx, rax
0x140018963  test    rcx, rcx
0x140018966  jnz     short loc_140018972
0x140018968  mov     ebx, 0C019000Fh
0x14001896d  jmp     loc_140018A9F
0x140018972  mov     rdx, [rdx]
0x140018975  jmp     short loc_140018937
0x140018977  mov     r14d, 1
0x14001897d  mov     [rsp+78h+var_48], r14b
0x140018982  mov     edx, 88h; NumberOfBytes
0x140018987  mov     ecx, 208h; PoolType
0x14001898c  mov     r8d, 72506D54h; Tag
0x140018992  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x140018999  nop     dword ptr [rax+rax+00h]
0x14001899e  mov     rdi, rax
0x1400189a1  mov     [rsp+78h+var_40], rax
0x1400189a6  test    rax, rax
0x1400189a9  jz      loc_140018A9A
0x1400189af  xor     edx, edx; Val
0x1400189b1  mov     r8d, 88h; Size
0x1400189b7  mov     rcx, rax; void *
0x1400189ba  call    memset
0x1400189bf  mov     dword ptr [rdi], 0B00B0005h
0x1400189c5  mov     [rdi+4], r14d
0x1400189c9  movups  xmm0, xmmword ptr [r15]
0x1400189cd  movdqu  xmmword ptr [rdi+8], xmm0
0x1400189d2  lea     rcx, [rdi+18h]; Mutex
0x1400189d6  xor     edx, edx; Level
0x1400189d8  call    cs:__imp_KeInitializeMutex
0x1400189df  nop     dword ptr [rax+rax+00h]
0x1400189e4  mov     [rdi+78h], r12d
0x1400189e8  test    r12d, r12d
0x1400189eb  jz      short loc_1400189FC
0x1400189ed  mov     rax, [rsp+78h+arg_18]
0x1400189f5  mov     [rdi+80h], rax
0x1400189fc  mov     [rdi+70h], rsi
0x140018a00  mov     rcx, rsi; Object
0x140018a03  call    cs:__imp_ObfReferenceObject
0x140018a0a  nop     dword ptr [rax+rax+00h]
0x140018a0f  add     rsi, 138h
0x140018a16  mov     rcx, [rsi+8]
0x140018a1a  cmp     [rcx], rsi
0x140018a1d  jnz     short loc_140018A93
0x140018a1f  lea     rax, [rdi+50h]
0x140018a23  mov     [rax], rsi
0x140018a26  mov     [rax+8], rcx
0x140018a2a  mov     [rcx], rax
0x140018a2d  mov     [rsi+8], rax
0x140018a31  mov     rdx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x140018a38  lea     rcx, WPP_MAIN_CB.Queue+30h
0x140018a3f  cmp     [rdx], rcx
0x140018a42  jnz     short loc_140018A93
0x140018a44  lea     rax, [rdi+60h]
0x140018a48  mov     [rax], rcx
0x140018a4b  mov     [rax+8], rdx
0x140018a4f  mov     [rdx], rax
0x140018a52  mov     qword ptr cs:WPP_MAIN_CB.Queue+38h, rax
0x140018a59  add     dword ptr cs:WPP_MAIN_CB.Queue+40h, r14d
0x140018a60  add     cs:TmpAllProtocolsStaticInfoLength, r12d
0x140018a67  mov     r8d, 10h; Length
0x140018a6d  lea     rdx, TmpPromotingProtocolId; Source2
0x140018a74  lea     rcx, [rdi+8]; Source1
0x140018a78  call    cs:__imp_RtlCompareMemory
0x140018a7f  nop     dword ptr [rax+rax+00h]
0x140018a84  cmp     rax, 10h
0x140018a88  jnz     short loc_140018AA3
0x140018a8a  mov     cs:TmpPromotingProtocolRegistered, rdi
0x140018a91  jmp     short loc_140018AA3
0x140018a93  mov     ecx, 3
0x140018a98  int     29h; Win8: RtlFailFast(ecx)
0x140018a9a  mov     ebx, 0C000009Ah
0x140018a9f  mov     [rsp+78h+var_44], ebx
0x140018aa3  xor     edx, edx; Wait
0x140018aa5  lea     rcx, WPP_MAIN_CB.DeviceExtension; Mutex
0x140018aac  call    cs:__imp_KeReleaseMutex
0x140018ab3  nop     dword ptr [rax+rax+00h]
0x140018ab8  xor     edx, edx; Wait
0x140018aba  mov     rcx, r13; Mutex
0x140018abd  call    cs:__imp_KeReleaseMutex
0x140018ac4  nop     dword ptr [rax+rax+00h]
0x140018ac9  test    ebx, ebx
0x140018acb  jns     short loc_140018AE8
0x140018acd  test    r14b, r14b
0x140018ad0  jz      short loc_140018AE8
0x140018ad2  test    rdi, rdi
0x140018ad5  jz      short loc_140018AE8
0x140018ad7  xor     edx, edx; Tag
0x140018ad9  mov     rcx, rdi; P
0x140018adc  call    cs:__imp_ExFreePoolWithTag
0x140018ae3  nop     dword ptr [rax+rax+00h]
0x140018ae8  mov     eax, ebx
0x140018aea  lea     r11, [rsp+78h+var_28]
0x140018aef  mov     rbx, [r11+38h]
0x140018af3  mov     rsi, [r11+40h]
0x140018af7  mov     rsp, r11
0x140018afa  pop     r15
0x140018afc  pop     r14
0x140018afe  pop     r13
0x140018b00  pop     r12
0x140018b02  pop     rdi
0x140018b03  retn
0x140022a4d  push    rbp
0x140022a4f  sub     rsp, 30h
0x140022a53  mov     rbp, rdx
0x140022a56  xor     edx, edx; Wait
0x140022a58  lea     rcx, WPP_MAIN_CB.DeviceExtension; Mutex
0x140022a5f  call    cs:__imp_KeReleaseMutex
0x140022a66  nop     dword ptr [rax+rax+00h]
0x140022a6b  mov     rcx, [rbp+80h]
0x140022a72  add     rcx, 28h ; '('; Mutex
0x140022a76  xor     edx, edx; Wait
0x140022a78  call    cs:__imp_KeReleaseMutex
0x140022a7f  nop     dword ptr [rax+rax+00h]
0x140022a84  cmp     dword ptr [rbp+34h], 0
0x140022a88  jge     short loc_140022AA8
0x140022a8a  cmp     byte ptr [rbp+30h], 0
0x140022a8e  jz      short loc_140022AA8
0x140022a90  mov     rcx, [rbp+38h]; P
0x140022a94  test    rcx, rcx
0x140022a97  jz      short loc_140022AA8
0x140022a99  xor     edx, edx; Tag
0x140022a9b  call    cs:__imp_ExFreePoolWithTag
0x140022aa2  nop     dword ptr [rax+rax+00h]
0x140022aa7  nop
0x140022aa8  add     rsp, 30h
0x140022aac  pop     rbp
0x140022aad  retn
```

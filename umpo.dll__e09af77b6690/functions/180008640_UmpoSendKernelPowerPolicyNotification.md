# UmpoSendKernelPowerPolicyNotification

- ea: `0x180008640`
- end: `0x180008865`
- name: `UmpoSendKernelPowerPolicyNotification`
- size: `549`
- prototype: `__int64 __fastcall(UUID *, UUID *, UUID *, GUID *, _OWORD *, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800012a0`
- `0x180001580`
- `0x180008510`
- `0x18000e0c0`

## callees

- `0x180004380`
- `0x180004e0c`
- `0x1800059c0`
- `0x180008640`
- `0x18000f3dc`
- `0x180015f78`
- `0x1800188c8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800086f3`
- `ntdll!RtlAllocateHeap` at `0x1800086f3`
- `ntdll!RtlFreeHeap` at `0x180008780`
- `ntdll!RtlFreeHeap` at `0x180008780`
- `KERNELBASE!WTSIsServerContainer` at `0x180008766`
- `KERNELBASE!WTSIsServerContainer` at `0x180008766`

## pseudocode

```c
__int64 __fastcall UmpoSendKernelPowerPolicyNotification(UUID *a1, UUID *a2, UUID *a3, GUID *a4, _OWORD *a5, char a6)
{
  _OWORD *v8; // rsi
  UUID *v9; // r14
  GUID *v10; // r15
  unsigned int ACValue; // eax
  unsigned int v12; // ebx
  char *Heap; // rax
  void *v14; // rdi
  char v15; // cl
  unsigned int v17; // eax
  int Src; // [rsp+50h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-14h]
  size_t Size; // [rsp+B8h] [rbp+50h] BYREF

  LODWORD(Size) = 4;
  Src = 0;
  if ( !a2 )
    return 87;
  v8 = a5;
  if ( !a5 )
    return 87;
  v9 = (UUID *)&NO_SUBGROUP_GUID;
  v10 = &GUID_POWER_POLICY_PROFILE_DEFAULT;
  if ( a3 )
    v9 = a3;
  if ( a4 )
    v10 = a4;
  if ( a6 )
    ACValue = UmpoReadACValue(a1, a2, v9, v10, (__int64)a5, 0, (__int64)&Src, (DWORD *)&Size);
  else
    ACValue = UmpoInternalReadxCValue(a1, a2, v9, v10, (__int64)a5, 0, 0, (__int64)&Src, (LPDWORD)&Size);
  v12 = ACValue;
  if ( ACValue )
  {
    if ( ACValue == 2 )
      return v12;
    if ( ACValue != 234 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      return v12;
    }
  }
  if ( (_DWORD)Size )
  {
    v19 = Size + 74;
    Heap = (char *)RtlAllocateHeap(UmpoHeapHandle, 8u, (unsigned int)(Size + 74));
    v14 = Heap;
    if ( !Heap )
      return 14;
    v15 = a6;
    *(_DWORD *)Heap = 4;
    *((_DWORD *)Heap + 2) = 1;
    *((_DWORD *)Heap + 16) = Size;
    *((_DWORD *)Heap + 15) = v15 == 0;
    *(GUID *)(Heap + 12) = *v10;
    *(_OWORD *)(Heap + 28) = *v8;
    *(UUID *)(Heap + 44) = *v9;
    if ( v12 )
    {
      if ( v15 )
        v17 = UmpoReadACValue(a1, a2, v9, v10, (__int64)v8, 0, (__int64)(Heap + 68), (DWORD *)&Size);
      else
        v17 = UmpoInternalReadxCValue(a1, a2, v9, v10, (__int64)v8, 0, 0, (__int64)(Heap + 68), (LPDWORD)&Size);
      v12 = v17;
      if ( v17 )
        goto LABEL_15;
    }
    else
    {
      memcpy_0(Heap + 68, &Src, (unsigned int)Size);
    }
    v12 = UmpoAlpcSendPowerMessage(v14, v19);
    if ( !(unsigned __int8)WTSIsServerContainer() && v12 )
      UmpoTraceSendKernelPowerPolicyNotification(v12);
LABEL_15:
    RtlFreeHeap(UmpoHeapHandle, 0, v14);
  }
  return v12;
}

```

## disassembly

```asm
0x180008640  push    rbp
0x180008642  push    rbx
0x180008643  push    rsi
0x180008644  push    rdi
0x180008645  push    r12
0x180008647  push    r13
0x180008649  push    r14
0x18000864b  push    r15
0x18000864d  mov     rbp, rsp
0x180008650  sub     rsp, 68h
0x180008654  xor     edi, edi
0x180008656  mov     dword ptr [rbp+Size], 4
0x18000865d  mov     [rbp+Src], edi
0x180008660  mov     r12, rdx
0x180008663  mov     r13, rcx
0x180008666  test    rdx, rdx
0x180008669  jz      loc_180008828
0x18000866f  mov     rsi, [rbp+arg_20]
0x180008673  test    rsi, rsi
0x180008676  jz      loc_180008828
0x18000867c  test    r8, r8
0x18000867f  lea     r14, NO_SUBGROUP_GUID
0x180008686  lea     r15, GUID_POWER_POLICY_PROFILE_DEFAULT
0x18000868d  cmovnz  r14, r8
0x180008691  lea     rax, [rbp+Size]
0x180008695  test    r9, r9
0x180008698  mov     r8, r14
0x18000869b  cmovnz  r15, r9
0x18000869f  mov     r9, r15
0x1800086a2  cmp     [rbp+arg_28], dil
0x1800086a6  jz      loc_180008799
0x1800086ac  mov     [rsp+68h+var_30], rax
0x1800086b1  lea     rax, [rbp+Src]
0x1800086b5  mov     [rsp+68h+var_38], rax
0x1800086ba  mov     [rsp+68h+var_40], rdi
0x1800086bf  mov     [rsp+68h+var_48], rsi
0x1800086c4  call    UmpoReadACValue
0x1800086c9  mov     ebx, eax
0x1800086cb  test    eax, eax
0x1800086cd  jnz     loc_180008832
0x1800086d3  mov     eax, dword ptr [rbp+Size]
0x1800086d6  test    eax, eax
0x1800086d8  jz      loc_180008786
0x1800086de  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x1800086e5  add     eax, 4Ah ; 'J'
0x1800086e8  mov     r8d, eax; Size
0x1800086eb  mov     edx, 8; Flags
0x1800086f0  mov     [rbp+var_14], eax
0x1800086f3  call    cs:__imp_RtlAllocateHeap
0x1800086f9  xor     edx, edx
0x1800086fb  mov     rdi, rax
0x1800086fe  test    rax, rax
0x180008701  jz      loc_1800087C0
0x180008707  mov     cl, [rbp+arg_28]
0x18000870a  mov     dword ptr [rax], 4
0x180008710  test    cl, cl
0x180008712  mov     dword ptr [rax+8], 1
0x180008719  mov     eax, dword ptr [rbp+Size]
0x18000871c  mov     [rdi+40h], eax
0x18000871f  mov     eax, edx
0x180008721  setz    al
0x180008724  mov     [rdi+3Ch], eax
0x180008727  lea     rax, [rdi+44h]
0x18000872b  movups  xmm0, xmmword ptr [r15]
0x18000872f  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x180008734  movups  xmm1, xmmword ptr [rsi]
0x180008737  movdqu  xmmword ptr [rdi+1Ch], xmm1
0x18000873c  movups  xmm0, xmmword ptr [r14]
0x180008740  movdqu  xmmword ptr [rdi+2Ch], xmm0
0x180008745  test    ebx, ebx
0x180008747  jnz     short loc_1800087C7
0x180008749  mov     r8d, dword ptr [rbp+Size]; Size
0x18000874d  lea     rdx, [rbp+Src]; Src
0x180008751  mov     rcx, rax; void *
0x180008754  call    memcpy_0
0x180008759  mov     edx, [rbp+var_14]
0x18000875c  mov     rcx, rdi
0x18000875f  call    UmpoAlpcSendPowerMessage
0x180008764  mov     ebx, eax
0x180008766  call    cs:__imp_WTSIsServerContainer
0x18000876c  test    al, al
0x18000876e  jz      loc_180008851
0x180008774  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000877b  mov     r8, rdi; P
0x18000877e  xor     edx, edx; Flags
0x180008780  call    cs:__imp_RtlFreeHeap
0x180008786  mov     eax, ebx
0x180008788  add     rsp, 68h
0x18000878c  pop     r15
0x18000878e  pop     r14
0x180008790  pop     r13
0x180008792  pop     r12
0x180008794  pop     rdi
0x180008795  pop     rsi
0x180008796  pop     rbx
0x180008797  pop     rbp
0x180008798  retn
0x180008799  mov     [rsp+68h+var_28], rax
0x18000879e  lea     rax, [rbp+Src]
0x1800087a2  mov     [rsp+68h+var_30], rax
0x1800087a7  mov     [rsp+68h+var_38], rdi
0x1800087ac  mov     byte ptr [rsp+68h+var_40], dil
0x1800087b1  mov     [rsp+68h+var_48], rsi
0x1800087b6  call    UmpoInternalReadxCValue
0x1800087bb  jmp     loc_1800086C9
0x1800087c0  mov     ebx, 0Eh
0x1800087c5  jmp     short loc_180008786
0x1800087c7  test    cl, cl
0x1800087c9  mov     r9, r15
0x1800087cc  lea     rcx, [rbp+Size]
0x1800087d0  mov     r8, r14
0x1800087d3  jz      short loc_180008803
0x1800087d5  mov     [rsp+68h+var_30], rcx
0x1800087da  mov     rcx, r13
0x1800087dd  mov     [rsp+68h+var_38], rax
0x1800087e2  mov     [rsp+68h+var_40], rdx
0x1800087e7  mov     rdx, r12
0x1800087ea  mov     [rsp+68h+var_48], rsi
0x1800087ef  call    UmpoReadACValue
0x1800087f4  mov     ebx, eax
0x1800087f6  test    eax, eax
0x1800087f8  jz      loc_180008759
0x1800087fe  jmp     loc_180008774
0x180008803  mov     [rsp+68h+var_28], rcx
0x180008808  mov     rcx, r13
0x18000880b  mov     [rsp+68h+var_30], rax
0x180008810  mov     [rsp+68h+var_38], rdx
0x180008815  mov     byte ptr [rsp+68h+var_40], dl
0x180008819  mov     rdx, r12
0x18000881c  mov     [rsp+68h+var_48], rsi
0x180008821  call    UmpoInternalReadxCValue
0x180008826  jmp     short loc_1800087F4
0x180008828  mov     ebx, 57h ; 'W'
0x18000882d  jmp     loc_180008786
0x180008832  cmp     ebx, 2
0x180008835  jz      loc_180008786
0x18000883b  cmp     ebx, 0EAh
0x180008841  jz      loc_1800086D3
0x180008847  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000884c  jmp     loc_180008786
0x180008851  test    ebx, ebx
0x180008853  jz      loc_180008774
0x180008859  mov     ecx, ebx
0x18000885b  call    UmpoTraceSendKernelPowerPolicyNotification
0x180008860  jmp     loc_180008774
```

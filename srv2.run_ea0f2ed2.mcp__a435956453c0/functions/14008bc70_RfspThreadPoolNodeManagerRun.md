# RfspThreadPoolNodeManagerRun

- ea: `0x14008bc70`
- end: `0x14008bd9c`
- name: `RfspThreadPoolNodeManagerRun`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140038490`
- `0x14008bc70`
- `0x14008bda4`

## import_xrefs

- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14008bce7`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14008bce7`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14008bd7d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14008bd7d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008bd2d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008bd2d`
- `ntoskrnl!KeSetPriorityThread` at `0x14008bcae`
- `ntoskrnl!KeSetPriorityThread` at `0x14008bcae`

## pseudocode

```c
NTSTATUS __fastcall RfspThreadPoolNodeManagerRun(__int64 a1)
{
  __int64 v1; // rdx
  __int16 epi16; // di
  KAFFINITY Mask; // rsi
  USHORT v5; // cx
  NTSTATUS result; // eax
  PVOID Object[2]; // [rsp+40h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+50h] [rbp-28h] BYREF

  v1 = *(_QWORD *)(a1 + 216);
  *(_OWORD *)Object = 0;
  LODWORD(v1) = *(_DWORD *)(v1 + 8);
  Affinity = 0;
  KeSetPriorityThread(KeGetCurrentThread(), v1);
  epi16 = 0;
  Mask = 0;
  Object[0] = (PVOID)(a1 + 96);
  Object[1] = (PVOID)(a1 + 32);
  do
  {
    while ( 1 )
    {
      v5 = *(_WORD *)(a1 + 232);
      Affinity = 0;
      KeQueryNodeActiveAffinity(v5, &Affinity, 0);
      if ( Mask != Affinity.Mask || epi16 != Affinity.Group )
      {
        if ( Affinity.Mask )
        {
          KeSetSystemGroupAffinityThread(&Affinity, 0);
          epi16 = _mm_extract_epi16((__m128i)Affinity, 4);
          Mask = Affinity.Mask;
        }
      }
      result = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, 0, 0);
      if ( result )
        break;
      if ( (int)RfspThreadPoolNodeCreateWorker(a1) < 0 )
        _InterlockedExchange((volatile __int32 *)(a1 + 68), 0);
    }
  }
  while ( result != 1 );
  return result;
}

```

## disassembly

```asm
0x14008bc70  push    rbp
0x14008bc72  push    rbx
0x14008bc73  push    rsi
0x14008bc74  push    rdi
0x14008bc75  mov     rbp, rsp
0x14008bc78  sub     rsp, 78h
0x14008bc7c  mov     rax, cs:__security_cookie
0x14008bc83  xor     rax, rsp
0x14008bc86  mov     [rbp+var_18], rax
0x14008bc8a  mov     rdx, [rcx+0D8h]
0x14008bc91  xorps   xmm1, xmm1
0x14008bc94  movups  xmmword ptr [rbp+Object], xmm1
0x14008bc98  mov     rbx, rcx
0x14008bc9b  mov     rcx, gs:188h; Thread
0x14008bca4  xorps   xmm0, xmm0
0x14008bca7  mov     edx, [rdx+8]; Priority
0x14008bcaa  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14008bcae  call    cs:__imp_KeSetPriorityThread
0x14008bcb5  nop     dword ptr [rax+rax+00h]
0x14008bcba  movzx   edi, [rbp+Affinity.Group]
0x14008bcbe  lea     rax, [rbx+60h]
0x14008bcc2  mov     rsi, [rbp+Affinity.Mask]
0x14008bcc6  mov     [rbp+Object], rax
0x14008bcca  lea     rax, [rbx+20h]
0x14008bcce  mov     [rbp+Object+8], rax
0x14008bcd2  movzx   ecx, word ptr [rbx+0E8h]; NodeNumber
0x14008bcd9  lea     rdx, [rbp+Affinity]; Affinity
0x14008bcdd  xorps   xmm0, xmm0
0x14008bce0  xor     r8d, r8d; Count
0x14008bce3  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14008bce7  call    cs:__imp_KeQueryNodeActiveAffinity
0x14008bcee  nop     dword ptr [rax+rax+00h]
0x14008bcf3  mov     rax, [rbp+Affinity.Mask]
0x14008bcf7  cmp     rsi, rax
0x14008bcfa  jnz     short loc_14008BD72
0x14008bcfc  cmp     di, [rbp+Affinity.Group]
0x14008bd00  jnz     short loc_14008BD72
0x14008bd02  xor     r9d, r9d; WaitReason
0x14008bd05  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14008bd0e  mov     [rsp+78h+Timeout], 0; Timeout
0x14008bd17  lea     rdx, [rbp+Object]; Object
0x14008bd1b  mov     [rsp+78h+Alertable], 0; Alertable
0x14008bd20  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14008bd25  lea     r8d, [r9+1]; WaitType
0x14008bd29  lea     ecx, [r9+2]; Count
0x14008bd2d  call    cs:__imp_KeWaitForMultipleObjects
0x14008bd34  nop     dword ptr [rax+rax+00h]
0x14008bd39  test    eax, eax
0x14008bd3b  jz      short loc_14008BD58
0x14008bd3d  cmp     eax, 1
0x14008bd40  jnz     short loc_14008BCD2
0x14008bd42  mov     rcx, [rbp+var_18]
0x14008bd46  xor     rcx, rsp; StackCookie
0x14008bd49  call    __security_check_cookie
0x14008bd4e  add     rsp, 78h
0x14008bd52  pop     rdi
0x14008bd53  pop     rsi
0x14008bd54  pop     rbx
0x14008bd55  pop     rbp
0x14008bd56  retn
0x14008bd58  mov     rcx, rbx
0x14008bd5b  call    RfspThreadPoolNodeCreateWorker
0x14008bd60  test    eax, eax
0x14008bd62  jns     loc_14008BCD2
0x14008bd68  xor     eax, eax
0x14008bd6a  xchg    eax, [rbx+44h]
0x14008bd6d  jmp     loc_14008BCD2
0x14008bd72  test    rax, rax
0x14008bd75  jz      short loc_14008BD02
0x14008bd77  xor     edx, edx; PreviousAffinity
0x14008bd79  lea     rcx, [rbp+Affinity]; Affinity
0x14008bd7d  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14008bd84  nop     dword ptr [rax+rax+00h]
0x14008bd89  movaps  xmm0, xmmword ptr [rbp+Affinity.Mask]
0x14008bd8d  pextrw  edi, xmm0, 4
0x14008bd92  movq    rsi, xmm0
0x14008bd97  jmp     loc_14008BD02
```

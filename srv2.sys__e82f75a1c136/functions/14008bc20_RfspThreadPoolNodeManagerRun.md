# RfspThreadPoolNodeManagerRun

- ea: `0x14008bc20`
- end: `0x14008bd4c`
- name: `RfspThreadPoolNodeManagerRun`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140038490`
- `0x14008bc20`
- `0x14008bd54`

## import_xrefs

- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14008bc97`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14008bc97`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14008bd2d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14008bd2d`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008bcdd`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14008bcdd`
- `ntoskrnl!KeSetPriorityThread` at `0x14008bc5e`
- `ntoskrnl!KeSetPriorityThread` at `0x14008bc5e`

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
0x14008bc20  push    rbp
0x14008bc22  push    rbx
0x14008bc23  push    rsi
0x14008bc24  push    rdi
0x14008bc25  mov     rbp, rsp
0x14008bc28  sub     rsp, 78h
0x14008bc2c  mov     rax, cs:__security_cookie
0x14008bc33  xor     rax, rsp
0x14008bc36  mov     [rbp+var_18], rax
0x14008bc3a  mov     rdx, [rcx+0D8h]
0x14008bc41  xorps   xmm1, xmm1
0x14008bc44  movups  xmmword ptr [rbp+Object], xmm1
0x14008bc48  mov     rbx, rcx
0x14008bc4b  mov     rcx, gs:188h; Thread
0x14008bc54  xorps   xmm0, xmm0
0x14008bc57  mov     edx, [rdx+8]; Priority
0x14008bc5a  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14008bc5e  call    cs:__imp_KeSetPriorityThread
0x14008bc65  nop     dword ptr [rax+rax+00h]
0x14008bc6a  movzx   edi, [rbp+Affinity.Group]
0x14008bc6e  lea     rax, [rbx+60h]
0x14008bc72  mov     rsi, [rbp+Affinity.Mask]
0x14008bc76  mov     [rbp+Object], rax
0x14008bc7a  lea     rax, [rbx+20h]
0x14008bc7e  mov     [rbp+Object+8], rax
0x14008bc82  movzx   ecx, word ptr [rbx+0E8h]; NodeNumber
0x14008bc89  lea     rdx, [rbp+Affinity]; Affinity
0x14008bc8d  xorps   xmm0, xmm0
0x14008bc90  xor     r8d, r8d; Count
0x14008bc93  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14008bc97  call    cs:__imp_KeQueryNodeActiveAffinity
0x14008bc9e  nop     dword ptr [rax+rax+00h]
0x14008bca3  mov     rax, [rbp+Affinity.Mask]
0x14008bca7  cmp     rsi, rax
0x14008bcaa  jnz     short loc_14008BD22
0x14008bcac  cmp     di, [rbp+Affinity.Group]
0x14008bcb0  jnz     short loc_14008BD22
0x14008bcb2  xor     r9d, r9d; WaitReason
0x14008bcb5  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x14008bcbe  mov     [rsp+78h+Timeout], 0; Timeout
0x14008bcc7  lea     rdx, [rbp+Object]; Object
0x14008bccb  mov     [rsp+78h+Alertable], 0; Alertable
0x14008bcd0  mov     [rsp+78h+WaitMode], 0; WaitMode
0x14008bcd5  lea     r8d, [r9+1]; WaitType
0x14008bcd9  lea     ecx, [r9+2]; Count
0x14008bcdd  call    cs:__imp_KeWaitForMultipleObjects
0x14008bce4  nop     dword ptr [rax+rax+00h]
0x14008bce9  test    eax, eax
0x14008bceb  jz      short loc_14008BD08
0x14008bced  cmp     eax, 1
0x14008bcf0  jnz     short loc_14008BC82
0x14008bcf2  mov     rcx, [rbp+var_18]
0x14008bcf6  xor     rcx, rsp; StackCookie
0x14008bcf9  call    __security_check_cookie
0x14008bcfe  add     rsp, 78h
0x14008bd02  pop     rdi
0x14008bd03  pop     rsi
0x14008bd04  pop     rbx
0x14008bd05  pop     rbp
0x14008bd06  retn
0x14008bd08  mov     rcx, rbx
0x14008bd0b  call    RfspThreadPoolNodeCreateWorker
0x14008bd10  test    eax, eax
0x14008bd12  jns     loc_14008BC82
0x14008bd18  xor     eax, eax
0x14008bd1a  xchg    eax, [rbx+44h]
0x14008bd1d  jmp     loc_14008BC82
0x14008bd22  test    rax, rax
0x14008bd25  jz      short loc_14008BCB2
0x14008bd27  xor     edx, edx; PreviousAffinity
0x14008bd29  lea     rcx, [rbp+Affinity]; Affinity
0x14008bd2d  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14008bd34  nop     dword ptr [rax+rax+00h]
0x14008bd39  movaps  xmm0, xmmword ptr [rbp+Affinity.Mask]
0x14008bd3d  pextrw  edi, xmm0, 4
0x14008bd42  movq    rsi, xmm0
0x14008bd47  jmp     loc_14008BCB2
```

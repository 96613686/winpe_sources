# SMDeInitStateMachine

- ea: `0x18007c5d0`
- end: `0x18007c692`
- name: `SMDeInitStateMachine`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18007bd78`
- `0x18007c308`

## callees

- `0x18000892c`
- `0x180008998`
- `0x18007b71c`
- `0x18007c5d0`
- `0x18007d138`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007c646`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18007c646`

## pseudocode

```c
__int64 __fastcall SMDeInitStateMachine(__int64 a1)
{
  PVOID *v2; // rcx
  unsigned int v3; // edi
  void *v4; // rcx

  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids);
    v2 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v3 = 0;
    if ( *(_DWORD *)(a1 + 16) )
    {
      SMStopStateMachine(a1);
      v4 = *(void **)(a1 + 120);
      if ( v4 )
        TmDeleteTimer(v4);
      *(_QWORD *)(a1 + 120) = 0;
      DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
      *(_DWORD *)(a1 + 16) = 0;
      v2 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v3 = 87;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 )
    WPP_SF_d(v2[2], 21, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18007c5d0  mov     [rsp+arg_0], rbx
0x18007c5d5  mov     [rsp+arg_8], rbp
0x18007c5da  push    rdi
0x18007c5db  sub     rsp, 20h
0x18007c5df  mov     rbx, rcx
0x18007c5e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c5e9  lea     rbp, WPP_GLOBAL_Control
0x18007c5f0  cmp     rcx, rbp
0x18007c5f3  jz      short loc_18007C617
0x18007c5f5  test    byte ptr [rcx+1Ch], 1
0x18007c5f9  jz      short loc_18007C617
0x18007c5fb  mov     rcx, [rcx+10h]
0x18007c5ff  lea     r8, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids
0x18007c606  mov     edx, 14h
0x18007c60b  call    WPP_SF_
0x18007c610  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c617  test    rbx, rbx
0x18007c61a  jnz     short loc_18007C621
0x18007c61c  lea     edi, [rbx+57h]
0x18007c61f  jmp     short loc_18007C65C
0x18007c621  xor     edi, edi
0x18007c623  cmp     [rbx+10h], edi
0x18007c626  jz      short loc_18007C65C
0x18007c628  mov     rcx, rbx
0x18007c62b  call    SMStopStateMachine
0x18007c630  mov     rcx, [rbx+78h]; Timer
0x18007c634  test    rcx, rcx
0x18007c637  jz      short loc_18007C63E
0x18007c639  call    TmDeleteTimer
0x18007c63e  lea     rcx, [rbx+18h]; lpCriticalSection
0x18007c642  mov     [rbx+78h], rdi
0x18007c646  call    cs:__imp_DeleteCriticalSection
0x18007c64d  nop     dword ptr [rax+rax+00h]
0x18007c652  mov     [rbx+10h], edi
0x18007c655  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c65c  cmp     rcx, rbp
0x18007c65f  jz      short loc_18007C67F
0x18007c661  test    byte ptr [rcx+1Ch], 1
0x18007c665  jz      short loc_18007C67F
0x18007c667  mov     rcx, [rcx+10h]
0x18007c66b  lea     r8, WPP_43dc2e3beb123d1ba4eafe48e18623e5_Traceguids
0x18007c672  mov     edx, 15h
0x18007c677  mov     r9d, edi
0x18007c67a  call    WPP_SF_d
0x18007c67f  mov     rbx, [rsp+28h+arg_0]
0x18007c684  mov     eax, edi
0x18007c686  mov     rbp, [rsp+28h+arg_8]
0x18007c68b  add     rsp, 20h
0x18007c68f  pop     rdi
0x18007c690  retn
```

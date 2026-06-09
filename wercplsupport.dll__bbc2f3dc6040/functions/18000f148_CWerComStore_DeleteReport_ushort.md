# CWerComStore::_DeleteReport(ushort *)

- ea: `0x18000f148`
- end: `0x18000f1f8`
- name: `?_DeleteReport@CWerComStore@@QEAAJPEAG@Z`
- size: `176`
- prototype: `__int64 __fastcall(CWerComStore *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a7a0`

## callees

- `0x180006c9c`
- `0x18000e3fc`
- `0x18000f148`

## import_xrefs

- `wer!WerpDeleteReport` at `0x18000f1c8`
- `wer!WerpDeleteReport` at `0x18000f1c8`

## pseudocode

```c
__int64 __fastcall CWerComStore::_DeleteReport(CWerComStore *this, unsigned __int16 *a2)
{
  int WerStoreApiLock; // ebx
  unsigned int v6; // edx
  __int64 v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  WerStoreApiLock = CWerStoreApiAutoLock::TryGetWerStoreApiLock((CWerStoreApiAutoLock *)&v7, this);
  if ( WerStoreApiLock >= 0 )
  {
    if ( a2 )
      v6 = WerpDeleteReport(*((_QWORD *)this + 4), a2);
    else
      v6 = -2147024809;
    if ( v7 )
      _InterlockedExchange((volatile __int32 *)(v7 + 40), 0);
    return v6;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids,
        (unsigned int)WerStoreApiLock);
    if ( v7 )
      _InterlockedExchange((volatile __int32 *)(v7 + 40), 0);
    return (unsigned int)WerStoreApiLock;
  }
}

```

## disassembly

```asm
0x18000f148  mov     rax, rsp
0x18000f14b  mov     [rax+8], rbx
0x18000f14f  mov     [rax+10h], rsi
0x18000f153  push    rdi
0x18000f154  sub     rsp, 20h
0x18000f158  mov     rdi, rdx
0x18000f15b  mov     qword ptr [rax+18h], 0
0x18000f163  mov     rdx, rcx; struct CWerComStore *
0x18000f166  mov     rsi, rcx
0x18000f169  lea     rcx, [rax+18h]; this
0x18000f16d  call    ?TryGetWerStoreApiLock@CWerStoreApiAutoLock@@QEAAJPEAVCWerComStore@@@Z; CWerStoreApiAutoLock::TryGetWerStoreApiLock(CWerComStore *)
0x18000f172  mov     ebx, eax
0x18000f174  test    eax, eax
0x18000f176  jns     short loc_18000F1BC
0x18000f178  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f17f  lea     rax, WPP_GLOBAL_Control
0x18000f186  cmp     rcx, rax
0x18000f189  jz      short loc_18000F1A9
0x18000f18b  test    byte ptr [rcx+1Ch], 1
0x18000f18f  jz      short loc_18000F1A9
0x18000f191  mov     rcx, [rcx+10h]
0x18000f195  lea     r8, WPP_132f0e6ae0033c985ddb49c0ccaaa1a1_Traceguids
0x18000f19c  mov     edx, 58h ; 'X'
0x18000f1a1  mov     r9d, ebx
0x18000f1a4  call    WPP_SF_d
0x18000f1a9  mov     rax, [rsp+28h+arg_10]
0x18000f1ae  test    rax, rax
0x18000f1b1  jz      short loc_18000F1B8
0x18000f1b3  xor     ecx, ecx
0x18000f1b5  xchg    ecx, [rax+28h]
0x18000f1b8  mov     eax, ebx
0x18000f1ba  jmp     short loc_18000F1E8
0x18000f1bc  test    rdi, rdi
0x18000f1bf  jz      short loc_18000F1D2
0x18000f1c1  mov     rcx, [rsi+20h]
0x18000f1c5  mov     rdx, rdi
0x18000f1c8  call    cs:__imp_WerpDeleteReport
0x18000f1ce  mov     edx, eax
0x18000f1d0  jmp     short loc_18000F1D7
0x18000f1d2  mov     edx, 80070057h
0x18000f1d7  mov     rax, [rsp+28h+arg_10]
0x18000f1dc  test    rax, rax
0x18000f1df  jz      short loc_18000F1E6
0x18000f1e1  xor     ecx, ecx
0x18000f1e3  xchg    ecx, [rax+28h]
0x18000f1e6  mov     eax, edx
0x18000f1e8  mov     rbx, [rsp+28h+arg_0]
0x18000f1ed  mov     rsi, [rsp+28h+arg_8]
0x18000f1f2  add     rsp, 20h
0x18000f1f6  pop     rdi
0x18000f1f7  retn
```

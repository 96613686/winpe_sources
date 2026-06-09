# PipeEvtChannelOpened

- ea: `0x140015d70`
- end: `0x140015f42`
- name: `PipeEvtChannelOpened`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1400155e0`
- `0x140015d70`
- `0x140017000`
- `0x140017540`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015f0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015f0e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e5f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015e5f`
- `vmbkmcl!VmbChannelGetOfferData` at `0x140015e74`
- `vmbkmcl!VmbChannelGetOfferData` at `0x140015e74`
- `vmbkmcl!VmbChannelGetPointer` at `0x140015dc0`
- `vmbkmcl!VmbChannelGetPointer` at `0x140015dc0`
- `vmbkmcl!VmbChannelGetRingBuffer` at `0x140015de7`
- `vmbkmcl!VmbChannelGetRingBuffer` at `0x140015de7`

## pseudocode

```c
__int64 __fastcall PipeEvtChannelOpened(__int64 a1)
{
  __int64 Pointer; // rdi
  __int64 result; // rax
  KIRQL v4; // bl
  int v5; // [rsp+40h] [rbp-69h] BYREF
  int v6; // [rsp+44h] [rbp-65h] BYREF
  __int64 v7; // [rsp+48h] [rbp-61h] BYREF
  __int64 v8; // [rsp+50h] [rbp-59h] BYREF
  _DWORD v9[32]; // [rsp+60h] [rbp-49h] BYREF

  v8 = 0;
  v6 = 0;
  v7 = 0;
  v5 = 0;
  memset(v9, 0, 0x78u);
  Pointer = VmbChannelGetPointer(a1);
  VmbChannelGetRingBuffer(a1, &v8, &v6, &v7, &v5);
  result = PkInitializeRingBuffer((void *)(Pointer + 64), v7, v7 + 4096, v5 - 1);
  if ( (int)result >= 0 )
  {
    if ( *(_BYTE *)(Pointer + 274) )
    {
      *(_QWORD *)(Pointer + 336) = Pointer;
      *(_QWORD *)(Pointer + 328) = PipeIndicationWorkItemRoutine;
      *(_QWORD *)(Pointer + 312) = 0;
    }
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Pointer);
    VmbChannelGetOfferData(a1, v9);
    if ( v9[0] )
    {
      if ( v9[0] == 4 )
      {
        *(_WORD *)(Pointer + 272) = 1;
      }
      else if ( v9[0] == 8 )
      {
        *(_WORD *)(Pointer + 272) = 0;
      }
    }
    else
    {
      *(_WORD *)(Pointer + 272) = 257;
    }
    if ( (v9[29] & 1) != 0 )
    {
      *(_BYTE *)(Pointer + 275) = 1;
      *(_QWORD *)(Pointer + 408) = 1937072726;
      *(_QWORD *)(Pointer + 424) = 0;
      *(_QWORD *)(Pointer + 432) = 0;
      *(_DWORD *)(Pointer + 404) = 0x2000;
      *(_QWORD *)(Pointer + 392) = Pointer + 424;
      *(_QWORD *)(Pointer + 416) = 64;
      *(_DWORD *)(Pointer + 400) = 1;
    }
    *(_DWORD *)(Pointer + 8) = 3;
    KeReleaseSpinLock((PKSPIN_LOCK)Pointer, v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140015d70  mov     [rsp-8+arg_8], rbx
0x140015d75  mov     [rsp-8+arg_10], rsi
0x140015d7a  push    rbp
0x140015d7b  push    rdi
0x140015d7c  push    r14
0x140015d7e  lea     rbp, [rsp-47h]
0x140015d83  sub     rsp, 0F0h
0x140015d8a  mov     rax, cs:__security_cookie
0x140015d91  xor     rax, rsp
0x140015d94  mov     [rbp+57h+var_20], rax
0x140015d98  xor     r14d, r14d
0x140015d9b  mov     rsi, rcx
0x140015d9e  xor     edx, edx; Val
0x140015da0  mov     [rbp+57h+var_B0], r14
0x140015da4  lea     rcx, [rbp+57h+var_A0]; void *
0x140015da8  mov     [rbp+57h+var_BC], r14d
0x140015dac  mov     [rbp+57h+var_B8], r14
0x140015db0  lea     r8d, [r14+78h]; Size
0x140015db4  mov     [rbp+57h+var_C0], r14d
0x140015db8  call    memset
0x140015dbd  mov     rcx, rsi
0x140015dc0  call    cs:__imp_VmbChannelGetPointer
0x140015dc7  nop     dword ptr [rax+rax+00h]
0x140015dcc  lea     r9, [rbp+57h+var_B8]
0x140015dd0  mov     rcx, rsi
0x140015dd3  mov     rdi, rax
0x140015dd6  lea     r8, [rbp+57h+var_BC]
0x140015dda  lea     rax, [rbp+57h+var_C0]
0x140015dde  lea     rdx, [rbp+57h+var_B0]
0x140015de2  mov     [rsp+100h+var_E0], rax
0x140015de7  call    cs:__imp_VmbChannelGetRingBuffer
0x140015dee  nop     dword ptr [rax+rax+00h]
0x140015df3  mov     rbx, [rbp+57h+var_B8]
0x140015df7  lea     rcx, [rdi+40h]; void *
0x140015dfb  mov     r11d, [rbp+57h+var_C0]
0x140015dff  mov     rdx, [rbp+57h+var_B0]
0x140015e03  dec     r11d
0x140015e06  mov     r9d, [rbp+57h+var_BC]
0x140015e0a  mov     [rsp+100h+var_D0], r11d; int
0x140015e0f  lea     r10, [rbx+1000h]
0x140015e16  mov     [rsp+100h+var_D8], r10; __int64
0x140015e1b  dec     r9d
0x140015e1e  lea     r8, [rdx+1000h]
0x140015e25  mov     [rsp+100h+var_E0], rbx; __int64
0x140015e2a  call    PkInitializeRingBuffer
0x140015e2f  test    eax, eax
0x140015e31  js      loc_140015F1D
0x140015e37  cmp     [rdi+112h], r14b
0x140015e3e  jz      short loc_140015E5C
0x140015e40  lea     rax, PipeIndicationWorkItemRoutine
0x140015e47  mov     [rdi+150h], rdi
0x140015e4e  mov     [rdi+148h], rax
0x140015e55  mov     [rdi+138h], r14
0x140015e5c  mov     rcx, rdi; SpinLock
0x140015e5f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015e66  nop     dword ptr [rax+rax+00h]
0x140015e6b  lea     rdx, [rbp+57h+var_A0]
0x140015e6f  mov     rcx, rsi
0x140015e72  mov     bl, al
0x140015e74  call    cs:__imp_VmbChannelGetOfferData
0x140015e7b  nop     dword ptr [rax+rax+00h]
0x140015e80  mov     ecx, [rbp+57h+var_A0]
0x140015e83  test    ecx, ecx
0x140015e85  jz      short loc_140015EA6
0x140015e87  cmp     ecx, 4
0x140015e8a  jz      short loc_140015E9B
0x140015e8c  cmp     ecx, 8
0x140015e8f  jnz     short loc_140015EAF
0x140015e91  mov     [rdi+110h], r14w
0x140015e99  jmp     short loc_140015EAF
0x140015e9b  mov     word ptr [rdi+110h], 1
0x140015ea4  jmp     short loc_140015EAF
0x140015ea6  mov     word ptr [rdi+110h], 101h
0x140015eaf  test    [rbp+57h+var_2C], 1
0x140015eb3  jz      short loc_140015F02
0x140015eb5  mov     byte ptr [rdi+113h], 1
0x140015ebc  lea     rax, [rdi+1A8h]
0x140015ec3  mov     qword ptr [rdi+198h], 73756256h
0x140015ece  mov     [rdi+1A8h], r14
0x140015ed5  mov     [rdi+1B0h], r14
0x140015edc  mov     dword ptr [rdi+194h], 2000h
0x140015ee6  mov     [rdi+188h], rax
0x140015eed  mov     qword ptr [rdi+1A0h], 40h ; '@'
0x140015ef8  mov     dword ptr [rdi+190h], 1
0x140015f02  mov     dl, bl; NewIrql
0x140015f04  mov     dword ptr [rdi+8], 3
0x140015f0b  mov     rcx, rdi; SpinLock
0x140015f0e  call    cs:__imp_KeReleaseSpinLock
0x140015f15  nop     dword ptr [rax+rax+00h]
0x140015f1a  mov     eax, r14d
0x140015f1d  mov     rcx, [rbp+57h+var_20]
0x140015f21  xor     rcx, rsp; StackCookie
0x140015f24  call    __security_check_cookie
0x140015f29  lea     r11, [rsp+100h+var_10]
0x140015f31  mov     rbx, [r11+28h]
0x140015f35  mov     rsi, [r11+30h]
0x140015f39  mov     rsp, r11
0x140015f3c  pop     r14
0x140015f3e  pop     rdi
0x140015f3f  pop     rbp
0x140015f40  retn
```

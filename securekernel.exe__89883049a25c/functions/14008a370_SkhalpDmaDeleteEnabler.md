# SkhalpDmaDeleteEnabler

- ea: `0x14008a370`
- end: `0x14008a50a`
- name: `SkhalpDmaDeleteEnabler`
- size: `410`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140002900`
- `0x14000b084`
- `0x1400119c4`
- `0x14008a14c`
- `0x14008a370`
- `0x14008e2e0`
- `0x140095cd8`
- `0x14009ccc4`
- `0x1400b3b28`

## pseudocode

```c
void __fastcall SkhalpDmaDeleteEnabler(_QWORD *a1)
{
  _QWORD *StackBase; // rcx
  __int64 v3; // rcx
  __int64 v4; // rdx
  _QWORD *v5; // rax
  char v6; // di
  __int64 v7; // r8
  __int64 v8; // r9
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v12; // esi
  _DWORD *DmaTarget; // rax
  int v14; // eax
  int v15; // eax
  char v16; // [rsp+50h] [rbp+8h] BYREF

  v16 = 0;
  if ( a1[2] )
  {
    SkhalpLaFreeAddressState(a1 + 6);
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( StackBase )
    {
      v3 = StackBase[18];
      if ( v3 )
        --*(_WORD *)(v3 + xmmword_140167150);
    }
    SkAcquirePushLockExclusive(&SkhalpDmaEnablerListLock);
    v4 = *a1;
    if ( *(_QWORD **)(*a1 + 8LL) != a1 || (v5 = (_QWORD *)a1[1], (_QWORD *)*v5 != a1) )
      __fastfail(3u);
    *v5 = v4;
    *(_QWORD *)(v4 + 8) = v5;
    v6 = 0;
    RtlReleaseSRWLockExclusive(&SkhalpDmaEnablerListLock);
    v9 = KeGetPcr()->NtTib.StackBase;
    if ( v9 )
    {
      v10 = v9[18];
      if ( v10 )
      {
        if ( (*(_WORD *)(v10 + xmmword_140167150))++ == 0xFFFF
          && *(_QWORD *)(v10 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v9[17]
          && !*(_WORD *)(v10 + *((_QWORD *)&xmmword_140167150 + 1)) )
        {
          SkiCheckForKernelApcDelivery(xmmword_140167160, v10, v7, v8);
        }
      }
    }
    v12 = 0;
    DmaTarget = (_DWORD *)SkpnpDeviceNodeGetDmaTarget(a1[2], 0, &v16);
    if ( !DmaTarget )
      goto LABEL_20;
    do
    {
      if ( *DmaTarget == 3 )
      {
        v6 = 1;
      }
      else if ( v16 )
      {
        v14 = SkhalDmaDetachDevice(DmaTarget);
        if ( v14 < 0 )
          SkeBugCheckEx(0x1D9u, 2u, v14, (ULONG_PTR)(a1 + 3), 0);
      }
      DmaTarget = (_DWORD *)SkpnpDeviceNodeGetDmaTarget(a1[2], (unsigned int)++v12, &v16);
    }
    while ( DmaTarget );
    if ( !v6 )
    {
LABEL_20:
      v15 = ShvlDeleteDeviceDomain(a1[3]);
      if ( v15 < 0 )
        SkeBugCheckEx(0x1D9u, 0, v15, (ULONG_PTR)(a1 + 3), 0);
    }
  }
}

```

## disassembly

```asm
0x14008a370  mov     [rsp+arg_10], rbx
0x14008a375  mov     [rsp+arg_18], rbp
0x14008a37a  push    rsi
0x14008a37b  push    rdi
0x14008a37c  push    r14
0x14008a37e  sub     rsp, 30h
0x14008a382  xor     ebp, ebp
0x14008a384  mov     rbx, rcx
0x14008a387  mov     [rsp+48h+arg_0], bpl
0x14008a38c  cmp     [rcx+10h], rbp
0x14008a390  jz      loc_14008A4C1
0x14008a396  add     rcx, 30h ; '0'
0x14008a39a  call    SkhalpLaFreeAddressState
0x14008a39f  mov     rcx, gs:8
0x14008a3a8  test    rcx, rcx
0x14008a3ab  jz      short loc_14008A3C5
0x14008a3ad  mov     rcx, [rcx+90h]
0x14008a3b4  test    rcx, rcx
0x14008a3b7  jz      short loc_14008A3C5
0x14008a3b9  mov     rax, qword ptr cs:xmmword_140167150
0x14008a3c0  dec     word ptr [rcx+rax]
0x14008a3c4  nop
0x14008a3c5  lea     rcx, SkhalpDmaEnablerListLock
0x14008a3cc  call    SkAcquirePushLockExclusive
0x14008a3d1  mov     rdx, [rbx]
0x14008a3d4  cmp     [rdx+8], rbx
0x14008a3d8  jnz     loc_14008A4BA
0x14008a3de  mov     rax, [rbx+8]
0x14008a3e2  cmp     [rax], rbx
0x14008a3e5  jnz     loc_14008A4BA
0x14008a3eb  mov     [rax], rdx
0x14008a3ee  lea     rcx, SkhalpDmaEnablerListLock
0x14008a3f5  mov     [rdx+8], rax
0x14008a3f9  mov     dil, bpl
0x14008a3fc  call    RtlReleaseSRWLockExclusive
0x14008a401  mov     rcx, gs:8
0x14008a40a  mov     r14d, 1
0x14008a410  test    rcx, rcx
0x14008a413  jz      short loc_14008A45A
0x14008a415  mov     rdx, [rcx+90h]
0x14008a41c  test    rdx, rdx
0x14008a41f  jz      short loc_14008A45A
0x14008a421  nop
0x14008a422  mov     rax, qword ptr cs:xmmword_140167150
0x14008a429  add     [rdx+rax], r14w
0x14008a42e  jnz     short loc_14008A45A
0x14008a430  mov     rax, [rcx+88h]
0x14008a437  nop
0x14008a438  mov     rcx, qword ptr cs:xmmword_140167160
0x14008a43f  add     rax, rcx
0x14008a442  cmp     [rdx+rcx], rax
0x14008a446  jz      short loc_14008A45A
0x14008a448  mov     rax, qword ptr cs:xmmword_140167150+8
0x14008a44f  cmp     [rdx+rax], bp
0x14008a453  jnz     short loc_14008A45A
0x14008a455  call    SkiCheckForKernelApcDelivery
0x14008a45a  mov     rcx, [rbx+10h]
0x14008a45e  lea     r8, [rsp+48h+arg_0]
0x14008a463  xor     edx, edx
0x14008a465  mov     esi, ebp
0x14008a467  call    SkpnpDeviceNodeGetDmaTarget
0x14008a46c  test    rax, rax
0x14008a46f  jz      short loc_14008A4AB
0x14008a471  cmp     dword ptr [rax], 3
0x14008a474  jnz     short loc_14008A47B
0x14008a476  mov     dil, r14b
0x14008a479  jmp     short loc_14008A48E
0x14008a47b  cmp     [rsp+48h+arg_0], bpl
0x14008a480  jz      short loc_14008A48E
0x14008a482  mov     rcx, rax
0x14008a485  call    SkhalDmaDetachDevice
0x14008a48a  test    eax, eax
0x14008a48c  js      short loc_14008A4EE
0x14008a48e  mov     rcx, [rbx+10h]
0x14008a492  lea     r8, [rsp+48h+arg_0]
0x14008a497  add     esi, r14d
0x14008a49a  mov     edx, esi
0x14008a49c  call    SkpnpDeviceNodeGetDmaTarget
0x14008a4a1  test    rax, rax
0x14008a4a4  jnz     short loc_14008A471
0x14008a4a6  test    dil, dil
0x14008a4a9  jnz     short loc_14008A4C1
0x14008a4ab  mov     rcx, [rbx+18h]
0x14008a4af  call    ShvlDeleteDeviceDomain
0x14008a4b4  test    eax, eax
0x14008a4b6  js      short loc_14008A4D5
0x14008a4b8  jmp     short loc_14008A4C1
0x14008a4ba  mov     ecx, 3
0x14008a4bf  int     29h; Win8: RtlFailFast(ecx)
0x14008a4c1  mov     rbx, [rsp+48h+arg_10]
0x14008a4c6  mov     rbp, [rsp+48h+arg_18]
0x14008a4cb  add     rsp, 30h
0x14008a4cf  pop     r14
0x14008a4d1  pop     rdi
0x14008a4d2  pop     rsi
0x14008a4d3  retn
0x14008a4d5  movsxd  r8, eax; BugCheckParameter2
0x14008a4d8  lea     r9, [rbx+18h]; BugCheckParameter3
0x14008a4dc  xor     edx, edx; BugCheckParameter1
0x14008a4de  mov     [rsp+48h+BugCheckParameter4], rbp; BugCheckParameter4
0x14008a4e3  mov     ecx, 1D9h; BugCheckCode
0x14008a4e8  call    SkeBugCheckEx
0x14008a4ee  lea     r9, [rbx+18h]; BugCheckParameter3
0x14008a4f2  movsxd  r8, eax; BugCheckParameter2
0x14008a4f5  mov     edx, 2; BugCheckParameter1
0x14008a4fa  mov     [rsp+48h+BugCheckParameter4], rbp; BugCheckParameter4
0x14008a4ff  mov     ecx, 1D9h; BugCheckCode
0x14008a504  call    SkeBugCheckEx
```

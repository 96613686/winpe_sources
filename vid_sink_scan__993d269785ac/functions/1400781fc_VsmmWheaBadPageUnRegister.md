# VsmmWheaBadPageUnRegister

- ea: `0x1400781fc`
- end: `0x14007831b`
- name: `VsmmWheaBadPageUnRegister`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140029340`

## callees

- `0x140030790`
- `0x1400307d0`
- `0x1400781fc`
- `0x140078454`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x14007828b`
- `ntoskrnl!RtlRbRemoveNode` at `0x14007828b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007829f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007829f`

## pseudocode

```c
char __fastcall VsmmWheaBadPageUnRegister(unsigned __int64 a1)
{
  __int64 v2; // r8
  unsigned __int64 v3; // rdi
  unsigned __int64 v4; // rbx
  int v5; // esi
  int v6; // eax
  unsigned __int64 v7; // rax
  char result; // al
  unsigned __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = a1;
  VidLockAcquireExclusive((char *)VidDeviceExtension + 1864);
  v3 = (unsigned __int64)VidDeviceExtension + 1848;
  v4 = *((_QWORD *)VidDeviceExtension + 231);
  if ( (*((_BYTE *)VidDeviceExtension + 1856) & 1) != 0 && v4 )
    v4 ^= v3;
  v5 = *((_BYTE *)VidDeviceExtension + 1856) & 1;
  if ( !v4 )
    goto LABEL_16;
  do
  {
    v6 = VsmmWheapBadPageTableNodeCompare(&v9, v4, v2);
    if ( v6 >= 0 )
    {
      if ( v6 <= 0 )
        break;
      v7 = *(_QWORD *)(v4 + 8);
    }
    else
    {
      v7 = *(_QWORD *)v4;
    }
    if ( v5 && v7 )
      v4 ^= v7;
    else
      v4 = v7;
  }
  while ( v4 );
  if ( v4 )
  {
    RtlRbRemoveNode(v3, v4);
    ExFreePoolWithTag((PVOID)v4, 0x6D4D6456u);
    --*((_QWORD *)VidDeviceExtension + 234);
    _bittestandreset64(*((signed __int64 **)VidDeviceExtension + 235), a1 >> 18);
    VidLockRelease((char *)VidDeviceExtension + 1864);
    result = 1;
    _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)VidDeviceExtension + 45) + 336LL));
  }
  else
  {
LABEL_16:
    VidLockRelease((char *)VidDeviceExtension + 1864);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400781fc  mov     [rsp+arg_0], rcx
0x140078201  push    rbx
0x140078202  push    rbp
0x140078203  push    rsi
0x140078204  push    rdi
0x140078205  sub     rsp, 28h
0x140078209  mov     rbp, rcx
0x14007820c  mov     rcx, cs:VidDeviceExtension
0x140078213  add     rcx, 748h
0x14007821a  call    VidLockAcquireExclusive
0x14007821f  mov     rdi, cs:VidDeviceExtension
0x140078226  add     rdi, 738h
0x14007822d  test    byte ptr [rdi+8], 1
0x140078231  mov     rbx, [rdi]
0x140078234  jz      short loc_14007823E
0x140078236  test    rbx, rbx
0x140078239  jz      short loc_14007823E
0x14007823b  xor     rbx, rdi
0x14007823e  movzx   esi, byte ptr [rdi+8]
0x140078242  and     esi, 1
0x140078245  test    rbx, rbx
0x140078248  jz      loc_1400782FC
0x14007824e  mov     rdx, rbx
0x140078251  lea     rcx, [rsp+48h+arg_0]
0x140078256  call    VsmmWheapBadPageTableNodeCompare
0x14007825b  test    eax, eax
0x14007825d  jns     short loc_140078264
0x14007825f  mov     rax, [rbx]
0x140078262  jmp     short loc_14007826A
0x140078264  jle     short loc_140078280
0x140078266  mov     rax, [rbx+8]
0x14007826a  test    esi, esi
0x14007826c  jz      short loc_140078278
0x14007826e  test    rax, rax
0x140078271  jz      short loc_140078278
0x140078273  xor     rbx, rax
0x140078276  jmp     short loc_14007827B
0x140078278  mov     rbx, rax
0x14007827b  test    rbx, rbx
0x14007827e  jnz     short loc_14007824E
0x140078280  test    rbx, rbx
0x140078283  jz      short loc_1400782FC
0x140078285  mov     rdx, rbx
0x140078288  mov     rcx, rdi
0x14007828b  call    cs:__imp_RtlRbRemoveNode
0x140078292  nop     dword ptr [rax+rax+00h]
0x140078297  mov     edx, 6D4D6456h; Tag
0x14007829c  mov     rcx, rbx; P
0x14007829f  call    cs:__imp_ExFreePoolWithTag
0x1400782a6  nop     dword ptr [rax+rax+00h]
0x1400782ab  mov     rax, cs:VidDeviceExtension
0x1400782b2  shr     rbp, 12h
0x1400782b6  dec     qword ptr [rax+750h]
0x1400782bd  mov     rcx, cs:VidDeviceExtension
0x1400782c4  mov     rdx, [rcx+758h]
0x1400782cb  btr     [rdx], rbp
0x1400782cf  mov     rcx, cs:VidDeviceExtension
0x1400782d6  add     rcx, 748h
0x1400782dd  call    VidLockRelease
0x1400782e2  mov     rcx, cs:VidDeviceExtension
0x1400782e9  mov     al, 1
0x1400782eb  mov     rdx, [rcx+168h]
0x1400782f2  lock dec qword ptr [rdx+150h]
0x1400782fa  jmp     short loc_140078311
0x1400782fc  mov     rcx, cs:VidDeviceExtension
0x140078303  add     rcx, 748h
0x14007830a  call    VidLockRelease
0x14007830f  xor     al, al
0x140078311  add     rsp, 28h
0x140078315  pop     rdi
0x140078316  pop     rsi
0x140078317  pop     rbp
0x140078318  pop     rbx
0x140078319  retn
```

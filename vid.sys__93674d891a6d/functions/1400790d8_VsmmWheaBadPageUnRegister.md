# VsmmWheaBadPageUnRegister

- ea: `0x1400790d8`
- end: `0x1400791f7`
- name: `VsmmWheaBadPageUnRegister`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400294f0`

## callees

- `0x140030990`
- `0x1400309d0`
- `0x1400790d8`
- `0x140079330`

## import_xrefs

- `ntoskrnl!RtlRbRemoveNode` at `0x140079167`
- `ntoskrnl!RtlRbRemoveNode` at `0x140079167`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007917b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007917b`

## pseudocode

```c
char __fastcall VsmmWheaBadPageUnRegister(unsigned __int64 a1)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // rbx
  int v4; // esi
  int v5; // eax
  unsigned __int64 v6; // rax
  char result; // al
  unsigned __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  v8 = a1;
  VidLockAcquireExclusive((char *)VidDeviceExtension + 1864);
  v2 = (unsigned __int64)VidDeviceExtension + 1848;
  v3 = *((_QWORD *)VidDeviceExtension + 231);
  if ( (*((_BYTE *)VidDeviceExtension + 1856) & 1) != 0 && v3 )
    v3 ^= v2;
  v4 = *((_BYTE *)VidDeviceExtension + 1856) & 1;
  if ( !v3 )
    goto LABEL_16;
  do
  {
    v5 = VsmmWheapBadPageTableNodeCompare(&v8, v3);
    if ( v5 >= 0 )
    {
      if ( v5 <= 0 )
        break;
      v6 = *(_QWORD *)(v3 + 8);
    }
    else
    {
      v6 = *(_QWORD *)v3;
    }
    if ( v4 && v6 )
      v3 ^= v6;
    else
      v3 = v6;
  }
  while ( v3 );
  if ( v3 )
  {
    RtlRbRemoveNode(v2, v3);
    ExFreePoolWithTag((PVOID)v3, 0x6D4D6456u);
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
0x1400790d8  mov     [rsp+arg_0], rcx
0x1400790dd  push    rbx
0x1400790de  push    rbp
0x1400790df  push    rsi
0x1400790e0  push    rdi
0x1400790e1  sub     rsp, 28h
0x1400790e5  mov     rbp, rcx
0x1400790e8  mov     rcx, cs:VidDeviceExtension
0x1400790ef  add     rcx, 748h
0x1400790f6  call    VidLockAcquireExclusive
0x1400790fb  mov     rdi, cs:VidDeviceExtension
0x140079102  add     rdi, 738h
0x140079109  test    byte ptr [rdi+8], 1
0x14007910d  mov     rbx, [rdi]
0x140079110  jz      short loc_14007911A
0x140079112  test    rbx, rbx
0x140079115  jz      short loc_14007911A
0x140079117  xor     rbx, rdi
0x14007911a  movzx   esi, byte ptr [rdi+8]
0x14007911e  and     esi, 1
0x140079121  test    rbx, rbx
0x140079124  jz      loc_1400791D8
0x14007912a  mov     rdx, rbx
0x14007912d  lea     rcx, [rsp+48h+arg_0]
0x140079132  call    VsmmWheapBadPageTableNodeCompare
0x140079137  test    eax, eax
0x140079139  jns     short loc_140079140
0x14007913b  mov     rax, [rbx]
0x14007913e  jmp     short loc_140079146
0x140079140  jle     short loc_14007915C
0x140079142  mov     rax, [rbx+8]
0x140079146  test    esi, esi
0x140079148  jz      short loc_140079154
0x14007914a  test    rax, rax
0x14007914d  jz      short loc_140079154
0x14007914f  xor     rbx, rax
0x140079152  jmp     short loc_140079157
0x140079154  mov     rbx, rax
0x140079157  test    rbx, rbx
0x14007915a  jnz     short loc_14007912A
0x14007915c  test    rbx, rbx
0x14007915f  jz      short loc_1400791D8
0x140079161  mov     rdx, rbx
0x140079164  mov     rcx, rdi
0x140079167  call    cs:__imp_RtlRbRemoveNode
0x14007916e  nop     dword ptr [rax+rax+00h]
0x140079173  mov     edx, 6D4D6456h; Tag
0x140079178  mov     rcx, rbx; P
0x14007917b  call    cs:__imp_ExFreePoolWithTag
0x140079182  nop     dword ptr [rax+rax+00h]
0x140079187  mov     rax, cs:VidDeviceExtension
0x14007918e  shr     rbp, 12h
0x140079192  dec     qword ptr [rax+750h]
0x140079199  mov     rcx, cs:VidDeviceExtension
0x1400791a0  mov     rdx, [rcx+758h]
0x1400791a7  btr     [rdx], rbp
0x1400791ab  mov     rcx, cs:VidDeviceExtension
0x1400791b2  add     rcx, 748h
0x1400791b9  call    VidLockRelease
0x1400791be  mov     rcx, cs:VidDeviceExtension
0x1400791c5  mov     al, 1
0x1400791c7  mov     rdx, [rcx+168h]
0x1400791ce  lock dec qword ptr [rdx+150h]
0x1400791d6  jmp     short loc_1400791ED
0x1400791d8  mov     rcx, cs:VidDeviceExtension
0x1400791df  add     rcx, 748h
0x1400791e6  call    VidLockRelease
0x1400791eb  xor     al, al
0x1400791ed  add     rsp, 28h
0x1400791f1  pop     rdi
0x1400791f2  pop     rsi
0x1400791f3  pop     rbp
0x1400791f4  pop     rbx
0x1400791f5  retn
```

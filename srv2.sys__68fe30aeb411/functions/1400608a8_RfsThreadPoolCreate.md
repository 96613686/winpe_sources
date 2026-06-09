# RfsThreadPoolCreate

- ea: `0x1400608a8`
- end: `0x140060a36`
- name: `RfsThreadPoolCreate`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005ddbc`

## callees

- `0x140038490`
- `0x1400607d8`
- `0x1400608a8`
- `0x140091e6c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140060912`
- `ntoskrnl!ExAllocatePool2` at `0x14006093d`
- `ntoskrnl!ExAllocatePool2` at `0x140060912`
- `ntoskrnl!ExAllocatePool2` at `0x14006093d`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400608cf`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x1400608cf`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400609a1`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400609a1`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400609c0`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400609c0`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x1400609f2`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x1400609f2`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140060981`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x140060981`

## pseudocode

```c
__int64 __fastcall RfsThreadPoolCreate(_QWORD *a1, _OWORD *a2)
{
  USHORT HighestNodeNumber; // ax
  USHORT v5; // bp
  _QWORD *Pool2; // rsi
  _OWORD *v8; // rax
  int v9; // ebx
  USHORT v10; // di
  __int128 v11; // xmm1
  USHORT Count; // [rsp+20h] [rbp-48h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-40h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-30h] BYREF

  HighestNodeNumber = KeQueryHighestNodeNumber();
  Count = 0;
  *a1 = 0;
  v5 = HighestNodeNumber + 1;
  Affinity = 0;
  PreviousAffinity = 0;
  Pool2 = (_QWORD *)ExAllocatePool2(64, 8LL * (unsigned __int16)(HighestNodeNumber + 1) + 8, 1382437708);
  if ( !Pool2 )
    return 3221225626LL;
  v8 = (_OWORD *)ExAllocatePool2(258, 32, 1382437708);
  *Pool2 = v8;
  if ( v8 )
  {
    v10 = 0;
    v11 = a2[1];
    *v8 = *a2;
    v8[1] = v11;
    while ( v10 < v5 )
    {
      if ( KeQueryNodeMaximumProcessorCount(v10) )
      {
        KeQueryNodeActiveAffinity(v10, &Affinity, &Count);
        if ( Count )
          KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
        v9 = RfspThreadPoolNodeCreate(&Pool2[v10 + 1], *Pool2, v10);
        if ( Count )
          KeRevertToUserGroupAffinityThread(&PreviousAffinity);
        if ( v9 < 0 )
          goto LABEL_5;
      }
      ++v10;
    }
    *a1 = Pool2;
    return 0;
  }
  else
  {
    v9 = -1073741670;
LABEL_5:
    RfsThreadPoolClose(Pool2);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1400608a8  mov     [rsp+arg_8], rbx
0x1400608ad  mov     [rsp+arg_10], rbp
0x1400608b2  push    rsi
0x1400608b3  push    rdi
0x1400608b4  push    r14
0x1400608b6  sub     rsp, 50h
0x1400608ba  mov     rax, cs:__security_cookie
0x1400608c1  xor     rax, rsp
0x1400608c4  mov     [rsp+68h+var_20], rax
0x1400608c9  mov     rbx, rdx
0x1400608cc  mov     r14, rcx
0x1400608cf  call    cs:__imp_KeQueryHighestNodeNumber
0x1400608d6  nop     dword ptr [rax+rax+00h]
0x1400608db  xor     r8d, r8d
0x1400608de  xorps   xmm0, xmm0
0x1400608e1  mov     [rsp+68h+Count], r8w
0x1400608e7  xorps   xmm1, xmm1
0x1400608ea  mov     [r14], r8
0x1400608ed  mov     edi, 5266534Ch
0x1400608f2  lea     ebp, [rax+1]
0x1400608f5  mov     r8d, edi
0x1400608f8  movzx   edx, bp
0x1400608fb  mov     ecx, 40h ; '@'
0x140060900  movups  xmmword ptr [rsp+68h+Affinity.Mask], xmm0
0x140060905  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm1
0x14006090a  lea     rdx, ds:8[rdx*8]
0x140060912  call    cs:__imp_ExAllocatePool2
0x140060919  nop     dword ptr [rax+rax+00h]
0x14006091e  mov     rsi, rax
0x140060921  test    rax, rax
0x140060924  jnz     short loc_140060930
0x140060926  mov     eax, 0C000009Ah
0x14006092b  jmp     loc_140060A13
0x140060930  mov     r8d, edi
0x140060933  mov     edx, 20h ; ' '
0x140060938  mov     ecx, 102h
0x14006093d  call    cs:__imp_ExAllocatePool2
0x140060944  nop     dword ptr [rax+rax+00h]
0x140060949  mov     [rsi], rax
0x14006094c  test    rax, rax
0x14006094f  jnz     short loc_140060965
0x140060951  mov     ebx, 0C000009Ah
0x140060956  mov     rcx, rsi; P
0x140060959  call    RfsThreadPoolClose
0x14006095e  mov     eax, ebx
0x140060960  jmp     loc_140060A13
0x140060965  movups  xmm0, xmmword ptr [rbx]
0x140060968  xor     edi, edi
0x14006096a  movups  xmm1, xmmword ptr [rbx+10h]
0x14006096e  movups  xmmword ptr [rax], xmm0
0x140060971  movups  xmmword ptr [rax+10h], xmm1
0x140060975  cmp     di, bp
0x140060978  jnb     loc_140060A0E
0x14006097e  movzx   ecx, di; NodeNumber
0x140060981  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x140060988  nop     dword ptr [rax+rax+00h]
0x14006098d  xor     ecx, ecx
0x14006098f  cmp     cx, ax
0x140060992  jz      short loc_140060A06
0x140060994  lea     r8, [rsp+68h+Count]; Count
0x140060999  movzx   ecx, di; NodeNumber
0x14006099c  lea     rdx, [rsp+68h+Affinity]; Affinity
0x1400609a1  call    cs:__imp_KeQueryNodeActiveAffinity
0x1400609a8  nop     dword ptr [rax+rax+00h]
0x1400609ad  xor     eax, eax
0x1400609af  cmp     ax, [rsp+68h+Count]
0x1400609b4  jz      short loc_1400609CC
0x1400609b6  lea     rdx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x1400609bb  lea     rcx, [rsp+68h+Affinity]; Affinity
0x1400609c0  call    cs:__imp_KeSetSystemGroupAffinityThread
0x1400609c7  nop     dword ptr [rax+rax+00h]
0x1400609cc  mov     rdx, [rsi]
0x1400609cf  movzx   r8d, di
0x1400609d3  movzx   eax, di
0x1400609d6  inc     rax
0x1400609d9  lea     rcx, [rsi+rax*8]
0x1400609dd  call    RfspThreadPoolNodeCreate
0x1400609e2  xor     ecx, ecx
0x1400609e4  mov     ebx, eax
0x1400609e6  cmp     cx, [rsp+68h+Count]
0x1400609eb  jz      short loc_1400609FE
0x1400609ed  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x1400609f2  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x1400609f9  nop     dword ptr [rax+rax+00h]
0x1400609fe  test    ebx, ebx
0x140060a00  js      loc_140060956
0x140060a06  inc     di
0x140060a09  jmp     loc_140060975
0x140060a0e  mov     [r14], rsi
0x140060a11  xor     eax, eax
0x140060a13  mov     rcx, [rsp+68h+var_20]
0x140060a18  xor     rcx, rsp; StackCookie
0x140060a1b  call    __security_check_cookie
0x140060a20  lea     r11, [rsp+68h+var_18]
0x140060a25  mov     rbx, [r11+28h]
0x140060a29  mov     rbp, [r11+30h]
0x140060a2d  mov     rsp, r11
0x140060a30  pop     r14
0x140060a32  pop     rdi
0x140060a33  pop     rsi
0x140060a34  retn
```

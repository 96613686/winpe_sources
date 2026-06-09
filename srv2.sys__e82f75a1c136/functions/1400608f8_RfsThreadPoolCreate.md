# RfsThreadPoolCreate

- ea: `0x1400608f8`
- end: `0x140060a86`
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
- `0x140060828`
- `0x1400608f8`
- `0x140091e6c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140060962`
- `ntoskrnl!ExAllocatePool2` at `0x14006098d`
- `ntoskrnl!ExAllocatePool2` at `0x140060962`
- `ntoskrnl!ExAllocatePool2` at `0x14006098d`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14006091f`
- `ntoskrnl!KeQueryHighestNodeNumber` at `0x14006091f`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400609f1`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x1400609f1`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140060a10`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140060a10`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140060a42`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140060a42`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x1400609d1`
- `ntoskrnl!KeQueryNodeMaximumProcessorCount` at `0x1400609d1`

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
0x1400608f8  mov     [rsp+arg_8], rbx
0x1400608fd  mov     [rsp+arg_10], rbp
0x140060902  push    rsi
0x140060903  push    rdi
0x140060904  push    r14
0x140060906  sub     rsp, 50h
0x14006090a  mov     rax, cs:__security_cookie
0x140060911  xor     rax, rsp
0x140060914  mov     [rsp+68h+var_20], rax
0x140060919  mov     rbx, rdx
0x14006091c  mov     r14, rcx
0x14006091f  call    cs:__imp_KeQueryHighestNodeNumber
0x140060926  nop     dword ptr [rax+rax+00h]
0x14006092b  xor     r8d, r8d
0x14006092e  xorps   xmm0, xmm0
0x140060931  mov     [rsp+68h+Count], r8w
0x140060937  xorps   xmm1, xmm1
0x14006093a  mov     [r14], r8
0x14006093d  mov     edi, 5266534Ch
0x140060942  lea     ebp, [rax+1]
0x140060945  mov     r8d, edi
0x140060948  movzx   edx, bp
0x14006094b  mov     ecx, 40h ; '@'
0x140060950  movups  xmmword ptr [rsp+68h+Affinity.Mask], xmm0
0x140060955  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm1
0x14006095a  lea     rdx, ds:8[rdx*8]
0x140060962  call    cs:__imp_ExAllocatePool2
0x140060969  nop     dword ptr [rax+rax+00h]
0x14006096e  mov     rsi, rax
0x140060971  test    rax, rax
0x140060974  jnz     short loc_140060980
0x140060976  mov     eax, 0C000009Ah
0x14006097b  jmp     loc_140060A63
0x140060980  mov     r8d, edi
0x140060983  mov     edx, 20h ; ' '
0x140060988  mov     ecx, 102h
0x14006098d  call    cs:__imp_ExAllocatePool2
0x140060994  nop     dword ptr [rax+rax+00h]
0x140060999  mov     [rsi], rax
0x14006099c  test    rax, rax
0x14006099f  jnz     short loc_1400609B5
0x1400609a1  mov     ebx, 0C000009Ah
0x1400609a6  mov     rcx, rsi; P
0x1400609a9  call    RfsThreadPoolClose
0x1400609ae  mov     eax, ebx
0x1400609b0  jmp     loc_140060A63
0x1400609b5  movups  xmm0, xmmword ptr [rbx]
0x1400609b8  xor     edi, edi
0x1400609ba  movups  xmm1, xmmword ptr [rbx+10h]
0x1400609be  movups  xmmword ptr [rax], xmm0
0x1400609c1  movups  xmmword ptr [rax+10h], xmm1
0x1400609c5  cmp     di, bp
0x1400609c8  jnb     loc_140060A5E
0x1400609ce  movzx   ecx, di; NodeNumber
0x1400609d1  call    cs:__imp_KeQueryNodeMaximumProcessorCount
0x1400609d8  nop     dword ptr [rax+rax+00h]
0x1400609dd  xor     ecx, ecx
0x1400609df  cmp     cx, ax
0x1400609e2  jz      short loc_140060A56
0x1400609e4  lea     r8, [rsp+68h+Count]; Count
0x1400609e9  movzx   ecx, di; NodeNumber
0x1400609ec  lea     rdx, [rsp+68h+Affinity]; Affinity
0x1400609f1  call    cs:__imp_KeQueryNodeActiveAffinity
0x1400609f8  nop     dword ptr [rax+rax+00h]
0x1400609fd  xor     eax, eax
0x1400609ff  cmp     ax, [rsp+68h+Count]
0x140060a04  jz      short loc_140060A1C
0x140060a06  lea     rdx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x140060a0b  lea     rcx, [rsp+68h+Affinity]; Affinity
0x140060a10  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140060a17  nop     dword ptr [rax+rax+00h]
0x140060a1c  mov     rdx, [rsi]
0x140060a1f  movzx   r8d, di
0x140060a23  movzx   eax, di
0x140060a26  inc     rax
0x140060a29  lea     rcx, [rsi+rax*8]
0x140060a2d  call    RfspThreadPoolNodeCreate
0x140060a32  xor     ecx, ecx
0x140060a34  mov     ebx, eax
0x140060a36  cmp     cx, [rsp+68h+Count]
0x140060a3b  jz      short loc_140060A4E
0x140060a3d  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x140060a42  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140060a49  nop     dword ptr [rax+rax+00h]
0x140060a4e  test    ebx, ebx
0x140060a50  js      loc_1400609A6
0x140060a56  inc     di
0x140060a59  jmp     loc_1400609C5
0x140060a5e  mov     [r14], rsi
0x140060a61  xor     eax, eax
0x140060a63  mov     rcx, [rsp+68h+var_20]
0x140060a68  xor     rcx, rsp; StackCookie
0x140060a6b  call    __security_check_cookie
0x140060a70  lea     r11, [rsp+68h+var_18]
0x140060a75  mov     rbx, [r11+28h]
0x140060a79  mov     rbp, [r11+30h]
0x140060a7d  mov     rsp, r11
0x140060a80  pop     r14
0x140060a82  pop     rdi
0x140060a83  pop     rsi
0x140060a84  retn
```

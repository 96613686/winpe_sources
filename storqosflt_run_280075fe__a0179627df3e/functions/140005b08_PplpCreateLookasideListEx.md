# PplpCreateLookasideListEx

- ea: `0x140005b08`
- end: `0x140005c42`
- name: `PplpCreateLookasideListEx`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400111bc`

## callees

- `0x140005b08`

## import_xrefs

- `ntoskrnl!ExAllocatePool3` at `0x140005b4b`
- `ntoskrnl!ExAllocatePool3` at `0x140005b4b`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140005bb6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x140005bb6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005bf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005bf9`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005b7e`
- `ntoskrnl!KeInitializeSpinLock` at `0x140005b7e`

## pseudocode

```c
_DWORD *__fastcall PplpCreateLookasideListEx(int a1)
{
  int v1; // ebp
  _DWORD *Pool3; // rbx
  int i; // esi
  _DWORD *v4; // rdi
  _DWORD *result; // rax
  _QWORD v6[7]; // [rsp+40h] [rbp-38h] BYREF

  v1 = a1 + 1;
  v6[1] = 0;
  v6[0] = 1;
  Pool3 = (_DWORD *)ExAllocatePool3(72, ((unsigned __int64)(unsigned int)(a1 + 1) << 7) + 64, 1179865427, v6, 1);
  if ( !Pool3 )
    return 0;
  for ( i = 0; i < v1; ++i )
  {
    v4 = &Pool3[32 * (__int64)i];
    KeInitializeSpinLock((PKSPIN_LOCK)v4 + 21);
    if ( i )
    {
      *((_BYTE *)v4 + 176) = 0;
      *((_QWORD *)v4 + 20) = Pool3 + 16;
    }
    else
    {
      if ( ExInitializeLookasideListEx((PLOOKASIDE_LIST_EX)(v4 + 16), 0, 0, (POOL_TYPE)516, 0, 0xC0u, 0x46535153u, 0) < 0 )
      {
        ExFreePoolWithTag(Pool3, 0x46535153u);
        return 0;
      }
      *((_QWORD *)v4 + 20) = 0;
      *((_BYTE *)v4 + 176) = 1;
    }
  }
  *Pool3 = v1;
  *((_WORD *)Pool3 + 18) = 0;
  *((_QWORD *)Pool3 + 3) = 0;
  result = Pool3;
  Pool3[1] = 0;
  Pool3[2] = 1179865427;
  Pool3[3] = 1179865427;
  *((_QWORD *)Pool3 + 2) = 192;
  Pool3[8] = 516;
  return result;
}

```

## disassembly

```asm
0x140005b08  mov     rax, rsp
0x140005b0b  push    rbx
0x140005b0c  push    rbp
0x140005b0d  push    rsi
0x140005b0e  push    rdi
0x140005b0f  push    r15
0x140005b11  sub     rsp, 50h
0x140005b15  lea     ebp, [rcx+1]
0x140005b18  mov     qword ptr [rax-30h], 0
0x140005b20  mov     edx, ebp
0x140005b22  lea     r9, [rax-38h]
0x140005b26  shl     rdx, 7
0x140005b2a  mov     r15d, 46535153h
0x140005b30  add     rdx, 40h ; '@'
0x140005b34  mov     qword ptr [rax-38h], 1
0x140005b3c  mov     r8d, r15d
0x140005b3f  mov     dword ptr [rax-58h], 1
0x140005b46  mov     ecx, 48h ; 'H'
0x140005b4b  call    cs:__imp_ExAllocatePool3
0x140005b52  nop     dword ptr [rax+rax+00h]
0x140005b57  mov     rbx, rax
0x140005b5a  test    rax, rax
0x140005b5d  jz      loc_140005C05
0x140005b63  xor     esi, esi
0x140005b65  cmp     esi, ebp
0x140005b67  jge     loc_140005C13
0x140005b6d  movsxd  rdi, esi
0x140005b70  shl     rdi, 7
0x140005b74  add     rdi, rbx
0x140005b77  lea     rcx, [rdi+0A8h]; SpinLock
0x140005b7e  call    cs:__imp_KeInitializeSpinLock
0x140005b85  nop     dword ptr [rax+rax+00h]
0x140005b8a  test    esi, esi
0x140005b8c  jnz     short loc_140005BDA
0x140005b8e  xor     eax, eax
0x140005b90  lea     rcx, [rdi+40h]; Lookaside
0x140005b94  mov     [rsp+78h+Depth], ax; Depth
0x140005b99  mov     r9d, 204h; PoolType
0x140005b9f  mov     [rsp+78h+Tag], r15d; Tag
0x140005ba4  xor     r8d, r8d; Free
0x140005ba7  mov     [rsp+78h+Size], 0C0h; Size
0x140005bb0  xor     edx, edx; Allocate
0x140005bb2  mov     [rsp+78h+Flags], eax; Flags
0x140005bb6  call    cs:__imp_ExInitializeLookasideListEx
0x140005bbd  nop     dword ptr [rax+rax+00h]
0x140005bc2  test    eax, eax
0x140005bc4  js      short loc_140005BF3
0x140005bc6  mov     qword ptr [rdi+0A0h], 0
0x140005bd1  mov     byte ptr [rdi+0B0h], 1
0x140005bd8  jmp     short loc_140005BEC
0x140005bda  lea     rax, [rbx+40h]
0x140005bde  mov     byte ptr [rdi+0B0h], 0
0x140005be5  mov     [rdi+0A0h], rax
0x140005bec  inc     esi
0x140005bee  jmp     loc_140005B65
0x140005bf3  mov     edx, r15d; Tag
0x140005bf6  mov     rcx, rbx; P
0x140005bf9  call    cs:__imp_ExFreePoolWithTag
0x140005c00  nop     dword ptr [rax+rax+00h]
0x140005c05  xor     eax, eax
0x140005c07  add     rsp, 50h
0x140005c0b  pop     r15
0x140005c0d  pop     rdi
0x140005c0e  pop     rsi
0x140005c0f  pop     rbp
0x140005c10  pop     rbx
0x140005c11  retn
0x140005c13  xor     eax, eax
0x140005c15  mov     [rbx], ebp
0x140005c17  mov     [rbx+24h], ax
0x140005c1b  mov     [rbx+18h], rax
0x140005c1f  mov     rax, rbx
0x140005c22  mov     dword ptr [rbx+4], 0
0x140005c29  mov     [rbx+8], r15d
0x140005c2d  mov     [rbx+0Ch], r15d
0x140005c31  mov     qword ptr [rbx+10h], 0C0h
0x140005c39  mov     dword ptr [rbx+20h], 204h
0x140005c40  jmp     short loc_140005C07
```

# UdfLockVolumeInternal

- ea: `0x140013128`
- end: `0x14001321c`
- name: `UdfLockVolumeInternal`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14003604c`
- `0x1400375d8`

## callees

- `0x140008790`
- `0x140013128`
- `0x14004ce50`
- `0x140052864`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x14001316c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001316c`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400131ac`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x1400131ac`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013200`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140013200`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140013178`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140013178`

## pseudocode

```c
__int64 __fastcall UdfLockVolumeInternal(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // r15d
  NTSTATUS v7; // eax
  int v8; // esi
  __int64 v9; // rdx
  KIRQL Irql; // [rsp+70h] [rbp+8h] BYREF

  Irql = 0;
  v4 = a3 != 0;
  UdfFlushVolume(a1, a2, 0, 1, 1, 0);
  ExReleaseResourceLite((PERESOURCE)(a2 + 1480));
  v7 = CcWaitForCurrentLazyWriterActivity();
  *(_DWORD *)(a1 + 28) |= 4u;
  v8 = v7;
  UdfAcquireResource(a1, a2 + 1480, 0, 0);
  if ( v8 >= 0 )
  {
    UdfFspClose(a2);
    IoAcquireVpbSpinLock(&Irql);
    v9 = *(_QWORD *)(a2 + 8);
    if ( (*(_BYTE *)(v9 + 4) & 2) == 0
      && *(_DWORD *)(a2 + 252) == v4
      && *(_DWORD *)(a2 + 260) == v4 + *(_DWORD *)(a2 + 268) )
    {
      *(_DWORD *)(a2 + 48) |= 1u;
      *(_WORD *)(v9 + 4) |= 0x22u;
      *(_QWORD *)(a2 + 56) = a3;
    }
    else
    {
      v8 = a3 != 0 ? -1073741790 : -2147483631;
    }
    IoReleaseVpbSpinLock(Irql);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140013128  push    rbx
0x14001312a  push    rbp
0x14001312b  push    rsi
0x14001312c  push    rdi
0x14001312d  push    r14
0x14001312f  push    r15
0x140013131  sub     rsp, 38h
0x140013135  xor     r15d, r15d
0x140013138  mov     [rsp+68h+var_40], 0; char
0x14001313d  test    r8, r8
0x140013140  mov     [rsp+68h+Irql], 0
0x140013145  mov     r14, r8
0x140013148  mov     [rsp+68h+var_48], 1; char
0x14001314d  setnz   r15b
0x140013151  mov     r9b, 1
0x140013154  xor     r8d, r8d
0x140013157  mov     rbp, rdx
0x14001315a  mov     rdi, rcx
0x14001315d  call    UdfFlushVolume
0x140013162  lea     rbx, [rbp+5C8h]
0x140013169  mov     rcx, rbx; Resource
0x14001316c  call    cs:__imp_ExReleaseResourceLite
0x140013173  nop     dword ptr [rax+rax+00h]
0x140013178  call    cs:__imp_CcWaitForCurrentLazyWriterActivity
0x14001317f  nop     dword ptr [rax+rax+00h]
0x140013184  or      dword ptr [rdi+1Ch], 4
0x140013188  xor     r9d, r9d
0x14001318b  xor     r8d, r8d
0x14001318e  mov     rdx, rbx
0x140013191  mov     rcx, rdi
0x140013194  mov     esi, eax
0x140013196  call    UdfAcquireResource
0x14001319b  test    esi, esi
0x14001319d  js      short loc_14001320C
0x14001319f  mov     rcx, rbp
0x1400131a2  call    UdfFspClose
0x1400131a7  lea     rcx, [rsp+68h+Irql]; Irql
0x1400131ac  call    cs:__imp_IoAcquireVpbSpinLock
0x1400131b3  nop     dword ptr [rax+rax+00h]
0x1400131b8  mov     rdx, [rbp+8]
0x1400131bc  test    byte ptr [rdx+4], 2
0x1400131c0  jnz     short loc_1400131EB
0x1400131c2  cmp     [rbp+0FCh], r15d
0x1400131c9  jnz     short loc_1400131EB
0x1400131cb  mov     ecx, [rbp+10Ch]
0x1400131d1  add     ecx, r15d
0x1400131d4  cmp     [rbp+104h], ecx
0x1400131da  jnz     short loc_1400131EB
0x1400131dc  or      dword ptr [rbp+30h], 1
0x1400131e0  or      word ptr [rdx+4], 22h
0x1400131e5  mov     [rbp+38h], r14
0x1400131e9  jmp     short loc_1400131FC
0x1400131eb  neg     r14
0x1400131ee  sbb     esi, esi
0x1400131f0  and     esi, 40000011h
0x1400131f6  add     esi, 80000011h
0x1400131fc  mov     cl, [rsp+68h+Irql]; Irql
0x140013200  call    cs:__imp_IoReleaseVpbSpinLock
0x140013207  nop     dword ptr [rax+rax+00h]
0x14001320c  mov     eax, esi
0x14001320e  add     rsp, 38h
0x140013212  pop     r15
0x140013214  pop     r14
0x140013216  pop     rdi
0x140013217  pop     rsi
0x140013218  pop     rbp
0x140013219  pop     rbx
0x14001321a  retn
```

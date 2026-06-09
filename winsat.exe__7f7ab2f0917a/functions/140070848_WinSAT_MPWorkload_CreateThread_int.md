# WinSAT::MPWorkload::CreateThread(int)

- ea: `0x140070848`
- end: `0x1400708f4`
- name: `?CreateThread@MPWorkload@WinSAT@@QEAAKH@Z`
- size: `172`
- prototype: `unsigned int __fastcall(WinSAT::MPWorkload *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140071430`

## callees

- `0x140070848`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140070891`
- `KERNEL32!GetLastError` at `0x140070891`
- `KERNEL32!SetThreadIdealProcessor` at `0x1400708d1`
- `KERNEL32!SetThreadIdealProcessor` at `0x1400708d1`
- `KERNEL32!SetThreadAffinityMask` at `0x1400708b2`
- `KERNEL32!SetThreadAffinityMask` at `0x1400708b2`
- `msvcrt!_beginthreadex` at `0x140070883`
- `msvcrt!_beginthreadex` at `0x140070883`

## pseudocode

```c
DWORD __fastcall WinSAT::MPWorkload::CreateThread(DWORD *this, DWORD a2)
{
  void *v4; // rax
  DWORD v6; // ecx
  DWORD v7; // edx
  void *v8; // rcx
  unsigned int ThrdAddr; // [rsp+50h] [rbp+18h] BYREF

  ThrdAddr = 0;
  v4 = (void *)_beginthreadex(0, 0, WinSAT::MPWorkload::ThreadEntryPoint, this, 4u, &ThrdAddr);
  if ( !v4 )
    return GetLastError();
  v6 = this[22];
  *((_QWORD *)this + 102) = v4;
  if ( !SetThreadAffinityMask(v4, 1 << v6) )
    return GetLastError();
  v7 = this[22];
  v8 = (void *)*((_QWORD *)this + 102);
  this[194] = 1 << v7;
  if ( SetThreadIdealProcessor(v8, v7) == -1 )
    return GetLastError();
  this[192] = a2;
  return 0;
}

```

## disassembly

```asm
0x140070848  mov     rax, rsp
0x14007084b  mov     [rax+8], rbx
0x14007084f  mov     [rax+10h], rsi
0x140070853  push    rdi
0x140070854  sub     rsp, 30h
0x140070858  mov     dword ptr [rax+18h], 0
0x14007085f  lea     rax, [rax+18h]
0x140070863  mov     esi, edx
0x140070865  mov     [rsp+38h+ThrdAddr], rax; ThrdAddr
0x14007086a  mov     rbx, rcx
0x14007086d  mov     [rsp+38h+InitFlag], 4; InitFlag
0x140070875  mov     r9, rcx; ArgList
0x140070878  lea     r8, ?ThreadEntryPoint@MPWorkload@WinSAT@@CAIPEAX@Z; StartAddress
0x14007087f  xor     edx, edx; StackSize
0x140070881  xor     ecx, ecx; Security
0x140070883  call    cs:__imp__beginthreadex
0x140070889  mov     r8, rax
0x14007088c  test    rax, rax
0x14007088f  jnz     short loc_140070899
0x140070891  call    cs:__imp_GetLastError
0x140070897  jmp     short loc_1400708E4
0x140070899  mov     ecx, [rbx+58h]
0x14007089c  mov     edi, 1
0x1400708a1  mov     eax, edi
0x1400708a3  mov     [rbx+330h], r8
0x1400708aa  shl     eax, cl
0x1400708ac  mov     rcx, r8; hThread
0x1400708af  movsxd  rdx, eax; dwThreadAffinityMask
0x1400708b2  call    cs:__imp_SetThreadAffinityMask
0x1400708b8  test    rax, rax
0x1400708bb  jz      short loc_140070891
0x1400708bd  mov     ecx, [rbx+58h]
0x1400708c0  mov     edx, ecx; dwIdealProcessor
0x1400708c2  shl     edi, cl
0x1400708c4  mov     rcx, [rbx+330h]; hThread
0x1400708cb  mov     [rbx+308h], edi
0x1400708d1  call    cs:__imp_SetThreadIdealProcessor
0x1400708d7  cmp     eax, 0FFFFFFFFh
0x1400708da  jz      short loc_140070891
0x1400708dc  mov     [rbx+300h], esi
0x1400708e2  xor     eax, eax
0x1400708e4  mov     rbx, [rsp+38h+arg_0]
0x1400708e9  mov     rsi, [rsp+38h+arg_8]
0x1400708ee  add     rsp, 30h
0x1400708f2  pop     rdi
0x1400708f3  retn
```

# EventDumpWorkspace::CreateHexDump(ushort * *,ushort,ushort)

- ea: `0x14000d9e0`
- end: `0x14000daa8`
- name: `?CreateHexDump@EventDumpWorkspace@@IEAAKPEAPEAGGG@Z`
- size: `200`
- prototype: `unsigned int __fastcall(EventDumpWorkspace *__hidden this, unsigned __int16 **, unsigned __int16, unsigned __int16)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e254`
- `0x14000e540`
- `0x14000e7a8`

## callees

- `0x14000d9e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9f9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000da17`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000da17`

## pseudocode

```c
__int64 __fastcall EventDumpWorkspace::CreateHexDump(
        EventDumpWorkspace *this,
        unsigned __int16 **a2,
        unsigned __int16 a3,
        unsigned __int16 a4)
{
  int v4; // ebx
  __int64 v6; // rdi
  HANDLE ProcessHeap; // rax
  int v9; // ebx
  unsigned __int16 *v10; // r8
  __int64 result; // rax
  unsigned __int16 v12; // r10
  unsigned __int16 *i; // r9
  __int64 v14; // rdx
  __int16 v15; // cx
  __int16 v16; // ax
  __int16 v17; // cx
  __int16 v18; // ax

  v4 = a4;
  v6 = a3;
  ProcessHeap = GetProcessHeap();
  v9 = v4 - v6;
  v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, (unsigned int)(4 * v9) + 2LL);
  if ( !v10 )
    return 8;
  v12 = 0;
  *v10 = 0;
  for ( i = v10; v12 < v9; i += 2 )
  {
    v14 = v12 + *(_QWORD *)(*(_QWORD *)this + 96LL);
    v15 = *(_BYTE *)(v14 + v6) >> 4;
    v16 = 55;
    if ( (unsigned __int8)v15 <= 9u )
      v16 = 48;
    *i = v15 + v16;
    v17 = *(_BYTE *)(v14 + v6) & 0xF;
    v18 = 55;
    if ( (unsigned __int8)v17 <= 9u )
      v18 = 48;
    ++v12;
    i[1] = v17 + v18;
  }
  result = 0;
  *i = 0;
  *a2 = v10;
  return result;
}

```

## disassembly

```asm
0x14000d9e0  push    rbx
0x14000d9e2  push    rbp
0x14000d9e3  push    rsi
0x14000d9e4  push    rdi
0x14000d9e5  push    r14
0x14000d9e7  sub     rsp, 20h
0x14000d9eb  movzx   ebx, r9w
0x14000d9ef  mov     rsi, rdx
0x14000d9f2  movzx   edi, r8w
0x14000d9f6  mov     r14, rcx
0x14000d9f9  call    cs:__imp_GetProcessHeap
0x14000d9ff  sub     ebx, edi
0x14000da01  mov     ebp, 8
0x14000da06  mov     edx, ebp; dwFlags
0x14000da08  mov     rcx, rax; hHeap
0x14000da0b  lea     r8d, ds:0[rbx*4]
0x14000da13  add     r8, 2; dwBytes
0x14000da17  call    cs:__imp_HeapAlloc
0x14000da1d  mov     r8, rax
0x14000da20  test    rax, rax
0x14000da23  jnz     short loc_14000DA29
0x14000da25  mov     eax, ebp
0x14000da27  jmp     short loc_14000DA9D
0x14000da29  xor     eax, eax
0x14000da2b  xor     r10d, r10d
0x14000da2e  mov     [r8], ax
0x14000da32  mov     r9, r8
0x14000da35  test    ebx, ebx
0x14000da37  jle     short loc_14000DA94
0x14000da39  mov     r11, rdi
0x14000da3c  lea     ebp, [rax+30h]
0x14000da3f  lea     edi, [rax+37h]
0x14000da42  mov     rax, [r14]
0x14000da45  movzx   ecx, r10w
0x14000da49  mov     rdx, [rax+60h]
0x14000da4d  add     rdx, rcx
0x14000da50  mov     al, [rdx+r11]
0x14000da54  shr     al, 4
0x14000da57  movzx   ecx, al
0x14000da5a  mov     eax, edi
0x14000da5c  cmp     cl, 9
0x14000da5f  cmovbe  ax, bp
0x14000da63  add     ax, cx
0x14000da66  mov     [r9], ax
0x14000da6a  mov     al, [rdx+r11]
0x14000da6e  and     al, 0Fh
0x14000da70  movzx   ecx, al
0x14000da73  mov     eax, edi
0x14000da75  cmp     cl, 9
0x14000da78  cmovbe  ax, bp
0x14000da7c  inc     r10w
0x14000da80  add     ax, cx
0x14000da83  mov     [r9+2], ax
0x14000da88  add     r9, 4
0x14000da8c  movzx   eax, r10w
0x14000da90  cmp     eax, ebx
0x14000da92  jl      short loc_14000DA42
0x14000da94  xor     eax, eax
0x14000da96  mov     [r9], ax
0x14000da9a  mov     [rsi], r8
0x14000da9d  add     rsp, 20h
0x14000daa1  pop     r14
0x14000daa3  pop     rdi
0x14000daa4  pop     rsi
0x14000daa5  pop     rbp
0x14000daa6  pop     rbx
0x14000daa7  retn
```

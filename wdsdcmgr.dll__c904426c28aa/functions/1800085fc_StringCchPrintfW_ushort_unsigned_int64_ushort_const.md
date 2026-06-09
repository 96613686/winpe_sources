# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800085fc`
- end: `0x180008673`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `119`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180007ba4`
- `0x18000a3f0`
- `0x18000a870`
- `0x18000bb58`
- `0x18000bd00`
- `0x18000be10`
- `0x18000bf44`
- `0x18000c03c`
- `0x18000c158`
- `0x18000c2d0`
- `0x18000c774`
- `0x1800102e0`
- `0x180010da0`
- `0x180012090`
- `0x1800144e4`

## callees

- `0x1800085fc`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000863c`
- `msvcrt!_vsnwprintf` at `0x18000863c`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const unsigned __int16 *a3, ...)
{
  int v4; // edi
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  v4 = 0;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
    v4 = -2147024809;
  if ( v4 < 0 )
  {
    if ( a2 )
      *Buffer = 0;
  }
  else
  {
    v5 = a2 - 1;
    v4 = 0;
    v6 = _vsnwprintf(Buffer, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v5 )
    {
      Buffer[v5] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v6 == v5 )
    {
      Buffer[v5] = 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800085fc  mov     [rsp+arg_10], r8
0x180008601  mov     qword ptr [rsp+Args], r9
0x180008606  push    rbx
0x180008607  push    rbp
0x180008608  push    rsi
0x180008609  push    rdi
0x18000860a  sub     rsp, 28h
0x18000860e  xor     ebp, ebp
0x180008610  lea     rax, [rdx-1]
0x180008614  cmp     rax, 7FFFFFFEh
0x18000861a  mov     rsi, rcx
0x18000861d  mov     edi, ebp
0x18000861f  mov     ecx, 80070057h
0x180008624  cmova   edi, ecx
0x180008627  test    edi, edi
0x180008629  js      short loc_180008660
0x18000862b  lea     rbx, [rdx-1]
0x18000862f  mov     rcx, rsi; Buffer
0x180008632  mov     rdx, rbx; BufferCount
0x180008635  lea     r9, [rsp+48h+Args]; Args
0x18000863a  mov     edi, ebp
0x18000863c  call    cs:__imp__vsnwprintf
0x180008642  test    eax, eax
0x180008644  js      short loc_180008655
0x180008646  cdqe
0x180008648  cmp     rax, rbx
0x18000864b  ja      short loc_180008655
0x18000864d  jnz     short loc_180008668
0x18000864f  mov     [rsi+rbx*2], bp
0x180008653  jmp     short loc_180008668
0x180008655  mov     [rsi+rbx*2], bp
0x180008659  mov     edi, 8007007Ah
0x18000865e  jmp     short loc_180008668
0x180008660  test    rdx, rdx
0x180008663  jz      short loc_180008668
0x180008665  mov     [rsi], bp
0x180008668  mov     eax, edi
0x18000866a  add     rsp, 28h
0x18000866e  pop     rdi
0x18000866f  pop     rsi
0x180008670  pop     rbp
0x180008671  pop     rbx
0x180008672  retn
```

# CWMIndexEntryArchiver::GetNextEntry(uchar *)

- ea: `0x18000ff40`
- end: `0x180010047`
- name: `?GetNextEntry@CWMIndexEntryArchiver@@UEAAJPEAE@Z`
- size: `263`
- prototype: `int(CWMIndexEntryArchiver *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180007e38`
- `0x18000ff40`
- `0x18002a070`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18000ff9d`
- `KERNEL32!ReadFile` at `0x18000ff9d`

## pseudocode

```c
__int64 __fastcall CWMIndexEntryArchiver::GetNextEntry(CWMIndexEntryArchiver *this, unsigned __int8 *a2)
{
  unsigned int v5; // r9d
  unsigned int v6; // edx
  DWORD v7; // r8d
  void *v8; // rcx
  int v9; // r10d
  unsigned int v10; // r9d
  int v11; // esi
  __int64 v12; // rcx
  size_t v13; // r8
  const void *v14; // rdx
  unsigned int v15; // eax
  DWORD NumberOfBytesRead; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = *((_DWORD *)this + 2599);
  if ( v5 >= *((_DWORD *)this + 5) )
    return 2147500037LL;
  v6 = *((_DWORD *)this + 2598);
  if ( v5 >= v6 )
  {
    v9 = *((_DWORD *)this + 2464) * *((_DWORD *)this + 3);
    if ( v5 >= v9 + v6 )
    {
      v15 = *((_DWORD *)this + 2);
      v13 = v15;
      v14 = (const void *)(*((_QWORD *)this + 1203) + v15 * (v5 - v9 - v6));
    }
    else
    {
      v10 = v5 - v6;
      v11 = v10 % *((_DWORD *)this + 3);
      v12 = CTPtrArray<unsigned char,20>::operator[]((char *)this + 9640, v10 / *((_DWORD *)this + 3));
      if ( !v12 )
        return 2147549183LL;
      v13 = *((unsigned int *)this + 2);
      v14 = (const void *)(v12 + (unsigned int)(v11 * v13));
    }
    memcpy_0(a2, v14, v13);
  }
  else
  {
    v7 = *((_DWORD *)this + 2);
    v8 = (void *)*((_QWORD *)this + 1233);
    NumberOfBytesRead = 0;
    if ( !ReadFile(v8, a2, v7, &NumberOfBytesRead, 0) || NumberOfBytesRead < *((_DWORD *)this + 2) )
      return 2147500037LL;
  }
  ++*((_DWORD *)this + 2599);
  return 0;
}

```

## disassembly

```asm
0x18000ff40  mov     [rsp+arg_0], rbx
0x18000ff45  mov     [rsp+arg_10], rsi
0x18000ff4a  push    rdi
0x18000ff4b  sub     rsp, 30h
0x18000ff4f  mov     rdi, rdx
0x18000ff52  mov     rbx, rcx
0x18000ff55  test    rdx, rdx
0x18000ff58  jnz     short loc_18000FF61
0x18000ff5a  mov     eax, 80070057h
0x18000ff5f  jmp     short loc_18000FFB9
0x18000ff61  mov     r9d, [rcx+289Ch]
0x18000ff68  cmp     r9d, [rcx+14h]
0x18000ff6c  jnb     short loc_18000FFB4
0x18000ff6e  mov     edx, [rcx+2898h]
0x18000ff74  cmp     r9d, edx
0x18000ff77  jnb     short loc_18000FFC9
0x18000ff79  mov     r8d, [rcx+8]; nNumberOfBytesToRead
0x18000ff7d  lea     r9, [rsp+38h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000ff82  mov     rcx, [rcx+2688h]; hFile
0x18000ff89  mov     rdx, rdi; lpBuffer
0x18000ff8c  mov     [rsp+38h+NumberOfBytesRead], 0
0x18000ff94  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18000ff9d  call    cs:__imp_ReadFile
0x18000ffa3  test    eax, eax
0x18000ffa5  jz      short loc_18000FFB4
0x18000ffa7  mov     eax, [rbx+8]
0x18000ffaa  cmp     [rsp+38h+NumberOfBytesRead], eax
0x18000ffae  jnb     loc_18001003A
0x18000ffb4  mov     eax, 80004005h
0x18000ffb9  mov     rbx, [rsp+38h+arg_0]
0x18000ffbe  mov     rsi, [rsp+38h+arg_10]
0x18000ffc3  add     rsp, 30h
0x18000ffc7  pop     rdi
0x18000ffc8  retn
0x18000ffc9  mov     r10d, [rcx+0Ch]
0x18000ffcd  imul    r10d, [rcx+2680h]
0x18000ffd5  lea     ecx, [r10+rdx]
0x18000ffd9  cmp     r9d, ecx
0x18000ffdc  jnb     short loc_180010018
0x18000ffde  sub     r9d, edx
0x18000ffe1  lea     rcx, [rbx+25A8h]
0x18000ffe8  xor     edx, edx
0x18000ffea  mov     eax, r9d
0x18000ffed  div     dword ptr [rbx+0Ch]
0x18000fff0  mov     esi, edx
0x18000fff2  mov     edx, eax
0x18000fff4  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x18000fff9  mov     rcx, rax
0x18000fffc  test    rax, rax
0x18000ffff  jnz     short loc_180010008
0x180010001  mov     eax, 8000FFFFh
0x180010006  jmp     short loc_18000FFB9
0x180010008  mov     eax, [rbx+8]
0x18001000b  mov     r8d, eax
0x18001000e  imul    eax, esi
0x180010011  mov     edx, eax
0x180010013  add     rdx, rcx
0x180010016  jmp     short loc_180010032
0x180010018  mov     eax, [rbx+8]
0x18001001b  sub     r9d, r10d
0x18001001e  sub     r9d, edx
0x180010021  mov     r8d, eax; Size
0x180010024  imul    r9d, eax
0x180010028  mov     edx, r9d
0x18001002b  add     rdx, [rbx+2598h]; Src
0x180010032  mov     rcx, rdi; void *
0x180010035  call    memcpy_0
0x18001003a  inc     dword ptr [rbx+289Ch]
0x180010040  xor     eax, eax
0x180010042  jmp     loc_18000FFB9
```

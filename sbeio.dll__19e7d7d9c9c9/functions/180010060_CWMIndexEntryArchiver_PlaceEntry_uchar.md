# CWMIndexEntryArchiver::PlaceEntry(uchar *)

- ea: `0x180010060`
- end: `0x180010262`
- name: `?PlaceEntry@CWMIndexEntryArchiver@@UEAAJPEAE@Z`
- size: `514`
- prototype: `int(CWMIndexEntryArchiver *__hidden this, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800011ec`
- `0x1800015f0`
- `0x180007e38`
- `0x18000b69c`
- `0x180010060`
- `0x180010268`
- `0x180029d08`
- `0x18002a070`

## import_xrefs

- `KERNEL32!GlobalMemoryStatus` at `0x180010111`
- `KERNEL32!GlobalMemoryStatus` at `0x180010111`
- `KERNEL32!CreateFileW` at `0x1800101a5`
- `KERNEL32!CreateFileW` at `0x1800101a5`
- `KERNEL32!WriteFile` at `0x1800101f4`
- `KERNEL32!WriteFile` at `0x1800101f4`

## pseudocode

```c
__int64 __fastcall CWMIndexEntryArchiver::PlaceEntry(CWMIndexEntryArchiver *this, unsigned __int8 *a2)
{
  __int64 result; // rax
  unsigned int v5; // ecx
  void *v6; // rax
  void *v7; // rcx
  HANDLE FileW; // rax
  void *v9; // rbp
  void *v10; // rcx
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-68h] BYREF
  struct _MEMORYSTATUS Buffer; // [rsp+48h] [rbp-60h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v5 = *((_DWORD *)this + 2408);
  if ( v5 < *((_DWORD *)this + 3) )
  {
    memcpy_0((void *)(*((_QWORD *)this + 1203) + *((_DWORD *)this + 2) * v5), a2, *((unsigned int *)this + 2));
    ++*((_DWORD *)this + 2408);
LABEL_18:
    ++*((_DWORD *)this + 5);
    return 0;
  }
  if ( (int)CTSparseBlock<unsigned long,WRITER_SINK_CALLBACK *,20,1>::SetValue(
              (char *)this + 9640,
              *((unsigned int *)this + 2464),
              *((_QWORD *)this + 1203)) >= 0 )
  {
    ++*((_DWORD *)this + 2464);
    memset(&Buffer, 0, sizeof(Buffer));
    GlobalMemoryStatus(&Buffer);
    if ( Buffer.dwAvailPhys / (10 * (unsigned __int64)*((unsigned __int16 *)this + 8)) >= 0x2580 )
    {
      v6 = operator new[](0x2580u);
      if ( !v6 )
        return 2147942414LL;
      *((_QWORD *)this + 1203) = v6;
      v7 = v6;
      goto LABEL_17;
    }
    if ( *((_QWORD *)this + 1233) != -1 )
      goto LABEL_15;
    result = GetRandomTempFileName((CWMIndexEntryArchiver *)((char *)this + 9872));
    if ( (int)result < 0 )
      return result;
    FileW = CreateFileW((LPCWSTR)this + 4936, 0xC0000000, 0, 0, 2u, 0x80u, 0);
    *((_QWORD *)this + 1233) = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
LABEL_15:
      v9 = (void *)CTPtrArray<unsigned char,20>::operator[]((char *)this + 9640, 0);
      if ( (unsigned int)CTPtrArray<unsigned char,20>::RemoveAt((char *)this + 9640) )
      {
        v10 = (void *)*((_QWORD *)this + 1233);
        NumberOfBytesWritten = 0;
        if ( WriteFile(v10, v9, 0x2580u, &NumberOfBytesWritten, 0) )
        {
          if ( NumberOfBytesWritten >= 0x2580 )
          {
            v7 = v9;
            *((_DWORD *)this + 2598) += *((_DWORD *)this + 3);
            *((_QWORD *)this + 1203) = v9;
LABEL_17:
            memcpy_0(v7, a2, *((unsigned int *)this + 2));
            *((_DWORD *)this + 2408) = 1;
            goto LABEL_18;
          }
        }
      }
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180010060  mov     [rsp+arg_10], rbx
0x180010065  mov     [rsp+arg_18], rbp
0x18001006a  push    rsi
0x18001006b  push    rdi
0x18001006c  push    r15
0x18001006e  sub     rsp, 90h
0x180010075  mov     rax, cs:__security_cookie
0x18001007c  xor     rax, rsp
0x18001007f  mov     [rsp+0A8h+var_28], rax
0x180010087  mov     rdi, rdx
0x18001008a  mov     rbx, rcx
0x18001008d  test    rdx, rdx
0x180010090  jnz     short loc_18001009C
0x180010092  mov     eax, 80070057h
0x180010097  jmp     loc_18001023A
0x18001009c  mov     ecx, [rcx+25A0h]
0x1800100a2  mov     rdx, [rbx+2598h]
0x1800100a9  cmp     ecx, [rbx+0Ch]
0x1800100ac  jnb     short loc_1800100CD
0x1800100ae  mov     eax, [rbx+8]
0x1800100b1  imul    ecx, eax
0x1800100b4  mov     r8d, eax; Size
0x1800100b7  add     rcx, rdx; void *
0x1800100ba  mov     rdx, rdi; Src
0x1800100bd  call    memcpy_0
0x1800100c2  inc     dword ptr [rbx+25A0h]
0x1800100c8  jmp     loc_18001022E
0x1800100cd  lea     rsi, [rbx+25A8h]
0x1800100d4  mov     r8, rdx
0x1800100d7  mov     edx, [rsi+0D8h]
0x1800100dd  mov     rcx, rsi
0x1800100e0  call    ?SetValue@?$CTSparseBlock@KPEAUWRITER_SINK_CALLBACK@@$0BE@$00@@QEAAJKPEAUWRITER_SINK_CALLBACK@@@Z; CTSparseBlock<ulong,WRITER_SINK_CALLBACK *,20,1>::SetValue(ulong,WRITER_SINK_CALLBACK *)
0x1800100e5  test    eax, eax
0x1800100e7  js      loc_180010235
0x1800100ed  inc     dword ptr [rbx+2680h]
0x1800100f3  lea     rcx, [rsp+0A8h+Buffer]; lpBuffer
0x1800100f8  xorps   xmm0, xmm0
0x1800100fb  xor     eax, eax
0x1800100fd  movups  xmmword ptr [rsp+0A8h+Buffer.dwLength], xmm0
0x180010102  mov     [rsp+0A8h+Buffer.dwAvailVirtual], rax
0x180010107  movups  xmmword ptr [rsp+0A8h+Buffer.dwAvailPhys], xmm0
0x18001010c  movups  xmmword ptr [rsp+0A8h+Buffer.dwAvailPageFile], xmm0
0x180010111  call    cs:__imp_GlobalMemoryStatus
0x180010117  movzx   eax, word ptr [rbx+10h]
0x18001011b  xor     edx, edx; unsigned int
0x18001011d  mov     r15d, 2580h
0x180010123  lea     rcx, [rax+rax*4]
0x180010127  mov     rax, [rsp+0A8h+Buffer.dwAvailPhys]
0x18001012c  add     rcx, rcx
0x18001012f  div     rcx
0x180010132  cmp     rax, r15
0x180010135  jb      short loc_18001015D
0x180010137  mov     ecx, r15d; unsigned __int64
0x18001013a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001013f  test    rax, rax
0x180010142  jnz     short loc_18001014E
0x180010144  mov     eax, 8007000Eh
0x180010149  jmp     loc_18001023A
0x18001014e  mov     [rbx+2598h], rax
0x180010155  mov     rcx, rax
0x180010158  jmp     loc_180010218
0x18001015d  cmp     qword ptr [rbx+2688h], 0FFFFFFFFFFFFFFFFh
0x180010165  jnz     short loc_1800101B8
0x180010167  lea     rbp, [rbx+2690h]
0x18001016e  mov     rcx, rbp; unsigned __int16 *
0x180010171  call    ?GetRandomTempFileName@@YAJPEAGK@Z; GetRandomTempFileName(ushort *,ulong)
0x180010176  test    eax, eax
0x180010178  js      loc_18001023A
0x18001017e  mov     [rsp+0A8h+hTemplateFile], 0; hTemplateFile
0x180010187  xor     r9d, r9d; lpSecurityAttributes
0x18001018a  mov     [rsp+0A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180010192  xor     r8d, r8d; dwShareMode
0x180010195  mov     edx, 0C0000000h; dwDesiredAccess
0x18001019a  mov     [rsp+0A8h+dwCreationDisposition], 2; dwCreationDisposition
0x1800101a2  mov     rcx, rbp; lpFileName
0x1800101a5  call    cs:__imp_CreateFileW
0x1800101ab  mov     [rbx+2688h], rax
0x1800101b2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800101b6  jz      short loc_180010235
0x1800101b8  xor     edx, edx
0x1800101ba  mov     rcx, rsi
0x1800101bd  call    ??A?$CTPtrArray@E$0BE@@@QEBAPEAEK@Z; CTPtrArray<uchar,20>::operator[](ulong)
0x1800101c2  mov     rcx, rsi
0x1800101c5  mov     rbp, rax
0x1800101c8  call    ?RemoveAt@?$CTPtrArray@E$0BE@@@QEAAHKK@Z; CTPtrArray<uchar,20>::RemoveAt(ulong,ulong)
0x1800101cd  test    eax, eax
0x1800101cf  jz      short loc_180010235
0x1800101d1  mov     rcx, [rbx+2688h]; hFile
0x1800101d8  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800101dd  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800101e0  mov     [rsp+0A8h+NumberOfBytesWritten], 0
0x1800101e8  mov     rdx, rbp; lpBuffer
0x1800101eb  mov     qword ptr [rsp+0A8h+dwCreationDisposition], 0; lpOverlapped
0x1800101f4  call    cs:__imp_WriteFile
0x1800101fa  test    eax, eax
0x1800101fc  jz      short loc_180010235
0x1800101fe  cmp     [rsp+0A8h+NumberOfBytesWritten], r15d
0x180010203  jb      short loc_180010235
0x180010205  mov     eax, [rbx+0Ch]
0x180010208  mov     rcx, rbp; void *
0x18001020b  add     [rbx+2898h], eax
0x180010211  mov     [rbx+2598h], rbp
0x180010218  mov     r8d, [rbx+8]; Size
0x18001021c  mov     rdx, rdi; Src
0x18001021f  call    memcpy_0
0x180010224  mov     dword ptr [rbx+25A0h], 1
0x18001022e  inc     dword ptr [rbx+14h]
0x180010231  xor     eax, eax
0x180010233  jmp     short loc_18001023A
0x180010235  mov     eax, 80004005h
0x18001023a  mov     rcx, [rsp+0A8h+var_28]
0x180010242  xor     rcx, rsp; StackCookie
0x180010245  call    __security_check_cookie
0x18001024a  lea     r11, [rsp+0A8h+var_18]
0x180010252  mov     rbx, [r11+30h]
0x180010256  mov     rbp, [r11+38h]
0x18001025a  mov     rsp, r11
0x18001025d  pop     r15
0x18001025f  pop     rdi
0x180010260  pop     rsi
0x180010261  retn
```

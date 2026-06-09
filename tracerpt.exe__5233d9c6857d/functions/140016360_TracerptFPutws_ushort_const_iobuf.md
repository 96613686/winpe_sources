# TracerptFPutws(ushort const *,_iobuf *)

- ea: `0x140016360`
- end: `0x1400164bc`
- name: `?TracerptFPutws@@YAKPEBGPEAU_iobuf@@@Z`
- size: `348`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, struct _iobuf *)`
- caller_count: `59`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000bec0`
- `0x14000bfe4`
- `0x14000c298`
- `0x14000c964`
- `0x14000ce24`
- `0x14000d174`
- `0x14000d4a8`
- `0x14000faa4`
- `0x14000ffcc`
- `0x140011ff8`
- `0x1400120f4`
- `0x1400121c0`
- `0x14001232c`
- `0x1400130d0`
- `0x1400131c8`
- `0x140013564`
- `0x1400137b8`
- `0x1400140f8`
- `0x140014218`
- `0x1400144c4`
- `0x1400145a0`
- `0x14001489c`
- `0x140014b98`
- `0x140014ccc`
- `0x140014e98`
- `0x1400152e8`
- `0x1400155e0`
- `0x140015974`
- `0x140016ae0`
- `0x1400192b4`
- `0x14001f330`
- `0x14001f4ac`
- `0x14001f7d8`
- `0x14001f8d8`
- `0x14001fa40`
- `0x14001fd7c`
- `0x140020310`
- `0x140020748`
- `0x1400208e4`
- `0x140021184`
- `0x140021ff4`
- `0x140022480`
- `0x1400268c8`
- `0x140026d88`
- `0x140027630`
- `0x140027de4`
- `0x1400281f0`
- `0x1400283dc`
- `0x14002ac00`
- `0x14002ae38`

## callees

- `0x140015ee0`
- `0x140016360`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400164a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140016432`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400164a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016493`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016424`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140016493`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400163e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001640b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001645c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400163e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001640b`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14001645c`

## pseudocode

```c
__int64 __fastcall TracerptFPutws(wchar_t *a1, struct _iobuf *a2)
{
  wchar_t *v3; // rbp
  __int64 result; // rax
  void *v5; // rsi
  __int64 v6; // rbx
  __int64 flag; // rcx
  char *ptr; // rcx
  HANDLE v9; // rax
  HANDLE ProcessHeap; // rax
  DWORD NumberOfBytesWritten; // [rsp+58h] [rbp+10h] BYREF

  v3 = a1;
  NumberOfBytesWritten = 0;
  if ( LOBYTE(a2[1365]._charbuf) )
  {
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( a1[v6] );
    LODWORD(v6) = 2 * v6;
  }
  else
  {
    result = ConvertWideCharToMultiByte(a1);
    v5 = (void *)result;
    if ( !result )
      return result;
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(result + v6) );
    v3 = (wchar_t *)result;
  }
  flag = (unsigned int)a2[1365]._flag;
  if ( (unsigned int)v6 <= 0x10000 )
  {
    if ( (unsigned int)(flag + v6) > 0xFFFF )
    {
      WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
      a2[1365]._file += NumberOfBytesWritten;
      a2[1365]._flag = 0;
      flag = 0;
    }
    memcpy_0((char *)&a2->_cnt + flag, v3, (unsigned int)v6);
    a2[1365]._flag += v6;
    if ( v5 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    return (unsigned int)v6;
  }
  else
  {
    WriteFile(a2->_ptr, &a2->_cnt, flag, &NumberOfBytesWritten, 0);
    ptr = a2->_ptr;
    a2[1365]._file += NumberOfBytesWritten;
    a2[1365]._flag = 0;
    WriteFile(ptr, v3, v6, &NumberOfBytesWritten, 0);
    result = NumberOfBytesWritten;
    a2[1365]._file += NumberOfBytesWritten;
    if ( v5 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v5);
      return NumberOfBytesWritten;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016360  mov     [rsp+arg_0], rbx
0x140016365  mov     [rsp+arg_10], rbp
0x14001636a  push    rsi
0x14001636b  push    rdi
0x14001636c  push    r14
0x14001636e  sub     rsp, 30h
0x140016372  xor     r14d, r14d
0x140016375  mov     rdi, rdx
0x140016378  mov     rbp, rcx
0x14001637b  mov     [rsp+48h+NumberOfBytesWritten], r14d
0x140016380  cmp     [rdx+10010h], r14b
0x140016387  jnz     short loc_1400163AC
0x140016389  call    ConvertWideCharToMultiByte
0x14001638e  mov     rsi, rax
0x140016391  test    rax, rax
0x140016394  jz      loc_1400164A9
0x14001639a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001639e  inc     rbx
0x1400163a1  cmp     [rax+rbx], r14b
0x1400163a5  jnz     short loc_14001639E
0x1400163a7  mov     rbp, rax
0x1400163aa  jmp     short loc_1400163BF
0x1400163ac  mov     rsi, r14
0x1400163af  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400163b3  inc     rbx
0x1400163b6  cmp     [rcx+rbx*2], r14w
0x1400163bb  jnz     short loc_1400163B3
0x1400163bd  add     ebx, ebx
0x1400163bf  mov     ecx, [rdi+10008h]
0x1400163c5  cmp     ebx, 10000h
0x1400163cb  jbe     short loc_14001643E
0x1400163cd  mov     r8d, ecx; nNumberOfBytesToWrite
0x1400163d0  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x1400163d5  mov     rcx, [rdi]; hFile
0x1400163d8  lea     rdx, [rdi+8]; lpBuffer
0x1400163dc  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400163e1  call    cs:__imp_WriteFile
0x1400163e7  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x1400163eb  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1400163f0  mov     rcx, [rdi]; hFile
0x1400163f3  mov     r8d, ebx; nNumberOfBytesToWrite
0x1400163f6  add     [rdi+1000Ch], eax
0x1400163fc  mov     rdx, rbp; lpBuffer
0x1400163ff  mov     [rdi+10008h], r14d
0x140016406  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x14001640b  call    cs:__imp_WriteFile
0x140016411  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x140016415  add     [rdi+1000Ch], eax
0x14001641b  test    rsi, rsi
0x14001641e  jz      loc_1400164A9
0x140016424  call    cs:__imp_GetProcessHeap
0x14001642a  mov     r8, rsi; lpMem
0x14001642d  xor     edx, edx; dwFlags
0x14001642f  mov     rcx, rax; hHeap
0x140016432  call    cs:__imp_HeapFree
0x140016438  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x14001643c  jmp     short loc_1400164A9
0x14001643e  lea     eax, [rcx+rbx]
0x140016441  cmp     eax, 0FFFFh
0x140016446  jbe     short loc_140016476
0x140016448  mov     r8d, ecx; nNumberOfBytesToWrite
0x14001644b  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x140016450  mov     rcx, [rdi]; hFile
0x140016453  lea     rdx, [rdi+8]; lpBuffer
0x140016457  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14001645c  call    cs:__imp_WriteFile
0x140016462  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x140016466  add     [rdi+1000Ch], eax
0x14001646c  mov     [rdi+10008h], r14d
0x140016473  mov     ecx, r14d
0x140016476  add     rcx, 8
0x14001647a  mov     r8d, ebx; Size
0x14001647d  add     rcx, rdi; void *
0x140016480  mov     rdx, rbp; Src
0x140016483  call    memcpy_0
0x140016488  add     [rdi+10008h], ebx
0x14001648e  test    rsi, rsi
0x140016491  jz      short loc_1400164A7
0x140016493  call    cs:__imp_GetProcessHeap
0x140016499  mov     r8, rsi; lpMem
0x14001649c  xor     edx, edx; dwFlags
0x14001649e  mov     rcx, rax; hHeap
0x1400164a1  call    cs:__imp_HeapFree
0x1400164a7  mov     eax, ebx
0x1400164a9  mov     rbx, [rsp+48h+arg_0]
0x1400164ae  mov     rbp, [rsp+48h+arg_10]
0x1400164b3  add     rsp, 30h
0x1400164b7  pop     r14
0x1400164b9  pop     rdi
0x1400164ba  pop     rsi
0x1400164bb  retn
```

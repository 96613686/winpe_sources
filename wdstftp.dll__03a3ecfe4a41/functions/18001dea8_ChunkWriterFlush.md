# ChunkWriterFlush

- ea: `0x18001dea8`
- end: `0x18001dfd3`
- name: `ChunkWriterFlush`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001da04`

## callees

- `0x18001d7c8`
- `0x18001dea8`
- `0x18001e3fc`
- `0x18001e500`
- `0x1800219c4`
- `0x180021bf4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001df67`
- `KERNEL32!GetLastError` at `0x18001df86`
- `KERNEL32!GetLastError` at `0x18001df67`
- `KERNEL32!GetLastError` at `0x18001df86`

## string_xrefs

- `0x18001df33`: `ChunkWriterFlush`
- `0x18001dfb0`: `ChunkWriterFlush`

## pseudocode

```c
__int64 __fastcall ChunkWriterFlush(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rsi
  signed int v3; // ebx
  int v5; // ebp
  int v6; // eax
  __int64 v7; // rdx
  int v8; // r9d
  unsigned int v9; // r8d
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  signed int LastError; // eax
  signed int v14; // ecx
  signed int v15; // eax

  v2 = a2[5];
  v3 = 0;
  v5 = a1;
  if ( v2 && *(_DWORD *)(v2 + 48) )
  {
    v6 = AllocChunkInfo(a1, a2, *(unsigned int *)(v2 + 56), v2 + 40);
    v3 = v6;
    if ( v6 < 0 )
    {
      v8 = v6;
      v9 = 719;
LABEL_18:
      UtilReportError((__int64)L"ChunkWriterFlush", v7, v9, v8);
      return (unsigned int)v3;
    }
    v10 = WimImageEnqueueOperation(v5, *a2, v2, (unsigned int)CompressChunk, 0, (__int64)ReclaimWriteChunk, 1);
    v3 = v10;
    if ( v10 < 0 )
    {
      UtilReportError((__int64)L"ChunkWriterFlush", v11, 0x2D7u, v10);
      ReclaimWriteChunk(v2);
    }
    a2[5] = 0;
    if ( v3 >= 0 )
    {
      v12 = AllocateWriteChunk(a2);
      a2[5] = v12;
      if ( !v12 )
      {
        LastError = GetLastError();
        v14 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v14 = LastError;
        if ( v14 >= 0 )
        {
          v3 = -2147467259;
        }
        else
        {
          v15 = GetLastError();
          v3 = (unsigned __int16)v15 | 0x80070000;
          if ( v15 <= 0 )
            v3 = v15;
        }
        if ( v3 < 0 )
        {
          v8 = v3;
          v9 = 747;
          goto LABEL_18;
        }
      }
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001dea8  mov     [rsp+arg_0], rbx
0x18001dead  mov     [rsp+arg_8], rbp
0x18001deb2  mov     [rsp+arg_10], rsi
0x18001deb7  push    rdi
0x18001deb8  sub     rsp, 40h
0x18001debc  mov     rsi, [rdx+28h]
0x18001dec0  xor     ebx, ebx
0x18001dec2  mov     rdi, rdx
0x18001dec5  mov     rbp, rcx
0x18001dec8  test    rsi, rsi
0x18001decb  jz      loc_18001DFBC
0x18001ded1  cmp     [rsi+30h], ebx
0x18001ded4  jz      loc_18001DFBC
0x18001deda  mov     r8d, [rsi+38h]
0x18001dede  lea     r9, [rsi+28h]
0x18001dee2  call    AllocChunkInfo
0x18001dee7  mov     ebx, eax
0x18001dee9  test    eax, eax
0x18001deeb  jns     short loc_18001DEFB
0x18001deed  mov     r9d, eax
0x18001def0  mov     r8d, 2CFh
0x18001def6  jmp     loc_18001DFB0
0x18001defb  mov     rdx, [rdi]
0x18001defe  lea     rax, ReclaimWriteChunk
0x18001df05  mov     [rsp+48h+var_18], 1
0x18001df0d  lea     r9, CompressChunk
0x18001df14  mov     [rsp+48h+var_20], rax
0x18001df19  mov     r8, rsi
0x18001df1c  and     [rsp+48h+var_28], 0
0x18001df22  mov     rcx, rbp
0x18001df25  call    WimImageEnqueueOperation
0x18001df2a  mov     ebx, eax
0x18001df2c  test    eax, eax
0x18001df2e  jns     short loc_18001DF4D
0x18001df30  mov     r9d, eax
0x18001df33  lea     rcx, aChunkwriterflu; "ChunkWriterFlush"
0x18001df3a  mov     r8d, 2D7h
0x18001df40  call    UtilReportError
0x18001df45  mov     rcx, rsi
0x18001df48  call    ReclaimWriteChunk
0x18001df4d  and     qword ptr [rdi+28h], 0
0x18001df52  test    ebx, ebx
0x18001df54  js      short loc_18001DFBC
0x18001df56  mov     rcx, rdi
0x18001df59  call    AllocateWriteChunk
0x18001df5e  mov     [rdi+28h], rax
0x18001df62  test    rax, rax
0x18001df65  jnz     short loc_18001DFBC
0x18001df67  call    cs:__imp_GetLastError
0x18001df6e  nop     dword ptr [rax+rax+00h]
0x18001df73  movzx   ecx, ax
0x18001df76  mov     edi, 80070000h
0x18001df7b  or      ecx, edi
0x18001df7d  test    eax, eax
0x18001df7f  cmovle  ecx, eax
0x18001df82  test    ecx, ecx
0x18001df84  jns     short loc_18001DF9E
0x18001df86  call    cs:__imp_GetLastError
0x18001df8d  nop     dword ptr [rax+rax+00h]
0x18001df92  movzx   ebx, ax
0x18001df95  or      ebx, edi
0x18001df97  test    eax, eax
0x18001df99  cmovle  ebx, eax
0x18001df9c  jmp     short loc_18001DFA3
0x18001df9e  mov     ebx, 80004005h
0x18001dfa3  test    ebx, ebx
0x18001dfa5  jns     short loc_18001DFBC
0x18001dfa7  mov     r9d, ebx
0x18001dfaa  mov     r8d, 2EBh
0x18001dfb0  lea     rcx, aChunkwriterflu; "ChunkWriterFlush"
0x18001dfb7  call    UtilReportError
0x18001dfbc  mov     rbp, [rsp+48h+arg_8]
0x18001dfc1  mov     eax, ebx
0x18001dfc3  mov     rbx, [rsp+48h+arg_0]
0x18001dfc8  mov     rsi, [rsp+48h+arg_10]
0x18001dfcd  add     rsp, 40h
0x18001dfd1  pop     rdi
0x18001dfd2  retn
```

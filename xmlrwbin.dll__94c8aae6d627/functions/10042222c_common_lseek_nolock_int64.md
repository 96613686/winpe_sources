# common_lseek_nolock___int64_

- ea: `0x10042222c`
- end: `0x1004222d5`
- name: `common_lseek_nolock___int64_`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1004222dc`

## callees

- `0x10041c158`
- `0x100420d90`
- `0x10042222c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100422282`
- `KERNEL32!GetLastError` at `0x100422282`
- `KERNEL32!SetFilePointerEx` at `0x100422278`
- `KERNEL32!SetFilePointerEx` at `0x100422278`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (LARGE_INTEGER)-1LL;
  }
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4);
    return (LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x10042222c  mov     [rsp+arg_0], rbx
0x100422231  mov     [rsp+arg_8], rbp
0x100422236  mov     [rsp+arg_10], rsi
0x10042223b  push    rdi
0x10042223c  sub     rsp, 30h
0x100422240  movsxd  rdi, ecx
0x100422243  mov     rbx, r9
0x100422246  mov     ecx, edi; FileHandle
0x100422248  mov     esi, r8d
0x10042224b  mov     rbp, rdx
0x10042224e  call    _get_osfhandle
0x100422253  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100422257  jnz     short loc_10042226A
0x100422259  mov     byte ptr [rbx+30h], 1
0x10042225d  mov     dword ptr [rbx+2Ch], 9
0x100422264  or      rax, 0FFFFFFFFFFFFFFFFh
0x100422268  jmp     short loc_1004222C0
0x10042226a  mov     r9d, esi; dwMoveMethod
0x10042226d  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x100422272  mov     rdx, rbp; liDistanceToMove
0x100422275  mov     rcx, rax; hFile
0x100422278  call    cs:__imp_SetFilePointerEx
0x10042227e  test    eax, eax
0x100422280  jnz     short loc_100422294
0x100422282  call    cs:__imp_GetLastError
0x100422288  mov     ecx, eax
0x10042228a  mov     rdx, rbx
0x10042228d  call    __acrt_errno_map_os_error_ptd
0x100422292  jmp     short loc_100422264
0x100422294  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x100422299  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x10042229d  jz      short loc_100422264
0x10042229f  mov     rdx, rdi
0x1004222a2  lea     r8, __pioinfo
0x1004222a9  and     edx, 3Fh
0x1004222ac  mov     rcx, rdi
0x1004222af  sar     rcx, 6
0x1004222b3  lea     rdx, [rdx+rdx*8]
0x1004222b7  mov     rcx, [r8+rcx*8]
0x1004222bb  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x1004222c0  mov     rbx, [rsp+38h+arg_0]
0x1004222c5  mov     rbp, [rsp+38h+arg_8]
0x1004222ca  mov     rsi, [rsp+38h+arg_10]
0x1004222cf  add     rsp, 30h
0x1004222d3  pop     rdi
0x1004222d4  retn
```

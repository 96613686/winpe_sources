# common_lseek_nolock___int64_

- ea: `0x1004371b4`
- end: `0x10043725d`
- name: `common_lseek_nolock___int64_`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100437264`

## callees

- `0x10042e6e8`
- `0x100434340`
- `0x1004371b4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10043720a`
- `KERNEL32!GetLastError` at `0x10043720a`
- `KERNEL32!SetFilePointerEx` at `0x100437200`
- `KERNEL32!SetFilePointerEx` at `0x100437200`

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
0x1004371b4  mov     [rsp+arg_0], rbx
0x1004371b9  mov     [rsp+arg_8], rbp
0x1004371be  mov     [rsp+arg_10], rsi
0x1004371c3  push    rdi
0x1004371c4  sub     rsp, 30h
0x1004371c8  movsxd  rdi, ecx
0x1004371cb  mov     rbx, r9
0x1004371ce  mov     ecx, edi; FileHandle
0x1004371d0  mov     esi, r8d
0x1004371d3  mov     rbp, rdx
0x1004371d6  call    _get_osfhandle
0x1004371db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004371df  jnz     short loc_1004371F2
0x1004371e1  mov     byte ptr [rbx+30h], 1
0x1004371e5  mov     dword ptr [rbx+2Ch], 9
0x1004371ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x1004371f0  jmp     short loc_100437248
0x1004371f2  mov     r9d, esi; dwMoveMethod
0x1004371f5  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x1004371fa  mov     rdx, rbp; liDistanceToMove
0x1004371fd  mov     rcx, rax; hFile
0x100437200  call    cs:__imp_SetFilePointerEx
0x100437206  test    eax, eax
0x100437208  jnz     short loc_10043721C
0x10043720a  call    cs:__imp_GetLastError
0x100437210  mov     ecx, eax
0x100437212  mov     rdx, rbx
0x100437215  call    __acrt_errno_map_os_error_ptd
0x10043721a  jmp     short loc_1004371EC
0x10043721c  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x100437221  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x100437225  jz      short loc_1004371EC
0x100437227  mov     rdx, rdi
0x10043722a  lea     r8, __pioinfo
0x100437231  and     edx, 3Fh
0x100437234  mov     rcx, rdi
0x100437237  sar     rcx, 6
0x10043723b  lea     rdx, [rdx+rdx*8]
0x10043723f  mov     rcx, [r8+rcx*8]
0x100437243  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x100437248  mov     rbx, [rsp+38h+arg_0]
0x10043724d  mov     rbp, [rsp+38h+arg_8]
0x100437252  mov     rsi, [rsp+38h+arg_10]
0x100437257  add     rsp, 30h
0x10043725b  pop     rdi
0x10043725c  retn
```

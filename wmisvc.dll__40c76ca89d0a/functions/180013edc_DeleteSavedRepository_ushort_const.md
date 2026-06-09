# DeleteSavedRepository(ushort const *)

- ea: `0x180013edc`
- end: `0x180013ff5`
- name: `?DeleteSavedRepository@@YAJPEBG@Z`
- size: `281`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dcdc`

## callees

- `0x180004120`
- `0x180004c30`
- `0x18000b4f4`
- `0x180012c34`
- `0x180013edc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013fb8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180013fd1`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180013fd1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013fa3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180013fa3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013f11`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180013f11`
- `wbemcomn!GetMemLogObject` at `0x180013f01`
- `wbemcomn!GetMemLogObject` at `0x180013f01`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013ef3`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180013ef3`

## pseudocode

```c
__int64 __fastcall DeleteSavedRepository(const unsigned __int16 *a1)
{
  unsigned __int16 *v2; // rax
  unsigned __int16 *v3; // rdi
  CMemoryLog *MemLogObject; // rax
  unsigned int v5; // ebx
  int i; // ebx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v2 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v3 = v2;
  if ( v2 )
  {
    v8[0] = v2;
    v8[1] = 0;
    for ( i = 0; i != 5; ++i )
    {
      StringCchCopyW(v3, 0x105u, a1);
      StringCchCatW(v3, 0x105u, off_180021E60[i]);
      if ( !DeleteFileW(v3) && GetLastError() != 2 && GetLastError() != 3 )
      {
        v5 = -2147217407;
        goto LABEL_14;
      }
    }
    RemoveDirectoryW(a1);
    v5 = 0;
LABEL_14:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v8);
  }
  else
  {
    MemLogObject = GetMemLogObject();
    v5 = -2147217402;
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180013edc  mov     [rsp+arg_0], rbx
0x180013ee1  mov     [rsp+arg_8], rsi
0x180013ee6  push    rdi
0x180013ee7  sub     rsp, 30h
0x180013eeb  mov     rsi, rcx
0x180013eee  mov     ecx, 20Ah
0x180013ef3  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180013ef9  mov     rdi, rax
0x180013efc  test    rax, rax
0x180013eff  jnz     short loc_180013F60
0x180013f01  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180013f07  mov     ebx, 80041006h
0x180013f0c  mov     edx, ebx
0x180013f0e  mov     rcx, rax
0x180013f11  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180013f17  lea     rax, WPP_GLOBAL_Control
0x180013f1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013f25  cmp     rcx, rax
0x180013f28  jz      loc_180013FE3
0x180013f2e  test    byte ptr [rcx+1Ch], 1
0x180013f32  jz      loc_180013FE3
0x180013f38  cmp     byte ptr [rcx+19h], 2
0x180013f3c  jb      loc_180013FE3
0x180013f42  lea     edx, [rdi+3Ah]
0x180013f45  mov     r9d, 80041006h
0x180013f4b  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180013f52  mov     rcx, [rcx+10h]
0x180013f56  call    WPP_SF_d
0x180013f5b  jmp     loc_180013FE3
0x180013f60  mov     [rsp+38h+var_18], rdi
0x180013f65  mov     [rsp+38h+var_10], 0
0x180013f6e  xor     ebx, ebx
0x180013f70  cmp     ebx, 5
0x180013f73  jz      short loc_180013FCE
0x180013f75  mov     r8, rsi; unsigned __int16 *
0x180013f78  mov     edx, 105h; unsigned __int64
0x180013f7d  mov     rcx, rdi; unsigned __int16 *
0x180013f80  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013f85  movsxd  r8, ebx
0x180013f88  lea     rax, off_180021E60; "\\index.btr"
0x180013f8f  mov     r8, [rax+r8*8]; unsigned __int16 *
0x180013f93  mov     edx, 105h; unsigned __int64
0x180013f98  mov     rcx, rdi; unsigned __int16 *
0x180013f9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013fa0  mov     rcx, rdi; lpFileName
0x180013fa3  call    cs:__imp_DeleteFileW
0x180013fa9  test    eax, eax
0x180013fab  jnz     short loc_180013FC3
0x180013fad  call    cs:__imp_GetLastError
0x180013fb3  cmp     eax, 2
0x180013fb6  jz      short loc_180013FC3
0x180013fb8  call    cs:__imp_GetLastError
0x180013fbe  cmp     eax, 3
0x180013fc1  jnz     short loc_180013FC7
0x180013fc3  inc     ebx
0x180013fc5  jmp     short loc_180013F70
0x180013fc7  mov     ebx, 80041001h
0x180013fcc  jmp     short loc_180013FD9
0x180013fce  mov     rcx, rsi; lpPathName
0x180013fd1  call    cs:__imp_RemoveDirectoryW
0x180013fd7  xor     ebx, ebx
0x180013fd9  lea     rcx, [rsp+38h+var_18]
0x180013fde  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180013fe3  mov     eax, ebx
0x180013fe5  mov     rbx, [rsp+38h+arg_0]
0x180013fea  mov     rsi, [rsp+38h+arg_8]
0x180013fef  add     rsp, 30h
0x180013ff3  pop     rdi
0x180013ff4  retn
```

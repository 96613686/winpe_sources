# MoveRepositoryFiles(ushort const *,ushort const *,bool)

- ea: `0x1800142c0`
- end: `0x1800144a5`
- name: `?MoveRepositoryFiles@@YAJPEBG0_N@Z`
- size: `485`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, char)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800148e4`
- `0x1800149e8`

## callees

- `0x180004120`
- `0x180004c30`
- `0x18000b4f4`
- `0x180012c34`
- `0x1800142c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001445a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014465`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001445a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014465`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180014450`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180014450`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800142ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001437d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800142ff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001437d`
- `wbemcomn!GetMemLogObject` at `0x1800142ef`
- `wbemcomn!GetMemLogObject` at `0x18001436d`
- `wbemcomn!GetMemLogObject` at `0x1800142ef`
- `wbemcomn!GetMemLogObject` at `0x18001436d`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800142e1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001435f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800142e1`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001435f`

## pseudocode

```c
__int64 __fastcall MoveRepositoryFiles(const unsigned __int16 *a1, const unsigned __int16 *a2, char a3)
{
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rbp
  CMemoryLog *v8; // rax
  unsigned int v9; // edi
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rsi
  CMemoryLog *MemLogObject; // rax
  int i; // r14d
  unsigned int v14; // r11d
  const unsigned __int16 *v15; // rbx
  unsigned int v16; // r11d
  const WCHAR *v17; // rdx
  const WCHAR *v18; // rcx
  _QWORD v20[2]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v21[11]; // [rsp+30h] [rbp-58h] BYREF

  v6 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v7 = v6;
  if ( v6 )
  {
    v21[0] = v6;
    v21[1] = 0;
    v10 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
    v11 = v10;
    if ( v10 )
    {
      v20[0] = v10;
      v20[1] = 0;
      v9 = 0;
      for ( i = 0; i != 5; ++i )
      {
        StringCchCopyW(v7, 0x105u, a1);
        StringCchCopyW(v11, v14, a2);
        v15 = off_180021E90[i];
        StringCchCatW(v7, v16, v15);
        StringCchCatW(v11, 0x105u, v15);
        if ( a3 )
        {
          v17 = v11;
          v18 = v7;
        }
        else
        {
          v17 = v7;
          v18 = v11;
        }
        if ( !MoveFileExW(v18, v17, 2u) && GetLastError() != 2 && GetLastError() != 3 )
        {
          v9 = -2147217407;
          break;
        }
      }
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v20);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      v9 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
      }
    }
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v21);
  }
  else
  {
    v8 = GetMemLogObject();
    v9 = -2147217402;
    CMemoryLog::Write(v8, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800142c0  push    rbx
0x1800142c2  push    rbp
0x1800142c3  push    rsi
0x1800142c4  push    rdi
0x1800142c5  push    r12
0x1800142c7  push    r13
0x1800142c9  push    r14
0x1800142cb  push    r15
0x1800142cd  sub     rsp, 48h
0x1800142d1  mov     r15b, r8b
0x1800142d4  mov     r12, rdx
0x1800142d7  mov     r13, rcx
0x1800142da  mov     ebx, 20Ah
0x1800142df  mov     ecx, ebx
0x1800142e1  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800142e7  mov     rbp, rax
0x1800142ea  test    rax, rax
0x1800142ed  jnz     short loc_18001434E
0x1800142ef  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800142f5  mov     edi, 80041006h
0x1800142fa  mov     edx, edi
0x1800142fc  mov     rcx, rax
0x1800142ff  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014305  lea     rax, WPP_GLOBAL_Control
0x18001430c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014313  cmp     rcx, rax
0x180014316  jz      loc_180014492
0x18001431c  test    byte ptr [rcx+1Ch], 1
0x180014320  jz      loc_180014492
0x180014326  cmp     byte ptr [rcx+19h], 2
0x18001432a  jb      loc_180014492
0x180014330  lea     edx, [rbp+38h]
0x180014333  mov     r9d, 80041006h
0x180014339  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180014340  mov     rcx, [rcx+10h]
0x180014344  call    WPP_SF_d
0x180014349  jmp     loc_180014492
0x18001434e  mov     [rsp+88h+var_58], rbp
0x180014353  mov     [rsp+88h+var_50], 0
0x18001435c  mov     rcx, rbx
0x18001435f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014365  mov     rsi, rax
0x180014368  test    rax, rax
0x18001436b  jnz     short loc_1800143CC
0x18001436d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180014373  mov     edi, 80041006h
0x180014378  mov     edx, edi
0x18001437a  mov     rcx, rax
0x18001437d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180014383  lea     rax, WPP_GLOBAL_Control
0x18001438a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014391  cmp     rcx, rax
0x180014394  jz      loc_180014488
0x18001439a  test    byte ptr [rcx+1Ch], 1
0x18001439e  jz      loc_180014488
0x1800143a4  cmp     byte ptr [rcx+19h], 2
0x1800143a8  jb      loc_180014488
0x1800143ae  lea     edx, [rsi+39h]
0x1800143b1  mov     r9d, 80041006h
0x1800143b7  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x1800143be  mov     rcx, [rcx+10h]
0x1800143c2  call    WPP_SF_d
0x1800143c7  jmp     loc_180014488
0x1800143cc  mov     [rsp+88h+var_68], rsi
0x1800143d1  mov     [rsp+88h+var_60], 0
0x1800143da  xor     edi, edi
0x1800143dc  xor     r14d, r14d
0x1800143df  mov     r11d, 105h
0x1800143e5  cmp     r14d, 5
0x1800143e9  jz      loc_18001447D
0x1800143ef  mov     r8, r13; unsigned __int16 *
0x1800143f2  mov     edx, r11d; unsigned __int64
0x1800143f5  mov     rcx, rbp; unsigned __int16 *
0x1800143f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800143fd  mov     r8, r12; unsigned __int16 *
0x180014400  mov     edx, r11d; unsigned __int64
0x180014403  mov     rcx, rsi; unsigned __int16 *
0x180014406  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001440b  movsxd  r10, r14d
0x18001440e  lea     rbx, off_180021E90; "\\index.btr"
0x180014415  mov     rbx, [rbx+r10*8]
0x180014419  mov     r8, rbx; unsigned __int16 *
0x18001441c  mov     edx, r11d; unsigned __int64
0x18001441f  mov     rcx, rbp; unsigned __int16 *
0x180014422  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014427  mov     r8, rbx; unsigned __int16 *
0x18001442a  mov     edx, 105h; unsigned __int64
0x18001442f  mov     rcx, rsi; unsigned __int16 *
0x180014432  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180014437  mov     r8d, 2; dwFlags
0x18001443d  test    r15b, r15b
0x180014440  jz      short loc_18001444A
0x180014442  mov     rdx, rsi
0x180014445  mov     rcx, rbp
0x180014448  jmp     short loc_180014450
0x18001444a  mov     rdx, rbp; lpNewFileName
0x18001444d  mov     rcx, rsi; lpExistingFileName
0x180014450  call    cs:__imp_MoveFileExW
0x180014456  test    eax, eax
0x180014458  jnz     short loc_180014470
0x18001445a  call    cs:__imp_GetLastError
0x180014460  cmp     eax, 2
0x180014463  jz      short loc_180014470
0x180014465  call    cs:__imp_GetLastError
0x18001446b  cmp     eax, 3
0x18001446e  jnz     short loc_180014478
0x180014470  inc     r14d
0x180014473  jmp     loc_1800143DF
0x180014478  mov     edi, 80041001h
0x18001447d  lea     rcx, [rsp+88h+var_68]
0x180014482  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180014487  nop
0x180014488  lea     rcx, [rsp+88h+var_58]
0x18001448d  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180014492  mov     eax, edi
0x180014494  add     rsp, 48h
0x180014498  pop     r15
0x18001449a  pop     r14
0x18001449c  pop     r13
0x18001449e  pop     r12
0x1800144a0  pop     rdi
0x1800144a1  pop     rsi
0x1800144a2  pop     rbp
0x1800144a3  pop     rbx
0x1800144a4  retn
```

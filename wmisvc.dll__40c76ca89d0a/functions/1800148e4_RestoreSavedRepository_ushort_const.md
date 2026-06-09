# RestoreSavedRepository(ushort const *)

- ea: `0x1800148e4`
- end: `0x1800149df`
- name: `?RestoreSavedRepository@@YAJPEBG@Z`
- size: `251`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000dcdc`

## callees

- `0x180007bc4`
- `0x18000b4f4`
- `0x180012c34`
- `0x1800142c0`
- `0x1800148e4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180014990`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180014990`
- `wbemcomn!?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z` at `0x1800149a8`
- `wbemcomn!?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z` at `0x1800149bc`
- `wbemcomn!?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z` at `0x1800149a8`
- `wbemcomn!?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z` at `0x1800149bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014919`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180014919`
- `wbemcomn!GetMemLogObject` at `0x180014909`
- `wbemcomn!GetMemLogObject` at `0x180014909`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800148fb`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800148fb`

## pseudocode

```c
__int64 __fastcall RestoreSavedRepository(const unsigned __int16 *a1)
{
  WCHAR *v2; // rax
  const unsigned __int16 *v3; // rbx
  CMemoryLog *MemLogObject; // rax
  int RepositoryDirectory; // edi
  _QWORD v7[3]; // [rsp+20h] [rbp-18h] BYREF
  char v8; // [rsp+48h] [rbp+10h] BYREF

  v2 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v3 = v2;
  if ( v2 )
  {
    v7[0] = v2;
    v7[1] = 0;
    RepositoryDirectory = GetRepositoryDirectory(v2);
    if ( RepositoryDirectory >= 0 )
    {
      RepositoryDirectory = MoveRepositoryFiles(v3, a1, 0);
      if ( RepositoryDirectory >= 0 )
        RemoveDirectoryW(a1);
    }
    v8 = 0;
    CPersistentConfig::SetPersistentCfgValue((CPersistentConfig *)&v8, 1u, 1u);
    CPersistentConfig::SetPersistentCfgValue((CPersistentConfig *)&v8, 4u, 1u);
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v7);
    return (unsigned int)RepositoryDirectory;
  }
  else
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217402);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
}

```

## disassembly

```asm
0x1800148e4  mov     [rsp+arg_0], rbx
0x1800148e9  mov     [rsp+arg_10], rsi
0x1800148ee  push    rdi
0x1800148ef  sub     rsp, 30h
0x1800148f3  mov     rsi, rcx
0x1800148f6  mov     ecx, 20Ah
0x1800148fb  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180014901  mov     rbx, rax
0x180014904  test    rax, rax
0x180014907  jnz     short loc_18001495D
0x180014909  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18001490f  mov     ebx, 80041006h
0x180014914  mov     edx, ebx
0x180014916  mov     rcx, rax
0x180014919  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18001491f  lea     rax, WPP_GLOBAL_Control
0x180014926  mov     rcx, cs:WPP_GLOBAL_Control
0x18001492d  cmp     rcx, rax
0x180014930  jz      short loc_180014959
0x180014932  test    byte ptr [rcx+1Ch], 1
0x180014936  jz      short loc_180014959
0x180014938  cmp     byte ptr [rcx+19h], 2
0x18001493c  jb      short loc_180014959
0x18001493e  mov     edx, 37h ; '7'
0x180014943  mov     r9d, 80041006h
0x180014949  lea     r8, WPP_da0c108f5fb630a241f44bac5f55929c_Traceguids
0x180014950  mov     rcx, [rcx+10h]
0x180014954  call    WPP_SF_d
0x180014959  mov     eax, ebx
0x18001495b  jmp     short loc_1800149CF
0x18001495d  mov     [rsp+38h+var_18], rbx
0x180014962  mov     [rsp+38h+var_10], 0
0x18001496b  mov     rcx, rbx; lpDst
0x18001496e  call    ?GetRepositoryDirectory@@YAJQEAG@Z; GetRepositoryDirectory(ushort * const)
0x180014973  mov     edi, eax
0x180014975  test    eax, eax
0x180014977  js      short loc_180014996
0x180014979  xor     r8d, r8d; bool
0x18001497c  mov     rdx, rsi; unsigned __int16 *
0x18001497f  mov     rcx, rbx; unsigned __int16 *
0x180014982  call    ?MoveRepositoryFiles@@YAJPEBG0_N@Z; MoveRepositoryFiles(ushort const *,ushort const *,bool)
0x180014987  mov     edi, eax
0x180014989  test    eax, eax
0x18001498b  js      short loc_180014996
0x18001498d  mov     rcx, rsi; lpPathName
0x180014990  call    cs:__imp_RemoveDirectoryW
0x180014996  mov     [rsp+38h+arg_8], 0
0x18001499b  mov     edx, 1
0x1800149a0  mov     r8d, edx
0x1800149a3  lea     rcx, [rsp+38h+arg_8]
0x1800149a8  call    cs:__imp_?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z; CPersistentConfig::SetPersistentCfgValue(ulong,ulong)
0x1800149ae  mov     edx, 4
0x1800149b3  lea     r8d, [rdx-3]
0x1800149b7  lea     rcx, [rsp+38h+arg_8]
0x1800149bc  call    cs:__imp_?SetPersistentCfgValue@CPersistentConfig@@QEAAHKK@Z; CPersistentConfig::SetPersistentCfgValue(ulong,ulong)
0x1800149c2  nop
0x1800149c3  lea     rcx, [rsp+38h+var_18]
0x1800149c8  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x1800149cd  mov     eax, edi
0x1800149cf  mov     rbx, [rsp+38h+arg_0]
0x1800149d4  mov     rsi, [rsp+38h+arg_10]
0x1800149d9  add     rsp, 30h
0x1800149dd  pop     rdi
0x1800149de  retn
```

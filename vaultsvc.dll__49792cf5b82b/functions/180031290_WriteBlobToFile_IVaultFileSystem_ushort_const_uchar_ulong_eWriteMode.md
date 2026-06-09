# WriteBlobToFile(IVaultFileSystem *,ushort const *,uchar *,ulong,eWriteMode)

- ea: `0x180031290`
- end: `0x1800314e2`
- name: `?WriteBlobToFile@@YAKPEAUIVaultFileSystem@@PEBGPEAEKW4eWriteMode@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(struct IVaultFileSystem *, __int64, const void *, DWORD, DWORD NumberOfBytesWritten)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f7d0`
- `0x18001ab50`
- `0x180039ea8`

## callees

- `0x180003140`
- `0x180031290`
- `0x180040108`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003148f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003148f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800312b5`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031334`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180031334`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003137a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18003137a`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031354`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180031354`

## pseudocode

```c
__int64 __fastcall WriteBlobToFile(
        struct IVaultFileSystem *a1,
        __int64 a2,
        const void *a3,
        DWORD a4,
        DWORD NumberOfBytesWritten)
{
  struct IVaultFileSystem *v8; // rbx
  struct IVaultFileSystem *v9; // rdi
  unsigned int v10; // esi
  DWORD LastError; // ebx
  BOOL (__stdcall *v13)(HANDLE); // [rsp+30h] [rbp-30h] BYREF
  HANDLE hFile; // [rsp+38h] [rbp-28h] BYREF
  int v15; // [rsp+40h] [rbp-20h]
  __int64 (__fastcall *v16)(); // [rsp+48h] [rbp-18h] BYREF
  struct IVaultFileSystem *v17; // [rsp+50h] [rbp-10h] BYREF
  int v18; // [rsp+58h] [rbp-8h]
  union _LARGE_INTEGER FileSize; // [rsp+90h] [rbp+30h] BYREF

  v8 = a1;
  v13 = CloseHandle;
  hFile = 0;
  v15 = 0;
  NumberOfBytesWritten = 0;
  FileSize.QuadPart = 0;
  v16 = AutoDereference<IVaultKeyManager>;
  v9 = 0;
  v17 = 0;
  v18 = 0;
  if ( !a1 )
  {
    LastError = CVaultTransacted::CreateNewFileSystem(&v17);
    if ( LastError )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return LastError;
    }
    v9 = v17;
    v8 = v17;
    v10 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v10 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return v10;
    }
  }
  v10 = (*(__int64 (__fastcall **)(struct IVaultFileSystem *, __int64, __int64, __int64, HANDLE *))(*(_QWORD *)v8 + 32LL))(
          v8,
          a2,
          3221225472LL,
          1,
          &hFile);
  if ( v10 )
  {
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
    return v10;
  }
  if ( !GetFileSizeEx(hFile, &FileSize) )
  {
LABEL_9:
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
    return LastError;
  }
  if ( FileSize.HighPart == v10 )
  {
    if ( SetFilePointer(hFile, FileSize.LowPart, 0, 0) != -1 && WriteFile(hFile, a3, a4, &NumberOfBytesWritten, 0) )
    {
      if ( v8 != v9
        || (LastError = (*(__int64 (__fastcall **)(struct IVaultFileSystem *))(*(_QWORD *)v8 + 24LL))(v8)) == 0 )
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
        return 0;
      }
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
      return LastError;
    }
    goto LABEL_9;
  }
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v16);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v13);
  return 223;
}

```

## disassembly

```asm
0x180031290  mov     [rsp-28h+arg_8], rbx
0x180031295  mov     [rsp-28h+arg_10], rsi
0x18003129a  push    rbp
0x18003129b  push    rdi
0x18003129c  push    r12
0x18003129e  push    r14
0x1800312a0  push    r15
0x1800312a2  mov     rbp, rsp
0x1800312a5  sub     rsp, 60h
0x1800312a9  mov     r14d, r9d
0x1800312ac  mov     r15, r8
0x1800312af  mov     r12, rdx
0x1800312b2  mov     rbx, rcx
0x1800312b5  mov     rax, cs:__imp_CloseHandle
0x1800312bc  mov     [rbp+var_30], rax
0x1800312c0  mov     [rbp+hFile], 0
0x1800312c8  mov     [rbp+var_20], 0
0x1800312cf  mov     [rbp+NumberOfBytesWritten], 0
0x1800312d6  mov     qword ptr [rbp+FileSize], 0
0x1800312de  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x1800312e5  mov     [rbp+var_18], rax
0x1800312e9  xor     edi, edi
0x1800312eb  mov     [rbp+var_10], rdi
0x1800312ef  mov     [rbp+var_8], edi
0x1800312f2  test    rcx, rcx
0x1800312f5  jz      loc_1800313FB
0x1800312fb  mov     rax, [rbx]
0x1800312fe  lea     rcx, [rbp+hFile]
0x180031302  mov     [rsp+60h+lpOverlapped], rcx
0x180031307  mov     r9d, 1
0x18003130d  mov     r8d, 0C0000000h
0x180031313  mov     rdx, r12
0x180031316  mov     rcx, rbx
0x180031319  mov     rax, [rax+20h]
0x18003131d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031322  mov     esi, eax
0x180031324  test    eax, eax
0x180031326  jnz     loc_180031456
0x18003132c  lea     rdx, [rbp+FileSize]; lpFileSize
0x180031330  mov     rcx, [rbp+hFile]; hFile
0x180031334  call    cs:__imp_GetFileSizeEx
0x18003133a  test    eax, eax
0x18003133c  jz      short loc_1800313A5
0x18003133e  cmp     dword ptr [rbp+FileSize+4], esi
0x180031341  jnz     loc_180031471
0x180031347  xor     r9d, r9d; dwMoveMethod
0x18003134a  xor     r8d, r8d; lpDistanceToMoveHigh
0x18003134d  mov     edx, dword ptr [rbp+FileSize]; lDistanceToMove
0x180031350  mov     rcx, [rbp+hFile]; hFile
0x180031354  call    cs:__imp_SetFilePointer
0x18003135a  cmp     eax, 0FFFFFFFFh
0x18003135d  jz      loc_18003148F
0x180031363  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18003136c  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180031370  mov     r8d, r14d; nNumberOfBytesToWrite
0x180031373  mov     rdx, r15; lpBuffer
0x180031376  mov     rcx, [rbp+hFile]; hFile
0x18003137a  call    cs:__imp_WriteFile
0x180031380  test    eax, eax
0x180031382  jz      short loc_1800313DC
0x180031384  cmp     rbx, rdi
0x180031387  jz      loc_1800314B0
0x18003138d  lea     rcx, [rbp+var_18]
0x180031391  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031396  nop
0x180031397  lea     rcx, [rbp+var_30]
0x18003139b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800313a0  nop
0x1800313a1  xor     eax, eax
0x1800313a3  jmp     short loc_1800313C3
0x1800313a5  call    cs:__imp_GetLastError
0x1800313ab  mov     ebx, eax
0x1800313ad  lea     rcx, [rbp+var_18]
0x1800313b1  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800313b6  nop
0x1800313b7  lea     rcx, [rbp+var_30]
0x1800313bb  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800313c0  nop
0x1800313c1  mov     eax, ebx
0x1800313c3  lea     r11, [rsp+60h+var_s0]
0x1800313c8  mov     rbx, [r11+38h]
0x1800313cc  mov     rsi, [r11+40h]
0x1800313d0  mov     rsp, r11
0x1800313d3  pop     r15
0x1800313d5  pop     r14
0x1800313d7  pop     r12
0x1800313d9  pop     rdi
0x1800313da  pop     rbp
0x1800313db  retn
0x1800313dc  call    cs:__imp_GetLastError
0x1800313e2  nop
0x1800313e3  mov     ebx, eax
0x1800313e5  lea     rcx, [rbp+var_18]
0x1800313e9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800313ee  nop
0x1800313ef  lea     rcx, [rbp+var_30]
0x1800313f3  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800313f8  nop
0x1800313f9  jmp     short loc_1800313C1
0x1800313fb  lea     rcx, [rbp+var_10]; struct IVaultFileSystem **
0x1800313ff  call    ?CreateNewFileSystem@CVaultTransacted@@SAKPEAPEAUIVaultFileSystem@@@Z; CVaultTransacted::CreateNewFileSystem(IVaultFileSystem * *)
0x180031404  mov     ebx, eax
0x180031406  test    eax, eax
0x180031408  jz      short loc_180031420
0x18003140a  lea     rcx, [rbp+var_18]
0x18003140e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031413  nop
0x180031414  lea     rcx, [rbp+var_30]
0x180031418  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003141d  nop
0x18003141e  jmp     short loc_1800313C1
0x180031420  mov     rdi, [rbp+var_10]
0x180031424  mov     rbx, rdi
0x180031427  mov     rax, [rdi]
0x18003142a  mov     rcx, rdi
0x18003142d  mov     rax, [rax+10h]
0x180031431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031436  mov     esi, eax
0x180031438  test    eax, eax
0x18003143a  jz      loc_1800312FB
0x180031440  lea     rcx, [rbp+var_18]
0x180031444  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031449  nop
0x18003144a  lea     rcx, [rbp+var_30]
0x18003144e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031453  nop
0x180031454  jmp     short loc_18003146A
0x180031456  lea     rcx, [rbp+var_18]
0x18003145a  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003145f  nop
0x180031460  lea     rcx, [rbp+var_30]
0x180031464  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031469  nop
0x18003146a  mov     eax, esi
0x18003146c  jmp     loc_1800313C3
0x180031471  lea     rcx, [rbp+var_18]
0x180031475  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18003147a  nop
0x18003147b  lea     rcx, [rbp+var_30]
0x18003147f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180031484  nop
0x180031485  mov     eax, 0DFh
0x18003148a  jmp     loc_1800313C3
0x18003148f  call    cs:__imp_GetLastError
0x180031495  mov     ebx, eax
0x180031497  lea     rcx, [rbp+var_18]
0x18003149b  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800314a0  nop
0x1800314a1  lea     rcx, [rbp+var_30]
0x1800314a5  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800314aa  nop
0x1800314ab  jmp     loc_1800313C1
0x1800314b0  mov     rax, [rbx]
0x1800314b3  mov     rcx, rbx
0x1800314b6  mov     rax, [rax+18h]
0x1800314ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314bf  mov     ebx, eax
0x1800314c1  test    eax, eax
0x1800314c3  jz      loc_18003138D
0x1800314c9  lea     rcx, [rbp+var_18]
0x1800314cd  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800314d2  nop
0x1800314d3  lea     rcx, [rbp+var_30]
0x1800314d7  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800314dc  nop
0x1800314dd  jmp     loc_1800313C1
```

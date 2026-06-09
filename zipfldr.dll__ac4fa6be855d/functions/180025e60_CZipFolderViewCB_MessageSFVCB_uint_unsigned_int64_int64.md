# CZipFolderViewCB::MessageSFVCB(uint,unsigned __int64,__int64)

- ea: `0x180025e60`
- end: `0x180025f3d`
- name: `?MessageSFVCB@CZipFolderViewCB@@UEAAJI_K_J@Z`
- size: `221`
- prototype: `int(CZipFolderViewCB *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180025e60`
- `0x1800350a0`
- `0x1800468b0`

## import_xrefs

- `SHELL32!SHAddToRecentDocs` at `0x180025f29`
- `SHELL32!SHAddToRecentDocs` at `0x180025f29`
- `SHELL32!__imp_Create_IEnumUICommand` at `0x180025ec1`
- `SHELL32!__imp_Create_IEnumUICommand` at `0x180025ec1`
- `SHLWAPI!__imp_SHCreateThread` at `0x180025f06`
- `SHLWAPI!__imp_SHCreateThread` at `0x180025f06`

## pseudocode

```c
__int64 __fastcall CZipFolderViewCB::MessageSFVCB(CZipFolderViewCB *this, int a2, _QWORD *a3, __int64 a4)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  unsigned int v10; // ebx

  v4 = a2 - 15;
  if ( !v4 )
  {
    SHAddToRecentDocs(1u, *(LPCVOID *)(*((_QWORD *)this + 4) + 1112LL));
    _InterlockedIncrement(&CZipFolderViewCB::s_cWindows);
    return 0;
  }
  v5 = v4 - 1;
  if ( v5 )
  {
    v6 = v5 - 11;
    if ( v6 )
    {
      v7 = v6 - 22;
      if ( v7 )
      {
        v8 = v7 - 14;
        if ( !v8 )
          return CZipFolderViewCB::_OnGetHelpTopic(this, 0, (struct _SFVM_HELPTOPIC_DATA *)a4);
        if ( v8 != 21 )
          return 2147500037LL;
        *(_OWORD *)a4 = 0;
        *(_QWORD *)(a4 + 16) = 0;
        Create_IEnumUICommand(this, &off_1800745B0, 1);
      }
      else
      {
        *a3 = *(_QWORD *)(*((_QWORD *)this + 4) + 1112LL);
        *(_DWORD *)a4 = 145439;
      }
    }
    else
    {
      *(_DWORD *)a4 = 4;
    }
    return 0;
  }
  v10 = 0;
  if ( _InterlockedExchangeAdd(&CZipFolderViewCB::s_cWindows, 0xFFFFFFFF) == 1
    && !SHCreateThread(CZipFolderViewCB::s_DeleteTempZipFilesThreadProc, 0, 8u, 0) )
  {
    return (unsigned int)ResultFromKnownLastError();
  }
  return v10;
}

```

## disassembly

```asm
0x180025e60  push    rbx
0x180025e62  sub     rsp, 20h
0x180025e66  sub     edx, 0Fh
0x180025e69  jz      loc_180025F19
0x180025e6f  sub     edx, 1
0x180025e72  jz      short loc_180025E93
0x180025e74  sub     edx, 0Bh
0x180025e77  jz      short loc_180025EED
0x180025e79  sub     edx, 16h
0x180025e7c  jz      short loc_180025ED6
0x180025e7e  sub     edx, 0Eh; unsigned int
0x180025e81  jz      short loc_180025EC9
0x180025e83  cmp     edx, 15h
0x180025e86  jz      short loc_180025EA9
0x180025e88  mov     eax, 80004005h
0x180025e8d  add     rsp, 20h
0x180025e91  pop     rbx
0x180025e92  retn
0x180025e93  xor     ebx, ebx
0x180025e95  or      eax, 0FFFFFFFFh
0x180025e98  lock xadd cs:?s_cWindows@CZipFolderViewCB@@0JA, eax; long CZipFolderViewCB::s_cWindows
0x180025ea0  cmp     eax, 1
0x180025ea3  jz      short loc_180025EF6
0x180025ea5  mov     eax, ebx
0x180025ea7  jmp     short loc_180025E8D
0x180025ea9  xor     eax, eax
0x180025eab  lea     rdx, off_1800745B0
0x180025eb2  xorps   xmm0, xmm0
0x180025eb5  movups  xmmword ptr [r9], xmm0
0x180025eb9  mov     [r9+10h], rax
0x180025ebd  lea     r8d, [rax+1]
0x180025ec1  call    cs:__imp_Create_IEnumUICommand
0x180025ec7  jmp     short loc_180025F36
0x180025ec9  mov     r8, r9; struct _SFVM_HELPTOPIC_DATA *
0x180025ecc  add     rsp, 20h
0x180025ed0  pop     rbx
0x180025ed1  jmp     ?_OnGetHelpTopic@CZipFolderViewCB@@AEAAJKPEAU_SFVM_HELPTOPIC_DATA@@@Z; CZipFolderViewCB::_OnGetHelpTopic(ulong,_SFVM_HELPTOPIC_DATA *)
0x180025ed6  mov     rax, [rcx+20h]
0x180025eda  mov     rcx, [rax+458h]
0x180025ee1  mov     [r8], rcx
0x180025ee4  mov     dword ptr [r9], 2381Fh
0x180025eeb  jmp     short loc_180025F36
0x180025eed  mov     dword ptr [r9], 4
0x180025ef4  jmp     short loc_180025F36
0x180025ef6  xor     r9d, r9d; pfnCallback
0x180025ef9  lea     rcx, ?s_DeleteTempZipFilesThreadProc@CZipFolderViewCB@@CAKPEAX@Z; pfnThreadProc
0x180025f00  xor     edx, edx; pData
0x180025f02  lea     r8d, [r9+8]; flags
0x180025f06  call    cs:__imp_SHCreateThread
0x180025f0c  test    eax, eax
0x180025f0e  jnz     short loc_180025EA5
0x180025f10  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180025f15  mov     ebx, eax
0x180025f17  jmp     short loc_180025EA5
0x180025f19  mov     rdx, [rcx+20h]
0x180025f1d  mov     ecx, 1; uFlags
0x180025f22  mov     rdx, [rdx+458h]; pv
0x180025f29  call    cs:__imp_SHAddToRecentDocs
0x180025f2f  lock inc cs:?s_cWindows@CZipFolderViewCB@@0JA; long CZipFolderViewCB::s_cWindows
0x180025f36  xor     eax, eax
0x180025f38  jmp     loc_180025E8D
```

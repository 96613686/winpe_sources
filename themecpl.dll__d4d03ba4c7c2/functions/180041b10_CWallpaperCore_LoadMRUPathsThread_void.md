# CWallpaperCore::_LoadMRUPathsThread(void *)

- ea: `0x180041b10`
- end: `0x180041bf8`
- name: `?_LoadMRUPathsThread@CWallpaperCore@@CAKPEAX@Z`
- size: `232`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18003dbc8`
- `0x180041b10`
- `0x180041f98`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetNameFromIDList` at `0x180041b6b`
- `SHELL32!SHGetNameFromIDList` at `0x180041b6b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041bb8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180041bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041ba5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041b94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041ba5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041b24`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041b24`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_LoadMRUPathsThread(volatile signed __int32 *a1)
{
  int v2; // edi
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp+8h] BYREF
  PWSTR ppszName; // [rsp+38h] [rbp+10h] BYREF

  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    v2 = -2;
    do
    {
      pidl = 0;
      if ( (int)CWallpaperCore::_LoadUserPath((unsigned int)v2, (LPITEMIDLIST *)&pidl) >= 0 )
      {
        ppszName = 0;
        if ( SHGetNameFromIDList(pidl, SIGDN_NORMALDISPLAY, &ppszName) >= 0 )
        {
          CTaskQueueItem::PostResult(a1, 0, pidl, ppszName);
          CoTaskMemFree(ppszName);
        }
        CoTaskMemFree((LPVOID)pidl);
      }
      ++v2;
    }
    while ( v2 <= 3 );
    CoUninitialize();
  }
  if ( _InterlockedExchangeAdd(a1 + 26, 0xFFFFFFFF) == 1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return 0;
}

```

## disassembly

```asm
0x180041b10  mov     [rsp+arg_10], rbx
0x180041b15  push    rdi
0x180041b16  sub     rsp, 20h
0x180041b1a  mov     rbx, rcx
0x180041b1d  mov     edx, 6; dwCoInit
0x180041b22  xor     ecx, ecx; pvReserved
0x180041b24  call    cs:__imp_CoInitializeEx
0x180041b2b  nop     dword ptr [rax+rax+00h]
0x180041b30  test    eax, eax
0x180041b32  js      loc_180041BC4
0x180041b38  mov     edi, 0FFFFFFFEh
0x180041b3d  lea     rdx, [rsp+28h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180041b42  mov     [rsp+28h+pidl], 0
0x180041b4b  mov     ecx, edi; int
0x180041b4d  call    ?_LoadUserPath@CWallpaperCore@@CAJHPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CWallpaperCore::_LoadUserPath(int,_ITEMIDLIST_ABSOLUTE * *)
0x180041b52  test    eax, eax
0x180041b54  js      short loc_180041BB1
0x180041b56  mov     rcx, [rsp+28h+pidl]; pidl
0x180041b5b  lea     r8, [rsp+28h+ppszName]; ppszName
0x180041b60  xor     edx, edx; sigdnName
0x180041b62  mov     [rsp+28h+ppszName], 0
0x180041b6b  call    cs:__imp_SHGetNameFromIDList
0x180041b72  nop     dword ptr [rax+rax+00h]
0x180041b77  test    eax, eax
0x180041b79  js      short loc_180041BA0
0x180041b7b  mov     r9, [rsp+28h+ppszName]
0x180041b80  xor     edx, edx
0x180041b82  mov     r8, [rsp+28h+pidl]
0x180041b87  mov     rcx, rbx
0x180041b8a  call    ?PostResult@CTaskQueueItem@@SAJPEAVCDefTaskLock@@W4PATH_TASK_ID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBG@Z; CTaskQueueItem::PostResult(CDefTaskLock *,PATH_TASK_ID,_ITEMIDLIST_ABSOLUTE const *,ushort const *)
0x180041b8f  mov     rcx, [rsp+28h+ppszName]; pv
0x180041b94  call    cs:__imp_CoTaskMemFree
0x180041b9b  nop     dword ptr [rax+rax+00h]
0x180041ba0  mov     rcx, [rsp+28h+pidl]; pv
0x180041ba5  call    cs:__imp_CoTaskMemFree
0x180041bac  nop     dword ptr [rax+rax+00h]
0x180041bb1  inc     edi
0x180041bb3  cmp     edi, 3
0x180041bb6  jle     short loc_180041B3D
0x180041bb8  call    cs:__imp_CoUninitialize
0x180041bbf  nop     dword ptr [rax+rax+00h]
0x180041bc4  or      eax, 0FFFFFFFFh
0x180041bc7  lock xadd [rbx+68h], eax
0x180041bcc  cmp     eax, 1
0x180041bcf  jnz     short loc_180041BEA
0x180041bd1  test    rbx, rbx
0x180041bd4  jz      short loc_180041BEA
0x180041bd6  mov     rax, [rbx]
0x180041bd9  mov     edx, 1
0x180041bde  mov     rcx, rbx
0x180041be1  mov     rax, [rax+10h]
0x180041be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bea  mov     rbx, [rsp+28h+arg_10]
0x180041bef  xor     eax, eax
0x180041bf1  add     rsp, 20h
0x180041bf5  pop     rdi
0x180041bf6  retn
```

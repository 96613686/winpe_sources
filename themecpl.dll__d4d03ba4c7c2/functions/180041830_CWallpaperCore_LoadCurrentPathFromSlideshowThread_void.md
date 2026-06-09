# CWallpaperCore::_LoadCurrentPathFromSlideshowThread(void *)

- ea: `0x180041830`
- end: `0x1800418f7`
- name: `?_LoadCurrentPathFromSlideshowThread@CWallpaperCore@@CAKPEAX@Z`
- size: `199`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x180002650`
- `0x18003dbc8`
- `0x180041830`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetNameFromIDList` at `0x180041863`
- `SHELL32!SHGetNameFromIDList` at `0x180041863`
- `SHELL32!__imp_ILFree` at `0x1800418ae`
- `SHELL32!__imp_ILFree` at `0x1800418ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004189a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18004189a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004188e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004188e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041840`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180041840`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_LoadCurrentPathFromSlideshowThread(const ITEMIDLIST **a1)
{
  const ITEMIDLIST *v2; // rcx
  volatile signed __int32 *v3; // rcx
  PWSTR ppszName; // [rsp+30h] [rbp+8h] BYREF

  if ( CoInitializeEx(0, 6u) >= 0 )
  {
    v2 = *a1;
    ppszName = 0;
    if ( SHGetNameFromIDList(v2, SIGDN_NORMALDISPLAY, &ppszName) >= 0 )
    {
      CTaskQueueItem::PostResult(a1[1], 2, *a1, ppszName);
      CoTaskMemFree(ppszName);
    }
    CoUninitialize();
  }
  if ( a1 )
  {
    ILFree((LPITEMIDLIST)*a1);
    v3 = (volatile signed __int32 *)a1[1];
    if ( v3 && _InterlockedExchangeAdd(v3 + 26, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v3 + 16LL))(v3, 1);
    operator delete(a1, (const struct std::nothrow_t *)0x10);
  }
  return 0;
}

```

## disassembly

```asm
0x180041830  push    rbx
0x180041832  sub     rsp, 20h
0x180041836  mov     rbx, rcx
0x180041839  mov     edx, 6; dwCoInit
0x18004183e  xor     ecx, ecx; pvReserved
0x180041840  call    cs:__imp_CoInitializeEx
0x180041847  nop     dword ptr [rax+rax+00h]
0x18004184c  test    eax, eax
0x18004184e  js      short loc_1800418A6
0x180041850  mov     rcx, [rbx]; pidl
0x180041853  lea     r8, [rsp+28h+ppszName]; ppszName
0x180041858  xor     edx, edx; sigdnName
0x18004185a  mov     [rsp+28h+ppszName], 0
0x180041863  call    cs:__imp_SHGetNameFromIDList
0x18004186a  nop     dword ptr [rax+rax+00h]
0x18004186f  test    eax, eax
0x180041871  js      short loc_18004189A
0x180041873  mov     r9, [rsp+28h+ppszName]
0x180041878  mov     edx, 2
0x18004187d  mov     r8, [rbx]
0x180041880  mov     rcx, [rbx+8]
0x180041884  call    ?PostResult@CTaskQueueItem@@SAJPEAVCDefTaskLock@@W4PATH_TASK_ID@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBG@Z; CTaskQueueItem::PostResult(CDefTaskLock *,PATH_TASK_ID,_ITEMIDLIST_ABSOLUTE const *,ushort const *)
0x180041889  mov     rcx, [rsp+28h+ppszName]; pv
0x18004188e  call    cs:__imp_CoTaskMemFree
0x180041895  nop     dword ptr [rax+rax+00h]
0x18004189a  call    cs:__imp_CoUninitialize
0x1800418a1  nop     dword ptr [rax+rax+00h]
0x1800418a6  test    rbx, rbx
0x1800418a9  jz      short loc_1800418EE
0x1800418ab  mov     rcx, [rbx]; pidl
0x1800418ae  call    cs:__imp_ILFree
0x1800418b5  nop     dword ptr [rax+rax+00h]
0x1800418ba  mov     rcx, [rbx+8]
0x1800418be  test    rcx, rcx
0x1800418c1  jz      short loc_1800418E1
0x1800418c3  or      eax, 0FFFFFFFFh
0x1800418c6  lock xadd [rcx+68h], eax
0x1800418cb  cmp     eax, 1
0x1800418ce  jnz     short loc_1800418E1
0x1800418d0  mov     rax, [rcx]
0x1800418d3  mov     edx, 1
0x1800418d8  mov     rax, [rax+10h]
0x1800418dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418e1  mov     edx, 10h; struct std::nothrow_t *
0x1800418e6  mov     rcx, rbx; void *
0x1800418e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800418ee  xor     eax, eax
0x1800418f0  add     rsp, 20h
0x1800418f4  pop     rbx
0x1800418f5  retn
```

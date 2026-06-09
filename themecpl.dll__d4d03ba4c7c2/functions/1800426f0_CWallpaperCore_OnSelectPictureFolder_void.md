# CWallpaperCore::_OnSelectPictureFolder(void)

- ea: `0x1800426f0`
- end: `0x180042775`
- name: `?_OnSelectPictureFolder@CWallpaperCore@@AEAAXXZ`
- size: `133`
- prototype: `void __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003ca90`
- `0x18003d150`

## callees

- `0x1800426f0`
- `0x18004277c`
- `0x180043624`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004275d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180042728`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004275d`

## pseudocode

```c
void __fastcall CWallpaperCore::_OnSelectPictureFolder(CWallpaperCore *this)
{
  __int64 v2; // rcx
  int MonitorWithWallpaper; // eax
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((_QWORD *)this + 52);
  pv = 0;
  MonitorWithWallpaper = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID *))(*(_QWORD *)v2 + 32LL))(v2, 0, &pv);
  if ( MonitorWithWallpaper == 1 )
  {
    CoTaskMemFree(pv);
    MonitorWithWallpaper = CWallpaperCore::_PathOfFirstMonitorWithWallpaper(this, (unsigned __int16 **)&pv);
  }
  if ( MonitorWithWallpaper >= 0 )
  {
    CWallpaperCore::_UpdatePictureFolder(this, *(_WORD *)pv != 0);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x1800426f0  mov     [rsp+arg_8], rbx
0x1800426f5  push    rdi
0x1800426f6  sub     rsp, 20h
0x1800426fa  mov     rbx, rcx
0x1800426fd  lea     r8, [rsp+28h+pv]
0x180042702  mov     rcx, [rcx+1A0h]
0x180042709  xor     edi, edi
0x18004270b  mov     [rsp+28h+pv], rdi
0x180042710  xor     edx, edx
0x180042712  mov     rax, [rcx]
0x180042715  mov     rax, [rax+20h]
0x180042719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004271e  cmp     eax, 1
0x180042721  jnz     short loc_180042741
0x180042723  mov     rcx, [rsp+28h+pv]; pv
0x180042728  call    cs:__imp_CoTaskMemFree
0x18004272f  nop     dword ptr [rax+rax+00h]
0x180042734  lea     rdx, [rsp+28h+pv]; unsigned __int16 **
0x180042739  mov     rcx, rbx; this
0x18004273c  call    ?_PathOfFirstMonitorWithWallpaper@CWallpaperCore@@AEAAJPEAPEAG@Z; CWallpaperCore::_PathOfFirstMonitorWithWallpaper(ushort * *)
0x180042741  test    eax, eax
0x180042743  js      short loc_180042769
0x180042745  mov     rax, [rsp+28h+pv]
0x18004274a  mov     rcx, rbx; this
0x18004274d  cmp     [rax], di
0x180042750  setnz   dl; bool
0x180042753  call    ?_UpdatePictureFolder@CWallpaperCore@@AEAAX_N@Z; CWallpaperCore::_UpdatePictureFolder(bool)
0x180042758  mov     rcx, [rsp+28h+pv]; pv
0x18004275d  call    cs:__imp_CoTaskMemFree
0x180042764  nop     dword ptr [rax+rax+00h]
0x180042769  mov     rbx, [rsp+28h+arg_8]
0x18004276e  add     rsp, 20h
0x180042772  pop     rdi
0x180042773  retn
```

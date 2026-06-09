# WimCbRemoveOverlay

- ea: `0x140027410`
- end: `0x1400274ef`
- name: `WimCbRemoveOverlay`
- size: `223`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x14000c3bc`
- `0x14000d250`
- `0x14000fd74`
- `0x140022cf4`
- `0x140027410`
- `0x14002b7cc`
- `0x14003c44c`

## pseudocode

```c
__int64 __fastcall WimCbRemoveOverlay(__int64 a1, _QWORD *a2, unsigned int a3)
{
  int v6; // esi
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = 0;
  if ( a3 < 8 )
    return 3221225485LL;
  WimFSFAcquireConfigLock(a1);
  v6 = WimRemoveOverlay(a1 - (unsigned int)dword_14001A2FC, *a2);
  WimFSFReleaseConfigLock(a1);
  if ( v6 >= 0 )
  {
    v8 = WimFSFFindOverlayByDataSource(a1, *a2, &v10);
    if ( v8 >= 0 )
    {
      WimFSFDismountOverlay(v10, 2);
    }
    else if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 17, v9, *a2);
    }
    return (unsigned int)v8;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 16, v7, *a2);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x140027410  mov     [rsp+arg_0], rbx
0x140027415  mov     [rsp+arg_10], rsi
0x14002741a  push    rdi
0x14002741b  sub     rsp, 20h
0x14002741f  mov     [rsp+28h+arg_8], 0
0x140027428  mov     rbx, rdx
0x14002742b  mov     rdi, rcx
0x14002742e  cmp     r8d, 8
0x140027432  jnb     short loc_14002743E
0x140027434  mov     eax, 0C000000Dh
0x140027439  jmp     loc_1400274DE
0x14002743e  call    WimFSFAcquireConfigLock
0x140027443  mov     eax, cs:dword_14001A2FC
0x140027449  mov     rcx, rdi
0x14002744c  mov     rdx, [rbx]
0x14002744f  sub     rcx, rax
0x140027452  call    WimRemoveOverlay
0x140027457  mov     rcx, rdi
0x14002745a  mov     esi, eax
0x14002745c  call    WimFSFReleaseConfigLock
0x140027461  test    esi, esi
0x140027463  jns     short loc_14002748F
0x140027465  mov     rcx, cs:WPP_GLOBAL_Control
0x14002746c  mov     edx, [rcx+2Ch]
0x14002746f  test    dl, 8
0x140027472  jz      short loc_14002748B
0x140027474  cmp     byte ptr [rcx+29h], 2
0x140027478  jb      short loc_14002748B
0x14002747a  mov     r9, [rbx]
0x14002747d  mov     edx, 10h
0x140027482  mov     rcx, [rcx+18h]
0x140027486  call    WPP_SF_i
0x14002748b  mov     eax, esi
0x14002748d  jmp     short loc_1400274DE
0x14002748f  mov     rdx, [rbx]
0x140027492  lea     r8, [rsp+28h+arg_8]
0x140027497  mov     rcx, rdi
0x14002749a  call    WimFSFFindOverlayByDataSource
0x14002749f  mov     edi, eax
0x1400274a1  test    eax, eax
0x1400274a3  jns     short loc_1400274CD
0x1400274a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400274ac  mov     edx, [rcx+2Ch]
0x1400274af  test    dl, 8
0x1400274b2  jz      short loc_1400274DC
0x1400274b4  cmp     byte ptr [rcx+29h], 2
0x1400274b8  jb      short loc_1400274DC
0x1400274ba  mov     r9, [rbx]
0x1400274bd  mov     edx, 11h
0x1400274c2  mov     rcx, [rcx+18h]
0x1400274c6  call    WPP_SF_i
0x1400274cb  jmp     short loc_1400274DC
0x1400274cd  mov     rcx, [rsp+28h+arg_8]
0x1400274d2  mov     edx, 2
0x1400274d7  call    WimFSFDismountOverlay
0x1400274dc  mov     eax, edi
0x1400274de  mov     rbx, [rsp+28h+arg_0]
0x1400274e3  mov     rsi, [rsp+28h+arg_10]
0x1400274e8  add     rsp, 20h
0x1400274ec  pop     rdi
0x1400274ed  retn
```

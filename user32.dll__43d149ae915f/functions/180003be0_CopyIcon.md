# CopyIcon

- ea: `0x180003be0`
- end: `0x180003c57`
- name: `CopyIcon`
- size: `119`
- prototype: `HICON __stdcall(HICON hIcon)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003be0`
- `0x180005950`

## import_xrefs

- `win32u!NtUserGetIconInfo` at `0x180003c06`
- `win32u!NtUserGetIconInfo` at `0x180003c06`
- `GDI32!GdiTrackHCreate` at `0x180003c15`
- `GDI32!GdiTrackHCreate` at `0x180003c20`
- `GDI32!GdiTrackHCreate` at `0x180003c15`
- `GDI32!GdiTrackHCreate` at `0x180003c20`
- `GDI32!DeleteObject` at `0x180003c38`
- `GDI32!DeleteObject` at `0x180003c48`
- `GDI32!DeleteObject` at `0x180003c38`
- `GDI32!DeleteObject` at `0x180003c48`

## pseudocode

```c
HICON __stdcall CopyIcon(HICON hIcon)
{
  HICON v1; // rbx
  ICONINFO piconinfo; // [rsp+30h] [rbp-28h] BYREF

  v1 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( (unsigned int)NtUserGetIconInfo(hIcon, &piconinfo, 0, 0, 0, 0) )
  {
    GdiTrackHCreate(piconinfo.hbmMask);
    GdiTrackHCreate(piconinfo.hbmColor);
    v1 = CreateIconIndirect(&piconinfo);
    DeleteObject(piconinfo.hbmMask);
    if ( piconinfo.hbmColor )
      DeleteObject(piconinfo.hbmColor);
  }
  return v1;
}

```

## disassembly

```asm
0x180003be0  mov     rax, rsp
0x180003be3  push    rbx
0x180003be4  sub     rsp, 50h
0x180003be8  xorps   xmm0, xmm0
0x180003beb  lea     rdx, [rax-28h]
0x180003bef  xor     ebx, ebx
0x180003bf1  xor     r9d, r9d
0x180003bf4  mov     [rax-30h], ebx
0x180003bf7  xor     r8d, r8d
0x180003bfa  mov     [rax-38h], rbx
0x180003bfe  movups  xmmword ptr [rax-28h], xmm0
0x180003c02  movups  xmmword ptr [rax-18h], xmm0
0x180003c06  call    cs:__imp_NtUserGetIconInfo
0x180003c0c  test    eax, eax
0x180003c0e  jz      short loc_180003C4E
0x180003c10  mov     rcx, [rsp+58h+piconinfo.hbmMask]
0x180003c15  call    cs:__imp_GdiTrackHCreate
0x180003c1b  mov     rcx, [rsp+58h+piconinfo.hbmColor]
0x180003c20  call    cs:__imp_GdiTrackHCreate
0x180003c26  lea     rcx, [rsp+58h+piconinfo]; piconinfo
0x180003c2b  call    CreateIconIndirect
0x180003c30  mov     rcx, [rsp+58h+piconinfo.hbmMask]; ho
0x180003c35  mov     rbx, rax
0x180003c38  call    cs:__imp_DeleteObject
0x180003c3e  mov     rcx, [rsp+58h+piconinfo.hbmColor]; ho
0x180003c43  test    rcx, rcx
0x180003c46  jz      short loc_180003C4E
0x180003c48  call    cs:__imp_DeleteObject
0x180003c4e  mov     rax, rbx
0x180003c51  add     rsp, 50h
0x180003c55  pop     rbx
0x180003c56  retn
```

# CUrlDownload::OnDownloadComplete(int)

- ea: `0x180007a54`
- end: `0x180007a82`
- name: `?OnDownloadComplete@CUrlDownload@@IEAAJH@Z`
- size: `46`
- prototype: `__int64 __fastcall(CUrlDownload *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005cc4`
- `0x180005f44`
- `0x18000601c`
- `0x1800060f8`
- `0x1800063d4`
- `0x180007890`

## callees

- `0x18000860c`

## import_xrefs

- `USER32!PostMessageW` at `0x180007a6c`
- `USER32!PostMessageW` at `0x180007a6c`

## pseudocode

```c
__int64 __fastcall CUrlDownload::OnDownloadComplete(HWND *this, int a2)
{
  PostMessageW(this[11], 0x1412u, a2, 0);
  CUrlDownload::StopTimer((CUrlDownload *)this);
  return 0;
}

```

## disassembly

```asm
0x180007a54  push    rbx
0x180007a56  sub     rsp, 20h
0x180007a5a  mov     rbx, rcx
0x180007a5d  movsxd  r8, edx; wParam
0x180007a60  mov     rcx, [rcx+58h]; hWnd
0x180007a64  mov     edx, 1412h; Msg
0x180007a69  xor     r9d, r9d; lParam
0x180007a6c  call    cs:__imp_PostMessageW
0x180007a72  mov     rcx, rbx; this
0x180007a75  call    ?StopTimer@CUrlDownload@@IEAAXXZ; CUrlDownload::StopTimer(void)
0x180007a7a  xor     eax, eax
0x180007a7c  add     rsp, 20h
0x180007a80  pop     rbx
0x180007a81  retn
```

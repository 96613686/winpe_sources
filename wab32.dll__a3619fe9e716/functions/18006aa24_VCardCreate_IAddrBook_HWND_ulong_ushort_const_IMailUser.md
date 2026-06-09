# VCardCreate(IAddrBook *,HWND__ *,ulong,ushort const *,IMailUser *)

- ea: `0x18006aa24`
- end: `0x18006ab0e`
- name: `?VCardCreate@@YAJPEAUIAddrBook@@PEAUHWND__@@KPEBGPEAUIMailUser@@@Z`
- size: `234`
- prototype: `int(struct IAddrBook *, HWND, unsigned int, const unsigned __int16 *, struct IMailUser *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003d850`
- `0x180075650`

## callees

- `0x180069f38`
- `0x18006aa24`
- `0x1800719e8`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18006aa5a`
- `KERNEL32!CreateFileW` at `0x18006aa5a`
- `KERNEL32!CloseHandle` at `0x18006aacd`
- `KERNEL32!CloseHandle` at `0x18006aaf8`
- `KERNEL32!CloseHandle` at `0x18006aacd`
- `KERNEL32!CloseHandle` at `0x18006aaf8`
- `KERNEL32!DeleteFileW` at `0x18006ab01`
- `KERNEL32!DeleteFileW` at `0x18006ab01`

## pseudocode

```c
__int64 __fastcall VCardCreate(
        struct IAddrBook *a1,
        HWND a2,
        char a3,
        const unsigned __int16 *a4,
        struct IMailUser *a5)
{
  HANDLE FileW; // rax
  void *v8; // rsi
  unsigned int v9; // ebx
  int v10; // eax
  int v11; // edi

  FileW = CreateFileW(a4, 0x40000000u, 0, 0, 2u, 0x8000000u, 0);
  v8 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v9 = -2147467259;
    if ( (a3 & 8) != 0 )
      ShowMessageBoxParam(0, 0x30u, 16, a4);
    goto LABEL_9;
  }
  v10 = WriteVCard(FileW, (int (*)(void *, void *, unsigned int, unsigned int *))FileWriteFn, a5);
  v9 = v10;
  if ( v10 < 0 )
  {
    v11 = a3 & 8;
    if ( v10 == -2147217406 )
    {
      if ( v11 )
        ShowMessageBoxParam(0, 0x35u, 48, a4);
      CloseHandle(v8);
      DeleteFileW(a4);
      return (unsigned int)-2147467259;
    }
    if ( v11 )
      ShowMessageBoxParam(0, 0x30u, 16, a4);
  }
  if ( v8 )
LABEL_9:
    CloseHandle(v8);
  return v9;
}

```

## disassembly

```asm
0x18006aa24  push    rbx
0x18006aa26  push    rbp
0x18006aa27  push    rsi
0x18006aa28  push    rdi
0x18006aa29  sub     rsp, 48h
0x18006aa2d  mov     rbp, r9
0x18006aa30  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18006aa39  mov     edi, r8d
0x18006aa3c  mov     [rsp+68h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18006aa44  mov     rcx, rbp; lpFileName
0x18006aa47  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x18006aa4f  xor     r9d, r9d; lpSecurityAttributes
0x18006aa52  xor     r8d, r8d; dwShareMode
0x18006aa55  mov     edx, 40000000h; dwDesiredAccess
0x18006aa5a  call    cs:__imp_CreateFileW
0x18006aa60  mov     rsi, rax
0x18006aa63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006aa67  jnz     short loc_18006AA87
0x18006aa69  mov     ebx, 80004005h
0x18006aa6e  test    dil, 8
0x18006aa72  jz      short loc_18006AACA
0x18006aa74  mov     r9, rbp
0x18006aa77  lea     edx, [rax+31h]; uID
0x18006aa7a  xor     ecx, ecx; hWnd
0x18006aa7c  lea     r8d, [rax+11h]; int
0x18006aa80  call    ?ShowMessageBoxParam@@YAHPEAUHWND__@@HHZZ; ShowMessageBoxParam(HWND__ *,int,int,...)
0x18006aa85  jmp     short loc_18006AACA
0x18006aa87  mov     r8, [rsp+68h+arg_20]; struct IMailUser *
0x18006aa8f  lea     rdx, ?FileWriteFn@@YAJPEAX0KPEAK@Z; int (*)(void *, void *, unsigned int, unsigned int *)
0x18006aa96  mov     rcx, rsi; void *
0x18006aa99  call    ?WriteVCard@@YAJPEAXP6AJ00KPEAK@ZPEAUIMailUser@@@Z; WriteVCard(void *,long (*)(void *,void *,ulong,ulong *),IMailUser *)
0x18006aa9e  mov     ebx, eax
0x18006aaa0  test    eax, eax
0x18006aaa2  jns     short loc_18006AAC5
0x18006aaa4  and     edi, 8
0x18006aaa7  cmp     eax, 80041002h
0x18006aaac  jz      short loc_18006AADE
0x18006aaae  test    edi, edi
0x18006aab0  jz      short loc_18006AAC5
0x18006aab2  mov     edx, 30h ; '0'; uID
0x18006aab7  mov     r9, rbp
0x18006aaba  xor     ecx, ecx; hWnd
0x18006aabc  lea     r8d, [rdx-20h]; int
0x18006aac0  call    ?ShowMessageBoxParam@@YAHPEAUHWND__@@HHZZ; ShowMessageBoxParam(HWND__ *,int,int,...)
0x18006aac5  test    rsi, rsi
0x18006aac8  jz      short loc_18006AAD3
0x18006aaca  mov     rcx, rsi; hObject
0x18006aacd  call    cs:__imp_CloseHandle
0x18006aad3  mov     eax, ebx
0x18006aad5  add     rsp, 48h
0x18006aad9  pop     rdi
0x18006aada  pop     rsi
0x18006aadb  pop     rbp
0x18006aadc  pop     rbx
0x18006aadd  retn
0x18006aade  test    edi, edi
0x18006aae0  jz      short loc_18006AAF5
0x18006aae2  mov     edx, 35h ; '5'; uID
0x18006aae7  mov     r9, rbp
0x18006aaea  xor     ecx, ecx; hWnd
0x18006aaec  lea     r8d, [rdx-5]; int
0x18006aaf0  call    ?ShowMessageBoxParam@@YAHPEAUHWND__@@HHZZ; ShowMessageBoxParam(HWND__ *,int,int,...)
0x18006aaf5  mov     rcx, rsi; hObject
0x18006aaf8  call    cs:__imp_CloseHandle
0x18006aafe  mov     rcx, rbp; lpFileName
0x18006ab01  call    cs:__imp_DeleteFileW
0x18006ab07  mov     ebx, 80004005h
0x18006ab0c  jmp     short loc_18006AAD3
```

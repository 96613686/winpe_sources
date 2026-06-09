# GetBitmapStreamFromSBEProperty

- ea: `0x18002ae94`
- end: `0x18002b095`
- name: `GetBitmapStreamFromSBEProperty`
- size: `513`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b794`

## callees

- `0x180001c00`
- `0x18002aa88`
- `0x18002ae94`
- `0x18002b1ec`
- `0x1800b33f9`
- `0x1800b6010`

## import_xrefs

- `KERNEL32!GlobalUnlock` at `0x18002af7f`
- `KERNEL32!GlobalUnlock` at `0x18002af7f`
- `KERNEL32!GlobalLock` at `0x18002af61`
- `KERNEL32!GlobalLock` at `0x18002af61`
- `KERNEL32!GlobalFree` at `0x18002b045`
- `KERNEL32!GlobalFree` at `0x18002b045`
- `KERNEL32!GlobalAlloc` at `0x18002af46`
- `KERNEL32!GlobalAlloc` at `0x18002af46`
- `ole32!CreateStreamOnHGlobal` at `0x18002af8e`
- `ole32!CreateStreamOnHGlobal` at `0x18002afa5`
- `ole32!CreateStreamOnHGlobal` at `0x18002af8e`
- `ole32!CreateStreamOnHGlobal` at `0x18002afa5`
- `gdiplus!GdiplusShutdown` at `0x18002b06c`
- `gdiplus!GdiplusShutdown` at `0x18002b06c`
- `gdiplus!GdiplusStartup` at `0x18002af28`
- `gdiplus!GdiplusStartup` at `0x18002af28`
- `gdiplus!GdipSaveImageToStream` at `0x18002afe7`
- `gdiplus!GdipSaveImageToStream` at `0x18002afe7`

## pseudocode

```c
__int64 __fastcall GetBitmapStreamFromSBEProperty(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rax
  HRESULT GDIPlusEncoderCLSID; // ebx
  __int64 v5; // rbx
  struct Gdiplus::Bitmap *v6; // rdi
  void *v7; // rsi
  HGLOBAL v8; // rax
  void *v9; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // eax
  LPSTREAM v13; // rcx
  LPSTREAM v15; // [rsp+20h] [rbp-50h] BYREF
  LPSTREAM ppstm; // [rsp+28h] [rbp-48h] BYREF
  __int64 v17; // [rsp+30h] [rbp-40h] BYREF
  int v18; // [rsp+38h] [rbp-38h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h]
  __int64 v20; // [rsp+48h] [rbp-28h]
  __int128 v21; // [rsp+50h] [rbp-20h] BYREF

  v2 = *(unsigned int *)(a1 + 8);
  v18 = 1;
  v19 = 0;
  v20 = 0;
  v17 = 0;
  ppstm = 0;
  v15 = 0;
  v21 = 0;
  if ( (unsigned int)v2 < 0x1D )
    return (unsigned int)-2147024809;
  v5 = *(_QWORD *)(a1 + 16);
  if ( v2 < (unsigned __int64)*(unsigned int *)(v5 + 17) + 29 )
    return (unsigned int)-2147024809;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v6 = 0;
  if ( (unsigned int)GdiplusStartup(&v17, &v18, 0) )
  {
    v7 = 0;
  }
  else
  {
    v8 = GlobalAlloc(0x22u, *(unsigned int *)(v5 + 17));
    v7 = v8;
    if ( !v8 )
    {
      GDIPlusEncoderCLSID = -2147024882;
      goto LABEL_18;
    }
    v9 = GlobalLock(v8);
    if ( v9 )
    {
      memcpy_0(v9, *(const void **)(v5 + 21), *(unsigned int *)(v5 + 17));
      GlobalUnlock(v7);
      GDIPlusEncoderCLSID = CreateStreamOnHGlobal(v7, 0, &ppstm);
      if ( GDIPlusEncoderCLSID < 0 )
        goto LABEL_18;
      GDIPlusEncoderCLSID = CreateStreamOnHGlobal(0, 1, &v15);
      if ( GDIPlusEncoderCLSID < 0 )
        goto LABEL_18;
      v6 = Gdiplus::Bitmap::FromStream(ppstm, v10);
      if ( !v6 )
      {
        GDIPlusEncoderCLSID = -2147024809;
        goto LABEL_18;
      }
      GDIPlusEncoderCLSID = GetGDIPlusEncoderCLSID(v11, &v21);
      if ( GDIPlusEncoderCLSID < 0 )
        goto LABEL_18;
      v12 = GdipSaveImageToStream(*((_QWORD *)v6 + 1), v15, &v21, 0);
      if ( !v12 )
      {
        v13 = v15;
        *(_WORD *)a2 = 66;
        *(_QWORD *)(a2 + 8) = v13;
        ((void (__fastcall *)(LPSTREAM))v13->lpVtbl->AddRef)(v13);
        goto LABEL_18;
      }
      *((_DWORD *)v6 + 4) = v12;
    }
  }
  GDIPlusEncoderCLSID = -2147467259;
LABEL_18:
  if ( ppstm )
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
  if ( v15 )
    ((void (__fastcall *)(LPSTREAM))v15->lpVtbl->Release)(v15);
  if ( v7 )
    GlobalFree(v7);
  if ( v6 )
    (**(void (__fastcall ***)(struct Gdiplus::Bitmap *, __int64))v6)(v6, 1);
  if ( v17 )
    GdiplusShutdown();
  return (unsigned int)GDIPlusEncoderCLSID;
}

```

## disassembly

```asm
0x18002ae94  mov     [rsp-18h+arg_10], rbx
0x18002ae99  mov     [rsp-18h+arg_18], rsi
0x18002ae9e  push    rbp
0x18002ae9f  push    rdi
0x18002aea0  push    r14
0x18002aea2  mov     rbp, rsp
0x18002aea5  sub     rsp, 70h
0x18002aea9  mov     rax, cs:__security_cookie
0x18002aeb0  xor     rax, rsp
0x18002aeb3  mov     [rbp+var_10], rax
0x18002aeb7  mov     eax, [rcx+8]
0x18002aeba  xorps   xmm0, xmm0
0x18002aebd  mov     [rbp+var_38], 1
0x18002aec4  mov     r14, rdx
0x18002aec7  mov     [rbp+var_30], 0
0x18002aecf  mov     [rbp+var_28], 0
0x18002aed7  mov     [rbp+var_40], 0
0x18002aedf  mov     [rbp+ppstm], 0
0x18002aee7  mov     [rbp+var_50], 0
0x18002aeef  movups  [rbp+var_20], xmm0
0x18002aef3  cmp     eax, 1Dh
0x18002aef6  jnb     short loc_18002AF02
0x18002aef8  mov     ebx, 80070057h
0x18002aefd  jmp     loc_18002B072
0x18002af02  mov     rbx, [rcx+10h]
0x18002af06  mov     ecx, [rbx+11h]
0x18002af09  add     rcx, 1Dh
0x18002af0d  cmp     rax, rcx
0x18002af10  jb      short loc_18002AEF8
0x18002af12  movups  xmmword ptr [rdx], xmm0
0x18002af15  xor     eax, eax
0x18002af17  lea     rcx, [rbp+var_40]
0x18002af1b  mov     [rdx+10h], rax
0x18002af1f  xor     r8d, r8d
0x18002af22  lea     rdx, [rbp+var_38]
0x18002af26  xor     edi, edi
0x18002af28  call    cs:__imp_GdiplusStartup
0x18002af2e  test    eax, eax
0x18002af30  jz      short loc_18002AF3E
0x18002af32  xor     esi, esi
0x18002af34  mov     ebx, 80004005h
0x18002af39  jmp     loc_18002B013
0x18002af3e  mov     edx, [rbx+11h]; dwBytes
0x18002af41  mov     ecx, 22h ; '"'; uFlags
0x18002af46  call    cs:__imp_GlobalAlloc
0x18002af4c  mov     rsi, rax
0x18002af4f  test    rax, rax
0x18002af52  jnz     short loc_18002AF5E
0x18002af54  mov     ebx, 8007000Eh
0x18002af59  jmp     loc_18002B013
0x18002af5e  mov     rcx, rsi; hMem
0x18002af61  call    cs:__imp_GlobalLock
0x18002af67  test    rax, rax
0x18002af6a  jz      short loc_18002AF34
0x18002af6c  mov     r8d, [rbx+11h]; Size
0x18002af70  mov     rcx, rax; void *
0x18002af73  mov     rdx, [rbx+15h]; Src
0x18002af77  call    memcpy_0
0x18002af7c  mov     rcx, rsi; hMem
0x18002af7f  call    cs:__imp_GlobalUnlock
0x18002af85  lea     r8, [rbp+ppstm]; ppstm
0x18002af89  xor     edx, edx; fDeleteOnRelease
0x18002af8b  mov     rcx, rsi; hGlobal
0x18002af8e  call    cs:__imp_CreateStreamOnHGlobal
0x18002af94  mov     ebx, eax
0x18002af96  test    eax, eax
0x18002af98  js      short loc_18002B013
0x18002af9a  lea     r8, [rbp+var_50]; ppstm
0x18002af9e  mov     edx, 1; fDeleteOnRelease
0x18002afa3  xor     ecx, ecx; hGlobal
0x18002afa5  call    cs:__imp_CreateStreamOnHGlobal
0x18002afab  mov     ebx, eax
0x18002afad  test    eax, eax
0x18002afaf  js      short loc_18002B013
0x18002afb1  mov     rcx, [rbp+ppstm]; struct IStream *
0x18002afb5  call    ?FromStream@Bitmap@Gdiplus@@SAPEAV12@PEAUIStream@@H@Z; Gdiplus::Bitmap::FromStream(IStream *,int)
0x18002afba  mov     rdi, rax
0x18002afbd  test    rax, rax
0x18002afc0  jnz     short loc_18002AFC9
0x18002afc2  mov     ebx, 80070057h
0x18002afc7  jmp     short loc_18002B013
0x18002afc9  lea     rdx, [rbp+var_20]
0x18002afcd  call    GetGDIPlusEncoderCLSID
0x18002afd2  mov     ebx, eax
0x18002afd4  test    eax, eax
0x18002afd6  js      short loc_18002B013
0x18002afd8  mov     rdx, [rbp+var_50]
0x18002afdc  lea     r8, [rbp+var_20]
0x18002afe0  mov     rcx, [rdi+8]
0x18002afe4  xor     r9d, r9d
0x18002afe7  call    cs:__imp_GdipSaveImageToStream
0x18002afed  test    eax, eax
0x18002afef  jz      short loc_18002AFF9
0x18002aff1  mov     [rdi+10h], eax
0x18002aff4  jmp     loc_18002AF34
0x18002aff9  mov     rcx, [rbp+var_50]
0x18002affd  mov     word ptr [r14], 42h ; 'B'
0x18002b003  mov     [r14+8], rcx
0x18002b007  mov     rax, [rcx]
0x18002b00a  mov     rax, [rax+8]
0x18002b00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b013  mov     rcx, [rbp+ppstm]
0x18002b017  test    rcx, rcx
0x18002b01a  jz      short loc_18002B028
0x18002b01c  mov     rax, [rcx]
0x18002b01f  mov     rax, [rax+10h]
0x18002b023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b028  mov     rcx, [rbp+var_50]
0x18002b02c  test    rcx, rcx
0x18002b02f  jz      short loc_18002B03D
0x18002b031  mov     rax, [rcx]
0x18002b034  mov     rax, [rax+10h]
0x18002b038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b03d  test    rsi, rsi
0x18002b040  jz      short loc_18002B04B
0x18002b042  mov     rcx, rsi; hMem
0x18002b045  call    cs:__imp_GlobalFree
0x18002b04b  test    rdi, rdi
0x18002b04e  jz      short loc_18002B063
0x18002b050  mov     rax, [rdi]
0x18002b053  mov     edx, 1
0x18002b058  mov     rcx, rdi
0x18002b05b  mov     rax, [rax]
0x18002b05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b063  mov     rcx, [rbp+var_40]
0x18002b067  test    rcx, rcx
0x18002b06a  jz      short loc_18002B072
0x18002b06c  call    cs:__imp_GdiplusShutdown
0x18002b072  mov     eax, ebx
0x18002b074  mov     rcx, [rbp+var_10]
0x18002b078  xor     rcx, rsp; StackCookie
0x18002b07b  call    __security_check_cookie
0x18002b080  lea     r11, [rsp+70h+var_s0]
0x18002b085  mov     rbx, [r11+30h]
0x18002b089  mov     rsi, [r11+38h]
0x18002b08d  mov     rsp, r11
0x18002b090  pop     r14
0x18002b092  pop     rdi
0x18002b093  pop     rbp
0x18002b094  retn
```

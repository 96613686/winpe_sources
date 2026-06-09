# LoadClockBitmap(uint)

- ea: `0x1800237dc`
- end: `0x1800238a0`
- name: `?LoadClockBitmap@@YAPEAVBitmap@Gdiplus@@I@Z`
- size: `196`
- prototype: `struct Gdiplus::Bitmap *__fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023f3c`

## callees

- `0x1800237dc`
- `0x1800247f8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180023805`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180023805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023822`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023822`
- `gdiplus!GdipAlloc` at `0x180023842`
- `gdiplus!GdipAlloc` at `0x180023842`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18002386b`
- `gdiplus!GdipCreateBitmapFromStream` at `0x18002386b`

## pseudocode

```c
struct Gdiplus::Bitmap *__fastcall LoadClockBitmap(unsigned __int16 a1)
{
  HINSTANCE v1; // rdi
  __int64 v2; // rbx
  HRSRC Resource; // rax
  signed int v4; // eax
  signed int LastError; // eax
  bool v6; // sf
  LPSTREAM v7; // rdi
  LPSTREAM ppstm; // [rsp+38h] [rbp+10h] BYREF
  __int64 v10; // [rsp+40h] [rbp+18h] BYREF

  v1 = g_hInstance;
  v2 = 0;
  ppstm = 0;
  Resource = FindResourceExW(g_hInstance, L"PNGFILE", (LPCWSTR)a1, 0);
  if ( Resource )
  {
    v4 = LoadStreamFromResourceHandle(v1, Resource, &ppstm);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_6;
    v4 = (unsigned __int16)LastError | 0x80070000;
  }
  v6 = v4 < 0;
LABEL_6:
  if ( !v6 )
  {
    v7 = ppstm;
    v2 = GdipAlloc(24);
    if ( v2 )
    {
      v10 = 0;
      *(_QWORD *)v2 = &Gdiplus::Image::`vftable';
      *(_DWORD *)(v2 + 16) = GdipCreateBitmapFromStream(v7, &v10);
      *(_QWORD *)(v2 + 8) = v10;
    }
    else
    {
      v2 = 0;
    }
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
  }
  return (struct Gdiplus::Bitmap *)v2;
}

```

## disassembly

```asm
0x1800237dc  mov     [rsp+arg_0], rbx
0x1800237e1  push    rdi
0x1800237e2  sub     rsp, 20h
0x1800237e6  mov     rdi, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800237ed  lea     rdx, Type; "PNGFILE"
0x1800237f4  movzx   r8d, cx; lpName
0x1800237f8  xor     ebx, ebx
0x1800237fa  mov     rcx, rdi; hModule
0x1800237fd  mov     [rsp+28h+ppstm], rbx
0x180023802  xor     r9d, r9d; wLanguage
0x180023805  call    cs:__imp_FindResourceExW
0x18002380b  test    rax, rax
0x18002380e  jz      short loc_180023822
0x180023810  lea     r8, [rsp+28h+ppstm]; ppstm
0x180023815  mov     rdx, rax; hResInfo
0x180023818  mov     rcx, rdi; hModule
0x18002381b  call    ?LoadStreamFromResourceHandle@@YAJPEAUHINSTANCE__@@PEAUHRSRC__@@PEAPEAUIStream@@@Z; LoadStreamFromResourceHandle(HINSTANCE__ *,HRSRC__ *,IStream * *)
0x180023820  jmp     short loc_180023834
0x180023822  call    cs:__imp_GetLastError
0x180023828  test    eax, eax
0x18002382a  jle     short loc_180023836
0x18002382c  movzx   eax, ax
0x18002382f  or      eax, 80070000h
0x180023834  test    eax, eax
0x180023836  js      short loc_180023892
0x180023838  mov     rdi, [rsp+28h+ppstm]
0x18002383d  mov     ecx, 18h
0x180023842  call    cs:__imp_GdipAlloc
0x180023848  mov     rbx, rax
0x18002384b  test    rax, rax
0x18002384e  jz      short loc_18002387F
0x180023850  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180023857  mov     [rsp+28h+arg_10], 0
0x180023860  lea     rdx, [rsp+28h+arg_10]
0x180023865  mov     [rbx], rax
0x180023868  mov     rcx, rdi
0x18002386b  call    cs:__imp_GdipCreateBitmapFromStream
0x180023871  mov     [rbx+10h], eax
0x180023874  mov     rax, [rsp+28h+arg_10]
0x180023879  mov     [rbx+8], rax
0x18002387d  jmp     short loc_180023881
0x18002387f  xor     ebx, ebx
0x180023881  mov     rcx, [rsp+28h+ppstm]
0x180023886  mov     rdx, [rcx]
0x180023889  mov     rax, [rdx+10h]
0x18002388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023892  mov     rax, rbx
0x180023895  mov     rbx, [rsp+28h+arg_0]
0x18002389a  add     rsp, 20h
0x18002389e  pop     rdi
0x18002389f  retn
```

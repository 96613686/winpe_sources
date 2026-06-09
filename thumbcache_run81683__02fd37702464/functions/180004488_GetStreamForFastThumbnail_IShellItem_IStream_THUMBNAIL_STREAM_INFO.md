# _GetStreamForFastThumbnail(IShellItem *,IStream * *,THUMBNAIL_STREAM_INFO *)

- ea: `0x180004488`
- end: `0x1800045db`
- name: `?_GetStreamForFastThumbnail@@YAJPEAUIShellItem@@PEAPEAUIStream@@PEAW4THUMBNAIL_STREAM_INFO@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct IShellItem *, struct IStream **, enum THUMBNAIL_STREAM_INFO *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003aec`

## callees

- `0x180003624`
- `0x180004488`
- `0x180004bdc`
- `0x180004c60`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800044ef`
- `ext-ms-win-ole32-bindctx-l1-1-0!CreateBindCtx` at `0x1800044ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall _GetStreamForFastThumbnail(
        struct IShellItem *a1,
        struct IStream **a2,
        enum THUMBNAIL_STREAM_INFO *a3)
{
  unsigned int v6; // edx
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  LPBC ppbc; // [rsp+38h] [rbp-18h] BYREF
  int v12; // [rsp+40h] [rbp-10h] BYREF

  *(_DWORD *)a3 = 0;
  v12 = 0;
  if ( ((unsigned int (__fastcall *)(struct IShellItem *, __int64, int *))a1->lpVtbl->GetAttributes)(a1, 0x400000, &v12) )
  {
    return (unsigned int)-2147175933;
  }
  else
  {
    ppbc = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
    CreateBindCtx(0, &ppbc);
    v7 = wil::ShellBindContextHelper::SetMode((wil::ShellBindContextHelper *)&ppbc, v6);
    if ( v7 >= 0 )
    {
      v10 = 0;
      v7 = Microsoft::WRL::Details::MakeAndInitialize<CThumbnailStreamBindCtx,CThumbnailStreamBindCtx,>(&v10);
      if ( v7 >= 0 )
      {
        if ( ppbc )
        {
          v7 = ((__int64 (__fastcall *)(LPBC, const wchar_t *, __int64))ppbc->lpVtbl->RegisterObjectParam)(
                 ppbc,
                 L"BindToThumbnailStream",
                 v10);
          if ( v7 >= 0 )
          {
            v7 = ((__int64 (__fastcall *)(struct IShellItem *, LPBC, const GUID *, GUID *, struct IStream **))a1->lpVtbl->BindToHandler)(
                   a1,
                   ppbc,
                   &BHID_Stream,
                   &GUID_0000000c_0000_0000_c000_000000000046,
                   a2);
            if ( v7 < 0 )
            {
              if ( (*(_BYTE *)(v10 + 16) & 8) != 0 )
                v7 = -2147175933;
            }
            else
            {
              *(_DWORD *)a3 = *(_DWORD *)(v10 + 16);
            }
          }
        }
        else
        {
          v7 = -2147024882;
        }
      }
      v8 = v10;
      if ( v10 )
      {
        v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppbc);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004488  push    rbp
0x18000448a  push    rbx
0x18000448b  push    rsi
0x18000448c  push    rdi
0x18000448d  push    r14
0x18000448f  mov     rbp, rsp
0x180004492  sub     rsp, 50h
0x180004496  mov     rax, cs:__security_cookie
0x18000449d  xor     rax, rsp
0x1800044a0  mov     [rbp+var_8], rax
0x1800044a4  mov     rsi, r8
0x1800044a7  mov     r14, rdx
0x1800044aa  mov     rdi, rcx
0x1800044ad  mov     dword ptr [r8], 0
0x1800044b4  mov     [rbp+var_10], 0
0x1800044bb  mov     rax, [rcx]
0x1800044be  lea     r8, [rbp+var_10]
0x1800044c2  mov     edx, 400000h
0x1800044c7  mov     rax, [rax+30h]
0x1800044cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044d0  test    eax, eax
0x1800044d2  jnz     loc_1800045C6
0x1800044d8  mov     [rbp+ppbc], 0
0x1800044e0  lea     rcx, [rbp+ppbc]
0x1800044e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800044e9  lea     rdx, [rbp+ppbc]; ppbc
0x1800044ed  xor     ecx, ecx; reserved
0x1800044ef  call    cs:__imp_CreateBindCtx
0x1800044f5  nop
0x1800044f6  lea     rcx, [rbp+ppbc]; this
0x1800044fa  call    ?SetMode@ShellBindContextHelper@wil@@QEAAJK@Z; wil::ShellBindContextHelper::SetMode(ulong)
0x1800044ff  mov     ebx, eax
0x180004501  test    eax, eax
0x180004503  js      loc_18000459D
0x180004509  mov     [rbp+var_20], 0
0x180004511  lea     rcx, [rbp+var_20]
0x180004515  call    ??$MakeAndInitialize@VCThumbnailStreamBindCtx@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCThumbnailStreamBindCtx@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<CThumbnailStreamBindCtx,CThumbnailStreamBindCtx,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CThumbnailStreamBindCtx>>)
0x18000451a  mov     ebx, eax
0x18000451c  test    eax, eax
0x18000451e  js      short loc_18000457F
0x180004520  mov     rcx, [rbp+ppbc]
0x180004524  test    rcx, rcx
0x180004527  jz      loc_1800045BF
0x18000452d  mov     rax, [rcx]
0x180004530  mov     r8, [rbp+var_20]
0x180004534  lea     rdx, aBindtothumbnai; "BindToThumbnailStream"
0x18000453b  mov     rax, [rax+48h]
0x18000453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004544  mov     ebx, eax
0x180004546  test    eax, eax
0x180004548  js      short loc_18000457F
0x18000454a  mov     rax, [rdi]
0x18000454d  mov     [rsp+50h+var_30], r14
0x180004552  lea     r9, _GUID_0000000c_0000_0000_c000_000000000046
0x180004559  lea     r8, BHID_Stream
0x180004560  mov     rdx, [rbp+ppbc]
0x180004564  mov     rcx, rdi
0x180004567  mov     rax, [rax+18h]
0x18000456b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004570  mov     ebx, eax
0x180004572  test    eax, eax
0x180004574  mov     rax, [rbp+var_20]
0x180004578  js      short loc_1800045CD
0x18000457a  mov     ecx, [rax+10h]
0x18000457d  mov     [rsi], ecx
0x18000457f  mov     rcx, [rbp+var_20]
0x180004583  test    rcx, rcx
0x180004586  jz      short loc_18000459D
0x180004588  mov     [rbp+var_20], 0
0x180004590  mov     rax, [rcx]
0x180004593  mov     rax, [rax+10h]
0x180004597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000459c  nop
0x18000459d  lea     rcx, [rbp+ppbc]
0x1800045a1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800045a6  mov     eax, ebx
0x1800045a8  mov     rcx, [rbp+var_8]
0x1800045ac  xor     rcx, rsp; StackCookie
0x1800045af  call    __security_check_cookie
0x1800045b4  add     rsp, 50h
0x1800045b8  pop     r14
0x1800045ba  pop     rdi
0x1800045bb  pop     rsi
0x1800045bc  pop     rbx
0x1800045bd  pop     rbp
0x1800045be  retn
0x1800045bf  mov     ebx, 8007000Eh
0x1800045c4  jmp     short loc_18000457F
0x1800045c6  mov     ebx, 8004B203h
0x1800045cb  jmp     short loc_1800045A6
0x1800045cd  test    byte ptr [rax+10h], 8
0x1800045d1  jz      short loc_18000457F
0x1800045d3  mov     ebx, 8004B203h
0x1800045d8  jmp     short loc_18000457F
```

# OpenVolume(wchar_t const *,ulong,ulong,void * *)

- ea: `0x180075bf8`
- end: `0x180075d5e`
- name: `?OpenVolume@@YAJPEB_WKKPEAPEAX@Z`
- size: `358`
- prototype: `__int64 __fastcall(const wchar_t *, unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800756d0`

## callees

- `0x180072288`
- `0x180072720`
- `0x180074cd4`
- `0x180074e6c`
- `0x180075bf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075c9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075d0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075c74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180075c74`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180075cd2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180075cd2`

## string_xrefs

- `0x180075c26`: `OpenVolume`
- `0x180075d39`: `OpenVolume`
- `0x180075d32`: `CreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OpenVolume(const wchar_t *a1, __int64 a2, __int64 a3, void **a4)
{
  unsigned int v6; // ebx
  int v7; // ebx
  HANDLE i; // rax
  void *v9; // rdi
  int v10; // eax
  signed int LastError; // eax
  int v12; // edx
  int v13; // ecx
  void *v15; // [rsp+88h] [rbp+20h] BYREF

  v15 = 0;
  if ( a4 )
  {
    v7 = 100;
    *a4 = (void *)-1LL;
    for ( i = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x28000080u, 0); ; i = CreateFileW(
                                                                              a1,
                                                                              0x80000000,
                                                                              7u,
                                                                              0,
                                                                              3u,
                                                                              0x80u,
                                                                              0) )
    {
      Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(
        &v15,
        i);
      v9 = v15;
      if ( (((unsigned __int64)v15 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        break;
      if ( GetLastError() != 21 )
      {
        if ( GetLastError() != 2 || (v10 = v7, --v7, !v10) )
        {
          if ( GetLastError() != 5 || !v7 )
          {
            if ( !v9 )
              goto LABEL_17;
            break;
          }
          --v7;
        }
      }
      Sleep(0x64u);
    }
    if ( v9 != (void *)-1LL )
    {
      v6 = 0;
      v15 = 0;
      *a4 = v9;
      goto LABEL_21;
    }
LABEL_17:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zzzq_EventWriteTransfer(
        v13,
        v12,
        (unsigned int)L"OpenVolume",
        (unsigned int)L"CreateFile",
        (__int64)a1,
        v6);
  }
  else
  {
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zz_EventWriteTransfer(a1, NullParameter, L"OpenVolume", L"phVolume");
    v6 = -2147024809;
  }
LABEL_21:
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&v15);
  return v6;
}

```

## disassembly

```asm
0x180075bf8  mov     rax, rsp
0x180075bfb  push    rbx
0x180075bfc  push    rbp
0x180075bfd  push    rsi
0x180075bfe  push    rdi
0x180075bff  sub     rsp, 48h
0x180075c03  mov     rsi, r9
0x180075c06  mov     rbp, rcx
0x180075c09  mov     qword ptr [rax+20h], 0
0x180075c11  test    r9, r9
0x180075c14  jnz     short loc_180075C43
0x180075c16  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180075c1d  jz      short loc_180075C39
0x180075c1f  lea     r9, aPhvolume; "phVolume"
0x180075c26  lea     r8, aOpenvolume; "OpenVolume"
0x180075c2d  lea     rdx, NullParameter
0x180075c34  call    McTemplateU0zz_EventWriteTransfer
0x180075c39  mov     ebx, 80070057h
0x180075c3e  jmp     loc_180075D46
0x180075c43  mov     ebx, 64h ; 'd'
0x180075c48  mov     qword ptr [r9], 0FFFFFFFFFFFFFFFFh
0x180075c4f  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180075c58  mov     [rsp+68h+dwFlagsAndAttributes], 28000080h; dwFlagsAndAttributes
0x180075c60  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x180075c68  xor     r9d, r9d; lpSecurityAttributes
0x180075c6b  lea     r8d, [r9+7]; dwShareMode
0x180075c6f  mov     edx, 80000000h; dwDesiredAccess
0x180075c74  call    cs:__imp_CreateFileW
0x180075c7a  mov     rdx, rax
0x180075c7d  lea     rcx, [rsp+68h+arg_18]
0x180075c85  call    ?TakeOwnership@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXPEAX@Z; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::TakeOwnership(void *)
0x180075c8a  mov     rdi, [rsp+68h+arg_18]
0x180075c92  lea     rax, [rdi+1]
0x180075c96  test    rax, 0FFFFFFFFFFFFFFFEh
0x180075c9c  jnz     short loc_180075CF6
0x180075c9e  call    cs:__imp_GetLastError
0x180075ca4  cmp     eax, 15h
0x180075ca7  jz      short loc_180075CCD
0x180075ca9  call    cs:__imp_GetLastError
0x180075caf  cmp     eax, 2
0x180075cb2  jnz     short loc_180075CBC
0x180075cb4  mov     eax, ebx
0x180075cb6  dec     ebx
0x180075cb8  test    eax, eax
0x180075cba  jnz     short loc_180075CCD
0x180075cbc  call    cs:__imp_GetLastError
0x180075cc2  cmp     eax, 5
0x180075cc5  jnz     short loc_180075CF1
0x180075cc7  test    ebx, ebx
0x180075cc9  jz      short loc_180075CF1
0x180075ccb  dec     ebx
0x180075ccd  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180075cd2  call    cs:__imp_Sleep
0x180075cd8  mov     [rsp+68h+hTemplateFile], 0
0x180075ce1  mov     [rsp+68h+dwFlagsAndAttributes], 80h
0x180075ce9  mov     rcx, rbp
0x180075cec  jmp     loc_180075C60
0x180075cf1  test    rdi, rdi
0x180075cf4  jz      short loc_180075D0B
0x180075cf6  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180075cfa  jz      short loc_180075D0B
0x180075cfc  xor     ebx, ebx
0x180075cfe  mov     [rsp+68h+arg_18], rbx
0x180075d06  mov     [rsi], rdi
0x180075d09  jmp     short loc_180075D46
0x180075d0b  call    cs:__imp_GetLastError
0x180075d11  mov     ebx, eax
0x180075d13  test    eax, eax
0x180075d15  jle     short loc_180075D20
0x180075d17  movzx   ebx, ax
0x180075d1a  or      ebx, 80070000h
0x180075d20  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180075d27  jz      short loc_180075D46
0x180075d29  mov     [rsp+68h+dwFlagsAndAttributes], ebx
0x180075d2d  mov     qword ptr [rsp+68h+dwCreationDisposition], rbp
0x180075d32  lea     r9, aCreatefile; "CreateFile"
0x180075d39  lea     r8, aOpenvolume; "OpenVolume"
0x180075d40  call    McTemplateU0zzzq_EventWriteTransfer
0x180075d45  nop
0x180075d46  lea     rcx, [rsp+68h+arg_18]
0x180075d4e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180075d53  mov     eax, ebx
0x180075d55  add     rsp, 48h
0x180075d59  pop     rdi
0x180075d5a  pop     rsi
0x180075d5b  pop     rbp
0x180075d5c  pop     rbx
0x180075d5d  retn
```

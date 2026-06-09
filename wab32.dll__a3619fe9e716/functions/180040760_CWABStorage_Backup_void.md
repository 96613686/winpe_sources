# CWABStorage::Backup(void)

- ea: `0x180040760`
- end: `0x18004091c`
- name: `?Backup@CWABStorage@@UEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(CWABStorage *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800045e4`
- `0x18001d778`
- `0x180030300`
- `0x180032704`
- `0x180032fd8`
- `0x180040760`
- `0x18004273c`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x1800408e3`
- `KERNEL32!ReleaseMutex` at `0x1800408e3`
- `KERNEL32!CreateFileW` at `0x180040854`
- `KERNEL32!CreateFileW` at `0x180040854`
- `KERNEL32!CloseHandle` at `0x1800408d5`
- `KERNEL32!CloseHandle` at `0x1800408d5`
- `USER32!LoadCursorW` at `0x180040791`
- `USER32!LoadCursorW` at `0x180040791`
- `USER32!SetCursor` at `0x18004079a`
- `USER32!SetCursor` at `0x1800408ec`
- `USER32!SetCursor` at `0x18004079a`
- `USER32!SetCursor` at `0x1800408ec`

## pseudocode

```c
__int64 __fastcall CWABStorage::Backup(CWABStorage *this)
{
  HCURSOR CursorW; // rax
  HCURSOR v3; // rbp
  unsigned int v4; // r11d
  unsigned int v5; // ebx
  __int64 v6; // rcx
  HANDLE FileW; // rax
  void *v8; // rsi
  __int64 v9; // rdx
  int v10; // eax
  unsigned __int16 v12[264]; // [rsp+40h] [rbp-238h] BYREF

  CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
  v3 = SetCursor(CursorW);
  memset_0(v12, 0, 0x208u);
  StringCchCopyW(v12, 0x104u, *(const unsigned __int16 **)(*((_QWORD *)this + 1) + 16LL));
  StringCchCatW(v12, v4, L"~");
  if ( v12[0] )
  {
    if ( (unsigned int)CWABStorage::LockFile(this) )
    {
      v6 = *((_QWORD *)this + 1);
      if ( (*(_DWORD *)(*(_QWORD *)(v6 + 24) + 128LL) & 0x1000) != 0 )
      {
        v5 = -2147467259;
        FileW = CreateFileW(*(LPCWSTR *)(v6 + 16), 0xC0000000, 3u, 0, 3u, 0x10000000u, 0);
        v8 = FileW;
        if ( FileW == (HANDLE)-1LL )
          goto LABEL_13;
        if ( (unsigned int)ReloadMPSWabFileInfo(*((struct _tagMPSWabFileInfo **)this + 1), FileW) )
        {
          v9 = *(_QWORD *)(*((_QWORD *)this + 1) + 24LL);
          v10 = *(_DWORD *)(v9 + 128);
          if ( (v10 & 0x110) == 0 )
          {
            *(_DWORD *)(v9 + 128) = v10 & 0xFFFFEFFF;
            if ( WriteDataToWABFile(v8, 0, *(void **)(*((_QWORD *)this + 1) + 24LL), 0xA4u) )
              CompressFile(*((LPCWSTR **)this + 1), v8, v12, 0, 0);
          }
        }
        if ( v8 )
LABEL_13:
          CloseHandle(v8);
      }
      else
      {
        v5 = 0;
      }
      ReleaseMutex(*(HANDLE *)(*((_QWORD *)this + 1) + 48LL));
    }
    else
    {
      v5 = -2147024891;
    }
  }
  else
  {
    v5 = -2147024809;
  }
  SetCursor(v3);
  return v5;
}

```

## disassembly

```asm
0x180040760  mov     [rsp+arg_8], rbx
0x180040765  mov     [rsp+arg_10], rbp
0x18004076a  push    rsi
0x18004076b  push    rdi
0x18004076c  push    r14
0x18004076e  sub     rsp, 260h
0x180040775  mov     rax, cs:__security_cookie
0x18004077c  xor     rax, rsp
0x18004077f  mov     [rsp+278h+var_28], rax
0x180040787  mov     rdi, rcx
0x18004078a  mov     edx, 7F02h; lpCursorName
0x18004078f  xor     ecx, ecx; hInstance
0x180040791  call    cs:__imp_LoadCursorW
0x180040797  mov     rcx, rax; hCursor
0x18004079a  call    cs:__imp_SetCursor
0x1800407a0  xor     edx, edx; Val
0x1800407a2  lea     rcx, [rsp+278h+var_238]; void *
0x1800407a7  mov     r8d, 208h; Size
0x1800407ad  mov     rbp, rax
0x1800407b0  call    memset_0
0x1800407b5  mov     r8, [rdi+8]
0x1800407b9  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800407be  mov     r11d, 104h
0x1800407c4  mov     edx, r11d; unsigned __int64
0x1800407c7  mov     r8, [r8+10h]; unsigned __int16 *
0x1800407cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800407d0  lea     r8, asc_18009AAC0; "~"
0x1800407d7  mov     edx, r11d; unsigned __int64
0x1800407da  lea     rcx, [rsp+278h+var_238]; unsigned __int16 *
0x1800407df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800407e4  xor     r14d, r14d
0x1800407e7  cmp     [rsp+278h+var_238], r14w
0x1800407ed  jnz     short loc_1800407F9
0x1800407ef  mov     ebx, 80070057h
0x1800407f4  jmp     loc_1800408E9
0x1800407f9  mov     rcx, rdi; this
0x1800407fc  call    ?LockFile@CWABStorage@@AEAAHXZ; CWABStorage::LockFile(void)
0x180040801  test    eax, eax
0x180040803  jnz     short loc_18004080F
0x180040805  mov     ebx, 80070005h
0x18004080a  jmp     loc_1800408E9
0x18004080f  mov     rcx, [rdi+8]
0x180040813  mov     rax, [rcx+18h]
0x180040817  test    dword ptr [rax+80h], 1000h
0x180040821  jnz     short loc_18004082B
0x180040823  mov     ebx, r14d
0x180040826  jmp     loc_1800408DB
0x18004082b  mov     rcx, [rcx+10h]; lpFileName
0x18004082f  mov     r8d, 3; dwShareMode
0x180040835  mov     [rsp+278h+hTemplateFile], r14; hTemplateFile
0x18004083a  xor     r9d, r9d; lpSecurityAttributes
0x18004083d  mov     [rsp+278h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x180040845  mov     edx, 0C0000000h; dwDesiredAccess
0x18004084a  mov     [rsp+278h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004084f  mov     ebx, 80004005h
0x180040854  call    cs:__imp_CreateFileW
0x18004085a  mov     rsi, rax
0x18004085d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040861  jz      short loc_1800408D2
0x180040863  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x180040867  mov     rdx, rax; void *
0x18004086a  call    ?ReloadMPSWabFileInfo@@YAHPEAU_tagMPSWabFileInfo@@PEAX@Z; ReloadMPSWabFileInfo(_tagMPSWabFileInfo *,void *)
0x18004086f  test    eax, eax
0x180040871  jz      short loc_1800408CD
0x180040873  mov     rcx, [rdi+8]
0x180040877  mov     rdx, [rcx+18h]
0x18004087b  mov     eax, [rdx+80h]
0x180040881  test    eax, 110h
0x180040886  jnz     short loc_1800408CD
0x180040888  btr     eax, 0Ch
0x18004088c  mov     r9d, 0A4h; unsigned int
0x180040892  mov     [rdx+80h], eax
0x180040898  mov     rcx, rsi; hFile
0x18004089b  mov     r8, [rdi+8]
0x18004089f  xor     edx, edx; unsigned int
0x1800408a1  mov     r8, [r8+18h]; void *
0x1800408a5  call    ?WriteDataToWABFile@@YAHPEAXK0K@Z; WriteDataToWABFile(void *,ulong,void *,ulong)
0x1800408aa  test    eax, eax
0x1800408ac  jz      short loc_1800408CD
0x1800408ae  mov     rcx, [rdi+8]; struct _tagMPSWabFileInfo *
0x1800408b2  lea     r8, [rsp+278h+var_238]; unsigned __int16 *
0x1800408b7  xor     r9d, r9d; int
0x1800408ba  mov     [rsp+278h+dwCreationDisposition], r14d; unsigned int
0x1800408bf  mov     rdx, rsi; void *
0x1800408c2  call    ?CompressFile@@YAHPEAU_tagMPSWabFileInfo@@PEAXPEAGHK@Z; CompressFile(_tagMPSWabFileInfo *,void *,ushort *,int,ulong)
0x1800408c7  test    eax, eax
0x1800408c9  cmovnz  ebx, r14d
0x1800408cd  test    rsi, rsi
0x1800408d0  jz      short loc_1800408DB
0x1800408d2  mov     rcx, rsi; hObject
0x1800408d5  call    cs:__imp_CloseHandle
0x1800408db  mov     rcx, [rdi+8]
0x1800408df  mov     rcx, [rcx+30h]; hMutex
0x1800408e3  call    cs:__imp_ReleaseMutex
0x1800408e9  mov     rcx, rbp; hCursor
0x1800408ec  call    cs:__imp_SetCursor
0x1800408f2  mov     eax, ebx
0x1800408f4  mov     rcx, [rsp+278h+var_28]
0x1800408fc  xor     rcx, rsp; StackCookie
0x1800408ff  call    __security_check_cookie
0x180040904  lea     r11, [rsp+278h+var_18]
0x18004090c  mov     rbx, [r11+28h]
0x180040910  mov     rbp, [r11+30h]
0x180040914  mov     rsp, r11
0x180040917  pop     r14
0x180040919  pop     rdi
0x18004091a  pop     rsi
0x18004091b  retn
```

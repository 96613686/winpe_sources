# IO::File::Open(IO::Path const &,IO::File::Access,IO::AssumeDirectoryExists)

- ea: `0x140084688`
- end: `0x140084830`
- name: `?Open@File@IO@@YA?AV?$unique_ptr@XUHandleClose@Private@@@std@@AEBVPath@2@W4Access@12@UAssumeDirectoryExists@2@@Z`
- size: `424`
- prototype: `_QWORD *__fastcall(_QWORD *, const WCHAR *, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14003b6d0`
- `0x1400843fc`
- `0x140086198`

## callees

- `0x140005530`
- `0x140006338`
- `0x14001c804`
- `0x14001f654`
- `0x140060e60`
- `0x140060f58`
- `0x14006b734`
- `0x14007aaf4`
- `0x140084688`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140084713`
- `KERNEL32!CreateFileW` at `0x140084713`
- `KERNEL32!GetLastError` at `0x140084724`
- `KERNEL32!GetLastError` at `0x140084724`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
_QWORD *__fastcall IO::File::Open(_QWORD *a1, const WCHAR *a2, int a3)
{
  DWORD v5; // edx
  DWORD v6; // eax
  DWORD dwCreationDisposition; // r8d
  const WCHAR *v8; // rcx
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // r10
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r10
  _BYTE pExceptionObject[80]; // [rsp+50h] [rbp-68h] BYREF

  if ( a3 )
  {
    v6 = 0;
    if ( a3 == 1 )
    {
      v5 = 0x40000000;
    }
    else
    {
      v5 = -1073741824;
      if ( a3 != 2 )
        goto LABEL_9;
    }
    dwCreationDisposition = 4;
    goto LABEL_6;
  }
  v5 = 0x80000000;
  v6 = 1;
LABEL_9:
  dwCreationDisposition = 3;
LABEL_6:
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v8 = a2;
  else
    v8 = *(const WCHAR **)a2;
  FileW = CreateFileW(v8, v5, v6, 0, dwCreationDisposition, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v13 = std::array<unsigned short,16>::data(a2);
        v14 = std::wstring::c_str(v13);
        WPP_SF_Sd(*(_QWORD *)(v15 + 16), 11, (unsigned int)WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v14, v11);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v11);
      throw (ErrorCodeException *)pExceptionObject;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v16 = std::array<unsigned short,16>::data(a2);
      v17 = std::wstring::c_str(v16);
      WPP_SF_S(*(_QWORD *)(v18 + 16), 10, WPP_fc52131781a63b563a504d48059c77ca_Traceguids, v17);
    }
    IO::FileNotFoundException::FileNotFoundException(
      (IO::FileNotFoundException *)pExceptionObject,
      (const struct Path *)a2);
    throw (IO::FileNotFoundException *)pExceptionObject;
  }
  *a1 = FileW;
  return a1;
}

```

## disassembly

```asm
0x140084688  mov     [rsp+arg_10], rbx
0x14008468d  push    rdi
0x14008468e  sub     rsp, 0B0h
0x140084695  mov     rax, cs:__security_cookie
0x14008469c  xor     rax, rsp
0x14008469f  mov     [rsp+0B8h+var_18], rax
0x1400846a7  mov     rdi, rdx
0x1400846aa  mov     rbx, rcx
0x1400846ad  mov     [rsp+0B8h+var_70], rcx
0x1400846b2  test    r8d, r8d
0x1400846b5  jnz     short loc_1400846C2
0x1400846b7  mov     edx, 80000000h
0x1400846bc  lea     eax, [r8+1]
0x1400846c0  jmp     short loc_1400846EC
0x1400846c2  xor     eax, eax
0x1400846c4  cmp     r8d, 1
0x1400846c8  jnz     short loc_1400846E1
0x1400846ca  mov     edx, 40000000h; dwDesiredAccess
0x1400846cf  mov     r8d, 4
0x1400846d5  cmp     qword ptr [rdi+18h], 7
0x1400846da  jbe     short loc_1400846F4
0x1400846dc  mov     rcx, [rdi]
0x1400846df  jmp     short loc_1400846F7
0x1400846e1  mov     edx, 0C0000000h
0x1400846e6  cmp     r8d, 2
0x1400846ea  jz      short loc_1400846CF
0x1400846ec  mov     r8d, 3
0x1400846f2  jmp     short loc_1400846D5
0x1400846f4  mov     rcx, rdi; lpFileName
0x1400846f7  mov     [rsp+0B8h+hTemplateFile], 0; hTemplateFile
0x140084700  mov     [rsp+0B8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140084708  mov     [rsp+0B8h+dwCreationDisposition], r8d; dwCreationDisposition
0x14008470d  xor     r9d, r9d; lpSecurityAttributes
0x140084710  mov     r8d, eax; dwShareMode
0x140084713  call    cs:__imp_CreateFileW
0x140084719  mov     [rsp+0B8h+var_70], rax
0x14008471e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140084722  jnz     short loc_140084737
0x140084724  call    cs:__imp_GetLastError
0x14008472a  mov     ebx, eax
0x14008472c  cmp     eax, 2
0x14008472f  jz      loc_1400847CF
0x140084735  jmp     short loc_14008475E
0x140084737  mov     [rbx], rax
0x14008473a  mov     rax, rbx
0x14008473d  mov     rcx, [rsp+0B8h+var_18]
0x140084745  xor     rcx, rsp; StackCookie
0x140084748  call    __security_check_cookie
0x14008474d  mov     rbx, [rsp+0B8h+arg_10]
0x140084755  add     rsp, 0B0h
0x14008475c  pop     rdi
0x14008475d  retn
0x14008475e  test    eax, eax
0x140084760  jle     short loc_14008476B
0x140084762  movzx   ebx, ax
0x140084765  or      ebx, 80070000h
0x14008476b  lea     rax, WPP_GLOBAL_Control
0x140084772  mov     r10, cs:WPP_GLOBAL_Control
0x140084779  cmp     r10, rax
0x14008477c  jz      short loc_1400847B1
0x14008477e  test    byte ptr [r10+1Ch], 1
0x140084783  jz      short loc_1400847B1
0x140084785  mov     rcx, rdi
0x140084788  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x14008478d  mov     rcx, rax
0x140084790  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140084795  mov     edx, 0Bh
0x14008479a  mov     [rsp+0B8h+dwCreationDisposition], ebx
0x14008479e  mov     r9, rax
0x1400847a1  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x1400847a8  mov     rcx, [r10+10h]
0x1400847ac  call    WPP_SF_Sd
0x1400847b1  mov     edx, ebx; int
0x1400847b3  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x1400847b8  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400847bd  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400847c4  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x1400847c9  call    _CxxThrowException_0
0x1400847cf  lea     rax, WPP_GLOBAL_Control
0x1400847d6  mov     r10, cs:WPP_GLOBAL_Control
0x1400847dd  cmp     r10, rax
0x1400847e0  jz      short loc_140084811
0x1400847e2  test    byte ptr [r10+1Ch], 1
0x1400847e7  jz      short loc_140084811
0x1400847e9  mov     rcx, rdi
0x1400847ec  call    ?data@?$array@G$0BA@@std@@QEAAPEAGXZ; std::array<ushort,16>::data(void)
0x1400847f1  mov     rcx, rax
0x1400847f4  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400847f9  mov     edx, 0Ah
0x1400847fe  mov     r9, rax
0x140084801  lea     r8, WPP_fc52131781a63b563a504d48059c77ca_Traceguids
0x140084808  mov     rcx, [r10+10h]
0x14008480c  call    WPP_SF_S
0x140084811  mov     rdx, rdi; struct Path *
0x140084814  lea     rcx, [rsp+0B8h+pExceptionObject]; this
0x140084819  call    ??0FileNotFoundException@IO@@QEAA@AEBVPath@1@@Z; IO::FileNotFoundException::FileNotFoundException(IO::Path const &)
0x14008481e  lea     rdx, _TI4?AUFileNotFoundException@IO@@; pThrowInfo
0x140084825  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x14008482a  call    _CxxThrowException_0
```

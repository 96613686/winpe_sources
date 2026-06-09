# CDVRFileCollection::CouldBeReferenceRecording(ushort const *)

- ea: `0x180073204`
- end: `0x180073362`
- name: `?CouldBeReferenceRecording@CDVRFileCollection@@SAHPEBG@Z`
- size: `350`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180068858`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x180001c00`
- `0x180073204`
- `0x1800b33ed`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180073338`
- `KERNEL32!CloseHandle` at `0x180073338`
- `KERNEL32!GetLastError` at `0x18007325e`
- `KERNEL32!GetLastError` at `0x1800732bf`
- `KERNEL32!GetLastError` at `0x18007325e`
- `KERNEL32!GetLastError` at `0x1800732bf`
- `KERNEL32!ReadFile` at `0x1800732b5`
- `KERNEL32!ReadFile` at `0x1800732b5`
- `KERNEL32!CreateFileW` at `0x18007324f`
- `KERNEL32!CreateFileW` at `0x18007324f`

## pseudocode

```c
_BOOL8 __fastcall CDVRFileCollection::CouldBeReferenceRecording(const unsigned __int16 *a1)
{
  HANDLE FileW; // rsi
  signed int LastError; // eax
  unsigned int v3; // ebx
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  unsigned __int64 v6; // rdx
  signed int v7; // eax
  __int64 v8; // rax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-18h] BYREF

  NumberOfBytesRead = 0;
  FileW = CreateFileW(a1, 0x80000000, 7u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v4 = operator new[](0x778u);
    v5 = v4;
    if ( v4 )
    {
      NumberOfBytesRead = 1912;
      if ( ReadFile(FileW, v4, 0x778u, &NumberOfBytesRead, 0) )
      {
        if ( NumberOfBytesRead < 0x778 )
        {
          v3 = -2147024883;
        }
        else
        {
          v8 = *v5 - *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1;
          if ( *v5 == *(_QWORD *)&CDVRFileCollection::m_guidV11.Data1 )
            v8 = v5[1] - *(_QWORD *)CDVRFileCollection::m_guidV11.Data4;
          if ( v8 )
            v3 = memcmp_0(v5, &CDVRFileCollection::m_guidV1, 0x10u) != 0 ? -2147024883 : -2147220924;
          else
            v3 = 0;
        }
      }
      else
      {
        v7 = GetLastError();
        v3 = v7;
        if ( v7 > 0 )
          v3 = (unsigned __int16)v7 | 0x80070000;
      }
      operator delete(v5, v6);
    }
    else
    {
      v3 = -2147024882;
    }
    if ( FileW )
      CloseHandle(FileW);
  }
  return v3 == 0;
}

```

## disassembly

```asm
0x180073204  mov     [rsp+arg_8], rbx
0x180073209  mov     [rsp+arg_10], rsi
0x18007320e  push    rdi
0x18007320f  sub     rsp, 50h
0x180073213  mov     rax, cs:__security_cookie
0x18007321a  xor     rax, rsp
0x18007321d  mov     [rsp+58h+var_10], rax
0x180073222  xor     r9d, r9d; lpSecurityAttributes
0x180073225  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18007322e  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180073236  mov     edx, 80000000h; dwDesiredAccess
0x18007323b  mov     [rsp+58h+NumberOfBytesRead], 0
0x180073243  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18007324b  lea     r8d, [r9+7]; dwShareMode
0x18007324f  call    cs:__imp_CreateFileW
0x180073255  mov     rsi, rax
0x180073258  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007325c  jnz     short loc_18007327C
0x18007325e  call    cs:__imp_GetLastError
0x180073264  mov     ebx, eax
0x180073266  test    eax, eax
0x180073268  jle     loc_18007333E
0x18007326e  movzx   ebx, ax
0x180073271  or      ebx, 80070000h
0x180073277  jmp     loc_18007333E
0x18007327c  mov     ebx, 778h
0x180073281  mov     ecx, ebx; unsigned __int64
0x180073283  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180073288  mov     rdi, rax
0x18007328b  test    rax, rax
0x18007328e  jnz     short loc_18007329A
0x180073290  mov     ebx, 8007000Eh
0x180073295  jmp     loc_180073330
0x18007329a  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18007329f  mov     [rsp+58h+NumberOfBytesRead], ebx
0x1800732a3  mov     r8d, ebx; nNumberOfBytesToRead
0x1800732a6  mov     qword ptr [rsp+58h+dwCreationDisposition], 0; lpOverlapped
0x1800732af  mov     rdx, rdi; lpBuffer
0x1800732b2  mov     rcx, rsi; hFile
0x1800732b5  call    cs:__imp_ReadFile
0x1800732bb  test    eax, eax
0x1800732bd  jnz     short loc_1800732D6
0x1800732bf  call    cs:__imp_GetLastError
0x1800732c5  mov     ebx, eax
0x1800732c7  test    eax, eax
0x1800732c9  jle     short loc_180073328
0x1800732cb  movzx   ebx, ax
0x1800732ce  or      ebx, 80070000h
0x1800732d4  jmp     short loc_180073328
0x1800732d6  cmp     [rsp+58h+NumberOfBytesRead], ebx
0x1800732da  jb      short loc_180073323
0x1800732dc  mov     rax, [rdi]
0x1800732df  sub     rax, qword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data1; _GUID const CDVRFileCollection::m_guidV11 ...
0x1800732e6  jnz     short loc_1800732F3
0x1800732e8  mov     rax, [rdi+8]
0x1800732ec  sub     rax, qword ptr cs:?m_guidV11@CDVRFileCollection@@2U_GUID@@B.Data4; _GUID const CDVRFileCollection::m_guidV11 ...
0x1800732f3  test    rax, rax
0x1800732f6  jz      short loc_18007331F
0x1800732f8  mov     r8d, 10h; Size
0x1800732fe  lea     rdx, ?m_guidV1@CDVRFileCollection@@2U_GUID@@B; Buf2
0x180073305  mov     rcx, rdi; Buf1
0x180073308  call    memcmp_0
0x18007330d  neg     eax
0x18007330f  sbb     ebx, ebx
0x180073311  and     ebx, 2FDC9h
0x180073317  add     ebx, 80040244h
0x18007331d  jmp     short loc_180073328
0x18007331f  xor     ebx, ebx
0x180073321  jmp     short loc_180073328
0x180073323  mov     ebx, 8007000Dh
0x180073328  mov     rcx, rdi; void *
0x18007332b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180073330  test    rsi, rsi
0x180073333  jz      short loc_18007333E
0x180073335  mov     rcx, rsi; hObject
0x180073338  call    cs:__imp_CloseHandle
0x18007333e  xor     eax, eax
0x180073340  test    ebx, ebx
0x180073342  setz    al
0x180073345  mov     rcx, [rsp+58h+var_10]
0x18007334a  xor     rcx, rsp; StackCookie
0x18007334d  call    __security_check_cookie
0x180073352  mov     rbx, [rsp+58h+arg_8]
0x180073357  mov     rsi, [rsp+58h+arg_10]
0x18007335c  add     rsp, 50h
0x180073360  pop     rdi
0x180073361  retn
```

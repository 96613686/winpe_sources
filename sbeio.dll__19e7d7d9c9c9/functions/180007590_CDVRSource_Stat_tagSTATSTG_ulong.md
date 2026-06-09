# CDVRSource::Stat(tagSTATSTG *,ulong)

- ea: `0x180007590`
- end: `0x180007744`
- name: `?Stat@CDVRSource@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `436`
- prototype: `__int64 __fastcall(CDVRSource *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180007590`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000772b`
- `ole32!CoTaskMemFree` at `0x18002a6f8`
- `ole32!CoTaskMemFree` at `0x18000772b`
- `ole32!CoTaskMemFree` at `0x18002a6f8`
- `ole32!CoTaskMemAlloc` at `0x180007652`
- `ole32!CoTaskMemAlloc` at `0x180007652`
- `KERNEL32!GetLastError` at `0x180007695`
- `KERNEL32!GetLastError` at `0x180007695`
- `KERNEL32!GetFileInformationByHandle` at `0x18000768b`
- `KERNEL32!GetFileInformationByHandle` at `0x18000768b`
- `KERNEL32!LeaveCriticalSection` at `0x180007737`
- `KERNEL32!LeaveCriticalSection` at `0x180007737`
- `KERNEL32!LeaveCriticalSection` at `0x18002a716`
- `KERNEL32!EnterCriticalSection` at `0x180007616`
- `KERNEL32!EnterCriticalSection` at `0x180007616`

## pseudocode

```c
__int64 __fastcall CDVRSource::Stat(CDVRSource *this, struct tagSTATSTG *a2, unsigned int a3)
{
  struct _RTL_CRITICAL_SECTION *v7; // r14
  signed int v8; // ebx
  __int64 v9; // rcx
  OLECHAR *v10; // rax
  signed int LastError; // eax
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+38h] [rbp-60h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( a3 >= 2 )
    return 2147942487LL;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  a2->pwcsName = 0;
  if ( *((_DWORD *)this + 46) == 1 )
  {
    if ( a3 == 1 )
      goto LABEL_12;
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*((_QWORD *)this + 7) + 2 * v9) );
    v10 = (OLECHAR *)CoTaskMemAlloc(2 * v9 + 2);
    a2->pwcsName = v10;
    if ( v10 )
    {
LABEL_12:
      memset(&FileInformation, 0, sizeof(FileInformation));
      if ( GetFileInformationByHandle(*((HANDLE *)this + 10), &FileInformation) )
      {
        a2->type = 2;
        if ( *((_DWORD *)this + 44) )
        {
          a2->cbSize.QuadPart = -1;
        }
        else
        {
          a2->cbSize.LowPart = FileInformation.nFileSizeLow;
          a2->cbSize.HighPart = FileInformation.nFileSizeHigh;
        }
        if ( *((_QWORD *)this + 5) == a2->cbSize.QuadPart )
        {
          a2->mtime = FileInformation.ftLastWriteTime;
          a2->ctime = FileInformation.ftCreationTime;
          a2->atime = FileInformation.ftLastAccessTime;
          *(_QWORD *)&a2->grfMode = 32;
          a2->clsid = GUID_NULL;
          *(_QWORD *)&a2->grfStateBits = 0;
          v8 = 0;
        }
        else
        {
          v8 = -2147467259;
        }
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v8 = -2147024882;
    }
  }
  else
  {
    v8 = -2147418113;
  }
  if ( v8 < 0 )
  {
    if ( a2->pwcsName )
    {
      CoTaskMemFree(a2->pwcsName);
      a2->pwcsName = 0;
    }
  }
  LeaveCriticalSection(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007590  mov     [rsp+arg_10], rbx
0x180007595  mov     [rsp+arg_18], rsi
0x18000759a  push    rdi
0x18000759b  push    r14
0x18000759d  push    r15
0x18000759f  sub     rsp, 80h
0x1800075a6  mov     rax, cs:__security_cookie
0x1800075ad  xor     rax, rsp
0x1800075b0  mov     [rsp+98h+var_28], rax
0x1800075b5  mov     esi, r8d
0x1800075b8  mov     rdi, rdx
0x1800075bb  mov     rbx, rcx
0x1800075be  mov     [rsp+98h+var_68], rcx
0x1800075c3  mov     [rsp+98h+var_70], rdx
0x1800075c8  xor     r15d, r15d
0x1800075cb  test    rdx, rdx
0x1800075ce  jnz     short loc_1800075FB
0x1800075d0  mov     eax, 80004003h
0x1800075d5  mov     rcx, [rsp+98h+var_28]
0x1800075da  xor     rcx, rsp; StackCookie
0x1800075dd  call    __security_check_cookie
0x1800075e2  lea     r11, [rsp+98h+var_18]
0x1800075ea  mov     rbx, [r11+30h]
0x1800075ee  mov     rsi, [r11+38h]
0x1800075f2  mov     rsp, r11
0x1800075f5  pop     r15
0x1800075f7  pop     r14
0x1800075f9  pop     rdi
0x1800075fa  retn
0x1800075fb  cmp     esi, 2
0x1800075fe  jb      short loc_180007607
0x180007600  mov     eax, 80070057h
0x180007605  jmp     short loc_1800075D5
0x180007607  mov     [rsp+98h+var_78], r15d
0x18000760c  lea     r14, [rcx+0C0h]
0x180007613  mov     rcx, r14; lpCriticalSection
0x180007616  call    cs:__imp_EnterCriticalSection
0x18000761c  nop
0x18000761d  mov     [rdi], r15
0x180007620  cmp     dword ptr [rbx+0B8h], 1
0x180007627  jz      short loc_180007633
0x180007629  mov     ebx, 8000FFFFh
0x18000762e  jmp     loc_18000771B
0x180007633  cmp     esi, 1
0x180007636  jz      short loc_18000766A
0x180007638  mov     rax, [rbx+38h]
0x18000763c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180007640  inc     rcx
0x180007643  cmp     [rax+rcx*2], r15w
0x180007648  jnz     short loc_180007640
0x18000764a  lea     rcx, ds:2[rcx*2]; cb
0x180007652  call    cs:__imp_CoTaskMemAlloc
0x180007658  mov     [rdi], rax
0x18000765b  test    rax, rax
0x18000765e  jnz     short loc_18000766A
0x180007660  mov     ebx, 8007000Eh
0x180007665  jmp     loc_18000771B
0x18000766a  xorps   xmm0, xmm0
0x18000766d  xor     eax, eax
0x18000766f  movups  xmmword ptr [rsp+98h+FileInformation.dwFileAttributes], xmm0
0x180007674  movups  xmmword ptr [rsp+98h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180007679  movups  xmmword ptr [rsp+98h+FileInformation.nFileSizeHigh], xmm0
0x18000767e  mov     [rsp+98h+FileInformation.nFileIndexLow], eax
0x180007682  lea     rdx, [rsp+98h+FileInformation]; lpFileInformation
0x180007687  mov     rcx, [rbx+50h]; hFile
0x18000768b  call    cs:__imp_GetFileInformationByHandle
0x180007691  test    eax, eax
0x180007693  jnz     short loc_1800076AC
0x180007695  call    cs:__imp_GetLastError
0x18000769b  mov     ebx, eax
0x18000769d  test    eax, eax
0x18000769f  jle     short loc_18000771B
0x1800076a1  movzx   ebx, ax
0x1800076a4  or      ebx, 80070000h
0x1800076aa  jmp     short loc_18000771B
0x1800076ac  mov     dword ptr [rdi+8], 2
0x1800076b3  cmp     [rbx+0B0h], r15d
0x1800076ba  jz      short loc_1800076C6
0x1800076bc  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1800076c4  jmp     short loc_1800076D4
0x1800076c6  mov     eax, [rsp+98h+FileInformation.nFileSizeLow]
0x1800076ca  mov     [rdi+10h], eax
0x1800076cd  mov     eax, [rsp+98h+FileInformation.nFileSizeHigh]
0x1800076d1  mov     [rdi+14h], eax
0x1800076d4  mov     rax, [rdi+10h]
0x1800076d8  cmp     [rbx+28h], rax
0x1800076dc  jz      short loc_1800076E5
0x1800076de  mov     ebx, 80004005h
0x1800076e3  jmp     short loc_18000771B
0x1800076e5  mov     rax, qword ptr [rsp+98h+FileInformation.ftLastWriteTime.dwLowDateTime]
0x1800076ea  mov     [rdi+18h], rax
0x1800076ee  mov     rax, qword ptr [rsp+98h+FileInformation.ftCreationTime.dwLowDateTime]
0x1800076f3  mov     [rdi+20h], rax
0x1800076f7  mov     rax, qword ptr [rsp+98h+FileInformation.ftLastAccessTime.dwLowDateTime]
0x1800076fc  mov     [rdi+28h], rax
0x180007700  mov     qword ptr [rdi+30h], 20h ; ' '
0x180007708  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18000770f  movdqu  xmmword ptr [rdi+38h], xmm0
0x180007714  mov     [rdi+48h], r15
0x180007718  mov     ebx, r15d
0x18000771b  mov     [rsp+98h+var_78], ebx
0x18000771f  test    ebx, ebx
0x180007721  jns     short loc_180007734
0x180007723  mov     rcx, [rdi]; pv
0x180007726  test    rcx, rcx
0x180007729  jz      short loc_180007734
0x18000772b  call    cs:__imp_CoTaskMemFree
0x180007731  mov     [rdi], r15
0x180007734  mov     rcx, r14; lpCriticalSection
0x180007737  call    cs:__imp_LeaveCriticalSection
0x18000773d  mov     eax, ebx
0x18000773f  jmp     loc_1800075D5
0x18002a6db  push    rbx
0x18002a6dd  push    rbp
0x18002a6de  sub     rsp, 28h
0x18002a6e2  mov     rbp, rdx
0x18002a6e5  cmp     dword ptr [rbp+20h], 0
0x18002a6e9  jge     short loc_18002A705
0x18002a6eb  mov     rbx, [rbp+28h]
0x18002a6ef  cmp     qword ptr [rbx], 0
0x18002a6f3  jz      short loc_18002A705
0x18002a6f5  mov     rcx, [rbx]; pv
0x18002a6f8  call    cs:__imp_CoTaskMemFree
0x18002a6fe  mov     qword ptr [rbx], 0
0x18002a705  mov     rcx, [rbp+30h]
0x18002a709  add     rcx, 0C0h
0x18002a710  add     rsp, 28h
0x18002a714  pop     rbp
0x18002a715  pop     rbx
0x18002a716  jmp     cs:__imp_LeaveCriticalSection
```

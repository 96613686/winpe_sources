# ReadBlobFromFile(ushort const *,ulong,uchar * *,ulong *)

- ea: `0x180010f20`
- end: `0x180011103`
- name: `?ReadBlobFromFile@@YAKPEBGKPEAPEAEPEAK@Z`
- size: `483`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18001a134`
- `0x18001b6b0`

## callees

- `0x180003140`
- `0x180010f20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011048`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011069`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010f54`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fe0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010fe0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011008`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180011008`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010fb1`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180010fb1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010f8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180010f8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ReadBlobFromFile(const unsigned __int16 *a1, DWORD a2, unsigned __int8 **a3, unsigned int *a4)
{
  HANDLE FileW; // rsi
  unsigned int LowPart; // edi
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rbx
  DWORD LastError; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-40h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-38h] BYREF
  BOOL (__stdcall *v17)(HANDLE); // [rsp+50h] [rbp-30h] BYREF
  HANDLE v18; // [rsp+58h] [rbp-28h]
  int v19; // [rsp+60h] [rbp-20h]
  __int64 v20; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int8 *v21; // [rsp+70h] [rbp-10h]
  int v22; // [rsp+78h] [rbp-8h]

  NumberOfBytesRead = 0;
  FileSize.QuadPart = 0;
  v21 = 0;
  v22 = 0;
  v20 = 0;
  v17 = CloseHandle;
  v18 = 0;
  v19 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
  v18 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
    return LastError;
  }
  else if ( GetFileSizeEx(FileW, &FileSize) )
  {
    if ( FileSize.HighPart || (LowPart = FileSize.LowPart, a2) && FileSize.LowPart > a2 )
    {
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
      CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
      return 223;
    }
    else
    {
      v9 = (unsigned __int8 *)LocalAlloc(0x40u, FileSize.LowPart);
      v10 = v9;
      v21 = v9;
      if ( v9 )
      {
        if ( ReadFile(FileW, v9, LowPart, &NumberOfBytesRead, 0) )
        {
          *a3 = v10;
          *a4 = LowPart;
          v21 = 0;
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
          return 0;
        }
        else
        {
          v14 = GetLastError();
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
          return v14;
        }
      }
      else
      {
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
        CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
        return 14;
      }
    }
  }
  else
  {
    v13 = GetLastError();
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v17);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v20);
    return v13;
  }
}

```

## disassembly

```asm
0x180010f20  push    rbp
0x180010f22  push    rbx
0x180010f23  push    rsi
0x180010f24  push    rdi
0x180010f25  push    r12
0x180010f27  push    r14
0x180010f29  push    r15
0x180010f2b  mov     rbp, rsp
0x180010f2e  sub     rsp, 80h
0x180010f35  mov     r14, r9
0x180010f38  mov     r15, r8
0x180010f3b  mov     ebx, edx
0x180010f3d  xor     r12d, r12d
0x180010f40  mov     [rbp+NumberOfBytesRead], r12d
0x180010f44  mov     qword ptr [rbp+FileSize], r12
0x180010f48  mov     [rbp+var_10], r12
0x180010f4c  mov     [rbp+var_8], r12d
0x180010f50  mov     [rbp+var_18], r12
0x180010f54  mov     rax, cs:__imp_CloseHandle
0x180010f5b  mov     [rbp+var_30], rax
0x180010f5f  mov     [rbp+var_28], r12
0x180010f63  mov     [rbp+var_20], r12d
0x180010f67  mov     [rsp+80h+hTemplateFile], r12; hTemplateFile
0x180010f6c  mov     [rsp+80h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180010f74  mov     [rsp+80h+dwCreationDisposition], 3; dwCreationDisposition
0x180010f7c  xor     r9d, r9d; lpSecurityAttributes
0x180010f7f  mov     edx, 80000000h; dwDesiredAccess
0x180010f84  mov     r8d, 1; dwShareMode
0x180010f8a  call    cs:__imp_CreateFileW
0x180010f90  mov     rsi, rax
0x180010f93  lea     rcx, [rbp+var_30]
0x180010f97  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180010f9c  mov     [rbp+var_28], rsi
0x180010fa0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180010fa4  jz      loc_180011048
0x180010faa  lea     rdx, [rbp+FileSize]; lpFileSize
0x180010fae  mov     rcx, rsi; hFile
0x180010fb1  call    cs:__imp_GetFileSizeEx
0x180010fb7  test    eax, eax
0x180010fb9  jz      loc_180011069
0x180010fbf  cmp     dword ptr [rbp+FileSize+4], r12d
0x180010fc3  jnz     loc_180011089
0x180010fc9  mov     edi, dword ptr [rbp+FileSize]
0x180010fcc  test    ebx, ebx
0x180010fce  jz      short loc_180010FD8
0x180010fd0  cmp     edi, ebx
0x180010fd2  ja      loc_1800110A4
0x180010fd8  mov     rdx, rdi; uBytes
0x180010fdb  mov     ecx, 40h ; '@'; uFlags
0x180010fe0  call    cs:__imp_LocalAlloc
0x180010fe6  mov     rbx, rax
0x180010fe9  mov     [rbp+var_10], rax
0x180010fed  test    rax, rax
0x180010ff0  jz      loc_1800110C2
0x180010ff6  mov     qword ptr [rsp+80h+dwCreationDisposition], r12; lpOverlapped
0x180010ffb  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180010fff  mov     r8d, edi; nNumberOfBytesToRead
0x180011002  mov     rdx, rax; lpBuffer
0x180011005  mov     rcx, rsi; hFile
0x180011008  call    cs:__imp_ReadFile
0x18001100e  test    eax, eax
0x180011010  jz      loc_1800110E0
0x180011016  mov     [r15], rbx
0x180011019  mov     [r14], edi
0x18001101c  mov     [rbp+var_10], r12
0x180011020  lea     rcx, [rbp+var_30]
0x180011024  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011029  nop
0x18001102a  lea     rcx, [rbp+var_18]
0x18001102e  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011033  nop
0x180011034  xor     eax, eax
0x180011036  add     rsp, 80h
0x18001103d  pop     r15
0x18001103f  pop     r14
0x180011041  pop     r12
0x180011043  pop     rdi
0x180011044  pop     rsi
0x180011045  pop     rbx
0x180011046  pop     rbp
0x180011047  retn
0x180011048  call    cs:__imp_GetLastError
0x18001104e  nop
0x18001104f  mov     ebx, eax
0x180011051  lea     rcx, [rbp+var_30]
0x180011055  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001105a  nop
0x18001105b  lea     rcx, [rbp+var_18]
0x18001105f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011064  nop
0x180011065  mov     eax, ebx
0x180011067  jmp     short loc_180011036
0x180011069  call    cs:__imp_GetLastError
0x18001106f  mov     ebx, eax
0x180011071  lea     rcx, [rbp+var_30]
0x180011075  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001107a  nop
0x18001107b  lea     rcx, [rbp+var_18]
0x18001107f  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011084  nop
0x180011085  mov     eax, ebx
0x180011087  jmp     short loc_180011036
0x180011089  lea     rcx, [rbp+var_30]
0x18001108d  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180011092  nop
0x180011093  lea     rcx, [rbp+var_18]
0x180011097  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x18001109c  nop
0x18001109d  mov     eax, 0DFh
0x1800110a2  jmp     short loc_180011036
0x1800110a4  lea     rcx, [rbp+var_30]
0x1800110a8  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110ad  nop
0x1800110ae  lea     rcx, [rbp+var_18]
0x1800110b2  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110b7  nop
0x1800110b8  mov     eax, 0DFh
0x1800110bd  jmp     loc_180011036
0x1800110c2  lea     rcx, [rbp+var_30]
0x1800110c6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110cb  nop
0x1800110cc  lea     rcx, [rbp+var_18]
0x1800110d0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110d5  nop
0x1800110d6  mov     eax, 0Eh
0x1800110db  jmp     loc_180011036
0x1800110e0  call    cs:__imp_GetLastError
0x1800110e6  mov     ebx, eax
0x1800110e8  lea     rcx, [rbp+var_30]
0x1800110ec  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110f1  nop
0x1800110f2  lea     rcx, [rbp+var_18]
0x1800110f6  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x1800110fb  nop
0x1800110fc  mov     eax, ebx
0x1800110fe  jmp     loc_180011036
```

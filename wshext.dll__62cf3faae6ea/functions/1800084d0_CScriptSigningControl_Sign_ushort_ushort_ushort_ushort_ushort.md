# CScriptSigningControl::Sign(ushort *,ushort *,ushort *,ushort *,ushort * *)

- ea: `0x1800084d0`
- end: `0x18000869a`
- name: `?Sign@CScriptSigningControl@@UEAAJPEAG000PEAPEAG@Z`
- size: `458`
- prototype: `int(CScriptSigningControl *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180008178`
- `0x1800084d0`
- `0x1800086a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800085ee`
- `KERNEL32!GetLastError` at `0x1800085ee`
- `KERNEL32!ReadFile` at `0x18000864f`
- `KERNEL32!ReadFile` at `0x18000864f`
- `KERNEL32!SetFilePointer` at `0x1800085df`
- `KERNEL32!SetFilePointer` at `0x1800085df`
- `KERNEL32!CloseHandle` at `0x180008671`
- `KERNEL32!CloseHandle` at `0x180008671`
- `KERNEL32!GetFileSize` at `0x18000860a`
- `KERNEL32!GetFileSize` at `0x18000860a`
- `OLEAUT32!__imp_SysFreeString` at `0x180008663`
- `OLEAUT32!__imp_SysFreeString` at `0x18000867c`
- `OLEAUT32!__imp_SysFreeString` at `0x180008663`
- `OLEAUT32!__imp_SysFreeString` at `0x18000867c`
- `OLEAUT32!__imp_SysStringLen` at `0x180008523`
- `OLEAUT32!__imp_SysStringLen` at `0x180008534`
- `OLEAUT32!__imp_SysStringLen` at `0x18000854c`
- `OLEAUT32!__imp_SysStringLen` at `0x180008575`
- `OLEAUT32!__imp_SysStringLen` at `0x180008523`
- `OLEAUT32!__imp_SysStringLen` at `0x180008534`
- `OLEAUT32!__imp_SysStringLen` at `0x18000854c`
- `OLEAUT32!__imp_SysStringLen` at `0x180008575`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000861e`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x18000861e`

## pseudocode

```c
__int64 __fastcall CScriptSigningControl::Sign(
        CScriptSigningControl *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *pbstr,
        unsigned __int16 **a6)
{
  unsigned __int16 *v10; // rdi
  const wchar_t *v11; // r15
  const WCHAR *v12; // r12
  UINT v13; // eax
  int TempFile; // eax
  HANDLE v15; // rsi
  int v16; // ebx
  DWORD v17; // ebx
  signed int LastError; // eax
  DWORD FileSize; // eax
  BSTR v20; // rax
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-58h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-50h] BYREF
  HANDLE hFile[9]; // [rsp+40h] [rbp-48h] BYREF

  hFile[0] = 0;
  NumberOfBytesRead = 0;
  bstrString = 0;
  if ( !a6 )
    return 2147500035LL;
  *a6 = 0;
  if ( !SysStringLen(a2) || !SysStringLen(a4) )
    return 2147942487LL;
  v10 = 0;
  v11 = L"my";
  v12 = &Default;
  if ( SysStringLen(pbstr) )
    v11 = pbstr;
  if ( a3 )
    v12 = a3;
  v13 = SysStringLen(a3);
  TempFile = SafeCreateTempFile(a2, a3, v13, hFile, (CHAR *)&bstrString);
  v15 = hFile[0];
  v16 = TempFile;
  if ( TempFile >= 0 )
  {
    v16 = SignFile((__int64)hFile[0], (__int64)bstrString, a4, v11);
    if ( v16 >= 0 )
    {
      v17 = SetFilePointer(v15, *v12 != 0xFEFF ? 2 : 0, 0, 0);
      if ( v17 != -1 )
      {
        FileSize = GetFileSize(v15, 0);
        NumberOfBytesRead = FileSize;
        if ( FileSize != -1 )
        {
          v20 = SysAllocStringByteLen(0, FileSize - v17);
          v10 = v20;
          if ( !v20 )
          {
            v16 = -2147024882;
            goto LABEL_19;
          }
          if ( ReadFile(v15, v20, NumberOfBytesRead - v17, &NumberOfBytesRead, 0) )
          {
            *a6 = v10;
            v10 = 0;
            v16 = 0;
            goto LABEL_19;
          }
        }
      }
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_19:
  SysFreeString(v10);
  if ( v15 )
    CloseHandle(v15);
  SysFreeString(bstrString);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800084d0  push    rbx
0x1800084d2  push    rbp
0x1800084d3  push    rsi
0x1800084d4  push    rdi
0x1800084d5  push    r12
0x1800084d7  push    r14
0x1800084d9  push    r15
0x1800084db  sub     rsp, 50h
0x1800084df  mov     r14, [rsp+88h+arg_28]
0x1800084e7  mov     rbp, r9
0x1800084ea  mov     [rsp+88h+hFile], 0
0x1800084f3  mov     rsi, r8
0x1800084f6  mov     [rsp+88h+NumberOfBytesRead], 0
0x1800084fe  mov     rbx, rdx
0x180008501  mov     [rsp+88h+bstrString], 0
0x18000850a  test    r14, r14
0x18000850d  jnz     short loc_180008519
0x18000850f  mov     eax, 80004003h
0x180008514  jmp     loc_18000868B
0x180008519  mov     rcx, rbx; pbstr
0x18000851c  mov     qword ptr [r14], 0
0x180008523  call    cs:__imp_SysStringLen
0x180008529  test    eax, eax
0x18000852b  jz      loc_180008686
0x180008531  mov     rcx, rbp; pbstr
0x180008534  call    cs:__imp_SysStringLen
0x18000853a  test    eax, eax
0x18000853c  jz      loc_180008686
0x180008542  mov     rcx, [rsp+88h+pbstr]; pbstr
0x18000854a  xor     edi, edi
0x18000854c  call    cs:__imp_SysStringLen
0x180008552  lea     r15, aMy; "my"
0x180008559  mov     rcx, rsi; pbstr
0x18000855c  test    eax, eax
0x18000855e  lea     r12, Default
0x180008565  cmovnz  r15, [rsp+88h+pbstr]
0x18000856e  test    rsi, rsi
0x180008571  cmovnz  r12, rsi
0x180008575  call    cs:__imp_SysStringLen
0x18000857b  lea     r9, [rsp+88h+hFile]
0x180008580  mov     rdx, rsi; lpBuffer
0x180008583  mov     r8d, eax
0x180008586  mov     rcx, rbx; lpWideCharStr
0x180008589  lea     rax, [rsp+88h+bstrString]
0x18000858e  mov     [rsp+88h+lpOverlapped], rax; lpPathName
0x180008593  call    SafeCreateTempFile
0x180008598  mov     rsi, [rsp+88h+hFile]
0x18000859d  mov     ebx, eax
0x18000859f  test    eax, eax
0x1800085a1  js      loc_180008660
0x1800085a7  mov     rdx, [rsp+88h+bstrString]
0x1800085ac  mov     r9, r15
0x1800085af  mov     r8, rbp
0x1800085b2  mov     rcx, rsi
0x1800085b5  call    SignFile
0x1800085ba  mov     ebx, eax
0x1800085bc  test    eax, eax
0x1800085be  js      loc_180008660
0x1800085c4  mov     eax, 0FEFFh
0x1800085c9  mov     rcx, rsi; hFile
0x1800085cc  sub     ax, [r12]
0x1800085d1  neg     ax
0x1800085d4  sbb     edx, edx
0x1800085d6  xor     r9d, r9d; dwMoveMethod
0x1800085d9  and     edx, 2; lDistanceToMove
0x1800085dc  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800085df  call    cs:__imp_SetFilePointer
0x1800085e5  or      ebp, 0FFFFFFFFh
0x1800085e8  mov     ebx, eax
0x1800085ea  cmp     eax, ebp
0x1800085ec  jnz     short loc_180008605
0x1800085ee  call    cs:__imp_GetLastError
0x1800085f4  mov     ebx, eax
0x1800085f6  test    eax, eax
0x1800085f8  jle     short loc_180008660
0x1800085fa  movzx   ebx, ax
0x1800085fd  or      ebx, 80070000h
0x180008603  jmp     short loc_180008660
0x180008605  xor     edx, edx; lpFileSizeHigh
0x180008607  mov     rcx, rsi; hFile
0x18000860a  call    cs:__imp_GetFileSize
0x180008610  mov     [rsp+88h+NumberOfBytesRead], eax
0x180008614  cmp     eax, ebp
0x180008616  jz      short loc_1800085EE
0x180008618  sub     eax, ebx
0x18000861a  xor     ecx, ecx; psz
0x18000861c  mov     edx, eax; len
0x18000861e  call    cs:__imp_SysAllocStringByteLen
0x180008624  mov     rdi, rax
0x180008627  test    rax, rax
0x18000862a  jnz     short loc_180008633
0x18000862c  mov     ebx, 8007000Eh
0x180008631  jmp     short loc_180008660
0x180008633  mov     r8d, [rsp+88h+NumberOfBytesRead]
0x180008638  lea     r9, [rsp+88h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000863d  sub     r8d, ebx; nNumberOfBytesToRead
0x180008640  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x180008649  mov     rdx, rdi; lpBuffer
0x18000864c  mov     rcx, rsi; hFile
0x18000864f  call    cs:__imp_ReadFile
0x180008655  test    eax, eax
0x180008657  jz      short loc_1800085EE
0x180008659  mov     [r14], rdi
0x18000865c  xor     edi, edi
0x18000865e  xor     ebx, ebx
0x180008660  mov     rcx, rdi; bstrString
0x180008663  call    cs:__imp_SysFreeString
0x180008669  test    rsi, rsi
0x18000866c  jz      short loc_180008677
0x18000866e  mov     rcx, rsi; hObject
0x180008671  call    cs:__imp_CloseHandle
0x180008677  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18000867c  call    cs:__imp_SysFreeString
0x180008682  mov     eax, ebx
0x180008684  jmp     short loc_18000868B
0x180008686  mov     eax, 80070057h
0x18000868b  add     rsp, 50h
0x18000868f  pop     r15
0x180008691  pop     r14
0x180008693  pop     r12
0x180008695  pop     rdi
0x180008696  pop     rsi
0x180008697  pop     rbp
0x180008698  pop     rbx
0x180008699  retn
```

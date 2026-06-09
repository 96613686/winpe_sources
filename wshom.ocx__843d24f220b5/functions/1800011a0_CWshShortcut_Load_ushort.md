# CWshShortcut::Load(ushort *)

- ea: `0x1800011a0`
- end: `0x1800013df`
- name: `?Load@CWshShortcut@@UEAAJPEAG@Z`
- size: `575`
- prototype: `int __fastcall(CWshShortcut *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800011a0`
- `0x180010250`
- `0x1800102e0`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800012ed`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800012ed`
- `ole32!CoCreateInstance` at `0x180001342`
- `ole32!CoCreateInstance` at `0x180001342`
- `KERNEL32!GetLastError` at `0x180001282`
- `KERNEL32!GetLastError` at `0x180001282`
- `KERNEL32!WideCharToMultiByte` at `0x18000120d`
- `KERNEL32!WideCharToMultiByte` at `0x18000125e`
- `KERNEL32!WideCharToMultiByte` at `0x18000120d`
- `KERNEL32!WideCharToMultiByte` at `0x18000125e`
- `KERNEL32!MultiByteToWideChar` at `0x1800012d8`
- `KERNEL32!MultiByteToWideChar` at `0x180001313`
- `KERNEL32!MultiByteToWideChar` at `0x1800012d8`
- `KERNEL32!MultiByteToWideChar` at `0x180001313`
- `KERNEL32!GetFullPathNameA` at `0x180001278`
- `KERNEL32!GetFullPathNameA` at `0x180001278`

## pseudocode

```c
int __fastcall CWshShortcut::Load(CWshShortcut *this, unsigned __int16 *a2)
{
  CHAR *v4; // rsi
  int v5; // eax
  unsigned __int64 cbMultiByte; // rdx
  __int64 v7; // rax
  void *v8; // rsp
  DWORD FullPathNameA; // eax
  int result; // eax
  int v11; // eax
  int v12; // ebx
  WCHAR *v13; // rax
  _QWORD *v14; // rsi
  int v15; // ebx
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  CHAR Buffer[272]; // [rsp+50h] [rbp+10h] BYREF

  if ( !a2 )
    return -2147467261;
  if ( *((_QWORD *)this + 11) )
    return -2147418113;
  v4 = 0;
  v5 = WideCharToMultiByte(0, 0, a2, -1, 0, 0, 0, 0);
  cbMultiByte = v5;
  if ( v5 )
  {
    v7 = v5 + 15LL;
    if ( cbMultiByte + 15 < cbMultiByte )
      v7 = 0xFFFFFFFFFFFFFF0LL;
    v8 = alloca(v7 & 0xFFFFFFFFFFFFFFF0uLL);
    v4 = MultiByteStr;
    WideCharToMultiByte(0, 0, a2, -1, MultiByteStr, cbMultiByte, 0, 0);
  }
  *(_QWORD *)MultiByteStr = 0;
  FullPathNameA = GetFullPathNameA(v4, 0x104u, Buffer, (LPSTR *)MultiByteStr);
  if ( FullPathNameA )
  {
    if ( FullPathNameA >= 0x104 )
    {
      return -2147024809;
    }
    else
    {
      v11 = MultiByteToWideChar(0, 0, Buffer, -1, 0, 0);
      v12 = v11;
      if ( v11 )
      {
        v13 = SysAllocStringLen(0, v11 - 1);
        *((_QWORD *)this + 11) = v13;
        if ( v13 )
          MultiByteToWideChar(0, 0, Buffer, -1, v13, v12);
      }
      else
      {
        *((_QWORD *)this + 11) = 0;
      }
      if ( *((_QWORD *)this + 11) )
      {
        v14 = (_QWORD *)((char *)this + 72);
        result = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkA, (LPVOID *)this + 9);
        if ( result >= 0 )
        {
          v15 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v14)(*v14, &IID_IPersistFile, (char *)this + 80);
          if ( v15 < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v14 + 16LL))(*v14);
            *v14 = 0;
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 10) + 40LL))(
              *((_QWORD *)this + 10),
              *((_QWORD *)this + 11),
              0);
          }
          return v15;
        }
      }
      else
      {
        return -2147024882;
      }
    }
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800011a0  push    rbp
0x1800011a2  push    rsi
0x1800011a3  push    rdi
0x1800011a4  push    r14
0x1800011a6  push    r15
0x1800011a8  sub     rsp, 170h
0x1800011af  lea     rbp, [rsp+40h]
0x1800011b4  mov     [rbp+150h+arg_10], rbx
0x1800011bb  mov     rax, cs:__security_cookie
0x1800011c2  xor     rax, rbp
0x1800011c5  mov     [rbp+150h+var_30], rax
0x1800011cc  mov     rbx, rdx
0x1800011cf  mov     rdi, rcx
0x1800011d2  test    rdx, rdx
0x1800011d5  jz      loc_18000138D
0x1800011db  cmp     qword ptr [rcx+58h], 0
0x1800011e0  jnz     loc_1800013A1
0x1800011e6  xor     r15d, r15d
0x1800011e9  mov     r8, rdx; lpWideCharStr
0x1800011ec  mov     [rsp+190h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800011f1  mov     r9d, 0FFFFFFFFh; cchWideChar
0x1800011f7  mov     [rsp+190h+lpDefaultChar], r15; lpDefaultChar
0x1800011fc  xor     edx, edx; dwFlags
0x1800011fe  mov     [rsp+190h+cbMultiByte], r15d; cbMultiByte
0x180001203  xor     ecx, ecx; CodePage
0x180001205  mov     [rsp+190h+lpMultiByteStr], r15; lpMultiByteStr
0x18000120a  mov     esi, r15d
0x18000120d  call    cs:__imp_WideCharToMultiByte
0x180001213  movsxd  rdx, eax
0x180001216  test    eax, eax
0x180001218  jz      short loc_180001264
0x18000121a  lea     rax, [rdx+0Fh]
0x18000121e  cmp     rax, rdx
0x180001221  ja      short loc_18000122D
0x180001223  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000122d  and     rax, 0FFFFFFFFFFFFFFF0h
0x180001231  call    _alloca_probe
0x180001236  sub     rsp, rax
0x180001239  mov     r9d, 0FFFFFFFFh; cchWideChar
0x18000123f  mov     r8, rbx; lpWideCharStr
0x180001242  xor     ecx, ecx; CodePage
0x180001244  mov     [rsp+190h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x180001249  lea     rsi, [rsp+190h+MultiByteStr]
0x18000124e  mov     [rsp+190h+lpDefaultChar], r15; lpDefaultChar
0x180001253  mov     [rsp+190h+cbMultiByte], edx; cbMultiByte
0x180001257  xor     edx, edx; dwFlags
0x180001259  mov     [rsp+190h+lpMultiByteStr], rsi; lpMultiByteStr
0x18000125e  call    cs:__imp_WideCharToMultiByte
0x180001264  lea     r9, [rbp+150h+MultiByteStr]; lpFilePart
0x180001268  mov     qword ptr [rbp+150h+MultiByteStr], r15
0x18000126c  lea     r8, [rbp+150h+Buffer]; lpBuffer
0x180001270  mov     edx, 104h; nBufferLength
0x180001275  mov     rcx, rsi; lpFileName
0x180001278  call    cs:__imp_GetFullPathNameA
0x18000127e  test    eax, eax
0x180001280  jnz     short loc_1800012B5
0x180001282  call    cs:__imp_GetLastError
0x180001288  test    eax, eax
0x18000128a  jg      loc_1800013AB
0x180001290  mov     rcx, [rbp+150h+var_30]
0x180001297  xor     rcx, rbp; StackCookie
0x18000129a  call    __security_check_cookie
0x18000129f  mov     rbx, [rbp+150h+arg_10]
0x1800012a6  lea     rsp, [rbp+130h]
0x1800012ad  pop     r15
0x1800012af  pop     r14
0x1800012b1  pop     rdi
0x1800012b2  pop     rsi
0x1800012b3  pop     rbp
0x1800012b4  retn
0x1800012b5  cmp     eax, 104h
0x1800012ba  jnb     loc_180001397
0x1800012c0  mov     [rsp+190h+cbMultiByte], r15d; cchWideChar
0x1800012c5  lea     r8, [rbp+150h+Buffer]; lpMultiByteStr
0x1800012c9  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x1800012cf  mov     [rsp+190h+lpMultiByteStr], r15; lpWideCharStr
0x1800012d4  xor     edx, edx; dwFlags
0x1800012d6  xor     ecx, ecx; CodePage
0x1800012d8  call    cs:__imp_MultiByteToWideChar
0x1800012de  mov     ebx, eax
0x1800012e0  test    eax, eax
0x1800012e2  jz      loc_1800013B8
0x1800012e8  lea     edx, [rax-1]; ui
0x1800012eb  xor     ecx, ecx; strIn
0x1800012ed  call    cs:__imp_SysAllocStringLen
0x1800012f3  mov     [rdi+58h], rax
0x1800012f7  test    rax, rax
0x1800012fa  jz      short loc_180001319
0x1800012fc  mov     [rsp+190h+cbMultiByte], ebx; cchWideChar
0x180001300  lea     r8, [rbp+150h+Buffer]; lpMultiByteStr
0x180001304  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000130a  mov     [rsp+190h+lpMultiByteStr], rax; lpWideCharStr
0x18000130f  xor     edx, edx; dwFlags
0x180001311  xor     ecx, ecx; CodePage
0x180001313  call    cs:__imp_MultiByteToWideChar
0x180001319  cmp     [rdi+58h], r15
0x18000131d  jz      loc_1800013C1
0x180001323  lea     rsi, [rdi+48h]
0x180001327  xor     edx, edx; pUnkOuter
0x180001329  lea     r9, IID_IShellLinkA; riid
0x180001330  mov     [rsp+190h+lpMultiByteStr], rsi; ppv
0x180001335  mov     r8d, 1; dwClsContext
0x18000133b  lea     rcx, CLSID_ShellLink; rclsid
0x180001342  call    cs:__imp_CoCreateInstance
0x180001348  test    eax, eax
0x18000134a  js      loc_180001290
0x180001350  mov     rcx, [rsi]
0x180001353  lea     r8, [rdi+50h]
0x180001357  lea     rdx, IID_IPersistFile
0x18000135e  mov     rax, [rcx]
0x180001361  mov     rax, [rax]
0x180001364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001369  mov     ebx, eax
0x18000136b  test    eax, eax
0x18000136d  js      short loc_1800013CB
0x18000136f  mov     rcx, [rdi+50h]
0x180001373  xor     r8d, r8d
0x180001376  mov     rdx, [rdi+58h]
0x18000137a  mov     rax, [rcx]
0x18000137d  mov     rax, [rax+28h]
0x180001381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001386  mov     eax, ebx
0x180001388  jmp     loc_180001290
0x18000138d  mov     eax, 80004003h
0x180001392  jmp     loc_180001290
0x180001397  mov     eax, 80070057h
0x18000139c  jmp     loc_180001290
0x1800013a1  mov     eax, 8000FFFFh
0x1800013a6  jmp     loc_180001290
0x1800013ab  movzx   eax, ax
0x1800013ae  or      eax, 80070000h
0x1800013b3  jmp     loc_180001290
0x1800013b8  mov     [rdi+58h], r15
0x1800013bc  jmp     loc_180001319
0x1800013c1  mov     eax, 8007000Eh
0x1800013c6  jmp     loc_180001290
0x1800013cb  mov     rcx, [rsi]
0x1800013ce  mov     rdx, [rcx]
0x1800013d1  mov     rax, [rdx+10h]
0x1800013d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013da  mov     [rsi], r15
0x1800013dd  jmp     short loc_180001386
```

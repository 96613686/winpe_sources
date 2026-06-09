# EdpEncryptExisting(ushort const *,ushort const *,int)

- ea: `0x18014887c`
- end: `0x180148b41`
- name: `?EdpEncryptExisting@@YAJPEBG0H@Z`
- size: `709`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x180148b70`

## callees

- `0x180021494`
- `0x180025910`
- `0x1800701d0`
- `0x18012ce48`
- `0x18014887c`
- `0x180148b48`
- `0x180148cfc`
- `0x18014a7a0`
- `0x1801e1790`
- `0x1801e21a0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801489fc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801489fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148a11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148b08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148a11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180148b08`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180148aa3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180148aa3`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180148a61`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180148a61`
- `srpapi!SrpCloseThreadNetworkContext` at `0x180148a29`
- `srpapi!SrpCloseThreadNetworkContext` at `0x180148a29`
- `srpapi!SrpCreateThreadNetworkContext` at `0x1801489c3`
- `srpapi!SrpCreateThreadNetworkContext` at `0x1801489c3`

## pseudocode

```c
__int64 __fastcall EdpEncryptExisting(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v6; // esi
  signed int LastError; // edi
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  HANDLE FileW; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // sf
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // eax
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-50h] BYREF
  __int128 v24; // [rsp+58h] [rbp-40h] BYREF

  lpFileName[0] = &Data;
  lpFileName[1] = 0;
  v24 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_SS(1036, 26, (unsigned int)WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids, (_DWORD)a1, (__int64)a2);
  if ( !a1 )
  {
    v6 = -2147024809;
    LastError = -2147024809;
    goto LABEL_39;
  }
  if ( !a2 )
  {
    v6 = -2147024809;
    LastError = -2147024809;
    goto LABEL_39;
  }
  v8 = -1;
  do
    ++v8;
  while ( a1[v8] );
  if ( (unsigned int)v8 > 0x104 )
  {
    LastError = -2147024690;
LABEL_11:
    v6 = LastError;
    goto LABEL_39;
  }
  v9 = CWxString::Set((CWxString *)lpFileName, a1, L".tmp");
  LastError = v9;
  if ( v9 < 0 )
    goto LABEL_13;
  v9 = CWxString::AntiCanonicalize((CWxString *)lpFileName);
  LastError = v9;
  if ( v9 < 0 )
    goto LABEL_13;
  v10 = TryDeleteFile(lpFileName[0]);
  LastError = v10;
  if ( v10 > 0 )
    LastError = (unsigned __int16)v10 | 0x80070000;
  if ( LastError < 0 )
    goto LABEL_11;
  v9 = SrpCreateThreadNetworkContext(a2, &v24);
  LastError = v9;
  if ( v9 < 0 )
  {
LABEL_13:
    v6 = v9;
  }
  else
  {
    FileW = CreateFileW(lpFileName[0], 0x40000000u, 7u, 0, 2u, 0, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = WxGetLastError(v13, v12);
    }
    else
    {
      LastError = 0;
      CloseHandle(FileW);
    }
    v14 = SrpCloseThreadNetworkContext(&v24);
    WxFatalHResult(v14);
    v15 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v15 = LastError < 0;
    }
    if ( v15 )
      goto LABEL_11;
    if ( a3 || CopyFileW(a1, lpFileName[0], 0) )
    {
      if ( MoveFileExW(lpFileName[0], a1, 1u) )
      {
        LastError = 0;
        v6 = 0;
      }
      else
      {
        v21 = WxGetLastError(v20, v19);
        LastError = v21;
        if ( v21 > 0 )
          LastError = (unsigned __int16)v21 | 0x80070000;
        if ( LastError < 0 )
        {
          v6 = LastError;
        }
        else
        {
          v6 = -2147418113;
          LastError = -2147418113;
        }
      }
    }
    else
    {
      v18 = WxGetLastError(v17, v16);
      LastError = v18;
      if ( v18 > 0 )
        LastError = (unsigned __int16)v18 | 0x80070000;
      if ( LastError < 0 )
      {
        v6 = LastError;
      }
      else
      {
        v6 = -2147418113;
        LastError = -2147418113;
      }
    }
  }
LABEL_39:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 27, WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids, (unsigned int)LastError);
  CWxString::_Release((CWxString *)lpFileName);
  return v6;
}

```

## disassembly

```asm
0x18014887c  mov     r11, rsp
0x18014887f  mov     [r11+18h], rbx
0x180148883  mov     [r11+20h], rsi
0x180148887  push    rdi
0x180148888  push    r12
0x18014888a  push    r13
0x18014888c  push    r14
0x18014888e  push    r15
0x180148890  sub     rsp, 70h
0x180148894  mov     rax, cs:__security_cookie
0x18014889b  xor     rax, rsp
0x18014889e  mov     [rsp+98h+var_30], rax
0x1801488a3  xor     r12d, r12d
0x1801488a6  lea     rax, Data
0x1801488ad  xorps   xmm0, xmm0
0x1801488b0  mov     [rsp+98h+var_54], r12d
0x1801488b5  mov     [r11-50h], rax
0x1801488b9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801488bd  mov     [r11-48h], r12
0x1801488c1  mov     r15d, r8d
0x1801488c4  movups  [rsp+98h+var_40], xmm0
0x1801488c9  mov     r14, rdx
0x1801488cc  mov     rsi, rcx
0x1801488cf  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1801488d6  jz      short loc_1801488F3
0x1801488d8  lea     edx, [rbx+1Bh]
0x1801488db  mov     [r11-78h], r14
0x1801488df  mov     ecx, 40Ch
0x1801488e4  lea     r8, WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids
0x1801488eb  mov     r9, rsi
0x1801488ee  call    WPP_SF_SS
0x1801488f3  test    rsi, rsi
0x1801488f6  jnz     short loc_18014890C
0x1801488f8  mov     esi, 80070057h
0x1801488fd  mov     [rsp+98h+var_54], 2B2h
0x180148905  mov     edi, esi
0x180148907  jmp     loc_180148ADD
0x18014890c  test    r14, r14
0x18014890f  jnz     short loc_180148925
0x180148911  mov     esi, 80070057h
0x180148916  mov     [rsp+98h+var_54], 2B3h
0x18014891e  mov     edi, esi
0x180148920  jmp     loc_180148ADD
0x180148925  or      rax, 0FFFFFFFFFFFFFFFFh
0x180148929  inc     rax
0x18014892c  cmp     [rsi+rax*2], r12w
0x180148931  jnz     short loc_180148929
0x180148933  cmp     eax, 104h
0x180148938  jbe     short loc_18014894E
0x18014893a  mov     edi, 800700CEh
0x18014893f  mov     [rsp+98h+var_54], 2B6h
0x180148947  mov     esi, edi
0x180148949  jmp     loc_180148ADD
0x18014894e  lea     r8, aTmp; ".tmp"
0x180148955  mov     rdx, rsi; unsigned __int16 *
0x180148958  lea     rcx, [rsp+98h+lpFileName]; this
0x18014895d  call    ?Set@CWxString@@QEAAJPEBG0@Z; CWxString::Set(ushort const *,ushort const *)
0x180148962  mov     edi, eax
0x180148964  test    eax, eax
0x180148966  jns     short loc_180148977
0x180148968  mov     [rsp+98h+var_54], 2B8h
0x180148970  mov     esi, eax
0x180148972  jmp     loc_180148ADD
0x180148977  lea     rcx, [rsp+98h+lpFileName]; this
0x18014897c  call    ?AntiCanonicalize@CWxString@@QEAAJXZ; CWxString::AntiCanonicalize(void)
0x180148981  mov     edi, eax
0x180148983  test    eax, eax
0x180148985  jns     short loc_180148991
0x180148987  mov     [rsp+98h+var_54], 2B9h
0x18014898f  jmp     short loc_180148970
0x180148991  mov     rcx, [rsp+98h+lpFileName]; unsigned __int16 *
0x180148996  call    ?TryDeleteFile@@YAKPEBG@Z; TryDeleteFile(ushort const *)
0x18014899b  mov     edi, eax
0x18014899d  mov     r13d, 80070000h
0x1801489a3  test    eax, eax
0x1801489a5  jle     short loc_1801489AD
0x1801489a7  movzx   edi, ax
0x1801489aa  or      edi, r13d
0x1801489ad  test    edi, edi
0x1801489af  jns     short loc_1801489BB
0x1801489b1  mov     [rsp+98h+var_54], 2BBh
0x1801489b9  jmp     short loc_180148947
0x1801489bb  lea     rdx, [rsp+98h+var_40]
0x1801489c0  mov     rcx, r14
0x1801489c3  call    cs:__imp_SrpCreateThreadNetworkContext
0x1801489c9  mov     edi, eax
0x1801489cb  test    eax, eax
0x1801489cd  jns     short loc_1801489D9
0x1801489cf  mov     [rsp+98h+var_54], 2BEh
0x1801489d7  jmp     short loc_180148970
0x1801489d9  mov     rcx, [rsp+98h+lpFileName]; lpFileName
0x1801489de  xor     r9d, r9d; lpSecurityAttributes
0x1801489e1  mov     [rsp+98h+hTemplateFile], r12; hTemplateFile
0x1801489e6  mov     edx, 40000000h; dwDesiredAccess
0x1801489eb  mov     [rsp+98h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x1801489f0  mov     [rsp+98h+dwCreationDisposition], 2; dwCreationDisposition
0x1801489f8  lea     r8d, [r9+7]; dwShareMode
0x1801489fc  call    cs:__imp_CreateFileW
0x180148a02  mov     rbx, rax
0x180148a05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180148a09  jz      short loc_180148A1D
0x180148a0b  mov     rcx, rax; hObject
0x180148a0e  mov     edi, r12d
0x180148a11  call    cs:__imp_CloseHandle
0x180148a17  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180148a1b  jmp     short loc_180148A24
0x180148a1d  call    WxGetLastError
0x180148a22  mov     edi, eax
0x180148a24  lea     rcx, [rsp+98h+var_40]
0x180148a29  call    cs:__imp_SrpCloseThreadNetworkContext
0x180148a2f  mov     ecx, eax; int
0x180148a31  call    ?WxFatalHResult@@YAXJ@Z; WxFatalHResult(long)
0x180148a36  test    edi, edi
0x180148a38  jle     short loc_180148A42
0x180148a3a  movzx   edi, di
0x180148a3d  or      edi, r13d
0x180148a40  test    edi, edi
0x180148a42  jns     short loc_180148A51
0x180148a44  mov     [rsp+98h+var_54], 2D3h
0x180148a4c  jmp     loc_180148947
0x180148a51  test    r15d, r15d
0x180148a54  jnz     short loc_180148A95
0x180148a56  mov     rdx, [rsp+98h+lpFileName]; lpNewFileName
0x180148a5b  xor     r8d, r8d; bFailIfExists
0x180148a5e  mov     rcx, rsi; lpExistingFileName
0x180148a61  call    cs:__imp_CopyFileW
0x180148a67  test    eax, eax
0x180148a69  jnz     short loc_180148A95
0x180148a6b  call    WxGetLastError
0x180148a70  mov     edi, eax
0x180148a72  test    eax, eax
0x180148a74  jle     short loc_180148A7C
0x180148a76  movzx   edi, ax
0x180148a79  or      edi, r13d
0x180148a7c  test    edi, edi
0x180148a7e  js      short loc_180148A89
0x180148a80  mov     esi, 8000FFFFh
0x180148a85  mov     edi, esi
0x180148a87  jmp     short loc_180148A8B
0x180148a89  mov     esi, edi
0x180148a8b  mov     [rsp+98h+var_54], 2D7h
0x180148a93  jmp     short loc_180148ADD
0x180148a95  mov     rcx, [rsp+98h+lpFileName]; lpExistingFileName
0x180148a9a  mov     r8d, 1; dwFlags
0x180148aa0  mov     rdx, rsi; lpNewFileName
0x180148aa3  call    cs:__imp_MoveFileExW
0x180148aa9  test    eax, eax
0x180148aab  jnz     short loc_180148AD7
0x180148aad  call    WxGetLastError
0x180148ab2  mov     edi, eax
0x180148ab4  test    eax, eax
0x180148ab6  jle     short loc_180148ABE
0x180148ab8  movzx   edi, ax
0x180148abb  or      edi, r13d
0x180148abe  test    edi, edi
0x180148ac0  js      short loc_180148ACB
0x180148ac2  mov     esi, 8000FFFFh
0x180148ac7  mov     edi, esi
0x180148ac9  jmp     short loc_180148ACD
0x180148acb  mov     esi, edi
0x180148acd  mov     [rsp+98h+var_54], 2DCh
0x180148ad5  jmp     short loc_180148ADD
0x180148ad7  mov     edi, r12d
0x180148ada  mov     esi, r12d
0x180148add  test    byte ptr cs:xmmword_180266B60+1, 10h
0x180148ae4  jz      short loc_180148AFF
0x180148ae6  mov     edx, 1Bh
0x180148aeb  lea     r8, WPP_29d8921fdfbf3b8597c2d9971819ee4e_Traceguids
0x180148af2  mov     ecx, 40Ch
0x180148af7  mov     r9d, edi
0x180148afa  call    WPP_SF_d
0x180148aff  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180148b03  jz      short loc_180148B0E
0x180148b05  mov     rcx, rbx; hObject
0x180148b08  call    cs:__imp_CloseHandle
0x180148b0e  lea     rcx, [rsp+98h+lpFileName]; this
0x180148b13  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x180148b18  mov     eax, esi
0x180148b1a  mov     rcx, [rsp+98h+var_30]
0x180148b1f  xor     rcx, rsp; StackCookie
0x180148b22  call    __security_check_cookie
0x180148b27  lea     r11, [rsp+98h+var_28]
0x180148b2c  mov     rbx, [r11+40h]
0x180148b30  mov     rsi, [r11+48h]
0x180148b34  mov     rsp, r11
0x180148b37  pop     r15
0x180148b39  pop     r14
0x180148b3b  pop     r13
0x180148b3d  pop     r12
0x180148b3f  pop     rdi
0x180148b40  retn
```

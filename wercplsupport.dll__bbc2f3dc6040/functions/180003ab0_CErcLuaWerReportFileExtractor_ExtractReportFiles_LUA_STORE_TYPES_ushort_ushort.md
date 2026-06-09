# CErcLuaWerReportFileExtractor::ExtractReportFiles(_LUA_STORE_TYPES,ushort *,ushort * *)

- ea: `0x180003ab0`
- end: `0x180003d92`
- name: `?ExtractReportFiles@CErcLuaWerReportFileExtractor@@QEAAJW4_LUA_STORE_TYPES@@PEAGPEAPEAG@Z`
- size: `738`
- prototype: `__int64 __fastcall(_QWORD *, int, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180003aa0`

## callees

- `0x180002850`
- `0x180002c98`
- `0x180003ab0`
- `0x18000576c`
- `0x180006c9c`
- `0x1800121b0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180003c9e`
- `OLEAUT32!__imp_SysAllocString` at `0x180003c9e`
- `wer!WerpCloseStore` at `0x180003d36`
- `wer!WerpCloseStore` at `0x180003d64`
- `wer!WerpCloseStore` at `0x180003d36`
- `wer!WerpCloseStore` at `0x180003d64`
- `wer!WerReportCloseHandle` at `0x180003c04`
- `wer!WerReportCloseHandle` at `0x180003d1d`
- `wer!WerReportCloseHandle` at `0x180003d54`
- `wer!WerReportCloseHandle` at `0x180003c04`
- `wer!WerReportCloseHandle` at `0x180003d1d`
- `wer!WerReportCloseHandle` at `0x180003d54`
- `wer!WerpOpenMachineArchive` at `0x180003b8b`
- `wer!WerpOpenMachineArchive` at `0x180003b8b`
- `wer!WerpExtractReportFiles` at `0x180003c66`
- `wer!WerpExtractReportFiles` at `0x180003c66`
- `wer!WerpLoadReport` at `0x180003c22`
- `wer!WerpLoadReport` at `0x180003c22`
- `wer!WerpOpenMachineQueue` at `0x180003b98`
- `wer!WerpOpenMachineQueue` at `0x180003b98`

## pseudocode

```c
__int64 __fastcall CErcLuaWerReportFileExtractor::ExtractReportFiles(
        _QWORD *a1,
        int a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  int v4; // esi
  unsigned __int64 v5; // rax
  int ExtractionDirectory; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  BSTR v14; // rax
  HREPORT v15; // rcx
  __int64 v16; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  HREPORT hReportHandle; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR psz[264]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = 0;
  v5 = *a1 + 1LL;
  v20 = 0;
  hReportHandle = 0;
  if ( v5 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
    ExtractionDirectory = -2147467259;
    goto LABEL_37;
  }
  if ( !a3 || !a4 )
  {
    ExtractionDirectory = -2147024809;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v11 = 59;
LABEL_36:
    WPP_SF_(v10[2], v11, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids);
    goto LABEL_37;
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      ExtractionDirectory = -2147024809;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v11 = 60;
      goto LABEL_36;
    }
    WerpOpenMachineArchive(&v20);
  }
  else
  {
    WerpOpenMachineQueue(&v20);
  }
  ExtractionDirectory = CreateExtractionDirectory(psz);
  if ( ExtractionDirectory < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v13 = 61;
    goto LABEL_19;
  }
  v4 = 1;
  hReportHandle = 0;
  v18 = 0;
  ExtractionDirectory = WerpLoadReport(v20, a3, &hReportHandle, 1);
  if ( ExtractionDirectory < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v13 = 62;
    goto LABEL_19;
  }
  ExtractionDirectory = WerpExtractReportFiles(hReportHandle, psz, *a1);
  if ( ExtractionDirectory < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_37;
    v13 = 63;
LABEL_19:
    WPP_SF_d(v12[2], v13, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids, (unsigned int)ExtractionDirectory);
    goto LABEL_37;
  }
  v14 = SysAllocString(psz);
  *(_QWORD *)a4 = v14;
  if ( v14 )
  {
    v4 = 0;
    ExtractionDirectory = 0;
    goto LABEL_37;
  }
  ExtractionDirectory = -2147024882;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 64;
    goto LABEL_36;
  }
LABEL_37:
  v15 = hReportHandle;
  hReportHandle = 0;
  if ( v15 )
    WerReportCloseHandle(v15);
  v16 = v20;
  v20 = 0;
  if ( v16 )
    WerpCloseStore();
  if ( v4 )
    UtilRecursiveRemoveDirectory(psz, a2, a3, a4, v18);
  if ( hReportHandle )
    WerReportCloseHandle(hReportHandle);
  if ( v20 )
    WerpCloseStore();
  return (unsigned int)ExtractionDirectory;
}

```

## disassembly

```asm
0x180003ab0  mov     [rsp-8+arg_8], rbx
0x180003ab5  push    rbp
0x180003ab6  push    rsi
0x180003ab7  push    rdi
0x180003ab8  push    r14
0x180003aba  push    r15
0x180003abc  lea     rbp, [rsp-160h]
0x180003ac4  sub     rsp, 260h
0x180003acb  mov     rax, cs:__security_cookie
0x180003ad2  xor     rax, rsp
0x180003ad5  mov     [rbp+180h+var_30], rax
0x180003adc  mov     rax, [rcx]
0x180003adf  xor     esi, esi
0x180003ae1  inc     rax
0x180003ae4  mov     [rsp+280h+var_248], 0
0x180003aed  mov     [rsp+280h+hReportHandle], 0
0x180003af6  mov     rdi, r9
0x180003af9  mov     r14, r8
0x180003afc  mov     r15, rcx
0x180003aff  cmp     rax, 1
0x180003b03  ja      short loc_180003B3B
0x180003b05  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b0c  lea     rax, WPP_GLOBAL_Control
0x180003b13  cmp     rcx, rax
0x180003b16  jz      short loc_180003B31
0x180003b18  test    byte ptr [rcx+1Ch], 1
0x180003b1c  jz      short loc_180003B31
0x180003b1e  mov     rcx, [rcx+10h]
0x180003b22  lea     edx, [rsi+3Ah]
0x180003b25  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003b2c  call    WPP_SF_
0x180003b31  mov     ebx, 80004005h
0x180003b36  jmp     loc_180003D0A
0x180003b3b  test    r14, r14
0x180003b3e  jz      loc_180003CD7
0x180003b44  test    rdi, rdi
0x180003b47  jz      loc_180003CD7
0x180003b4d  test    edx, edx
0x180003b4f  jz      short loc_180003B93
0x180003b51  cmp     edx, 1
0x180003b54  jz      short loc_180003B86
0x180003b56  mov     ebx, 80070057h
0x180003b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b62  lea     rax, WPP_GLOBAL_Control
0x180003b69  cmp     rcx, rax
0x180003b6c  jz      loc_180003D0A
0x180003b72  test    byte ptr [rcx+1Ch], 1
0x180003b76  jz      loc_180003D0A
0x180003b7c  mov     edx, 3Ch ; '<'
0x180003b81  jmp     loc_180003CFA
0x180003b86  lea     rcx, [rsp+280h+var_248]
0x180003b8b  call    cs:__imp_WerpOpenMachineArchive
0x180003b91  jmp     short loc_180003B9E
0x180003b93  lea     rcx, [rsp+280h+var_248]
0x180003b98  call    cs:__imp_WerpOpenMachineQueue
0x180003b9e  lea     rcx, [rsp+280h+psz]; lpPathName
0x180003ba3  call    ?CreateExtractionDirectory@@YAJPEAG@Z; CreateExtractionDirectory(ushort *)
0x180003ba8  mov     ebx, eax
0x180003baa  test    eax, eax
0x180003bac  jns     short loc_180003BEC
0x180003bae  mov     rcx, cs:WPP_GLOBAL_Control
0x180003bb5  lea     rax, WPP_GLOBAL_Control
0x180003bbc  cmp     rcx, rax
0x180003bbf  jz      loc_180003D0A
0x180003bc5  test    byte ptr [rcx+1Ch], 1
0x180003bc9  jz      loc_180003D0A
0x180003bcf  mov     edx, 3Dh ; '='
0x180003bd4  mov     rcx, [rcx+10h]
0x180003bd8  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003bdf  mov     r9d, ebx
0x180003be2  call    WPP_SF_d
0x180003be7  jmp     loc_180003D0A
0x180003bec  mov     rcx, [rsp+280h+hReportHandle]; hReportHandle
0x180003bf1  mov     esi, 1
0x180003bf6  mov     [rsp+280h+hReportHandle], 0
0x180003bff  test    rcx, rcx
0x180003c02  jz      short loc_180003C0A
0x180003c04  call    cs:__imp_WerReportCloseHandle
0x180003c0a  mov     rcx, [rsp+280h+var_248]
0x180003c0f  lea     r8, [rsp+280h+hReportHandle]
0x180003c14  mov     r9d, esi
0x180003c17  mov     [rsp+280h+var_260], 0
0x180003c1f  mov     rdx, r14
0x180003c22  call    cs:__imp_WerpLoadReport
0x180003c28  mov     ebx, eax
0x180003c2a  test    eax, eax
0x180003c2c  jns     short loc_180003C59
0x180003c2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c35  lea     rax, WPP_GLOBAL_Control
0x180003c3c  cmp     rcx, rax
0x180003c3f  jz      loc_180003D0A
0x180003c45  test    [rcx+1Ch], sil
0x180003c49  jz      loc_180003D0A
0x180003c4f  mov     edx, 3Eh ; '>'
0x180003c54  jmp     loc_180003BD4
0x180003c59  mov     r8, [r15]
0x180003c5c  lea     rdx, [rsp+280h+psz]
0x180003c61  mov     rcx, [rsp+280h+hReportHandle]
0x180003c66  call    cs:__imp_WerpExtractReportFiles
0x180003c6c  mov     ebx, eax
0x180003c6e  test    eax, eax
0x180003c70  jns     short loc_180003C99
0x180003c72  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c79  lea     rax, WPP_GLOBAL_Control
0x180003c80  cmp     rcx, rax
0x180003c83  jz      loc_180003D0A
0x180003c89  test    [rcx+1Ch], sil
0x180003c8d  jz      short loc_180003D0A
0x180003c8f  mov     edx, 3Fh ; '?'
0x180003c94  jmp     loc_180003BD4
0x180003c99  lea     rcx, [rsp+280h+psz]; psz
0x180003c9e  call    cs:__imp_SysAllocString
0x180003ca4  mov     [rdi], rax
0x180003ca7  test    rax, rax
0x180003caa  jnz     short loc_180003CD1
0x180003cac  mov     ebx, 8007000Eh
0x180003cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cb8  lea     rax, WPP_GLOBAL_Control
0x180003cbf  cmp     rcx, rax
0x180003cc2  jz      short loc_180003D0A
0x180003cc4  test    [rcx+1Ch], sil
0x180003cc8  jz      short loc_180003D0A
0x180003cca  mov     edx, 40h ; '@'
0x180003ccf  jmp     short loc_180003CFA
0x180003cd1  xor     esi, esi
0x180003cd3  xor     ebx, ebx
0x180003cd5  jmp     short loc_180003D0A
0x180003cd7  mov     ebx, 80070057h
0x180003cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ce3  lea     rax, WPP_GLOBAL_Control
0x180003cea  cmp     rcx, rax
0x180003ced  jz      short loc_180003D0A
0x180003cef  test    byte ptr [rcx+1Ch], 1
0x180003cf3  jz      short loc_180003D0A
0x180003cf5  mov     edx, 3Bh ; ';'
0x180003cfa  mov     rcx, [rcx+10h]
0x180003cfe  lea     r8, WPP_3ca0dc6e98af379c14c85ca518011099_Traceguids
0x180003d05  call    WPP_SF_
0x180003d0a  mov     rcx, [rsp+280h+hReportHandle]; hReportHandle
0x180003d0f  mov     [rsp+280h+hReportHandle], 0
0x180003d18  test    rcx, rcx
0x180003d1b  jz      short loc_180003D23
0x180003d1d  call    cs:__imp_WerReportCloseHandle
0x180003d23  mov     rcx, [rsp+280h+var_248]
0x180003d28  mov     [rsp+280h+var_248], 0
0x180003d31  test    rcx, rcx
0x180003d34  jz      short loc_180003D3C
0x180003d36  call    cs:__imp_WerpCloseStore
0x180003d3c  test    esi, esi
0x180003d3e  jz      short loc_180003D4A
0x180003d40  lea     rcx, [rsp+280h+psz]; unsigned __int16 *
0x180003d45  call    ?UtilRecursiveRemoveDirectory@@YAJPEBGH00H@Z; UtilRecursiveRemoveDirectory(ushort const *,int,ushort const *,ushort const *,int)
0x180003d4a  mov     rcx, [rsp+280h+hReportHandle]; hReportHandle
0x180003d4f  test    rcx, rcx
0x180003d52  jz      short loc_180003D5A
0x180003d54  call    cs:__imp_WerReportCloseHandle
0x180003d5a  mov     rcx, [rsp+280h+var_248]
0x180003d5f  test    rcx, rcx
0x180003d62  jz      short loc_180003D6A
0x180003d64  call    cs:__imp_WerpCloseStore
0x180003d6a  mov     eax, ebx
0x180003d6c  mov     rcx, [rbp+180h+var_30]
0x180003d73  xor     rcx, rsp; StackCookie
0x180003d76  call    __security_check_cookie
0x180003d7b  mov     rbx, [rsp+280h+arg_8]
0x180003d83  add     rsp, 260h
0x180003d8a  pop     r15
0x180003d8c  pop     r14
0x180003d8e  pop     rdi
0x180003d8f  pop     rsi
0x180003d90  pop     rbp
0x180003d91  retn
```

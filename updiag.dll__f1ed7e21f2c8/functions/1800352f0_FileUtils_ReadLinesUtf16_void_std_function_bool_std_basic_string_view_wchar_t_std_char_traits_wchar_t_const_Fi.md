# FileUtils::ReadLinesUtf16(void *,std::function<bool (std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)> const &,FileUtils::FileEncoding)

- ea: `0x1800352f0`
- end: `0x18003563e`
- name: `?ReadLinesUtf16@FileUtils@@SA_NPEAXAEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@std@@W4FileEncoding@1@@Z`
- size: `846`
- prototype: `__int64 __fastcall(HANDLE hFile)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800349bc`

## callees

- `0x180018eec`
- `0x1800352f0`
- `0x180035644`
- `0x180046e60`
- `0x180046edc`
- `0x18006932c`
- `0x180078da8`
- `0x18008fe00`
- `0x1800957dc`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180035384`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800354b2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180035384`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800354b2`

## string_xrefs

- `0x1800355f0`: `Invalid encoding for UTF-16 line reading`
- `0x180035611`: `Invalid encoding for UTF-16 line reading`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall FileUtils::ReadLinesUtf16(HANDLE hFile, __int64 a2, int a3)
{
  char v6; // bl
  unsigned __int8 v7; // r13
  char v8; // r12
  char v9; // di
  DWORD v10; // edx
  __int64 v11; // r14
  unsigned __int16 v12; // r10
  __int64 v13; // rdi
  __int64 v14; // rcx
  __int16 v15; // ax
  __int128 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int128 *v20; // rax
  __int64 v21; // rcx
  char v22; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v23[15]; // [rsp+31h] [rbp-58h] BYREF
  HANDLE hFilea; // [rsp+40h] [rbp-49h] BYREF
  __int64 v25; // [rsp+48h] [rbp-41h]
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp-29h] BYREF
  __int128 v27; // [rsp+68h] [rbp-21h] BYREF
  __int64 v28; // [rsp+78h] [rbp-11h]
  unsigned __int64 v29; // [rsp+80h] [rbp-9h]
  LPVOID lpBuffer[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v31; // [rsp+98h] [rbp+Fh]

  hFilea = hFile;
  *(_OWORD *)lpBuffer = 0;
  v31 = 0;
  std::vector<unsigned char>::vector<unsigned char>(lpBuffer, 0x2000);
  v27 = 0;
  v6 = 0;
  v28 = 0;
  v29 = 7;
  LOWORD(v27) = 0;
  NumberOfBytesRead = 0;
  v7 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  v23[0] = 0;
  if ( ReadFile(hFile, lpBuffer[0], 0x2000u, &NumberOfBytesRead, 0) )
  {
    do
    {
      v10 = NumberOfBytesRead;
      if ( !NumberOfBytesRead )
        break;
      v11 = 0;
      if ( v8 )
      {
        if ( a3 == 1 )
        {
          v12 = v7 | (*(unsigned __int8 *)lpBuffer[0] << 8);
        }
        else
        {
          if ( a3 != 2 )
          {
            std::runtime_error::runtime_error((std::runtime_error *)&hFilea, "Invalid encoding for UTF-16 line reading");
            throw (std::runtime_error *)&hFilea;
          }
          v12 = *(unsigned __int8 *)lpBuffer[0] | (v7 << 8);
        }
        if ( !(unsigned __int8)FileUtils::ProcessWcharForLine(v12, &v27, a2, &v22, v23) )
          goto LABEL_26;
        v11 = 1;
        v8 = 0;
        v10 = NumberOfBytesRead;
      }
      v13 = v11;
      if ( v11 + 1 < (unsigned __int64)v10 )
      {
        do
        {
          if ( a3 == 1 )
          {
            v14 = *((unsigned __int8 *)lpBuffer[0] + v13 + 1);
            v15 = *((unsigned __int8 *)lpBuffer[0] + v13);
          }
          else
          {
            if ( a3 != 2 )
            {
              std::runtime_error::runtime_error(
                (std::runtime_error *)&hFilea,
                "Invalid encoding for UTF-16 line reading");
              throw (std::runtime_error *)&hFilea;
            }
            v14 = *((unsigned __int8 *)lpBuffer[0] + v13);
            v15 = *((unsigned __int8 *)lpBuffer[0] + v13 + 1);
          }
          LOWORD(v14) = v15 | ((_WORD)v14 << 8);
          if ( !(unsigned __int8)FileUtils::ProcessWcharForLine(v14, &v27, a2, &v22, v23) )
            goto LABEL_26;
          v13 += 2;
          v10 = NumberOfBytesRead;
        }
        while ( v13 + 1 < (unsigned __int64)NumberOfBytesRead );
      }
      if ( (((_BYTE)v10 - (_BYTE)v11) & 1) != 0 )
      {
        v7 = *((_BYTE *)lpBuffer[0] + v10 - 1);
        v8 = 1;
      }
    }
    while ( ReadFile(hFilea, lpBuffer[0], 0x2000u, &NumberOfBytesRead, 0) );
    if ( v22 )
    {
      v16 = &v27;
      if ( v29 > 7 )
        v16 = (__int128 *)v27;
      hFilea = v16;
      v25 = v28;
      v17 = *(_QWORD *)(a2 + 56);
      if ( !v17 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v17 + 16LL))(v17, &hFilea);
      hFilea = (HANDLE)&psz;
      v25 = 0;
      v18 = *(_QWORD *)(a2 + 56);
      if ( !v18 )
        std::_Xbad_function_call();
      (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v18 + 16LL))(v18, &hFilea);
      v6 = 1;
LABEL_26:
      std::wstring::~wstring((__int64)&v27);
      std::vector<char>::~vector<char>(lpBuffer);
      return v6;
    }
    v9 = v23[0];
  }
  if ( v28 )
  {
    v20 = &v27;
    if ( v29 > 7 )
      v20 = (__int128 *)v27;
    hFilea = v20;
    v25 = v28;
    v21 = *(_QWORD *)(a2 + 56);
    if ( !v21 )
      std::_Xbad_function_call();
LABEL_35:
    (*(void (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v21 + 16LL))(v21, &hFilea);
    goto LABEL_36;
  }
  if ( v9 )
  {
    hFilea = (HANDLE)&psz;
    v25 = 0;
    v21 = *(_QWORD *)(a2 + 56);
    if ( !v21 )
      std::_Xbad_function_call();
    goto LABEL_35;
  }
LABEL_36:
  std::wstring::~wstring((__int64)&v27);
  std::vector<char>::~vector<char>(lpBuffer);
  return 1;
}

```

## disassembly

```asm
0x1800352f0  mov     [rsp-8+arg_10], rbx
0x1800352f5  push    rbp
0x1800352f6  push    rsi
0x1800352f7  push    rdi
0x1800352f8  push    r12
0x1800352fa  push    r13
0x1800352fc  push    r14
0x1800352fe  push    r15
0x180035300  lea     rbp, [rsp-27h]
0x180035305  sub     rsp, 0B0h
0x18003530c  mov     rax, cs:__security_cookie
0x180035313  xor     rax, rsp
0x180035316  mov     [rbp+57h+var_40], rax
0x18003531a  mov     r15d, r8d
0x18003531d  mov     rsi, rdx
0x180035320  mov     r14, rcx
0x180035323  mov     [rbp+57h+hFile], rcx
0x180035327  xorps   xmm0, xmm0
0x18003532a  xor     eax, eax
0x18003532c  movups  xmmword ptr [rbp+57h+lpBuffer], xmm0
0x180035330  mov     [rbp+57h+var_48], rax
0x180035334  mov     edx, 2000h
0x180035339  lea     rcx, [rbp+57h+lpBuffer]
0x18003533d  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x180035342  nop
0x180035343  xorps   xmm0, xmm0
0x180035346  movups  [rbp+57h+var_78], xmm0
0x18003534a  xor     ebx, ebx
0x18003534c  mov     [rbp+57h+var_68], rbx
0x180035350  mov     [rbp+57h+var_60], 7
0x180035358  mov     word ptr [rbp+57h+var_78], bx
0x18003535c  mov     [rbp+57h+NumberOfBytesRead], ebx
0x18003535f  mov     r13b, bl
0x180035362  mov     r12b, bl
0x180035365  mov     [rbp+57h+var_B0], bl
0x180035368  mov     dil, bl
0x18003536b  mov     [rbp+57h+var_AF], bl
0x18003536e  mov     [rsp+0E0h+lpOverlapped], rbx; lpOverlapped
0x180035373  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180035377  mov     r8d, 2000h; nNumberOfBytesToRead
0x18003537d  mov     rdx, [rbp+57h+lpBuffer]; lpBuffer
0x180035381  mov     rcx, r14; hFile
0x180035384  call    cs:__imp_ReadFile
0x18003538a  test    eax, eax
0x18003538c  jz      loc_180035545
0x180035392  mov     edx, [rbp+57h+NumberOfBytesRead]
0x180035395  test    edx, edx
0x180035397  jz      loc_1800354C0
0x18003539d  mov     r14, rbx
0x1800353a0  test    r12b, r12b
0x1800353a3  jz      short loc_180035412
0x1800353a5  mov     ecx, r15d
0x1800353a8  sub     ecx, 1
0x1800353ab  jz      short loc_1800353CC
0x1800353ad  cmp     ecx, 1
0x1800353b0  jnz     loc_1800355F0
0x1800353b6  movzx   r10d, r13b
0x1800353ba  shl     r10w, 8
0x1800353bf  mov     rax, [rbp+57h+lpBuffer]
0x1800353c3  movzx   ecx, byte ptr [rax]
0x1800353c6  or      r10w, cx
0x1800353ca  jmp     short loc_1800353E1
0x1800353cc  mov     rax, [rbp+57h+lpBuffer]
0x1800353d0  movzx   r10d, byte ptr [rax]
0x1800353d4  shl     r10w, 8
0x1800353d9  movzx   eax, r13b
0x1800353dd  or      r10w, ax
0x1800353e1  lea     rax, [rbp+57h+var_AF]
0x1800353e5  mov     [rsp+0E0h+lpOverlapped], rax
0x1800353ea  lea     r9, [rbp+57h+var_B0]
0x1800353ee  mov     r8, rsi
0x1800353f1  lea     rdx, [rbp+57h+var_78]
0x1800353f5  movzx   ecx, r10w
0x1800353f9  call    ?ProcessWcharForLine@FileUtils@@SA_N_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@3@AEA_N3@Z; FileUtils::ProcessWcharForLine(wchar_t,std::wstring &,std::function<bool (std::wstring_view)> const &,bool &,bool &)
0x1800353fe  test    al, al
0x180035400  jz      loc_18003552A
0x180035406  mov     r14d, 1
0x18003540c  mov     r12b, bl
0x18003540f  mov     edx, [rbp+57h+NumberOfBytesRead]
0x180035412  mov     rdi, r14
0x180035415  lea     rcx, [r14+1]
0x180035419  mov     eax, edx
0x18003541b  cmp     rcx, rax
0x18003541e  jnb     short loc_180035485
0x180035420  mov     ecx, r15d
0x180035423  sub     ecx, 1
0x180035426  jz      short loc_180035440
0x180035428  cmp     ecx, 1
0x18003542b  jnz     loc_180035611
0x180035431  mov     rax, [rbp+57h+lpBuffer]
0x180035435  movzx   ecx, byte ptr [rax+rdi]
0x180035439  movzx   eax, byte ptr [rax+rdi+1]
0x18003543e  jmp     short loc_18003544D
0x180035440  mov     rax, [rbp+57h+lpBuffer]
0x180035444  movzx   ecx, byte ptr [rax+rdi+1]
0x180035449  movzx   eax, byte ptr [rax+rdi]
0x18003544d  shl     cx, 8
0x180035451  or      cx, ax
0x180035454  lea     rax, [rbp+57h+var_AF]
0x180035458  mov     [rsp+0E0h+lpOverlapped], rax
0x18003545d  lea     r9, [rbp+57h+var_B0]
0x180035461  mov     r8, rsi
0x180035464  lea     rdx, [rbp+57h+var_78]
0x180035468  call    ?ProcessWcharForLine@FileUtils@@SA_N_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$function@$$A6A_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z@3@AEA_N3@Z; FileUtils::ProcessWcharForLine(wchar_t,std::wstring &,std::function<bool (std::wstring_view)> const &,bool &,bool &)
0x18003546d  test    al, al
0x18003546f  jz      loc_18003552A
0x180035475  add     rdi, 2
0x180035479  lea     rcx, [rdi+1]
0x18003547d  mov     edx, [rbp+57h+NumberOfBytesRead]
0x180035480  cmp     rcx, rdx
0x180035483  jb      short loc_180035420
0x180035485  mov     eax, edx
0x180035487  sub     al, r14b
0x18003548a  mov     r10, [rbp+57h+lpBuffer]
0x18003548e  test    al, 1
0x180035490  jz      short loc_18003549C
0x180035492  lea     eax, [rdx-1]
0x180035495  mov     r13b, [rax+r10]
0x180035499  mov     r12b, 1
0x18003549c  mov     [rsp+0E0h+lpOverlapped], rbx; lpOverlapped
0x1800354a1  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800354a5  mov     r8d, 2000h; nNumberOfBytesToRead
0x1800354ab  mov     rdx, r10; lpBuffer
0x1800354ae  mov     rcx, [rbp+57h+hFile]; hFile
0x1800354b2  call    cs:__imp_ReadFile
0x1800354b8  test    eax, eax
0x1800354ba  jnz     loc_180035392
0x1800354c0  cmp     [rbp+57h+var_B0], bl
0x1800354c3  jz      short loc_180035541
0x1800354c5  lea     rax, [rbp+57h+var_78]
0x1800354c9  cmp     [rbp+57h+var_60], 7
0x1800354ce  cmova   rax, qword ptr [rbp+57h+var_78]
0x1800354d3  mov     [rbp+57h+hFile], rax
0x1800354d7  mov     rax, [rbp+57h+var_68]
0x1800354db  mov     [rbp+57h+var_98], rax
0x1800354df  mov     rcx, [rsi+38h]
0x1800354e3  test    rcx, rcx
0x1800354e6  jz      loc_1800355EA
0x1800354ec  mov     rax, [rcx]
0x1800354ef  lea     rdx, [rbp+57h+hFile]
0x1800354f3  mov     rax, [rax+10h]
0x1800354f7  call    _guard_dispatch_icall
0x1800354fc  lea     rax, psz
0x180035503  mov     [rbp+57h+hFile], rax
0x180035507  mov     [rbp+57h+var_98], rbx
0x18003550b  mov     rcx, [rsi+38h]
0x18003550f  test    rcx, rcx
0x180035512  jz      loc_180035632
0x180035518  mov     rax, [rcx]
0x18003551b  lea     rdx, [rbp+57h+hFile]
0x18003551f  mov     rax, [rax+10h]
0x180035523  call    _guard_dispatch_icall
0x180035528  mov     bl, 1
0x18003552a  lea     rcx, [rbp+57h+var_78]
0x18003552e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180035533  nop
0x180035534  lea     rcx, [rbp+57h+lpBuffer]
0x180035538  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18003553d  mov     al, bl
0x18003553f  jmp     short loc_1800355BD
0x180035541  mov     dil, [rbp+57h+var_AF]
0x180035545  mov     rcx, [rbp+57h+var_68]
0x180035549  test    rcx, rcx
0x18003554c  jz      short loc_18003557A
0x18003554e  lea     rax, [rbp+57h+var_78]
0x180035552  cmp     [rbp+57h+var_60], 7
0x180035557  cmova   rax, qword ptr [rbp+57h+var_78]
0x18003555c  mov     [rbp+57h+hFile], rax
0x180035560  mov     [rbp+57h+var_98], rcx
0x180035564  mov     rcx, [rsi+38h]
0x180035568  test    rcx, rcx
0x18003556b  jz      loc_180035638
0x180035571  mov     rax, [rcx]
0x180035574  mov     rax, [rax+10h]
0x180035578  jmp     short loc_18003559E
0x18003557a  test    dil, dil
0x18003557d  jz      short loc_1800355A8
0x18003557f  lea     rax, psz
0x180035586  mov     [rbp+57h+hFile], rax
0x18003558a  mov     [rbp+57h+var_98], rbx
0x18003558e  mov     rcx, [rsi+38h]
0x180035592  test    rcx, rcx
0x180035595  jz      short loc_1800355E4
0x180035597  mov     rdx, [rcx]
0x18003559a  mov     rax, [rdx+10h]
0x18003559e  lea     rdx, [rbp+57h+hFile]
0x1800355a2  call    _guard_dispatch_icall
0x1800355a7  nop
0x1800355a8  lea     rcx, [rbp+57h+var_78]
0x1800355ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800355b1  nop
0x1800355b2  lea     rcx, [rbp+57h+lpBuffer]
0x1800355b6  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x1800355bb  mov     al, 1
0x1800355bd  mov     rcx, [rbp+57h+var_40]
0x1800355c1  xor     rcx, rsp; StackCookie
0x1800355c4  call    __security_check_cookie
0x1800355c9  mov     rbx, [rsp+0E0h+arg_10]
0x1800355d1  add     rsp, 0B0h
0x1800355d8  pop     r15
0x1800355da  pop     r14
0x1800355dc  pop     r13
0x1800355de  pop     r12
0x1800355e0  pop     rdi
0x1800355e1  pop     rsi
0x1800355e2  pop     rbp
0x1800355e3  retn
0x1800355e4  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800355ea  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x1800355f0  lea     rdx, aInvalidEncodin; "Invalid encoding for UTF-16 line readin"...
0x1800355f7  lea     rcx, [rbp+57h+hFile]; this
0x1800355fb  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180035600  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180035607  lea     rcx, [rbp+57h+hFile]; pExceptionObject
0x18003560b  call    _CxxThrowException
0x180035611  lea     rdx, aInvalidEncodin; "Invalid encoding for UTF-16 line readin"...
0x180035618  lea     rcx, [rbp+57h+hFile]; this
0x18003561c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180035621  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180035628  lea     rcx, [rbp+57h+hFile]; pExceptionObject
0x18003562c  call    _CxxThrowException
0x180035632  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180035638  call    ?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
```

# p9fs::File::SymLink(std::basic_string_view<char,std::char_traits<char>>,std::basic_string_view<char,std::char_traits<char>>,uint)

- ea: `0x1800218b0`
- end: `0x180021d4a`
- name: `?SymLink@File@p9fs@@UEAA?AV?$BasicExpected@UQid@p9fs@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@0I@Z`
- size: `1178`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting`

## callees

- `0x180004120`
- `0x180004c98`
- `0x1800074e0`
- `0x18001c93c`
- `0x18001ca24`
- `0x18001d8b4`
- `0x18001d940`
- `0x18001e428`
- `0x18001e5f0`
- `0x18001ec64`
- `0x18001f194`
- `0x1800218b0`
- `0x18002c9b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021bbb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021c2d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021bad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021c2d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021c21`
- `lxutil!LxUtilFsCreateNtLinkReparseBuffer` at `0x180021a36`
- `lxutil!LxUtilFsCreateNtLinkReparseBuffer` at `0x180021a36`
- `lxutil!LxUtilFsDeleteFile` at `0x180021c07`
- `lxutil!LxUtilFsDeleteFile` at `0x180021c07`
- `lxutil!LxUtilFsCreateLinkReparseBuffer` at `0x180021a6a`
- `lxutil!LxUtilFsCreateLinkReparseBuffer` at `0x180021ba4`
- `lxutil!LxUtilFsCreateLinkReparseBuffer` at `0x180021a6a`
- `lxutil!LxUtilFsCreateLinkReparseBuffer` at `0x180021ba4`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall p9fs::File::SymLink(__int64 a1, __int64 a2, __int128 *a3, __int128 *a4, int a5)
{
  __int64 v8; // rax
  int v10; // eax
  int v11; // eax
  _QWORD *v12; // rcx
  const char *v13; // r9
  int i; // r12d
  _QWORD *v15; // rcx
  __int64 v16; // rax
  const char *v17; // r9
  __int64 v18; // rax
  void *v19; // r15
  void *v20; // rsi
  __int64 v21; // r8
  char v22; // cl
  int v23; // eax
  HANDLE v24; // rax
  HANDLE ProcessHeap; // rax
  void *v26; // r8
  __int64 v27; // rax
  HANDLE v28; // rax
  gsl::details *v29; // rcx
  int v30; // eax
  int v31; // edx
  int v32; // eax
  bool v33; // zf
  __int128 pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+80h] [rbp-80h]
  int v37; // [rsp+84h] [rbp-7Ch]
  __int64 v38; // [rsp+88h] [rbp-78h]
  _WORD v39[8]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h]
  int v42; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v43[8]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v44[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v46; // [rsp+D8h] [rbp-28h]
  __int128 v47; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v48; // [rsp+F0h] [rbp-10h]
  _BYTE v49[8]; // [rsp+F8h] [rbp-8h] BYREF
  _DWORD v50[8]; // [rsp+100h] [rbp+0h] BYREF
  char v51; // [rsp+120h] [rbp+20h] BYREF
  int v52; // [rsp+128h] [rbp+28h]
  __int128 v53; // [rsp+130h] [rbp+30h]
  HANDLE hObject; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v37 = a5;
  v8 = *(_QWORD *)(a1 + 72);
  if ( (*(_BYTE *)(v8 + 40) & 0x10) == 0 )
  {
    *(_DWORD *)(a2 + 8) = -1;
LABEL_3:
    *(_BYTE *)a2 = 0;
    return a2;
  }
  if ( (*(_BYTE *)(v8 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 8) = -30;
    goto LABEL_3;
  }
  if ( *(char *)(v8 + 48) < 0 )
  {
    *(_DWORD *)(a2 + 8) = -13;
    goto LABEL_3;
  }
  pExceptionObject = *a3;
  p9fs::File::ChildPath(a1, v49, &pExceptionObject);
  if ( v49[0] )
  {
    pExceptionObject = *a4;
    p9fs::File::ConvertPath(v43, &pExceptionObject);
    if ( v43[0] )
    {
      v12 = v44;
      if ( v46 > 7 )
        v12 = (_QWORD *)v44[0];
      v40 = v12;
      v41 = v45;
      for ( i = p9fs::File::DetermineSymlinkType(a1, &v40); ; i = 0 )
      {
        v38 = 0;
        v39[0] = 0;
        v36 = 0;
        if ( i )
        {
          if ( !v43[0] )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x139,
              (unsigned int)"onecore\\vm\\inc\\expected.h",
              v13);
          v15 = v44;
          if ( v46 > 7 )
            v15 = (_QWORD *)v44[0];
          if ( (unsigned __int16)(2 * v45) != 2 * v45 )
          {
            pExceptionObject = 0;
            v35 = 0;
            gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
            throw (gsl::narrowing_error *)&pExceptionObject;
          }
          v36 = (i != 1) | 0x10;
          LOWORD(v47) = 2 * v45;
          WORD1(v47) = 2 * v45;
          DWORD1(v47) = 0;
          *((_QWORD *)&v47 + 1) = v15;
          v16 = LxUtilFsCreateNtLinkReparseBuffer(&v47, 0, v39);
        }
        else
        {
          v18 = *((unsigned __int16 *)a4 + 4);
          if ( v18 != *((_QWORD *)a4 + 1) )
          {
            pExceptionObject = 0;
            v35 = 0;
            gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
            throw (gsl::narrowing_error *)&pExceptionObject;
          }
          LOWORD(v40) = *((_WORD *)a4 + 4);
          WORD1(v40) = v18;
          HIDWORD(v40) = 0;
          v41 = *(_QWORD *)a4;
          v16 = LxUtilFsCreateLinkReparseBuffer(&v40, v39, 0);
        }
        v19 = (void *)v16;
        v38 = v16;
        v20 = (void *)v16;
        if ( !v16 )
        {
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 8) = -12;
          goto LABEL_48;
        }
        v42 = 0;
        if ( !v49[0] )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x139,
            (unsigned int)"onecore\\vm\\inc\\expected.h",
            v17);
        *(_QWORD *)&pExceptionObject = v39[0];
        *((_QWORD *)&pExceptionObject + 1) = v16;
        p9fs::File::CreateFile(
          a1,
          (unsigned int)&v51,
          (unsigned int)v50,
          v37,
          41471,
          0,
          65792,
          2,
          v36,
          (__int64)&pExceptionObject,
          (__int64)&v42);
        v22 = v51;
        if ( v51 )
          break;
        v23 = v52;
        if ( v52 != -1 || !i )
        {
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 8) = v23;
          ProcessHeap = GetProcessHeap();
          v26 = v19;
LABEL_32:
          HeapFree(ProcessHeap, 0, v26);
          goto LABEL_48;
        }
        if ( v20 )
        {
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v20);
        }
      }
      if ( (v42 & 2) == 0 )
      {
        v35 = 1;
        *(_QWORD *)&pExceptionObject = a1;
        *((_QWORD *)&pExceptionObject + 1) = &hObject;
        v27 = *((unsigned __int16 *)a4 + 4);
        if ( v27 != *((_QWORD *)a4 + 1) )
        {
          v47 = 0;
          v48 = 0;
          gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&v47);
          throw (gsl::narrowing_error *)&v47;
        }
        LOWORD(v40) = *((_WORD *)a4 + 4);
        WORD1(v40) = v27;
        HIDWORD(v40) = 0;
        v41 = *(_QWORD *)a4;
        v20 = (void *)LxUtilFsCreateLinkReparseBuffer(&v40, v39, v21);
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v19);
        if ( !v20 && v39[0] )
          gsl::details::terminate(v29);
        *(_QWORD *)&pExceptionObject = v39[0];
        *((_QWORD *)&pExceptionObject + 1) = v20;
        v30 = p9fs::util::SetReparsePoint(hObject, &pExceptionObject);
        if ( v30 < 0 )
        {
          v32 = p9fs::util::NtStatusToLinuxError((p9fs::util *)(unsigned int)v30, v31);
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 8) = v32;
          LxUtilFsDeleteFile(hObject, *(_QWORD *)(a1 + 72) + 32LL);
          v33 = v51 == 0;
          goto LABEL_39;
        }
        v22 = v51;
      }
      if ( !v22 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\vm\\inc\\expected.h",
          (const char *)retaddr);
      *(_BYTE *)a2 = 1;
      *(_OWORD *)(a2 + 8) = v53;
      v33 = v22 == 0;
LABEL_39:
      if ( !v33 && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      if ( v20 )
      {
        ProcessHeap = GetProcessHeap();
        v26 = v20;
        goto LABEL_32;
      }
LABEL_48:
      if ( v43[0] )
        std::wstring::~wstring(v44);
    }
    else
    {
      v11 = v44[0];
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = v11;
    }
    if ( v49[0] )
      std::wstring::~wstring(v50);
  }
  else
  {
    v10 = v50[0];
    *(_BYTE *)a2 = 0;
    *(_DWORD *)(a2 + 8) = v10;
  }
  return a2;
}

```

## disassembly

```asm
0x1800218b0  push    rbp
0x1800218b2  push    rbx
0x1800218b3  push    rsi
0x1800218b4  push    rdi
0x1800218b5  push    r12
0x1800218b7  push    r13
0x1800218b9  push    r14
0x1800218bb  push    r15
0x1800218bd  lea     rbp, [rsp-58h]
0x1800218c2  sub     rsp, 158h
0x1800218c9  mov     rax, cs:__security_cookie
0x1800218d0  xor     rax, rsp
0x1800218d3  mov     [rbp+90h+var_48], rax
0x1800218d7  mov     r13, r9
0x1800218da  mov     rdi, rdx
0x1800218dd  mov     r14, rcx
0x1800218e0  mov     eax, [rbp+90h+arg_20]
0x1800218e6  mov     [rbp+90h+var_10C], eax
0x1800218e9  mov     rax, [rcx+48h]
0x1800218ed  test    byte ptr [rax+28h], 10h
0x1800218f1  jnz     short loc_180021921
0x1800218f3  mov     dword ptr [rdx+8], 0FFFFFFFFh
0x1800218fa  xor     ebx, ebx
0x1800218fc  mov     [rdx], bl
0x1800218fe  mov     rax, rdi
0x180021901  mov     rcx, [rbp+90h+var_48]
0x180021905  xor     rcx, rsp; StackCookie
0x180021908  call    __security_check_cookie
0x18002190d  add     rsp, 158h
0x180021914  pop     r15
0x180021916  pop     r14
0x180021918  pop     r13
0x18002191a  pop     r12
0x18002191c  pop     rdi
0x18002191d  pop     rsi
0x18002191e  pop     rbx
0x18002191f  pop     rbp
0x180021920  retn
0x180021921  test    byte ptr [rax+30h], 1
0x180021925  jz      short loc_180021930
0x180021927  mov     dword ptr [rdx+8], 0FFFFFFE2h
0x18002192e  jmp     short loc_1800218FA
0x180021930  test    byte ptr [rax+30h], 80h
0x180021934  jz      short loc_18002193F
0x180021936  mov     dword ptr [rdx+8], 0FFFFFFF3h
0x18002193d  jmp     short loc_1800218FA
0x18002193f  movups  xmm0, xmmword ptr [r8]
0x180021943  movdqu  [rsp+190h+pExceptionObject], xmm0
0x180021949  lea     r8, [rsp+190h+pExceptionObject]
0x18002194e  lea     rdx, [rbp+90h+var_98]
0x180021952  call    ?ChildPath@File@p9fs@@QEAA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::File::ChildPath(std::string_view)
0x180021957  nop
0x180021958  xor     ebx, ebx
0x18002195a  cmp     [rbp+90h+var_98], bl
0x18002195d  jnz     short loc_180021969
0x18002195f  mov     eax, [rbp+90h+var_90]
0x180021962  mov     [rdi], bl
0x180021964  mov     [rdi+8], eax
0x180021967  jmp     short loc_1800218FE
0x180021969  movups  xmm0, xmmword ptr [r13+0]
0x18002196e  movdqu  [rsp+190h+pExceptionObject], xmm0
0x180021974  lea     rdx, [rsp+190h+pExceptionObject]
0x180021979  lea     rcx, [rbp+90h+var_D8]
0x18002197d  call    ?ConvertPath@File@p9fs@@CA?AV?$BasicExpected@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@util@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; p9fs::File::ConvertPath(std::string_view)
0x180021982  nop
0x180021983  cmp     [rbp+90h+var_D8], bl
0x180021986  jnz     short loc_180021995
0x180021988  mov     eax, dword ptr [rbp+90h+var_D0]
0x18002198b  mov     [rdi], bl
0x18002198d  mov     [rdi+8], eax
0x180021990  jmp     loc_180021C7A
0x180021995  lea     rcx, [rbp+90h+var_D0]
0x180021999  cmp     [rbp+90h+var_B8], 7
0x18002199e  cmova   rcx, [rbp+90h+var_D0]
0x1800219a3  mov     rax, [rbp+90h+var_C0]
0x1800219a7  mov     [rbp+90h+var_F0], rcx
0x1800219ab  mov     [rbp+90h+var_E8], rax
0x1800219af  lea     rdx, [rbp+90h+var_F0]
0x1800219b3  mov     rcx, r14
0x1800219b6  call    ?DetermineSymlinkType@File@p9fs@@AEAA?AW4SymlinkType@12@V?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; p9fs::File::DetermineSymlinkType(std::basic_string_view<ushort>)
0x1800219bb  mov     r12d, eax
0x1800219be  mov     [rbp+90h+var_108], rbx
0x1800219c2  mov     [rbp+90h+var_100], bx
0x1800219c6  mov     r8d, ebx
0x1800219c9  mov     [rbp+90h+var_110], ebx
0x1800219cc  test    r12d, r12d
0x1800219cf  jz      short loc_180021A3E
0x1800219d1  cmp     r12d, 1
0x1800219d5  jz      short loc_1800219DD
0x1800219d7  mov     r8d, 1
0x1800219dd  cmp     [rbp+90h+var_D8], bl
0x1800219e0  setz    al
0x1800219e3  mov     rcx, [rbp+98h]; this
0x1800219ea  test    al, al
0x1800219ec  jnz     loc_180021CF9
0x1800219f2  lea     rcx, [rbp+90h+var_D0]
0x1800219f6  cmp     [rbp+90h+var_B8], 7
0x1800219fb  cmova   rcx, [rbp+90h+var_D0]
0x180021a00  mov     rax, [rbp+90h+var_C0]
0x180021a04  add     rax, rax
0x180021a07  movzx   edx, ax
0x180021a0a  cmp     rdx, rax
0x180021a0d  jnz     loc_180021CCE
0x180021a13  or      r8d, 10h
0x180021a17  mov     [rbp+90h+var_110], r8d
0x180021a1b  xor     eax, eax
0x180021a1d  mov     word ptr [rbp+90h+var_B0], dx
0x180021a21  mov     word ptr [rbp+90h+var_B0+2], dx
0x180021a25  mov     dword ptr [rbp+90h+var_B0+4], eax
0x180021a28  mov     qword ptr [rbp+90h+var_B0+8], rcx
0x180021a2c  lea     r8, [rbp+90h+var_100]
0x180021a30  xor     edx, edx
0x180021a32  lea     rcx, [rbp+90h+var_B0]
0x180021a36  call    cs:__imp_LxUtilFsCreateNtLinkReparseBuffer
0x180021a3c  jmp     short loc_180021A70
0x180021a3e  movzx   eax, word ptr [r13+8]
0x180021a43  cmp     rax, [r13+8]
0x180021a47  jnz     loc_180021CA3
0x180021a4d  xor     ecx, ecx
0x180021a4f  mov     word ptr [rbp+90h+var_F0], ax
0x180021a53  mov     word ptr [rbp+90h+var_F0+2], ax
0x180021a57  mov     dword ptr [rbp+90h+var_F0+4], ecx
0x180021a5a  mov     rax, [r13+0]
0x180021a5e  mov     [rbp+90h+var_E8], rax
0x180021a62  lea     rdx, [rbp+90h+var_100]
0x180021a66  lea     rcx, [rbp+90h+var_F0]
0x180021a6a  call    cs:__imp_LxUtilFsCreateLinkReparseBuffer
0x180021a70  mov     r15, rax
0x180021a73  mov     [rbp+90h+var_108], rax
0x180021a77  mov     rsi, rax
0x180021a7a  test    rax, rax
0x180021a7d  jz      loc_180021C62
0x180021a83  mov     [rbp+90h+var_E0], ebx
0x180021a86  cmp     [rbp+90h+var_98], bl
0x180021a89  setz    al
0x180021a8c  mov     rcx, [rbp+98h]; this
0x180021a93  test    al, al
0x180021a95  jnz     loc_180021C91
0x180021a9b  movzx   eax, [rbp+90h+var_100]
0x180021a9f  mov     qword ptr [rsp+190h+pExceptionObject], rax
0x180021aa4  mov     qword ptr [rsp+190h+pExceptionObject+8], rsi
0x180021aa9  lea     rax, [rbp+90h+var_E0]
0x180021aad  mov     [rsp+190h+var_140], rax
0x180021ab2  lea     rax, [rsp+190h+pExceptionObject]
0x180021ab7  mov     [rsp+190h+var_148], rax
0x180021abc  mov     eax, [rbp+90h+var_110]
0x180021abf  mov     [rsp+190h+var_150], eax
0x180021ac3  mov     [rsp+190h+var_158], 2
0x180021acb  mov     [rsp+190h+var_160], 10100h
0x180021ad3  mov     [rsp+190h+var_168], rbx
0x180021ad8  mov     [rsp+190h+var_170], 0A1FFh
0x180021ae0  mov     r9d, [rbp+90h+var_10C]
0x180021ae4  lea     r8, [rbp+90h+var_90]
0x180021ae8  lea     rdx, [rbp+90h+var_70]
0x180021aec  mov     rcx, r14
0x180021aef  call    ?CreateFile@File@p9fs@@AEAA?AV?$BasicExpected@V?$tuple@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@UQid@p9fs@@K@std@@J@util@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KK_KKKW4OpenFileFlags@42@V?$span@W4byte@gsl@@$0?0@gsl@@PEAW4OpenFileOutputFlags@42@@Z; p9fs::File::CreateFile(std::wstring const &,ulong,ulong,unsigned __int64,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)
0x180021af4  nop
0x180021af5  mov     cl, [rbp+90h+var_70]
0x180021af8  test    cl, cl
0x180021afa  jnz     short loc_180021B4C
0x180021afc  mov     eax, [rbp+90h+var_68]
0x180021aff  cmp     eax, 0FFFFFFFFh
0x180021b02  jnz     short loc_180021B2E
0x180021b04  test    r12d, r12d
0x180021b07  jz      short loc_180021B2E
0x180021b09  mov     r12d, ebx
0x180021b0c  test    rsi, rsi
0x180021b0f  jz      loc_1800219BE
0x180021b15  call    cs:__imp_GetProcessHeap
0x180021b1b  mov     rcx, rax; hHeap
0x180021b1e  mov     r8, rsi; lpMem
0x180021b21  xor     edx, edx; dwFlags
0x180021b23  call    cs:__imp_HeapFree
0x180021b29  jmp     loc_1800219BE
0x180021b2e  mov     [rdi], bl
0x180021b30  mov     [rdi+8], eax
0x180021b33  call    cs:__imp_GetProcessHeap
0x180021b39  mov     r8, r15; lpMem
0x180021b3c  mov     rcx, rax; hHeap
0x180021b3f  xor     edx, edx; dwFlags
0x180021b41  call    cs:__imp_HeapFree
0x180021b47  jmp     loc_180021C6B
0x180021b4c  test    byte ptr [rbp+90h+var_E0], 2
0x180021b50  jnz     loc_180021C3E
0x180021b56  xorps   xmm0, xmm0
0x180021b59  xor     eax, eax
0x180021b5b  movups  [rsp+190h+pExceptionObject], xmm0
0x180021b60  mov     [rsp+190h+var_120], rax
0x180021b65  mov     qword ptr [rsp+190h+pExceptionObject], r14
0x180021b6a  lea     rax, [rbp+90h+hObject]
0x180021b6e  mov     qword ptr [rsp+190h+pExceptionObject+8], rax
0x180021b73  mov     byte ptr [rsp+190h+var_120], 1
0x180021b78  movzx   eax, word ptr [r13+8]
0x180021b7d  cmp     rax, [r13+8]
0x180021b81  jnz     loc_180021D26
0x180021b87  xor     ecx, ecx
0x180021b89  mov     word ptr [rbp+90h+var_F0], ax
0x180021b8d  mov     word ptr [rbp+90h+var_F0+2], ax
0x180021b91  mov     dword ptr [rbp+90h+var_F0+4], ecx
0x180021b94  mov     rax, [r13+0]
0x180021b98  mov     [rbp+90h+var_E8], rax
0x180021b9c  lea     rdx, [rbp+90h+var_100]
0x180021ba0  lea     rcx, [rbp+90h+var_F0]
0x180021ba4  call    cs:__imp_LxUtilFsCreateLinkReparseBuffer
0x180021baa  mov     rsi, rax
0x180021bad  call    cs:__imp_GetProcessHeap
0x180021bb3  mov     rcx, rax; hHeap
0x180021bb6  mov     r8, r15; lpMem
0x180021bb9  xor     edx, edx; dwFlags
0x180021bbb  call    cs:__imp_HeapFree
0x180021bc1  movzx   eax, [rbp+90h+var_100]
0x180021bc5  test    rsi, rsi
0x180021bc8  jnz     short loc_180021BD3
0x180021bca  test    rax, rax
0x180021bcd  jnz     loc_180021D0B
0x180021bd3  mov     qword ptr [rsp+190h+pExceptionObject], rax
0x180021bd8  mov     qword ptr [rsp+190h+pExceptionObject+8], rsi
0x180021bdd  lea     rdx, [rsp+190h+pExceptionObject]
0x180021be2  mov     rcx, [rbp+90h+hObject]
0x180021be6  call    ?SetReparsePoint@util@p9fs@@YAJPEAXV?$span@W4byte@gsl@@$0?0@gsl@@@Z; p9fs::util::SetReparsePoint(void *,gsl::span<gsl::byte,-1>)
0x180021beb  test    eax, eax
0x180021bed  jns     short loc_180021C3B
0x180021bef  mov     ecx, eax; this
0x180021bf1  call    ?NtStatusToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::NtStatusToLinuxError(long)
0x180021bf6  mov     [rdi], bl
0x180021bf8  mov     [rdi+8], eax
0x180021bfb  mov     rdx, [r14+48h]
0x180021bff  add     rdx, 20h ; ' '
0x180021c03  mov     rcx, [rbp+90h+hObject]
0x180021c07  call    cs:__imp_LxUtilFsDeleteFile
0x180021c0d  nop
0x180021c0e  cmp     [rbp+90h+var_70], bl
0x180021c11  jz      short loc_180021C28
0x180021c13  mov     rcx, [rbp+90h+hObject]; hObject
0x180021c17  lea     rax, [rcx-1]
0x180021c1b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180021c1f  ja      short loc_180021C28
0x180021c21  call    cs:__imp_CloseHandle
0x180021c27  nop
0x180021c28  test    rsi, rsi
0x180021c2b  jz      short loc_180021C6B
0x180021c2d  call    cs:__imp_GetProcessHeap
0x180021c33  mov     r8, rsi
0x180021c36  jmp     loc_180021B3C
0x180021c3b  mov     cl, [rbp+90h+var_70]
0x180021c3e  test    cl, cl
0x180021c40  setz    al
0x180021c43  mov     r9, [rbp+98h]; char *
0x180021c4a  test    al, al
0x180021c4c  jnz     loc_180021D11
0x180021c52  mov     byte ptr [rdi], 1
0x180021c55  movups  xmm0, [rbp+90h+var_60]
0x180021c59  movdqu  xmmword ptr [rdi+8], xmm0
0x180021c5e  test    cl, cl
0x180021c60  jmp     short loc_180021C11
0x180021c62  mov     [rdi], bl
0x180021c64  mov     dword ptr [rdi+8], 0FFFFFFF4h
0x180021c6b  cmp     [rbp+90h+var_D8], bl
0x180021c6e  jz      short loc_180021C7A
0x180021c70  lea     rcx, [rbp+90h+var_D0]
0x180021c74  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c79  nop
0x180021c7a  cmp     [rbp+90h+var_98], bl
0x180021c7d  jz      loc_1800218FE
0x180021c83  lea     rcx, [rbp+90h+var_90]
0x180021c87  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021c8c  jmp     loc_1800218FE
0x180021c91  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x180021c98  mov     edx, 139h; void *
0x180021c9d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180021ca3  xorps   xmm0, xmm0
0x180021ca6  xor     eax, eax
0x180021ca8  movups  [rsp+190h+pExceptionObject], xmm0
0x180021cad  mov     [rsp+190h+var_120], rax
0x180021cb2  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180021cb7  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x180021cbc  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x180021cc3  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180021cc8  call    _CxxThrowException_0
0x180021cce  xorps   xmm0, xmm0
0x180021cd1  xor     eax, eax
0x180021cd3  movups  [rsp+190h+pExceptionObject], xmm0
0x180021cd8  mov     [rsp+190h+var_120], rax
0x180021cdd  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180021ce2  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x180021ce7  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x180021cee  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180021cf3  call    _CxxThrowException_0
0x180021cf9  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x180021d00  mov     edx, 139h; void *
0x180021d05  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180021d0b  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x180021d11  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x180021d18  mov     edx, 139h; void *
0x180021d1d  mov     rcx, r9; this
0x180021d20  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180021d26  xor     eax, eax
0x180021d28  movups  [rbp+90h+var_B0], xmm0
0x180021d2c  mov     [rbp+90h+var_A0], rax
0x180021d30  lea     rcx, [rbp+90h+var_B0]; this
  ... truncated ...
```

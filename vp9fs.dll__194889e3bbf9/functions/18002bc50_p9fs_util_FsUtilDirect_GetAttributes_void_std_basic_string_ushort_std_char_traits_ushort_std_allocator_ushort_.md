# p9fs::util::FsUtilDirect::GetAttributes(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,void *,p9fs::util::GetAttributeFlags)

- ea: `0x18002bc50`
- end: `0x18002bf0c`
- name: `?GetAttributes@FsUtilDirect@util@p9fs@@UEAA?AV?$BasicExpected@U_FILE_STAT_LX_INFORMATION@@J@2@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4GetAttributeFlags@23@@Z`
- size: `700`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x180004120`
- `0x180004c80`
- `0x180004c98`
- `0x18001d8b4`
- `0x18002bc50`
- `0x18002c040`
- `0x18002c130`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bdeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002beba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bdeb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002beba`
- `lxutil!LxUtilFsReadLinkLength` at `0x18002bdd1`
- `lxutil!LxUtilFsReadLinkLength` at `0x18002bdd1`
- `lxutil!LxUtilFsQueryStatLxInformationByName` at `0x18002bd0f`
- `lxutil!LxUtilFsQueryStatLxInformationByName` at `0x18002bd0f`

## pseudocode

```c
__int64 __fastcall p9fs::util::FsUtilDirect::GetAttributes(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        void **a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  __int64 v11; // rdi
  void *v12; // rcx
  unsigned __int16 v13; // dx
  int StatLxInformationByName; // eax
  int v15; // ecx
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  unsigned __int128 pExceptionObject; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h]
  struct _IO_STATUS_BLOCK v24; // [rsp+70h] [rbp-90h] BYREF
  _WORD v25[2]; // [rsp+80h] [rbp-80h] BYREF
  int v26; // [rsp+84h] [rbp-7Ch]
  HANDLE v27; // [rsp+88h] [rbp-78h]
  _BYTE v28[8]; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  _OWORD v30[3]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v31[3]; // [rsp+D0h] [rbp-30h] BYREF

  if ( (unsigned __int64)(a6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    p9fs::util::GetAttributesByHandle(a2, *(_QWORD *)(a1 + 8), a6, a5, a7);
    return a2;
  }
  v11 = *(_QWORD *)(a1 + 8);
  if ( (*(_BYTE *)(v11 + 8) & 1) != 0 )
  {
    if ( (unsigned __int64)a4[3] <= 7 )
      v12 = a4;
    else
      v12 = *a4;
    v13 = 2 * *((_WORD *)a4 + 8);
    if ( v13 != 2LL * (_QWORD)a4[2] )
    {
      pExceptionObject = 0;
      v23 = 0;
      gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
      throw (gsl::narrowing_error *)&pExceptionObject;
    }
    v25[0] = 2 * *((_WORD *)a4 + 8);
    v25[1] = v13;
    v27 = v12;
    v26 = 0;
    memset_0(v30, 0, 0x60u);
    StatLxInformationByName = LxUtilFsQueryStatLxInformationByName(v11, a3, v25, v30);
    if ( StatLxInformationByName < 0 )
      goto LABEL_9;
    if ( (a7 & 1) == 0 && (WORD4(v31[0]) & 0x400) != 0 && (unsigned int)(HIDWORD(v31[0]) + 1610612733) <= 0x1A )
    {
      v15 = 67109377;
      if ( _bittest(&v15, HIDWORD(v31[0]) + 1610612733) )
      {
        if ( !*(_QWORD *)&v31[0] )
        {
          v24.Pointer = 0;
          v24.Information = 0;
          pExceptionObject = 0u;
          p9fs::util::FsUtilDirect::OpenFile(
            a1,
            (__int64)v28,
            a3,
            a4,
            128,
            1u,
            0,
            (struct _IO_STATUS_BLOCK *)&pExceptionObject,
            &v24,
            0);
          if ( v28[0] )
          {
            LxUtilFsReadLinkLength(*(_QWORD *)(a1 + 8), hObject, a5, v31);
            if ( v28[0] )
            {
              if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hObject);
            }
          }
        }
      }
    }
    v16 = v30[1];
    *(_OWORD *)(a2 + 8) = v30[0];
    *(_BYTE *)a2 = 1;
    v17 = v30[2];
    *(_OWORD *)(a2 + 24) = v16;
    v18 = v31[0];
    *(_OWORD *)(a2 + 40) = v17;
    v19 = v31[1];
    *(_OWORD *)(a2 + 56) = v18;
    v20 = v31[2];
    *(_OWORD *)(a2 + 72) = v19;
    *(_OWORD *)(a2 + 88) = v20;
  }
  else
  {
    pExceptionObject = 0u;
    v24.Pointer = 0;
    v24.Information = 0;
    p9fs::util::FsUtilDirect::OpenFile(
      a1,
      (__int64)v25,
      a3,
      a4,
      131208,
      1u,
      0,
      &v24,
      (struct _IO_STATUS_BLOCK *)&pExceptionObject,
      0);
    if ( !LOBYTE(v25[0]) )
    {
      StatLxInformationByName = (int)v27;
LABEL_9:
      *(_BYTE *)a2 = 0;
      *(_DWORD *)(a2 + 8) = StatLxInformationByName;
      return a2;
    }
    p9fs::util::GetAttributesByHandle(a2, *(_QWORD *)(a1 + 8), (_DWORD)v27, a5, a7);
    if ( LOBYTE(v25[0]) && (char *)v27 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(v27);
  }
  return a2;
}

```

## disassembly

```asm
0x18002bc50  push    rbp
0x18002bc52  push    rbx
0x18002bc53  push    rsi
0x18002bc54  push    rdi
0x18002bc55  push    r12
0x18002bc57  push    r14
0x18002bc59  push    r15
0x18002bc5b  lea     rbp, [rsp-10h]
0x18002bc60  sub     rsp, 110h
0x18002bc67  mov     rax, cs:__security_cookie
0x18002bc6e  xor     rax, rsp
0x18002bc71  mov     [rbp+40h+var_40], rax
0x18002bc75  mov     r15, [rbp+40h+arg_20]
0x18002bc79  mov     r12, r8
0x18002bc7c  mov     r8, [rbp+40h+arg_28]
0x18002bc80  mov     rsi, rcx
0x18002bc83  mov     r14, r9
0x18002bc86  mov     rbx, rdx
0x18002bc89  lea     rcx, [r8-1]
0x18002bc8d  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002bc91  ja      short loc_18002BCB1
0x18002bc93  mov     ecx, [rbp+40h+arg_30]
0x18002bc99  mov     r9, r15
0x18002bc9c  mov     rdx, [rsi+8]
0x18002bca0  mov     [rsp+140h+var_120], ecx
0x18002bca4  mov     rcx, rbx
0x18002bca7  call    ?GetAttributesByHandle@util@p9fs@@YA?AV?$BasicExpected@U_FILE_STAT_LX_INFORMATION@@J@1@AEBU_LX_UTIL_FS_CONTEXT@@PEAX1W4GetAttributeFlags@12@@Z; p9fs::util::GetAttributesByHandle(_LX_UTIL_FS_CONTEXT const &,void *,void *,p9fs::util::GetAttributeFlags)
0x18002bcac  jmp     loc_18002BEC0
0x18002bcb1  mov     rdi, [rsi+8]
0x18002bcb5  test    byte ptr [rdi+8], 1
0x18002bcb9  jz      loc_18002BE29
0x18002bcbf  cmp     qword ptr [r9+18h], 7
0x18002bcc4  jbe     short loc_18002BCCB
0x18002bcc6  mov     rcx, [r9]
0x18002bcc9  jmp     short loc_18002BCCE
0x18002bccb  mov     rcx, r14
0x18002bcce  mov     rax, [r9+10h]
0x18002bcd2  add     rax, rax
0x18002bcd5  movzx   edx, ax
0x18002bcd8  cmp     rdx, rax
0x18002bcdb  jnz     loc_18002BEE1
0x18002bce1  xor     eax, eax
0x18002bce3  mov     [rbp+40h+var_C0], dx
0x18002bce7  mov     [rbp+40h+var_BE], dx
0x18002bceb  xor     edx, edx; Val
0x18002bced  mov     [rbp+40h+var_B8], rcx
0x18002bcf1  lea     rcx, [rbp+40h+var_A0]; void *
0x18002bcf5  mov     [rbp+40h+var_BC], eax
0x18002bcf8  lea     r8d, [rax+60h]; Size
0x18002bcfc  call    memset_0
0x18002bd01  lea     r9, [rbp+40h+var_A0]
0x18002bd05  mov     rdx, r12
0x18002bd08  lea     r8, [rbp+40h+var_C0]
0x18002bd0c  mov     rcx, rdi
0x18002bd0f  call    cs:__imp_LxUtilFsQueryStatLxInformationByName
0x18002bd15  xor     edi, edi
0x18002bd17  test    eax, eax
0x18002bd19  jns     short loc_18002BD26
0x18002bd1b  mov     [rbx], dil
0x18002bd1e  mov     [rbx+8], eax
0x18002bd21  jmp     loc_18002BEC0
0x18002bd26  test    byte ptr [rbp+40h+arg_30], 1
0x18002bd2d  jnz     loc_18002BDF1
0x18002bd33  test    dword ptr [rbp+40h+var_70+8], 400h
0x18002bd3a  jz      loc_18002BDF1
0x18002bd40  mov     eax, dword ptr [rbp+40h+var_70+0Ch]
0x18002bd43  add     eax, 5FFFFFFDh
0x18002bd48  cmp     eax, 1Ah
0x18002bd4b  ja      loc_18002BDF1
0x18002bd51  mov     ecx, 4000201h
0x18002bd56  bt      ecx, eax
0x18002bd59  jnb     loc_18002BDF1
0x18002bd5f  cmp     qword ptr [rbp+40h+var_70], rdi
0x18002bd63  jnz     loc_18002BDF1
0x18002bd69  mov     [rsp+140h+var_F8], rdi
0x18002bd6e  lea     rax, [rsp+140h+var_D0]
0x18002bd73  mov     [rsp+140h+var_100], rax
0x18002bd78  lea     rdx, [rbp+40h+var_B0]
0x18002bd7c  lea     rax, [rsp+140h+pExceptionObject]
0x18002bd81  mov     [rsp+140h+var_D0], rdi
0x18002bd86  mov     [rsp+140h+var_108], rax
0x18002bd8b  mov     r9, r14
0x18002bd8e  mov     [rsp+140h+var_110], edi
0x18002bd92  mov     r8, r12
0x18002bd95  mov     [rsp+140h+var_118], 1
0x18002bd9d  mov     rcx, rsi
0x18002bda0  mov     [rsp+140h+var_120], 80h
0x18002bda8  mov     [rsp+140h+var_C8], rdi
0x18002bdad  mov     qword ptr [rsp+140h+pExceptionObject], rdi
0x18002bdb2  mov     qword ptr [rsp+140h+pExceptionObject+8], rdi
0x18002bdb7  call    ?OpenFile@FsUtilDirect@util@p9fs@@UEAA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@2@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKW4OpenFileFlags@23@V?$span@W4byte@gsl@@$0?0@gsl@@3PEAW4OpenFileOutputFlags@23@@Z; p9fs::util::FsUtilDirect::OpenFile(void *,std::wstring const &,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)
0x18002bdbc  cmp     [rbp+40h+var_B0], dil
0x18002bdc0  jz      short loc_18002BDF1
0x18002bdc2  mov     rdx, [rbp+40h+hObject]
0x18002bdc6  lea     r9, [rbp+40h+var_70]
0x18002bdca  mov     rcx, [rsi+8]
0x18002bdce  mov     r8, r15
0x18002bdd1  call    cs:__imp_LxUtilFsReadLinkLength
0x18002bdd7  cmp     [rbp+40h+var_B0], dil
0x18002bddb  jz      short loc_18002BDF1
0x18002bddd  mov     rcx, [rbp+40h+hObject]; hObject
0x18002bde1  lea     rax, [rcx-1]
0x18002bde5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bde9  ja      short loc_18002BDF1
0x18002bdeb  call    cs:__imp_CloseHandle
0x18002bdf1  movaps  xmm0, [rbp+40h+var_A0]
0x18002bdf5  movaps  xmm1, [rbp+40h+var_90]
0x18002bdf9  movups  xmmword ptr [rbx+8], xmm0
0x18002bdfd  mov     byte ptr [rbx], 1
0x18002be00  movaps  xmm0, [rbp+40h+var_80]
0x18002be04  movups  xmmword ptr [rbx+18h], xmm1
0x18002be08  movaps  xmm1, [rbp+40h+var_70]
0x18002be0c  movups  xmmword ptr [rbx+28h], xmm0
0x18002be10  movaps  xmm0, [rbp+40h+var_60]
0x18002be14  movups  xmmword ptr [rbx+38h], xmm1
0x18002be18  movaps  xmm1, [rbp+40h+var_50]
0x18002be1c  movups  xmmword ptr [rbx+48h], xmm0
0x18002be20  movups  xmmword ptr [rbx+58h], xmm1
0x18002be24  jmp     loc_18002BEC0
0x18002be29  xor     edi, edi
0x18002be2b  lea     rax, [rsp+140h+pExceptionObject]
0x18002be30  mov     [rsp+140h+var_F8], rdi
0x18002be35  lea     rdx, [rbp+40h+var_C0]
0x18002be39  mov     [rsp+140h+var_100], rax
0x18002be3e  mov     r8, r12
0x18002be41  lea     rax, [rsp+140h+var_D0]
0x18002be46  mov     qword ptr [rsp+140h+pExceptionObject], rdi
0x18002be4b  mov     [rsp+140h+var_108], rax
0x18002be50  mov     rcx, rsi
0x18002be53  mov     [rsp+140h+var_110], edi
0x18002be57  mov     [rsp+140h+var_118], 1
0x18002be5f  mov     [rsp+140h+var_120], 20088h
0x18002be67  mov     qword ptr [rsp+140h+pExceptionObject+8], rdi
0x18002be6c  mov     [rsp+140h+var_D0], rdi
0x18002be71  mov     [rsp+140h+var_C8], rdi
0x18002be76  call    ?OpenFile@FsUtilDirect@util@p9fs@@UEAA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@2@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKW4OpenFileFlags@23@V?$span@W4byte@gsl@@$0?0@gsl@@3PEAW4OpenFileOutputFlags@23@@Z; p9fs::util::FsUtilDirect::OpenFile(void *,std::wstring const &,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)
0x18002be7b  cmp     byte ptr [rbp+40h+var_C0], dil
0x18002be7f  jnz     short loc_18002BE89
0x18002be81  mov     eax, dword ptr [rbp+40h+var_B8]
0x18002be84  jmp     loc_18002BD1B
0x18002be89  mov     eax, [rbp+40h+arg_30]
0x18002be8f  mov     r9, r15
0x18002be92  mov     r8, [rbp+40h+var_B8]
0x18002be96  mov     rcx, rbx
0x18002be99  mov     rdx, [rsi+8]
0x18002be9d  mov     [rsp+140h+var_120], eax
0x18002bea1  call    ?GetAttributesByHandle@util@p9fs@@YA?AV?$BasicExpected@U_FILE_STAT_LX_INFORMATION@@J@1@AEBU_LX_UTIL_FS_CONTEXT@@PEAX1W4GetAttributeFlags@12@@Z; p9fs::util::GetAttributesByHandle(_LX_UTIL_FS_CONTEXT const &,void *,void *,p9fs::util::GetAttributeFlags)
0x18002bea6  cmp     byte ptr [rbp+40h+var_C0], dil
0x18002beaa  jz      short loc_18002BEC0
0x18002beac  mov     rcx, [rbp+40h+var_B8]; hObject
0x18002beb0  lea     rax, [rcx-1]
0x18002beb4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002beb8  ja      short loc_18002BEC0
0x18002beba  call    cs:__imp_CloseHandle
0x18002bec0  mov     rax, rbx
0x18002bec3  mov     rcx, [rbp+40h+var_40]
0x18002bec7  xor     rcx, rsp; StackCookie
0x18002beca  call    __security_check_cookie
0x18002becf  add     rsp, 110h
0x18002bed6  pop     r15
0x18002bed8  pop     r14
0x18002beda  pop     r12
0x18002bedc  pop     rdi
0x18002bedd  pop     rsi
0x18002bede  pop     rbx
0x18002bedf  pop     rbp
0x18002bee0  retn
0x18002bee1  xorps   xmm0, xmm0
0x18002bee4  lea     rcx, [rsp+140h+pExceptionObject]; this
0x18002bee9  xor     eax, eax
0x18002beeb  movups  [rsp+140h+pExceptionObject], xmm0
0x18002bef0  mov     [rsp+140h+var_E0], rax
0x18002bef5  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18002befa  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18002bf01  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x18002bf06  call    _CxxThrowException_0
```

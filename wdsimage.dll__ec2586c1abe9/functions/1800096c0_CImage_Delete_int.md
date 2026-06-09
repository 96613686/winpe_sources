# CImage::Delete(int)

- ea: `0x1800096c0`
- end: `0x180009c27`
- name: `?Delete@CImage@@QEAAJH@Z`
- size: `1383`
- prototype: `__int64 __fastcall(CImage *__hidden this, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800042d0`
- `0x180005ad0`

## callees

- `0x1800073c0`
- `0x180007cac`
- `0x180007fd4`
- `0x1800081b8`
- `0x1800092a4`
- `0x1800096c0`
- `0x18000a688`
- `0x18000d5b0`
- `0x18000d6b0`
- `0x18000e39c`
- `0x18000e5f0`
- `0x18000e688`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009bd9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bf2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bd9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009bf2`
- `KERNEL32!DeleteFileW` at `0x180009b1d`
- `KERNEL32!DeleteFileW` at `0x180009b1d`
- `KERNEL32!GetFileAttributesW` at `0x180009739`
- `KERNEL32!GetFileAttributesW` at `0x180009739`
- `KERNEL32!GetLastError` at `0x180009aa2`
- `KERNEL32!GetLastError` at `0x180009b2d`
- `KERNEL32!GetLastError` at `0x180009aa2`
- `KERNEL32!GetLastError` at `0x180009b2d`
- `WIMGAPI!WIMDeleteImage` at `0x180009a92`
- `WIMGAPI!WIMDeleteImage` at `0x180009a92`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x1800097e2`
- `WdsCommonLib!WdsGetParentFolderPathOfFile` at `0x1800097e2`
- `WdsCommonLib!WdsDeleteDirectory` at `0x180009b67`
- `WdsCommonLib!WdsDeleteDirectory` at `0x180009b67`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x1800098a9`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000990b`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x1800098a9`
- `WdsCommonLib!WdsIdnCompareFilePaths` at `0x18000990b`

## pseudocode

```c
__int64 __fastcall CImage::Delete(CImage *this, int a2)
{
  const WCHAR *v3; // rcx
  void (__fastcall ***v4)(_QWORD); // rsi
  __int64 v5; // rdx
  __int64 First; // rbx
  unsigned int v7; // r14d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r14
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // r15d
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  DWORD LastError; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  int v37; // r15d
  unsigned int v38; // r12d
  DWORD v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // edi
  int v46; // ebx
  LPCWSTR *v48; // [rsp+40h] [rbp-79h] BYREF
  __int64 v49; // [rsp+48h] [rbp-71h]
  _QWORD v50[2]; // [rsp+58h] [rbp-61h] BYREF
  int v51; // [rsp+68h] [rbp-51h]
  __int64 v52; // [rsp+70h] [rbp-49h]
  void **v53; // [rsp+80h] [rbp-39h] BYREF
  int v54; // [rsp+88h] [rbp-31h]
  int v55; // [rsp+90h] [rbp-29h]
  __int64 v56; // [rsp+98h] [rbp-21h]
  __int64 v57; // [rsp+A0h] [rbp-19h]
  int v58; // [rsp+B0h] [rbp-9h]
  __int64 v59; // [rsp+B8h] [rbp-1h]
  void (__fastcall ***v60)(_QWORD); // [rsp+C0h] [rbp+7h]
  int v61; // [rsp+120h] [rbp+67h] BYREF
  int v62; // [rsp+128h] [rbp+6Fh]
  unsigned int v63; // [rsp+130h] [rbp+77h] BYREF
  LPCWSTR lpFileName; // [rsp+138h] [rbp+7Fh] BYREF

  v62 = a2;
  v54 = 1;
  lpFileName = 0;
  v3 = (const WCHAR *)*((_QWORD *)this + 11);
  v63 = 0;
  v4 = 0;
  v52 = 0;
  v50[0] = 0;
  v50[1] = 0;
  v51 = 0;
  v53 = &CEnumImages::`vftable';
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v48 = 0;
  v49 = 0;
  v55 = 6;
  if ( GetFileAttributesW(v3) == -1 )
  {
    LODWORD(First) = -2147024894;
    if ( (int)ElValidateHr_5(2147942402LL, v5, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1601) < 0 )
      goto LABEL_61;
  }
  v7 = 0;
  if ( *((_DWORD *)this + 91) )
  {
    while ( 1 )
    {
      First = (unsigned int)CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(
                              &v48,
                              *(_QWORD *)(*((_QWORD *)this + 46) + 8LL * v7));
      if ( (unsigned int)ElValidateWin32_4(First, v8, v9, 1610) )
        break;
      if ( ++v7 >= *((_DWORD *)this + 91) )
        goto LABEL_6;
    }
  }
  else
  {
LABEL_6:
    v10 = *((_QWORD *)this + 14);
    if ( !v10
      || (First = (unsigned int)CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(&v48, v10),
          !(unsigned int)ElValidateWin32_4(First, v11, v12, 1619)) )
    {
      LODWORD(First) = WdsGetParentFolderPathOfFile(*((_QWORD *)this + 11), &lpFileName);
      if ( !(unsigned int)ElValidateWin32_4((unsigned int)First, v13, v14, 1633) )
      {
        First = (unsigned int)CEnumImages::FindFirst((CEnumImages *)&v53, lpFileName, 0);
        if ( (int)ElValidateHr_5(First, v15, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1639) < 0 )
          goto LABEL_61;
        do
        {
          v61 = 0;
          if ( v4 )
          {
            (*v4)[1](v4);
            v4 = 0;
          }
          LODWORD(First) = 0;
          if ( v60 )
          {
            v4 = v60;
            (**v60)(v60);
          }
          else
          {
            LODWORD(First) = -1056833013;
          }
          if ( (int)ElValidateHr_5((unsigned int)First, v16, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1647) < 0 )
            goto LABEL_59;
          v17 = (unsigned int)WdsIdnCompareFilePaths(*((_QWORD *)this + 11), v4[11], &v61);
          if ( (unsigned int)ElValidateWin32_4(v17, v18, v19, 1653) )
            goto LABEL_54;
          if ( v61 || *((_DWORD *)this + 33) != *((_DWORD *)v4 + 33) )
          {
            v20 = 0;
            if ( *((_DWORD *)v4 + 91) )
            {
              do
              {
                v17 = (unsigned int)WdsIdnCompareFilePaths(*((_QWORD *)this + 11), v4[46][v20], &v61);
                if ( (unsigned int)ElValidateWin32_4(v17, v21, v22, 1668) )
                  goto LABEL_54;
                if ( !v61 )
                {
                  LODWORD(First) = -1056833001;
                  if ( (int)ElValidateHr_5(3238134295LL, v23, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 1676) < 0 )
                    goto LABEL_59;
                }
                if ( (unsigned int)CDynArray<unsigned short *,CDeallocateNone>::FindString(&v48, v4[46][v20], &v63) )
                  CDynArray<unsigned short *,CDeallocateNone>::ClearItem(&v48, v63);
              }
              while ( (unsigned int)++v20 < *((_DWORD *)v4 + 91) );
            }
          }
        }
        while ( !(unsigned int)CEnumImages::FindNext((CEnumImages *)&v53) );
        v24 = *((_QWORD *)this + 49);
        if ( v24 )
        {
          v25 = v24 + 8 + *(int *)(*(_QWORD *)(v24 + 8) + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          *((_QWORD *)this + 49) = 0;
        }
        v26 = *((_QWORD *)this + 48);
        if ( v26 )
        {
          v27 = v26 + 8 + *(int *)(*(_QWORD *)(v26 + 8) + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          *((_QWORD *)this + 48) = 0;
        }
        v28 = *((_QWORD *)this + 47);
        if ( v28 )
        {
          v29 = v28 + 8 + *(int *)(*(_QWORD *)(v28 + 8) + 4LL);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          *((_QWORD *)this + 47) = 0;
        }
        if ( *((_DWORD *)this + 7) == 2 && *((_DWORD *)this + 32) > 1u )
        {
          v17 = CWIMFile::Create((CWIMFile *)v50, *((const unsigned __int16 **)this + 11), 0x40000000u, 3u, 0, 0, 0);
          if ( !(unsigned int)ElValidateWin32_4(v17, v30, v31, 1709) )
          {
            LODWORD(v17) = 0;
            if ( !(unsigned int)WIMDeleteImage(v50[0], *((unsigned int *)this + 33)) )
            {
              LastError = GetLastError();
              LODWORD(v17) = ElValidateWin32_5(LastError, v35, v36, 379);
            }
            if ( !(unsigned int)ElValidateWin32_4((unsigned int)v17, v32, v33, 1712) )
            {
              CWIMFile::Shutdown((CWIMFile *)v50);
              if ( (unsigned int)CDynArray<unsigned short *,CDeallocateNone>::FindString(
                                   &v48,
                                   *((_QWORD *)this + 11),
                                   &v63) )
                CDynArray<unsigned short *,CDeallocateNone>::ClearItem(&v48, v63);
              goto LABEL_43;
            }
          }
LABEL_54:
          if ( (int)v17 <= 0 )
          {
            LODWORD(First) = v17;
            goto LABEL_59;
          }
          v46 = (unsigned __int16)v17;
        }
        else
        {
LABEL_43:
          v37 = 0;
          v38 = HIDWORD(v49);
          if ( HIDWORD(v49) )
          {
            do
            {
              if ( !DeleteFileW(v48[v37]) )
              {
                v39 = GetLastError();
                LODWORD(v17) = v39;
                if ( v39 != 2 )
                {
                  if ( (unsigned int)ElValidateWin32_4(v39, v40, v41, 1740) )
                    goto LABEL_54;
                }
              }
            }
            while ( ++v37 < v38 );
          }
          if ( !v62
            || (v42 = WdsDeleteDirectory(*((_QWORD *)this + 12)), v45 = v42, v42 - 2 <= 1)
            || v42 == 123
            || !(unsigned int)ElValidateWin32_4(v42, v43, v44, 1755) )
          {
LABEL_59:
            if ( v4 )
              (*v4)[1](v4);
            goto LABEL_61;
          }
          if ( v45 <= 0 )
          {
            LODWORD(First) = v45;
            goto LABEL_59;
          }
          v46 = (unsigned __int16)v45;
        }
        LODWORD(First) = v46 | 0x80070000;
        goto LABEL_59;
      }
    }
  }
  if ( (int)First > 0 )
    LODWORD(First) = (unsigned __int16)First | 0x80070000;
LABEL_61:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v48 )
    operator delete(v48);
  CEnumImages::~CEnumImages((CEnumImages *)&v53);
  CWIMFile::Shutdown((CWIMFile *)v50);
  return (unsigned int)First;
}

```

## disassembly

```asm
0x1800096c0  mov     [rsp-8+arg_8], edx
0x1800096c4  push    rbp
0x1800096c5  push    rbx
0x1800096c6  push    rsi
0x1800096c7  push    rdi
0x1800096c8  push    r12
0x1800096ca  push    r13
0x1800096cc  push    r14
0x1800096ce  push    r15
0x1800096d0  lea     rbp, [rsp-1Fh]
0x1800096d5  sub     rsp, 0D8h
0x1800096dc  xor     r12d, r12d
0x1800096df  mov     [rbp+57h+var_88], 1
0x1800096e6  mov     rdi, rcx
0x1800096e9  mov     [rbp+57h+lpFileName], r12
0x1800096ed  mov     rcx, [rcx+58h]; lpFileName
0x1800096f1  lea     rax, ??_7CEnumImages@@6B@; const CEnumImages::`vftable'
0x1800096f8  mov     r13d, r12d
0x1800096fb  mov     [rbp+57h+arg_10], r12d
0x1800096ff  mov     esi, r12d
0x180009702  mov     [rbp+57h+var_A0], r12
0x180009706  mov     [rbp+57h+var_B8], r12
0x18000970a  mov     [rbp+57h+var_B0], r12
0x18000970e  mov     [rbp+57h+var_A8], r12d
0x180009712  mov     [rbp+57h+var_90], rax
0x180009716  mov     [rbp+57h+var_78], r12
0x18000971a  mov     [rbp+57h+var_70], r12
0x18000971e  mov     [rbp+57h+var_60], r12d
0x180009722  mov     [rbp+57h+var_58], r12
0x180009726  mov     [rbp+57h+var_50], r12
0x18000972a  mov     [rbp+57h+var_D0], r12
0x18000972e  mov     [rbp+57h+var_C8], r12
0x180009732  mov     [rbp+57h+var_80], 6
0x180009739  call    cs:__imp_GetFileAttributesW
0x180009740  nop     dword ptr [rax+rax+00h]
0x180009745  cmp     eax, 0FFFFFFFFh
0x180009748  jnz     short loc_18000976B
0x18000974a  mov     ebx, 80070002h
0x18000974f  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009756  mov     ecx, ebx
0x180009758  mov     r9d, 641h
0x18000975e  call    ElValidateHr_5
0x180009763  test    eax, eax
0x180009765  js      loc_180009BD0
0x18000976b  mov     r14d, r12d
0x18000976e  cmp     [rdi+16Ch], r12d
0x180009775  jbe     short loc_1800097B1
0x180009777  mov     rdx, [rdi+170h]
0x18000977e  lea     rcx, [rbp+57h+var_D0]
0x180009782  mov     eax, r14d
0x180009785  mov     rdx, [rdx+rax*8]
0x180009789  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x18000978e  mov     r9d, 64Ah
0x180009794  mov     ecx, eax
0x180009796  mov     ebx, eax
0x180009798  call    ElValidateWin32_4
0x18000979d  test    eax, eax
0x18000979f  jnz     loc_18000985D
0x1800097a5  inc     r14d
0x1800097a8  cmp     r14d, [rdi+16Ch]
0x1800097af  jb      short loc_180009777
0x1800097b1  mov     rdx, [rdi+70h]
0x1800097b5  test    rdx, rdx
0x1800097b8  jz      short loc_1800097DA
0x1800097ba  lea     rcx, [rbp+57h+var_D0]
0x1800097be  call    ?AddItem@?$CDynArray@PEAUWdsImgParentImage@@VCDeallocatePointer@@@@QEAAKPEAUWdsImgParentImage@@@Z; CDynArray<WdsImgParentImage *,CDeallocatePointer>::AddItem(WdsImgParentImage *)
0x1800097c3  mov     r9d, 653h
0x1800097c9  mov     ecx, eax
0x1800097cb  mov     ebx, eax
0x1800097cd  call    ElValidateWin32_4
0x1800097d2  test    eax, eax
0x1800097d4  jnz     loc_18000985D
0x1800097da  mov     rcx, [rdi+58h]
0x1800097de  lea     rdx, [rbp+57h+lpFileName]
0x1800097e2  call    cs:__imp_WdsGetParentFolderPathOfFile
0x1800097e9  nop     dword ptr [rax+rax+00h]
0x1800097ee  mov     ecx, eax
0x1800097f0  mov     r9d, 661h
0x1800097f6  mov     ebx, eax
0x1800097f8  call    ElValidateWin32_4
0x1800097fd  test    eax, eax
0x1800097ff  jnz     short loc_18000985D
0x180009801  mov     rdx, [rbp+57h+lpFileName]; lpFileName
0x180009805  lea     rcx, [rbp+57h+var_90]; this
0x180009809  xor     r8d, r8d; unsigned int
0x18000980c  call    ?FindFirst@CEnumImages@@QEAAJPEBGK@Z; CEnumImages::FindFirst(ushort const *,ulong)
0x180009811  mov     r9d, 667h
0x180009817  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000981e  mov     ecx, eax
0x180009820  mov     ebx, eax
0x180009822  call    ElValidateHr_5
0x180009827  test    eax, eax
0x180009829  js      loc_180009BD0
0x18000982f  mov     [rbp+57h+arg_0], r12d
0x180009833  test    rsi, rsi
0x180009836  jz      short loc_18000984A
0x180009838  mov     rax, [rsi]
0x18000983b  mov     rcx, rsi
0x18000983e  mov     rax, [rax+8]
0x180009842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009847  mov     rsi, r12
0x18000984a  mov     rcx, [rbp+57h+var_50]
0x18000984e  mov     ebx, r12d
0x180009851  test    rcx, rcx
0x180009854  jnz     short loc_180009873
0x180009856  mov     ebx, 0C102020Bh
0x18000985b  jmp     short loc_180009881
0x18000985d  test    ebx, ebx
0x18000985f  jle     loc_180009BD0
0x180009865  movzx   ebx, bx
0x180009868  or      ebx, 80070000h
0x18000986e  jmp     loc_180009BD0
0x180009873  mov     rax, [rcx]
0x180009876  mov     rsi, rcx
0x180009879  mov     rax, [rax]
0x18000987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009881  mov     r9d, 66Fh
0x180009887  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000988e  mov     ecx, ebx
0x180009890  call    ElValidateHr_5
0x180009895  test    eax, eax
0x180009897  js      loc_180009BBC
0x18000989d  mov     rdx, [rsi+58h]
0x1800098a1  lea     r8, [rbp+57h+arg_0]
0x1800098a5  mov     rcx, [rdi+58h]
0x1800098a9  call    cs:__imp_WdsIdnCompareFilePaths
0x1800098b0  nop     dword ptr [rax+rax+00h]
0x1800098b5  mov     ecx, eax
0x1800098b7  mov     r9d, 675h
0x1800098bd  mov     r14d, eax
0x1800098c0  call    ElValidateWin32_4
0x1800098c5  test    eax, eax
0x1800098c7  jnz     loc_180009B9E
0x1800098cd  cmp     [rbp+57h+arg_0], r12d
0x1800098d1  jnz     short loc_1800098E5
0x1800098d3  mov     eax, [rsi+84h]
0x1800098d9  cmp     [rdi+84h], eax
0x1800098df  jz      loc_180009993
0x1800098e5  mov     r15d, r12d
0x1800098e8  cmp     [rsi+16Ch], r12d
0x1800098ef  jbe     loc_180009993
0x1800098f5  mov     rdx, [rsi+170h]
0x1800098fc  lea     r8, [rbp+57h+arg_0]
0x180009900  mov     rcx, [rdi+58h]
0x180009904  mov     r12d, r15d
0x180009907  mov     rdx, [rdx+r12*8]
0x18000990b  call    cs:__imp_WdsIdnCompareFilePaths
0x180009912  nop     dword ptr [rax+rax+00h]
0x180009917  mov     ecx, eax
0x180009919  mov     r9d, 684h
0x18000991f  mov     r14d, eax
0x180009922  call    ElValidateWin32_4
0x180009927  test    eax, eax
0x180009929  jnz     loc_180009B9B
0x18000992f  cmp     [rbp+57h+arg_0], r13d
0x180009933  jnz     short loc_180009958
0x180009935  mov     eax, 0C1020217h
0x18000993a  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x180009941  mov     ecx, eax
0x180009943  mov     r9d, 68Ch
0x180009949  mov     ebx, eax
0x18000994b  call    ElValidateHr_5
0x180009950  test    eax, eax
0x180009952  js      loc_180009BB9
0x180009958  mov     rdx, [rsi+170h]
0x18000995f  lea     r8, [rbp+57h+arg_10]
0x180009963  lea     rcx, [rbp+57h+var_D0]
0x180009967  mov     rdx, [rdx+r12*8]
0x18000996b  call    ?FindString@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAHPEBGPEAK@Z; CDynArray<ushort *,CDeallocateNone>::FindString(ushort const *,ulong *)
0x180009970  xor     r12d, r12d
0x180009973  test    eax, eax
0x180009975  jz      short loc_180009983
0x180009977  mov     edx, [rbp+57h+arg_10]
0x18000997a  lea     rcx, [rbp+57h+var_D0]
0x18000997e  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateNone>::ClearItem(ulong)
0x180009983  inc     r15d
0x180009986  cmp     r15d, [rsi+16Ch]
0x18000998d  jb      loc_1800098F5
0x180009993  lea     rcx, [rbp+57h+var_90]; this
0x180009997  call    ?FindNext@CEnumImages@@QEAAJXZ; CEnumImages::FindNext(void)
0x18000999c  test    eax, eax
0x18000999e  jz      loc_18000982F
0x1800099a4  mov     rdx, [rdi+188h]
0x1800099ab  test    rdx, rdx
0x1800099ae  jz      short loc_1800099D2
0x1800099b0  mov     rax, [rdx+8]
0x1800099b4  add     rdx, 8
0x1800099b8  movsxd  rcx, dword ptr [rax+4]
0x1800099bc  add     rcx, rdx
0x1800099bf  mov     rax, [rcx]
0x1800099c2  mov     rax, [rax+10h]
0x1800099c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099cb  mov     [rdi+188h], r12
0x1800099d2  mov     rdx, [rdi+180h]
0x1800099d9  test    rdx, rdx
0x1800099dc  jz      short loc_180009A00
0x1800099de  mov     rax, [rdx+8]
0x1800099e2  add     rdx, 8
0x1800099e6  movsxd  rcx, dword ptr [rax+4]
0x1800099ea  add     rcx, rdx
0x1800099ed  mov     rax, [rcx]
0x1800099f0  mov     rax, [rax+10h]
0x1800099f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f9  mov     [rdi+180h], r12
0x180009a00  mov     rdx, [rdi+178h]
0x180009a07  test    rdx, rdx
0x180009a0a  jz      short loc_180009A2E
0x180009a0c  mov     rax, [rdx+8]
0x180009a10  add     rdx, 8
0x180009a14  movsxd  rcx, dword ptr [rax+4]
0x180009a18  add     rcx, rdx
0x180009a1b  mov     rax, [rcx]
0x180009a1e  mov     rax, [rax+10h]
0x180009a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a27  mov     [rdi+178h], r12
0x180009a2e  cmp     dword ptr [rdi+1Ch], 2
0x180009a32  jnz     loc_180009AFE
0x180009a38  cmp     dword ptr [rdi+80h], 1
0x180009a3f  jbe     loc_180009AFE
0x180009a45  mov     rdx, [rdi+58h]; unsigned __int16 *
0x180009a49  lea     rcx, [rbp+57h+var_B8]; this
0x180009a4d  mov     [rsp+110h+var_E0], r12; unsigned int *
0x180009a52  mov     r9d, 3; unsigned int
0x180009a58  mov     [rsp+110h+var_E8], r12d; unsigned int
0x180009a5d  mov     r8d, 40000000h; unsigned int
0x180009a63  mov     [rsp+110h+var_F0], r12d; unsigned int
0x180009a68  call    ?Create@CWIMFile@@QEAAKPEBGKKKKPEAK@Z; CWIMFile::Create(ushort const *,ulong,ulong,ulong,ulong,ulong *)
0x180009a6d  mov     r9d, 6ADh
0x180009a73  mov     ecx, eax
0x180009a75  mov     r14d, eax
0x180009a78  call    ElValidateWin32_4
0x180009a7d  test    eax, eax
0x180009a7f  jnz     loc_180009B9E
0x180009a85  mov     edx, [rdi+84h]
0x180009a8b  mov     r14d, r12d
0x180009a8e  mov     rcx, [rbp+57h+var_B8]
0x180009a92  call    cs:__imp_WIMDeleteImage
0x180009a99  nop     dword ptr [rax+rax+00h]
0x180009a9e  test    eax, eax
0x180009aa0  jnz     short loc_180009ABE
0x180009aa2  call    cs:__imp_GetLastError
0x180009aa9  nop     dword ptr [rax+rax+00h]
0x180009aae  mov     ecx, eax
0x180009ab0  mov     r9d, 17Bh
0x180009ab6  call    ElValidateWin32_5
0x180009abb  mov     r14d, eax
0x180009abe  mov     r9d, 6B0h
0x180009ac4  mov     ecx, r14d
0x180009ac7  call    ElValidateWin32_4
0x180009acc  test    eax, eax
0x180009ace  jnz     loc_180009B9E
0x180009ad4  lea     rcx, [rbp+57h+var_B8]; this
0x180009ad8  call    ?Shutdown@CWIMFile@@QEAAKXZ; CWIMFile::Shutdown(void)
0x180009add  mov     rdx, [rdi+58h]
0x180009ae1  lea     r8, [rbp+57h+arg_10]
0x180009ae5  lea     rcx, [rbp+57h+var_D0]
0x180009ae9  call    ?FindString@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAHPEBGPEAK@Z; CDynArray<ushort *,CDeallocateNone>::FindString(ushort const *,ulong *)
0x180009aee  test    eax, eax
0x180009af0  jz      short loc_180009AFE
0x180009af2  mov     edx, [rbp+57h+arg_10]
0x180009af5  lea     rcx, [rbp+57h+var_D0]
0x180009af9  call    ?ClearItem@?$CDynArray@PEAGVCDeallocateNone@@@@QEAAKK@Z; CDynArray<ushort *,CDeallocateNone>::ClearItem(ulong)
0x180009afe  mov     r15d, r12d
0x180009b01  mov     r12d, dword ptr [rbp+57h+var_C8+4]
0x180009b05  test    r12d, r12d
0x180009b08  jz      short loc_180009B5A
0x180009b0a  cmp     r15d, r12d
0x180009b0d  jnb     short loc_180009B1A
0x180009b0f  mov     rax, [rbp+57h+var_D0]
0x180009b13  mov     ecx, r15d
0x180009b16  mov     r13, [rax+rcx*8]
0x180009b1a  mov     rcx, r13; lpFileName
0x180009b1d  call    cs:__imp_DeleteFileW
0x180009b24  nop     dword ptr [rax+rax+00h]
0x180009b29  test    eax, eax
0x180009b2b  jnz     short loc_180009B52
0x180009b2d  call    cs:__imp_GetLastError
0x180009b34  nop     dword ptr [rax+rax+00h]
0x180009b39  mov     r14d, eax
0x180009b3c  cmp     eax, 2
0x180009b3f  jz      short loc_180009B52
0x180009b41  mov     r9d, 6CCh
0x180009b47  mov     ecx, eax
0x180009b49  call    ElValidateWin32_4
0x180009b4e  test    eax, eax
0x180009b50  jnz     short loc_180009B9B
0x180009b52  inc     r15d
0x180009b55  cmp     r15d, r12d
0x180009b58  jb      short loc_180009B0F
0x180009b5a  xor     r12d, r12d
0x180009b5d  cmp     [rbp+57h+arg_8], r12d
0x180009b61  jz      short loc_180009BBC
0x180009b63  mov     rcx, [rdi+60h]
0x180009b67  call    cs:__imp_WdsDeleteDirectory
0x180009b6e  nop     dword ptr [rax+rax+00h]
0x180009b73  mov     edi, eax
0x180009b75  lea     ecx, [rax-2]
0x180009b78  cmp     ecx, 1
0x180009b7b  jbe     short loc_180009BBC
0x180009b7d  cmp     eax, 7Bh ; '{'
  ... truncated ...
```

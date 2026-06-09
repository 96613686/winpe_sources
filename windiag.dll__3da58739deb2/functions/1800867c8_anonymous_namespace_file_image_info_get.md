# _anonymous_namespace_::file_image_info::get

- ea: `0x1800867c8`
- end: `0x180086e69`
- name: `_anonymous_namespace_::file_image_info::get`
- size: `1697`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x18008700c`

## callees

- `0x180004090`
- `0x180004510`
- `0x1800054e4`
- `0x18003a52c`
- `0x18003b0bc`
- `0x18003f668`
- `0x18003f6b8`
- `0x180041564`
- `0x1800587c8`
- `0x180083e58`
- `0x1800867c8`
- `0x180088a9c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180086887`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180086813`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180086813`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180086842`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180086842`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008686d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18008686d`
- `imagehlp!ImageDirectoryEntryToDataEx` at `0x180086a10`
- `imagehlp!ImageDirectoryEntryToDataEx` at `0x180086a10`
- `imagehlp!ImageNtHeader` at `0x1800868bd`
- `imagehlp!ImageNtHeader` at `0x1800868bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::file_image_info::get(__int64 a1, void *a2)
{
  HANDLE FileMappingW; // rax
  void *v5; // rbx
  void *v6; // rax
  PIMAGE_NT_HEADERS v7; // rax
  _QWORD *v8; // rdx
  char v9; // cl
  char *v10; // r8
  unsigned __int64 v11; // r9
  char *v12; // r14
  char *v13; // r11
  unsigned int i; // ecx
  __int64 v15; // r12
  unsigned __int64 v16; // rdi
  char *v17; // r15
  unsigned int v18; // r12d
  int j; // eax
  __int128 *v20; // r14
  __int64 v21; // r15
  char *v22; // rdi
  __int64 last_trivial_1; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int128 *v26; // rdx
  _QWORD *v27; // rdx
  _QWORD *v28; // rdx
  ULONG Size; // [rsp+30h] [rbp-D0h] BYREF
  PVOID Base; // [rsp+38h] [rbp-C8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v33[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int128 v35; // [rsp+68h] [rbp-98h]
  __int128 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+88h] [rbp-78h]
  __int128 v38; // [rsp+98h] [rbp-68h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41; // [rsp+B8h] [rbp-48h]
  char v42; // [rsp+C0h] [rbp-40h]
  _QWORD v43[2]; // [rsp+C8h] [rbp-38h] BYREF
  int v44; // [rsp+D8h] [rbp-28h]
  __int128 v45; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v46; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v47; // [rsp+F8h] [rbp-8h]
  char v48; // [rsp+100h] [rbp+0h]
  char v49; // [rsp+108h] [rbp+8h]
  __int64 v50; // [rsp+120h] [rbp+20h] BYREF
  __int128 v51; // [rsp+128h] [rbp+28h]
  __int128 v52; // [rsp+138h] [rbp+38h]
  __int128 v53; // [rsp+148h] [rbp+48h]
  __int128 v54; // [rsp+158h] [rbp+58h] BYREF
  __int64 v55; // [rsp+168h] [rbp+68h]
  __int64 v56; // [rsp+170h] [rbp+70h]
  char v57; // [rsp+178h] [rbp+78h]
  char v58; // [rsp+180h] [rbp+80h]
  HANDLE v59; // [rsp+190h] [rbp+90h]
  __int128 v60; // [rsp+198h] [rbp+98h] BYREF
  unsigned __int64 v61; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v62; // [rsp+1B0h] [rbp+B0h]
  _QWORD v63[7]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD *v64; // [rsp+1F8h] [rbp+F8h]
  _OWORD v65[2]; // [rsp+200h] [rbp+100h] BYREF

  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(a2, &FileSize) || FileSize.HighPart )
  {
    *(_BYTE *)(a1 + 192) = 0;
  }
  else
  {
    FileMappingW = CreateFileMappingW(a2, 0, 2u, 0, 0, 0);
    v5 = FileMappingW;
    v59 = FileMappingW;
    if ( FileMappingW )
    {
      v6 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
      Base = v6;
      if ( v6 )
      {
        v63[0] = off_18009F950;
        v63[1] = &Base;
        v64 = v63;
        v7 = ImageNtHeader(v6);
        if ( v7 )
        {
          v33[0] = v7->FileHeader.TimeDateStamp;
          v33[1] = v7->OptionalHeader.SizeOfImage;
          v33[2] = v7->OptionalHeader.CheckSum;
          v33[3] = 0;
          v42 = 0;
          v49 = 0;
          anonymous_namespace_::file_image_info::version_info(&v50);
          v9 = v58;
          if ( v58 )
          {
            if ( v42 && v41 )
            {
              std::wstring::~wstring(&v38);
              v9 = v58;
            }
            v34 = v50;
            v35 = v51;
            v36 = v52;
            v37 = v53;
            v41 = 0;
            if ( v57 )
            {
              v38 = v54;
              v39 = v55;
              v40 = v56;
              v55 = 0;
              v56 = 7;
              LOWORD(v54) = 0;
              v41 = 1;
            }
            v42 = 1;
            if ( v9 && v57 )
              std::wstring::~wstring(&v54);
          }
          Size = 0;
          v10 = (char *)ImageDirectoryEntryToDataEx(Base, 0, 6u, &Size, 0);
          if ( v10 && (v11 = Size / 0x1CuLL, Size == 28 * v11) )
          {
            v12 = (char *)Base;
            if ( v10 < Base || (v13 = (char *)Base + FileSize.LowPart, &v10[Size] > v13) )
            {
              std::optional__anonymous_namespace_::file_image_info_::optional__anonymous_namespace_::file_image_info___anonymous_namespace_::file_image_info_0_(
                a1,
                v33,
                v10);
              if ( v49 && v48 )
                std::string::~string(&v45);
              if ( v42 && v41 )
                std::wstring::~wstring(&v38);
              if ( v64 )
              {
                (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
                if ( v64 )
                {
                  v27 = v63;
                  LOBYTE(v27) = v64 != v63;
                  (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v64 + 32LL))(v64, v27);
                  v64 = 0;
                }
              }
            }
            else
            {
              for ( i = 0; i < v11; ++i )
              {
                v15 = *((unsigned int *)v10 + 4);
                if ( &v10[v15] > v13 )
                  break;
                if ( *((_DWORD *)v10 + 3) == 2 )
                {
                  v16 = *((unsigned int *)v10 + 6);
                  if ( v16 + 24 < FileSize.LowPart && v16 + 24 > v16 && *(_DWORD *)((char *)Base + v16) == 1396986706 )
                  {
                    v17 = (char *)Base + v16 + 24;
                    v18 = v15 - 24;
                    if ( v49 && v48 )
                      std::string::~string(&v45);
                    memset_0(v43, 0, 0x40u);
                    v44 = 0;
                    v48 = 0;
                    v49 = 1;
                    v43[0] = *(_QWORD *)&v12[v16 + 4];
                    v43[1] = *(_QWORD *)&v12[v16 + 12];
                    v44 = *(_DWORD *)&v12[v16 + 20];
                    v10 = &v12[v16 + 24];
                    for ( j = (int)v17; j - (int)v17 < v18; j = (int)v10 )
                    {
                      if ( !*v10 )
                      {
                        v60 = 0;
                        v61 = 0;
                        v62 = 0;
                        if ( v17 == v10 )
                        {
                          v61 = 0;
                          v62 = 15;
                          LOBYTE(v60) = 0;
                        }
                        else
                        {
                          std::string::_Construct<1,char const *>(&v60, &v12[v16 + 24], v10 - v17);
                        }
                        v20 = &v60;
                        if ( v62 > 0xF )
                          v20 = (__int128 *)v60;
                        if ( v61 )
                        {
                          v21 = -1;
                          v22 = (char *)v20 + v61;
                          LOBYTE(v10) = 92;
                          last_trivial_1 = _std_find_last_trivial_1(v20, (char *)v20 + v61, v10);
                          if ( (char *)last_trivial_1 != v22 )
                          {
                            v24 = last_trivial_1 - (_QWORD)v20;
                            if ( v24 != -1 )
                            {
                              v25 = v24 + 1;
                              memset(v65, 0, sizeof(v65));
                              if ( v61 < v24 + 1 )
                                std::_String_val<std::_Simple_types<char>>::_Xran();
                              if ( v61 - v25 != -1 )
                                v21 = v61 - v25;
                              v26 = &v60;
                              if ( v62 > 0xF )
                                v26 = (__int128 *)v60;
                              std::string::_Construct<1,char const *>(v65, (char *)v26 + v25, v21);
                              std::string::operator=(&v60, v65);
                              std::string::~string(v65);
                            }
                          }
                        }
                        if ( v48 )
                        {
                          std::string::operator=(&v45, &v60);
                        }
                        else
                        {
                          v45 = v60;
                          v46 = v61;
                          v47 = v62;
                          v61 = 0;
                          v62 = 15;
                          LOBYTE(v60) = 0;
                          v48 = 1;
                        }
                        std::string::~string(&v60);
                        goto LABEL_59;
                      }
                      ++v10;
                    }
                  }
                  break;
                }
                v10 += 28;
              }
LABEL_59:
              std::optional__anonymous_namespace_::file_image_info_::optional__anonymous_namespace_::file_image_info___anonymous_namespace_::file_image_info_0_(
                a1,
                v33,
                v10);
              if ( v49 && v48 )
                std::string::~string(&v45);
              if ( v42 && v41 )
                std::wstring::~wstring(&v38);
              windiag::scope_exit::~scope_exit((windiag::scope_exit *)v63);
            }
          }
          else
          {
            std::optional__anonymous_namespace_::file_image_info_::optional__anonymous_namespace_::file_image_info___anonymous_namespace_::file_image_info_0_(
              a1,
              v33,
              v10);
            if ( v49 && v48 )
              std::string::~string(&v45);
            if ( v42 && v41 )
              std::wstring::~wstring(&v38);
            if ( v64 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
              if ( v64 )
              {
                v28 = v63;
                LOBYTE(v28) = v64 != v63;
                (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v64 + 32LL))(v64, v28);
                v64 = 0;
              }
            }
          }
        }
        else
        {
          *(_BYTE *)(a1 + 192) = 0;
          if ( v64 )
          {
            (*(void (__fastcall **)(_QWORD *))(*v64 + 16LL))(v64);
            if ( v64 )
            {
              v8 = v63;
              LOBYTE(v8) = v64 != v63;
              (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v64 + 32LL))(v64, v8);
              v64 = 0;
            }
          }
        }
      }
      else
      {
        *(_BYTE *)(a1 + 192) = 0;
      }
      CloseHandle(v5);
    }
    else
    {
      *(_BYTE *)(a1 + 192) = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800867c8  mov     [rsp-8+arg_10], rbx
0x1800867cd  push    rbp
0x1800867ce  push    rsi
0x1800867cf  push    rdi
0x1800867d0  push    r12
0x1800867d2  push    r13
0x1800867d4  push    r14
0x1800867d6  push    r15
0x1800867d8  lea     rbp, [rsp-130h]
0x1800867e0  sub     rsp, 230h
0x1800867e7  mov     rax, cs:__security_cookie
0x1800867ee  xor     rax, rsp
0x1800867f1  mov     [rbp+160h+var_40], rax
0x1800867f8  mov     rbx, rdx
0x1800867fb  mov     rsi, rcx
0x1800867fe  mov     qword ptr [rsp+260h+FileSize], rcx
0x180086803  xor     r13d, r13d
0x180086806  mov     qword ptr [rsp+260h+FileSize], r13
0x18008680b  lea     rdx, [rsp+260h+FileSize]; lpFileSize
0x180086810  mov     rcx, rbx; hFile
0x180086813  call    cs:__imp_GetFileSizeEx
0x180086819  test    eax, eax
0x18008681b  jz      loc_180086E2F
0x180086821  cmp     dword ptr [rsp+260h+FileSize+4], r13d
0x180086826  jnz     loc_180086E2F
0x18008682c  mov     [rsp+260h+lpName], r13; lpName
0x180086831  mov     [rsp+260h+dwMaximumSizeLow], r13d; dwMaximumSizeLow
0x180086836  xor     r9d, r9d; dwMaximumSizeHigh
0x180086839  xor     edx, edx; lpFileMappingAttributes
0x18008683b  lea     r8d, [r13+2]; flProtect
0x18008683f  mov     rcx, rbx; hFile
0x180086842  call    cs:__imp_CreateFileMappingW
0x180086848  mov     rbx, rax
0x18008684b  mov     [rbp+160h+var_D0], rax
0x180086852  test    rax, rax
0x180086855  jz      loc_180086E26
0x18008685b  mov     qword ptr [rsp+260h+dwMaximumSizeLow], r13; dwNumberOfBytesToMap
0x180086860  xor     r9d, r9d; dwFileOffsetLow
0x180086863  xor     r8d, r8d; dwFileOffsetHigh
0x180086866  lea     edx, [r13+4]; dwDesiredAccess
0x18008686a  mov     rcx, rax; hFileMappingObject
0x18008686d  call    cs:__imp_MapViewOfFile
0x180086873  mov     [rsp+260h+Base], rax
0x180086878  test    rax, rax
0x18008687b  jnz     short loc_180086892
0x18008687d  mov     [rsi+0C0h], r13b
0x180086884  mov     rcx, rbx; hObject
0x180086887  call    cs:__imp_CloseHandle
0x18008688d  jmp     loc_180086E36
0x180086892  lea     rcx, off_18009F950
0x180086899  mov     [rbp+160h+var_A0], rcx
0x1800868a0  lea     rcx, [rsp+260h+Base]
0x1800868a5  mov     [rbp+160h+var_98], rcx
0x1800868ac  lea     rcx, [rbp+160h+var_A0]
0x1800868b3  mov     [rbp+160h+var_68], rcx
0x1800868ba  mov     rcx, rax; Base
0x1800868bd  call    cs:__imp_ImageNtHeader
0x1800868c3  mov     rcx, rax
0x1800868c6  test    rax, rax
0x1800868c9  jnz     short loc_18008691B
0x1800868cb  mov     [rsi+0C0h], r13b
0x1800868d2  mov     rcx, [rbp+160h+var_68]
0x1800868d9  test    rcx, rcx
0x1800868dc  jz      short loc_180086916
0x1800868de  mov     rax, [rcx]
0x1800868e1  mov     rax, [rax+10h]
0x1800868e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800868ea  mov     rcx, [rbp+160h+var_68]
0x1800868f1  test    rcx, rcx
0x1800868f4  jz      short loc_180086916
0x1800868f6  mov     rax, [rcx]
0x1800868f9  lea     rdx, [rbp+160h+var_A0]
0x180086900  cmp     rcx, rdx
0x180086903  setnz   dl
0x180086906  mov     rax, [rax+20h]
0x18008690a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008690f  mov     [rbp+160h+var_68], r13
0x180086916  jmp     loc_180086884
0x18008691b  mov     eax, [rax+8]
0x18008691e  mov     [rsp+260h+var_210], eax
0x180086922  mov     eax, [rcx+50h]
0x180086925  mov     [rsp+260h+var_20C], eax
0x180086929  mov     eax, [rcx+58h]
0x18008692c  mov     [rsp+260h+var_208], eax
0x180086930  xor     eax, eax
0x180086932  mov     [rsp+260h+var_204], eax
0x180086936  mov     [rbp+160h+var_1A0], r13b
0x18008693a  mov     [rbp+160h+var_158], r13b
0x18008693e  mov     rdx, [rsp+260h+Base]
0x180086943  lea     rcx, [rbp+160h+var_140]; void *
0x180086947  call    _anonymous_namespace___file_image_info__version_info
0x18008694c  mov     cl, [rbp+160h+var_E0]
0x180086952  test    cl, cl
0x180086954  jz      loc_1800869F4
0x18008695a  cmp     [rbp+160h+var_1A0], r13b
0x18008695e  jz      short loc_180086975
0x180086960  cmp     [rbp+160h+var_1A8], r13b
0x180086964  jz      short loc_180086975
0x180086966  lea     rcx, [rbp+160h+var_1C8]
0x18008696a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008696f  mov     cl, [rbp+160h+var_E0]
0x180086975  mov     rax, [rbp+160h+var_140]
0x180086979  mov     [rsp+260h+var_200], rax
0x18008697e  movups  xmm0, [rbp+160h+var_138]
0x180086982  movups  [rsp+260h+var_1F8], xmm0
0x180086987  movups  xmm1, [rbp+160h+var_128]
0x18008698b  movups  [rsp+260h+var_1E8], xmm1
0x180086990  movups  xmm0, [rbp+160h+var_118]
0x180086994  movups  [rbp+160h+var_1D8], xmm0
0x180086998  mov     [rbp+160h+var_1A8], r13b
0x18008699c  mov     dl, [rbp+160h+var_E8]
0x18008699f  test    dl, dl
0x1800869a1  jz      short loc_1800869DF
0x1800869a3  xorps   xmm0, xmm0
0x1800869a6  movups  [rbp+160h+var_1C8], xmm0
0x1800869aa  mov     rax, qword ptr [rbp+160h+var_108]
0x1800869ae  mov     qword ptr [rbp+160h+var_1C8], rax
0x1800869b2  mov     rax, qword ptr [rbp+160h+var_108+8]
0x1800869b6  mov     qword ptr [rbp+160h+var_1C8+8], rax
0x1800869ba  mov     rax, [rbp+160h+var_F8]
0x1800869be  mov     [rbp+160h+var_1B8], rax
0x1800869c2  mov     rax, [rbp+160h+var_F0]
0x1800869c6  mov     [rbp+160h+var_1B0], rax
0x1800869ca  mov     [rbp+160h+var_F8], r13
0x1800869ce  mov     [rbp+160h+var_F0], 7
0x1800869d6  mov     word ptr [rbp+160h+var_108], r13w
0x1800869db  mov     [rbp+160h+var_1A8], 1
0x1800869df  mov     [rbp+160h+var_1A0], 1
0x1800869e3  test    cl, cl
0x1800869e5  jz      short loc_1800869F4
0x1800869e7  test    dl, dl
0x1800869e9  jz      short loc_1800869F4
0x1800869eb  lea     rcx, [rbp+160h+var_108]
0x1800869ef  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800869f4  mov     [rsp+260h+Size], r13d
0x1800869f9  mov     r8d, 6; DirectoryEntry
0x1800869ff  mov     qword ptr [rsp+260h+dwMaximumSizeLow], r13; FoundHeader
0x180086a04  lea     r9, [rsp+260h+Size]; Size
0x180086a09  xor     edx, edx; MappedAsImage
0x180086a0b  mov     rcx, [rsp+260h+Base]; Base
0x180086a10  call    cs:__imp_ImageDirectoryEntryToDataEx
0x180086a16  mov     r8, rax
0x180086a19  test    rax, rax
0x180086a1c  jz      loc_180086DA4
0x180086a22  mov     r10d, [rsp+260h+Size]
0x180086a27  mov     rax, 2492492492492493h
0x180086a31  mul     r10
0x180086a34  mov     r9d, r10d
0x180086a37  sub     r9, rdx
0x180086a3a  shr     r9, 1
0x180086a3d  add     r9, rdx
0x180086a40  shr     r9, 4
0x180086a44  imul    rcx, r9, 1Ch
0x180086a48  cmp     r10, rcx
0x180086a4b  jnz     loc_180086DA4
0x180086a51  mov     r14, [rsp+260h+Base]
0x180086a56  cmp     r8, r14
0x180086a59  jb      loc_180086D22
0x180086a5f  mov     edx, dword ptr [rsp+260h+FileSize]
0x180086a63  lea     r11, [rdx+r14]
0x180086a67  lea     rax, [r10+r8]
0x180086a6b  cmp     rax, r11
0x180086a6e  ja      loc_180086D22
0x180086a74  mov     ecx, r13d
0x180086a77  test    r9, r9
0x180086a7a  jz      loc_180086CD8
0x180086a80  mov     r12d, [r8+10h]
0x180086a84  lea     rax, [r8+r12]
0x180086a88  cmp     rax, r11
0x180086a8b  ja      loc_180086CD8
0x180086a91  cmp     dword ptr [r8+0Ch], 2
0x180086a96  jz      short loc_180086AAA
0x180086a98  add     r8, 1Ch
0x180086a9c  inc     ecx
0x180086a9e  mov     eax, ecx
0x180086aa0  cmp     rax, r9
0x180086aa3  jb      short loc_180086A80
0x180086aa5  jmp     loc_180086CD8
0x180086aaa  mov     edi, [r8+18h]
0x180086aae  lea     rax, [rdi+18h]
0x180086ab2  cmp     rax, rdx
0x180086ab5  jnb     loc_180086CD8
0x180086abb  cmp     rax, rdi
0x180086abe  jbe     loc_180086CD8
0x180086ac4  cmp     dword ptr [rdi+r14], 53445352h
0x180086acc  jnz     loc_180086CD8
0x180086ad2  lea     r15, [r14+18h]
0x180086ad6  add     r15, rdi
0x180086ad9  add     r12d, 0FFFFFFE8h
0x180086add  cmp     [rbp+160h+var_158], r13b
0x180086ae1  jz      short loc_180086AF2
0x180086ae3  cmp     [rbp+160h+var_160], r13b
0x180086ae7  jz      short loc_180086AF2
0x180086ae9  lea     rcx, [rbp+160h+var_180]
0x180086aed  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180086af2  xor     edx, edx; Val
0x180086af4  lea     r8d, [rdx+40h]; Size
0x180086af8  lea     rcx, [rbp+160h+var_198]; void *
0x180086afc  call    memset_0
0x180086b01  mov     [rbp+160h+var_188], r13d
0x180086b05  mov     [rbp+160h+var_160], r13b
0x180086b09  mov     [rbp+160h+var_158], 1
0x180086b0d  mov     rax, [rdi+r14+4]
0x180086b12  mov     [rbp+160h+var_198], rax
0x180086b16  mov     rax, [rdi+r14+0Ch]
0x180086b1b  mov     [rbp+160h+var_190], rax
0x180086b1f  mov     eax, [rdi+r14+14h]
0x180086b24  mov     [rbp+160h+var_188], eax
0x180086b27  mov     r8, r15
0x180086b2a  mov     eax, r15d
0x180086b2d  jmp     short loc_180086B3A
0x180086b2f  cmp     [r8], r13b
0x180086b32  jz      short loc_180086B47
0x180086b34  inc     r8
0x180086b37  mov     eax, r8d
0x180086b3a  sub     eax, r15d
0x180086b3d  cmp     eax, r12d
0x180086b40  jb      short loc_180086B2F
0x180086b42  jmp     loc_180086CD8
0x180086b47  xorps   xmm0, xmm0
0x180086b4a  movups  [rbp+160h+var_C8], xmm0
0x180086b51  mov     [rbp+160h+var_B8], r13
0x180086b58  mov     [rbp+160h+var_B0], r13
0x180086b5f  mov     r12d, 0Fh
0x180086b65  cmp     r15, r8
0x180086b68  jnz     short loc_180086B81
0x180086b6a  mov     [rbp+160h+var_B8], r13
0x180086b71  mov     [rbp+160h+var_B0], r12
0x180086b78  mov     byte ptr [rbp+160h+var_C8], r13b
0x180086b7f  jmp     short loc_180086B94
0x180086b81  sub     r8, r15
0x180086b84  mov     rdx, r15
0x180086b87  lea     rcx, [rbp+160h+var_C8]
0x180086b8e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180086b93  nop
0x180086b94  mov     rax, [rbp+160h+var_B8]
0x180086b9b  lea     r14, [rbp+160h+var_C8]
0x180086ba2  cmp     [rbp+160h+var_B0], r12
0x180086ba9  cmova   r14, qword ptr [rbp+160h+var_C8]
0x180086bb1  test    rax, rax
0x180086bb4  jz      loc_180086C68
0x180086bba  dec     rax
0x180086bbd  or      r15, 0FFFFFFFFFFFFFFFFh
0x180086bc1  cmp     rax, r15
0x180086bc4  cmovnb  rax, r15
0x180086bc8  lea     rdi, [rax+1]
0x180086bcc  add     rdi, r14
0x180086bcf  mov     r8b, 5Ch ; '\'
0x180086bd2  mov     rdx, rdi
0x180086bd5  mov     rcx, r14
0x180086bd8  call    __std_find_last_trivial_1
0x180086bdd  cmp     rax, rdi
0x180086be0  jz      loc_180086C68
0x180086be6  sub     rax, r14
0x180086be9  cmp     rax, r15
0x180086bec  jz      short loc_180086C68
0x180086bee  lea     rcx, [rax+1]
0x180086bf2  xorps   xmm0, xmm0
0x180086bf5  movups  [rbp+160h+var_60], xmm0
0x180086bfc  xorps   xmm1, xmm1
0x180086bff  movdqu  [rbp+160h+var_50], xmm1
0x180086c07  mov     rax, [rbp+160h+var_B8]
0x180086c0e  cmp     rax, rcx
0x180086c11  jb      loc_180086E63
0x180086c17  sub     rax, rcx
0x180086c1a  cmp     rax, r15
0x180086c1d  cmovb   r15, rax
0x180086c21  lea     rdx, [rbp+160h+var_C8]
0x180086c28  cmp     [rbp+160h+var_B0], r12
0x180086c2f  cmova   rdx, qword ptr [rbp+160h+var_C8]
0x180086c37  add     rdx, rcx
0x180086c3a  mov     r8, r15
0x180086c3d  lea     rcx, [rbp+160h+var_60]
0x180086c44  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180086c49  lea     rdx, [rbp+160h+var_60]
0x180086c50  lea     rcx, [rbp+160h+var_C8]
0x180086c57  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180086c5c  lea     rcx, [rbp+160h+var_60]
0x180086c63  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180086c68  cmp     [rbp+160h+var_160], r13b
0x180086c6c  jz      short loc_180086C80
0x180086c6e  lea     rdx, [rbp+160h+var_C8]
0x180086c75  lea     rcx, [rbp+160h+var_180]
0x180086c79  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180086c7e  jmp     short loc_180086CCC
0x180086c80  xorps   xmm0, xmm0
0x180086c83  movups  [rbp+160h+var_180], xmm0
0x180086c87  mov     rax, qword ptr [rbp+160h+var_C8]
0x180086c8e  mov     qword ptr [rbp+160h+var_180], rax
0x180086c92  mov     rax, qword ptr [rbp+160h+var_C8+8]
0x180086c99  mov     qword ptr [rbp+160h+var_180+8], rax
0x180086c9d  mov     rax, [rbp+160h+var_B8]
0x180086ca4  mov     [rbp+160h+var_170], rax
0x180086ca8  mov     rax, [rbp+160h+var_B0]
0x180086caf  mov     [rbp+160h+var_168], rax
0x180086cb3  mov     [rbp+160h+var_B8], r13
0x180086cba  mov     [rbp+160h+var_B0], r12
0x180086cc1  mov     byte ptr [rbp+160h+var_C8], r13b
0x180086cc8  mov     [rbp+160h+var_160], 1
0x180086ccc  lea     rcx, [rbp+160h+var_C8]
  ... truncated ...
```

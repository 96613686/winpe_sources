# p9fs::util::FsUtilDirect::OpenFile(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ulong,p9fs::util::OpenFileFlags,gsl::span<gsl::byte,-1>,gsl::span<gsl::byte,-1>,p9fs::util::OpenFileOutputFlags *)

- ea: `0x18002c130`
- end: `0x18002c354`
- name: `?OpenFile@FsUtilDirect@util@p9fs@@UEAA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@2@PEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KKW4OpenFileFlags@23@V?$span@W4byte@gsl@@$0?0@gsl@@3PEAW4OpenFileOutputFlags@23@@Z`
- size: `548`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002bc50`
- `0x18002c8d0`

## callees

- `0x180004120`
- `0x18001ca24`
- `0x18002c130`
- `0x18002c4ec`
- `0x18002c9b4`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c2f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c2f5`
- `ntdll!NtSetInformationFile` at `0x18002c2bc`
- `ntdll!NtSetInformationFile` at `0x18002c2bc`
- `lxutil!LxUtilFsDeleteFile` at `0x18002c2db`
- `lxutil!LxUtilFsDeleteFile` at `0x18002c2db`

## pseudocode

```c
__int64 __fastcall p9fs::util::FsUtilDirect::OpenFile(
        __int64 a1,
        __int64 a2,
        int a3,
        _QWORD *a4,
        int a5,
        ULONG a6,
        char a7,
        struct _IO_STATUS_BLOCK *a8,
        struct _IO_STATUS_BLOCK *a9,
        int *a10)
{
  int v14; // r9d
  ULONG v15; // r8d
  ULONG v16; // edx
  bool v17; // cc
  _QWORD *v18; // rax
  struct _IO_STATUS_BLOCK v19; // xmm0
  int v20; // edi
  NTSTATUS v21; // eax
  int v22; // edx
  int v23; // eax
  HANDLE v24; // rcx
  char v25; // al
  __int64 v27; // [rsp+50h] [rbp-59h] BYREF
  int v28[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v29; // [rsp+68h] [rbp-41h]
  int FileInformation; // [rsp+70h] [rbp-39h] BYREF
  int v31; // [rsp+78h] [rbp-31h] BYREF
  HANDLE FileHandle; // [rsp+80h] [rbp-29h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-19h] BYREF

  FileInformation = a7 & 1;
  v14 = a5 | 0x100000;
  v15 = FileInformation != 0 ? 16 : 128;
  if ( (a7 & 4) != 0 )
    v14 = a5;
  v16 = (FileInformation + 0x200000) | 0x10;
  if ( (a7 & 4) != 0 )
    v16 = FileInformation + 0x200000;
  if ( (a7 & 8) != 0 )
    v15 |= 1u;
  if ( a6 - 2 <= 1 && (a9->Pointer || (a7 & 2) != 0) )
    v14 |= 0x10100u;
  v17 = a4[3] <= 7u;
  v27 = 0;
  if ( v17 )
    v18 = a4;
  else
    v18 = (_QWORD *)*a4;
  v19 = *(struct _IO_STATUS_BLOCK *)&a8->Status;
  *(_QWORD *)v28 = v18;
  v29 = a4[2];
  IoStatusBlock = v19;
  p9fs::util::OpenRelativeFile((int)&v31, a3, (int)v28, v14, a6, v15, v16, (__int64)&IoStatusBlock, (__int64)&v27);
  if ( !(_BYTE)v31 )
  {
    *(_DWORD *)(a2 + 8) = (_DWORD)FileHandle;
    *(_BYTE *)a2 = 0;
    return a2;
  }
  v20 = 0;
  if ( a6 == 2 || v27 == 2 )
  {
    if ( a9->Pointer )
    {
      IoStatusBlock = *(struct _IO_STATUS_BLOCK *)&a9->Status;
      v21 = p9fs::util::SetReparsePoint(FileHandle, &IoStatusBlock);
      if ( v21 < 0 )
      {
        if ( (a7 & 0x10) == 0 )
          goto LABEL_25;
      }
      else
      {
        v20 = 2;
      }
    }
    if ( (a7 & 2) != 0 )
    {
      if ( FileInformation )
      {
        FileInformation = 1;
        IoStatusBlock = 0;
        v21 = NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 4u, FileEaInformation|0x40);
        if ( v21 < 0 )
        {
LABEL_25:
          v23 = p9fs::util::NtStatusToLinuxError((p9fs::util *)(unsigned int)v21, v22);
          v24 = FileHandle;
          *(_BYTE *)a2 = 0;
          *(_DWORD *)(a2 + 8) = v23;
          LxUtilFsDeleteFile(v24, *(_QWORD *)(a1 + 8));
          if ( (_BYTE)v31 && (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            CloseHandle(FileHandle);
          return a2;
        }
      }
    }
  }
  if ( a10 )
  {
    if ( v27 == 2 )
      v20 |= 1u;
    *a10 = v20;
  }
  v25 = v31;
  *(_BYTE *)a2 = v31;
  if ( v25 )
    *(_QWORD *)(a2 + 8) = FileHandle;
  else
    *(_DWORD *)(a2 + 8) = (_DWORD)FileHandle;
  return a2;
}

```

## disassembly

```asm
0x18002c130  mov     [rsp-8+arg_0], rbx
0x18002c135  mov     [rsp-8+arg_18], rsi
0x18002c13a  push    rbp
0x18002c13b  push    rdi
0x18002c13c  push    r12
0x18002c13e  push    r13
0x18002c140  push    r15
0x18002c142  lea     rbp, [rsp-7]
0x18002c147  sub     rsp, 0B0h
0x18002c14e  mov     rax, cs:__security_cookie
0x18002c155  xor     rax, rsp
0x18002c158  mov     [rbp+27h+var_30], rax
0x18002c15c  mov     eax, dword ptr [rbp+27h+arg_30]
0x18002c15f  mov     rbx, rdx
0x18002c162  mov     edx, [rbp+27h+arg_20]
0x18002c165  and     eax, 1
0x18002c168  mov     rdi, [rbp+27h+arg_38]
0x18002c16c  mov     r11, r8
0x18002c16f  mov     r15, [rbp+27h+arg_40]
0x18002c173  mov     r10, r9
0x18002c176  mov     r12, [rbp+27h+arg_48]
0x18002c17a  mov     r9d, edx
0x18002c17d  mov     r13, rcx
0x18002c180  mov     [rbp+27h+FileInformation], eax
0x18002c183  lea     ecx, [rax+200000h]
0x18002c189  neg     eax
0x18002c18b  sbb     r8d, r8d
0x18002c18e  bts     r9d, 14h
0x18002c193  and     r8d, 0FFFFFF90h
0x18002c197  sub     r8d, 0FFFFFF80h
0x18002c19b  test    dword ptr [rbp+27h+arg_30], 4
0x18002c1a2  cmovnz  r9d, edx
0x18002c1a6  mov     edx, ecx
0x18002c1a8  or      edx, 10h
0x18002c1ab  test    dword ptr [rbp+27h+arg_30], 4
0x18002c1b2  cmovnz  edx, ecx
0x18002c1b5  test    [rbp+27h+arg_30], 8
0x18002c1b9  jz      short loc_18002C1BF
0x18002c1bb  or      r8d, 1
0x18002c1bf  mov     esi, [rbp+27h+arg_28]
0x18002c1c2  lea     eax, [rsi-2]
0x18002c1c5  cmp     eax, 1
0x18002c1c8  ja      short loc_18002C1DD
0x18002c1ca  cmp     qword ptr [r15], 0
0x18002c1ce  ja      short loc_18002C1D6
0x18002c1d0  test    [rbp+27h+arg_30], 2
0x18002c1d4  jz      short loc_18002C1DD
0x18002c1d6  or      r9d, 10100h; int
0x18002c1dd  cmp     qword ptr [r10+18h], 7
0x18002c1e2  mov     [rbp+27h+var_80], 0
0x18002c1ea  jbe     short loc_18002C1F1
0x18002c1ec  mov     rax, [r10]
0x18002c1ef  jmp     short loc_18002C1F4
0x18002c1f1  mov     rax, r10
0x18002c1f4  movups  xmm0, xmmword ptr [rdi]
0x18002c1f7  mov     qword ptr [rbp+27h+var_70], rax
0x18002c1fb  lea     rcx, [rbp+27h+var_58]; int
0x18002c1ff  mov     rax, [r10+10h]
0x18002c203  mov     [rbp+27h+var_68], rax
0x18002c207  lea     rax, [rbp+27h+var_80]
0x18002c20b  mov     [rsp+0D0h+var_90], rax; __int64
0x18002c210  lea     rax, [rbp+27h+IoStatusBlock]
0x18002c214  mov     [rsp+0D0h+var_98], rax; __int64
0x18002c219  mov     [rsp+0D0h+var_A0], edx; ULONG
0x18002c21d  mov     rdx, r11; int
0x18002c220  mov     [rsp+0D0h+var_A8], r8d; ULONG
0x18002c225  lea     r8, [rbp+27h+var_70]; int
0x18002c229  movdqu  xmmword ptr [rbp+27h+IoStatusBlock], xmm0
0x18002c22e  mov     [rsp+0D0h+FileInformationClass], esi; ULONG
0x18002c232  call    ?OpenRelativeFile@util@p9fs@@YA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@1@PEAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@KKKKV?$span@W4byte@gsl@@$0?0@gsl@@PEA_K@Z; p9fs::util::OpenRelativeFile(void *,std::basic_string_view<ushort>,ulong,ulong,ulong,ulong,gsl::span<gsl::byte,-1>,unsigned __int64 *)
0x18002c237  cmp     byte ptr [rbp+27h+var_58], 0
0x18002c23b  jnz     short loc_18002C24B
0x18002c23d  mov     ecx, dword ptr [rbp+27h+FileHandle]
0x18002c240  mov     [rbx+8], ecx
0x18002c243  mov     byte ptr [rbx], 0
0x18002c246  jmp     loc_18002C329
0x18002c24b  xor     edi, edi
0x18002c24d  cmp     esi, 2
0x18002c250  jz      short loc_18002C25D
0x18002c252  cmp     [rbp+27h+var_80], 2
0x18002c257  jnz     loc_18002C2FD
0x18002c25d  xor     esi, esi
0x18002c25f  cmp     [r15], rsi
0x18002c262  jbe     short loc_18002C289
0x18002c264  movups  xmm0, xmmword ptr [r15]
0x18002c268  mov     rcx, [rbp+27h+FileHandle]
0x18002c26c  lea     rdx, [rbp+27h+IoStatusBlock]
0x18002c270  movdqu  xmmword ptr [rbp+27h+IoStatusBlock], xmm0
0x18002c275  call    ?SetReparsePoint@util@p9fs@@YAJPEAXV?$span@W4byte@gsl@@$0?0@gsl@@@Z; p9fs::util::SetReparsePoint(void *,gsl::span<gsl::byte,-1>)
0x18002c27a  test    eax, eax
0x18002c27c  js      short loc_18002C283
0x18002c27e  lea     edi, [rsi+2]
0x18002c281  jmp     short loc_18002C289
0x18002c283  test    [rbp+27h+arg_30], 10h
0x18002c287  jz      short loc_18002C2C6
0x18002c289  test    [rbp+27h+arg_30], 2
0x18002c28d  jz      short loc_18002C2FD
0x18002c28f  cmp     [rbp+27h+FileInformation], esi
0x18002c292  jz      short loc_18002C2FD
0x18002c294  mov     rcx, [rbp+27h+FileHandle]; FileHandle
0x18002c298  lea     r8, [rbp+27h+FileInformation]; FileInformation
0x18002c29c  xorps   xmm0, xmm0
0x18002c29f  mov     [rbp+27h+FileInformation], 1
0x18002c2a6  mov     r9d, 4; Length
0x18002c2ac  mov     [rsp+0D0h+FileInformationClass], 47h ; 'G'; FileInformationClass
0x18002c2b4  lea     rdx, [rbp+27h+IoStatusBlock]; IoStatusBlock
0x18002c2b8  movups  xmmword ptr [rbp+27h+IoStatusBlock], xmm0
0x18002c2bc  call    cs:__imp_NtSetInformationFile
0x18002c2c2  test    eax, eax
0x18002c2c4  jns     short loc_18002C2FD
0x18002c2c6  mov     ecx, eax; this
0x18002c2c8  call    ?NtStatusToLinuxError@util@p9fs@@YAJJ@Z; p9fs::util::NtStatusToLinuxError(long)
0x18002c2cd  mov     rcx, [rbp+27h+FileHandle]
0x18002c2d1  mov     [rbx], sil
0x18002c2d4  mov     [rbx+8], eax
0x18002c2d7  mov     rdx, [r13+8]
0x18002c2db  call    cs:__imp_LxUtilFsDeleteFile
0x18002c2e1  cmp     byte ptr [rbp+27h+var_58], sil
0x18002c2e5  jz      short loc_18002C329
0x18002c2e7  mov     rcx, [rbp+27h+FileHandle]; hObject
0x18002c2eb  lea     rax, [rcx-1]
0x18002c2ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002c2f3  ja      short loc_18002C329
0x18002c2f5  call    cs:__imp_CloseHandle
0x18002c2fb  jmp     short loc_18002C329
0x18002c2fd  test    r12, r12
0x18002c300  jz      short loc_18002C310
0x18002c302  cmp     [rbp+27h+var_80], 2
0x18002c307  jnz     short loc_18002C30C
0x18002c309  or      edi, 1
0x18002c30c  mov     [r12], edi
0x18002c310  mov     al, byte ptr [rbp+27h+var_58]
0x18002c313  mov     [rbx], al
0x18002c315  test    al, al
0x18002c317  jz      short loc_18002C323
0x18002c319  mov     rax, [rbp+27h+FileHandle]
0x18002c31d  mov     [rbx+8], rax
0x18002c321  jmp     short loc_18002C329
0x18002c323  mov     eax, dword ptr [rbp+27h+FileHandle]
0x18002c326  mov     [rbx+8], eax
0x18002c329  mov     rax, rbx
0x18002c32c  mov     rcx, [rbp+27h+var_30]
0x18002c330  xor     rcx, rsp; StackCookie
0x18002c333  call    __security_check_cookie
0x18002c338  lea     r11, [rsp+0D0h+var_20]
0x18002c340  mov     rbx, [r11+30h]
0x18002c344  mov     rsi, [r11+48h]
0x18002c348  mov     rsp, r11
0x18002c34b  pop     r15
0x18002c34d  pop     r13
0x18002c34f  pop     r12
0x18002c351  pop     rdi
0x18002c352  pop     rbp
0x18002c353  retn
```

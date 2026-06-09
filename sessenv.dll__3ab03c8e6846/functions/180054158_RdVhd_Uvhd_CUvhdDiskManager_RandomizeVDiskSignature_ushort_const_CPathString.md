# RdVhd::Uvhd::CUvhdDiskManager::RandomizeVDiskSignature(ushort const *,CPathString &)

- ea: `0x180054158`
- end: `0x1800545ba`
- name: `?RandomizeVDiskSignature@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBGAEAVCPathString@@@Z`
- size: `1122`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, struct CPathString *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180051058`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x1800488e4`
- `0x180048b28`
- `0x180048b68`
- `0x18004aafc`
- `0x180054158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005444b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005444b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054591`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005443c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005443c`
- `CRYPTBASE!SystemFunction036` at `0x1800544b0`
- `CRYPTBASE!SystemFunction036` at `0x1800544b0`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180054368`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x180054368`

## string_xrefs

- `0x1800541ed`: `szVhdFilePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::RandomizeVDiskSignature(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        struct CPathString *a3)
{
  signed int v6; // ebx
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  bool v10; // sf
  RdVhd::Uvhd::CUvhdDiskManager *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  int v14; // eax
  WCHAR *Buffer; // rax
  signed int VirtualDiskPhysicalPath; // eax
  const WCHAR *v17; // rax
  HANDLE FileW; // r15
  signed int LastError; // eax
  RdVhd::Util::CVhdHelper *v20; // rcx
  RdVhd::Uvhd::CUvhdDiskManager *v21; // rcx
  __int64 v22; // rdx
  int v23; // eax
  int v24; // edx
  int v25; // r8d
  bool v26; // sf
  int v28; // [rsp+40h] [rbp-40h] BYREF
  HANDLE VirtualDiskHandle; // [rsp+48h] [rbp-38h] BYREF
  void **v30; // [rsp+50h] [rbp-30h] BYREF
  int v31; // [rsp+58h] [rbp-28h]
  __int64 v32; // [rsp+5Ch] [rbp-24h]
  int v33; // [rsp+64h] [rbp-1Ch]
  __int64 v34; // [rsp+68h] [rbp-18h]
  int v35; // [rsp+70h] [rbp-10h]
  ULONG DiskPathSizeInBytes; // [rsp+B8h] [rbp+38h] BYREF
  unsigned int RandomBuffer; // [rsp+C8h] [rbp+48h] BYREF

  VirtualDiskHandle = (HANDLE)-1LL;
  v30 = &CPathString::`vftable';
  v28 = 0;
  v32 = 128;
  v34 = 0;
  v33 = 0;
  v35 = 0x8000000;
  v31 = 0;
  DiskPathSizeInBytes = 0;
  RandomBuffer = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        139,
        WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
        L"szVhdFilePath");
    }
    v6 = -2147024809;
    goto LABEL_83;
  }
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, a2);
  }
  v7 = RdVhd::Util::CVhdHelper::AttachVhd(
         (__int64)this + 8,
         (__int64)a2,
         1,
         (__int64 *)&VirtualDiskHandle,
         &v28,
         (__int64)a3);
  v6 = v7;
  if ( v7 >= 0 )
    goto LABEL_28;
  v8 = HIWORD(v7) & 0x7FF;
  if ( (v7 & 0x78000000) != 0x50000000 )
    v8 = 0;
  if ( v8 )
    goto LABEL_22;
  v9 = (v7 >> 16) & 0x1FFF;
  if ( v9 == 7 || !v9 && (v7 & 0x10000000) == 0 )
  {
    v6 = (unsigned __int16)v7;
    v10 = 0;
    if ( !(_WORD)v7 )
      goto LABEL_21;
    v6 = (unsigned __int16)v7 | 0xD0730000;
  }
  v10 = v6 < 0;
LABEL_21:
  if ( v10 )
  {
LABEL_22:
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v12 = 141;
LABEL_26:
    v13 = (unsigned int)v6;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v13);
    goto LABEL_83;
  }
LABEL_28:
  v14 = CBaseStringT<unsigned short>::EnsureSpace(&v30, 260);
  v6 = v14;
  if ( v14 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v12 = 142;
LABEL_33:
    v13 = (unsigned int)v14;
    goto LABEL_27;
  }
  DiskPathSizeInBytes = 2 * CBaseStringT<unsigned short>::GetBufferLength(&v30);
  Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v30);
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(VirtualDiskHandle, &DiskPathSizeInBytes, Buffer);
  v6 = VirtualDiskPhysicalPath;
  if ( VirtualDiskPhysicalPath )
  {
    if ( (VirtualDiskPhysicalPath & 0xFFFF0000) == 0 )
    {
      if ( VirtualDiskPhysicalPath > 0 )
        v6 = (unsigned __int16)VirtualDiskPhysicalPath | 0x80070000;
      v6 = v6 & 0x8000FFFF | 0x50550000;
    }
    if ( v6 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_83;
      }
      v12 = 143;
      goto LABEL_26;
    }
  }
  v14 = CBaseStringT<unsigned short>::SetLength(&v30, DiskPathSizeInBytes >> 1);
  v6 = v14;
  if ( v14 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v12 = 144;
    goto LABEL_33;
  }
  v17 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v30);
  FileW = CreateFileW(v17, 0xC0000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError && (LastError & 0xFFFF0000) == 0 )
    {
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v6 = v6 & 0x8000FFFF | 0x50560000;
    }
    if ( v6 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_83;
      }
      v12 = 145;
      goto LABEL_26;
    }
  }
  if ( !SystemFunction036(&RandomBuffer, 4u) )
  {
    v6 = -797702565;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = 146;
LABEL_80:
      WPP_SF_d(*((_QWORD *)v21 + 2), v22, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, (unsigned int)v6);
      goto LABEL_81;
    }
    goto LABEL_81;
  }
  v23 = RdVhd::Util::CVhdHelper::SetDiskSignature(v20, FileW, RandomBuffer);
  v6 = v23;
  if ( v23 >= 0 )
    goto LABEL_81;
  v24 = HIWORD(v23) & 0x7FF;
  if ( (v23 & 0x78000000) != 0x50000000 )
    v24 = 0;
  if ( !v24 )
  {
    v25 = (v23 >> 16) & 0x1FFF;
    if ( v25 == 7 || !v25 && (v23 & 0x10000000) == 0 )
    {
      v6 = (unsigned __int16)v23;
      v26 = 0;
      if ( !(_WORD)v23 )
        goto LABEL_75;
      v6 = (unsigned __int16)v23 | 0xD0750000;
    }
    v26 = v6 < 0;
LABEL_75:
    if ( !v26 )
      goto LABEL_81;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = 147;
    goto LABEL_80;
  }
LABEL_81:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
LABEL_83:
  if ( VirtualDiskHandle != (HANDLE)-1LL )
    CloseHandle(VirtualDiskHandle);
  CPathString::~CPathString((CPathString *)&v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180054158  mov     [rsp-28h+arg_0], rbx
0x18005415d  push    rbp
0x18005415e  push    rsi
0x18005415f  push    r13
0x180054161  push    r14
0x180054163  push    r15
0x180054165  mov     rbp, rsp
0x180054168  sub     rsp, 80h
0x18005416f  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180054176  mov     [rbp+VirtualDiskHandle], 0FFFFFFFFFFFFFFFFh
0x18005417e  mov     [rbp+var_30], rax
0x180054182  mov     r15, r8
0x180054185  mov     rbx, rdx
0x180054188  mov     [rbp+var_40], 0
0x18005418f  mov     r13, rcx
0x180054192  mov     [rbp+var_24], 80h
0x18005419a  mov     [rbp+var_18], 0
0x1800541a2  mov     [rbp+var_1C], 0
0x1800541a9  mov     [rbp+var_10], 8000000h
0x1800541b0  mov     [rbp+var_28], 0
0x1800541b7  mov     [rbp+DiskPathSizeInBytes], 0
0x1800541be  mov     [rbp+RandomBuffer], 0
0x1800541c5  test    rdx, rdx
0x1800541c8  jnz     short loc_18005420F
0x1800541ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800541d1  lea     rsi, WPP_GLOBAL_Control
0x1800541d8  cmp     rcx, rsi
0x1800541db  jz      short loc_180054205
0x1800541dd  test    byte ptr [rcx+1Ch], 4
0x1800541e1  jz      short loc_180054205
0x1800541e3  cmp     byte ptr [rcx+19h], 2
0x1800541e7  jb      short loc_180054205
0x1800541e9  mov     rcx, [rcx+10h]
0x1800541ed  lea     r9, aSzvhdfilepath; "szVhdFilePath"
0x1800541f4  mov     edx, 8Bh
0x1800541f9  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180054200  call    WPP_SF_S
0x180054205  mov     ebx, 80070057h
0x18005420a  jmp     loc_180054587
0x18005420f  mov     rcx, cs:WPP_GLOBAL_Control
0x180054216  lea     rsi, WPP_GLOBAL_Control
0x18005421d  lea     r14, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180054224  cmp     rcx, rsi
0x180054227  jz      short loc_180054249
0x180054229  test    byte ptr [rcx+1Ch], 4
0x18005422d  jz      short loc_180054249
0x18005422f  cmp     byte ptr [rcx+19h], 4
0x180054233  jb      short loc_180054249
0x180054235  mov     rcx, [rcx+10h]
0x180054239  mov     edx, 8Ch
0x18005423e  mov     r9, rbx
0x180054241  mov     r8, r14
0x180054244  call    WPP_SF_S
0x180054249  lea     rax, [rbp+var_40]
0x18005424d  mov     qword ptr [rsp+80h+dwFlagsAndAttributes], r15
0x180054252  lea     rcx, [r13+8]
0x180054256  mov     qword ptr [rsp+80h+dwCreationDisposition], rax
0x18005425b  lea     r9, [rbp+VirtualDiskHandle]
0x18005425f  mov     r8d, 1
0x180054265  mov     rdx, rbx
0x180054268  call    ?AttachVhd@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@PEAPEAXPEAKPEAVCPathString@@@Z; RdVhd::Util::CVhdHelper::AttachVhd(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,void * *,ulong *,CPathString *)
0x18005426d  mov     ebx, eax
0x18005426f  test    eax, eax
0x180054271  jns     loc_180054304
0x180054277  mov     r8d, eax
0x18005427a  mov     ecx, eax
0x18005427c  sar     r8d, 10h
0x180054280  xor     eax, eax
0x180054282  and     ecx, 78000000h
0x180054288  mov     edx, r8d
0x18005428b  and     edx, 7FFh
0x180054291  cmp     ecx, 50000000h
0x180054297  cmovnz  edx, eax
0x18005429a  test    edx, edx
0x18005429c  jnz     short loc_1800542C7
0x18005429e  and     r8d, 1FFFh
0x1800542a5  cmp     r8d, 7
0x1800542a9  jz      short loc_1800542B6
0x1800542ab  test    r8d, r8d
0x1800542ae  jnz     short loc_1800542C3
0x1800542b0  bt      ebx, 1Ch
0x1800542b4  jb      short loc_1800542C3
0x1800542b6  movzx   ebx, bx
0x1800542b9  test    ebx, ebx
0x1800542bb  jz      short loc_1800542C5
0x1800542bd  or      ebx, 0D0730000h
0x1800542c3  test    ebx, ebx
0x1800542c5  jns     short loc_180054304
0x1800542c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800542ce  cmp     rcx, rsi
0x1800542d1  jz      loc_180054587
0x1800542d7  test    byte ptr [rcx+1Ch], 4
0x1800542db  jz      loc_180054587
0x1800542e1  cmp     byte ptr [rcx+19h], 2
0x1800542e5  jb      loc_180054587
0x1800542eb  mov     edx, 8Dh
0x1800542f0  mov     r9d, ebx
0x1800542f3  mov     rcx, [rcx+10h]
0x1800542f7  mov     r8, r14
0x1800542fa  call    WPP_SF_d
0x1800542ff  jmp     loc_180054587
0x180054304  mov     edx, 104h
0x180054309  lea     rcx, [rbp+var_30]
0x18005430d  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x180054312  mov     ebx, eax
0x180054314  test    eax, eax
0x180054316  jns     short loc_180054346
0x180054318  mov     rcx, cs:WPP_GLOBAL_Control
0x18005431f  cmp     rcx, rsi
0x180054322  jz      loc_180054587
0x180054328  test    byte ptr [rcx+1Ch], 4
0x18005432c  jz      loc_180054587
0x180054332  cmp     byte ptr [rcx+19h], 2
0x180054336  jb      loc_180054587
0x18005433c  mov     edx, 8Eh
0x180054341  mov     r9d, eax
0x180054344  jmp     short loc_1800542F3
0x180054346  lea     rcx, [rbp+var_30]
0x18005434a  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x18005434f  add     eax, eax
0x180054351  lea     rcx, [rbp+var_30]
0x180054355  mov     [rbp+DiskPathSizeInBytes], eax
0x180054358  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18005435d  mov     rcx, [rbp+VirtualDiskHandle]; VirtualDiskHandle
0x180054361  lea     rdx, [rbp+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x180054365  mov     r8, rax; DiskPath
0x180054368  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18005436e  mov     ebx, eax
0x180054370  mov     r13d, 0FFFF0000h
0x180054376  test    eax, eax
0x180054378  jz      short loc_1800543CA
0x18005437a  test    r13d, eax
0x18005437d  jnz     short loc_180054398
0x18005437f  test    eax, eax
0x180054381  jle     short loc_18005438C
0x180054383  movzx   ebx, ax
0x180054386  or      ebx, 80070000h
0x18005438c  and     ebx, 0D055FFFFh
0x180054392  or      ebx, 50550000h
0x180054398  test    ebx, ebx
0x18005439a  jns     short loc_1800543CA
0x18005439c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543a3  cmp     rcx, rsi
0x1800543a6  jz      loc_180054587
0x1800543ac  test    byte ptr [rcx+1Ch], 4
0x1800543b0  jz      loc_180054587
0x1800543b6  cmp     byte ptr [rcx+19h], 2
0x1800543ba  jb      loc_180054587
0x1800543c0  mov     edx, 8Fh
0x1800543c5  jmp     loc_1800542F0
0x1800543ca  mov     edx, [rbp+DiskPathSizeInBytes]
0x1800543cd  lea     rcx, [rbp+var_30]
0x1800543d1  shr     edx, 1
0x1800543d3  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x1800543d8  mov     ebx, eax
0x1800543da  test    eax, eax
0x1800543dc  jns     short loc_18005440C
0x1800543de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800543e5  cmp     rcx, rsi
0x1800543e8  jz      loc_180054587
0x1800543ee  test    byte ptr [rcx+1Ch], 4
0x1800543f2  jz      loc_180054587
0x1800543f8  cmp     byte ptr [rcx+19h], 2
0x1800543fc  jb      loc_180054587
0x180054402  mov     edx, 90h
0x180054407  jmp     loc_180054341
0x18005440c  lea     rcx, [rbp+var_30]
0x180054410  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180054415  mov     r8d, 3; dwShareMode
0x18005441b  mov     [rsp+80h+hTemplateFile], 0; hTemplateFile
0x180054424  mov     rcx, rax; lpFileName
0x180054427  mov     [rsp+80h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18005442f  xor     r9d, r9d; lpSecurityAttributes
0x180054432  mov     [rsp+80h+dwCreationDisposition], r8d; dwCreationDisposition
0x180054437  mov     edx, 0C0000000h; dwDesiredAccess
0x18005443c  call    cs:__imp_CreateFileW
0x180054442  mov     r15, rax
0x180054445  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180054449  jnz     short loc_1800544A7
0x18005444b  call    cs:__imp_GetLastError
0x180054451  mov     ebx, eax
0x180054453  test    eax, eax
0x180054455  jz      short loc_180054475
0x180054457  test    r13d, eax
0x18005445a  jnz     short loc_180054475
0x18005445c  test    eax, eax
0x18005445e  jle     short loc_180054469
0x180054460  movzx   ebx, ax
0x180054463  or      ebx, 80070000h
0x180054469  and     ebx, 0D056FFFFh
0x18005446f  or      ebx, 50560000h
0x180054475  test    ebx, ebx
0x180054477  jns     short loc_1800544A7
0x180054479  mov     rcx, cs:WPP_GLOBAL_Control
0x180054480  cmp     rcx, rsi
0x180054483  jz      loc_180054587
0x180054489  test    byte ptr [rcx+1Ch], 4
0x18005448d  jz      loc_180054587
0x180054493  cmp     byte ptr [rcx+19h], 2
0x180054497  jb      loc_180054587
0x18005449d  mov     edx, 91h
0x1800544a2  jmp     loc_1800542F0
0x1800544a7  mov     edx, 4; RandomBufferLength
0x1800544ac  lea     rcx, [rbp+RandomBuffer]; RandomBuffer
0x1800544b0  call    cs:__imp_SystemFunction036
0x1800544b6  test    al, al
0x1800544b8  jnz     short loc_1800544EA
0x1800544ba  mov     ebx, 0D074065Bh
0x1800544bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800544c6  cmp     rcx, rsi
0x1800544c9  jz      loc_180054578
0x1800544cf  test    byte ptr [rcx+1Ch], 4
0x1800544d3  jz      loc_180054578
0x1800544d9  cmp     byte ptr [rcx+19h], 2
0x1800544dd  jb      loc_180054578
0x1800544e3  mov     edx, 92h
0x1800544e8  jmp     short loc_180054569
0x1800544ea  mov     r8d, [rbp+RandomBuffer]; unsigned int
0x1800544ee  mov     rdx, r15; void *
0x1800544f1  call    ?SetDiskSignature@CVhdHelper@Util@RdVhd@@QEBAJPEAXK@Z; RdVhd::Util::CVhdHelper::SetDiskSignature(void *,ulong)
0x1800544f6  mov     ebx, eax
0x1800544f8  test    eax, eax
0x1800544fa  jns     short loc_180054578
0x1800544fc  mov     r8d, eax
0x1800544ff  mov     ecx, eax
0x180054501  sar     r8d, 10h
0x180054505  xor     eax, eax
0x180054507  and     ecx, 78000000h
0x18005450d  mov     edx, r8d
0x180054510  and     edx, 7FFh
0x180054516  cmp     ecx, 50000000h
0x18005451c  cmovnz  edx, eax
0x18005451f  test    edx, edx
0x180054521  jnz     short loc_18005454C
0x180054523  and     r8d, 1FFFh
0x18005452a  cmp     r8d, 7
0x18005452e  jz      short loc_18005453B
0x180054530  test    r8d, r8d
0x180054533  jnz     short loc_180054548
0x180054535  bt      ebx, 1Ch
0x180054539  jb      short loc_180054548
0x18005453b  movzx   ebx, bx
0x18005453e  test    ebx, ebx
0x180054540  jz      short loc_18005454A
0x180054542  or      ebx, 0D0750000h
0x180054548  test    ebx, ebx
0x18005454a  jns     short loc_180054578
0x18005454c  mov     rcx, cs:WPP_GLOBAL_Control
0x180054553  cmp     rcx, rsi
0x180054556  jz      short loc_180054578
0x180054558  test    byte ptr [rcx+1Ch], 4
0x18005455c  jz      short loc_180054578
0x18005455e  cmp     byte ptr [rcx+19h], 2
0x180054562  jb      short loc_180054578
0x180054564  mov     edx, 93h
0x180054569  mov     rcx, [rcx+10h]
0x18005456d  mov     r9d, ebx
0x180054570  mov     r8, r14
0x180054573  call    WPP_SF_d
0x180054578  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18005457c  jz      short loc_180054587
0x18005457e  mov     rcx, r15; hObject
0x180054581  call    cs:__imp_CloseHandle
0x180054587  mov     rcx, [rbp+VirtualDiskHandle]; hObject
0x18005458b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005458f  jz      short loc_180054597
0x180054591  call    cs:__imp_CloseHandle
0x180054597  lea     rcx, [rbp+var_30]; this
0x18005459b  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800545a0  mov     eax, ebx
0x1800545a2  mov     rbx, [rsp+80h+arg_0]
0x1800545aa  add     rsp, 80h
0x1800545b1  pop     r15
0x1800545b3  pop     r14
0x1800545b5  pop     r13
0x1800545b7  pop     rsi
0x1800545b8  pop     rbp
0x1800545b9  retn
```

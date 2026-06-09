# RdVhd::Uvhd::CUvhdDiskManager::IsProfileVhdVolume(ushort const *,ushort const *,int *)

- ea: `0x180053eb0`
- end: `0x180054151`
- name: `?IsProfileVhdVolume@CUvhdDiskManager@Uvhd@RdVhd@@AEBAJPEBG0PEAH@Z`
- size: `673`
- prototype: `int(RdVhd::Uvhd::CUvhdDiskManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800533ac`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18001b461`
- `0x180031204`
- `0x180031448`
- `0x180035db4`
- `0x1800488e4`
- `0x180048b28`
- `0x180053eb0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005411b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005411b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054061`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180054061`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800540e8`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800540e8`

## string_xrefs

- `0x180053f51`: `szVolumePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdDiskManager::IsProfileVhdVolume(
        RdVhd::Uvhd::CUvhdDiskManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // r9
  int v9; // ebx
  const WCHAR *v10; // rax
  __int64 v11; // rdi
  HANDLE FileW; // r15
  DWORD v13; // edi
  void *Buffer; // rax
  const void *v15; // rax
  const int *v17; // [rsp+48h] [rbp-19h] BYREF
  int v18; // [rsp+50h] [rbp-11h]
  __int64 v19; // [rsp+54h] [rbp-Dh]
  int v20; // [rsp+5Ch] [rbp-5h]
  __int64 v21; // [rsp+60h] [rbp-1h]
  int v22; // [rsp+68h] [rbp+7h]
  void **v23; // [rsp+70h] [rbp+Fh] BYREF
  int v24; // [rsp+78h] [rbp+17h]
  __int64 v25; // [rsp+7Ch] [rbp+1Bh]
  int v26; // [rsp+84h] [rbp+23h]
  __int64 v27; // [rsp+88h] [rbp+27h]
  int v28; // [rsp+90h] [rbp+2Fh]
  DWORD NumberOfBytesRead; // [rsp+C8h] [rbp+67h] BYREF
  int v30; // [rsp+CCh] [rbp+6Bh]

  v30 = HIDWORD(this);
  v25 = 128;
  v27 = 0;
  v23 = &CPathString::`vftable';
  v26 = 0;
  v17 = &CBaseStringT<unsigned short>::`vftable';
  v28 = 0x8000000;
  v24 = 0;
  NumberOfBytesRead = 0;
  v19 = 128;
  v21 = 0;
  v20 = 0;
  v22 = 0x8000000;
  v18 = 0;
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 178;
    v8 = L"szVolumePath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v6 + 2), v7, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids, v8);
LABEL_7:
    v9 = -2147024809;
    goto LABEL_35;
  }
  if ( !a3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 179;
    v8 = L"szBindingInfoToMatch";
    goto LABEL_6;
  }
  if ( !a4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 180;
    v8 = L"pfProfileVhdVolume";
    goto LABEL_6;
  }
  *a4 = 0;
  v9 = CPathString::BuildPath((CPathString *)&v23, a2, L"Uvhd-Binding");
  if ( v9 >= 0 )
  {
    v10 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v23);
    v11 = -1;
    FileW = CreateFileW(v10, 0x80000000, 1u, 0, 3u, 0, 0);
    if ( FileW != (HANDLE)-1LL )
    {
      do
        ++v11;
      while ( a3[v11] );
      v9 = CBaseStringT<unsigned short>::EnsureSpace(&v17, (unsigned int)v11);
      if ( v9 >= 0 )
      {
        v13 = 2 * v11;
        Buffer = (void *)CBaseStringT<unsigned short>::GetBuffer(&v17);
        if ( ReadFile(FileW, Buffer, v13, &NumberOfBytesRead, 0) )
        {
          if ( v13 == NumberOfBytesRead )
          {
            v15 = (const void *)CBaseStringT<unsigned short>::GetBuffer(&v17);
            if ( !memcmp_0(v15, a3, v13) )
              *a4 = 1;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          182,
          WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
          (unsigned int)v9);
      }
      CloseHandle(FileW);
    }
  }
  else if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      181,
      WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids,
      (unsigned int)v9);
  }
LABEL_35:
  CPathString::~CPathString((CPathString *)&v17);
  CPathString::~CPathString((CPathString *)&v23);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180053eb0  mov     rax, rsp
0x180053eb3  mov     [rax+10h], rbx
0x180053eb7  mov     [rax+18h], rsi
0x180053ebb  mov     [rax+8], rcx
0x180053ebf  push    rbp
0x180053ec0  push    rdi
0x180053ec1  push    r12
0x180053ec3  push    r14
0x180053ec5  push    r15
0x180053ec7  lea     rbp, [rax-5Fh]
0x180053ecb  sub     rsp, 90h
0x180053ed2  xor     r12d, r12d
0x180053ed5  mov     [rbp+57h+var_3C], 80h
0x180053edd  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180053ee4  mov     [rbp+57h+var_30], r12
0x180053ee8  mov     ecx, 8000000h
0x180053eed  mov     [rbp+57h+var_48], rax
0x180053ef1  lea     rax, ??_7?$CBaseStringT@G@@6B@; const CBaseStringT<ushort>::`vftable'
0x180053ef8  mov     [rbp+57h+var_34], r12d
0x180053efc  mov     [rbp+57h+var_70], rax
0x180053f00  mov     rsi, r9
0x180053f03  mov     r14, r8
0x180053f06  mov     [rbp+57h+var_28], ecx
0x180053f09  mov     [rbp+57h+var_40], r12d
0x180053f0d  mov     [rbp+57h+NumberOfBytesRead], r12d
0x180053f11  mov     [rbp+57h+var_64], 80h
0x180053f19  mov     [rbp+57h+var_58], r12
0x180053f1d  mov     [rbp+57h+var_5C], r12d
0x180053f21  mov     [rbp+57h+var_50], ecx
0x180053f24  mov     [rbp+57h+var_68], r12d
0x180053f28  test    rdx, rdx
0x180053f2b  jnz     short loc_180053F72
0x180053f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f34  lea     rax, WPP_GLOBAL_Control
0x180053f3b  cmp     rcx, rax
0x180053f3e  jz      short loc_180053F68
0x180053f40  test    byte ptr [rcx+1Ch], 4
0x180053f44  jz      short loc_180053F68
0x180053f46  cmp     byte ptr [rcx+19h], 2
0x180053f4a  jb      short loc_180053F68
0x180053f4c  mov     edx, 0B2h
0x180053f51  lea     r9, aSzvolumepath; "szVolumePath"
0x180053f58  mov     rcx, [rcx+10h]
0x180053f5c  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180053f63  call    WPP_SF_S
0x180053f68  mov     ebx, 80070057h
0x180053f6d  jmp     loc_180054121
0x180053f72  test    r14, r14
0x180053f75  jnz     short loc_180053FA4
0x180053f77  mov     rcx, cs:WPP_GLOBAL_Control
0x180053f7e  lea     rax, WPP_GLOBAL_Control
0x180053f85  cmp     rcx, rax
0x180053f88  jz      short loc_180053F68
0x180053f8a  test    byte ptr [rcx+1Ch], 4
0x180053f8e  jz      short loc_180053F68
0x180053f90  cmp     byte ptr [rcx+19h], 2
0x180053f94  jb      short loc_180053F68
0x180053f96  mov     edx, 0B3h
0x180053f9b  lea     r9, aSzbindinginfot; "szBindingInfoToMatch"
0x180053fa2  jmp     short loc_180053F58
0x180053fa4  test    rsi, rsi
0x180053fa7  jnz     short loc_180053FD6
0x180053fa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180053fb0  lea     rax, WPP_GLOBAL_Control
0x180053fb7  cmp     rcx, rax
0x180053fba  jz      short loc_180053F68
0x180053fbc  test    byte ptr [rcx+1Ch], 4
0x180053fc0  jz      short loc_180053F68
0x180053fc2  cmp     byte ptr [rcx+19h], 2
0x180053fc6  jb      short loc_180053F68
0x180053fc8  mov     edx, 0B4h; unsigned __int16 *
0x180053fcd  lea     r9, aPfprofilevhdvo; "pfProfileVhdVolume"
0x180053fd4  jmp     short loc_180053F58
0x180053fd6  lea     r8, aUvhdBinding; "Uvhd-Binding"
0x180053fdd  mov     [r9], r12d
0x180053fe0  lea     rcx, [rbp+57h+var_48]; this
0x180053fe4  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180053fe9  mov     ebx, eax
0x180053feb  test    eax, eax
0x180053fed  jns     short loc_180054037
0x180053fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180053ff6  lea     rax, WPP_GLOBAL_Control
0x180053ffd  cmp     rcx, rax
0x180054000  jz      loc_180054121
0x180054006  test    byte ptr [rcx+1Ch], 4
0x18005400a  jz      loc_180054121
0x180054010  cmp     byte ptr [rcx+19h], 2
0x180054014  jb      loc_180054121
0x18005401a  mov     rcx, [rcx+10h]
0x18005401e  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x180054025  mov     edx, 0B5h
0x18005402a  mov     r9d, ebx
0x18005402d  call    WPP_SF_d
0x180054032  jmp     loc_180054121
0x180054037  lea     rcx, [rbp+57h+var_48]
0x18005403b  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180054040  xor     r9d, r9d; lpSecurityAttributes
0x180054043  mov     [rsp+0B0h+hTemplateFile], r12; hTemplateFile
0x180054048  mov     rcx, rax; lpFileName
0x18005404b  mov     [rsp+0B0h+dwFlagsAndAttributes], r12d; dwFlagsAndAttributes
0x180054050  mov     edx, 80000000h; dwDesiredAccess
0x180054055  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005405d  lea     r8d, [r9+1]; dwShareMode
0x180054061  call    cs:__imp_CreateFileW
0x180054067  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005406b  mov     r15, rax
0x18005406e  cmp     rax, rdi
0x180054071  jz      loc_180054121
0x180054077  inc     rdi
0x18005407a  cmp     [r14+rdi*2], r12w
0x18005407f  jnz     short loc_180054077
0x180054081  mov     edx, edi
0x180054083  lea     rcx, [rbp+57h+var_70]
0x180054087  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18005408c  mov     ebx, eax
0x18005408e  test    eax, eax
0x180054090  jns     short loc_1800540CB
0x180054092  mov     rcx, cs:WPP_GLOBAL_Control
0x180054099  lea     rax, WPP_GLOBAL_Control
0x1800540a0  cmp     rcx, rax
0x1800540a3  jz      short loc_180054118
0x1800540a5  test    byte ptr [rcx+1Ch], 4
0x1800540a9  jz      short loc_180054118
0x1800540ab  cmp     byte ptr [rcx+19h], 2
0x1800540af  jb      short loc_180054118
0x1800540b1  mov     rcx, [rcx+10h]
0x1800540b5  lea     r8, WPP_59ca9d798db93fed5e210ee14600c8f5_Traceguids
0x1800540bc  mov     edx, 0B6h
0x1800540c1  mov     r9d, ebx
0x1800540c4  call    WPP_SF_d
0x1800540c9  jmp     short loc_180054118
0x1800540cb  lea     rcx, [rbp+57h+var_70]
0x1800540cf  add     edi, edi
0x1800540d1  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x1800540d6  mov     rdx, rax; lpBuffer
0x1800540d9  mov     qword ptr [rsp+0B0h+dwCreationDisposition], r12; lpOverlapped
0x1800540de  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800540e2  mov     r8d, edi; nNumberOfBytesToRead
0x1800540e5  mov     rcx, r15; hFile
0x1800540e8  call    cs:__imp_ReadFile
0x1800540ee  test    eax, eax
0x1800540f0  jz      short loc_180054118
0x1800540f2  cmp     edi, [rbp+57h+NumberOfBytesRead]
0x1800540f5  jnz     short loc_180054118
0x1800540f7  lea     rcx, [rbp+57h+var_70]
0x1800540fb  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x180054100  mov     rcx, rax; Buf1
0x180054103  mov     r8d, edi; Size
0x180054106  mov     rdx, r14; Buf2
0x180054109  call    memcmp_0
0x18005410e  test    eax, eax
0x180054110  jnz     short loc_180054118
0x180054112  mov     dword ptr [rsi], 1
0x180054118  mov     rcx, r15; hObject
0x18005411b  call    cs:__imp_CloseHandle
0x180054121  lea     rcx, [rbp+57h+var_70]; this
0x180054125  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18005412a  lea     rcx, [rbp+57h+var_48]; this
0x18005412e  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180054133  lea     r11, [rsp+0B0h+var_20]
0x18005413b  mov     eax, ebx
0x18005413d  mov     rbx, [r11+38h]
0x180054141  mov     rsi, [r11+40h]
0x180054145  mov     rsp, r11
0x180054148  pop     r15
0x18005414a  pop     r14
0x18005414c  pop     r12
0x18005414e  pop     rdi
0x18005414f  pop     rbp
0x180054150  retn
```

# RdVhd::Util::CVhdHelper::IsVolumeOnDisk(ushort const *,ulong,int *)

- ea: `0x18004a2ec`
- end: `0x18004a570`
- name: `?IsVolumeOnDisk@CVhdHelper@Util@RdVhd@@IEBAJPEBGKPEAH@Z`
- size: `644`
- prototype: `__int64 __fastcall(RdVhd::Util::CVhdHelper *__hidden this, const unsigned __int16 *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800491b0`
- `0x180049574`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x18001a880`
- `0x18001a8d0`
- `0x18003114c`
- `0x180037110`
- `0x1800488e4`
- `0x180048b28`
- `0x18004a2ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a493`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a54a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a54a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a484`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004a484`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004a51b`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004a51b`

## string_xrefs

- `0x18004a366`: `szVolumePath`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::IsVolumeOnDisk(
        RdVhd::Util::CVhdHelper *this,
        const unsigned __int16 *a2,
        int a3,
        int *a4)
{
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  const wchar_t *v8; // r9
  signed int v9; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  _DWORD *v15; // r14
  __int64 i; // rdx
  void **v18; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+48h] [rbp-30h]
  __int64 v20; // [rsp+4Ch] [rbp-2Ch]
  int v21; // [rsp+54h] [rbp-24h]
  __int64 v22; // [rsp+58h] [rbp-20h]
  int v23; // [rsp+60h] [rbp-18h]
  DWORD BytesReturned; // [rsp+B0h] [rbp+38h] BYREF
  int v25; // [rsp+B4h] [rbp+3Ch]

  v25 = HIDWORD(this);
  v20 = 128;
  v18 = &CPathString::`vftable';
  v22 = 0;
  v21 = 0;
  v23 = 0x8000000;
  v19 = 0;
  BytesReturned = 0;
  if ( !a2 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 100;
    v8 = L"szVolumePath";
LABEL_6:
    WPP_SF_S(*((_QWORD *)v6 + 2), v7, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v8);
LABEL_7:
    v9 = -2147024809;
    goto LABEL_41;
  }
  if ( !a4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    v7 = 101;
    v8 = L"fVolumeIsOnDisk";
    goto LABEL_6;
  }
  *a4 = 0;
  v9 = CBaseStringT<unsigned short>::Append(&v18, a2);
  if ( v9 >= 0 )
  {
    v9 = CPathString::TrimBackslash((CPathString *)&v18);
    if ( v9 >= 0 )
    {
      v12 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v18);
      FileW = CreateFileW(v12, 0, 1u, 0, 3u, 0, 0);
      if ( FileW != (HANDLE)-1LL )
        goto LABEL_32;
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      if ( v9 < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = 104;
          goto LABEL_18;
        }
      }
      else
      {
LABEL_32:
        v15 = operator new(0x2800u);
        if ( DeviceIoControl(FileW, 0x560000u, 0, 0, v15, 0x2800u, &BytesReturned, 0) )
        {
          for ( i = 0; (unsigned int)i < *v15; i = (unsigned int)(i + 1) )
          {
            if ( v15[6 * i + 2] == a3 )
            {
              *a4 = 1;
              break;
            }
          }
        }
        if ( FileW != (HANDLE)-1LL )
          CloseHandle(FileW);
        operator delete(v15);
      }
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 103;
        goto LABEL_18;
      }
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = 102;
LABEL_18:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, (unsigned int)v9);
    }
  }
LABEL_41:
  CPathString::~CPathString((CPathString *)&v18);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a2ec  mov     qword ptr [rsp-30h+BytesReturned], rcx
0x18004a2f1  push    rbp
0x18004a2f2  push    rbx
0x18004a2f3  push    rsi
0x18004a2f4  push    rdi
0x18004a2f5  push    r14
0x18004a2f7  push    r15
0x18004a2f9  mov     rbp, rsp
0x18004a2fc  sub     rsp, 78h
0x18004a300  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004a307  mov     [rbp+var_2C], 80h
0x18004a30f  mov     [rbp+var_38], rax
0x18004a313  mov     rdi, r9
0x18004a316  mov     r15d, r8d
0x18004a319  mov     [rbp+var_20], 0
0x18004a321  mov     [rbp+var_24], 0
0x18004a328  mov     [rbp+var_18], 8000000h
0x18004a32f  mov     [rbp+var_30], 0
0x18004a336  mov     [rbp+BytesReturned], 0
0x18004a33d  test    rdx, rdx
0x18004a340  jnz     short loc_18004A387
0x18004a342  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a349  lea     rax, WPP_GLOBAL_Control
0x18004a350  cmp     rcx, rax
0x18004a353  jz      short loc_18004A37D
0x18004a355  test    byte ptr [rcx+1Ch], 1
0x18004a359  jz      short loc_18004A37D
0x18004a35b  cmp     byte ptr [rcx+19h], 2
0x18004a35f  jb      short loc_18004A37D
0x18004a361  mov     edx, 64h ; 'd'
0x18004a366  lea     r9, aSzvolumepath; "szVolumePath"
0x18004a36d  mov     rcx, [rcx+10h]
0x18004a371  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004a378  call    WPP_SF_S
0x18004a37d  mov     ebx, 80070057h
0x18004a382  jmp     loc_18004A558
0x18004a387  test    rdi, rdi
0x18004a38a  jnz     short loc_18004A3B7
0x18004a38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a393  lea     rax, WPP_GLOBAL_Control
0x18004a39a  cmp     rcx, rax
0x18004a39d  jz      short loc_18004A37D
0x18004a39f  test    byte ptr [rcx+1Ch], 1
0x18004a3a3  jz      short loc_18004A37D
0x18004a3a5  cmp     byte ptr [rcx+19h], 2
0x18004a3a9  jb      short loc_18004A37D
0x18004a3ab  lea     edx, [rdi+65h]
0x18004a3ae  lea     r9, aFvolumeisondis; "fVolumeIsOnDisk"
0x18004a3b5  jmp     short loc_18004A36D
0x18004a3b7  lea     rcx, [rbp+var_38]
0x18004a3bb  mov     dword ptr [r9], 0
0x18004a3c2  call    ?Append@?$CBaseStringT@G@@QEAAJPEBG@Z; CBaseStringT<ushort>::Append(ushort const *)
0x18004a3c7  mov     ebx, eax
0x18004a3c9  test    eax, eax
0x18004a3cb  jns     short loc_18004A415
0x18004a3cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a3d4  lea     rax, WPP_GLOBAL_Control
0x18004a3db  cmp     rcx, rax
0x18004a3de  jz      loc_18004A558
0x18004a3e4  test    byte ptr [rcx+1Ch], 1
0x18004a3e8  jz      loc_18004A558
0x18004a3ee  cmp     byte ptr [rcx+19h], 2
0x18004a3f2  jb      loc_18004A558
0x18004a3f8  mov     edx, 66h ; 'f'
0x18004a3fd  mov     rcx, [rcx+10h]
0x18004a401  lea     r8, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004a408  mov     r9d, ebx
0x18004a40b  call    WPP_SF_d
0x18004a410  jmp     loc_18004A558
0x18004a415  lea     rcx, [rbp+var_38]; this
0x18004a419  call    ?TrimBackslash@CPathString@@QEAAJXZ; CPathString::TrimBackslash(void)
0x18004a41e  mov     ebx, eax
0x18004a420  test    eax, eax
0x18004a422  jns     short loc_18004A456
0x18004a424  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a42b  lea     rax, WPP_GLOBAL_Control
0x18004a432  cmp     rcx, rax
0x18004a435  jz      loc_18004A558
0x18004a43b  test    byte ptr [rcx+1Ch], 1
0x18004a43f  jz      loc_18004A558
0x18004a445  cmp     byte ptr [rcx+19h], 2
0x18004a449  jb      loc_18004A558
0x18004a44f  mov     edx, 67h ; 'g'
0x18004a454  jmp     short loc_18004A3FD
0x18004a456  lea     rcx, [rbp+var_38]
0x18004a45a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004a45f  xor     r9d, r9d; lpSecurityAttributes
0x18004a462  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18004a46b  mov     rcx, rax; lpFileName
0x18004a46e  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004a476  xor     edx, edx; dwDesiredAccess
0x18004a478  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18004a480  lea     r8d, [r9+1]; dwShareMode
0x18004a484  call    cs:__imp_CreateFileW
0x18004a48a  mov     rsi, rax
0x18004a48d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004a491  jnz     short loc_18004A4E1
0x18004a493  call    cs:__imp_GetLastError
0x18004a499  mov     ebx, eax
0x18004a49b  test    eax, eax
0x18004a49d  jle     short loc_18004A4A8
0x18004a49f  movzx   ebx, ax
0x18004a4a2  or      ebx, 80070000h
0x18004a4a8  test    ebx, ebx
0x18004a4aa  jns     short loc_18004A4E1
0x18004a4ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a4b3  lea     rax, WPP_GLOBAL_Control
0x18004a4ba  cmp     rcx, rax
0x18004a4bd  jz      loc_18004A558
0x18004a4c3  test    byte ptr [rcx+1Ch], 1
0x18004a4c7  jz      loc_18004A558
0x18004a4cd  cmp     byte ptr [rcx+19h], 2
0x18004a4d1  jb      loc_18004A558
0x18004a4d7  mov     edx, 68h ; 'h'
0x18004a4dc  jmp     loc_18004A3FD
0x18004a4e1  mov     ecx, 2800h; Size
0x18004a4e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004a4eb  mov     r14, rax
0x18004a4ee  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18004a4f7  lea     rax, [rbp+BytesReturned]
0x18004a4fb  xor     r9d, r9d; nInBufferSize
0x18004a4fe  mov     [rsp+78h+hTemplateFile], rax; lpBytesReturned
0x18004a503  xor     r8d, r8d; lpInBuffer
0x18004a506  mov     [rsp+78h+dwFlagsAndAttributes], 2800h; nOutBufferSize
0x18004a50e  mov     edx, 560000h; dwIoControlCode
0x18004a513  mov     rcx, rsi; hDevice
0x18004a516  mov     qword ptr [rsp+78h+dwCreationDisposition], r14; lpOutBuffer
0x18004a51b  call    cs:__imp_DeviceIoControl
0x18004a521  test    eax, eax
0x18004a523  jz      short loc_18004A541
0x18004a525  xor     edx, edx
0x18004a527  cmp     edx, [r14]
0x18004a52a  jnb     short loc_18004A541
0x18004a52c  lea     rcx, [rdx+rdx*2]
0x18004a530  cmp     [r14+rcx*8+8], r15d
0x18004a535  jz      short loc_18004A53B
0x18004a537  inc     edx
0x18004a539  jmp     short loc_18004A527
0x18004a53b  mov     dword ptr [rdi], 1
0x18004a541  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004a545  jz      short loc_18004A550
0x18004a547  mov     rcx, rsi; hObject
0x18004a54a  call    cs:__imp_CloseHandle
0x18004a550  mov     rcx, r14; Block
0x18004a553  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004a558  lea     rcx, [rbp+var_38]; this
0x18004a55c  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004a561  mov     eax, ebx
0x18004a563  add     rsp, 78h
0x18004a567  pop     r15
0x18004a569  pop     r14
0x18004a56b  pop     rdi
0x18004a56c  pop     rsi
0x18004a56d  pop     rbx
0x18004a56e  pop     rbp
0x18004a56f  retn
```

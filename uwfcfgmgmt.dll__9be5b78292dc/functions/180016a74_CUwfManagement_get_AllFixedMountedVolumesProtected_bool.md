# CUwfManagement::get_AllFixedMountedVolumesProtected(bool *)

- ea: `0x180016a74`
- end: `0x180016c72`
- name: `?get_AllFixedMountedVolumesProtected@CUwfManagement@@AEAAJPEA_N@Z`
- size: `510`
- prototype: `__int64 __fastcall(CUwfManagement *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180017230`

## callees

- `0x180002468`
- `0x18000e660`
- `0x180013100`
- `0x1800139f0`
- `0x1800147d0`
- `0x180016a74`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016ac3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016c1d`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180016c05`
- `api-ms-win-core-file-l1-1-0!FindNextVolumeW` at `0x180016c05`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180016ab4`
- `api-ms-win-core-file-l1-1-0!FindFirstVolumeW` at `0x180016ab4`

## pseudocode

```c
__int64 __fastcall CUwfManagement::get_AllFixedMountedVolumesProtected(CUwfManagement *this, bool *a2)
{
  HANDLE FirstVolumeW; // r12
  signed int v4; // eax
  int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  bool v9; // di
  bool v10; // si
  signed int LastError; // eax
  bool v13; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v14[2]; // [rsp+48h] [rbp-B8h] BYREF
  char v15; // [rsp+58h] [rbp-A8h]
  __int128 v16; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szVolumeName[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[308]; // [rsp+78h] [rbp-88h] BYREF

  *a2 = 0;
  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x136u);
  if ( FirstVolumeW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      v7 = -1;
      do
        ++v7;
      while ( szVolumeName[v7] );
      v8 = 2 * v7 - 2;
      if ( v8 >= 0x26C )
        _report_rangecheckfailure();
      *(WCHAR *)((char *)szVolumeName + v8) = 0;
      v13 = 0;
      v5 = CanVolumeBeProtected(v18, 1, &v13);
      if ( v5 < 0 )
        return (unsigned int)v5;
      if ( v13 )
        break;
LABEL_23:
      if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x136u) )
      {
        LastError = GetLastError();
        if ( LastError == 18 )
        {
          *a2 = 1;
          return (unsigned int)v5;
        }
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        else
          v5 = LastError;
        v6 = -2147467259;
        goto LABEL_5;
      }
    }
    v14[0] = &CDevice::`vftable';
    v14[1] = -1;
    v15 = 0;
    v16 = 0;
    v9 = 1;
    v5 = CDevice::Initialize((CDevice *)v14, szVolumeName);
    if ( v5 >= 0 )
    {
      v5 = CDevice::SendIOCTL((CDevice *)v14, 0x22496Cu, 0, 0, &v16, 0x10u, 0);
      if ( v5 < 0 )
      {
        v9 = 0;
LABEL_17:
        v5 = 0;
        goto LABEL_19;
      }
      if ( !BYTE12(v16) )
        goto LABEL_17;
      v9 = (_DWORD)v16 == 2;
    }
LABEL_19:
    v10 = 0;
    v14[0] = &CDevice::`vftable';
    if ( v5 >= 0 )
      v10 = v9;
    CDevice::Close((CDevice *)v14);
    if ( v5 < 0 || !v10 )
      return (unsigned int)v5;
    goto LABEL_23;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v6 = -2147024890;
LABEL_5:
  if ( v5 >= 0 )
    return v6;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180016a74  push    rbp
0x180016a76  push    rbx
0x180016a77  push    rsi
0x180016a78  push    rdi
0x180016a79  push    r12
0x180016a7b  push    r13
0x180016a7d  push    r14
0x180016a7f  push    r15
0x180016a81  lea     rbp, [rsp-1F8h]
0x180016a89  sub     rsp, 2F8h
0x180016a90  mov     rax, cs:__security_cookie
0x180016a97  xor     rax, rsp
0x180016a9a  mov     [rbp+230h+var_50], rax
0x180016aa1  mov     r15, rdx
0x180016aa4  lea     rcx, [rsp+330h+szVolumeName]; lpszVolumeName
0x180016aa9  xor     r13d, r13d
0x180016aac  mov     [rdx], r13b
0x180016aaf  mov     edx, 136h; cchBufferLength
0x180016ab4  call    cs:__imp_FindFirstVolumeW
0x180016aba  mov     r12, rax
0x180016abd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016ac1  jnz     short loc_180016AE7
0x180016ac3  call    cs:__imp_GetLastError
0x180016ac9  mov     ebx, eax
0x180016acb  test    eax, eax
0x180016acd  jle     short loc_180016AD8
0x180016acf  movzx   ebx, ax
0x180016ad2  or      ebx, 80070000h
0x180016ad8  mov     eax, 80070006h
0x180016add  test    ebx, ebx
0x180016adf  cmovns  ebx, eax
0x180016ae2  jmp     loc_180016C47
0x180016ae7  mov     r14d, 1
0x180016aed  lea     rdi, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180016af4  lea     rcx, [rsp+330h+szVolumeName]
0x180016af9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016afd  inc     rax
0x180016b00  cmp     [rcx+rax*2], r13w
0x180016b05  jnz     short loc_180016AFD
0x180016b07  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x180016b0f  cmp     rcx, 26Ch
0x180016b16  jnb     loc_180016C6C
0x180016b1c  mov     [rsp+rcx+330h+szVolumeName], r13w
0x180016b22  lea     r8, [rsp+330h+var_2F0]; bool *
0x180016b27  lea     rcx, [rsp+330h+var_2B8]; unsigned __int16 *
0x180016b2c  mov     [rsp+330h+var_2F0], r13b
0x180016b31  mov     dl, 1; bool
0x180016b33  call    ?CanVolumeBeProtected@@YAJPEBG_NPEA_N@Z; CanVolumeBeProtected(ushort const *,bool,bool *)
0x180016b38  mov     ebx, eax
0x180016b3a  test    eax, eax
0x180016b3c  js      loc_180016C47
0x180016b42  cmp     [rsp+330h+var_2F0], r13b
0x180016b47  jz      loc_180016BF7
0x180016b4d  xorps   xmm0, xmm0
0x180016b50  mov     [rsp+330h+var_2E8], rdi
0x180016b55  lea     rdx, [rsp+330h+szVolumeName]; lpFileName
0x180016b5a  mov     [rsp+330h+var_2E0], 0FFFFFFFFFFFFFFFFh
0x180016b63  lea     rcx, [rsp+330h+var_2E8]; this
0x180016b68  mov     [rsp+330h+var_2D8], r13b
0x180016b6d  movups  [rsp+330h+var_2D0], xmm0
0x180016b72  mov     dil, 1
0x180016b75  call    ?Initialize@CDevice@@QEAAJPEBG@Z; CDevice::Initialize(ushort const *)
0x180016b7a  mov     ebx, eax
0x180016b7c  test    eax, eax
0x180016b7e  js      short loc_180016BCC
0x180016b80  mov     [rsp+330h+var_300], r13; unsigned int *
0x180016b85  lea     rax, [rsp+330h+var_2D0]
0x180016b8a  mov     [rsp+330h+var_308], 10h; DWORD
0x180016b92  lea     rcx, [rsp+330h+var_2E8]; this
0x180016b97  xor     r9d, r9d; unsigned int
0x180016b9a  mov     [rsp+330h+var_310], rax; void *
0x180016b9f  xor     r8d, r8d; void *
0x180016ba2  mov     edx, 22496Ch; unsigned int
0x180016ba7  call    ?SendIOCTL@CDevice@@QEAAJKPEAXK0KPEAK@Z; CDevice::SendIOCTL(ulong,void *,ulong,void *,ulong,ulong *)
0x180016bac  mov     ebx, eax
0x180016bae  test    eax, eax
0x180016bb0  jns     short loc_180016BB7
0x180016bb2  mov     dil, r13b
0x180016bb5  jmp     short loc_180016BBE
0x180016bb7  cmp     byte ptr [rsp+330h+var_2D0+0Ch], r13b
0x180016bbc  jnz     short loc_180016BC3
0x180016bbe  mov     ebx, r13d
0x180016bc1  jmp     short loc_180016BCC
0x180016bc3  cmp     dword ptr [rsp+330h+var_2D0], 2
0x180016bc8  setz    dil
0x180016bcc  movzx   eax, dil
0x180016bd0  lea     rcx, [rsp+330h+var_2E8]; this
0x180016bd5  test    ebx, ebx
0x180016bd7  lea     rdi, ??_7CDevice@@6B@; const CDevice::`vftable'
0x180016bde  mov     esi, r13d
0x180016be1  mov     [rsp+330h+var_2E8], rdi
0x180016be6  cmovns  esi, eax
0x180016be9  call    ?Close@CDevice@@QEAAXXZ; CDevice::Close(void)
0x180016bee  test    ebx, ebx
0x180016bf0  js      short loc_180016C47
0x180016bf2  test    sil, sil
0x180016bf5  jz      short loc_180016C18
0x180016bf7  mov     r8d, 136h; cchBufferLength
0x180016bfd  lea     rdx, [rsp+330h+szVolumeName]; lpszVolumeName
0x180016c02  mov     rcx, r12; hFindVolume
0x180016c05  call    cs:__imp_FindNextVolumeW
0x180016c0b  mov     r14d, eax
0x180016c0e  test    eax, eax
0x180016c10  jnz     loc_180016AF4
0x180016c16  jmp     short loc_180016C1D
0x180016c18  test    r14d, r14d
0x180016c1b  jnz     short loc_180016C47
0x180016c1d  call    cs:__imp_GetLastError
0x180016c23  cmp     eax, 12h
0x180016c26  jz      short loc_180016C43
0x180016c28  test    eax, eax
0x180016c2a  jg      short loc_180016C30
0x180016c2c  mov     ebx, eax
0x180016c2e  jmp     short loc_180016C39
0x180016c30  movzx   ebx, ax
0x180016c33  or      ebx, 80070000h
0x180016c39  mov     eax, 80004005h
0x180016c3e  jmp     loc_180016ADD
0x180016c43  mov     byte ptr [r15], 1
0x180016c47  mov     eax, ebx
0x180016c49  mov     rcx, [rbp+230h+var_50]
0x180016c50  xor     rcx, rsp; StackCookie
0x180016c53  call    __security_check_cookie
0x180016c58  add     rsp, 2F8h
0x180016c5f  pop     r15
0x180016c61  pop     r14
0x180016c63  pop     r13
0x180016c65  pop     r12
0x180016c67  pop     rdi
0x180016c68  pop     rsi
0x180016c69  pop     rbx
0x180016c6a  pop     rbp
0x180016c6b  retn
0x180016c6c  call    __report_rangecheckfailure
```

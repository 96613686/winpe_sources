# GetFileSystemType(ushort const *,eFileSystemType *)

- ea: `0x180019ef0`
- end: `0x18001a12e`
- name: `?GetFileSystemType@@YAXPEBGPEAW4eFileSystemType@@@Z`
- size: `574`
- prototype: `void __fastcall(const unsigned __int16 *Src, enum eFileSystemType *)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180019dec`
- `0x18003cc10`
- `0x180040944`

## callees

- `0x180019ef0`
- `0x18001a404`
- `0x18003a580`
- `0x18003af10`
- `0x18003af34`
- `0x18003b7d8`
- `0x18003b9ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a09f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a067`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a09f`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180019f62`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180019f62`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180019faf`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180019faf`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180019fc2`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180019fc2`

## pseudocode

```c
void __fastcall GetFileSystemType(WCHAR *Src, enum eFileSystemType *a2)
{
  UINT DriveTypeW; // eax
  int v5; // eax
  _QWORD *v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // eax
  __int64 v9; // rdx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh]
  WCHAR szVolumePathName[264]; // [rsp+50h] [rbp-B0h] BYREF

  FileSystemFlags = 0;
  memset_0(szVolumePathName, 0, 0x20Au);
  v11 = 0;
  if ( !(unsigned __int8)IsCreateDirectoryTransactedWPresent() )
    goto LABEL_13;
  if ( !GetVolumePathNameW(Src, szVolumePathName, 0x105u)
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, LastError);
  }
  if ( !GetVolumeInformationW(szVolumePathName, 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v8 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, v8);
    }
    FileSystemFlags = 0x200000;
  }
  DriveTypeW = GetDriveTypeW(szVolumePathName);
  if ( (FileSystemFlags & 0x200000) == 0 || DriveTypeW == 4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_13;
    v9 = 19;
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, szVolumePathName);
  v5 = IsEfsDirectory(Src);
  if ( v5 || v11 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_13;
    v9 = 18;
LABEL_26:
    WPP_SF_S(v6[2], v9, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids, szVolumePathName);
LABEL_13:
    v5 = 1;
  }
  *(_DWORD *)a2 = v5;
}

```

## disassembly

```asm
0x180019ef0  mov     [rsp-8+arg_10], rbx
0x180019ef5  mov     [rsp-8+arg_18], rdi
0x180019efa  push    rbp
0x180019efb  push    r14
0x180019efd  push    r15
0x180019eff  lea     rbp, [rsp-170h]
0x180019f07  sub     rsp, 270h
0x180019f0e  mov     rax, cs:__security_cookie
0x180019f15  xor     rax, rsp
0x180019f18  mov     [rbp+180h+var_20], rax
0x180019f1f  mov     rdi, rdx
0x180019f22  mov     [rsp+280h+FileSystemFlags], 0
0x180019f2a  mov     rbx, rcx
0x180019f2d  xor     edx, edx; Val
0x180019f2f  lea     rcx, [rsp+280h+szVolumePathName]; void *
0x180019f34  mov     r8d, 20Ah; Size
0x180019f3a  call    memset_0
0x180019f3f  mov     [rsp+280h+var_23C], 0
0x180019f47  call    IsCreateDirectoryTransactedWPresent
0x180019f4c  test    al, al
0x180019f4e  jz      loc_18001A046
0x180019f54  mov     r8d, 105h; cchBufferLength
0x180019f5a  lea     rdx, [rsp+280h+szVolumePathName]; lpszVolumePathName
0x180019f5f  mov     rcx, rbx; lpszFileName
0x180019f62  call    cs:__imp_GetVolumePathNameW
0x180019f68  lea     r15, WPP_e65014c76418321bb93a76a498c7a7da_Traceguids
0x180019f6f  lea     r14, WPP_GLOBAL_Control
0x180019f76  test    eax, eax
0x180019f78  jz      loc_18001A04D
0x180019f7e  mov     [rsp+280h+nFileSystemNameSize], 0; nFileSystemNameSize
0x180019f86  lea     rax, [rsp+280h+FileSystemFlags]
0x180019f8b  mov     [rsp+280h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x180019f94  lea     rcx, [rsp+280h+szVolumePathName]; lpRootPathName
0x180019f99  mov     [rsp+280h+lpFileSystemFlags], rax; lpFileSystemFlags
0x180019f9e  xor     r9d, r9d; lpVolumeSerialNumber
0x180019fa1  xor     r8d, r8d; nVolumeNameSize
0x180019fa4  mov     [rsp+280h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x180019fad  xor     edx, edx; lpVolumeNameBuffer
0x180019faf  call    cs:__imp_GetVolumeInformationW
0x180019fb5  test    eax, eax
0x180019fb7  jz      loc_18001A08D
0x180019fbd  lea     rcx, [rsp+280h+szVolumePathName]; lpRootPathName
0x180019fc2  call    cs:__imp_GetDriveTypeW
0x180019fc8  test    [rsp+280h+FileSystemFlags], 200000h
0x180019fd0  jz      short loc_18001A036
0x180019fd2  cmp     eax, 4
0x180019fd5  jz      short loc_18001A036
0x180019fd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180019fde  cmp     rcx, r14
0x180019fe1  jz      short loc_180019FED
0x180019fe3  test    byte ptr [rcx+1Ch], 8
0x180019fe7  jnz     loc_18001A0CD
0x180019fed  lea     rdx, [rsp+280h+var_23C]
0x180019ff2  mov     rcx, rbx; Src
0x180019ff5  call    IsEfsDirectory
0x180019ffa  test    eax, eax
0x180019ffc  jnz     loc_18001A0E8
0x18001a002  cmp     [rsp+280h+var_23C], eax
0x18001a006  jnz     loc_18001A0E8
0x18001a00c  mov     [rdi], eax
0x18001a00e  mov     rcx, [rbp+180h+var_20]
0x18001a015  xor     rcx, rsp; StackCookie
0x18001a018  call    __security_check_cookie
0x18001a01d  lea     r11, [rsp+280h+var_10]
0x18001a025  mov     rbx, [r11+30h]
0x18001a029  mov     rdi, [r11+38h]
0x18001a02d  mov     rsp, r11
0x18001a030  pop     r15
0x18001a032  pop     r14
0x18001a034  pop     rbp
0x18001a035  retn
0x18001a036  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a03d  cmp     rcx, r14
0x18001a040  jnz     loc_18001A109
0x18001a046  mov     eax, 1
0x18001a04b  jmp     short loc_18001A00C
0x18001a04d  mov     rax, cs:WPP_GLOBAL_Control
0x18001a054  cmp     rax, r14
0x18001a057  jz      loc_180019F7E
0x18001a05d  test    byte ptr [rax+1Ch], 4
0x18001a061  jz      loc_180019F7E
0x18001a067  call    cs:__imp_GetLastError
0x18001a06d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a074  mov     edx, 0Fh
0x18001a079  mov     r9d, eax
0x18001a07c  mov     r8, r15
0x18001a07f  mov     rcx, [rcx+10h]
0x18001a083  call    WPP_SF_d
0x18001a088  jmp     loc_180019F7E
0x18001a08d  mov     rax, cs:WPP_GLOBAL_Control
0x18001a094  cmp     rax, r14
0x18001a097  jz      short loc_18001A0C0
0x18001a099  test    byte ptr [rax+1Ch], 4
0x18001a09d  jz      short loc_18001A0C0
0x18001a09f  call    cs:__imp_GetLastError
0x18001a0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ac  mov     edx, 10h
0x18001a0b1  mov     r9d, eax
0x18001a0b4  mov     r8, r15
0x18001a0b7  mov     rcx, [rcx+10h]
0x18001a0bb  call    WPP_SF_d
0x18001a0c0  mov     [rsp+280h+FileSystemFlags], 200000h
0x18001a0c8  jmp     loc_180019FBD
0x18001a0cd  mov     rcx, [rcx+10h]
0x18001a0d1  lea     r9, [rsp+280h+szVolumePathName]
0x18001a0d6  mov     edx, 11h
0x18001a0db  mov     r8, r15
0x18001a0de  call    WPP_SF_S
0x18001a0e3  jmp     loc_180019FED
0x18001a0e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0ef  cmp     rcx, r14
0x18001a0f2  jz      loc_18001A046
0x18001a0f8  test    byte ptr [rcx+1Ch], 8
0x18001a0fc  jz      loc_18001A046
0x18001a102  mov     edx, 12h
0x18001a107  jmp     short loc_18001A118
0x18001a109  test    byte ptr [rcx+1Ch], 8
0x18001a10d  jz      loc_18001A046
0x18001a113  mov     edx, 13h
0x18001a118  mov     rcx, [rcx+10h]
0x18001a11c  lea     r9, [rsp+280h+szVolumePathName]
0x18001a121  mov     r8, r15
0x18001a124  call    WPP_SF_S
0x18001a129  jmp     loc_18001A046
```

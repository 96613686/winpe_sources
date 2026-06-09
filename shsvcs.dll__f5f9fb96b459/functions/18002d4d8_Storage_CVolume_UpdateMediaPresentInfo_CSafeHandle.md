# Storage::CVolume::_UpdateMediaPresentInfo(CSafeHandle *)

- ea: `0x18002d4d8`
- end: `0x18002d5d9`
- name: `?_UpdateMediaPresentInfo@CVolume@Storage@@AEAAJPEAVCSafeHandle@@@Z`
- size: `257`
- prototype: `int __fastcall(Storage::CVolume *this, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update`

## callers

- `0x180008230`

## callees

- `0x1800166e0`
- `0x180019574`
- `0x18002c878`
- `0x18002ce28`
- `0x18002d4d8`
- `0x18002d66c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d586`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d586`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d536`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002d536`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18002d529`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18002d529`

## pseudocode

```c
int __fastcall Storage::CVolume::_UpdateMediaPresentInfo(Storage::CVolume *this, void **a2)
{
  WCHAR *v3; // rdi
  DWORD FileAttributesW; // eax
  int result; // eax
  DWORD LastError; // ecx
  unsigned __int16 *v8; // r8
  unsigned int v9; // r9d

  v3 = (WCHAR *)((char *)this + 110);
  if ( GetVolumeInformationW(
         (LPCWSTR)this + 55,
         (LPWSTR)this + 105,
         0x21u,
         (LPDWORD)this + 18,
         (LPDWORD)this + 19,
         (LPDWORD)this + 20,
         (LPWSTR)this + 138,
         0x1Eu) )
  {
    FileAttributesW = GetFileAttributesW(v3);
    *((_DWORD *)this + 17) = FileAttributesW;
    if ( FileAttributesW == -1 )
    {
      Storage::CVolume::_HandleAccessDenied(this);
    }
    else
    {
      result = Storage::CVolume::_UpdateSpecialFilePresence(this);
      if ( result < 0 )
        goto LABEL_11;
      if ( *((_DWORD *)this + 13) == 16 )
        result = Storage::CVolume::_UpdateTrackInfo(this, *a2);
      if ( (*((_BYTE *)this + 44) & 1) == 0 )
        goto LABEL_11;
      result = Storage::CVolume::_ExtractAutorunIconAndLabel(this);
      if ( result >= 0 )
        goto LABEL_11;
    }
    result = 1;
LABEL_11:
    *((_DWORD *)this + 9) |= 0x20000000u;
    return result;
  }
  LastError = GetLastError();
  if ( LastError == 21 )
  {
    *((_DWORD *)this + 12) |= 4u;
  }
  else
  {
    *((_WORD *)this + 46) = 0;
    if ( LastError == 87 || LastError == 1005 )
      Storage::_GetIsUnsupportedFileSystem((Storage *)v3, (LPWSTR)this + 46, v8, v9);
    Storage::CVolume::_HandleAccessDenied(this);
    *((_DWORD *)this + 9) &= ~0x20000000u;
  }
  return 1;
}

```

## disassembly

```asm
0x18002d4d8  mov     r11, rsp
0x18002d4db  mov     [r11+8], rbx
0x18002d4df  mov     [r11+10h], rsi
0x18002d4e3  push    rdi
0x18002d4e4  sub     rsp, 40h
0x18002d4e8  lea     r8, [rcx+50h]
0x18002d4ec  mov     [rsp+48h+nFileSystemNameSize], 1Eh; nFileSystemNameSize
0x18002d4f4  lea     rax, [rcx+114h]
0x18002d4fb  mov     rsi, rdx
0x18002d4fe  mov     [r11-18h], rax
0x18002d502  lea     r10, [rcx+4Ch]
0x18002d506  mov     [r11-20h], r8
0x18002d50a  lea     rdi, [rcx+6Eh]
0x18002d50e  mov     rbx, rcx
0x18002d511  mov     [r11-28h], r10
0x18002d515  lea     r9, [rcx+48h]; lpVolumeSerialNumber
0x18002d519  mov     r8d, 21h ; '!'; nVolumeNameSize
0x18002d51f  lea     rdx, [rcx+0D2h]; lpVolumeNameBuffer
0x18002d526  mov     rcx, rdi; lpRootPathName
0x18002d529  call    cs:__imp_GetVolumeInformationW
0x18002d52f  test    eax, eax
0x18002d531  jz      short loc_18002D586
0x18002d533  mov     rcx, rdi; lpFileName
0x18002d536  call    cs:__imp_GetFileAttributesW
0x18002d53c  mov     [rbx+44h], eax
0x18002d53f  mov     rcx, rbx; this
0x18002d542  cmp     eax, 0FFFFFFFFh
0x18002d545  jz      short loc_18002D575
0x18002d547  call    ?_UpdateSpecialFilePresence@CVolume@Storage@@AEAAJXZ; Storage::CVolume::_UpdateSpecialFilePresence(void)
0x18002d54c  test    eax, eax
0x18002d54e  js      short loc_18002D57F
0x18002d550  cmp     dword ptr [rbx+34h], 10h
0x18002d554  jnz     short loc_18002D561
0x18002d556  mov     rdx, [rsi]; void *
0x18002d559  mov     rcx, rbx; this
0x18002d55c  call    ?_UpdateTrackInfo@CVolume@Storage@@AEAAJPEAX@Z; Storage::CVolume::_UpdateTrackInfo(void *)
0x18002d561  test    byte ptr [rbx+2Ch], 1
0x18002d565  jz      short loc_18002D57F
0x18002d567  mov     rcx, rbx; this
0x18002d56a  call    ?_ExtractAutorunIconAndLabel@CVolume@Storage@@AEAAJXZ; Storage::CVolume::_ExtractAutorunIconAndLabel(void)
0x18002d56f  test    eax, eax
0x18002d571  jns     short loc_18002D57F
0x18002d573  jmp     short loc_18002D57A
0x18002d575  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002d57a  mov     eax, 1
0x18002d57f  bts     dword ptr [rbx+24h], 1Dh
0x18002d584  jmp     short loc_18002D5C9
0x18002d586  call    cs:__imp_GetLastError
0x18002d58c  mov     ecx, eax
0x18002d58e  cmp     eax, 15h
0x18002d591  jnz     short loc_18002D599
0x18002d593  or      dword ptr [rbx+30h], 4
0x18002d597  jmp     short loc_18002D5C4
0x18002d599  xor     eax, eax
0x18002d59b  lea     rdx, [rbx+5Ch]; lpWideCharStr
0x18002d59f  mov     [rdx], ax
0x18002d5a2  cmp     ecx, 57h ; 'W'
0x18002d5a5  jz      short loc_18002D5AF
0x18002d5a7  cmp     ecx, 3EDh
0x18002d5ad  jnz     short loc_18002D5B7
0x18002d5af  mov     rcx, rdi; this
0x18002d5b2  call    ?_GetIsUnsupportedFileSystem@Storage@@YAJPEBGPEAGK@Z; Storage::_GetIsUnsupportedFileSystem(ushort const *,ushort *,ulong)
0x18002d5b7  mov     rcx, rbx; this
0x18002d5ba  call    ?_HandleAccessDenied@CVolume@Storage@@AEAAXXZ; Storage::CVolume::_HandleAccessDenied(void)
0x18002d5bf  btr     dword ptr [rbx+24h], 1Dh
0x18002d5c4  mov     eax, 1
0x18002d5c9  mov     rbx, [rsp+48h+arg_0]
0x18002d5ce  mov     rsi, [rsp+48h+arg_8]
0x18002d5d3  add     rsp, 40h
0x18002d5d7  pop     rdi
0x18002d5d8  retn
```

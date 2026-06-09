# Storage::_GetVolumeName(ushort const *,ushort *,ulong)

- ea: `0x18002d004`
- end: `0x18002d0b2`
- name: `?_GetVolumeName@Storage@@YAJPEBGPEAGK@Z`
- size: `174`
- prototype: `__int64 __fastcall(Storage *this, LPWSTR lpszVolumeName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x18002d2ec`

## callees

- `0x1800140f0`
- `0x180014c70`
- `0x18002d004`
- `0x180032c90`

## import_xrefs

- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002d081`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002d081`

## pseudocode

```c
__int64 __fastcall Storage::_GetVolumeName(Storage *this, LPWSTR lpszVolumeName, unsigned __int16 *a3)
{
  __int64 result; // rax
  unsigned int v5; // [rsp+28h] [rbp-240h]
  unsigned __int64 v6; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 *v7; // [rsp+38h] [rbp-230h] BYREF
  WCHAR szVolumeMountPoint[264]; // [rsp+40h] [rbp-228h] BYREF

  v7 = 0;
  v6 = 0;
  result = StringCchCopyExW(szVolumeMountPoint, 0x104u, (const unsigned __int16 *)this, &v7, &v6, v5);
  if ( (int)result >= 0 )
  {
    result = StringCchCopyW(v7, v6, L"\\");
    if ( (int)result >= 0 )
    {
      if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, lpszVolumeName, 0x32u) )
      {
        return 0;
      }
      else
      {
        *lpszVolumeName = 0;
        return 2147500037LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002d004  push    rbx
0x18002d006  sub     rsp, 260h
0x18002d00d  mov     rax, cs:__security_cookie
0x18002d014  xor     rax, rsp
0x18002d017  mov     [rsp+268h+var_18], rax
0x18002d01f  mov     rbx, rdx
0x18002d022  mov     [rsp+268h+var_230], 0
0x18002d02b  lea     rax, [rsp+268h+var_238]
0x18002d030  mov     [rsp+268h+var_238], 0
0x18002d039  mov     r8, rcx; unsigned __int16 *
0x18002d03c  mov     [rsp+268h+var_248], rax; unsigned __int64 *
0x18002d041  mov     edx, 104h; unsigned __int64
0x18002d046  lea     rcx, [rsp+268h+szVolumeMountPoint]; unsigned __int16 *
0x18002d04b  lea     r9, [rsp+268h+var_230]; unsigned __int16 **
0x18002d050  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18002d055  test    eax, eax
0x18002d057  js      short loc_18002D099
0x18002d059  mov     rdx, [rsp+268h+var_238]; unsigned __int64
0x18002d05e  lea     r8, asc_1800373FC; "\\"
0x18002d065  mov     rcx, [rsp+268h+var_230]; unsigned __int16 *
0x18002d06a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d06f  test    eax, eax
0x18002d071  js      short loc_18002D099
0x18002d073  mov     r8d, 32h ; '2'; cchBufferLength
0x18002d079  lea     rcx, [rsp+268h+szVolumeMountPoint]; lpszVolumeMountPoint
0x18002d07e  mov     rdx, rbx; lpszVolumeName
0x18002d081  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002d087  test    eax, eax
0x18002d089  jz      short loc_18002D08F
0x18002d08b  xor     eax, eax
0x18002d08d  jmp     short loc_18002D099
0x18002d08f  xor     eax, eax
0x18002d091  mov     [rbx], ax
0x18002d094  mov     eax, 80004005h
0x18002d099  mov     rcx, [rsp+268h+var_18]
0x18002d0a1  xor     rcx, rsp; StackCookie
0x18002d0a4  call    __security_check_cookie
0x18002d0a9  add     rsp, 260h
0x18002d0b0  pop     rbx
0x18002d0b1  retn
```

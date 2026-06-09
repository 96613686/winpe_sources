# GetVolumeGuidFromDriveName(ushort const *,ushort *,ulong)

- ea: `0x1800122f0`
- end: `0x18001241c`
- name: `?GetVolumeGuidFromDriveName@@YAJPEBGPEAGK@Z`
- size: `300`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path`

## callers

- `0x18000ee48`

## callees

- `0x1800122f0`
- `0x180012640`
- `0x1800129d0`
- `0x18001afe2`
- `0x18001b020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800123db`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800123bd`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1800123bd`

## pseudocode

```c
__int64 __fastcall GetVolumeGuidFromDriveName(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // r8
  WCHAR *v8; // r9
  WCHAR *v9; // rcx
  unsigned int v10; // edx
  signed int LastError; // eax
  WCHAR szVolumeMountPoint[8]; // [rsp+20h] [rbp-248h] BYREF
  WCHAR szVolumeName[264]; // [rsp+30h] [rbp-238h] BYREF

  *(_QWORD *)szVolumeMountPoint = 0;
  memset_0(szVolumeName, 0, 0x208u);
  if ( a1 && a2 && IsValidDriveLetter(a1) )
  {
    v6 = 2147483646;
    v7 = 3;
    v8 = szVolumeMountPoint;
    do
    {
      if ( !v6 )
        break;
      if ( !*a1 )
        break;
      *v8++ = *a1++;
      --v6;
      --v7;
    }
    while ( v7 );
    v9 = v8 - 1;
    v10 = v7 == 0 ? 0x8007007A : 0;
    if ( v7 )
      v9 = v8;
    *v9 = 0;
    if ( v7 )
    {
      wcscpy(&szVolumeMountPoint[2], L"\\");
      if ( GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
      {
        return (unsigned int)ParseVolumeGUID(szVolumeName, a2, a3);
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v10;
}

```

## disassembly

```asm
0x1800122f0  mov     [rsp+arg_18], rbx
0x1800122f5  push    rbp
0x1800122f6  push    rsi
0x1800122f7  push    rdi
0x1800122f8  sub     rsp, 250h
0x1800122ff  mov     rax, cs:__security_cookie
0x180012306  xor     rax, rsp
0x180012309  mov     [rsp+268h+var_28], rax
0x180012311  mov     esi, r8d
0x180012314  mov     rdi, rdx
0x180012317  mov     rbx, rcx
0x18001231a  xor     ebp, ebp
0x18001231c  xor     edx, edx; Val
0x18001231e  mov     qword ptr [rsp+268h+szVolumeMountPoint], rbp
0x180012323  mov     r8d, 208h; Size
0x180012329  lea     rcx, [rsp+268h+szVolumeName]; void *
0x18001232e  call    memset_0
0x180012333  test    rbx, rbx
0x180012336  jz      loc_1800123F2
0x18001233c  test    rdi, rdi
0x18001233f  jz      loc_1800123F2
0x180012345  mov     rcx, rbx; unsigned __int16 *
0x180012348  call    ?IsValidDriveLetter@@YA_NPEBG@Z; IsValidDriveLetter(ushort const *)
0x18001234d  test    al, al
0x18001234f  jz      loc_1800123F2
0x180012355  mov     eax, 7FFFFFFEh
0x18001235a  lea     r8d, [rbp+3]
0x18001235e  lea     r9, [rsp+268h+szVolumeMountPoint]
0x180012363  test    rax, rax
0x180012366  jz      short loc_180012385
0x180012368  movzx   ecx, word ptr [rbx]
0x18001236b  test    cx, cx
0x18001236e  jz      short loc_180012385
0x180012370  mov     [r9], cx
0x180012374  add     rbx, 2
0x180012378  add     r9, 2
0x18001237c  dec     rax
0x18001237f  sub     r8, 1
0x180012383  jnz     short loc_180012363
0x180012385  mov     rax, r8
0x180012388  lea     rcx, [r9-2]
0x18001238c  neg     rax
0x18001238f  sbb     edx, edx
0x180012391  not     edx
0x180012393  and     edx, 8007007Ah
0x180012399  test    r8, r8
0x18001239c  cmovnz  rcx, r9
0x1800123a0  mov     [rcx], bp
0x1800123a3  jz      short loc_1800123F7
0x1800123a5  mov     r8d, 104h; cchBufferLength
0x1800123ab  mov     dword ptr [rsp+268h+szVolumeMountPoint+4], 5Ch ; '\'
0x1800123b3  lea     rdx, [rsp+268h+szVolumeName]; lpszVolumeName
0x1800123b8  lea     rcx, [rsp+268h+szVolumeMountPoint]; lpszVolumeMountPoint
0x1800123bd  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1800123c3  test    eax, eax
0x1800123c5  jz      short loc_1800123DB
0x1800123c7  mov     r8d, esi; unsigned int
0x1800123ca  lea     rcx, [rsp+268h+szVolumeName]; unsigned __int16 *
0x1800123cf  mov     rdx, rdi; unsigned __int16 *
0x1800123d2  call    ?ParseVolumeGUID@@YAJPEBGPEAGK@Z; ParseVolumeGUID(ushort const *,ushort *,ulong)
0x1800123d7  mov     edx, eax
0x1800123d9  jmp     short loc_1800123F7
0x1800123db  call    cs:__imp_GetLastError
0x1800123e1  mov     edx, eax
0x1800123e3  test    eax, eax
0x1800123e5  jle     short loc_1800123F7
0x1800123e7  movzx   edx, ax
0x1800123ea  or      edx, 80070000h
0x1800123f0  jmp     short loc_1800123F7
0x1800123f2  mov     edx, 80070057h
0x1800123f7  mov     eax, edx
0x1800123f9  mov     rcx, [rsp+268h+var_28]
0x180012401  xor     rcx, rsp; StackCookie
0x180012404  call    __security_check_cookie
0x180012409  mov     rbx, [rsp+268h+arg_18]
0x180012411  add     rsp, 250h
0x180012418  pop     rdi
0x180012419  pop     rsi
0x18001241a  pop     rbp
0x18001241b  retn
```

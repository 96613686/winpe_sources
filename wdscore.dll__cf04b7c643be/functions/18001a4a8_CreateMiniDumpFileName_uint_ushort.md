# CreateMiniDumpFileName(uint,ushort *)

- ea: `0x18001a4a8`
- end: `0x18001a5d2`
- name: `?CreateMiniDumpFileName@@YAHIPEAG@Z`
- size: `298`
- prototype: `int(unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001c830`

## callees

- `0x180009da4`
- `0x18001a4a8`
- `0x18001ad0c`
- `0x1800274de`
- `0x180027510`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001a502`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18001a502`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a5bc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001a5bc`

## pseudocode

```c
__int64 __fastcall CreateMiniDumpFileName(__int64 a1, unsigned __int16 *a2)
{
  size_t v3; // rdx
  size_t v4; // rax
  WCHAR *v6; // rcx
  __int64 v7; // r10
  unsigned __int16 *v8; // r8
  unsigned __int16 *v9; // r9
  size_t pcchLength[2]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR TempFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(TempFileName, 0, 0x208u);
  pcchLength[0] = 0;
  if ( !g_szMiniDumpPath
    || !GetTempFileNameW(&g_szMiniDumpPath, L"mnd", 0, TempFileName)
    || StringLengthWorkerW(TempFileName, v3, pcchLength) < 0 )
  {
    return 0;
  }
  v4 = pcchLength[0] - 3;
  if ( pcchLength[0] - 3 > 0x7FFFFFFE )
  {
    *a2 = 0;
    return 0;
  }
  v6 = TempFileName;
  v7 = 260;
  v8 = a2;
  do
  {
    if ( !v4 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v4;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  if ( !v7 || StringCchCatW(a2, 0x104u, L"diagerr.mdmp") < 0 )
    return 0;
  DeleteFileW(TempFileName);
  return 1;
}

```

## disassembly

```asm
0x18001a4a8  mov     [rsp+arg_0], rbx
0x18001a4ad  push    rdi
0x18001a4ae  sub     rsp, 250h
0x18001a4b5  mov     rax, cs:__security_cookie
0x18001a4bc  xor     rax, rsp
0x18001a4bf  mov     [rsp+258h+var_18], rax
0x18001a4c7  mov     rbx, rdx
0x18001a4ca  lea     rcx, [rsp+258h+TempFileName]; void *
0x18001a4cf  xor     edx, edx; Val
0x18001a4d1  mov     r8d, 208h; Size
0x18001a4d7  call    memset_0
0x18001a4dc  xor     edi, edi
0x18001a4de  cmp     cs:?g_szMiniDumpPath@@3PAGA, di; ushort near * g_szMiniDumpPath
0x18001a4e5  mov     [rsp+258h+pcchLength], rdi
0x18001a4ea  jz      short loc_18001A539
0x18001a4ec  lea     r9, [rsp+258h+TempFileName]; lpTempFileName
0x18001a4f1  xor     r8d, r8d; uUnique
0x18001a4f4  lea     rdx, aMnd; "mnd"
0x18001a4fb  lea     rcx, ?g_szMiniDumpPath@@3PAGA; lpPathName
0x18001a502  call    cs:__imp_GetTempFileNameW
0x18001a509  nop     dword ptr [rax+rax+00h]
0x18001a50e  test    eax, eax
0x18001a510  jz      short loc_18001A539
0x18001a512  lea     r8, [rsp+258h+pcchLength]; pcchLength
0x18001a517  lea     rcx, [rsp+258h+TempFileName]; psz
0x18001a51c  call    StringLengthWorkerW
0x18001a521  test    eax, eax
0x18001a523  js      short loc_18001A539
0x18001a525  mov     rax, [rsp+258h+pcchLength]
0x18001a52a  add     rax, 0FFFFFFFFFFFFFFFDh
0x18001a52e  cmp     rax, 7FFFFFFEh
0x18001a534  jbe     short loc_18001A55D
0x18001a536  mov     [rbx], di
0x18001a539  xor     eax, eax
0x18001a53b  mov     rcx, [rsp+258h+var_18]
0x18001a543  xor     rcx, rsp; StackCookie
0x18001a546  call    __security_check_cookie
0x18001a54b  mov     rbx, [rsp+258h+arg_0]
0x18001a553  add     rsp, 250h
0x18001a55a  pop     rdi
0x18001a55b  retn
0x18001a55d  mov     r11d, 104h
0x18001a563  lea     rcx, [rsp+258h+TempFileName]
0x18001a568  mov     r10d, r11d
0x18001a56b  mov     r8, rbx
0x18001a56e  test    rax, rax
0x18001a571  jz      short loc_18001A590
0x18001a573  movzx   edx, word ptr [rcx]
0x18001a576  test    dx, dx
0x18001a579  jz      short loc_18001A590
0x18001a57b  mov     [r8], dx
0x18001a57f  add     rcx, 2
0x18001a583  add     r8, 2
0x18001a587  dec     rax
0x18001a58a  sub     r10, 1
0x18001a58e  jnz     short loc_18001A56E
0x18001a590  test    r10, r10
0x18001a593  lea     r9, [r8-2]
0x18001a597  cmovnz  r9, r8
0x18001a59b  mov     [r9], di
0x18001a59f  jz      short loc_18001A539
0x18001a5a1  lea     r8, aDiagerrMdmp; "diagerr.mdmp"
0x18001a5a8  mov     rdx, r11; unsigned __int64
0x18001a5ab  mov     rcx, rbx; unsigned __int16 *
0x18001a5ae  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a5b3  test    eax, eax
0x18001a5b5  js      short loc_18001A539
0x18001a5b7  lea     rcx, [rsp+258h+TempFileName]; lpFileName
0x18001a5bc  call    cs:__imp_DeleteFileW
0x18001a5c3  nop     dword ptr [rax+rax+00h]
0x18001a5c8  mov     eax, 1
0x18001a5cd  jmp     loc_18001A53B
```

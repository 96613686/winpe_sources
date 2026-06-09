# SuScopeRegeneration(_SP_ID *)

- ea: `0x14000b434`
- end: `0x14000b5d2`
- name: `?SuScopeRegeneration@@YAHPEAU_SP_ID@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x140002230`

## callees

- `0x1400090b0`
- `0x14000ac90`
- `0x14000b344`
- `0x14000b434`
- `0x14000b950`
- `0x14000d1be`
- `0x14000d1f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b5ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b5ab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b515`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b515`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b59d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b59d`

## pseudocode

```c
__int64 __fastcall SuScopeRegeneration(struct _GUID *a1)
{
  struct _GUID v2; // xmm0
  int Space; // eax
  unsigned int *v4; // rsi
  unsigned int v5; // edi
  HANDLE FileW; // rax
  void *v7; // r14
  unsigned int DriveLayout; // eax
  _DWORD *v9; // rbx
  __int64 v10; // r15
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  HLOCAL v13; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16[32]; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v17; // [rsp+78h] [rbp-88h]
  WCHAR FileName[40]; // [rsp+BA0h] [rbp+AA0h] BYREF

  hMem = 0;
  memset_0(FileName, 0, sizeof(FileName));
  v15 = 0;
  memset_0(v16, 0, 0xB40u);
  v2 = *a1;
  v13 = 0;
  v17 = v2;
  Space = SuGetSpace((struct _SU_POOL_OBJECT *)&v15, a1 + 1, (struct _SU_SPACE_OBJECT **)&v13);
  v4 = (unsigned int *)v13;
  v5 = Space;
  if ( Space )
  {
    StringCchPrintfW(FileName, 0x28u, L"\\\\.\\PhysicalDrive%d", *((unsigned int *)v13 + 669));
    FileW = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0x80u, 0);
    v7 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v5 = 0;
    }
    else
    {
      DriveLayout = SiGetDriveLayoutEx(FileW, (struct _DRIVE_LAYOUT_INFORMATION_EX **)&hMem);
      v9 = hMem;
      v5 = DriveLayout;
      if ( DriveLayout )
      {
        v10 = 0;
        if ( *((_DWORD *)hMem + 1) )
        {
          do
          {
            LODWORD(dwCreationDisposition) = v9[36 * v10 + 18];
            StringCchPrintfW(FileName, 0x28u, L"\\\\.\\Harddisk%dPartition%d\\", v4[669], dwCreationDisposition);
            SiScopeRegeneration(FileName);
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < v9[1] );
        }
      }
      if ( v9 )
        LocalFree(v9);
      CloseHandle(v7);
    }
  }
  if ( v4 )
    LocalFree(v4);
  return v5;
}

```

## disassembly

```asm
0x14000b434  push    rbp
0x14000b436  push    rbx
0x14000b437  push    rsi
0x14000b438  push    rdi
0x14000b439  push    r14
0x14000b43b  push    r15
0x14000b43d  lea     rbp, [rsp-0B08h]
0x14000b445  sub     rsp, 0C08h
0x14000b44c  mov     rax, cs:__security_cookie
0x14000b453  xor     rax, rsp
0x14000b456  mov     [rbp+0B30h+var_40], rax
0x14000b45d  xor     edx, edx; Val
0x14000b45f  mov     [rsp+0C30h+hMem], 0
0x14000b468  mov     rbx, rcx
0x14000b46b  lea     rcx, [rbp+0B30h+FileName]; void *
0x14000b472  lea     r8d, [rdx+50h]; Size
0x14000b476  call    memset_0
0x14000b47b  xor     edx, edx; Val
0x14000b47d  mov     [rsp+0C30h+var_BE0], 0
0x14000b486  mov     r8d, 0B40h; Size
0x14000b48c  lea     rcx, [rsp+0C30h+var_BD8]; void *
0x14000b491  call    memset_0
0x14000b496  movups  xmm0, xmmword ptr [rbx]
0x14000b499  lea     rdx, [rbx+10h]; struct _GUID *
0x14000b49d  mov     [rsp+0C30h+var_BF0], 0
0x14000b4a6  lea     r8, [rsp+0C30h+var_BF0]; struct _SU_SPACE_OBJECT **
0x14000b4ab  lea     rcx, [rsp+0C30h+var_BE0]; struct _SU_POOL_OBJECT *
0x14000b4b0  movdqu  [rsp+0C30h+var_BB8], xmm0
0x14000b4b6  call    ?SuGetSpace@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@PEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpace(_SU_POOL_OBJECT *,_GUID *,_SU_SPACE_OBJECT * *)
0x14000b4bb  mov     rsi, [rsp+0C30h+var_BF0]
0x14000b4c0  mov     edi, eax
0x14000b4c2  test    eax, eax
0x14000b4c4  jz      loc_14000B5A3
0x14000b4ca  mov     r9d, [rsi+0A74h]
0x14000b4d1  lea     r8, aPhysicaldriveD; "\\\\.\\PhysicalDrive%d"
0x14000b4d8  mov     edx, 28h ; '('; unsigned __int64
0x14000b4dd  lea     rcx, [rbp+0B30h+FileName]; unsigned __int16 *
0x14000b4e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b4e9  xor     r9d, r9d; lpSecurityAttributes
0x14000b4ec  mov     [rsp+0C30h+hTemplateFile], 0; hTemplateFile
0x14000b4f5  mov     [rsp+0C30h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000b4fd  lea     rcx, [rbp+0B30h+FileName]; lpFileName
0x14000b504  mov     edx, 80000000h; dwDesiredAccess
0x14000b509  mov     dword ptr [rsp+0C30h+dwCreationDisposition], 3; dwCreationDisposition
0x14000b511  lea     r8d, [r9+7]; dwShareMode
0x14000b515  call    cs:__imp_CreateFileW
0x14000b51b  mov     r14, rax
0x14000b51e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b522  jnz     short loc_14000B528
0x14000b524  xor     edi, edi
0x14000b526  jmp     short loc_14000B5A3
0x14000b528  lea     rdx, [rsp+0C30h+hMem]; struct _DRIVE_LAYOUT_INFORMATION_EX **
0x14000b52d  mov     rcx, r14; hDevice
0x14000b530  call    ?SiGetDriveLayoutEx@@YAHPEAXPEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; SiGetDriveLayoutEx(void *,_DRIVE_LAYOUT_INFORMATION_EX * *)
0x14000b535  mov     rbx, [rsp+0C30h+hMem]
0x14000b53a  mov     edi, eax
0x14000b53c  test    eax, eax
0x14000b53e  jz      short loc_14000B58C
0x14000b540  xor     r15d, r15d
0x14000b543  cmp     [rbx+4], r15d
0x14000b547  jbe     short loc_14000B58C
0x14000b549  mov     r9d, [rsi+0A74h]
0x14000b550  lea     rax, [r15+r15*8]
0x14000b554  add     rax, rax
0x14000b557  lea     r8, aHarddiskDparti; "\\\\.\\Harddisk%dPartition%d\\"
0x14000b55e  mov     edx, 28h ; '('; unsigned __int64
0x14000b563  lea     rcx, [rbp+0B30h+FileName]; unsigned __int16 *
0x14000b56a  mov     eax, [rbx+rax*8+48h]
0x14000b56e  mov     dword ptr [rsp+0C30h+dwCreationDisposition], eax
0x14000b572  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000b577  lea     rcx, [rbp+0B30h+FileName]; lpFileName
0x14000b57e  call    ?SiScopeRegeneration@@YAHPEAG@Z; SiScopeRegeneration(ushort *)
0x14000b583  inc     r15d
0x14000b586  cmp     r15d, [rbx+4]
0x14000b58a  jb      short loc_14000B549
0x14000b58c  test    rbx, rbx
0x14000b58f  jz      short loc_14000B59A
0x14000b591  mov     rcx, rbx; hMem
0x14000b594  call    cs:__imp_LocalFree
0x14000b59a  mov     rcx, r14; hObject
0x14000b59d  call    cs:__imp_CloseHandle
0x14000b5a3  test    rsi, rsi
0x14000b5a6  jz      short loc_14000B5B1
0x14000b5a8  mov     rcx, rsi; hMem
0x14000b5ab  call    cs:__imp_LocalFree
0x14000b5b1  mov     eax, edi
0x14000b5b3  mov     rcx, [rbp+0B30h+var_40]
0x14000b5ba  xor     rcx, rsp; StackCookie
0x14000b5bd  call    __security_check_cookie
0x14000b5c2  add     rsp, 0C08h
0x14000b5c9  pop     r15
0x14000b5cb  pop     r14
0x14000b5cd  pop     rdi
0x14000b5ce  pop     rsi
0x14000b5cf  pop     rbx
0x14000b5d0  pop     rbp
0x14000b5d1  retn
```

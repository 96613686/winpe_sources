# ReadByte

- ea: `0x180006e30`
- end: `0x180007363`
- name: `ReadByte`
- size: `1331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005880`
- `0x180005de0`
- `0x180005f70`
- `0x1800064e0`
- `0x180006630`
- `0x180006940`
- `0x180007370`
- `0x180007eb4`
- `0x18000820c`
- `0x18006a818`
- `0x18006af68`
- `0x18006bcc8`
- `0x18006c188`
- `0x18006c648`
- `0x18006ca64`
- `0x18006ce80`

## callees

- `0x180006e30`
- `0x1800153c4`
- `0x18001548c`
- `0x180017af4`
- `0x18002b5e4`
- `0x180036f50`
- `0x18006aae8`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006f50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006faf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006fed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007005`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007128`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006f50`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006faf`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006fed`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007005`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800070ec`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007128`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006f6b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000703d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000703d`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180007326`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180007326`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006eff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007070`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006eff`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007070`
- `KERNEL32!lstrcmpW` at `0x180007350`
- `KERNEL32!lstrcmpW` at `0x180007350`

## pseudocode

```c
__int64 __fastcall ReadByte(_WORD *a1, __int64 a2)
{
  __int64 v3; // rdx
  int v5; // eax
  __int64 result; // rax
  int v7; // eax
  int v8; // ecx
  _QWORD *Value; // rax
  _QWORD *v10; // rsi
  void *v11; // rcx
  int v12; // esi
  int v13; // eax
  int v14; // r15d
  __int64 v15; // rbp
  _QWORD *v16; // rax
  _QWORD *v17; // rdx
  int MVFromHDName; // eax
  int v19; // r15d
  _DWORD *v20; // rax
  _DWORD *v21; // rsi
  _QWORD *v22; // rsi
  HANDLE FileW; // rax
  unsigned __int16 v24; // ax
  _BYTE *v25; // r14
  __int64 v26; // rdx
  __int64 v27; // rsi
  _WORD *v28; // rax
  int v29; // ecx
  char v30; // bp
  _DWORD *v31; // rax
  _DWORD *v32; // r9
  unsigned int v33; // ecx
  int v34; // r8d
  int v35; // eax
  unsigned int v36; // r9d
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64, _QWORD, int, _QWORD); // r10
  unsigned int v38; // eax
  unsigned int v39; // r13d
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-108h] BYREF
  DWORD FileSystemFlags; // [rsp+44h] [rbp-104h] BYREF
  DWORD MaximumComponentLength; // [rsp+48h] [rbp-100h] BYREF
  WCHAR VolumeNameBuffer[20]; // [rsp+50h] [rbp-F8h] BYREF
  wchar_t String1[20]; // [rsp+78h] [rbp-D0h] BYREF
  wchar_t pszDest[32]; // [rsp+A0h] [rbp-A8h] BYREF
  WCHAR FileSystemNameBuffer[20]; // [rsp+E0h] [rbp-68h] BYREF

  v3 = *(_QWORD *)(a2 + 3784);
  NumberOfBytesRead = 0;
  *(_QWORD *)(a2 + 3784) = v3 - 1;
  if ( v3 > 0 )
  {
    v5 = *(_DWORD *)(a2 + 70472);
    if ( v5 >= 0 )
    {
      if ( v5 )
      {
LABEL_4:
        result = 8;
        *a1 = *(unsigned __int8 *)(*(_QWORD *)(a2 + 70464))++;
        --*(_DWORD *)(a2 + 70472);
        return result;
      }
      if ( ReadFile(*(HANDLE *)(a2 + 70488), *(LPVOID *)(a2 + 70456), *(_DWORD *)(a2 + 72), &NumberOfBytesRead, 0) )
      {
        v7 = (unsigned __int16)NumberOfBytesRead;
        *(_DWORD *)(a2 + 70472) = (unsigned __int16)NumberOfBytesRead;
        if ( v7 )
        {
          while ( *(_DWORD *)(a2 + 4796) )
          {
LABEL_11:
            if ( *(int *)(a2 + 70472) > 0 )
              break;
            v8 = *(_DWORD *)(a2 + 4342);
            if ( v8 != -1 && *(_DWORD *)(a2 + 4800) + 1 > v8 )
              return 0;
            Value = TlsGetValue(dwUnZIPTlsIndex);
            v10 = Value;
            if ( Value )
            {
              v11 = (void *)Value[8811];
              if ( v11 != (void *)-1LL && CloseHandle(v11) )
                v10[8811] = -1;
            }
            v12 = *(_DWORD *)(a2 + 4342);
            v13 = *(_DWORD *)(a2 + 12);
            v14 = *(_DWORD *)(a2 + 4800);
            if ( v12 == -1 )
            {
              v36 = v14 + 2;
              if ( v13 )
                MVFromHDName = duzMakeMVFromHDName(v36, 0, a2);
              else
                MVFromHDName = MsgCB(*(_QWORD *)(a2 + 3808), 0, 1, v36, 0);
            }
            else if ( v13 )
            {
              MVFromHDName = duzMakeMVFromHDName((unsigned int)(v14 + 2), (unsigned int)(v12 + 1), a2);
            }
            else
            {
              v15 = *(_QWORD *)(a2 + 3808);
              v16 = TlsGetValue(dwUnZIPTlsIndex);
              v17 = v16;
              if ( v16 )
              {
                v37 = (__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD, int, _QWORD))v16[475];
                MVFromHDName = -1;
                if ( v37 )
                  MVFromHDName = v37(v15, 0, 1, (unsigned int)(v14 + 2), v12 + 1, v17[477]);
              }
              else
              {
                MVFromHDName = 4;
              }
            }
            if ( MVFromHDName != 1 )
            {
              if ( MVFromHDName == 2 )
                *(_DWORD *)a2 = 1;
              return 0;
            }
            v19 = *(_DWORD *)(a2 + 4800);
            MaximumComponentLength = 0;
            FileSystemFlags = 0;
            v20 = TlsGetValue(dwUnZIPTlsIndex);
            v21 = v20;
            if ( v20 )
            {
              if ( !v20[3] )
              {
                if ( a2 == -70496 )
                  continue;
                if ( !*(_WORD *)(a2 + 70496) )
                  continue;
                v38 = DriveFromPath((wchar_t *)(a2 + 70496));
                v39 = v38;
                if ( !v21[1199] )
                  continue;
                if ( !(unsigned int)IsMediaRemovable(v38) )
                  continue;
                StringCchPrintfW(pszDest, 0x20u, L"%c:\\", v39 + 64);
                GetVolumeInformationW(
                  pszDest,
                  VolumeNameBuffer,
                  0x14u,
                  0,
                  &MaximumComponentLength,
                  &FileSystemFlags,
                  FileSystemNameBuffer,
                  0x14u);
                StringCchPrintfW(String1, 0x14u, L"PKBACK# %03d", (unsigned int)(v19 + 2));
                if ( lstrcmpW(String1, VolumeNameBuffer) )
                  continue;
              }
            }
            v22 = TlsGetValue(dwUnZIPTlsIndex);
            if ( v22 )
            {
              FileW = CreateFileW((LPCWSTR)(a2 + 70496), 0x80000000, 3u, 0, 3u, 0x8000080u, 0);
              v22[8811] = FileW;
              if ( FileW != (HANDLE)-1LL )
              {
                if ( ReadFile(
                       *(HANDLE *)(a2 + 70488),
                       *(LPVOID *)(a2 + 70456),
                       *(_DWORD *)(a2 + 72),
                       &NumberOfBytesRead,
                       0)
                  && (v24 = NumberOfBytesRead, NumberOfBytesRead) )
                {
                  ++*(_DWORD *)(a2 + 4800);
                  *(_DWORD *)(a2 + 70472) = v24;
                }
                else
                {
                  *(_DWORD *)(a2 + 70472) = 0;
                }
              }
            }
          }
          v25 = *(_BYTE **)(a2 + 70456);
          *(_QWORD *)(a2 + 70464) = v25;
          if ( *(_DWORD *)(a2 + 4804) )
          {
            v26 = *(_QWORD *)(a2 + 3784);
            v27 = *(int *)(a2 + 70472);
            if ( v27 > v26 + 1 )
              LODWORD(v27) = v26 + 1;
            for ( ; (_DWORD)v27; ++v25 )
            {
              LODWORD(v27) = v27 - 1;
              v28 = TlsGetValue(dwUnZIPTlsIndex);
              if ( v28 )
                v29 = (unsigned __int16)((v28[2442] | 2) * ((v28[2442] | 2) ^ 1)) >> 8;
              else
                LOBYTE(v29) = 0;
              v30 = v29 ^ *v25;
              v31 = TlsGetValue(dwUnZIPTlsIndex);
              v32 = v31;
              if ( v31 )
              {
                v33 = v31[1221];
                v34 = *((_DWORD *)crc_32_tab + (unsigned __int8)(v30 ^ v31[1219])) ^ (v31[1219] >> 8);
                v31[1219] = v34;
                v35 = 134775813 * (v31[1220] + (unsigned __int8)v34) + 1;
                v32[1220] = v35;
                v32[1221] = *((_DWORD *)crc_32_tab + (unsigned __int8)(v33 ^ HIBYTE(v35))) ^ (v33 >> 8);
              }
              *v25 = v30;
            }
          }
          goto LABEL_4;
        }
      }
      else
      {
        *(_DWORD *)(a2 + 70472) = -1;
      }
      if ( *(_DWORD *)(a2 + 4796) )
        goto LABEL_11;
      *(_BYTE *)(a2 + 70484) = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006e30  mov     [rsp+arg_10], rbx
0x180006e35  push    rbp
0x180006e36  push    rsi
0x180006e37  push    rdi
0x180006e38  push    r12
0x180006e3a  push    r13
0x180006e3c  push    r14
0x180006e3e  push    r15
0x180006e40  sub     rsp, 110h
0x180006e47  mov     rax, cs:__security_cookie
0x180006e4e  xor     rax, rsp
0x180006e51  mov     [rsp+148h+var_40], rax
0x180006e59  mov     rbx, rdx
0x180006e5c  xor     r12d, r12d
0x180006e5f  mov     rdx, [rdx+0EC8h]
0x180006e66  mov     rdi, rcx
0x180006e69  mov     [rsp+148h+NumberOfBytesRead], r12d
0x180006e6e  lea     rax, [rdx-1]
0x180006e72  mov     [rbx+0EC8h], rax
0x180006e79  test    rdx, rdx
0x180006e7c  jle     short loc_180006EDF
0x180006e7e  mov     eax, [rbx+11348h]
0x180006e84  test    eax, eax
0x180006e86  js      short loc_180006EDF
0x180006e88  jz      short loc_180006EE3
0x180006e8a  mov     rax, [rbx+11340h]
0x180006e91  movzx   ecx, byte ptr [rax]
0x180006e94  mov     eax, 8
0x180006e99  mov     [rdi], cx
0x180006e9c  inc     qword ptr [rbx+11340h]
0x180006ea3  dec     dword ptr [rbx+11348h]
0x180006ea9  mov     rcx, [rsp+148h+var_40]
0x180006eb1  xor     rcx, rsp; StackCookie
0x180006eb4  call    __security_check_cookie
0x180006eb9  mov     rbx, [rsp+148h+arg_10]
0x180006ec1  add     rsp, 110h
0x180006ec8  pop     r15
0x180006eca  pop     r14
0x180006ecc  pop     r13
0x180006ece  pop     r12
0x180006ed0  pop     rdi
0x180006ed1  pop     rsi
0x180006ed2  pop     rbp
0x180006ed3  retn
0x180006ed4  cmp     eax, 2
0x180006ed7  jnz     short loc_180006EDF
0x180006ed9  mov     dword ptr [rbx], 1
0x180006edf  xor     eax, eax
0x180006ee1  jmp     short loc_180006EA9
0x180006ee3  mov     r8d, [rbx+48h]; nNumberOfBytesToRead
0x180006ee7  lea     r9, [rsp+148h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180006eec  mov     rdx, [rbx+11338h]; lpBuffer
0x180006ef3  mov     rcx, [rbx+11358h]; hFile
0x180006efa  mov     [rsp+148h+lpOverlapped], r12; lpOverlapped
0x180006eff  call    cs:__imp_ReadFile
0x180006f05  cmp     eax, 1
0x180006f08  jnz     loc_1800071BD
0x180006f0e  movzx   eax, word ptr [rsp+148h+NumberOfBytesRead]
0x180006f13  mov     [rbx+11348h], eax
0x180006f19  test    eax, eax
0x180006f1b  jz      loc_1800071C7
0x180006f21  cmp     [rbx+12BCh], r12d
0x180006f28  jz      loc_18000709F
0x180006f2e  cmp     [rbx+11348h], r12d
0x180006f35  jg      loc_18000709F
0x180006f3b  mov     ecx, [rbx+10F6h]
0x180006f41  cmp     ecx, 0FFFFFFFFh
0x180006f44  jnz     loc_1800071E0
0x180006f4a  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180006f50  call    cs:__imp_TlsGetValue
0x180006f56  mov     rsi, rax
0x180006f59  test    rax, rax
0x180006f5c  jz      short loc_180006F81
0x180006f5e  mov     rcx, [rax+11358h]; hObject
0x180006f65  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006f69  jz      short loc_180006F81
0x180006f6b  call    cs:__imp_CloseHandle
0x180006f71  cmp     eax, 1
0x180006f74  jnz     short loc_180006F81
0x180006f76  mov     qword ptr [rsi+11358h], 0FFFFFFFFFFFFFFFFh
0x180006f81  mov     esi, [rbx+10F6h]
0x180006f87  mov     eax, [rbx+0Ch]
0x180006f8a  mov     r15d, [rbx+12C0h]
0x180006f91  cmp     esi, 0FFFFFFFFh
0x180006f94  jz      loc_1800071F5
0x180006f9a  test    eax, eax
0x180006f9c  jnz     loc_18000722B
0x180006fa2  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180006fa8  mov     rbp, [rbx+0EE0h]
0x180006faf  call    cs:__imp_TlsGetValue
0x180006fb5  mov     rdx, rax
0x180006fb8  test    rax, rax
0x180006fbb  jnz     loc_18000723F
0x180006fc1  mov     eax, 4
0x180006fc6  cmp     eax, 1
0x180006fc9  jnz     loc_180006ED4
0x180006fcf  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180006fd5  lea     rbp, [rbx+11360h]
0x180006fdc  mov     r15d, [rbx+12C0h]
0x180006fe3  mov     [rsp+148h+MaximumComponentLength], r12d
0x180006fe8  mov     [rsp+148h+FileSystemFlags], r12d
0x180006fed  call    cs:__imp_TlsGetValue
0x180006ff3  mov     rsi, rax
0x180006ff6  test    rax, rax
0x180006ff9  jnz     loc_180007285
0x180006fff  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180007005  call    cs:__imp_TlsGetValue
0x18000700b  mov     rsi, rax
0x18000700e  test    rax, rax
0x180007011  jz      loc_180006F21
0x180007017  mov     [rsp+148h+hTemplateFile], r12; hTemplateFile
0x18000701c  xor     r9d, r9d; lpSecurityAttributes
0x18000701f  mov     [rsp+148h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180007027  mov     edx, 80000000h; dwDesiredAccess
0x18000702c  mov     r8d, 3; dwShareMode
0x180007032  mov     dword ptr [rsp+148h+lpOverlapped], 3; dwCreationDisposition
0x18000703a  mov     rcx, rbp; lpFileName
0x18000703d  call    cs:__imp_CreateFileW
0x180007043  mov     [rsi+11358h], rax
0x18000704a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000704e  jz      loc_180006F21
0x180007054  mov     r8d, [rbx+48h]; nNumberOfBytesToRead
0x180007058  lea     r9, [rsp+148h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000705d  mov     rdx, [rbx+11338h]; lpBuffer
0x180007064  mov     rcx, [rbx+11358h]; hFile
0x18000706b  mov     [rsp+148h+lpOverlapped], r12; lpOverlapped
0x180007070  call    cs:__imp_ReadFile
0x180007076  cmp     eax, 1
0x180007079  jnz     loc_1800071A1
0x18000707f  mov     eax, [rsp+148h+NumberOfBytesRead]
0x180007083  test    eax, eax
0x180007085  jz      loc_1800071A1
0x18000708b  inc     dword ptr [rbx+12C0h]
0x180007091  movzx   eax, ax
0x180007094  mov     [rbx+11348h], eax
0x18000709a  jmp     loc_180006F21
0x18000709f  mov     r14, [rbx+11338h]
0x1800070a6  mov     [rbx+11340h], r14
0x1800070ad  cmp     [rbx+12C4h], r12d
0x1800070b4  jz      loc_180006E8A
0x1800070ba  mov     rdx, [rbx+0EC8h]
0x1800070c1  movsxd  rsi, dword ptr [rbx+11348h]
0x1800070c8  lea     rcx, [rdx+1]
0x1800070cc  cmp     rsi, rcx
0x1800070cf  jg      loc_1800071AD
0x1800070d5  test    esi, esi
0x1800070d7  jz      loc_180006E8A
0x1800070dd  lea     r15, crc_32_tab
0x1800070e4  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x1800070ea  dec     esi
0x1800070ec  call    cs:__imp_TlsGetValue
0x1800070f2  test    rax, rax
0x1800070f5  jz      loc_1800071B5
0x1800070fb  movzx   ecx, word ptr [rax+1314h]
0x180007102  or      cx, 2
0x180007106  movzx   eax, cx
0x180007109  movzx   ecx, cx
0x18000710c  xor     ax, 1
0x180007110  movzx   edx, ax
0x180007113  imul    edx, ecx
0x180007116  movzx   ecx, dx
0x180007119  shr     ecx, 8
0x18000711c  movzx   ebp, byte ptr [r14]
0x180007120  xor     ebp, ecx
0x180007122  mov     ecx, cs:dwUnZIPTlsIndex; dwTlsIndex
0x180007128  call    cs:__imp_TlsGetValue
0x18000712e  mov     r9, rax
0x180007131  test    rax, rax
0x180007134  jz      short loc_18000718E
0x180007136  mov     r8d, [rax+130Ch]
0x18000713d  mov     ecx, r8d
0x180007140  xor     rcx, rbp
0x180007143  shr     r8d, 8
0x180007147  movzx   edx, cl
0x18000714a  mov     ecx, [r9+1314h]
0x180007151  xor     r8d, [r15+rdx*4]
0x180007155  mov     [rax+130Ch], r8d
0x18000715c  movzx   eax, r8b
0x180007160  add     eax, [r9+1310h]
0x180007167  imul    eax, 8088405h
0x18000716d  inc     eax
0x18000716f  mov     [r9+1310h], eax
0x180007176  shr     rax, 18h
0x18000717a  xor     rax, rcx
0x18000717d  shr     ecx, 8
0x180007180  movzx   eax, al
0x180007183  xor     ecx, [r15+rax*4]
0x180007187  mov     [r9+1314h], ecx
0x18000718e  mov     [r14], bpl
0x180007191  inc     r14
0x180007194  test    esi, esi
0x180007196  jnz     loc_1800070E4
0x18000719c  jmp     loc_180006E8A
0x1800071a1  mov     [rbx+11348h], r12d
0x1800071a8  jmp     loc_180006F21
0x1800071ad  lea     esi, [rdx+1]
0x1800071b0  jmp     loc_1800070D5
0x1800071b5  mov     ecx, r12d
0x1800071b8  jmp     loc_18000711C
0x1800071bd  mov     dword ptr [rbx+11348h], 0FFFFFFFFh
0x1800071c7  cmp     [rbx+12BCh], r12d
0x1800071ce  jnz     loc_180006F2E
0x1800071d4  mov     byte ptr [rbx+11354h], 1
0x1800071db  jmp     loc_180006EDF
0x1800071e0  mov     eax, [rbx+12C0h]
0x1800071e6  inc     eax
0x1800071e8  cmp     eax, ecx
0x1800071ea  jg      loc_180006EDF
0x1800071f0  jmp     loc_180006F4A
0x1800071f5  xor     edx, edx
0x1800071f7  lea     r9d, [r15+2]
0x1800071fb  test    eax, eax
0x1800071fd  jz      short loc_18000720F
0x1800071ff  mov     r8, rbx
0x180007202  mov     ecx, r9d
0x180007205  call    duzMakeMVFromHDName
0x18000720a  jmp     loc_180006FC6
0x18000720f  mov     rcx, [rbx+0EE0h]
0x180007216  mov     r8d, 1
0x18000721c  mov     dword ptr [rsp+148h+lpOverlapped], r12d
0x180007221  call    MsgCB
0x180007226  jmp     loc_180006FC6
0x18000722b  lea     edx, [rsi+1]
0x18000722e  mov     r8, rbx
0x180007231  lea     ecx, [r15+2]
0x180007235  call    duzMakeMVFromHDName
0x18000723a  jmp     loc_180006FC6
0x18000723f  mov     r10, [rdx+0ED8h]
0x180007246  mov     eax, 0FFFFFFFFh
0x18000724b  test    r10, r10
0x18000724e  jz      loc_180006FC6
0x180007254  mov     rdx, [rdx+0EE8h]
0x18000725b  lea     r8d, [rsi+1]
0x18000725f  mov     qword ptr [rsp+148h+dwFlagsAndAttributes], rdx
0x180007264  lea     r9d, [r15+2]
0x180007268  mov     dword ptr [rsp+148h+lpOverlapped], r8d
0x18000726d  xor     edx, edx
0x18000726f  mov     r8d, 1
0x180007275  mov     rcx, rbp
0x180007278  mov     rax, r10
0x18000727b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007280  jmp     loc_180006FC6
0x180007285  cmp     [rax+0Ch], r12d
0x180007289  jnz     loc_180006FFF
0x18000728f  test    rbp, rbp
0x180007292  jz      loc_180006F21
0x180007298  cmp     [rbp+0], r12w
0x18000729d  jz      loc_180006F21
0x1800072a3  mov     rcx, rbp; Str
0x1800072a6  call    DriveFromPath
0x1800072ab  mov     r13d, eax
0x1800072ae  cmp     [rsi+12BCh], r12d
0x1800072b5  jz      loc_180006F21
0x1800072bb  mov     ecx, eax
0x1800072bd  call    IsMediaRemovable
0x1800072c2  test    eax, eax
0x1800072c4  jz      loc_180006F21
0x1800072ca  lea     r9d, [r13+40h]
0x1800072ce  mov     edx, 20h ; ' '; cchDest
0x1800072d3  lea     r8, aC; "%c:\\"
0x1800072da  lea     rcx, [rsp+148h+pszDest]; pszDest
0x1800072e2  call    StringCchPrintfW
0x1800072e7  mov     [rsp+148h+nFileSystemNameSize], 14h; nFileSystemNameSize
0x1800072ef  lea     rax, [rsp+148h+FileSystemNameBuffer]
0x1800072f7  mov     [rsp+148h+hTemplateFile], rax; lpFileSystemNameBuffer
0x1800072fc  lea     rdx, [rsp+148h+VolumeNameBuffer]; lpVolumeNameBuffer
0x180007301  lea     rax, [rsp+148h+FileSystemFlags]
0x180007306  xor     r9d, r9d; lpVolumeSerialNumber
0x180007309  mov     qword ptr [rsp+148h+dwFlagsAndAttributes], rax; lpFileSystemFlags
0x18000730e  lea     rcx, [rsp+148h+pszDest]; lpRootPathName
0x180007316  lea     rax, [rsp+148h+MaximumComponentLength]
0x18000731b  mov     r8d, 14h; nVolumeNameSize
0x180007321  mov     [rsp+148h+lpOverlapped], rax; lpMaximumComponentLength
0x180007326  call    cs:__imp_GetVolumeInformationW
0x18000732c  lea     r9d, [r15+2]
0x180007330  mov     edx, 14h; cchDest
0x180007335  lea     r8, aPkback03d; "PKBACK# %03d"
0x18000733c  lea     rcx, [rsp+148h+String1]; pszDest
0x180007341  call    StringCchPrintfW
0x180007346  lea     rdx, [rsp+148h+VolumeNameBuffer]; lpString2
0x18000734b  lea     rcx, [rsp+148h+String1]; lpString1
0x180007350  call    cs:__imp_lstrcmpW
0x180007356  test    eax, eax
0x180007358  jnz     loc_180006F21
0x18000735e  jmp     loc_180006FFF
```

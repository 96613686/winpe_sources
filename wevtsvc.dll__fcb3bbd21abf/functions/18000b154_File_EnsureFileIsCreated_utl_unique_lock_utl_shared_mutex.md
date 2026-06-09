# File::EnsureFileIsCreated(utl::unique_lock<utl::shared_mutex> &)

- ea: `0x18000b154`
- end: `0x18000b383`
- name: `?EnsureFileIsCreated@File@@AEAAKAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(File *this)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180008100`
- `0x18000ac90`
- `0x18003f260`
- `0x1800b3194`

## callees

- `0x180004a3c`
- `0x18000b154`
- `0x18000bc38`
- `0x180077ad0`
- `0x180092008`
- `0x18009e770`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18000b29d`
- `ntdll!NtSetInformationFile` at `0x18000b29d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b1be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b1a0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000b1a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall File::EnsureFileIsCreated(File *this)
{
  HANDLE FileW; // rax
  void *v3; // rcx
  void *v4; // rcx
  DWORD v5; // eax
  DWORD LastError; // ebp
  bool v7; // zf
  NTSTATUS v9; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-18h] BYREF
  int FileInformation; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_BYTE *)this + 832) )
    return 0;
  FileW = CreateFileW(*((LPCWSTR *)this + 85), 0xC0000000, 1u, 0, 4u, 0, 0);
  v3 = (void *)*((_QWORD *)this + 84);
  *((_QWORD *)this + 84) = FileW;
  if ( (unsigned __int64)v3 + 1 > 1 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 84);
  if ( (unsigned __int64)v4 + 1 <= 1 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
        LastError,
        *((_QWORD *)this + 85));
    }
  }
  else
  {
    if ( (*((_BYTE *)this + 825) & 8) == 0 )
    {
      FileInformation = 2;
      IoStatusBlock = 0;
      v9 = NtSetInformationFile(v4, &IoStatusBlock, &FileInformation, 4u, FileRenameInformation|0x40);
      if ( v9 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
          *((_QWORD *)this + 85),
          v9);
      }
    }
    *((_BYTE *)this + 832) = 0;
    v5 = File::InitializeEmptyFile(this);
    LastError = v5;
    if ( !v5 )
    {
      v7 = (*((_BYTE *)this + 825) & 8) == 0;
      *((_BYTE *)this + 829) = 1;
      if ( v7
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          (unsigned int)&WPP_d3d936efbc913e3641017ad303784371_Traceguids,
          *((_QWORD *)this + 89),
          *((_QWORD *)this + 85));
      }
      return 0;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v5);
    }
  }
  return LastError;
}

```

## disassembly

```asm
0x18000b154  mov     rax, rsp
0x18000b157  mov     [rax+10h], rbx
0x18000b15b  mov     [rax+18h], rbp
0x18000b15f  push    rsi
0x18000b160  sub     rsp, 50h
0x18000b164  cmp     byte ptr [rcx+340h], 0
0x18000b16b  mov     rbp, rdx
0x18000b16e  mov     rbx, rcx
0x18000b171  jz      loc_18000B21E
0x18000b177  mov     rcx, [rcx+2A8h]; lpFileName
0x18000b17e  xor     r9d, r9d; lpSecurityAttributes
0x18000b181  mov     qword ptr [rax-28h], 0
0x18000b189  mov     edx, 0C0000000h; dwDesiredAccess
0x18000b18e  mov     dword ptr [rax-30h], 0
0x18000b195  mov     dword ptr [rax-38h], 4
0x18000b19c  lea     r8d, [r9+1]; dwShareMode
0x18000b1a0  call    cs:__imp_CreateFileW
0x18000b1a6  mov     rcx, [rbx+2A0h]; hObject
0x18000b1ad  mov     [rbx+2A0h], rax
0x18000b1b4  lea     rax, [rcx+1]
0x18000b1b8  cmp     rax, 1
0x18000b1bc  jbe     short loc_18000B1C4
0x18000b1be  call    cs:__imp_CloseHandle
0x18000b1c4  mov     rcx, [rbx+2A0h]; FileHandle
0x18000b1cb  lea     rax, [rcx+1]
0x18000b1cf  cmp     rax, 1
0x18000b1d3  jbe     loc_18000B2F7
0x18000b1d9  test    byte ptr [rbx+339h], 8
0x18000b1e0  lea     rsi, WPP_GLOBAL_Control
0x18000b1e7  jz      loc_18000B275
0x18000b1ed  mov     r8, rbp
0x18000b1f0  mov     byte ptr [rbx+340h], 0
0x18000b1f7  mov     edx, 1
0x18000b1fc  mov     rcx, rbx; this
0x18000b1ff  call    ?InitializeEmptyFile@File@@AEAAK_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::InitializeEmptyFile(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)
0x18000b204  mov     ebp, eax
0x18000b206  test    eax, eax
0x18000b208  jnz     loc_18000B366
0x18000b20e  test    byte ptr [rbx+339h], 8
0x18000b215  mov     byte ptr [rbx+33Dh], 1
0x18000b21c  jz      short loc_18000B230
0x18000b21e  xor     eax, eax
0x18000b220  mov     rbx, [rsp+58h+arg_8]
0x18000b225  mov     rbp, [rsp+58h+arg_10]
0x18000b22a  add     rsp, 50h
0x18000b22e  pop     rsi
0x18000b22f  retn
0x18000b230  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b237  cmp     rcx, rsi
0x18000b23a  jz      short loc_18000B21E
0x18000b23c  test    dword ptr [rcx+1Ch], 8000h
0x18000b243  jz      short loc_18000B21E
0x18000b245  cmp     byte ptr [rcx+19h], 4
0x18000b249  jb      short loc_18000B21E
0x18000b24b  mov     rax, [rbx+2A8h]
0x18000b252  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18000b259  mov     r9, [rbx+2C8h]
0x18000b260  mov     edx, 21h ; '!'
0x18000b265  mov     rcx, [rcx+10h]
0x18000b269  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x18000b26e  call    WPP_SF_SS
0x18000b273  jmp     short loc_18000B21E
0x18000b275  xorps   xmm0, xmm0
0x18000b278  mov     [rsp+58h+FileInformation], 2
0x18000b280  mov     r9d, 4; Length
0x18000b286  mov     [rsp+58h+FileInformationClass], 4Ah ; 'J'; FileInformationClass
0x18000b28e  lea     r8, [rsp+58h+FileInformation]; FileInformation
0x18000b293  lea     rdx, [rsp+58h+IoStatusBlock]; IoStatusBlock
0x18000b298  movups  xmmword ptr [rsp+58h+IoStatusBlock], xmm0
0x18000b29d  call    cs:__imp_NtSetInformationFile
0x18000b2a3  test    eax, eax
0x18000b2a5  jns     loc_18000B1ED
0x18000b2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2b2  cmp     rcx, rsi
0x18000b2b5  jz      loc_18000B1ED
0x18000b2bb  test    dword ptr [rcx+1Ch], 8000h
0x18000b2c2  jz      loc_18000B1ED
0x18000b2c8  cmp     byte ptr [rcx+19h], 2
0x18000b2cc  jb      loc_18000B1ED
0x18000b2d2  mov     r9, [rbx+2A8h]
0x18000b2d9  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18000b2e0  mov     rcx, [rcx+10h]
0x18000b2e4  mov     edx, 1Fh
0x18000b2e9  mov     [rsp+58h+FileInformationClass], eax
0x18000b2ed  call    WPP_SF_Sd
0x18000b2f2  jmp     loc_18000B1ED
0x18000b2f7  call    cs:__imp_GetLastError
0x18000b2fd  mov     ebp, eax
0x18000b2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b306  lea     rsi, WPP_GLOBAL_Control
0x18000b30d  cmp     rcx, rsi
0x18000b310  jz      short loc_18000B35F
0x18000b312  test    dword ptr [rcx+1Ch], 8000h
0x18000b319  jz      short loc_18000B35F
0x18000b31b  cmp     byte ptr [rcx+19h], 2
0x18000b31f  jb      short loc_18000B35F
0x18000b321  mov     rax, [rbx+2A8h]
0x18000b328  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18000b32f  mov     rcx, [rcx+10h]
0x18000b333  mov     edx, 1Eh
0x18000b338  mov     r9d, ebp
0x18000b33b  mov     qword ptr [rsp+58h+FileInformationClass], rax
0x18000b340  call    WPP_SF_dS
0x18000b345  jmp     short loc_18000B35F
0x18000b347  mov     rcx, [rcx+10h]
0x18000b34b  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18000b352  mov     edx, 20h ; ' '
0x18000b357  mov     r9d, ebp
0x18000b35a  call    WPP_SF_d
0x18000b35f  mov     eax, ebp
0x18000b361  jmp     loc_18000B220
0x18000b366  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b36d  cmp     rcx, rsi
0x18000b370  jz      short loc_18000B35F
0x18000b372  test    dword ptr [rcx+1Ch], 8000h
0x18000b379  jz      short loc_18000B35F
0x18000b37b  cmp     byte ptr [rcx+19h], 2
0x18000b37f  jb      short loc_18000B35F
0x18000b381  jmp     short loc_18000B347
```

# IsHiberboot(ulong)

- ea: `0x14008b244`
- end: `0x14008b39c`
- name: `?IsHiberboot@@YAHK@Z`
- size: `344`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x14004c400`
- `0x140052c20`
- `0x140065950`

## callees

- `0x140041c34`
- `0x14004df08`
- `0x140089844`
- `0x14008b244`
- `0x14008b3a4`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14008b312`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14008b312`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14008b32d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14008b32d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14008b353`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14008b353`
- `ntdll!NtPowerInformation` at `0x14008b2a2`
- `ntdll!NtPowerInformation` at `0x14008b2a2`

## string_xrefs

- `0x14008b306`: `fmifs.dll`
- `0x14008b320`: `QueryIsDiskCheckScheduledForNextBoot`

## pseudocode

```c
__int64 __fastcall IsHiberboot(unsigned int a1, unsigned __int8 a2)
{
  unsigned int v4; // ebx
  NTSTATUS v5; // edi
  HMODULE Library; // rax
  HMODULE v7; // rdi
  char v8; // si
  FARPROC ProcAddress; // rax
  __int64 v10; // r9
  char v11; // [rsp+58h] [rbp+10h] BYREF
  int OutputBuffer; // [rsp+60h] [rbp+18h] BYREF

  OutputBuffer = 0;
  if ( CallCheckForHiberbootRpc(0, a2) )
    return 1;
  v4 = 0;
  if ( (a1 & 0xB) != 0 && (LogoffFlagsToShutdownFlags(a1) & 0x200) != 0 )
  {
    v5 = NtPowerInformation((POWER_INFORMATION_LEVEL)65, 0, 0, &OutputBuffer, 4u);
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids,
        (unsigned int)v5,
        OutputBuffer);
    }
    if ( v5 >= 0 )
    {
      if ( OutputBuffer )
      {
        v11 = 0;
        v4 = 1;
        Library = LoadLibraryExW(L"fmifs.dll", 0, 0x800u);
        v7 = Library;
        if ( Library )
        {
          v8 = 0;
          ProcAddress = GetProcAddress(Library, "QueryIsDiskCheckScheduledForNextBoot");
          if ( ProcAddress )
          {
            v8 = 0;
            if ( ((unsigned __int8 (__fastcall *)(char *))ProcAddress)(&v11) )
              v8 = v11;
          }
          FreeLibrary(v7);
          if ( v8 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids, v10);
            }
            return 0;
          }
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14008b244  mov     [rsp+arg_0], rbx
0x14008b249  push    rsi
0x14008b24a  push    rdi
0x14008b24b  push    r14
0x14008b24d  sub     rsp, 30h
0x14008b251  mov     edi, ecx
0x14008b253  mov     [rsp+48h+OutputBuffer], 0
0x14008b25b  xor     ecx, ecx; unsigned __int8
0x14008b25d  call    ?CallCheckForHiberbootRpc@@YAHEE@Z; CallCheckForHiberbootRpc(uchar,uchar)
0x14008b262  test    eax, eax
0x14008b264  jz      short loc_14008B270
0x14008b266  mov     eax, 1
0x14008b26b  jmp     loc_14008B38E
0x14008b270  xor     ebx, ebx
0x14008b272  test    dil, 0Bh
0x14008b276  jz      loc_14008B38C
0x14008b27c  mov     ecx, edi; unsigned int
0x14008b27e  call    ?LogoffFlagsToShutdownFlags@@YAKK@Z; LogoffFlagsToShutdownFlags(ulong)
0x14008b283  bt      eax, 9
0x14008b287  jnb     loc_14008B38C
0x14008b28d  lea     r9, [rsp+48h+OutputBuffer]; OutputBuffer
0x14008b292  mov     [rsp+48h+OutputBufferLength], 4; OutputBufferLength
0x14008b29a  xor     r8d, r8d; InputBufferLength
0x14008b29d  lea     ecx, [rbx+41h]; PowerInformationLevel
0x14008b2a0  xor     edx, edx; InputBuffer
0x14008b2a2  call    cs:__imp_NtPowerInformation
0x14008b2a8  mov     edi, eax
0x14008b2aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b2b1  lea     r14, WPP_GLOBAL_Control
0x14008b2b8  cmp     rcx, r14
0x14008b2bb  jz      short loc_14008B2E7
0x14008b2bd  test    byte ptr [rcx+1Ch], 1
0x14008b2c1  jz      short loc_14008B2E7
0x14008b2c3  cmp     byte ptr [rcx+19h], 4
0x14008b2c7  jb      short loc_14008B2E7
0x14008b2c9  mov     eax, [rsp+48h+OutputBuffer]
0x14008b2cd  lea     edx, [rbx+61h]
0x14008b2d0  mov     rcx, [rcx+10h]
0x14008b2d4  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b2db  mov     r9d, edi
0x14008b2de  mov     [rsp+48h+OutputBufferLength], eax
0x14008b2e2  call    WPP_SF_DD
0x14008b2e7  test    edi, edi
0x14008b2e9  js      loc_14008B38C
0x14008b2ef  cmp     [rsp+48h+OutputBuffer], ebx
0x14008b2f3  jz      loc_14008B38C
0x14008b2f9  xor     edx, edx; hFile
0x14008b2fb  mov     [rsp+48h+arg_8], 0
0x14008b300  mov     r8d, 800h; dwFlags
0x14008b306  lea     rcx, aFmifsDll; "fmifs.dll"
0x14008b30d  mov     ebx, 1
0x14008b312  call    cs:__imp_LoadLibraryExW
0x14008b318  mov     rdi, rax
0x14008b31b  test    rax, rax
0x14008b31e  jz      short loc_14008B38C
0x14008b320  lea     rdx, aQueryisdiskche; "QueryIsDiskCheckScheduledForNextBoot"
0x14008b327  mov     rcx, rax; hModule
0x14008b32a  xor     sil, sil
0x14008b32d  call    cs:__imp_GetProcAddress
0x14008b333  test    rax, rax
0x14008b336  jz      short loc_14008B350
0x14008b338  lea     rcx, [rsp+48h+arg_8]
0x14008b33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008b342  movzx   ecx, [rsp+48h+arg_8]
0x14008b347  test    al, al
0x14008b349  movzx   esi, sil
0x14008b34d  cmovnz  esi, ecx
0x14008b350  mov     rcx, rdi; hLibModule
0x14008b353  call    cs:__imp_FreeLibrary
0x14008b359  test    sil, sil
0x14008b35c  jz      short loc_14008B38C
0x14008b35e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b365  cmp     rcx, r14
0x14008b368  jz      short loc_14008B38A
0x14008b36a  test    [rcx+1Ch], bl
0x14008b36d  jz      short loc_14008B38A
0x14008b36f  cmp     byte ptr [rcx+19h], 4
0x14008b373  jb      short loc_14008B38A
0x14008b375  mov     rcx, [rcx+10h]
0x14008b379  lea     r8, WPP_6767f1e3976c37dffaa064fbfa18a65b_Traceguids
0x14008b380  mov     edx, 62h ; 'b'
0x14008b385  call    WPP_SF_
0x14008b38a  xor     ebx, ebx
0x14008b38c  mov     eax, ebx
0x14008b38e  mov     rbx, [rsp+48h+arg_0]
0x14008b393  add     rsp, 30h
0x14008b397  pop     r14
0x14008b399  pop     rdi
0x14008b39a  pop     rsi
0x14008b39b  retn
```

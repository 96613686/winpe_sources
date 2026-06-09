# UpdateCachedCustomErrorText(void)

- ea: `0x18000e9f8`
- end: `0x18000ec7c`
- name: `?UpdateCachedCustomErrorText@@YAJXZ`
- size: `644`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000ec7c`

## callees

- `0x180007824`
- `0x18000e978`
- `0x18000e9f8`
- `0x18004d350`
- `0x18004d6c8`
- `0x18004d754`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18000ec24`
- `KERNEL32!ReadFile` at `0x18000ec24`
- `KERNEL32!CloseHandle` at `0x18000ec44`
- `KERNEL32!CloseHandle` at `0x18000ec44`
- `KERNEL32!lstrlenW` at `0x18000ead7`
- `KERNEL32!lstrlenW` at `0x18000eae9`
- `KERNEL32!lstrlenW` at `0x18000ead7`
- `KERNEL32!lstrlenW` at `0x18000eae9`
- `KERNEL32!CreateFileW` at `0x18000eba4`
- `KERNEL32!CreateFileW` at `0x18000eba4`
- `KERNEL32!GetTickCount` at `0x18000ebd7`
- `KERNEL32!GetTickCount` at `0x18000ebd7`

## pseudocode

```c
__int64 UpdateCachedCustomErrorText(void)
{
  unsigned int LastWin32Error; // ebx
  __int64 v1; // rdx
  WCHAR *v2; // rcx
  WCHAR v3; // ax
  WCHAR *v4; // rax
  int v5; // ebx
  __int64 v6; // rdi
  WCHAR *v7; // rcx
  WCHAR v8; // ax
  WCHAR *v9; // rax
  HANDLE FileW; // rdi
  void *v11; // rax
  DWORD NumberOfBytesRead; // [rsp+60h] [rbp+8h] BYREF

  LastWin32Error = 0;
  NumberOfBytesRead = 0;
  MemFree(g_pCachedCustomErrorText);
  g_pCachedCustomErrorText = 0;
  g_CachedCustomErrorTextLength = 0;
  if ( g_szCustomErrorFile )
  {
    if ( g_szCustomErrorFile == 92 || word_18008F362 == 58 )
    {
      v6 = 260;
      v7 = &g_szCustomErrorRealFilename;
      do
      {
        if ( v6 == -2147483386 )
          break;
        v8 = *(WCHAR *)((char *)v7 + (char *)&g_szCustomErrorFile - (char *)&g_szCustomErrorRealFilename);
        if ( !v8 )
          break;
        *v7++ = v8;
        --v6;
      }
      while ( v6 );
      v9 = v7 - 1;
      if ( v6 )
        v9 = v7;
      *v9 = 0;
      LastWin32Error = v6 == 0 ? 0x8007007A : 0;
      if ( !v6 )
        goto LABEL_33;
    }
    else
    {
      v1 = 260;
      v2 = &g_szCustomErrorRealFilename;
      do
      {
        if ( v1 == -2147483386 )
          break;
        v3 = *(WCHAR *)((char *)v2 + (char *)&Names::s_wszGlobalConfigDirectory - (char *)&g_szCustomErrorRealFilename);
        if ( !v3 )
          break;
        *v2++ = v3;
        --v1;
      }
      while ( v1 );
      v4 = v2 - 1;
      if ( v1 )
        v4 = v2;
      *v4 = 0;
      LastWin32Error = v1 == 0 ? 0x8007007A : 0;
      if ( !v1 )
        goto LABEL_33;
      LastWin32Error = StringCchCatW(&g_szCustomErrorRealFilename, 0x104u, L"\\");
      if ( LastWin32Error )
        goto LABEL_33;
      v5 = lstrlenW(&g_szCustomErrorRealFilename);
      if ( lstrlenW(&g_szCustomErrorFile) + v5 > 258 )
      {
        LastWin32Error = -2147024882;
LABEL_33:
        MemFree(g_pCachedCustomErrorText);
        g_pCachedCustomErrorText = 0;
        g_CachedCustomErrorTextLength = 0;
        return LastWin32Error;
      }
      LastWin32Error = StringCchCatW(&g_szCustomErrorRealFilename, 0x104u, &g_szCustomErrorFile);
      if ( LastWin32Error )
        goto LABEL_33;
    }
    FileW = CreateFileW(&g_szCustomErrorRealFilename, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastWin32Error = GetLastWin32Error();
    }
    else
    {
      LastWin32Error = GetCustomErrorFileInfo(
                         &g_szCustomErrorRealFilename,
                         &g_LastCustomErrorFileSize,
                         &g_LastCustomErrorFileTime);
      g_LastCustomErrorUpdateCheck = GetTickCount();
      if ( !LastWin32Error )
      {
        g_CachedCustomErrorTextLength = g_LastCustomErrorFileSize;
        v11 = MemAllocClear(g_LastCustomErrorFileSize);
        g_pCachedCustomErrorText = v11;
        if ( v11 )
        {
          if ( !ReadFile(FileW, v11, g_CachedCustomErrorTextLength, &NumberOfBytesRead, 0)
            || NumberOfBytesRead != g_CachedCustomErrorTextLength )
          {
            LastWin32Error = GetLastWin32Error();
          }
        }
        else
        {
          LastWin32Error = -2147024882;
        }
      }
      CloseHandle(FileW);
    }
    if ( LastWin32Error )
      goto LABEL_33;
  }
  return LastWin32Error;
}

```

## disassembly

```asm
0x18000e9f8  mov     [rsp+arg_8], rbx
0x18000e9fd  mov     [rsp+arg_10], rbp
0x18000ea02  push    rsi
0x18000ea03  push    rdi
0x18000ea04  push    r14
0x18000ea06  sub     rsp, 40h
0x18000ea0a  mov     rcx, cs:?g_pCachedCustomErrorText@@3PEADEA; lpMem
0x18000ea11  xor     ebp, ebp
0x18000ea13  mov     ebx, ebp
0x18000ea15  mov     [rsp+58h+NumberOfBytesRead], ebp
0x18000ea19  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000ea1e  movzx   eax, cs:?g_szCustomErrorFile@@3PAGA; ushort near * g_szCustomErrorFile
0x18000ea25  mov     cs:?g_pCachedCustomErrorText@@3PEADEA, rbp; char * g_pCachedCustomErrorText
0x18000ea2c  mov     cs:?g_CachedCustomErrorTextLength@@3KA, ebp; ulong g_CachedCustomErrorTextLength
0x18000ea32  test    ax, ax
0x18000ea35  jz      loc_18000EC67
0x18000ea3b  cmp     ax, 5Ch ; '\'
0x18000ea3f  jz      loc_18000EB1D
0x18000ea45  cmp     cs:word_18008F362, 3Ah ; ':'
0x18000ea4d  jz      loc_18000EB1D
0x18000ea53  lea     rsi, ?g_szCustomErrorRealFilename@@3PAGA; ushort near * g_szCustomErrorRealFilename
0x18000ea5a  mov     edi, 104h
0x18000ea5f  lea     r8, ?s_wszGlobalConfigDirectory@Names@@0PAGA; ushort near * Names::s_wszGlobalConfigDirectory
0x18000ea66  mov     edx, edi
0x18000ea68  mov     rcx, rsi
0x18000ea6b  sub     r8, rsi
0x18000ea6e  lea     rax, [rdx+7FFFFEFAh]
0x18000ea75  test    rax, rax
0x18000ea78  jz      short loc_18000EA91
0x18000ea7a  movzx   eax, word ptr [r8+rcx]
0x18000ea7f  test    ax, ax
0x18000ea82  jz      short loc_18000EA91
0x18000ea84  mov     [rcx], ax
0x18000ea87  add     rcx, 2
0x18000ea8b  sub     rdx, 1
0x18000ea8f  jnz     short loc_18000EA6E
0x18000ea91  test    rdx, rdx
0x18000ea94  lea     rax, [rcx-2]
0x18000ea98  cmovnz  rax, rcx
0x18000ea9c  mov     [rax], bp
0x18000ea9f  mov     rax, rdx
0x18000eaa2  neg     rax
0x18000eaa5  sbb     ebx, ebx
0x18000eaa7  not     ebx
0x18000eaa9  and     ebx, 8007007Ah
0x18000eaaf  test    rdx, rdx
0x18000eab2  jz      loc_18000EC4E
0x18000eab8  lea     r8, SubBlock; "\\"
0x18000eabf  mov     rdx, rdi; unsigned __int64
0x18000eac2  mov     rcx, rsi; unsigned __int16 *
0x18000eac5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eaca  mov     ebx, eax
0x18000eacc  test    eax, eax
0x18000eace  jnz     loc_18000EC4E
0x18000ead4  mov     rcx, rsi; lpString
0x18000ead7  call    cs:__imp_lstrlenW
0x18000eadd  lea     r14, ?g_szCustomErrorFile@@3PAGA; ushort near * g_szCustomErrorFile
0x18000eae4  mov     ebx, eax
0x18000eae6  mov     rcx, r14; lpString
0x18000eae9  call    cs:__imp_lstrlenW
0x18000eaef  add     ebx, eax
0x18000eaf1  cmp     ebx, 102h
0x18000eaf7  jle     short loc_18000EB03
0x18000eaf9  mov     ebx, 8007000Eh
0x18000eafe  jmp     loc_18000EC4E
0x18000eb03  mov     r8, r14; unsigned __int16 *
0x18000eb06  mov     rdx, rdi; unsigned __int64
0x18000eb09  mov     rcx, rsi; unsigned __int16 *
0x18000eb0c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eb11  mov     ebx, eax
0x18000eb13  test    eax, eax
0x18000eb15  jnz     loc_18000EC4E
0x18000eb1b  jmp     short loc_18000EB80
0x18000eb1d  lea     rsi, ?g_szCustomErrorRealFilename@@3PAGA; ushort near * g_szCustomErrorRealFilename
0x18000eb24  mov     edi, 104h
0x18000eb29  lea     r14, ?g_szCustomErrorFile@@3PAGA; ushort near * g_szCustomErrorFile
0x18000eb30  mov     rcx, rsi
0x18000eb33  sub     r14, rsi
0x18000eb36  lea     rax, [rdi+7FFFFEFAh]
0x18000eb3d  test    rax, rax
0x18000eb40  jz      short loc_18000EB59
0x18000eb42  movzx   eax, word ptr [r14+rcx]
0x18000eb47  test    ax, ax
0x18000eb4a  jz      short loc_18000EB59
0x18000eb4c  mov     [rcx], ax
0x18000eb4f  add     rcx, 2
0x18000eb53  sub     rdi, 1
0x18000eb57  jnz     short loc_18000EB36
0x18000eb59  test    rdi, rdi
0x18000eb5c  lea     rax, [rcx-2]
0x18000eb60  cmovnz  rax, rcx
0x18000eb64  mov     [rax], bp
0x18000eb67  mov     rax, rdi
0x18000eb6a  neg     rax
0x18000eb6d  sbb     ebx, ebx
0x18000eb6f  not     ebx
0x18000eb71  and     ebx, 8007007Ah
0x18000eb77  test    rdi, rdi
0x18000eb7a  jz      loc_18000EC4E
0x18000eb80  xor     r9d, r9d; lpSecurityAttributes
0x18000eb83  mov     [rsp+58h+hTemplateFile], rbp; hTemplateFile
0x18000eb88  mov     [rsp+58h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18000eb90  mov     edx, 80000000h; dwDesiredAccess
0x18000eb95  mov     rcx, rsi; lpFileName
0x18000eb98  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18000eba0  lea     r8d, [r9+1]; dwShareMode
0x18000eba4  call    cs:__imp_CreateFileW
0x18000ebaa  mov     rdi, rax
0x18000ebad  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ebb1  jnz     short loc_18000EBBF
0x18000ebb3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000ebb8  mov     ebx, eax
0x18000ebba  jmp     loc_18000EC4A
0x18000ebbf  lea     r8, ?g_LastCustomErrorFileTime@@3U_FILETIME@@A; struct _FILETIME *
0x18000ebc6  mov     rcx, rsi; unsigned __int16 *
0x18000ebc9  lea     rdx, ?g_LastCustomErrorFileSize@@3KA; unsigned int *
0x18000ebd0  call    ?GetCustomErrorFileInfo@@YAJPEAGPEAKPEAU_FILETIME@@@Z; GetCustomErrorFileInfo(ushort *,ulong *,_FILETIME *)
0x18000ebd5  mov     ebx, eax
0x18000ebd7  call    cs:__imp_GetTickCount
0x18000ebdd  mov     cs:?g_LastCustomErrorUpdateCheck@@3KA, eax; ulong g_LastCustomErrorUpdateCheck
0x18000ebe3  test    ebx, ebx
0x18000ebe5  jnz     short loc_18000EC41
0x18000ebe7  mov     eax, cs:?g_LastCustomErrorFileSize@@3KA; ulong g_LastCustomErrorFileSize
0x18000ebed  mov     ecx, eax; unsigned __int64
0x18000ebef  mov     cs:?g_CachedCustomErrorTextLength@@3KA, eax; ulong g_CachedCustomErrorTextLength
0x18000ebf5  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x18000ebfa  mov     cs:?g_pCachedCustomErrorText@@3PEADEA, rax; char * g_pCachedCustomErrorText
0x18000ec01  test    rax, rax
0x18000ec04  jnz     short loc_18000EC0D
0x18000ec06  mov     ebx, 8007000Eh
0x18000ec0b  jmp     short loc_18000EC41
0x18000ec0d  mov     r8d, cs:?g_CachedCustomErrorTextLength@@3KA; nNumberOfBytesToRead
0x18000ec14  lea     r9, [rsp+58h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18000ec19  mov     rdx, rax; lpBuffer
0x18000ec1c  mov     qword ptr [rsp+58h+dwCreationDisposition], rbp; lpOverlapped
0x18000ec21  mov     rcx, rdi; hFile
0x18000ec24  call    cs:__imp_ReadFile
0x18000ec2a  test    eax, eax
0x18000ec2c  jz      short loc_18000EC3A
0x18000ec2e  mov     eax, cs:?g_CachedCustomErrorTextLength@@3KA; ulong g_CachedCustomErrorTextLength
0x18000ec34  cmp     [rsp+58h+NumberOfBytesRead], eax
0x18000ec38  jz      short loc_18000EC41
0x18000ec3a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000ec3f  mov     ebx, eax
0x18000ec41  mov     rcx, rdi; hObject
0x18000ec44  call    cs:__imp_CloseHandle
0x18000ec4a  test    ebx, ebx
0x18000ec4c  jz      short loc_18000EC67
0x18000ec4e  mov     rcx, cs:?g_pCachedCustomErrorText@@3PEADEA; lpMem
0x18000ec55  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18000ec5a  mov     cs:?g_pCachedCustomErrorText@@3PEADEA, rbp; char * g_pCachedCustomErrorText
0x18000ec61  mov     cs:?g_CachedCustomErrorTextLength@@3KA, ebp; ulong g_CachedCustomErrorTextLength
0x18000ec67  mov     rbp, [rsp+58h+arg_10]
0x18000ec6c  mov     eax, ebx
0x18000ec6e  mov     rbx, [rsp+58h+arg_8]
0x18000ec73  add     rsp, 40h
0x18000ec77  pop     r14
0x18000ec79  pop     rdi
0x18000ec7a  pop     rsi
0x18000ec7b  retn
```

# MapVolumeDeviceNameToIndex(ushort const *)

- ea: `0x180002c90`
- end: `0x180002f1e`
- name: `?MapVolumeDeviceNameToIndex@@YAJPEBG@Z`
- size: `654`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x180002488`

## callees

- `0x180002c90`
- `0x18000c29c`
- `0x18000d020`
- `0x18000d038`
- `0x18000d12c`
- `0x18000dae8`
- `0x18000db28`
- `0x180010fca`
- `0x180010fd6`
- `0x180011000`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dd2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180002d02`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002dc2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180002dc2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011247`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002ec0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011247`

## string_xrefs

- `0x180002cfb`: `\\.\MountPointManager`

## pseudocode

```c
__int64 __fastcall MapVolumeDeviceNameToIndex(const unsigned __int16 *a1)
{
  unsigned int v2; // esi
  DWORD *v3; // rbx
  HANDLE FileW; // r15
  size_t *v5; // r8
  __int64 v6; // rax
  DWORD v7; // eax
  BOOL v8; // edi
  DWORD v9; // eax
  DWORD v10; // edi
  const wchar_t *v11; // r13
  int v12; // ecx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-2B8h]
  DWORD BytesReturned; // [rsp+40h] [rbp-298h] BYREF
  BOOL v16; // [rsp+44h] [rbp-294h]
  DWORD v17; // [rsp+48h] [rbp-290h]
  HANDLE v18; // [rsp+50h] [rbp-288h]
  DWORD *v19; // [rsp+58h] [rbp-280h]
  int v20; // [rsp+60h] [rbp-278h]
  _BYTE InBuffer[16]; // [rsp+70h] [rbp-268h] BYREF
  unsigned int v22; // [rsp+80h] [rbp-258h]
  __int16 v23; // [rsp+84h] [rbp-254h]
  wchar_t pszDest[132]; // [rsp+88h] [rbp-250h] BYREF
  _BYTE OutBuffer[272]; // [rsp+190h] [rbp-148h] BYREF

  v2 = -1;
  v3 = (DWORD *)OutBuffer;
  v19 = (DWORD *)OutBuffer;
  BytesReturned = 0;
  FileW = CreateFileW(L"\\\\.\\MountPointManager", 0x80000000, 3u, 0, 3u, 0x80u, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v18 = FileW;
  if ( FileW == (HANDLE)-1LL )
    TrkRaiseLastError();
  memset_0(InBuffer, 0, 0x11Cu);
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v20 = 2 * v6;
  v22 = 24;
  v23 = 2 * v6;
  StringCopyWorkerW_0(pszDest, 0x82u, v5, L"\\??", *(size_t *)dwCreationDisposition);
  StringCbCatW((unsigned __int16 *)&InBuffer[v22], 284LL - v22, a1 + 3);
  v16 = 0;
  v7 = 260;
  for ( BytesReturned = 260; ; v7 = BytesReturned )
  {
    v8 = DeviceIoControl(FileW, 0x6D0008u, InBuffer, 0x11Cu, v3, v7, &BytesReturned, 0);
    v16 = v8;
    if ( v8 || GetLastError() != 234 )
      break;
    v9 = *v3;
    BytesReturned = *v3;
    if ( OutBuffer != (_BYTE *)v3 )
    {
      operator delete(v3);
      v9 = BytesReturned;
    }
    v3 = (DWORD *)operator new(v9);
    v19 = v3;
    if ( !v3 )
      TrkRaiseWin32Error(8);
  }
  if ( !v8 )
    TrkRaiseLastError();
  v10 = 0;
  v17 = 0;
  while ( v10 < v3[1] )
  {
    if ( (v3[6 * v10 + 3] & 0xFFFE) >= 0x1C )
    {
      v11 = (const wchar_t *)((char *)v3 + v3[6 * v10 + 2]);
      if ( !wcsncmp_0(v11, L"\\DosDevices\\", 0xCu) )
      {
        if ( LOWORD(v3[6 * v10 + 5]) )
        {
          v12 = v11[12];
          if ( (unsigned __int16)(v12 - 97) <= 0x19u )
          {
            v2 = v12 - 97;
            break;
          }
          if ( (unsigned __int16)(v12 - 65) <= 0x19u )
          {
            v2 = v12 - 65;
            break;
          }
        }
      }
    }
    v17 = ++v10;
  }
  CloseHandle(FileW);
  if ( OutBuffer != (_BYTE *)v3 )
    operator delete(v3);
  return v2;
}

```

## disassembly

```asm
0x180002c90  mov     [rsp+arg_8], rbx
0x180002c95  mov     [rsp+arg_10], rsi
0x180002c9a  push    rdi
0x180002c9b  push    r12
0x180002c9d  push    r13
0x180002c9f  push    r14
0x180002ca1  push    r15
0x180002ca3  sub     rsp, 2B0h
0x180002caa  mov     rax, cs:__security_cookie
0x180002cb1  xor     rax, rsp
0x180002cb4  mov     [rsp+2D8h+var_38], rax
0x180002cbc  mov     rdi, rcx
0x180002cbf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002cc3  mov     [rsp+2D8h+var_288], rsi
0x180002cc8  lea     rbx, [rsp+2D8h+OutBuffer]
0x180002cd0  mov     [rsp+2D8h+var_280], rbx
0x180002cd5  xor     r12d, r12d
0x180002cd8  mov     [rsp+2D8h+BytesReturned], r12d
0x180002cdd  mov     [rsp+2D8h+hTemplateFile], rsi; hTemplateFile
0x180002ce2  mov     [rsp+2D8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180002cea  lea     r8d, [rsi+4]; dwShareMode
0x180002cee  mov     [rsp+2D8h+dwCreationDisposition], r8d; cchToCopy
0x180002cf3  xor     r9d, r9d; lpSecurityAttributes
0x180002cf6  mov     edx, 80000000h; dwDesiredAccess
0x180002cfb  lea     rcx, FileName; "\\\\.\\MountPointManager"
0x180002d02  call    cs:__imp_CreateFileW
0x180002d08  mov     r15, rax
0x180002d0b  mov     [rsp+2D8h+var_288], rax
0x180002d10  cmp     rax, rsi
0x180002d13  jz      loc_180002F0A
0x180002d19  mov     r14d, 11Ch
0x180002d1f  mov     r8d, r14d; Size
0x180002d22  xor     edx, edx; Val
0x180002d24  lea     rcx, [rsp+2D8h+InBuffer]; void *
0x180002d29  call    memset_0
0x180002d2e  mov     rax, rsi
0x180002d31  inc     rax
0x180002d34  cmp     [rdi+rax*2], r12w
0x180002d39  jnz     short loc_180002D31
0x180002d3b  add     eax, eax
0x180002d3d  mov     [rsp+2D8h+var_278], eax
0x180002d41  mov     [rsp+2D8h+var_258], 18h
0x180002d4c  mov     [rsp+2D8h+var_254], ax
0x180002d54  lea     r9, pszSrc; "\\??"
0x180002d5b  mov     edx, 82h; cchDest
0x180002d60  lea     rcx, [rsp+2D8h+pszDest]; pszDest
0x180002d68  call    StringCopyWorkerW_0
0x180002d6d  mov     r11d, [rsp+2D8h+var_258]
0x180002d75  lea     r8, [rdi+6]; unsigned __int16 *
0x180002d79  mov     rdx, r14
0x180002d7c  sub     rdx, r11; unsigned __int64
0x180002d7f  lea     rcx, [rsp+2D8h+InBuffer]
0x180002d84  add     rcx, r11; unsigned __int16 *
0x180002d87  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x180002d8c  mov     [rsp+2D8h+var_294], r12d
0x180002d91  mov     eax, 104h
0x180002d96  mov     [rsp+2D8h+BytesReturned], eax
0x180002d9a  mov     [rsp+2D8h+lpOverlapped], r12; lpOverlapped
0x180002d9f  lea     rcx, [rsp+2D8h+BytesReturned]
0x180002da4  mov     [rsp+2D8h+hTemplateFile], rcx; lpBytesReturned
0x180002da9  mov     [rsp+2D8h+dwFlagsAndAttributes], eax; nOutBufferSize
0x180002dad  mov     qword ptr [rsp+2D8h+dwCreationDisposition], rbx; lpOutBuffer
0x180002db2  mov     r9d, r14d; nInBufferSize
0x180002db5  lea     r8, [rsp+2D8h+InBuffer]; lpInBuffer
0x180002dba  mov     edx, 6D0008h; dwIoControlCode
0x180002dbf  mov     rcx, r15; hDevice
0x180002dc2  call    cs:__imp_DeviceIoControl
0x180002dc8  mov     edi, eax
0x180002dca  mov     [rsp+2D8h+var_294], eax
0x180002dce  test    eax, eax
0x180002dd0  jnz     short loc_180002E1F
0x180002dd2  call    cs:__imp_GetLastError
0x180002dd8  cmp     eax, 0EAh
0x180002ddd  jnz     short loc_180002E1F
0x180002ddf  mov     eax, [rbx]
0x180002de1  mov     [rsp+2D8h+BytesReturned], eax
0x180002de5  lea     rcx, [rsp+2D8h+OutBuffer]
0x180002ded  cmp     rcx, rbx
0x180002df0  jz      short loc_180002DFE
0x180002df2  mov     rcx, rbx; Block
0x180002df5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002dfa  mov     eax, [rsp+2D8h+BytesReturned]
0x180002dfe  mov     ecx, eax; Size
0x180002e00  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e05  mov     rbx, rax
0x180002e08  mov     [rsp+2D8h+var_280], rax
0x180002e0d  test    rax, rax
0x180002e10  jz      loc_180002F0F
0x180002e16  mov     eax, [rsp+2D8h+BytesReturned]
0x180002e1a  jmp     loc_180002D9A
0x180002e1f  test    edi, edi
0x180002e21  jz      loc_180002F17
0x180002e27  mov     edi, r12d
0x180002e2a  mov     [rsp+2D8h+var_290], r12d
0x180002e2f  cmp     edi, [rbx+4]
0x180002e32  jnb     loc_180002EBD
0x180002e38  movsxd  rax, edi
0x180002e3b  lea     r14, [rax+rax*2]
0x180002e3f  movzx   eax, word ptr [rbx+r14*8+0Ch]
0x180002e45  mov     ecx, 0FFFEh
0x180002e4a  and     ax, cx
0x180002e4d  cmp     ax, 1Ch
0x180002e51  jb      short loc_180002EB2
0x180002e53  mov     r13d, [rbx+r14*8+8]
0x180002e58  add     r13, rbx
0x180002e5b  mov     r8d, 0Ch; MaxCount
0x180002e61  lea     rdx, aDosdevices; "\\DosDevices\\"
0x180002e68  mov     rcx, r13; String1
0x180002e6b  call    wcsncmp_0
0x180002e70  test    eax, eax
0x180002e72  jnz     short loc_180002EB2
0x180002e74  cmp     [rbx+r14*8+14h], r12w
0x180002e7a  jz      short loc_180002EB2
0x180002e7c  movzx   ecx, word ptr [r13+18h]
0x180002e81  movzx   eax, cx
0x180002e84  mov     r8d, 61h ; 'a'
0x180002e8a  sub     ax, r8w
0x180002e8e  cmp     ax, 19h
0x180002e92  ja      short loc_180002E9B
0x180002e94  mov     esi, ecx
0x180002e96  sub     esi, r8d
0x180002e99  jmp     short loc_180002EBD
0x180002e9b  movzx   eax, cx
0x180002e9e  mov     edx, 41h ; 'A'
0x180002ea3  sub     ax, dx
0x180002ea6  cmp     ax, 19h
0x180002eaa  ja      short loc_180002EB2
0x180002eac  mov     esi, ecx
0x180002eae  sub     esi, edx
0x180002eb0  jmp     short loc_180002EBD
0x180002eb2  inc     edi
0x180002eb4  mov     [rsp+2D8h+var_290], edi
0x180002eb8  jmp     loc_180002E2F
0x180002ebd  mov     rcx, r15; hObject
0x180002ec0  call    cs:__imp_CloseHandle
0x180002ec6  lea     rax, [rsp+2D8h+OutBuffer]
0x180002ece  cmp     rax, rbx
0x180002ed1  jz      short loc_180002EDB
0x180002ed3  mov     rcx, rbx; Block
0x180002ed6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002edb  mov     eax, esi
0x180002edd  mov     rcx, [rsp+2D8h+var_38]
0x180002ee5  xor     rcx, rsp; StackCookie
0x180002ee8  call    __security_check_cookie
0x180002eed  lea     r11, [rsp+2D8h+var_28]
0x180002ef5  mov     rbx, [r11+38h]
0x180002ef9  mov     rsi, [r11+40h]
0x180002efd  mov     rsp, r11
0x180002f00  pop     r15
0x180002f02  pop     r14
0x180002f04  pop     r13
0x180002f06  pop     r12
0x180002f08  pop     rdi
0x180002f09  retn
0x180002f0a  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180002f0f  lea     ecx, [rax+8]; int
0x180002f12  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180002f17  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x180011234  push    rbp
0x180011236  sub     rsp, 40h
0x18001123a  mov     rbp, rdx
0x18001123d  mov     rcx, [rbp+50h]; hObject
0x180011241  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011245  jz      short loc_18001124E
0x180011247  call    cs:__imp_CloseHandle
0x18001124d  nop
0x18001124e  lea     rax, [rbp+190h]
0x180011255  mov     rcx, [rbp+58h]; Block
0x180011259  cmp     rax, rcx
0x18001125c  jz      short loc_180011269
0x18001125e  test    rcx, rcx
0x180011261  jz      short loc_180011269
0x180011263  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011268  nop
0x180011269  add     rsp, 40h
0x18001126d  pop     rbp
0x18001126e  retn
```

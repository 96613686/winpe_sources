# ClusterInternalIsPathOnSharedVolume

- ea: `0x180032fec`
- end: `0x180033208`
- name: `ClusterInternalIsPathOnSharedVolume`
- size: `540`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180012740`
- `0x180026da0`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180007604`
- `0x180032fec`
- `0x180033210`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800331cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800331cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003314b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003314b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033188`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003313c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18003313c`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003317e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800331b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18003317e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800331b6`

## pseudocode

```c
__int64 __fastcall ClusterInternalIsPathOnSharedVolume(unsigned __int16 *a1)
{
  __int64 v2; // rax
  __int16 v3; // ax
  HANDLE FileW; // rdi
  DWORD LastError; // ebx
  DWORD BytesReturned[4]; // [rsp+40h] [rbp-98h] BYREF
  unsigned __int16 v8[56]; // [rsp+50h] [rbp-88h] BYREF

  BytesReturned[0] = 0;
  if ( a1 && *a1 )
  {
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
    v3 = 2 * v2;
    if ( (v3 == 96 || v3 == 98 && a1[48] == 92)
      && *a1 == 92
      && (a1[1] == 63 || a1[1] == 92)
      && a1[2] == 63
      && a1[3] == 92
      && a1[4] == 86
      && a1[5] == 111
      && a1[6] == 108
      && a1[7] == 117
      && a1[8] == 109
      && a1[9] == 101
      && a1[10] == 123
      && a1[19] == 45
      && a1[24] == 45
      && a1[29] == 45
      && a1[34] == 45
      && a1[47] == 125 )
    {
      memset_0(v8, 0, 0x64u);
      StringCchCopyW(v8, 0x32u, a1);
      v8[48] = 0;
      return ClusterInternalIsVolumeCsv(v8);
    }
    FileW = CreateFileW(a1, 0x100000u, 3u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      if ( DeviceIoControl(FileW, 0x90248u, 0, 0, 0, 0, BytesReturned, 0) )
      {
        LastError = 0;
      }
      else
      {
        GetLastError();
        LastError = 0;
        if ( !DeviceIoControl(FileW, 0x9025Cu, 0, 0, 0, 0, BytesReturned, 0) )
          LastError = GetLastError();
      }
      CloseHandle(FileW);
    }
  }
  else
  {
    LastError = 87;
  }
  return LastError == 0;
}

```

## disassembly

```asm
0x180032fec  mov     [rsp+arg_8], rbx
0x180032ff1  mov     [rsp+arg_10], rsi
0x180032ff6  push    rdi
0x180032ff7  sub     rsp, 0D0h
0x180032ffe  mov     rax, cs:__security_cookie
0x180033005  xor     rax, rsp
0x180033008  mov     [rsp+0D8h+var_18], rax
0x180033010  xor     esi, esi
0x180033012  mov     rbx, rcx
0x180033015  mov     [rsp+0D8h+BytesReturned], esi
0x180033019  test    rcx, rcx
0x18003301c  jz      loc_1800331D7
0x180033022  cmp     [rcx], si
0x180033025  jz      loc_1800331D7
0x18003302b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003302f  inc     rax
0x180033032  cmp     [rcx+rax*2], si
0x180033036  jnz     short loc_18003302F
0x180033038  add     ax, ax
0x18003303b  mov     cx, 5Ch ; '\'
0x18003303f  cmp     ax, 60h ; '`'
0x180033043  jz      short loc_180033059
0x180033045  cmp     ax, 62h ; 'b'
0x180033049  jnz     loc_180033119
0x18003304f  cmp     [rbx+60h], cx
0x180033053  jnz     loc_180033119
0x180033059  cmp     [rbx], cx
0x18003305c  jnz     loc_180033119
0x180033062  cmp     word ptr [rbx+2], 3Fh ; '?'
0x180033067  jz      short loc_180033073
0x180033069  cmp     [rbx+2], cx
0x18003306d  jnz     loc_180033119
0x180033073  cmp     word ptr [rbx+4], 3Fh ; '?'
0x180033078  jnz     loc_180033119
0x18003307e  cmp     [rbx+6], cx
0x180033082  jnz     loc_180033119
0x180033088  cmp     word ptr [rbx+8], 56h ; 'V'
0x18003308d  jnz     loc_180033119
0x180033093  cmp     word ptr [rbx+0Ah], 6Fh ; 'o'
0x180033098  jnz     short loc_180033119
0x18003309a  cmp     word ptr [rbx+0Ch], 6Ch ; 'l'
0x18003309f  jnz     short loc_180033119
0x1800330a1  cmp     word ptr [rbx+0Eh], 75h ; 'u'
0x1800330a6  jnz     short loc_180033119
0x1800330a8  cmp     word ptr [rbx+10h], 6Dh ; 'm'
0x1800330ad  jnz     short loc_180033119
0x1800330af  cmp     word ptr [rbx+12h], 65h ; 'e'
0x1800330b4  jnz     short loc_180033119
0x1800330b6  cmp     word ptr [rbx+14h], 7Bh ; '{'
0x1800330bb  jnz     short loc_180033119
0x1800330bd  mov     ax, 2Dh ; '-'
0x1800330c1  cmp     [rbx+26h], ax
0x1800330c5  jnz     short loc_180033119
0x1800330c7  cmp     [rbx+30h], ax
0x1800330cb  jnz     short loc_180033119
0x1800330cd  cmp     [rbx+3Ah], ax
0x1800330d1  jnz     short loc_180033119
0x1800330d3  cmp     [rbx+44h], ax
0x1800330d7  jnz     short loc_180033119
0x1800330d9  cmp     word ptr [rbx+5Eh], 7Dh ; '}'
0x1800330de  jnz     short loc_180033119
0x1800330e0  xor     edx, edx; Val
0x1800330e2  lea     rcx, [rsp+0D8h+var_88]; void *
0x1800330e7  lea     r8d, [rdx+64h]; Size
0x1800330eb  call    memset_0
0x1800330f0  mov     r8, rbx; unsigned __int16 *
0x1800330f3  lea     rcx, [rsp+0D8h+var_88]; unsigned __int16 *
0x1800330f8  mov     edx, 32h ; '2'; unsigned __int64
0x1800330fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033102  lea     rcx, [rsp+0D8h+var_88]
0x180033107  mov     [rsp+0D8h+var_28], si
0x18003310f  call    ClusterInternalIsVolumeCsv
0x180033114  jmp     loc_1800331E3
0x180033119  mov     [rsp+0D8h+hTemplateFile], rsi; hTemplateFile
0x18003311e  mov     r8d, 3; dwShareMode
0x180033124  mov     [rsp+0D8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18003312c  xor     r9d, r9d; lpSecurityAttributes
0x18003312f  mov     edx, 100000h; dwDesiredAccess
0x180033134  mov     [rsp+0D8h+dwCreationDisposition], r8d; dwCreationDisposition
0x180033139  mov     rcx, rbx; lpFileName
0x18003313c  call    cs:__imp_CreateFileW
0x180033142  mov     rdi, rax
0x180033145  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033149  jnz     short loc_180033158
0x18003314b  call    cs:__imp_GetLastError
0x180033151  mov     ebx, eax
0x180033153  jmp     loc_1800331DC
0x180033158  mov     [rsp+0D8h+lpOverlapped], rsi; lpOverlapped
0x18003315d  lea     rax, [rsp+0D8h+BytesReturned]
0x180033162  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x180033167  xor     r9d, r9d; nInBufferSize
0x18003316a  mov     [rsp+0D8h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18003316e  xor     r8d, r8d; lpInBuffer
0x180033171  mov     edx, 90248h; dwIoControlCode
0x180033176  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rsi; lpOutBuffer
0x18003317b  mov     rcx, rdi; hDevice
0x18003317e  call    cs:__imp_DeviceIoControl
0x180033184  test    eax, eax
0x180033186  jnz     short loc_1800331CA
0x180033188  call    cs:__imp_GetLastError
0x18003318e  mov     [rsp+0D8h+lpOverlapped], rsi; lpOverlapped
0x180033193  lea     rax, [rsp+0D8h+BytesReturned]
0x180033198  mov     [rsp+0D8h+hTemplateFile], rax; lpBytesReturned
0x18003319d  xor     r9d, r9d; nInBufferSize
0x1800331a0  mov     [rsp+0D8h+dwFlagsAndAttributes], esi; nOutBufferSize
0x1800331a4  xor     r8d, r8d; lpInBuffer
0x1800331a7  mov     edx, 9025Ch; dwIoControlCode
0x1800331ac  mov     qword ptr [rsp+0D8h+dwCreationDisposition], rsi; lpOutBuffer
0x1800331b1  mov     rcx, rdi; hDevice
0x1800331b4  mov     ebx, esi
0x1800331b6  call    cs:__imp_DeviceIoControl
0x1800331bc  test    eax, eax
0x1800331be  jnz     short loc_1800331CC
0x1800331c0  call    cs:__imp_GetLastError
0x1800331c6  mov     ebx, eax
0x1800331c8  jmp     short loc_1800331CC
0x1800331ca  mov     ebx, esi
0x1800331cc  mov     rcx, rdi; hObject
0x1800331cf  call    cs:__imp_CloseHandle
0x1800331d5  jmp     short loc_1800331DC
0x1800331d7  mov     ebx, 57h ; 'W'
0x1800331dc  test    ebx, ebx
0x1800331de  mov     eax, esi
0x1800331e0  setz    al
0x1800331e3  mov     rcx, [rsp+0D8h+var_18]
0x1800331eb  xor     rcx, rsp; StackCookie
0x1800331ee  call    __security_check_cookie
0x1800331f3  lea     r11, [rsp+0D8h+var_8]
0x1800331fb  mov     rbx, [r11+18h]
0x1800331ff  mov     rsi, [r11+20h]
0x180033203  mov     rsp, r11
0x180033206  pop     rdi
0x180033207  retn
```

# WimpFSFBackgroundValidateNextBlocks

- ea: `0x140028ef4`
- end: `0x1400290cc`
- name: `WimpFSFBackgroundValidateNextBlocks`
- size: `472`
- prototype: `__int64 __fastcall(PVOID Buffer, PRTL_BITMAP BitMapHeader)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400290e0`

## callees

- `0x140011560`
- `0x140027fac`
- `0x140028ef4`
- `0x140029c50`
- `0x14002aa38`
- `0x14002ab40`

## import_xrefs

- `ntoskrnl!RtlAreBitsSet` at `0x140028f64`
- `ntoskrnl!RtlAreBitsSet` at `0x140028f64`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140028fb3`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140028fd1`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140028fb3`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140028fd1`
- `FLTMGR!FltReadFile` at `0x140029055`
- `FLTMGR!FltReadFile` at `0x140029055`

## pseudocode

```c
__int64 __fastcall WimpFSFBackgroundValidateNextBlocks(_QWORD *Buffer, PRTL_BITMAP BitMapHeader, _BYTE *a3)
{
  int v6; // r14d
  unsigned int v7; // eax
  ULONG v8; // edx
  ULONG v9; // edi
  unsigned int v10; // ebp
  ULONG *v11; // rdi
  ULONG NextForwardRunClear; // eax
  ULONG v13; // eax
  unsigned int v14; // esi
  struct _FILE_OBJECT *v15; // rdx
  struct _FLT_INSTANCE *v16; // rcx
  ULONG BytesRead; // [rsp+50h] [rbp-68h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+58h] [rbp-60h] BYREF
  __int128 v20; // [rsp+60h] [rbp-58h] BYREF

  BytesRead = 0;
  ByteOffset.QuadPart = 0;
  v20 = 0;
  v6 = 0;
  WimpFSFSetBackgroundPriorities((__int64)&v20);
  v7 = (unsigned int)BitMapHeader[12].Buffer;
  if ( v7 )
  {
    v8 = *(&BitMapHeader[12].SizeOfBitMap + 1);
    do
    {
      v9 = 64;
      if ( v7 < 0x40 )
        v9 = v7;
      if ( !RtlAreBitsSet(BitMapHeader, v8, v9) )
        break;
      LODWORD(BitMapHeader[12].Buffer) -= v9;
      *(&BitMapHeader[12].SizeOfBitMap + 1) += v9;
      v7 = (unsigned int)BitMapHeader[12].Buffer;
      v8 = *(&BitMapHeader[12].SizeOfBitMap + 1);
    }
    while ( v7 );
  }
  v10 = 0;
  v11 = &BitMapHeader[12].SizeOfBitMap + 1;
  while ( v10 < 0x40 )
  {
    if ( !LODWORD(BitMapHeader[12].Buffer) )
    {
      NextForwardRunClear = RtlFindNextForwardRunClear(BitMapHeader, *v11, &BitMapHeader[12].SizeOfBitMap + 1);
      LODWORD(BitMapHeader[12].Buffer) = NextForwardRunClear;
      if ( !NextForwardRunClear )
      {
        v13 = RtlFindNextForwardRunClear(BitMapHeader, 0, &BitMapHeader[12].SizeOfBitMap + 1);
        LODWORD(BitMapHeader[12].Buffer) = v13;
        if ( !v13 )
        {
          *a3 = 1;
          break;
        }
        WimpFSFIntegrityReportBlockFailure(BitMapHeader, *v11);
      }
    }
    v14 = (unsigned int)BitMapHeader[12].Buffer;
    v15 = *(struct _FILE_OBJECT **)&BitMapHeader[10].SizeOfBitMap;
    v16 = (struct _FLT_INSTANCE *)Buffer[0x8000];
    if ( v14 >= 64 - v10 )
      v14 = 64 - v10;
    ByteOffset.QuadPart = (unsigned __int64)*v11 << 12;
    v6 = FltReadFile(v16, v15, &ByteOffset, v14 << 12, Buffer, 1u, &BytesRead, 0, 0);
    if ( v6 < 0 )
      break;
    ByteOffset.QuadPart = (unsigned __int64)*v11 << 12;
    v6 = WimFSFCheckIntegrityOfBlocks(BitMapHeader, ByteOffset.QuadPart, (__int64)Buffer, BytesRead);
    if ( v6 < 0 )
      break;
    *v11 += v14;
    LODWORD(BitMapHeader[12].Buffer) -= v14;
    v10 += v14;
  }
  WimpFSFSetPriorities(&v20, 1);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140028ef4  push    rbx
0x140028ef6  push    rbp
0x140028ef7  push    rsi
0x140028ef8  push    rdi
0x140028ef9  push    r13
0x140028efb  push    r14
0x140028efd  push    r15
0x140028eff  sub     rsp, 80h
0x140028f06  mov     rax, cs:__security_cookie
0x140028f0d  xor     rax, rsp
0x140028f10  mov     [rsp+0B8h+var_48], rax
0x140028f15  mov     r13, rcx
0x140028f18  mov     [rsp+0B8h+var_68], 0
0x140028f20  xorps   xmm0, xmm0
0x140028f23  mov     qword ptr [rsp+0B8h+ByteOffset], 0
0x140028f2c  lea     rcx, [rsp+0B8h+var_58]
0x140028f31  mov     r15, r8
0x140028f34  movups  [rsp+0B8h+var_58], xmm0
0x140028f39  mov     rbx, rdx
0x140028f3c  xor     r14d, r14d
0x140028f3f  call    WimpFSFSetBackgroundPriorities
0x140028f44  mov     eax, [rbx+0C8h]
0x140028f4a  test    eax, eax
0x140028f4c  jz      short loc_140028F90
0x140028f4e  mov     edx, [rbx+0C4h]; StartingIndex
0x140028f54  mov     edi, 40h ; '@'
0x140028f59  mov     rcx, rbx; BitMapHeader
0x140028f5c  cmp     eax, edi
0x140028f5e  cmovb   edi, eax
0x140028f61  mov     r8d, edi; Length
0x140028f64  call    cs:__imp_RtlAreBitsSet
0x140028f6b  nop     dword ptr [rax+rax+00h]
0x140028f70  test    al, al
0x140028f72  jz      short loc_140028F90
0x140028f74  sub     [rbx+0C8h], edi
0x140028f7a  add     [rbx+0C4h], edi
0x140028f80  mov     eax, [rbx+0C8h]
0x140028f86  mov     edx, [rbx+0C4h]
0x140028f8c  test    eax, eax
0x140028f8e  jnz     short loc_140028F54
0x140028f90  xor     ebp, ebp
0x140028f92  lea     rdi, [rbx+0C4h]
0x140028f99  cmp     ebp, 40h ; '@'
0x140028f9c  jnb     loc_14002909D
0x140028fa2  cmp     dword ptr [rbx+0C8h], 0
0x140028fa9  jnz     short loc_140028FF5
0x140028fab  mov     edx, [rdi]; FromIndex
0x140028fad  mov     r8, rdi; StartingRunIndex
0x140028fb0  mov     rcx, rbx; BitMapHeader
0x140028fb3  call    cs:__imp_RtlFindNextForwardRunClear
0x140028fba  nop     dword ptr [rax+rax+00h]
0x140028fbf  mov     [rbx+0C8h], eax
0x140028fc5  test    eax, eax
0x140028fc7  jnz     short loc_140028FF5
0x140028fc9  mov     r8, rdi; StartingRunIndex
0x140028fcc  xor     edx, edx; FromIndex
0x140028fce  mov     rcx, rbx; BitMapHeader
0x140028fd1  call    cs:__imp_RtlFindNextForwardRunClear
0x140028fd8  nop     dword ptr [rax+rax+00h]
0x140028fdd  mov     [rbx+0C8h], eax
0x140028fe3  test    eax, eax
0x140028fe5  jz      loc_140029099
0x140028feb  mov     edx, [rdi]
0x140028fed  mov     rcx, rbx
0x140028ff0  call    WimpFSFIntegrityReportBlockFailure
0x140028ff5  mov     esi, [rbx+0C8h]
0x140028ffb  lea     r8, [rsp+0B8h+ByteOffset]; ByteOffset
0x140029000  mov     rdx, [rbx+0A0h]; FileObject
0x140029007  mov     eax, 40h ; '@'
0x14002900c  mov     rcx, [r13+40000h]; InitiatingInstance
0x140029013  sub     eax, ebp
0x140029015  cmp     esi, eax
0x140029017  mov     [rsp+0B8h+CallbackContext], 0; CallbackContext
0x140029020  mov     [rsp+0B8h+CallbackRoutine], 0; CallbackRoutine
0x140029029  cmovnb  esi, eax
0x14002902c  mov     eax, [rdi]
0x14002902e  shl     rax, 0Ch
0x140029032  mov     r9d, esi
0x140029035  mov     qword ptr [rsp+0B8h+ByteOffset], rax
0x14002903a  lea     rax, [rsp+0B8h+var_68]
0x14002903f  mov     [rsp+0B8h+BytesRead], rax; BytesRead
0x140029044  mov     [rsp+0B8h+Flags], 1; Flags
0x14002904c  shl     r9d, 0Ch; Length
0x140029050  mov     [rsp+0B8h+Buffer], r13; Buffer
0x140029055  call    cs:__imp_FltReadFile
0x14002905c  nop     dword ptr [rax+rax+00h]
0x140029061  mov     r14d, eax
0x140029064  test    eax, eax
0x140029066  js      short loc_14002909D
0x140029068  mov     edx, [rdi]
0x14002906a  mov     r8, r13
0x14002906d  mov     r9d, [rsp+0B8h+var_68]
0x140029072  mov     rcx, rbx; BitMapHeader
0x140029075  shl     rdx, 0Ch
0x140029079  mov     qword ptr [rsp+0B8h+ByteOffset], rdx
0x14002907e  call    WimFSFCheckIntegrityOfBlocks
0x140029083  mov     r14d, eax
0x140029086  test    eax, eax
0x140029088  js      short loc_14002909D
0x14002908a  add     [rdi], esi
0x14002908c  sub     [rbx+0C8h], esi
0x140029092  add     ebp, esi
0x140029094  jmp     loc_140028F99
0x140029099  mov     byte ptr [r15], 1
0x14002909d  mov     dl, 1
0x14002909f  lea     rcx, [rsp+0B8h+var_58]
0x1400290a4  call    WimpFSFSetPriorities
0x1400290a9  mov     eax, r14d
0x1400290ac  mov     rcx, [rsp+0B8h+var_48]
0x1400290b1  xor     rcx, rsp; StackCookie
0x1400290b4  call    __security_check_cookie
0x1400290b9  add     rsp, 80h
0x1400290c0  pop     r15
0x1400290c2  pop     r14
0x1400290c4  pop     r13
0x1400290c6  pop     rdi
0x1400290c7  pop     rsi
0x1400290c8  pop     rbp
0x1400290c9  pop     rbx
0x1400290ca  retn
```

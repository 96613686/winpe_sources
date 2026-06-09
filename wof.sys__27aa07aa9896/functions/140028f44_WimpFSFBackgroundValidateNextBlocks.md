# WimpFSFBackgroundValidateNextBlocks

- ea: `0x140028f44`
- end: `0x14002911c`
- name: `WimpFSFBackgroundValidateNextBlocks`
- size: `472`
- prototype: `__int64 __fastcall(PVOID Buffer, PRTL_BITMAP BitMapHeader)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140029130`

## callees

- `0x140011560`
- `0x140027ffc`
- `0x140028f44`
- `0x140029ca0`
- `0x14002aa88`
- `0x14002ab90`

## import_xrefs

- `ntoskrnl!RtlAreBitsSet` at `0x140028fb4`
- `ntoskrnl!RtlAreBitsSet` at `0x140028fb4`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140029003`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140029021`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140029003`
- `ntoskrnl!RtlFindNextForwardRunClear` at `0x140029021`
- `FLTMGR!FltReadFile` at `0x1400290a5`
- `FLTMGR!FltReadFile` at `0x1400290a5`

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
0x140028f44  push    rbx
0x140028f46  push    rbp
0x140028f47  push    rsi
0x140028f48  push    rdi
0x140028f49  push    r13
0x140028f4b  push    r14
0x140028f4d  push    r15
0x140028f4f  sub     rsp, 80h
0x140028f56  mov     rax, cs:__security_cookie
0x140028f5d  xor     rax, rsp
0x140028f60  mov     [rsp+0B8h+var_48], rax
0x140028f65  mov     r13, rcx
0x140028f68  mov     [rsp+0B8h+var_68], 0
0x140028f70  xorps   xmm0, xmm0
0x140028f73  mov     qword ptr [rsp+0B8h+ByteOffset], 0
0x140028f7c  lea     rcx, [rsp+0B8h+var_58]
0x140028f81  mov     r15, r8
0x140028f84  movups  [rsp+0B8h+var_58], xmm0
0x140028f89  mov     rbx, rdx
0x140028f8c  xor     r14d, r14d
0x140028f8f  call    WimpFSFSetBackgroundPriorities
0x140028f94  mov     eax, [rbx+0C8h]
0x140028f9a  test    eax, eax
0x140028f9c  jz      short loc_140028FE0
0x140028f9e  mov     edx, [rbx+0C4h]; StartingIndex
0x140028fa4  mov     edi, 40h ; '@'
0x140028fa9  mov     rcx, rbx; BitMapHeader
0x140028fac  cmp     eax, edi
0x140028fae  cmovb   edi, eax
0x140028fb1  mov     r8d, edi; Length
0x140028fb4  call    cs:__imp_RtlAreBitsSet
0x140028fbb  nop     dword ptr [rax+rax+00h]
0x140028fc0  test    al, al
0x140028fc2  jz      short loc_140028FE0
0x140028fc4  sub     [rbx+0C8h], edi
0x140028fca  add     [rbx+0C4h], edi
0x140028fd0  mov     eax, [rbx+0C8h]
0x140028fd6  mov     edx, [rbx+0C4h]
0x140028fdc  test    eax, eax
0x140028fde  jnz     short loc_140028FA4
0x140028fe0  xor     ebp, ebp
0x140028fe2  lea     rdi, [rbx+0C4h]
0x140028fe9  cmp     ebp, 40h ; '@'
0x140028fec  jnb     loc_1400290ED
0x140028ff2  cmp     dword ptr [rbx+0C8h], 0
0x140028ff9  jnz     short loc_140029045
0x140028ffb  mov     edx, [rdi]; FromIndex
0x140028ffd  mov     r8, rdi; StartingRunIndex
0x140029000  mov     rcx, rbx; BitMapHeader
0x140029003  call    cs:__imp_RtlFindNextForwardRunClear
0x14002900a  nop     dword ptr [rax+rax+00h]
0x14002900f  mov     [rbx+0C8h], eax
0x140029015  test    eax, eax
0x140029017  jnz     short loc_140029045
0x140029019  mov     r8, rdi; StartingRunIndex
0x14002901c  xor     edx, edx; FromIndex
0x14002901e  mov     rcx, rbx; BitMapHeader
0x140029021  call    cs:__imp_RtlFindNextForwardRunClear
0x140029028  nop     dword ptr [rax+rax+00h]
0x14002902d  mov     [rbx+0C8h], eax
0x140029033  test    eax, eax
0x140029035  jz      loc_1400290E9
0x14002903b  mov     edx, [rdi]
0x14002903d  mov     rcx, rbx
0x140029040  call    WimpFSFIntegrityReportBlockFailure
0x140029045  mov     esi, [rbx+0C8h]
0x14002904b  lea     r8, [rsp+0B8h+ByteOffset]; ByteOffset
0x140029050  mov     rdx, [rbx+0A0h]; FileObject
0x140029057  mov     eax, 40h ; '@'
0x14002905c  mov     rcx, [r13+40000h]; InitiatingInstance
0x140029063  sub     eax, ebp
0x140029065  cmp     esi, eax
0x140029067  mov     [rsp+0B8h+CallbackContext], 0; CallbackContext
0x140029070  mov     [rsp+0B8h+CallbackRoutine], 0; CallbackRoutine
0x140029079  cmovnb  esi, eax
0x14002907c  mov     eax, [rdi]
0x14002907e  shl     rax, 0Ch
0x140029082  mov     r9d, esi
0x140029085  mov     qword ptr [rsp+0B8h+ByteOffset], rax
0x14002908a  lea     rax, [rsp+0B8h+var_68]
0x14002908f  mov     [rsp+0B8h+BytesRead], rax; BytesRead
0x140029094  mov     [rsp+0B8h+Flags], 1; Flags
0x14002909c  shl     r9d, 0Ch; Length
0x1400290a0  mov     [rsp+0B8h+Buffer], r13; Buffer
0x1400290a5  call    cs:__imp_FltReadFile
0x1400290ac  nop     dword ptr [rax+rax+00h]
0x1400290b1  mov     r14d, eax
0x1400290b4  test    eax, eax
0x1400290b6  js      short loc_1400290ED
0x1400290b8  mov     edx, [rdi]
0x1400290ba  mov     r8, r13
0x1400290bd  mov     r9d, [rsp+0B8h+var_68]
0x1400290c2  mov     rcx, rbx; BitMapHeader
0x1400290c5  shl     rdx, 0Ch
0x1400290c9  mov     qword ptr [rsp+0B8h+ByteOffset], rdx
0x1400290ce  call    WimFSFCheckIntegrityOfBlocks
0x1400290d3  mov     r14d, eax
0x1400290d6  test    eax, eax
0x1400290d8  js      short loc_1400290ED
0x1400290da  add     [rdi], esi
0x1400290dc  sub     [rbx+0C8h], esi
0x1400290e2  add     ebp, esi
0x1400290e4  jmp     loc_140028FE9
0x1400290e9  mov     byte ptr [r15], 1
0x1400290ed  mov     dl, 1
0x1400290ef  lea     rcx, [rsp+0B8h+var_58]
0x1400290f4  call    WimpFSFSetPriorities
0x1400290f9  mov     eax, r14d
0x1400290fc  mov     rcx, [rsp+0B8h+var_48]
0x140029101  xor     rcx, rsp; StackCookie
0x140029104  call    __security_check_cookie
0x140029109  add     rsp, 80h
0x140029110  pop     r15
0x140029112  pop     r14
0x140029114  pop     r13
0x140029116  pop     rdi
0x140029117  pop     rsi
0x140029118  pop     rbp
0x140029119  pop     rbx
0x14002911a  retn
```

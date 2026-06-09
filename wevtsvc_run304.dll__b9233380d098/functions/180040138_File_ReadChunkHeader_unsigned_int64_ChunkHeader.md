# File::ReadChunkHeader(unsigned __int64,ChunkHeader &)

- ea: `0x180040138`
- end: `0x1800402dd`
- name: `?ReadChunkHeader@File@@AEAAX_KAEAUChunkHeader@@@Z`
- size: `421`
- prototype: `void(File *__hidden this, unsigned __int64, struct ChunkHeader *)`
- caller_count: `11`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x180009384`
- `0x180009764`
- `0x1800097f8`
- `0x180012560`
- `0x18003ef70`
- `0x18003f68c`
- `0x18003f950`
- `0x18003fbd0`
- `0x18003ff2c`
- `0x1800402e4`
- `0x1800b3040`

## callees

- `0x180040138`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180040261`
- `ntdll!RtlSetLastWin32Error` at `0x180040261`
- `ntdll!NtReadFile` at `0x1800401d3`
- `ntdll!NtReadFile` at `0x1800401d3`
- `ntdll!RtlNtStatusToDosError` at `0x180040254`
- `ntdll!RtlNtStatusToDosError` at `0x180040254`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall File::ReadChunkHeader(File *this, __int64 a2, struct ChunkHeader *Buffer)
{
  union _LARGE_INTEGER v3; // rdx
  int v4; // eax
  _OWORD *v5; // rax
  ULONG v6; // ebx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-19h] BYREF
  __int128 pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  __int64 v9; // [rsp+70h] [rbp+7h]
  ULONG v10; // [rsp+78h] [rbp+Fh]
  int v11; // [rsp+7Ch] [rbp+13h]
  int v12; // [rsp+80h] [rbp+17h]
  struct ChunkHeader *v13; // [rsp+88h] [rbp+1Fh]
  __int64 v14; // [rsp+90h] [rbp+27h]
  struct ChunkHeader *v15; // [rsp+98h] [rbp+2Fh]
  char *v16; // [rsp+A0h] [rbp+37h]
  int v17; // [rsp+A8h] [rbp+3Fh]
  ULONG v18; // [rsp+ACh] [rbp+43h]
  char v19; // [rsp+B0h] [rbp+47h]
  char v20; // [rsp+B1h] [rbp+48h]
  union _LARGE_INTEGER ByteOffset; // [rsp+D0h] [rbp+67h] BYREF

  v3.QuadPart = (a2 << 16) + 4096;
  if ( *((_QWORD *)this + 21) == v3.QuadPart )
  {
    v5 = (_OWORD *)*((_QWORD *)this + 22);
    *(_OWORD *)Buffer = *v5;
    *((_OWORD *)Buffer + 1) = v5[1];
    *((_OWORD *)Buffer + 2) = v5[2];
    *((_OWORD *)Buffer + 3) = v5[3];
    *((_OWORD *)Buffer + 4) = v5[4];
    *((_OWORD *)Buffer + 5) = v5[5];
    *((_OWORD *)Buffer + 6) = v5[6];
    *((_OWORD *)Buffer + 7) = v5[7];
  }
  else
  {
    v14 = -1;
    v15 = Buffer;
    v17 = 128;
    v20 = 0;
    v13 = Buffer;
    if ( Buffer )
      v16 = (char *)Buffer + 128;
    else
      v16 = 0;
    IoStatusBlock = 0;
    ByteOffset = v3;
    v4 = NtReadFile(*((HANDLE *)this + 84), 0, 0, 0, &IoStatusBlock, Buffer, 0x80u, &ByteOffset, 0);
    if ( v4 < 0 )
    {
      v14 = -1;
      v19 = 2;
      v6 = RtlNtStatusToDosError(v4);
      v18 = v6;
      RtlSetLastWin32Error(v6);
      if ( !v6 )
        v6 = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids, v6);
      }
      pExceptionObject = 0;
      v9 = 0;
      v10 = v6;
      v11 = -1;
      v12 = 112;
      throw (EvtException *)&pExceptionObject;
    }
  }
}

```

## disassembly

```asm
0x180040138  mov     [rsp-8+arg_8], rbx
0x18004013d  push    rbp
0x18004013e  lea     rbp, [rsp-57h]
0x180040143  sub     rsp, 0C0h
0x18004014a  shl     rdx, 10h
0x18004014e  add     rdx, 1000h
0x180040155  cmp     [rcx+0A8h], rdx
0x18004015c  jz      loc_1800401EE
0x180040162  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180040166  mov     [rbp+57h+var_30], rbx
0x18004016a  mov     [rbp+57h+var_28], r8
0x18004016e  mov     r9d, 80h
0x180040174  mov     [rbp+57h+var_18], r9d
0x180040178  mov     [rbp+57h+var_F], 0
0x18004017c  mov     [rbp+57h+var_38], r8
0x180040180  test    r8, r8
0x180040183  jz      loc_18004023D
0x180040189  lea     rax, [r8+80h]
0x180040190  mov     [rbp+57h+var_20], rax
0x180040194  xorps   xmm0, xmm0
0x180040197  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18004019b  mov     qword ptr [rbp+57h+arg_0], rdx
0x18004019f  mov     [rsp+0C0h+Key], 0; Key
0x1800401a8  lea     rax, [rbp+57h+arg_0]
0x1800401ac  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x1800401b1  mov     [rsp+0C0h+Length], r9d; Length
0x1800401b6  mov     [rsp+0C0h+Buffer], r8; Buffer
0x1800401bb  lea     rax, [rbp+57h+var_70]
0x1800401bf  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x1800401c4  xor     r9d, r9d; ApcContext
0x1800401c7  xor     r8d, r8d; ApcRoutine
0x1800401ca  xor     edx, edx; Event
0x1800401cc  mov     rcx, [rcx+2A0h]; FileHandle
0x1800401d3  call    cs:__imp_NtReadFile
0x1800401d9  test    eax, eax
0x1800401db  js      short loc_18004024A
0x1800401dd  mov     rbx, [rsp+0C0h+arg_8]
0x1800401e5  add     rsp, 0C0h
0x1800401ec  pop     rbp
0x1800401ed  retn
0x1800401ee  mov     rax, [rcx+0B0h]
0x1800401f5  movups  xmm0, xmmword ptr [rax]
0x1800401f8  movaps  xmmword ptr [r8], xmm0
0x1800401fc  movups  xmm1, xmmword ptr [rax+10h]
0x180040200  movaps  xmmword ptr [r8+10h], xmm1
0x180040205  movups  xmm0, xmmword ptr [rax+20h]
0x180040209  movaps  xmmword ptr [r8+20h], xmm0
0x18004020e  movups  xmm1, xmmword ptr [rax+30h]
0x180040212  movaps  xmmword ptr [r8+30h], xmm1
0x180040217  movups  xmm0, xmmword ptr [rax+40h]
0x18004021b  movaps  xmmword ptr [r8+40h], xmm0
0x180040220  movups  xmm1, xmmword ptr [rax+50h]
0x180040224  movaps  xmmword ptr [r8+50h], xmm1
0x180040229  movups  xmm0, xmmword ptr [rax+60h]
0x18004022d  movaps  xmmword ptr [r8+60h], xmm0
0x180040232  movups  xmm1, xmmword ptr [rax+70h]
0x180040236  movaps  xmmword ptr [r8+70h], xmm1
0x18004023b  jmp     short loc_1800401DD
0x18004023d  mov     [rbp+57h+var_20], 0
0x180040245  jmp     loc_180040194
0x18004024a  mov     [rbp+57h+var_30], rbx
0x18004024e  mov     [rbp+57h+var_10], 2
0x180040252  mov     ecx, eax; Status
0x180040254  call    cs:__imp_RtlNtStatusToDosError
0x18004025a  mov     ebx, eax
0x18004025c  mov     [rbp+57h+var_14], eax
0x18004025f  mov     ecx, eax; LastError
0x180040261  call    cs:__imp_RtlSetLastWin32Error
0x180040267  mov     eax, 507h
0x18004026c  test    ebx, ebx
0x18004026e  cmovz   ebx, eax
0x180040271  lea     rax, WPP_GLOBAL_Control
0x180040278  mov     rcx, cs:WPP_GLOBAL_Control
0x18004027f  cmp     rcx, rax
0x180040282  jz      short loc_1800402AB
0x180040284  test    dword ptr [rcx+1Ch], 8000h
0x18004028b  jz      short loc_1800402AB
0x18004028d  cmp     byte ptr [rcx+19h], 2
0x180040291  jb      short loc_1800402AB
0x180040293  mov     edx, 0Ch
0x180040298  mov     r9d, ebx
0x18004029b  lea     r8, WPP_978fcd34fd223a1a0030c3cde256baa0_Traceguids
0x1800402a2  mov     rcx, [rcx+10h]
0x1800402a6  call    WPP_SF_d
0x1800402ab  xorps   xmm0, xmm0
0x1800402ae  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800402b3  mov     [rbp+57h+var_50], 0
0x1800402bb  mov     [rbp+57h+var_48], ebx
0x1800402be  mov     [rbp+57h+var_44], 0FFFFFFFFh
0x1800402c5  mov     [rbp+57h+var_40], 70h ; 'p'
0x1800402cc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800402d3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800402d7  call    _CxxThrowException_0
```

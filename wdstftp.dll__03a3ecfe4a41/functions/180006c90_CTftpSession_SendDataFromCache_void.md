# CTftpSession::SendDataFromCache(void *)

- ea: `0x180006c90`
- end: `0x180007105`
- name: `?SendDataFromCache@CTftpSession@@AEAAKPEAX@Z`
- size: `1141`
- prototype: `__int64 __fastcall(CTftpSession *this, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000728c`

## callees

- `0x180006c90`
- `0x1800091a4`
- `0x18000bbe0`
- `0x18000c49c`
- `0x18000cdd0`
- `0x18003c084`
- `0x18003ce78`
- `0x180060e70`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180006cda`
- `KERNEL32!EnterCriticalSection` at `0x180006cda`
- `KERNEL32!LeaveCriticalSection` at `0x1800070e5`
- `KERNEL32!LeaveCriticalSection` at `0x1800070e5`
- `WDSSRV!WdsSendPacketList` at `0x180006fa7`
- `WDSSRV!WdsSendPacketList` at `0x180006fa7`
- `WDSSRV!WdsPacketFree` at `0x180006dab`
- `WDSSRV!WdsPacketFree` at `0x18000701e`
- `WDSSRV!WdsPacketFree` at `0x180006dab`
- `WDSSRV!WdsPacketFree` at `0x18000701e`

## string_xrefs

- `0x180006f26`: `TftpSession[%s] - Cache Hit: Block#=%u, Size=%u`
- `0x180006e57`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`
- `0x180006e97`: `base\eco\wds\transport\server\tftp\tftpfilereader.cpp`

## pseudocode

```c
__int64 __fastcall CTftpSession::SendDataFromCache(CTftpSession *this, void *a2)
{
  void *v3; // rdi
  int v4; // r13d
  struct CMemoryBuffer *v5; // rsi
  int v6; // edx
  bool v7; // zf
  int i; // r12d
  __int64 v9; // r8
  unsigned int v10; // ecx
  int v11; // ebx
  unsigned int v12; // eax
  union _ULARGE_INTEGER v13; // rcx
  union _ULARGE_INTEGER v14; // rbx
  unsigned int v15; // ebx
  unsigned __int16 v16; // si
  unsigned int Data; // r15d
  const char *v18; // rdx
  __int64 v19; // r9
  struct CMemoryBuffer *v20; // rcx
  _ULARGE_INTEGER v21; // r8
  __int64 v22; // rdi
  LPCRITICAL_SECTION *v23; // rsi
  const char *v24; // rdx
  const char *v25; // rdx
  const char *v26; // rdx
  unsigned int v27; // eax
  const char *v28; // rdx
  const char *v29; // rdx
  const char *v30; // rdx
  _QWORD *v31; // rax
  _QWORD *v32; // rbx
  _QWORD *v33; // rcx
  _QWORD *v34; // rdx
  int *v36; // [rsp+20h] [rbp-58h]
  struct CMemoryBuffer *v37; // [rsp+30h] [rbp-48h] BYREF
  _ULARGE_INTEGER v38; // [rsp+38h] [rbp-40h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-38h]
  union _ULARGE_INTEGER v40; // [rsp+48h] [rbp-30h]
  __int128 v41; // [rsp+50h] [rbp-28h] BYREF
  int v42; // [rsp+64h] [rbp-14h]
  unsigned int v43; // [rsp+C0h] [rbp+48h] BYREF
  int v44; // [rsp+C8h] [rbp+50h] BYREF
  int v45; // [rsp+CCh] [rbp+54h]
  unsigned int v46; // [rsp+D0h] [rbp+58h]
  void *v47; // [rsp+D8h] [rbp+60h] BYREF

  v45 = HIDWORD(a2);
  v47 = 0;
  v44 = 0;
  v37 = 0;
  v3 = 0;
  v42 = 0;
  v4 = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 24);
  v5 = 0;
  v41 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  v6 = *((_DWORD *)this + 603);
  v7 = *((_DWORD *)this + 584) == v6;
  for ( i = *((_DWORD *)this + 584) - v6; !v7; --i )
  {
    v9 = *((unsigned int *)this + 583);
    v10 = v6 + *((_DWORD *)this + 602);
    v11 = *((_DWORD *)this + 583);
    v12 = v10 - 0x10000;
    if ( v10 <= 0xFFFF )
      v12 = v6 + *((_DWORD *)this + 602);
    v13 = *(union _ULARGE_INTEGER *)((char *)this + 2432);
    v46 = v12;
    v14.QuadPart = *((_QWORD *)this + 303) + (unsigned int)(v6 * v11);
    v40 = v14;
    if ( v14.QuadPart > v13.QuadPart )
      break;
    if ( v14.QuadPart == v13.QuadPart )
    {
      v3 = 0;
      v47 = 0;
      v15 = 0;
      i = 1;
LABEL_8:
      v16 = v46;
      goto LABEL_9;
    }
    v21.QuadPart = v14.QuadPart + v9 - 1;
    v38 = v21;
    if ( v21.QuadPart >= v13.QuadPart )
    {
      v21.QuadPart = v13.QuadPart - 1;
      v38.QuadPart = v13.QuadPart - 1;
    }
    v43 = v21.LowPart - v14.LowPart + 1;
    if ( ::lpCriticalSection[14].LockCount )
    {
      v22 = *((_QWORD *)this + 305);
      v23 = (LPCRITICAL_SECTION *)((char *)this + 2448);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 56), 0)
        || *(LPCRITICAL_SECTION *)(v22 + 88) == *v23
        || (unsigned int)CTptReadFile::ModifiedSinceOpen(*v23)
        || (Data = CTftpFileReader::MoveRequestToSharedReader(
                     (CTftpFileReader *)v22,
                     (struct CTptReadFile **)this + 306),
            !ElValidateWin32(Data, v24, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x1E2u)) )
      {
        Data = CTptReadFile::GetData(*v23, v14, v38, &v47, &v44, &v43);
        ElValidateWin32(Data, v26, "base\\eco\\wds\\transport\\server\\tftp\\tftpfilereader.cpp", 0x1EAu);
      }
      v27 = ElValidateWin32(Data, v25, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x3ADu);
      v5 = v37;
    }
    else
    {
      Data = CTptReadFile::GetData(*((LPCRITICAL_SECTION *)this + 307), v14, v21, &v47, &v44, &v43);
      v27 = ElValidateWin32(Data, v28, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x3B6u);
    }
    v3 = v47;
    if ( v27 )
      goto LABEL_35;
    if ( !v47 )
      break;
    v15 = v43;
    if ( !g_ErrLibTraceFunctionEx )
      goto LABEL_8;
    v16 = v46;
    LODWORD(v36) = v43;
    g_ErrLibTraceFunctionEx(
      0x400000u,
      L"TftpSession[%s] - Cache Hit: Block#=%u, Size=%u",
      *((_QWORD *)this + 272),
      v46,
      v36);
LABEL_9:
    Data = CTftpPacket::CreateDataPacket(v16, v3, v15, &v37);
    if ( ElValidateWin32(Data, v18, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x3D3u) )
    {
      v5 = v37;
      goto LABEL_35;
    }
    if ( v44 && v3 )
    {
      WdsPacketFree(*(_QWORD *)&::lpCriticalSection[4].LockCount, 0, v3, v19);
      v3 = 0;
      v47 = 0;
      v44 = 0;
    }
    v20 = v37;
    if ( (_QWORD)v41 )
    {
      *((_QWORD *)v37 + 7) = 0;
      *((_QWORD *)v20 + 8) = *((_QWORD *)&v41 + 1);
      *(_QWORD *)(*((_QWORD *)&v41 + 1) + 56LL) = v20;
      *((_QWORD *)&v41 + 1) = v20;
    }
    else
    {
      *((_QWORD *)&v41 + 1) = v37;
      *(_QWORD *)&v41 = v37;
      *((_QWORD *)v37 + 7) = 0;
      *((_QWORD *)v20 + 8) = 0;
    }
    ++v42;
    v5 = 0;
    v4 += *((_DWORD *)v20 + 12);
    v6 = ++*((_DWORD *)this + 603);
    v7 = i == 1;
    v37 = 0;
  }
  Data = WdsSendPacketList(*((_QWORD *)this + 280), (char *)this + 2184, (char *)this + 1120, &v41);
  if ( !ElValidateWin32(Data, v29, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x739u) )
  {
    LODWORD(v36) = v4;
    CPerfCounters::Batch((CPerfCounters *)&qword_1800779F0, 1u, 1, 0, v36);
  }
  ElValidateWin32(Data, v30, "base\\eco\\wds\\transport\\server\\tftp\\tftpsession.cpp", 0x3EBu);
LABEL_35:
  if ( v44 && v3 )
    WdsPacketFree(*(_QWORD *)&::lpCriticalSection[4].LockCount, 0, v3, v19);
  v31 = (_QWORD *)v41;
  if ( (_QWORD)v41 )
  {
    v32 = (_QWORD *)v41;
    do
    {
      v33 = v32;
      if ( v31 == *((_QWORD **)&v41 + 1) )
      {
        v41 = 0u;
        v32 = 0;
      }
      else if ( v32 == v31 )
      {
        *(_QWORD *)&v41 = v31[7];
        *(_QWORD *)(v41 + 64) = 0;
        v32 = (_QWORD *)v41;
      }
      else if ( v32 == *((_QWORD **)&v41 + 1) )
      {
        v32 = 0;
        *((_QWORD *)&v41 + 1) = *(_QWORD *)(*((_QWORD *)&v41 + 1) + 64LL);
        *(_QWORD *)(*((_QWORD *)&v41 + 1) + 56LL) = 0;
      }
      else
      {
        v34 = v32 + 7;
        v32 = (_QWORD *)v32[7];
        *(_QWORD *)(v33[8] + 56LL) = v32;
        *(_QWORD *)(*v34 + 64LL) = v33[8];
      }
      --v42;
      (*(void (__fastcall **)(_QWORD *))(*v33 + 8LL))(v33);
      v31 = (_QWORD *)v41;
    }
    while ( v32 );
  }
  if ( v5 )
    (*(void (__fastcall **)(struct CMemoryBuffer *))(*(_QWORD *)v5 + 8LL))(v5);
  LeaveCriticalSection(lpCriticalSection);
  return Data;
}

```

## disassembly

```asm
0x180006c90  mov     qword ptr [rsp-40h+arg_8], rdx
0x180006c95  push    rbp
0x180006c96  push    rbx
0x180006c97  push    rsi
0x180006c98  push    rdi
0x180006c99  push    r12
0x180006c9b  push    r13
0x180006c9d  push    r14
0x180006c9f  push    r15
0x180006ca1  mov     rbp, rsp
0x180006ca4  sub     rsp, 78h
0x180006ca8  xor     r15d, r15d
0x180006cab  lea     rax, [rcx+18h]
0x180006caf  mov     r14, rcx
0x180006cb2  mov     [rbp+arg_18], r15
0x180006cb6  xorps   xmm0, xmm0
0x180006cb9  mov     [rbp+arg_8], r15d
0x180006cbd  mov     rcx, rax; lpCriticalSection
0x180006cc0  mov     [rbp+var_48], r15
0x180006cc4  mov     edi, r15d
0x180006cc7  mov     [rbp+var_14], r15d
0x180006ccb  mov     r13d, r15d
0x180006cce  mov     [rbp+lpCriticalSection], rax
0x180006cd2  mov     esi, r15d
0x180006cd5  movdqu  [rbp+var_28], xmm0
0x180006cda  call    cs:__imp_EnterCriticalSection
0x180006ce1  nop     dword ptr [rax+rax+00h]
0x180006ce6  mov     r12d, [r14+920h]
0x180006ced  mov     edx, [r14+96Ch]
0x180006cf4  sub     r12d, edx
0x180006cf7  jz      loc_180006F8E
0x180006cfd  mov     ecx, [r14+968h]
0x180006d04  mov     r8d, [r14+91Ch]
0x180006d0b  add     ecx, edx
0x180006d0d  cmp     ecx, 0FFFFh
0x180006d13  mov     ebx, r8d
0x180006d16  lea     eax, [rcx-10000h]
0x180006d1c  cmovbe  eax, ecx
0x180006d1f  mov     rcx, [r14+980h]
0x180006d26  imul    ebx, edx
0x180006d29  mov     [rbp+arg_10], eax
0x180006d2c  add     rbx, [r14+978h]
0x180006d33  mov     [rbp+var_30], rbx
0x180006d37  cmp     rbx, rcx
0x180006d3a  ja      loc_180006F8E
0x180006d40  jnz     loc_180006DE5
0x180006d46  mov     rdi, r15
0x180006d49  mov     [rbp+arg_18], r15
0x180006d4d  mov     ebx, r15d
0x180006d50  mov     r12d, 1
0x180006d56  mov     esi, [rbp+arg_10]
0x180006d59  lea     r9, [rbp+var_48]; struct CMemoryBuffer **
0x180006d5d  mov     r8d, ebx; unsigned int
0x180006d60  mov     rdx, rdi; void *
0x180006d63  movzx   ecx, si; unsigned __int16
0x180006d66  call    ?CreateDataPacket@CTftpPacket@@SAKGPEAXKPEAPEAVCMemoryBuffer@@@Z; CTftpPacket::CreateDataPacket(ushort,void *,ulong,CMemoryBuffer * *)
0x180006d6b  mov     r9d, 3D3h; unsigned int
0x180006d71  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006d78  mov     ecx, eax; unsigned int
0x180006d7a  mov     r15d, eax
0x180006d7d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006d82  test    eax, eax
0x180006d84  jnz     loc_180006F88
0x180006d8a  xor     r15d, r15d
0x180006d8d  cmp     [rbp+arg_8], r15d
0x180006d91  jz      short loc_180006DC2
0x180006d93  test    rdi, rdi
0x180006d96  jz      short loc_180006DC2
0x180006d98  mov     rcx, cs:lpCriticalSection
0x180006d9f  mov     r8, rdi
0x180006da2  xor     edx, edx
0x180006da4  mov     rcx, [rcx+0A8h]
0x180006dab  call    cs:__imp_WdsPacketFree
0x180006db2  nop     dword ptr [rax+rax+00h]
0x180006db7  mov     edi, r15d
0x180006dba  mov     [rbp+arg_18], r15
0x180006dbe  mov     [rbp+arg_8], r15d
0x180006dc2  mov     rcx, [rbp+var_48]
0x180006dc6  cmp     qword ptr [rbp+var_28], r15
0x180006dca  jnz     loc_180006F4B
0x180006dd0  mov     qword ptr [rbp+var_28+8], rcx
0x180006dd4  mov     qword ptr [rbp+var_28], rcx
0x180006dd8  mov     [rcx+38h], r15
0x180006ddc  mov     [rcx+40h], r15
0x180006de0  jmp     loc_180006F63
0x180006de5  dec     r8
0x180006de8  add     r8, rbx
0x180006deb  mov     qword ptr [rbp+var_40], r8
0x180006def  cmp     r8, rcx
0x180006df2  jb      short loc_180006DFC
0x180006df4  lea     r8, [rcx-1]; union _ULARGE_INTEGER
0x180006df8  mov     qword ptr [rbp+var_40], r8
0x180006dfc  mov     eax, r8d
0x180006dff  sub     eax, ebx
0x180006e01  inc     eax
0x180006e03  mov     [rbp+arg_0], eax
0x180006e06  mov     rax, cs:lpCriticalSection
0x180006e0d  cmp     [rax+238h], r15d
0x180006e14  jz      loc_180006EC3
0x180006e1a  mov     rdi, [r14+988h]
0x180006e21  lea     rsi, [r14+990h]
0x180006e28  mov     eax, r15d
0x180006e2b  lock xadd [rdi+38h], eax
0x180006e30  test    eax, eax
0x180006e32  jz      short loc_180006E6C
0x180006e34  mov     rcx, [rsi]; lpCriticalSection
0x180006e37  cmp     [rdi+58h], rcx
0x180006e3b  jz      short loc_180006E6C
0x180006e3d  call    ?ModifiedSinceOpen@CTptReadFile@@QEAAHXZ; CTptReadFile::ModifiedSinceOpen(void)
0x180006e42  test    eax, eax
0x180006e44  jnz     short loc_180006E6C
0x180006e46  mov     rdx, rsi; struct CTptReadFile **
0x180006e49  mov     rcx, rdi; this
0x180006e4c  call    ?MoveRequestToSharedReader@CTftpFileReader@@AEAAKPEAPEAVCTptReadFile@@@Z; CTftpFileReader::MoveRequestToSharedReader(CTptReadFile * *)
0x180006e51  mov     r9d, 1E2h; unsigned int
0x180006e57  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006e5e  mov     ecx, eax; unsigned int
0x180006e60  mov     r15d, eax
0x180006e63  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006e68  test    eax, eax
0x180006e6a  jnz     short loc_180006EA8
0x180006e6c  mov     r8, qword ptr [rbp+var_40]; union _ULARGE_INTEGER
0x180006e70  lea     rax, [rbp+arg_0]
0x180006e74  mov     rcx, [rsi]; lpCriticalSection
0x180006e77  lea     r9, [rbp+arg_18]; void **
0x180006e7b  mov     [rsp+78h+var_50], rax; unsigned int *
0x180006e80  mov     rdx, rbx; union _ULARGE_INTEGER
0x180006e83  lea     rax, [rbp+arg_8]
0x180006e87  mov     [rsp+78h+var_58], rax; int *
0x180006e8c  call    ?GetData@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAPEAXPEAHPEAK@Z; CTptReadFile::GetData(_ULARGE_INTEGER,_ULARGE_INTEGER,void * *,int *,ulong *)
0x180006e91  mov     r9d, 1EAh; unsigned int
0x180006e97  lea     r8, aBaseEcoWdsTran_3; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006e9e  mov     ecx, eax; unsigned int
0x180006ea0  mov     r15d, eax
0x180006ea3  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006ea8  mov     r9d, 3ADh; unsigned int
0x180006eae  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006eb5  mov     ecx, r15d; unsigned int
0x180006eb8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006ebd  mov     rsi, [rbp+var_48]
0x180006ec1  jmp     short loc_180006EFF
0x180006ec3  mov     rcx, [r14+998h]; lpCriticalSection
0x180006eca  lea     rax, [rbp+arg_0]
0x180006ece  mov     [rsp+78h+var_50], rax; unsigned int *
0x180006ed3  lea     r9, [rbp+arg_18]; void **
0x180006ed7  lea     rax, [rbp+arg_8]
0x180006edb  mov     rdx, rbx; union _ULARGE_INTEGER
0x180006ede  mov     [rsp+78h+var_58], rax; int *
0x180006ee3  call    ?GetData@CTptReadFile@@QEAAKT_ULARGE_INTEGER@@0PEAPEAXPEAHPEAK@Z; CTptReadFile::GetData(_ULARGE_INTEGER,_ULARGE_INTEGER,void * *,int *,ulong *)
0x180006ee8  mov     r9d, 3B6h; unsigned int
0x180006eee  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006ef5  mov     ecx, eax; unsigned int
0x180006ef7  mov     r15d, eax
0x180006efa  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006eff  mov     rdi, [rbp+arg_18]
0x180006f03  test    eax, eax
0x180006f05  jnz     loc_180006FFD
0x180006f0b  test    rdi, rdi
0x180006f0e  jz      short loc_180006F8E
0x180006f10  mov     rax, cs:?g_ErrLibTraceFunctionEx@@3P6AXKPEBGZZEA; void (*g_ErrLibTraceFunctionEx)(ulong,ushort const *,...)
0x180006f17  mov     ebx, [rbp+arg_0]
0x180006f1a  test    rax, rax
0x180006f1d  jz      loc_180006D56
0x180006f23  mov     esi, [rbp+arg_10]
0x180006f26  lea     rdx, aTftpsessionSCa; "TftpSession[%s] - Cache Hit: Block#=%u,"...
0x180006f2d  mov     r8, [r14+880h]
0x180006f34  mov     r9d, esi
0x180006f37  mov     ecx, 400000h
0x180006f3c  mov     dword ptr [rsp+78h+var_58], ebx
0x180006f40  call    cs:__guard_dispatch_icall_fptr
0x180006f46  jmp     loc_180006D59
0x180006f4b  mov     [rcx+38h], r15
0x180006f4f  mov     rax, qword ptr [rbp+var_28+8]
0x180006f53  mov     [rcx+40h], rax
0x180006f57  mov     rax, qword ptr [rbp+var_28+8]
0x180006f5b  mov     [rax+38h], rcx
0x180006f5f  mov     qword ptr [rbp+var_28+8], rcx
0x180006f63  inc     [rbp+var_14]
0x180006f66  mov     rsi, r15
0x180006f69  add     r13d, [rcx+30h]
0x180006f6d  inc     dword ptr [r14+96Ch]
0x180006f74  mov     edx, [r14+96Ch]
0x180006f7b  add     r12d, 0FFFFFFFFh
0x180006f7f  mov     [rbp+var_48], r15
0x180006f83  jmp     loc_180006CF7
0x180006f88  mov     rsi, [rbp+var_48]
0x180006f8c  jmp     short loc_180006FFD
0x180006f8e  mov     rcx, [r14+8C0h]
0x180006f95  lea     r8, [r14+460h]
0x180006f9c  lea     rdx, [r14+888h]
0x180006fa3  lea     r9, [rbp+var_28]
0x180006fa7  call    cs:__imp_WdsSendPacketList
0x180006fae  nop     dword ptr [rax+rax+00h]
0x180006fb3  mov     r9d, 739h; unsigned int
0x180006fb9  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006fc0  mov     ecx, eax; unsigned int
0x180006fc2  mov     r15d, eax
0x180006fc5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006fca  test    eax, eax
0x180006fcc  jnz     short loc_180006FE8
0x180006fce  lea     edx, [rax+1]; unsigned int
0x180006fd1  mov     dword ptr [rsp+78h+var_58], r13d
0x180006fd6  mov     r8d, edx
0x180006fd9  lea     rcx, qword_1800779F0; this
0x180006fe0  xor     r9d, r9d
0x180006fe3  call    ?Batch@CPerfCounters@@QEAAKKZZ; CPerfCounters::Batch(ulong,...)
0x180006fe8  mov     r9d, 3EBh; unsigned int
0x180006fee  lea     r8, aBaseEcoWdsTran_6; "base\\eco\\wds\\transport\\server\\tftp"...
0x180006ff5  mov     ecx, r15d; unsigned int
0x180006ff8  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180006ffd  xor     r13d, r13d
0x180007000  cmp     [rbp+arg_8], r13d
0x180007004  jz      short loc_18000702A
0x180007006  test    rdi, rdi
0x180007009  jz      short loc_18000702A
0x18000700b  mov     rcx, cs:lpCriticalSection
0x180007012  mov     r8, rdi
0x180007015  xor     edx, edx
0x180007017  mov     rcx, [rcx+0A8h]
0x18000701e  call    cs:__imp_WdsPacketFree
0x180007025  nop     dword ptr [rax+rax+00h]
0x18000702a  mov     rax, qword ptr [rbp+var_28]
0x18000702e  test    rax, rax
0x180007031  jz      loc_1800070CC
0x180007037  mov     rbx, rax
0x18000703a  mov     rcx, rbx
0x18000703d  test    rbx, rbx
0x180007040  jz      short loc_1800070AD
0x180007042  cmp     rax, qword ptr [rbp+var_28+8]
0x180007046  jnz     short loc_180007058
0x180007048  mov     rax, r13
0x18000704b  mov     qword ptr [rbp+var_28+8], r13
0x18000704f  mov     qword ptr [rbp+var_28], rax
0x180007053  mov     rbx, r13
0x180007056  jmp     short loc_1800070AA
0x180007058  cmp     rbx, rax
0x18000705b  jnz     short loc_180007072
0x18000705d  mov     rax, [rax+38h]
0x180007061  mov     qword ptr [rbp+var_28], rax
0x180007065  mov     [rax+40h], r13
0x180007069  mov     rax, qword ptr [rbp+var_28]
0x18000706d  mov     rbx, rax
0x180007070  jmp     short loc_1800070AA
0x180007072  mov     rax, qword ptr [rbp+var_28+8]
0x180007076  cmp     rbx, rax
0x180007079  jnz     short loc_18000708C
0x18000707b  mov     rax, [rax+40h]
0x18000707f  mov     rbx, r13
0x180007082  mov     qword ptr [rbp+var_28+8], rax
0x180007086  mov     [rax+38h], r13
0x18000708a  jmp     short loc_1800070A6
0x18000708c  mov     rax, [rcx+40h]
0x180007090  lea     rdx, [rbx+38h]
0x180007094  mov     rbx, [rdx]
0x180007097  mov     [rax+38h], rbx
0x18000709b  mov     rdx, [rdx]
0x18000709e  mov     rax, [rcx+40h]
0x1800070a2  mov     [rdx+40h], rax
0x1800070a6  mov     rax, qword ptr [rbp+var_28]
0x1800070aa  dec     [rbp+var_14]
0x1800070ad  test    rcx, rcx
0x1800070b0  jz      short loc_1800070C3
0x1800070b2  mov     rax, [rcx]
0x1800070b5  mov     rax, [rax+8]
0x1800070b9  call    cs:__guard_dispatch_icall_fptr
0x1800070bf  mov     rax, qword ptr [rbp+var_28]
0x1800070c3  test    rbx, rbx
0x1800070c6  jnz     loc_18000703A
0x1800070cc  test    rsi, rsi
0x1800070cf  jz      short loc_1800070E1
0x1800070d1  mov     rax, [rsi]
0x1800070d4  mov     rcx, rsi
0x1800070d7  mov     rax, [rax+8]
0x1800070db  call    cs:__guard_dispatch_icall_fptr
0x1800070e1  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800070e5  call    cs:__imp_LeaveCriticalSection
0x1800070ec  nop     dword ptr [rax+rax+00h]
0x1800070f1  mov     eax, r15d
0x1800070f4  add     rsp, 78h
0x1800070f8  pop     r15
0x1800070fa  pop     r14
0x1800070fc  pop     r13
0x1800070fe  pop     r12
0x180007100  pop     rdi
0x180007101  pop     rsi
0x180007102  pop     rbx
0x180007103  pop     rbp
0x180007104  retn
```

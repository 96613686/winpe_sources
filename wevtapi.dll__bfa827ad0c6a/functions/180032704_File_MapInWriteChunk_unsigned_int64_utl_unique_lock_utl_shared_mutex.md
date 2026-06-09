# File::MapInWriteChunk(unsigned __int64,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180032704`
- end: `0x180032a08`
- name: `?MapInWriteChunk@File@@AEAAX_KAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `772`
- prototype: `__int64 __fastcall(File *this, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003316c`

## callees

- `0x180023548`
- `0x180023a28`
- `0x180023ac8`
- `0x180025514`
- `0x180031c3c`
- `0x180032704`
- `0x180032db0`
- `0x180032dbc`
- `0x180033828`
- `0x180033ac0`
- `0x180033c4c`
- `0x180033de0`
- `0x180035170`
- `0x1800357f0`
- `0x180038fa4`

## pseudocode

```c
void __fastcall File::MapInWriteChunk(File *this, unsigned __int64 a2, const char *a3)
{
  union _LARGE_INTEGER *v3; // rdi
  __int64 v5; // r14
  unsigned int v7; // eax
  unsigned int v8; // esi
  unsigned int v9; // eax
  unsigned int v10; // esi
  int v11; // edx
  int v12; // r8d
  bool v13; // zf
  __int64 v14; // rdx
  __int64 v15; // rcx
  const char *v16; // r8
  _BYTE pExceptionObject[48]; // [rsp+30h] [rbp-48h] BYREF
  unsigned __int64 v18; // [rsp+80h] [rbp+8h] BYREF

  v3 = (union _LARGE_INTEGER *)((char *)this + 152);
  v5 = (a2 << 16) + 4096;
  if ( *((_QWORD *)this + 21) != v5 )
  {
    if ( a2 >= (unsigned __int64)(*((_QWORD *)this + 7) - 4096LL) >> 16 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0x5DCu, a3, 621);
      throw (EvtException *)pExceptionObject;
    }
    if ( *((_BYTE *)this + 826) )
    {
      v7 = File::WriteCurrentChunk((__int64)this, 1, (__int64)a3);
      v8 = v7;
      if ( v7 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v7);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v8);
        throw (EvtException *)pExceptionObject;
      }
    }
    v9 = WriteFileView::TryAllocIfNecessary((WriteFileView *)v3);
    v10 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v9);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, v10);
      throw (EvtException *)pExceptionObject;
    }
    FileView::ReadIn(v3 + 1, *((void **)this + 84), (union _LARGE_INTEGER)v5);
    if ( !VerifyChunk((const struct FileView *)&v3[1]) )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_iS(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, a2, *((_QWORD *)this + 85));
      }
      v13 = *((_BYTE *)this + 836) == 0;
      v18 = 0;
      if ( !v13 || !File::DetermineFirstRecordForRecovery(this, a2, &v18) )
      {
        FileView::SetOffset((FileView *)&v3[1], 0xFFFFFFFFFFFFFFFFuLL);
        *((_BYTE *)this + 830) = 0;
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, 1500);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x5DCu, v16, 654);
        throw (EvtException *)pExceptionObject;
      }
      InitializeChunkHeaderInfo(*((struct ChunkHeader **)this + 20), v18);
      memset_0(*((void **)this + 28), 0, 0x100u);
      memset_0(*((void **)this + 63), 0, 0x80u);
      *((_BYTE *)this + 827) = 1;
      *((_BYTE *)this + 836) = 1;
      if ( (Microsoft_Windows_EventlogEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v15, v14, *((_QWORD *)this + 89));
    }
  }
}

```

## disassembly

```asm
0x180032704  mov     [rsp+arg_8], rbx
0x180032709  mov     [rsp+arg_10], rbp
0x18003270e  push    rsi
0x18003270f  push    rdi
0x180032710  push    r14
0x180032712  sub     rsp, 60h
0x180032716  mov     r14, rdx
0x180032719  lea     rdi, [rcx+98h]
0x180032720  shl     r14, 10h
0x180032724  mov     rbp, rdx
0x180032727  add     r14, 1000h
0x18003272e  mov     rbx, rcx
0x180032731  cmp     [rdi+10h], r14
0x180032735  jz      loc_180032871
0x18003273b  mov     rax, [rcx+38h]
0x18003273f  sub     rax, 1000h
0x180032745  shr     rax, 10h
0x180032749  cmp     rdx, rax
0x18003274c  jnb     loc_18003294D
0x180032752  cmp     byte ptr [rcx+33Ah], 0
0x180032759  jz      short loc_18003276C
0x18003275b  mov     dl, 1
0x18003275d  call    ?WriteCurrentChunk@File@@AEAAK_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z; File::WriteCurrentChunk(bool,utl::unique_lock<utl::shared_mutex> &)
0x180032762  mov     esi, eax
0x180032764  test    eax, eax
0x180032766  jnz     loc_1800329B0
0x18003276c  mov     rcx, rdi; this
0x18003276f  call    ?TryAllocIfNecessary@WriteFileView@@QEAAKXZ; WriteFileView::TryAllocIfNecessary(void)
0x180032774  mov     esi, eax
0x180032776  test    eax, eax
0x180032778  jnz     loc_180032886
0x18003277e  mov     rdx, [rbx+2A0h]; void *
0x180032785  lea     rsi, [rdi+8]
0x180032789  mov     rcx, rsi; this
0x18003278c  mov     r8, r14; unsigned __int64
0x18003278f  call    ?ReadIn@FileView@@QEAAXPEAX_K@Z; FileView::ReadIn(void *,unsigned __int64)
0x180032794  mov     rcx, rsi; struct FileView *
0x180032797  call    ?VerifyChunk@@YA_NAEBVFileView@@@Z; VerifyChunk(FileView const &)
0x18003279c  test    al, al
0x18003279e  jnz     loc_180032871
0x1800327a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800327ab  lea     rdi, WPP_GLOBAL_Control
0x1800327b2  cmp     rcx, rdi
0x1800327b5  jz      short loc_1800327DE
0x1800327b7  test    dword ptr [rcx+1Ch], 8000h
0x1800327be  jz      short loc_1800327DE
0x1800327c0  cmp     byte ptr [rcx+19h], 4
0x1800327c4  jb      short loc_1800327DE
0x1800327c6  mov     rax, [rbx+2A8h]
0x1800327cd  mov     r9, rbp
0x1800327d0  mov     rcx, [rcx+10h]
0x1800327d4  mov     [rsp+78h+var_58], rax
0x1800327d9  call    WPP_SF_iS
0x1800327de  cmp     byte ptr [rbx+344h], 0
0x1800327e5  mov     [rsp+78h+arg_0], 0
0x1800327f1  jnz     loc_1800328DE
0x1800327f7  lea     r8, [rsp+78h+arg_0]; unsigned __int64 *
0x1800327ff  mov     rdx, rbp; unsigned __int64
0x180032802  mov     rcx, rbx; this
0x180032805  call    ?DetermineFirstRecordForRecovery@File@@AEAA_N_KAEA_K@Z; File::DetermineFirstRecordForRecovery(unsigned __int64,unsigned __int64 &)
0x18003280a  test    al, al
0x18003280c  jz      loc_1800328DE
0x180032812  mov     rdx, [rsp+78h+arg_0]; unsigned __int64
0x18003281a  mov     rcx, [rbx+0A0h]; struct ChunkHeader *
0x180032821  call    ?InitializeChunkHeaderInfo@@YAXPEAUChunkHeader@@_K@Z; InitializeChunkHeaderInfo(ChunkHeader *,unsigned __int64)
0x180032826  mov     rcx, [rbx+0E0h]; void *
0x18003282d  xor     edx, edx; Val
0x18003282f  mov     r8d, 100h; Size
0x180032835  call    memset_0
0x18003283a  mov     rcx, [rbx+1F8h]; void *
0x180032841  xor     edx, edx; Val
0x180032843  mov     r8d, 80h; Size
0x180032849  call    memset_0
0x18003284e  mov     byte ptr [rbx+33Bh], 1
0x180032855  mov     byte ptr [rbx+344h], 1
0x18003285c  test    cs:Microsoft_Windows_EventlogEnableBits, 1
0x180032863  jz      short loc_180032871
0x180032865  mov     r8, [rbx+2C8h]
0x18003286c  call    McTemplateU0z_EventWriteTransfer
0x180032871  lea     r11, [rsp+78h+var_18]
0x180032876  mov     rbx, [r11+28h]
0x18003287a  mov     rbp, [r11+30h]
0x18003287e  mov     rsp, r11
0x180032881  pop     r14
0x180032883  pop     rdi
0x180032884  pop     rsi
0x180032885  retn
0x180032886  mov     rcx, cs:WPP_GLOBAL_Control
0x18003288d  lea     rdi, WPP_GLOBAL_Control
0x180032894  cmp     rcx, rdi
0x180032897  jz      short loc_1800328C0
0x180032899  test    dword ptr [rcx+1Ch], 8000h
0x1800328a0  jz      short loc_1800328C0
0x1800328a2  cmp     byte ptr [rcx+19h], 2
0x1800328a6  jb      short loc_1800328C0
0x1800328a8  mov     rcx, [rcx+10h]
0x1800328ac  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800328b3  mov     edx, 24h ; '$'
0x1800328b8  mov     r9d, esi
0x1800328bb  call    WPP_SF_D
0x1800328c0  mov     edx, esi; unsigned int
0x1800328c2  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800328c7  call    ??0EvtException@@QEAA@K@Z; EvtException::EvtException(ulong)
0x1800328cc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800328d3  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800328d8  call    _CxxThrowException_0
0x1800328de  or      rdx, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x1800328e2  mov     rcx, rsi; this
0x1800328e5  call    ?SetOffset@FileView@@QEAAX_K@Z; FileView::SetOffset(unsigned __int64)
0x1800328ea  mov     byte ptr [rbx+33Eh], 0
0x1800328f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800328f8  mov     ebx, 5DCh
0x1800328fd  cmp     rcx, rdi
0x180032900  jz      short loc_180032929
0x180032902  test    dword ptr [rcx+1Ch], 8000h
0x180032909  jz      short loc_180032929
0x18003290b  cmp     byte ptr [rcx+19h], 2
0x18003290f  jb      short loc_180032929
0x180032911  mov     rcx, [rcx+10h]
0x180032915  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003291c  mov     edx, 26h ; '&'
0x180032921  mov     r9d, ebx
0x180032924  call    WPP_SF_D
0x180032929  mov     r9d, 28Eh; int
0x18003292f  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032934  mov     edx, ebx; unsigned int
0x180032936  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x18003293b  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180032942  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032947  call    _CxxThrowException_0
0x18003294d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032954  lea     rdi, WPP_GLOBAL_Control
0x18003295b  mov     ebx, 5DCh
0x180032960  cmp     rcx, rdi
0x180032963  jz      short loc_18003298C
0x180032965  test    dword ptr [rcx+1Ch], 8000h
0x18003296c  jz      short loc_18003298C
0x18003296e  cmp     byte ptr [rcx+19h], 2
0x180032972  jb      short loc_18003298C
0x180032974  mov     rcx, [rcx+10h]
0x180032978  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x18003297f  mov     edx, 22h ; '"'
0x180032984  mov     r9d, ebx
0x180032987  call    WPP_SF_D
0x18003298c  mov     r9d, 26Dh; int
0x180032992  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180032997  mov     edx, ebx; unsigned int
0x180032999  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x18003299e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800329a5  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800329aa  call    _CxxThrowException_0
0x1800329b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800329b7  lea     rdi, WPP_GLOBAL_Control
0x1800329be  cmp     rcx, rdi
0x1800329c1  jz      short loc_1800329EA
0x1800329c3  test    dword ptr [rcx+1Ch], 8000h
0x1800329ca  jz      short loc_1800329EA
0x1800329cc  cmp     byte ptr [rcx+19h], 2
0x1800329d0  jb      short loc_1800329EA
0x1800329d2  mov     rcx, [rcx+10h]
0x1800329d6  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x1800329dd  mov     edx, 23h ; '#'
0x1800329e2  mov     r9d, esi
0x1800329e5  call    WPP_SF_D
0x1800329ea  mov     edx, esi; unsigned int
0x1800329ec  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800329f1  call    ??0EvtException@@QEAA@K@Z; EvtException::EvtException(ulong)
0x1800329f6  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800329fd  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180032a02  call    _CxxThrowException_0
```

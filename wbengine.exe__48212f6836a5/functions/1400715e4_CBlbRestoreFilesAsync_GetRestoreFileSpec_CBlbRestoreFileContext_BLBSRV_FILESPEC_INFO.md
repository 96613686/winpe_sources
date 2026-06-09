# CBlbRestoreFilesAsync::GetRestoreFileSpec(CBlbRestoreFileContext *,_BLBSRV_FILESPEC_INFO * *)

- ea: `0x1400715e4`
- end: `0x14007186d`
- name: `?GetRestoreFileSpec@CBlbRestoreFilesAsync@@QEAAJPEAVCBlbRestoreFileContext@@PEAPEAU_BLBSRV_FILESPEC_INFO@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(CBlbRestoreFilesAsync *__hidden this, struct CBlbRestoreFileContext *, struct _BLBSRV_FILESPEC_INFO **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x140070400`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x1400715e4`
- `0x1400889f0`
- `0x140088d0c`
- `0x14008d704`
- `0x14008e440`
- `0x1400f3848`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400716aa`
- `ole32!CoTaskMemAlloc` at `0x1400716aa`
- `ole32!CoTaskMemFree` at `0x1400716cb`
- `ole32!CoTaskMemFree` at `0x1400716d5`
- `ole32!CoTaskMemFree` at `0x1400716de`
- `ole32!CoTaskMemFree` at `0x1400716f0`
- `ole32!CoTaskMemFree` at `0x1400716fa`
- `ole32!CoTaskMemFree` at `0x140071703`
- `ole32!CoTaskMemFree` at `0x1400716cb`
- `ole32!CoTaskMemFree` at `0x1400716d5`
- `ole32!CoTaskMemFree` at `0x1400716de`
- `ole32!CoTaskMemFree` at `0x1400716f0`
- `ole32!CoTaskMemFree` at `0x1400716fa`
- `ole32!CoTaskMemFree` at `0x140071703`

## string_xrefs

- `0x1400715f8`: `base\stor\blb\engine\service\restorefiles.cpp`

## pseudocode

```c
__int64 __fastcall CBlbRestoreFilesAsync::GetRestoreFileSpec(
        CBlbRestoreFilesAsync *this,
        unsigned __int16 **a2,
        struct _BLBSRV_FILESPEC_INFO **a3)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // r15
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  int IsFile; // ebx
  int MappedPath; // eax
  unsigned __int16 *v13; // rcx
  int v14; // eax
  char v15; // al
  unsigned __int8 v16; // [rsp+70h] [rbp+48h] BYREF
  unsigned __int16 *v17; // [rsp+78h] [rbp+50h] BYREF
  unsigned __int16 *v18; // [rsp+80h] [rbp+58h] BYREF
  LPVOID pv; // [rsp+88h] [rbp+60h] BYREF

  if ( !a2 )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x3C6u, "pRestoreFileContext != NULL");
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x3C7u, "ppRestoreFileSpec != NULL");
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  if ( *((_DWORD *)this + 58) >= *((_DWORD *)this + 67) )
    BlbAssert("base\\stor\\blb\\engine\\service\\restorefiles.cpp", 0x3CDu, "m_iCurrentRestoreFiles < m_cRestoreFiles");
  v6 = 0;
  v16 = 0;
  v7 = 0;
  v17 = 0;
  pv = 0;
  v18 = 0;
  v8 = CoTaskMemAlloc(0x18u);
  v9 = v8;
  if ( !v8 )
  {
    IsFile = -2147024882;
    goto LABEL_13;
  }
  *(_OWORD *)v8 = 0;
  v8[2] = 0;
  MappedPath = BlbutilGetMappedPath(a2[6], *((unsigned __int16 **)this + 34), *((unsigned __int16 **)this + 35), &v18);
  v7 = v18;
  IsFile = MappedPath;
  if ( MappedPath >= 0 )
  {
    IsFile = BlbIsFile(v18, &v16);
    if ( IsFile >= 0 )
    {
      v13 = a2[6];
      if ( v16 )
      {
        v14 = BlbutilSplitFilePath(v13, &v17, (unsigned __int16 **)&pv);
        v6 = v17;
        IsFile = v14;
        if ( v14 >= 0 )
        {
          IsFile = BlbutilSlashTerminatePath(v17, (LPVOID *)v9);
          if ( IsFile >= 0 )
          {
            IsFile = BlbutilDuplicateString((const unsigned __int16 *)pv, (unsigned __int16 **)v9 + 1, 0);
            if ( IsFile >= 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
              }
              v15 = 0;
              goto LABEL_35;
            }
          }
        }
      }
      else
      {
        IsFile = BlbutilSlashTerminatePath(v13, (LPVOID *)v9);
        if ( IsFile >= 0 )
        {
          IsFile = BlbutilDuplicateString(L"*", (unsigned __int16 **)v9 + 1, 0);
          if ( IsFile >= 0 )
          {
            v15 = *((_BYTE *)this + 316);
LABEL_35:
            *((_BYTE *)v9 + 16) = v15;
            *a3 = (struct _BLBSRV_FILESPEC_INFO *)v9;
          }
        }
      }
    }
  }
LABEL_13:
  CoTaskMemFree(v6);
  CoTaskMemFree(pv);
  CoTaskMemFree(v7);
  if ( IsFile < 0 && v9 )
  {
    CoTaskMemFree((LPVOID)*v9);
    CoTaskMemFree((LPVOID)v9[1]);
    CoTaskMemFree(v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids);
  }
  return (unsigned int)IsFile;
}

```

## disassembly

```asm
0x1400715e4  push    rbp
0x1400715e6  push    rbx
0x1400715e7  push    rsi
0x1400715e8  push    rdi
0x1400715e9  push    r12
0x1400715eb  push    r13
0x1400715ed  push    r14
0x1400715ef  push    r15
0x1400715f1  mov     rbp, rsp
0x1400715f4  sub     rsp, 28h
0x1400715f8  lea     rbx, aBaseStorBlbEng_38; "base\\stor\\blb\\engine\\service\\resto"...
0x1400715ff  mov     r12, r8
0x140071602  mov     r13, rdx
0x140071605  mov     r14, rcx
0x140071608  test    rdx, rdx
0x14007160b  jnz     short loc_140071621
0x14007160d  lea     r8, aPrestorefileco; "pRestoreFileContext != NULL"
0x140071614  mov     edx, 3C6h; unsigned int
0x140071619  mov     rcx, rbx; char *
0x14007161c  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140071621  test    r12, r12
0x140071624  jnz     short loc_14007163A
0x140071626  lea     r8, aPprestorefiles; "ppRestoreFileSpec != NULL"
0x14007162d  mov     edx, 3C7h; unsigned int
0x140071632  mov     rcx, rbx; char *
0x140071635  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x14007163a  mov     rcx, cs:WPP_GLOBAL_Control
0x140071641  lea     rax, WPP_GLOBAL_Control
0x140071648  cmp     rcx, rax
0x14007164b  jz      short loc_14007166E
0x14007164d  test    byte ptr [rcx+1Ch], 1
0x140071651  jz      short loc_14007166E
0x140071653  cmp     byte ptr [rcx+19h], 4
0x140071657  jb      short loc_14007166E
0x140071659  mov     rcx, [rcx+10h]
0x14007165d  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071664  mov     edx, 28h ; '('
0x140071669  call    WPP_SF_
0x14007166e  mov     eax, [r14+10Ch]
0x140071675  cmp     [r14+0E8h], eax
0x14007167c  jb      short loc_140071692
0x14007167e  lea     r8, aMIcurrentresto; "m_iCurrentRestoreFiles < m_cRestoreFile"...
0x140071685  mov     edx, 3CDh; unsigned int
0x14007168a  mov     rcx, rbx; char *
0x14007168d  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x140071692  xor     esi, esi
0x140071694  mov     [rbp+arg_0], 0
0x140071698  xor     r15d, r15d
0x14007169b  mov     [rbp+arg_8], rsi
0x14007169f  mov     [rbp+pv], rsi
0x1400716a3  mov     [rbp+arg_10], r15
0x1400716a7  lea     ecx, [rsi+18h]; cb
0x1400716aa  call    cs:__imp_CoTaskMemAlloc
0x1400716b0  mov     rdi, rax
0x1400716b3  test    rax, rax
0x1400716b6  jnz     loc_140071749
0x1400716bc  mov     ebx, 8007000Eh
0x1400716c1  lea     r14, WPP_GLOBAL_Control
0x1400716c8  mov     rcx, rsi; pv
0x1400716cb  call    cs:__imp_CoTaskMemFree
0x1400716d1  mov     rcx, [rbp+pv]; pv
0x1400716d5  call    cs:__imp_CoTaskMemFree
0x1400716db  mov     rcx, r15; pv
0x1400716de  call    cs:__imp_CoTaskMemFree
0x1400716e4  test    ebx, ebx
0x1400716e6  jns     short loc_140071709
0x1400716e8  test    rdi, rdi
0x1400716eb  jz      short loc_140071709
0x1400716ed  mov     rcx, [rdi]; pv
0x1400716f0  call    cs:__imp_CoTaskMemFree
0x1400716f6  mov     rcx, [rdi+8]; pv
0x1400716fa  call    cs:__imp_CoTaskMemFree
0x140071700  mov     rcx, rdi; pv
0x140071703  call    cs:__imp_CoTaskMemFree
0x140071709  mov     rcx, cs:WPP_GLOBAL_Control
0x140071710  cmp     rcx, r14
0x140071713  jz      short loc_140071736
0x140071715  test    byte ptr [rcx+1Ch], 1
0x140071719  jz      short loc_140071736
0x14007171b  cmp     byte ptr [rcx+19h], 4
0x14007171f  jb      short loc_140071736
0x140071721  mov     rcx, [rcx+10h]
0x140071725  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x14007172c  mov     edx, 2Ah ; '*'
0x140071731  call    WPP_SF_
0x140071736  mov     eax, ebx
0x140071738  add     rsp, 28h
0x14007173c  pop     r15
0x14007173e  pop     r14
0x140071740  pop     r13
0x140071742  pop     r12
0x140071744  pop     rdi
0x140071745  pop     rsi
0x140071746  pop     rbx
0x140071747  pop     rbp
0x140071748  retn
0x140071749  xorps   xmm0, xmm0
0x14007174c  lea     r9, [rbp+arg_10]; unsigned __int16 **
0x140071750  movups  xmmword ptr [rdi], xmm0
0x140071753  xor     eax, eax
0x140071755  mov     [rdi+10h], rax
0x140071759  mov     r8, [r14+118h]; unsigned __int16 *
0x140071760  mov     rdx, [r14+110h]; unsigned __int16 *
0x140071767  mov     rcx, [r13+30h]; unsigned __int16 *
0x14007176b  call    ?BlbutilGetMappedPath@@YAJPEAG00PEAPEAG@Z; BlbutilGetMappedPath(ushort *,ushort *,ushort *,ushort * *)
0x140071770  mov     r15, [rbp+arg_10]
0x140071774  mov     ebx, eax
0x140071776  test    eax, eax
0x140071778  js      loc_1400716C1
0x14007177e  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x140071782  mov     rcx, r15; unsigned __int16 *
0x140071785  call    ?BlbIsFile@@YAJPEAGPEAE@Z; BlbIsFile(ushort *,uchar *)
0x14007178a  mov     ebx, eax
0x14007178c  test    eax, eax
0x14007178e  js      loc_1400716C1
0x140071794  mov     rcx, [r13+30h]; unsigned __int16 *
0x140071798  cmp     [rbp+arg_0], sil
0x14007179c  jz      loc_140071824
0x1400717a2  lea     r8, [rbp+pv]; unsigned __int16 **
0x1400717a6  lea     rdx, [rbp+arg_8]; unsigned __int16 **
0x1400717aa  call    ?BlbutilSplitFilePath@@YAJPEAGPEAPEAG1@Z; BlbutilSplitFilePath(ushort *,ushort * *,ushort * *)
0x1400717af  mov     rsi, [rbp+arg_8]
0x1400717b3  mov     ebx, eax
0x1400717b5  test    eax, eax
0x1400717b7  js      loc_1400716C1
0x1400717bd  mov     rdx, rdi; unsigned __int16 **
0x1400717c0  mov     rcx, rsi; unsigned __int16 *
0x1400717c3  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x1400717c8  mov     ebx, eax
0x1400717ca  test    eax, eax
0x1400717cc  js      loc_1400716C1
0x1400717d2  mov     rcx, [rbp+pv]; unsigned __int16 *
0x1400717d6  lea     rdx, [rdi+8]; unsigned __int16 **
0x1400717da  xor     r8d, r8d; unsigned __int64
0x1400717dd  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1400717e2  mov     ebx, eax
0x1400717e4  test    eax, eax
0x1400717e6  js      loc_1400716C1
0x1400717ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400717f3  lea     r14, WPP_GLOBAL_Control
0x1400717fa  cmp     rcx, r14
0x1400717fd  jz      short loc_140071820
0x1400717ff  test    byte ptr [rcx+1Ch], 1
0x140071803  jz      short loc_140071820
0x140071805  cmp     byte ptr [rcx+19h], 4
0x140071809  jb      short loc_140071820
0x14007180b  mov     rcx, [rcx+10h]
0x14007180f  lea     r8, WPP_9bc2e6579c4134c7eec8e8241f17499a_Traceguids
0x140071816  mov     edx, 29h ; ')'
0x14007181b  call    WPP_SF_
0x140071820  xor     al, al
0x140071822  jmp     short loc_140071861
0x140071824  mov     rdx, rdi; unsigned __int16 **
0x140071827  call    ?BlbutilSlashTerminatePath@@YAJPEAGPEAPEAG@Z; BlbutilSlashTerminatePath(ushort *,ushort * *)
0x14007182c  mov     ebx, eax
0x14007182e  test    eax, eax
0x140071830  js      loc_1400716C1
0x140071836  lea     rdx, [rdi+8]; unsigned __int16 **
0x14007183a  xor     r8d, r8d; unsigned __int64
0x14007183d  lea     rcx, asc_14013BEE0; "*"
0x140071844  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x140071849  mov     ebx, eax
0x14007184b  test    eax, eax
0x14007184d  js      loc_1400716C1
0x140071853  mov     al, [r14+13Ch]
0x14007185a  lea     r14, WPP_GLOBAL_Control
0x140071861  mov     [rdi+10h], al
0x140071864  mov     [r12], rdi
0x140071868  jmp     loc_1400716C8
```

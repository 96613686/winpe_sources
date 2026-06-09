# CIconCache::SaveIcon(int,int,HICON__ *)

- ea: `0x18001880c`
- end: `0x180018adb`
- name: `?SaveIcon@CIconCache@@QEAAJHHPEAUHICON__@@@Z`
- size: `719`
- prototype: `int(CIconCache *__hidden this, int, int, HICON)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017ac0`

## callees

- `0x180017060`
- `0x180017fcc`
- `0x180018090`
- `0x18001880c`
- `0x180018ae4`
- `0x180018e4c`
- `0x18003ef10`
- `0x1800b0b5c`
- `0x1801188ec`
- `0x180249490`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018896`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800189f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800189cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800189cc`
- `USER32!GetIconInfo` at `0x180018918`
- `USER32!GetIconInfo` at `0x180018918`
- `GDI32!DeleteObject` at `0x180018969`
- `GDI32!DeleteObject` at `0x1800189a1`
- `GDI32!DeleteObject` at `0x180018aca`
- `GDI32!DeleteObject` at `0x180018969`
- `GDI32!DeleteObject` at `0x1800189a1`
- `GDI32!DeleteObject` at `0x180018aca`
- `GDI32!GetObjectW` at `0x180018a3e`
- `GDI32!GetObjectW` at `0x180018a3e`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18001883a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018887`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800189bd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800189e5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x18001883a`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180018887`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800189bd`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800189e5`
- `Windows.Storage!GetThreadIconCache` at `0x1800188ea`
- `Windows.Storage!GetThreadIconCache` at `0x1800188ea`

## pseudocode

```c
__int64 __fastcall CIconCache::SaveIcon(CIconCache *this, int a2, unsigned int a3, HICON a4)
{
  struct _RTL_CRITICAL_SECTION *v8; // rax
  struct _DSA *v9; // rcx
  int ThreadIconCache; // edi
  const struct RECOVERY_ENTRY *ItemPtr; // rax
  struct _RTL_CRITICAL_SECTION *v12; // rax
  HBITMAP v13; // rbx
  int v14; // r8d
  HBITMAP hbmColor; // rcx
  bool v16; // al
  struct _RTL_CRITICAL_SECTION *v17; // rax
  struct _RTL_CRITICAL_SECTION *v18; // rax
  int BitmapFromIcon; // eax
  bool v21; // [rsp+30h] [rbp-79h] BYREF
  HBITMAP v22; // [rsp+38h] [rbp-71h] BYREF
  _DWORD v23[2]; // [rsp+40h] [rbp-69h] BYREF
  _OWORD v24[2]; // [rsp+48h] [rbp-61h] BYREF
  __int64 v25; // [rsp+68h] [rbp-41h] BYREF
  ICONINFO piconinfo; // [rsp+70h] [rbp-39h] BYREF
  WTS_THUMBNAILID v27; // [rsp+90h] [rbp-19h] BYREF
  _OWORD pv[2]; // [rsp+A0h] [rbp-9h] BYREF

  v8 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  EnterCriticalSection(v8);
  v9 = (struct _DSA *)*((_QWORD *)this + 5);
  ThreadIconCache = -2147467259;
  memset(v24, 0, sizeof(v24));
  ItemPtr = (const struct RECOVERY_ENTRY *)DSA_GetItemPtr(v9, a2);
  if ( ItemPtr )
    ThreadIconCache = RECOVERY_ENTRY::CloneFrom((RECOVERY_ENTRY *)v24, *((struct _HashTable ***)this + 7), ItemPtr);
  v12 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  LeaveCriticalSection(v12);
  if ( ThreadIconCache >= 0 )
  {
    v27 = 0;
    if ( (v24[0] & 3) != 1 && (v24[0] & 3) != 2 )
    {
      ThreadIconCache = -2147467259;
      goto LABEL_16;
    }
    ThreadIconCache = _ComputeThumbailIDFromRecoveryEntry((const struct RECOVERY_ENTRY *)v24, &v27);
    if ( ThreadIconCache >= 0 )
    {
      v25 = 0;
      ThreadIconCache = GetThreadIconCache(&GUID_69bd8647_874f_4808_9b36_e8012d8560dd, &v25);
      if ( ThreadIconCache >= 0 )
      {
        v13 = 0;
        v22 = 0;
        memset(&piconinfo, 0, sizeof(piconinfo));
        if ( !GetIconInfo(a4, &piconinfo) )
        {
          ThreadIconCache = ResultFromKnownLastError();
          if ( ThreadIconCache < 0 )
          {
LABEL_15:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            goto LABEL_16;
          }
        }
        hbmColor = piconinfo.hbmColor;
        v16 = 0;
        v21 = 0;
        if ( piconinfo.hbmColor )
        {
          ThreadIconCache = _DoesBitmapHaveAlpha(piconinfo.hbmColor, &v21);
          if ( ThreadIconCache < 0 )
            goto LABEL_11;
          hbmColor = piconinfo.hbmColor;
          v16 = v21;
        }
        if ( v16 )
        {
          memset(pv, 0, sizeof(pv));
          if ( GetObjectW(hbmColor, 32, pv) )
          {
            ThreadIconCache = 0;
          }
          else
          {
            ThreadIconCache = ResultFromKnownLastError();
            if ( ThreadIconCache < 0 )
            {
LABEL_11:
              if ( piconinfo.hbmColor )
                DeleteObject(piconinfo.hbmColor);
              goto LABEL_13;
            }
          }
          if ( __PAIR64__(DWORD1(pv[0]), a3) == *(_QWORD *)((char *)pv + 4) )
          {
            v13 = piconinfo.hbmColor;
            piconinfo.hbmColor = 0;
LABEL_13:
            DeleteObject(piconinfo.hbmMask);
            if ( ThreadIconCache >= 0 )
            {
              ThreadIconCache = (*(__int64 (__fastcall **)(__int64, WTS_THUMBNAILID *, _QWORD, HBITMAP))(*(_QWORD *)v25 + 24LL))(
                                  v25,
                                  &v27,
                                  a3,
                                  v13);
              DeleteObject(v13);
            }
            goto LABEL_15;
          }
          BitmapFromIcon = _ScaleBitmap(piconinfo.hbmColor, a3, &v22);
        }
        else
        {
          v23[0] = a3;
          v23[1] = a3;
          BitmapFromIcon = CreateBitmapFromIcon((_DWORD)a4, 0, v14, (unsigned int)v23, (__int64)&v22);
        }
        v13 = v22;
        ThreadIconCache = BitmapFromIcon;
        goto LABEL_11;
      }
    }
  }
LABEL_16:
  v17 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  EnterCriticalSection(v17);
  RECOVERY_ENTRY::Destruct((RECOVERY_ENTRY *)v24, *((struct _HashTable ***)this + 7));
  v18 = (struct _RTL_CRITICAL_SECTION *)Global_WindowsStorage_csIconCache();
  LeaveCriticalSection(v18);
  return (unsigned int)ThreadIconCache;
}

```

## disassembly

```asm
0x18001880c  push    rbp
0x18001880e  push    rbx
0x18001880f  push    rsi
0x180018810  push    rdi
0x180018811  push    r14
0x180018813  push    r15
0x180018815  lea     rbp, [rsp-2Fh]
0x18001881a  sub     rsp, 0D8h
0x180018821  mov     rax, cs:__security_cookie
0x180018828  xor     rax, rsp
0x18001882b  mov     [rbp+57h+var_40], rax
0x18001882f  mov     r14, r9
0x180018832  mov     esi, r8d
0x180018835  mov     ebx, edx
0x180018837  mov     r15, rcx
0x18001883a  call    cs:__imp_Global_WindowsStorage_csIconCache
0x180018841  nop     dword ptr [rax+rax+00h]
0x180018846  mov     rcx, rax; lpCriticalSection
0x180018849  call    cs:__imp_EnterCriticalSection
0x180018850  nop     dword ptr [rax+rax+00h]
0x180018855  mov     rcx, [r15+28h]; hdsa
0x180018859  xorps   xmm0, xmm0
0x18001885c  mov     edx, ebx; i
0x18001885e  mov     edi, 80004005h
0x180018863  movups  [rbp+57h+var_B8], xmm0
0x180018867  movups  [rbp+57h+var_A8], xmm0
0x18001886b  call    DSA_GetItemPtr
0x180018870  test    rax, rax
0x180018873  jz      short loc_180018887
0x180018875  mov     rdx, [r15+38h]; struct _HashTable **
0x180018879  lea     rcx, [rbp+57h+var_B8]; this
0x18001887d  mov     r8, rax; struct RECOVERY_ENTRY *
0x180018880  call    ?CloneFrom@RECOVERY_ENTRY@@QEAAJPEAPEAU_HashTable@@PEBU1@@Z; RECOVERY_ENTRY::CloneFrom(_HashTable * *,RECOVERY_ENTRY const *)
0x180018885  mov     edi, eax
0x180018887  call    cs:__imp_Global_WindowsStorage_csIconCache
0x18001888e  nop     dword ptr [rax+rax+00h]
0x180018893  mov     rcx, rax; lpCriticalSection
0x180018896  call    cs:__imp_LeaveCriticalSection
0x18001889d  nop     dword ptr [rax+rax+00h]
0x1800188a2  test    edi, edi
0x1800188a4  js      loc_1800189BD
0x1800188aa  mov     ecx, dword ptr [rbp+57h+var_B8]
0x1800188ad  xorps   xmm0, xmm0
0x1800188b0  and     ecx, 3
0x1800188b3  movups  xmmword ptr [rbp+57h+var_70.rgbKey], xmm0
0x1800188b7  sub     ecx, 1
0x1800188ba  jnz     loc_180018AB7
0x1800188c0  lea     rdx, [rbp+57h+var_70]; struct WTS_THUMBNAILID *
0x1800188c4  lea     rcx, [rbp+57h+var_B8]; struct RECOVERY_ENTRY *
0x1800188c8  call    ?_ComputeThumbailIDFromRecoveryEntry@@YAJPEBURECOVERY_ENTRY@@PEAUWTS_THUMBNAILID@@@Z; _ComputeThumbailIDFromRecoveryEntry(RECOVERY_ENTRY const *,WTS_THUMBNAILID *)
0x1800188cd  mov     edi, eax
0x1800188cf  test    eax, eax
0x1800188d1  js      loc_1800189BD
0x1800188d7  lea     rdx, [rbp+57h+var_98]
0x1800188db  mov     [rbp+57h+var_98], 0
0x1800188e3  lea     rcx, _GUID_69bd8647_874f_4808_9b36_e8012d8560dd
0x1800188ea  call    cs:__imp_GetThreadIconCache
0x1800188f1  nop     dword ptr [rax+rax+00h]
0x1800188f6  mov     edi, eax
0x1800188f8  test    eax, eax
0x1800188fa  js      loc_1800189BD
0x180018900  xorps   xmm0, xmm0
0x180018903  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x180018907  xor     ebx, ebx
0x180018909  mov     rcx, r14; hIcon
0x18001890c  mov     [rbp+57h+var_C8], rbx
0x180018910  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x180018914  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x180018918  call    cs:__imp_GetIconInfo
0x18001891f  nop     dword ptr [rax+rax+00h]
0x180018924  test    eax, eax
0x180018926  jnz     short loc_180018933
0x180018928  call    ResultFromKnownLastError
0x18001892d  mov     edi, eax
0x18001892f  test    eax, eax
0x180018931  js      short loc_1800189AD
0x180018933  mov     rcx, [rbp+57h+piconinfo.hbmColor]; hbm
0x180018937  xor     al, al
0x180018939  mov     [rbp+57h+var_D0], al
0x18001893c  test    rcx, rcx
0x18001893f  jz      loc_180018A26
0x180018945  lea     rdx, [rbp+57h+var_D0]; bool *
0x180018949  call    ?_DoesBitmapHaveAlpha@@YAJPEAUHBITMAP__@@PEA_N@Z; _DoesBitmapHaveAlpha(HBITMAP__ *,bool *)
0x18001894e  mov     edi, eax
0x180018950  test    eax, eax
0x180018952  jns     loc_180018A1F
0x180018958  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x18001895c  test    rcx, rcx
0x18001895f  jnz     loc_180018ACA
0x180018965  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180018969  call    cs:__imp_DeleteObject
0x180018970  nop     dword ptr [rax+rax+00h]
0x180018975  test    edi, edi
0x180018977  js      short loc_1800189AD
0x180018979  mov     rcx, [rbp+57h+var_98]
0x18001897d  lea     rdx, [rbp+57h+var_70]
0x180018981  movaps  xmm0, xmmword ptr [rbp+57h+var_70.rgbKey]
0x180018985  mov     r9, rbx
0x180018988  mov     r8d, esi
0x18001898b  movdqa  xmmword ptr [rbp+57h+var_70.rgbKey], xmm0
0x180018990  mov     rax, [rcx]
0x180018993  mov     rax, [rax+18h]
0x180018997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001899c  mov     rcx, rbx; ho
0x18001899f  mov     edi, eax
0x1800189a1  call    cs:__imp_DeleteObject
0x1800189a8  nop     dword ptr [rax+rax+00h]
0x1800189ad  mov     rcx, [rbp+57h+var_98]
0x1800189b1  mov     rax, [rcx]
0x1800189b4  mov     rax, [rax+10h]
0x1800189b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189bd  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800189c4  nop     dword ptr [rax+rax+00h]
0x1800189c9  mov     rcx, rax; lpCriticalSection
0x1800189cc  call    cs:__imp_EnterCriticalSection
0x1800189d3  nop     dword ptr [rax+rax+00h]
0x1800189d8  mov     rdx, [r15+38h]; struct _HashTable **
0x1800189dc  lea     rcx, [rbp+57h+var_B8]; this
0x1800189e0  call    ?Destruct@RECOVERY_ENTRY@@QEAAXPEAPEAU_HashTable@@@Z; RECOVERY_ENTRY::Destruct(_HashTable * *)
0x1800189e5  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800189ec  nop     dword ptr [rax+rax+00h]
0x1800189f1  mov     rcx, rax; lpCriticalSection
0x1800189f4  call    cs:__imp_LeaveCriticalSection
0x1800189fb  nop     dword ptr [rax+rax+00h]
0x180018a00  mov     eax, edi
0x180018a02  mov     rcx, [rbp+57h+var_40]
0x180018a06  xor     rcx, rsp; StackCookie
0x180018a09  call    __security_check_cookie
0x180018a0e  add     rsp, 0D8h
0x180018a15  pop     r15
0x180018a17  pop     r14
0x180018a19  pop     rdi
0x180018a1a  pop     rsi
0x180018a1b  pop     rbx
0x180018a1c  pop     rbp
0x180018a1d  retn
0x180018a1f  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x180018a23  mov     al, [rbp+57h+var_D0]
0x180018a26  test    al, al
0x180018a28  jz      short loc_180018A87
0x180018a2a  xorps   xmm0, xmm0
0x180018a2d  lea     r8, [rbp+57h+pv]; pv
0x180018a31  mov     edx, 20h ; ' '; c
0x180018a36  movups  [rbp+57h+pv], xmm0
0x180018a3a  movups  [rbp+57h+var_50], xmm0
0x180018a3e  call    cs:__imp_GetObjectW
0x180018a45  nop     dword ptr [rax+rax+00h]
0x180018a4a  test    eax, eax
0x180018a4c  jz      short loc_180018AA6
0x180018a4e  xor     edi, edi
0x180018a50  mov     eax, dword ptr [rbp+57h+pv+4]
0x180018a53  cmp     eax, dword ptr [rbp+57h+pv+8]
0x180018a56  jnz     short loc_180018A6D
0x180018a58  cmp     esi, eax
0x180018a5a  jnz     short loc_180018A6D
0x180018a5c  mov     rbx, [rbp+57h+piconinfo.hbmColor]
0x180018a60  mov     [rbp+57h+piconinfo.hbmColor], 0
0x180018a68  jmp     loc_180018965
0x180018a6d  mov     rcx, [rbp+57h+piconinfo.hbmColor]; HBITMAP
0x180018a71  lea     r8, [rbp+57h+var_C8]; HBITMAP *
0x180018a75  mov     edx, esi; unsigned int
0x180018a77  call    ?_ScaleBitmap@@YAJPEAUHBITMAP__@@IPEAPEAU1@@Z; _ScaleBitmap(HBITMAP__ *,uint,HBITMAP__ * *)
0x180018a7c  mov     rbx, [rbp+57h+var_C8]
0x180018a80  mov     edi, eax
0x180018a82  jmp     loc_180018958
0x180018a87  lea     rax, [rbp+57h+var_C8]
0x180018a8b  mov     [rbp+57h+var_C0], esi
0x180018a8e  lea     r9, [rbp+57h+var_C0]
0x180018a92  mov     [rsp+100h+var_E0], rax
0x180018a97  xor     edx, edx
0x180018a99  mov     [rbp+57h+var_BC], esi
0x180018a9c  mov     rcx, r14
0x180018a9f  call    CreateBitmapFromIcon
0x180018aa4  jmp     short loc_180018A7C
0x180018aa6  call    ResultFromKnownLastError
0x180018aab  mov     edi, eax
0x180018aad  test    eax, eax
0x180018aaf  js      loc_180018958
0x180018ab5  jmp     short loc_180018A50
0x180018ab7  cmp     ecx, 1
0x180018aba  jz      loc_1800188C0
0x180018ac0  mov     edi, 80004005h
0x180018ac5  jmp     loc_1800189BD
0x180018aca  call    cs:__imp_DeleteObject
0x180018ad1  nop     dword ptr [rax+rax+00h]
0x180018ad6  jmp     loc_180018965
```

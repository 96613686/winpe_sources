# CIconCache::SaveIcon(int,int,HICON__ *)

- ea: `0x180020324`
- end: `0x18002059e`
- name: `?SaveIcon@CIconCache@@QEAAJHHPEAUHICON__@@@Z`
- size: `634`
- prototype: `int(CIconCache *__hidden this, int, int, HICON)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001f6e0`

## callees

- `0x18001ebb0`
- `0x18001fb6c`
- `0x18001fc2c`
- `0x180020324`
- `0x1800205a4`
- `0x1800208d8`
- `0x180043380`
- `0x18009c520`
- `0x18010e198`
- `0x180233280`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002039c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002039c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800204ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002035b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800204ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002035b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800204ae`
- `USER32!GetIconInfo` at `0x180020412`
- `USER32!GetIconInfo` at `0x180020412`
- `GDI32!DeleteObject` at `0x18002045d`
- `GDI32!DeleteObject` at `0x18002048f`
- `GDI32!DeleteObject` at `0x180020593`
- `GDI32!DeleteObject` at `0x18002045d`
- `GDI32!DeleteObject` at `0x18002048f`
- `GDI32!DeleteObject` at `0x180020593`
- `GDI32!GetObjectW` at `0x18002050d`
- `GDI32!GetObjectW` at `0x18002050d`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020352`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020393`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800204a5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800204c1`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020352`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x180020393`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800204a5`
- `api-ms-win-storage-exports-internal-l1-1-0!Global_WindowsStorage_csIconCache` at `0x1800204c1`
- `Windows.Storage!GetThreadIconCache` at `0x1800203ea`
- `Windows.Storage!GetThreadIconCache` at `0x1800203ea`

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
0x180020324  push    rbp
0x180020326  push    rbx
0x180020327  push    rsi
0x180020328  push    rdi
0x180020329  push    r14
0x18002032b  push    r15
0x18002032d  lea     rbp, [rsp-2Fh]
0x180020332  sub     rsp, 0D8h
0x180020339  mov     rax, cs:__security_cookie
0x180020340  xor     rax, rsp
0x180020343  mov     [rbp+57h+var_40], rax
0x180020347  mov     r14, r9
0x18002034a  mov     esi, r8d
0x18002034d  mov     ebx, edx
0x18002034f  mov     r15, rcx
0x180020352  call    cs:__imp_Global_WindowsStorage_csIconCache
0x180020358  mov     rcx, rax; lpCriticalSection
0x18002035b  call    cs:__imp_EnterCriticalSection
0x180020361  mov     rcx, [r15+28h]; hdsa
0x180020365  xorps   xmm0, xmm0
0x180020368  mov     edx, ebx; i
0x18002036a  mov     edi, 80004005h
0x18002036f  movups  [rbp+57h+var_B8], xmm0
0x180020373  movups  [rbp+57h+var_A8], xmm0
0x180020377  call    DSA_GetItemPtr
0x18002037c  test    rax, rax
0x18002037f  jz      short loc_180020393
0x180020381  mov     rdx, [r15+38h]; struct _HashTable **
0x180020385  lea     rcx, [rbp+57h+var_B8]; this
0x180020389  mov     r8, rax; struct RECOVERY_ENTRY *
0x18002038c  call    ?CloneFrom@RECOVERY_ENTRY@@QEAAJPEAPEAU_HashTable@@PEBU1@@Z; RECOVERY_ENTRY::CloneFrom(_HashTable * *,RECOVERY_ENTRY const *)
0x180020391  mov     edi, eax
0x180020393  call    cs:__imp_Global_WindowsStorage_csIconCache
0x180020399  mov     rcx, rax; lpCriticalSection
0x18002039c  call    cs:__imp_LeaveCriticalSection
0x1800203a2  test    edi, edi
0x1800203a4  js      loc_1800204A5
0x1800203aa  mov     ecx, dword ptr [rbp+57h+var_B8]
0x1800203ad  xorps   xmm0, xmm0
0x1800203b0  and     ecx, 3
0x1800203b3  movups  xmmword ptr [rbp+57h+var_70.rgbKey], xmm0
0x1800203b7  sub     ecx, 1
0x1800203ba  jnz     loc_180020580
0x1800203c0  lea     rdx, [rbp+57h+var_70]; struct WTS_THUMBNAILID *
0x1800203c4  lea     rcx, [rbp+57h+var_B8]; struct RECOVERY_ENTRY *
0x1800203c8  call    ?_ComputeThumbailIDFromRecoveryEntry@@YAJPEBURECOVERY_ENTRY@@PEAUWTS_THUMBNAILID@@@Z; _ComputeThumbailIDFromRecoveryEntry(RECOVERY_ENTRY const *,WTS_THUMBNAILID *)
0x1800203cd  mov     edi, eax
0x1800203cf  test    eax, eax
0x1800203d1  js      loc_1800204A5
0x1800203d7  lea     rdx, [rbp+57h+var_98]
0x1800203db  mov     [rbp+57h+var_98], 0
0x1800203e3  lea     rcx, _GUID_69bd8647_874f_4808_9b36_e8012d8560dd
0x1800203ea  call    cs:__imp_GetThreadIconCache
0x1800203f0  mov     edi, eax
0x1800203f2  test    eax, eax
0x1800203f4  js      loc_1800204A5
0x1800203fa  xorps   xmm0, xmm0
0x1800203fd  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x180020401  xor     ebx, ebx
0x180020403  mov     rcx, r14; hIcon
0x180020406  mov     [rbp+57h+var_C8], rbx
0x18002040a  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x18002040e  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x180020412  call    cs:__imp_GetIconInfo
0x180020418  test    eax, eax
0x18002041a  jnz     short loc_180020427
0x18002041c  call    ResultFromKnownLastError
0x180020421  mov     edi, eax
0x180020423  test    eax, eax
0x180020425  js      short loc_180020495
0x180020427  mov     rcx, [rbp+57h+piconinfo.hbmColor]; hbm
0x18002042b  xor     al, al
0x18002042d  mov     [rbp+57h+var_D0], al
0x180020430  test    rcx, rcx
0x180020433  jz      loc_1800204F5
0x180020439  lea     rdx, [rbp+57h+var_D0]; bool *
0x18002043d  call    ?_DoesBitmapHaveAlpha@@YAJPEAUHBITMAP__@@PEA_N@Z; _DoesBitmapHaveAlpha(HBITMAP__ *,bool *)
0x180020442  mov     edi, eax
0x180020444  test    eax, eax
0x180020446  jns     loc_1800204EE
0x18002044c  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x180020450  test    rcx, rcx
0x180020453  jnz     loc_180020593
0x180020459  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x18002045d  call    cs:__imp_DeleteObject
0x180020463  test    edi, edi
0x180020465  js      short loc_180020495
0x180020467  mov     rcx, [rbp+57h+var_98]
0x18002046b  lea     rdx, [rbp+57h+var_70]
0x18002046f  movaps  xmm0, xmmword ptr [rbp+57h+var_70.rgbKey]
0x180020473  mov     r9, rbx
0x180020476  mov     r8d, esi
0x180020479  movdqa  xmmword ptr [rbp+57h+var_70.rgbKey], xmm0
0x18002047e  mov     rax, [rcx]
0x180020481  mov     rax, [rax+18h]
0x180020485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002048a  mov     rcx, rbx; ho
0x18002048d  mov     edi, eax
0x18002048f  call    cs:__imp_DeleteObject
0x180020495  mov     rcx, [rbp+57h+var_98]
0x180020499  mov     rax, [rcx]
0x18002049c  mov     rax, [rax+10h]
0x1800204a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204a5  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800204ab  mov     rcx, rax; lpCriticalSection
0x1800204ae  call    cs:__imp_EnterCriticalSection
0x1800204b4  mov     rdx, [r15+38h]; struct _HashTable **
0x1800204b8  lea     rcx, [rbp+57h+var_B8]; this
0x1800204bc  call    ?Destruct@RECOVERY_ENTRY@@QEAAXPEAPEAU_HashTable@@@Z; RECOVERY_ENTRY::Destruct(_HashTable * *)
0x1800204c1  call    cs:__imp_Global_WindowsStorage_csIconCache
0x1800204c7  mov     rcx, rax; lpCriticalSection
0x1800204ca  call    cs:__imp_LeaveCriticalSection
0x1800204d0  mov     eax, edi
0x1800204d2  mov     rcx, [rbp+57h+var_40]
0x1800204d6  xor     rcx, rsp; StackCookie
0x1800204d9  call    __security_check_cookie
0x1800204de  add     rsp, 0D8h
0x1800204e5  pop     r15
0x1800204e7  pop     r14
0x1800204e9  pop     rdi
0x1800204ea  pop     rsi
0x1800204eb  pop     rbx
0x1800204ec  pop     rbp
0x1800204ed  retn
0x1800204ee  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x1800204f2  mov     al, [rbp+57h+var_D0]
0x1800204f5  test    al, al
0x1800204f7  jz      short loc_180020550
0x1800204f9  xorps   xmm0, xmm0
0x1800204fc  lea     r8, [rbp+57h+pv]; pv
0x180020500  mov     edx, 20h ; ' '; c
0x180020505  movups  [rbp+57h+pv], xmm0
0x180020509  movups  [rbp+57h+var_50], xmm0
0x18002050d  call    cs:__imp_GetObjectW
0x180020513  test    eax, eax
0x180020515  jz      short loc_18002056F
0x180020517  xor     edi, edi
0x180020519  mov     eax, dword ptr [rbp+57h+pv+4]
0x18002051c  cmp     eax, dword ptr [rbp+57h+pv+8]
0x18002051f  jnz     short loc_180020536
0x180020521  cmp     esi, eax
0x180020523  jnz     short loc_180020536
0x180020525  mov     rbx, [rbp+57h+piconinfo.hbmColor]
0x180020529  mov     [rbp+57h+piconinfo.hbmColor], 0
0x180020531  jmp     loc_180020459
0x180020536  mov     rcx, [rbp+57h+piconinfo.hbmColor]; HBITMAP
0x18002053a  lea     r8, [rbp+57h+var_C8]; HBITMAP *
0x18002053e  mov     edx, esi; unsigned int
0x180020540  call    ?_ScaleBitmap@@YAJPEAUHBITMAP__@@IPEAPEAU1@@Z; _ScaleBitmap(HBITMAP__ *,uint,HBITMAP__ * *)
0x180020545  mov     rbx, [rbp+57h+var_C8]
0x180020549  mov     edi, eax
0x18002054b  jmp     loc_18002044C
0x180020550  lea     rax, [rbp+57h+var_C8]
0x180020554  mov     [rbp+57h+var_C0], esi
0x180020557  lea     r9, [rbp+57h+var_C0]
0x18002055b  mov     [rsp+100h+var_E0], rax
0x180020560  xor     edx, edx
0x180020562  mov     [rbp+57h+var_BC], esi
0x180020565  mov     rcx, r14
0x180020568  call    CreateBitmapFromIcon
0x18002056d  jmp     short loc_180020545
0x18002056f  call    ResultFromKnownLastError
0x180020574  mov     edi, eax
0x180020576  test    eax, eax
0x180020578  js      loc_18002044C
0x18002057e  jmp     short loc_180020519
0x180020580  cmp     ecx, 1
0x180020583  jz      loc_1800203C0
0x180020589  mov     edi, 80004005h
0x18002058e  jmp     loc_1800204A5
0x180020593  call    cs:__imp_DeleteObject
0x180020599  jmp     loc_180020459
```

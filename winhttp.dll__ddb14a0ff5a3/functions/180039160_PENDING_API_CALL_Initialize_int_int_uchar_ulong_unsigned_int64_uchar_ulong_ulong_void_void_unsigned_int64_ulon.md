# PENDING_API_CALL::Initialize(int,int,uchar *,ulong,unsigned __int64,uchar *,ulong,ulong,void (*)(void *,unsigned __int64,ulong,void *,ulong),unsigned __int64)

- ea: `0x180039160`
- end: `0x180039378`
- name: `?Initialize@PENDING_API_CALL@@AEAAKHHPEAEK_K0KKP6AXPEAX1K2K@Z1@Z`
- size: `536`
- prototype: `unsigned int __fastcall(PENDING_API_CALL *__hidden this, int, int, unsigned __int8 *, unsigned int, unsigned __int64, unsigned __int8 *, unsigned int, unsigned int, void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int), unsigned __int64)`
- caller_count: `5`
- callee_count: `7`
- tags: ``

## callers

- `0x180034dc0`
- `0x180036e40`
- `0x180037f80`
- `0x180039380`
- `0x18003dd30`

## callees

- `0x1800334f4`
- `0x1800339d0`
- `0x180039160`
- `0x18008da14`
- `0x1800cf58c`
- `0x1800d61d4`
- `0x1800d6250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800391e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180039286`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800391e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180039286`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800392e4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800392e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800391cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800391cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039299`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800391fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039299`

## pseudocode

```c
__int64 __fastcall PENDING_API_CALL::Initialize(
        PENDING_API_CALL *this,
        int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int64 a6,
        unsigned __int8 *a7,
        unsigned int a8,
        unsigned int a9,
        void (*a10)(void *, unsigned __int64, unsigned int, void *, unsigned int),
        unsigned __int64 a11)
{
  HANDLE EventA; // rax
  DWORD LastError; // eax
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rdx
  char *v18; // rax
  int v19; // ecx
  int v20; // r8d
  int v21; // edx
  unsigned int v22; // edi
  struct _INTERNET_THREAD_INFO *ThreadInfo; // rax
  HANDLE v25; // rax
  DWORD v26; // eax
  char *v27; // rax

  *((_DWORD *)this + 24) = a5;
  *((_QWORD *)this + 13) = a6;
  *((_QWORD *)this + 14) = a7;
  *((_DWORD *)this + 30) = a8;
  *((_DWORD *)this + 14) = a9;
  *((_QWORD *)this + 6) = a10;
  *((_QWORD *)this + 8) = a11;
  *((_DWORD *)this + 10) = a2;
  *((_DWORD *)this + 41) = a3;
  *((_QWORD *)this + 11) = a4;
  *((_DWORD *)this + 11) = GetCurrentThreadId();
  if ( a2 )
  {
    EventA = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 9) = EventA;
    if ( !EventA )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( g_fKirHttpBugFix2605 )
      {
        if ( (xmmword_180107A50 & 2) == 0 )
        {
LABEL_10:
          v22 = WINHTTP_ERROR_FROM_WIN32(v16);
          ThreadInfo = InternetGetThreadInfo();
          if ( ThreadInfo )
            *((_DWORD *)ThreadInfo + 7) = v16;
          return v22;
        }
        v17 = 10;
LABEL_6:
        WPP_SF_qdD(*((unsigned int *)this + 6), v17, v15, this, *((_DWORD *)this + 6), v16);
        goto LABEL_10;
      }
      if ( (xmmword_180107A50 & 2) == 0 )
        goto LABEL_10;
      v18 = InternetMapError(LastError);
      v21 = 11;
      goto LABEL_9;
    }
    v25 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 10) = v25;
    if ( !v25 )
    {
      v26 = GetLastError();
      v16 = v26;
      if ( g_fKirHttpBugFix2605 )
      {
        if ( (xmmword_180107A50 & 2) == 0 )
          goto LABEL_10;
        v17 = 12;
        goto LABEL_6;
      }
      if ( (xmmword_180107A50 & 2) == 0 )
        goto LABEL_10;
      v18 = InternetMapError(v26);
      v21 = 13;
LABEL_9:
      WPP_SF_qdsd(v19, v21, v20, (_DWORD)this, *((_DWORD *)this + 6), (__int64)v18, v16);
      goto LABEL_10;
    }
    return 0;
  }
  v27 = (char *)HeapAlloc(g_hWxProcessHeap, 0, 0x80u);
  if ( v27 )
  {
    *((_QWORD *)v27 + 9) = 0;
    *((_QWORD *)v27 + 11) = 0;
    *((_QWORD *)v27 + 10) = 0;
    *((_OWORD *)v27 + 6) = 0;
    *((_QWORD *)v27 + 8) = &HTTP_THREAD_POOL::WORK_ITEM::`vftable';
    *(_QWORD *)v27 = 0;
    *((_QWORD *)v27 + 1) = 0;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 3) = 0;
    *((_QWORD *)v27 + 4) = 0;
    *(_OWORD *)(v27 + 40) = 0;
    *((_QWORD *)v27 + 7) = 0;
    *((_QWORD *)this + 21) = v27;
    return 0;
  }
  *((_QWORD *)this + 21) = 0;
  if ( (xmmword_180107A50 & 2) != 0 )
    WPP_SF_qD(513, 14, WPP_6eddd303f6273b7c9ee1c50fc867b592_Traceguids, this);
  return 8;
}

```

## disassembly

```asm
0x180039160  push    rbx
0x180039162  push    rbp
0x180039163  push    rsi
0x180039164  push    rdi
0x180039165  sub     rsp, 48h
0x180039169  mov     eax, [rsp+68h+arg_20]
0x180039170  mov     ebx, edx
0x180039172  mov     [rcx+60h], eax
0x180039175  mov     rdi, rcx
0x180039178  mov     rax, [rsp+68h+arg_28]
0x180039180  xor     ebp, ebp
0x180039182  mov     [rcx+68h], rax
0x180039186  mov     rax, [rsp+68h+arg_30]
0x18003918e  mov     [rcx+70h], rax
0x180039192  mov     eax, [rsp+68h+arg_38]
0x180039199  mov     [rcx+78h], eax
0x18003919c  mov     eax, [rsp+68h+arg_40]
0x1800391a3  mov     [rcx+38h], eax
0x1800391a6  mov     rax, [rsp+68h+arg_48]
0x1800391ae  mov     [rcx+30h], rax
0x1800391b2  mov     rax, [rsp+68h+arg_50]
0x1800391ba  mov     [rcx+40h], rax
0x1800391be  mov     [rcx+28h], edx
0x1800391c1  mov     [rcx+0A4h], r8d
0x1800391c8  mov     [rcx+58h], r9
0x1800391cc  call    cs:__imp_GetCurrentThreadId
0x1800391d2  xor     edx, edx; dwFlags
0x1800391d4  mov     [rdi+2Ch], eax
0x1800391d7  test    ebx, ebx
0x1800391d9  jz      loc_1800392D7
0x1800391df  xor     r9d, r9d; lpName
0x1800391e2  xor     r8d, r8d; bInitialState
0x1800391e5  xor     ecx, ecx; lpEventAttributes
0x1800391e7  call    cs:__imp_CreateEventA
0x1800391ed  mov     [rdi+48h], rax
0x1800391f1  test    rax, rax
0x1800391f4  jnz     loc_18003927C
0x1800391fa  call    cs:__imp_GetLastError
0x180039200  cmp     cs:g_fKirHttpBugFix2605, bpl
0x180039207  mov     ebx, eax
0x180039209  jz      short loc_18003922E
0x18003920b  test    byte ptr cs:xmmword_180107A50, 2
0x180039212  jz      short loc_18003925B
0x180039214  mov     edx, 0Ah
0x180039219  mov     ecx, [rdi+18h]
0x18003921c  mov     r9, rdi
0x18003921f  mov     dword ptr [rsp+68h+var_40], ebx
0x180039223  mov     [rsp+68h+var_48], ecx
0x180039227  call    WPP_SF_qdD
0x18003922c  jmp     short loc_18003925B
0x18003922e  test    byte ptr cs:xmmword_180107A50, 2
0x180039235  jz      short loc_18003925B
0x180039237  mov     ecx, ebx; unsigned int
0x180039239  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x18003923e  mov     edx, 0Bh
0x180039243  mov     [rsp+68h+var_38], ebx
0x180039247  mov     r9, rdi
0x18003924a  mov     [rsp+68h+var_40], rax
0x18003924f  mov     eax, [rdi+18h]
0x180039252  mov     [rsp+68h+var_48], eax
0x180039256  call    WPP_SF_qdsd
0x18003925b  mov     ecx, ebx; unsigned int
0x18003925d  call    ?WINHTTP_ERROR_FROM_WIN32@@YAKK@Z; WINHTTP_ERROR_FROM_WIN32(ulong)
0x180039262  mov     edi, eax
0x180039264  call    ?InternetGetThreadInfo@@YAPEAU_INTERNET_THREAD_INFO@@XZ; InternetGetThreadInfo(void)
0x180039269  test    rax, rax
0x18003926c  jz      short loc_180039271
0x18003926e  mov     [rax+1Ch], ebx
0x180039271  mov     eax, edi
0x180039273  add     rsp, 48h
0x180039277  pop     rdi
0x180039278  pop     rsi
0x180039279  pop     rbp
0x18003927a  pop     rbx
0x18003927b  retn
0x18003927c  xor     r9d, r9d; lpName
0x18003927f  xor     r8d, r8d; bInitialState
0x180039282  xor     edx, edx; bManualReset
0x180039284  xor     ecx, ecx; lpEventAttributes
0x180039286  call    cs:__imp_CreateEventA
0x18003928c  mov     [rdi+50h], rax
0x180039290  test    rax, rax
0x180039293  jnz     loc_18003932F
0x180039299  call    cs:__imp_GetLastError
0x18003929f  cmp     cs:g_fKirHttpBugFix2605, bpl
0x1800392a6  mov     ebx, eax
0x1800392a8  jz      short loc_1800392BD
0x1800392aa  test    byte ptr cs:xmmword_180107A50, 2
0x1800392b1  jz      short loc_18003925B
0x1800392b3  mov     edx, 0Ch
0x1800392b8  jmp     loc_180039219
0x1800392bd  test    byte ptr cs:xmmword_180107A50, 2
0x1800392c4  jz      short loc_18003925B
0x1800392c6  mov     ecx, ebx; unsigned int
0x1800392c8  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x1800392cd  mov     edx, 0Dh
0x1800392d2  jmp     loc_180039243
0x1800392d7  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800392de  mov     r8d, 80h; dwBytes
0x1800392e4  call    cs:__imp_HeapAlloc
0x1800392ea  test    rax, rax
0x1800392ed  jz      short loc_18003933A
0x1800392ef  mov     [rax+48h], rbp
0x1800392f3  lea     rcx, ??_7WORK_ITEM@HTTP_THREAD_POOL@@6B@; const HTTP_THREAD_POOL::WORK_ITEM::`vftable'
0x1800392fa  mov     [rax+58h], rbp
0x1800392fe  xorps   xmm0, xmm0
0x180039301  mov     [rax+50h], rbp
0x180039305  movups  xmmword ptr [rax+60h], xmm0
0x180039309  mov     [rax+40h], rcx
0x18003930d  mov     [rax], rbp
0x180039310  mov     [rax+8], rbp
0x180039314  mov     [rax+10h], rbp
0x180039318  mov     [rax+18h], rbp
0x18003931c  mov     [rax+20h], rbp
0x180039320  movups  xmmword ptr [rax+28h], xmm0
0x180039324  mov     [rax+38h], rbp
0x180039328  mov     [rdi+0A8h], rax
0x18003932f  mov     eax, ebp
0x180039331  add     rsp, 48h
0x180039335  pop     rdi
0x180039336  pop     rsi
0x180039337  pop     rbp
0x180039338  pop     rbx
0x180039339  retn
0x18003933a  mov     [rdi+0A8h], rbp
0x180039341  test    byte ptr cs:xmmword_180107A50, 2
0x180039348  jz      short loc_18003936A
0x18003934a  mov     eax, [rdi+18h]
0x18003934d  lea     r8, WPP_6eddd303f6273b7c9ee1c50fc867b592_Traceguids
0x180039354  mov     edx, 0Eh
0x180039359  mov     [rsp+68h+var_48], eax
0x18003935d  mov     ecx, 201h
0x180039362  mov     r9, rdi
0x180039365  call    WPP_SF_qD
0x18003936a  mov     eax, 8
0x18003936f  add     rsp, 48h
0x180039373  pop     rdi
0x180039374  pop     rsi
0x180039375  pop     rbp
0x180039376  pop     rbx
0x180039377  retn
```

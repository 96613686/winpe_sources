# FileLogAddEx

- ea: `0x180018e40`
- end: `0x1800193f8`
- name: `FileLogAddEx`
- size: `1464`
- prototype: `void __fastcall(char, const wchar_t *, va_list)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180018138`
- `0x180018dfc`

## callees

- `0x180003ac0`
- `0x180018e40`
- `0x180019688`
- `0x1800298d0`
- `0x180029fa0`
- `0x18002d870`
- `0x180037164`
- `0x18003d270`
- `0x18004e894`
- `0x18004ea9c`
- `0x180063ef0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019309`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180019309`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800190a3`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019100`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180019100`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800190ec`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800190ec`
- `ntdll!RtlReleaseResource` at `0x180018fc2`
- `ntdll!RtlReleaseResource` at `0x180018fc2`
- `ntdll!RtlAcquireResourceShared` at `0x180018f5e`
- `ntdll!RtlAcquireResourceShared` at `0x180018f5e`

## pseudocode

```c
void __fastcall FileLogAddEx(char a1, const wchar_t *a2, va_list a3)
{
  void *v6; // rsp
  __int64 *v7; // rsi
  char v8; // r12
  unsigned __int16 *v9; // r13
  void *v10; // rsp
  unsigned __int16 *v11; // rdi
  __int64 *v12; // rax
  unsigned __int16 *v13; // rax
  size_t *v14; // r8
  FILETIME v15; // rbx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v17; // r8
  __int64 v18; // rax
  unsigned __int64 v20; // r15
  unsigned __int64 v21; // rbx
  unsigned __int64 v22; // rcx
  __int64 v23; // rcx
  void *v24; // rsp
  void *v25; // rsp
  unsigned __int16 *v26; // rax
  const wchar_t *i; // r14
  wchar_t *v28; // rax
  unsigned __int64 v29; // rbx
  char v30; // r15
  unsigned __int64 v31; // rbx
  _BYTE v32[32]; // [rsp-20h] [rbp-A80h] BYREF
  va_list argList; // [rsp+0h] [rbp-A60h]
  __int64 v34; // [rsp+8h] [rbp-A58h]
  __int64 v35; // [rsp+10h] [rbp-A50h]
  __int64 v36; // [rsp+18h] [rbp-A48h]
  __int64 v37; // [rsp+20h] [rbp-A40h]
  __int64 v38; // [rsp+28h] [rbp-A38h]
  int v39; // [rsp+40h] [rbp-A20h] BYREF
  _BYTE v40[424]; // [rsp+48h] [rbp-A18h] BYREF
  int v41; // [rsp+1F0h] [rbp-870h] BYREF
  int v42; // [rsp+250h] [rbp-810h] BYREF
  __int64 v43; // [rsp+258h] [rbp-808h] BYREF
  FILETIME FileTime; // [rsp+A60h] [rbp+0h] BYREF
  struct _FILETIME LocalFileTime; // [rsp+A68h] [rbp+8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A70h] [rbp+10h] BYREF

  FileTime = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x800 && (unsigned __int64)(g_ulAdditionalProbeSize + 2056) >= 0x800 )
  {
    if ( (unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
    {
      v6 = alloca(2064);
      if ( &v41 != (int *)-96LL )
      {
        v7 = &v43;
        v42 = 1801679955;
        if ( &v42 != (int *)-8LL )
          goto LABEL_6;
      }
    }
  }
  v12 = (__int64 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(2056);
  v7 = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = 1885431112;
    v7 = v12 + 1;
  }
  if ( v7 )
  {
LABEL_6:
    v8 = 0;
    v9 = 0;
    if ( (unsigned __int64)g_ulMaxStackAllocSize < 0x200
      || (unsigned __int64)(g_ulAdditionalProbeSize + 520) < 0x200
      || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)()
      || (v10 = alloca(528), v32 == (_BYTE *)-96LL)
      || (v39 = 1801679955, (v11 = (unsigned __int16 *)v40) == 0) )
    {
      v13 = (unsigned __int16 *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(520);
      v11 = v13;
      if ( v13 )
      {
        *(_DWORD *)v13 = 1885431112;
        v11 = v13 + 4;
      }
    }
    if ( v11 )
    {
      if ( RtlAcquireResourceShared((PRTL_RESOURCE)((char *)_pflstate + 80), 1u) )
      {
        v8 = 1;
        if ( *((_QWORD *)_pflstate + 5) )
        {
          FLTI_FreeAsManyAsPossible();
          if ( StringVPrintfWorkerW((STRSAFE_LPWSTR)v7, 0x400u, v14, a2, a3) < 0 )
          {
            *(_DWORD *)((char *)v7 + 2042) = 655395;
            *((_WORD *)v7 + 1023) = 0;
          }
          if ( a1 )
            goto LABEL_38;
          AccurateGetSystemTime((unsigned __int64 *)&FileTime);
          if ( (*(_DWORD *)_pflstate & 1) != 0 )
          {
            v15 = FileTime;
            CurrentThreadId = GetCurrentThreadId();
            StringCchPrintfW(v11, 0x100u, L"%08X:%016I64X:", CurrentThreadId, v15);
          }
          else if ( (*(_DWORD *)_pflstate & 2) != 0 )
          {
            LocalFileTime = 0;
            SystemTime = 0;
            FileTimeToLocalFileTime(&FileTime, &LocalFileTime);
            FileTimeToSystemTime(&LocalFileTime, &SystemTime);
            LODWORD(v38) = SystemTime.wMilliseconds;
            LODWORD(v37) = SystemTime.wSecond;
            LODWORD(v36) = SystemTime.wMinute;
            LODWORD(v35) = SystemTime.wHour;
            LODWORD(v34) = SystemTime.wDay;
            LODWORD(argList) = SystemTime.wMonth;
            StringCchPrintfW(
              v11,
              0x100u,
              L"%d/%02d/%02d %02d:%02d:%02d.%03d%04I64d - ",
              SystemTime.wYear,
              argList,
              v34,
              v35,
              v36,
              v37,
              v38,
              *(unsigned __int64 *)&FileTime % 0x2710);
          }
          else
          {
            v17 = *(unsigned __int64 *)&FileTime / 0x989680 / 0x3C;
            LODWORD(v36) = *(unsigned __int64 *)&FileTime % 0x989680;
            LODWORD(v35) = *(unsigned __int64 *)&FileTime / 0x989680 % 0x3C;
            LODWORD(v34) = v17 % 0x3C;
            LODWORD(argList) = v17 / 0x3C % 0x18;
            StringCchPrintfW(
              v11,
              0x100u,
              L"%u %02u:%02u:%02u.%07us - ",
              (unsigned int)(v17 / 0x3C / 0x18),
              argList,
              v34,
              v35,
              v36);
          }
          if ( (int)FLTI_Append(v11) >= 0 )
          {
LABEL_38:
            v18 = -1;
            while ( *((_WORD *)v7 + ++v18) != 0 )
              ;
            v20 = v18 + 3;
            v21 = 2 * (v18 + 3);
            LocalFileTime = (struct _FILETIME)(v18 + 3);
            if ( !v21 )
              goto LABEL_67;
            if ( v21 > g_ulMaxStackAllocSize )
              goto LABEL_67;
            v22 = v21 + g_ulAdditionalProbeSize + 8;
            if ( v22 < v21 || !(unsigned int)VerifyStackAvailable(v22, 10) )
              goto LABEL_67;
            v23 = v21 + 23;
            if ( v21 + 23 <= v21 + 8 )
              v23 = 0xFFFFFFFFFFFFFF0LL;
            v24 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
            v25 = alloca(v23 & 0xFFFFFFFFFFFFFFF0uLL);
            v9 = (unsigned __int16 *)&v39;
            if ( v32 == (_BYTE *)-96LL || (v39 = 1801679955, (v9 = (unsigned __int16 *)v40) == 0) )
            {
LABEL_67:
              if ( v21 + 8 >= v21 )
              {
                v26 = (unsigned __int16 *)((__int64 (__fastcall *)(unsigned __int64, __int64))g_pfnAllocate)(
                                            v21 + 8,
                                            10);
                v9 = v26;
                if ( v26 )
                {
                  *(_DWORD *)v26 = 1885431112;
                  v9 = v26 + 4;
                }
              }
            }
            if ( v9 )
            {
              for ( i = (const wchar_t *)v7; *i; i += v31 )
              {
                v28 = wcschr(i, 0xAu);
                if ( v28 )
                {
                  v29 = (unsigned int)(v28 - i) + 2;
                  StringCchCopyNW(v9, v20, i, v29);
                  *(_DWORD *)&v9[v29 - 1] = 10;
                  v30 = 1;
                  v9[v29 - 2] = 13;
                  v31 = v29 - 1;
                }
                else
                {
                  v30 = 0;
                  v31 = -1;
                  do
                    ++v31;
                  while ( i[v31] );
                  StringCchCopyNW(v9, *(_QWORD *)&LocalFileTime, i, v31);
                  v9[v31] = 0;
                }
                if ( (int)FLTI_Append(v9) < 0 || v30 && (int)FLTI_Flush() < 0 )
                  break;
                v20 = (unsigned __int64)LocalFileTime;
              }
            }
          }
        }
      }
    }
    if ( *((_DWORD *)v7 - 2) == 1885431112 )
      ((void (__fastcall *)(__int64 *))g_pfnFree)(v7 - 1);
    if ( v11 && *((_DWORD *)v11 - 2) == 1885431112 )
      ((void (__fastcall *)(unsigned __int16 *))g_pfnFree)(v11 - 4);
    if ( v9 && *((_DWORD *)v9 - 2) == 1885431112 )
      ((void (__fastcall *)(unsigned __int16 *))g_pfnFree)(v9 - 4);
    if ( v8 )
      RtlReleaseResource((PRTL_RESOURCE)((char *)_pflstate + 80));
  }
}

```

## disassembly

```asm
0x180018e40  push    rbp
0x180018e42  push    rsi
0x180018e43  push    rdi
0x180018e44  push    r12
0x180018e46  push    r13
0x180018e48  push    r14
0x180018e4a  push    r15
0x180018e4c  sub     rsp, 90h
0x180018e53  lea     rbp, [rsp+60h]
0x180018e58  mov     [rbp+60h+arg_0], rbx
0x180018e5c  mov     rax, cs:__security_cookie
0x180018e63  xor     rax, rbp
0x180018e66  mov     [rbp+60h+var_40], rax
0x180018e6a  cmp     cs:g_ulMaxStackAllocSize, 800h
0x180018e75  mov     r15, r8
0x180018e78  mov     r14, rdx
0x180018e7b  mov     qword ptr [rbp+60h+FileTime.dwLowDateTime], 0
0x180018e83  movzx   ebx, cl
0x180018e86  jb      loc_180018FF9
0x180018e8c  mov     rcx, cs:g_ulAdditionalProbeSize
0x180018e93  add     rcx, 808h
0x180018e9a  cmp     rcx, 800h
0x180018ea1  jb      loc_180018FF9
0x180018ea7  call    VerifyStackAvailable
0x180018eac  test    eax, eax
0x180018eae  jz      loc_180018FF9
0x180018eb4  mov     eax, [rsp+0C0h+var_C0]
0x180018eb7  mov     eax, 810h
0x180018ebc  sub     rsp, rax
0x180018ebf  lea     rcx, [rsp+8D0h+var_870]
0x180018ec4  mov     eax, [rcx]
0x180018ec6  test    rcx, rcx
0x180018ec9  jz      loc_180018FF9
0x180018ecf  lea     rsi, [rcx+8]
0x180018ed3  mov     dword ptr [rcx], 6B637453h
0x180018ed9  test    rsi, rsi
0x180018edc  jz      loc_180018FF9
0x180018ee2  xor     r12b, r12b
0x180018ee5  xor     r13d, r13d
0x180018ee8  cmp     cs:g_ulMaxStackAllocSize, 200h
0x180018ef3  jb      loc_18001901E
0x180018ef9  mov     rcx, cs:g_ulAdditionalProbeSize
0x180018f00  add     rcx, 208h
0x180018f07  cmp     rcx, 200h
0x180018f0e  jb      loc_18001901E
0x180018f14  call    VerifyStackAvailable
0x180018f19  test    eax, eax
0x180018f1b  jz      loc_18001901E
0x180018f21  mov     eax, [rsp+8D0h+var_8D0]
0x180018f24  mov     eax, 210h
0x180018f29  sub     rsp, rax
0x180018f2c  lea     rdi, [rsp+0AE0h+var_A80]
0x180018f31  mov     eax, [rdi]
0x180018f33  test    rdi, rdi
0x180018f36  jz      loc_18001901E
0x180018f3c  mov     dword ptr [rdi], 6B637453h
0x180018f42  add     rdi, 8
0x180018f46  jz      loc_18001901E
0x180018f4c  test    rdi, rdi
0x180018f4f  jz      short loc_180018F82
0x180018f51  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180018f58  mov     dl, 1; Wait
0x180018f5a  add     rcx, 50h ; 'P'; Resource
0x180018f5e  call    cs:__imp_RtlAcquireResourceShared
0x180018f65  nop     dword ptr [rax+rax+00h]
0x180018f6a  test    al, al
0x180018f6c  jz      short loc_180018F82
0x180018f6e  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180018f75  mov     r12b, 1
0x180018f78  cmp     [rax+28h], r13
0x180018f7c  jnz     loc_18001904A
0x180018f82  cmp     dword ptr [rsi-8], 70616548h
0x180018f89  lea     rcx, [rsi-8]
0x180018f8d  jz      loc_1800193B3
0x180018f93  test    rdi, rdi
0x180018f96  jz      short loc_180018FA9
0x180018f98  cmp     dword ptr [rdi-8], 70616548h
0x180018f9f  lea     rcx, [rdi-8]
0x180018fa3  jz      loc_1800193C4
0x180018fa9  test    r13, r13
0x180018fac  jnz     loc_1800193D5
0x180018fb2  test    r12b, r12b
0x180018fb5  jz      short loc_180018FCE
0x180018fb7  mov     rcx, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180018fbe  add     rcx, 50h ; 'P'; Resource
0x180018fc2  call    cs:__imp_RtlReleaseResource
0x180018fc9  nop     dword ptr [rax+rax+00h]
0x180018fce  mov     rcx, [rbp+60h+var_40]
0x180018fd2  xor     rcx, rbp; StackCookie
0x180018fd5  call    __security_check_cookie
0x180018fda  mov     rbx, [rbp+60h+arg_0]
0x180018fde  lea     rsp, [rbp+30h]
0x180018fe2  pop     r15
0x180018fe4  pop     r14
0x180018fe6  pop     r13
0x180018fe8  pop     r12
0x180018fea  pop     rdi
0x180018feb  pop     rsi
0x180018fec  pop     rbp
0x180018fed  retn
0x180018fef  test    rsi, rsi
0x180018ff2  jz      short loc_180018FCE
0x180018ff4  jmp     loc_180018EE2
0x180018ff9  mov     rax, cs:g_pfnAllocate
0x180019000  mov     ecx, 808h
0x180019005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001900a  mov     rsi, rax
0x18001900d  test    rax, rax
0x180019010  jz      short loc_180018FEF
0x180019012  mov     dword ptr [rax], 70616548h
0x180019018  add     rsi, 8
0x18001901c  jmp     short loc_180018FEF
0x18001901e  mov     rax, cs:g_pfnAllocate
0x180019025  mov     ecx, 208h
0x18001902a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001902f  mov     rdi, rax
0x180019032  test    rax, rax
0x180019035  jz      loc_180018F4C
0x18001903b  mov     dword ptr [rax], 70616548h
0x180019041  add     rdi, 8
0x180019045  jmp     loc_180018F4C
0x18001904a  call    ?FLTI_FreeAsManyAsPossible@@YA_NXZ; FLTI_FreeAsManyAsPossible(void)
0x18001904f  mov     r9, r14; pszFormat
0x180019052  mov     [rsp+0AE0h+argList], r15; argList
0x180019057  mov     edx, 400h; cchDest
0x18001905c  mov     rcx, rsi; pszDest
0x18001905f  call    StringVPrintfWorkerW
0x180019064  mov     edx, 0Ah
0x180019069  test    eax, eax
0x18001906b  jns     short loc_180019080
0x18001906d  xor     eax, eax
0x18001906f  mov     dword ptr [rsi+7FAh], 0A0023h
0x180019079  mov     [rsi+7FEh], ax
0x180019080  test    bl, bl
0x180019082  jnz     loc_18001922F
0x180019088  lea     rcx, [rbp+60h+FileTime]; unsigned __int64 *
0x18001908c  call    ?AccurateGetSystemTime@@YAXPEA_K@Z; AccurateGetSystemTime(unsigned __int64 *)
0x180019091  mov     rax, cs:?_pflstate@@3PEAUFileLogState@@EA; FileLogState * _pflstate
0x180019098  mov     ecx, [rax]
0x18001909a  test    r12b, cl
0x18001909d  jz      short loc_1800190D0
0x18001909f  mov     rbx, qword ptr [rbp+60h+FileTime.dwLowDateTime]
0x1800190a3  call    cs:__imp_GetCurrentThreadId
0x1800190aa  nop     dword ptr [rax+rax+00h]
0x1800190af  lea     r8, a08x016i64x; "%08X:%016I64X:"
0x1800190b6  mov     [rsp+0AE0h+argList], rbx
0x1800190bb  mov     r9d, eax
0x1800190be  mov     edx, 100h; unsigned __int64
0x1800190c3  mov     rcx, rdi; unsigned __int16 *
0x1800190c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800190cb  jmp     loc_18001921A
0x1800190d0  test    cl, 2
0x1800190d3  jz      loc_180019184
0x1800190d9  xorps   xmm0, xmm0
0x1800190dc  mov     qword ptr [rbp+60h+LocalFileTime.dwLowDateTime], r13
0x1800190e0  lea     rdx, [rbp+60h+LocalFileTime]; lpLocalFileTime
0x1800190e4  lea     rcx, [rbp+60h+FileTime]; lpFileTime
0x1800190e8  movups  xmmword ptr [rbp+60h+SystemTime.wYear], xmm0
0x1800190ec  call    cs:__imp_FileTimeToLocalFileTime
0x1800190f3  nop     dword ptr [rax+rax+00h]
0x1800190f8  lea     rdx, [rbp+60h+SystemTime]; lpSystemTime
0x1800190fc  lea     rcx, [rbp+60h+LocalFileTime]; lpFileTime
0x180019100  call    cs:__imp_FileTimeToSystemTime
0x180019107  nop     dword ptr [rax+rax+00h]
0x18001910c  mov     rbx, qword ptr [rbp+60h+FileTime.dwLowDateTime]
0x180019110  mov     rax, 346DC5D63886594Bh
0x18001911a  movzx   ecx, [rbp+60h+SystemTime.wSecond]
0x18001911e  movzx   r8d, [rbp+60h+SystemTime.wHour]
0x180019123  movzx   r10d, [rbp+60h+SystemTime.wDay]
0x180019128  movzx   r11d, [rbp+60h+SystemTime.wMonth]
0x18001912d  movzx   r9d, [rbp+60h+SystemTime.wYear]
0x180019132  mul     rbx
0x180019135  shr     rdx, 0Bh
0x180019139  imul    rax, rdx, 2710h
0x180019140  movzx   edx, [rbp+60h+SystemTime.wMinute]
0x180019144  sub     rbx, rax
0x180019147  movzx   eax, [rbp+60h+SystemTime.wMilliseconds]
0x18001914b  mov     [rsp+0AE0h+var_A90], rbx
0x180019150  mov     dword ptr [rsp+0AE0h+var_A98], eax
0x180019154  mov     dword ptr [rsp+0AE0h+var_AA0], ecx
0x180019158  mov     rcx, rdi; unsigned __int16 *
0x18001915b  mov     dword ptr [rsp+0AE0h+var_AA8], edx
0x18001915f  mov     edx, 100h; unsigned __int64
0x180019164  mov     dword ptr [rsp+0AE0h+var_AB0], r8d
0x180019169  lea     r8, aD02d02d02d02d0; "%d/%02d/%02d %02d:%02d:%02d.%03d%04I64d"...
0x180019170  mov     dword ptr [rsp+0AE0h+var_AB8], r10d
0x180019175  mov     dword ptr [rsp+0AE0h+argList], r11d
0x18001917a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001917f  jmp     loc_18001921A
0x180019184  mov     r10, qword ptr [rbp+60h+FileTime.dwLowDateTime]
0x180019188  mov     rcx, 8888888888888889h
0x180019192  mov     rax, 0D6BF94D5E57A42BDh
0x18001919c  mul     r10
0x18001919f  mov     rax, rcx
0x1800191a2  mov     r9, rdx
0x1800191a5  shr     r9, 17h
0x1800191a9  mul     r9
0x1800191ac  mov     rax, rcx
0x1800191af  mov     r8, rdx
0x1800191b2  shr     r8, 5
0x1800191b6  mul     r8
0x1800191b9  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800191c3  mov     rcx, rdx
0x1800191c6  shr     rcx, 5
0x1800191ca  mul     rcx
0x1800191cd  imul    eax, r9d, 989680h
0x1800191d4  shr     rdx, 4
0x1800191d8  sub     r10d, eax
0x1800191db  imul    eax, r8d, 3Ch ; '<'
0x1800191df  mov     dword ptr [rsp+0AE0h+var_AA8], r10d
0x1800191e4  sub     r9d, eax
0x1800191e7  imul    eax, ecx, 3Ch ; '<'
0x1800191ea  mov     dword ptr [rsp+0AE0h+var_AB0], r9d
0x1800191ef  mov     r9d, edx
0x1800191f2  sub     r8d, eax
0x1800191f5  lea     eax, [rdx+rdx*2]
0x1800191f8  mov     dword ptr [rsp+0AE0h+var_AB8], r8d
0x1800191fd  mov     edx, 100h; unsigned __int64
0x180019202  shl     eax, 3
0x180019205  lea     r8, aU02u02u02u07us; "%u %02u:%02u:%02u.%07us - "
0x18001920c  sub     ecx, eax
0x18001920e  mov     dword ptr [rsp+0AE0h+argList], ecx
0x180019212  mov     rcx, rdi; unsigned __int16 *
0x180019215  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001921a  mov     rcx, rdi; unsigned __int16 *
0x18001921d  call    ?FLTI_Append@@YAJPEAG@Z; FLTI_Append(ushort *)
0x180019222  test    eax, eax
0x180019224  js      loc_180018F82
0x18001922a  mov     edx, 0Ah
0x18001922f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019236  cmp     [rsi+rax*2+2], r13w
0x18001923c  lea     rax, [rax+1]
0x180019240  jnz     short loc_180019236
0x180019242  lea     r15, [rax+3]
0x180019246  lea     rbx, [r15+r15]
0x18001924a  mov     qword ptr [rbp+60h+LocalFileTime.dwLowDateTime], r15
0x18001924e  test    rbx, rbx
0x180019251  jz      short loc_1800192C2
0x180019253  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001925a  ja      short loc_1800192C2
0x18001925c  mov     rcx, cs:g_ulAdditionalProbeSize
0x180019263  add     rcx, 8
0x180019267  add     rcx, rbx
0x18001926a  cmp     rcx, rbx
0x18001926d  jb      short loc_1800192C2
0x18001926f  call    VerifyStackAvailable
0x180019274  test    eax, eax
0x180019276  jz      short loc_1800192BD
0x180019278  lea     rax, [rbx+8]
0x18001927c  lea     rcx, [rax+0Fh]
0x180019280  cmp     rcx, rax
0x180019283  ja      short loc_18001928F
0x180019285  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001928f  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180019293  mov     rax, rcx
0x180019296  call    _alloca_probe
0x18001929b  sub     rsp, rcx
0x18001929e  mov     edx, 0Ah
0x1800192a3  lea     r13, [rsp+0AE0h+var_A80]
0x1800192a8  test    r13, r13
0x1800192ab  jz      short loc_1800192C2
0x1800192ad  mov     dword ptr [r13+0], 6B637453h
0x1800192b5  add     r13, 8
0x1800192b9  jz      short loc_1800192C2
0x1800192bb  jmp     short loc_1800192EE
0x1800192bd  mov     edx, 0Ah
0x1800192c2  lea     rcx, [rbx+8]
0x1800192c6  cmp     rcx, rbx
0x1800192c9  jb      short loc_1800192EE
0x1800192cb  mov     rax, cs:g_pfnAllocate
0x1800192d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192d7  mov     r13, rax
0x1800192da  mov     edx, 0Ah; Ch
0x1800192df  test    rax, rax
0x1800192e2  jz      short loc_1800192EE
0x1800192e4  mov     dword ptr [rax], 70616548h
0x1800192ea  add     r13, 8
0x1800192ee  test    r13, r13
0x1800192f1  jz      loc_180018F82
0x1800192f7  mov     r14, rsi
0x1800192fa  xor     eax, eax
0x1800192fc  cmp     ax, [r14]
0x180019300  jz      loc_180018F82
0x180019306  mov     rcx, r14; Str
0x180019309  call    cs:__imp_wcschr
0x180019310  nop     dword ptr [rax+rax+00h]
0x180019315  test    rax, rax
0x180019318  jz      short loc_180019350
0x18001931a  sub     rax, r14
0x18001931d  mov     r8, r14; unsigned __int16 *
0x180019320  sar     rax, 1
0x180019323  mov     rdx, r15; unsigned __int64
0x180019326  add     eax, 2
0x180019329  mov     rcx, r13; unsigned __int16 *
0x18001932c  mov     r9d, eax; unsigned __int64
0x18001932f  mov     ebx, eax
0x180019331  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180019336  mov     dword ptr [r13+rbx*2-2], 0Ah
0x18001933f  movzx   r15d, r12b
0x180019343  mov     word ptr [r13+rbx*2-4], 0Dh
  ... truncated ...
```

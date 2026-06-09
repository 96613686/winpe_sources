# CMUILocale::GetFunctionPointers(void)

- ea: `0x180014f20`
- end: `0x180015355`
- name: `?GetFunctionPointers@CMUILocale@@CAJXZ`
- size: `1077`
- prototype: `__int64(void)`
- caller_count: `9`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180011480`
- `0x1800135a0`
- `0x180013720`
- `0x1800141e0`
- `0x1800144e0`
- `0x1800145d0`
- `0x1800146e0`
- `0x180016000`
- `0x180017080`

## callees

- `0x180013564`
- `0x180014120`
- `0x180014f20`
- `0x180016730`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015082`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015082`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800150ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001525e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001514a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800151a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015202`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001525e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014fe0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015000`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015060`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014fc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014fe0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015000`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015020`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015060`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014f8f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014fa4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014f8f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180014fa4`

## string_xrefs

- `0x180014fb6`: `GetThreadPreferredUILanguages`
- `0x180014f9d`: `api-ms-win-core-localization-obsolete-l1-1-0.dll`
- `0x180014f88`: `api-ms-win-core-localization-l1-2-0.dll`
- `0x180014fd6`: `SetThreadPreferredUILanguages`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CMUILocale::GetFunctionPointers(void)
{
  HMODULE Library; // rbx
  HMODULE v2; // rdi
  signed int v3; // eax
  signed int v4; // ebx
  _QWORD *v5; // rcx
  signed int v6; // eax
  __int64 v7; // rdx
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  signed int v11; // eax
  signed int LastError; // eax
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF

  if ( CMUILocale::m_hKernel32 )
    goto LABEL_2;
  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, &CMUILocale::m_csFunctionPointers);
  if ( !CMUILocale::m_hKernel32 )
  {
    Library = LoadLibraryExW(L"api-ms-win-core-localization-l1-2-0.dll", 0, 8u);
    v2 = LoadLibraryExW(L"api-ms-win-core-localization-obsolete-l1-1-0.dll", 0, 8u);
    if ( Library )
    {
      CMUILocale::m_fGetThreadPreferredUILanguages = GetProcAddress(Library, "GetThreadPreferredUILanguages");
      if ( CMUILocale::m_fGetThreadPreferredUILanguages )
      {
        CMUILocale::m_fSetThreadPreferredUILanguages = GetProcAddress(Library, "SetThreadPreferredUILanguages");
        if ( CMUILocale::m_fSetThreadPreferredUILanguages )
        {
          CMUILocale::m_fLocaleNameToLCID = GetProcAddress(Library, "LocaleNameToLCID");
          if ( CMUILocale::m_fLocaleNameToLCID )
          {
            CMUILocale::m_fGetLocaleInfoEx = GetProcAddress(Library, "GetLocaleInfoEx");
            if ( CMUILocale::m_fGetLocaleInfoEx )
            {
              CMUILocale::m_fLCIDToLocaleName = GetProcAddress(v2, "LCIDToLocaleName");
              if ( CMUILocale::m_fLCIDToLocaleName )
              {
                CMUILocale::m_fGetSystemDefaultLocaleName = GetProcAddress(v2, "GetSystemDefaultLocaleName");
                if ( CMUILocale::m_fGetSystemDefaultLocaleName )
                {
                  CMUILocale::m_hKernel32 = Library;
                  goto LABEL_14;
                }
                LastError = GetLastError();
                v4 = LastError;
                if ( LastError > 0 )
                  v4 = (unsigned __int16)LastError | 0x80070000;
                if ( v4 < 0 )
                  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
LABEL_22:
                  LeaveCriticalSection(lpCriticalSection);
                  return (unsigned int)v4;
                }
                v7 = 16;
              }
              else
              {
                v11 = GetLastError();
                v4 = v11;
                if ( v11 > 0 )
                  v4 = (unsigned __int16)v11 | 0x80070000;
                if ( v4 < 0 )
                  CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
                v5 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_22;
                }
                v7 = 15;
              }
            }
            else
            {
              v10 = GetLastError();
              v4 = v10;
              if ( v10 > 0 )
                v4 = (unsigned __int16)v10 | 0x80070000;
              if ( v4 < 0 )
                CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
              v5 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_22;
              }
              v7 = 14;
            }
          }
          else
          {
            v9 = GetLastError();
            v4 = v9;
            if ( v9 > 0 )
              v4 = (unsigned __int16)v9 | 0x80070000;
            if ( v4 < 0 )
              CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_22;
            }
            v7 = 13;
          }
        }
        else
        {
          v8 = GetLastError();
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
          if ( v4 < 0 )
            CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_22;
          }
          v7 = 12;
        }
      }
      else
      {
        v3 = GetLastError();
        v4 = v3;
        if ( v3 > 0 )
          v4 = (unsigned __int16)v3 | 0x80070000;
        if ( v4 < 0 )
          CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_22;
        }
        v7 = 11;
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      if ( v4 < 0 )
        CMemoryLog::Write((CMemoryLog *)qword_18006A9C0, v4);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_22;
      }
      v7 = 10;
    }
    WPP_SF_D(v5[2], v7, WPP_6f99fdf990383d18e8dfd3c8d83499a1_Traceguids, (unsigned int)v4);
    goto LABEL_22;
  }
LABEL_14:
  LeaveCriticalSection(lpCriticalSection);
LABEL_2:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6f99fdf990383d18e8dfd3c8d83499a1_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180014f20  mov     [rsp+arg_8], rbx
0x180014f25  push    rdi
0x180014f26  sub     rsp, 20h
0x180014f2a  cmp     cs:?m_hKernel32@CMUILocale@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CMUILocale::m_hKernel32
0x180014f32  jz      short loc_180014F5E
0x180014f34  lea     rax, WPP_GLOBAL_Control
0x180014f3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f42  cmp     rcx, rax
0x180014f45  jz      short loc_180014F51
0x180014f47  test    byte ptr [rcx+1Ch], 1
0x180014f4b  jnz     loc_18001508D
0x180014f51  xor     eax, eax
0x180014f53  mov     rbx, [rsp+28h+arg_8]
0x180014f58  add     rsp, 20h
0x180014f5c  pop     rdi
0x180014f5d  retn
0x180014f5e  lea     rdx, ?m_csFunctionPointers@CMUILocale@@0VCCritSec@@A; struct _RTL_CRITICAL_SECTION *
0x180014f65  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x180014f6a  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180014f6f  nop
0x180014f70  cmp     cs:?m_hKernel32@CMUILocale@@0PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * CMUILocale::m_hKernel32
0x180014f78  jnz     loc_18001507D
0x180014f7e  mov     edi, 8
0x180014f83  mov     r8d, edi; dwFlags
0x180014f86  xor     edx, edx; hFile
0x180014f88  lea     rcx, aApiMsWinCoreLo_1; "api-ms-win-core-localization-l1-2-0.dll"
0x180014f8f  call    cs:__imp_LoadLibraryExW
0x180014f95  mov     rbx, rax
0x180014f98  mov     r8d, edi; dwFlags
0x180014f9b  xor     edx, edx; hFile
0x180014f9d  lea     rcx, aApiMsWinCoreLo_3; "api-ms-win-core-localization-obsolete-l"...
0x180014fa4  call    cs:__imp_LoadLibraryExW
0x180014faa  mov     rdi, rax
0x180014fad  test    rbx, rbx
0x180014fb0  jz      loc_1800150FA
0x180014fb6  lea     rdx, aGetthreadprefe_0; "GetThreadPreferredUILanguages"
0x180014fbd  mov     rcx, rbx; hModule
0x180014fc0  call    cs:__imp_GetProcAddress
0x180014fc6  mov     cs:?m_fGetThreadPreferredUILanguages@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fGetThreadPreferredUILanguages
0x180014fcd  test    rax, rax
0x180014fd0  jz      loc_1800150B4
0x180014fd6  lea     rdx, aSetthreadprefe_0; "SetThreadPreferredUILanguages"
0x180014fdd  mov     rcx, rbx; hModule
0x180014fe0  call    cs:__imp_GetProcAddress
0x180014fe6  mov     cs:?m_fSetThreadPreferredUILanguages@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fSetThreadPreferredUILanguages
0x180014fed  test    rax, rax
0x180014ff0  jz      loc_18001514A
0x180014ff6  lea     rdx, aLocalenametolc_0; "LocaleNameToLCID"
0x180014ffd  mov     rcx, rbx; hModule
0x180015000  call    cs:__imp_GetProcAddress
0x180015006  mov     cs:?m_fLocaleNameToLCID@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fLocaleNameToLCID
0x18001500d  test    rax, rax
0x180015010  jz      loc_1800151A6
0x180015016  lea     rdx, aGetlocaleinfoe; "GetLocaleInfoEx"
0x18001501d  mov     rcx, rbx; hModule
0x180015020  call    cs:__imp_GetProcAddress
0x180015026  mov     cs:?m_fGetLocaleInfoEx@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fGetLocaleInfoEx
0x18001502d  test    rax, rax
0x180015030  jz      loc_180015202
0x180015036  lea     rdx, aLcidtolocalena_0; "LCIDToLocaleName"
0x18001503d  mov     rcx, rdi; hModule
0x180015040  call    cs:__imp_GetProcAddress
0x180015046  mov     cs:?m_fLCIDToLocaleName@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fLCIDToLocaleName
0x18001504d  test    rax, rax
0x180015050  jz      loc_18001525E
0x180015056  lea     rdx, aGetsystemdefau_1; "GetSystemDefaultLocaleName"
0x18001505d  mov     rcx, rdi; hModule
0x180015060  call    cs:__imp_GetProcAddress
0x180015066  mov     cs:?m_fGetSystemDefaultLocaleName@CMUILocale@@0PEAXEA, rax; void * CMUILocale::m_fGetSystemDefaultLocaleName
0x18001506d  test    rax, rax
0x180015070  jz      loc_1800152B7
0x180015076  mov     cs:?m_hKernel32@CMUILocale@@0PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * CMUILocale::m_hKernel32
0x18001507d  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x180015082  call    cs:__imp_LeaveCriticalSection
0x180015088  jmp     loc_180014F34
0x18001508d  cmp     byte ptr [rcx+19h], 2
0x180015091  jb      loc_180014F51
0x180015097  mov     edx, 11h
0x18001509c  xor     r9d, r9d
0x18001509f  lea     r8, WPP_6f99fdf990383d18e8dfd3c8d83499a1_Traceguids
0x1800150a6  mov     rcx, [rcx+10h]
0x1800150aa  call    WPP_SF_D
0x1800150af  jmp     loc_180014F51
0x1800150b4  call    cs:__imp_GetLastError
0x1800150ba  mov     ebx, eax
0x1800150bc  test    eax, eax
0x1800150be  jle     short loc_1800150C9
0x1800150c0  movzx   ebx, ax
0x1800150c3  or      ebx, 80070000h
0x1800150c9  test    ebx, ebx
0x1800150cb  js      loc_180015326
0x1800150d1  lea     rax, WPP_GLOBAL_Control
0x1800150d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150df  cmp     rcx, rax
0x1800150e2  jnz     loc_180015339
0x1800150e8  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1800150ed  call    cs:__imp_LeaveCriticalSection
0x1800150f3  mov     eax, ebx
0x1800150f5  jmp     loc_180014F53
0x1800150fa  call    cs:__imp_GetLastError
0x180015100  mov     ebx, eax
0x180015102  test    eax, eax
0x180015104  jle     short loc_18001510F
0x180015106  movzx   ebx, ax
0x180015109  or      ebx, 80070000h
0x18001510f  test    ebx, ebx
0x180015111  jns     short loc_180015121
0x180015113  mov     edx, ebx; int
0x180015115  lea     rcx, qword_18006A9C0; this
0x18001511c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015121  lea     rax, WPP_GLOBAL_Control
0x180015128  mov     rcx, cs:WPP_GLOBAL_Control
0x18001512f  cmp     rcx, rax
0x180015132  jz      short loc_1800150E8
0x180015134  test    byte ptr [rcx+1Ch], 1
0x180015138  jz      short loc_1800150E8
0x18001513a  cmp     byte ptr [rcx+19h], 2
0x18001513e  jb      short loc_1800150E8
0x180015140  mov     edx, 0Ah
0x180015145  jmp     loc_18001530E
0x18001514a  call    cs:__imp_GetLastError
0x180015150  mov     ebx, eax
0x180015152  test    eax, eax
0x180015154  jle     short loc_18001515F
0x180015156  movzx   ebx, ax
0x180015159  or      ebx, 80070000h
0x18001515f  test    ebx, ebx
0x180015161  jns     short loc_180015171
0x180015163  mov     edx, ebx; int
0x180015165  lea     rcx, qword_18006A9C0; this
0x18001516c  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015171  lea     rax, WPP_GLOBAL_Control
0x180015178  mov     rcx, cs:WPP_GLOBAL_Control
0x18001517f  cmp     rcx, rax
0x180015182  jz      loc_1800150E8
0x180015188  test    byte ptr [rcx+1Ch], 1
0x18001518c  jz      loc_1800150E8
0x180015192  cmp     byte ptr [rcx+19h], 2
0x180015196  jb      loc_1800150E8
0x18001519c  mov     edx, 0Ch
0x1800151a1  jmp     loc_18001530E
0x1800151a6  call    cs:__imp_GetLastError
0x1800151ac  mov     ebx, eax
0x1800151ae  test    eax, eax
0x1800151b0  jle     short loc_1800151BB
0x1800151b2  movzx   ebx, ax
0x1800151b5  or      ebx, 80070000h
0x1800151bb  test    ebx, ebx
0x1800151bd  jns     short loc_1800151CD
0x1800151bf  mov     edx, ebx; int
0x1800151c1  lea     rcx, qword_18006A9C0; this
0x1800151c8  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800151cd  lea     rax, WPP_GLOBAL_Control
0x1800151d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151db  cmp     rcx, rax
0x1800151de  jz      loc_1800150E8
0x1800151e4  test    byte ptr [rcx+1Ch], 1
0x1800151e8  jz      loc_1800150E8
0x1800151ee  cmp     byte ptr [rcx+19h], 2
0x1800151f2  jb      loc_1800150E8
0x1800151f8  mov     edx, 0Dh
0x1800151fd  jmp     loc_18001530E
0x180015202  call    cs:__imp_GetLastError
0x180015208  mov     ebx, eax
0x18001520a  test    eax, eax
0x18001520c  jle     short loc_180015217
0x18001520e  movzx   ebx, ax
0x180015211  or      ebx, 80070000h
0x180015217  test    ebx, ebx
0x180015219  jns     short loc_180015229
0x18001521b  mov     edx, ebx; int
0x18001521d  lea     rcx, qword_18006A9C0; this
0x180015224  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015229  lea     rax, WPP_GLOBAL_Control
0x180015230  mov     rcx, cs:WPP_GLOBAL_Control
0x180015237  cmp     rcx, rax
0x18001523a  jz      loc_1800150E8
0x180015240  test    byte ptr [rcx+1Ch], 1
0x180015244  jz      loc_1800150E8
0x18001524a  cmp     byte ptr [rcx+19h], 2
0x18001524e  jb      loc_1800150E8
0x180015254  mov     edx, 0Eh
0x180015259  jmp     loc_18001530E
0x18001525e  call    cs:__imp_GetLastError
0x180015264  mov     ebx, eax
0x180015266  test    eax, eax
0x180015268  jle     short loc_180015273
0x18001526a  movzx   ebx, ax
0x18001526d  or      ebx, 80070000h
0x180015273  test    ebx, ebx
0x180015275  jns     short loc_180015285
0x180015277  mov     edx, ebx; int
0x180015279  lea     rcx, qword_18006A9C0; this
0x180015280  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015285  lea     rax, WPP_GLOBAL_Control
0x18001528c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015293  cmp     rcx, rax
0x180015296  jz      loc_1800150E8
0x18001529c  test    byte ptr [rcx+1Ch], 1
0x1800152a0  jz      loc_1800150E8
0x1800152a6  cmp     byte ptr [rcx+19h], 2
0x1800152aa  jb      loc_1800150E8
0x1800152b0  mov     edx, 0Fh
0x1800152b5  jmp     short loc_18001530E
0x1800152b7  call    cs:__imp_GetLastError
0x1800152bd  mov     ebx, eax
0x1800152bf  test    eax, eax
0x1800152c1  jle     short loc_1800152CC
0x1800152c3  movzx   ebx, ax
0x1800152c6  or      ebx, 80070000h
0x1800152cc  test    ebx, ebx
0x1800152ce  jns     short loc_1800152DE
0x1800152d0  mov     edx, ebx; int
0x1800152d2  lea     rcx, qword_18006A9C0; this
0x1800152d9  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800152de  lea     rax, WPP_GLOBAL_Control
0x1800152e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152ec  cmp     rcx, rax
0x1800152ef  jz      loc_1800150E8
0x1800152f5  test    byte ptr [rcx+1Ch], 1
0x1800152f9  jz      loc_1800150E8
0x1800152ff  cmp     byte ptr [rcx+19h], 2
0x180015303  jb      loc_1800150E8
0x180015309  mov     edx, 10h
0x18001530e  mov     r9d, ebx
0x180015311  lea     r8, WPP_6f99fdf990383d18e8dfd3c8d83499a1_Traceguids
0x180015318  mov     rcx, [rcx+10h]
0x18001531c  call    WPP_SF_D
0x180015321  jmp     loc_1800150E8
0x180015326  mov     edx, ebx; int
0x180015328  lea     rcx, qword_18006A9C0; this
0x18001532f  call    ?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180015334  jmp     loc_1800150D1
0x180015339  test    byte ptr [rcx+1Ch], 1
0x18001533d  jz      loc_1800150E8
0x180015343  cmp     byte ptr [rcx+19h], 2
0x180015347  jb      loc_1800150E8
0x18001534d  mov     edx, 0Bh
0x180015352  jmp     short loc_18001530E
```

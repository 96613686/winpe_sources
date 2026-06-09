# CStorage::Open(ushort const *,ushort const *,ulong)

- ea: `0x18001700c`
- end: `0x1800174b9`
- name: `?Open@CStorage@@IEAAHPEBG0K@Z`
- size: `1197`
- prototype: `__int64 __fastcall(CStorage *__hidden this, const unsigned __int16 *Src, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800174c0`

## callees

- `0x180002250`
- `0x18000ffa4`
- `0x1800114e4`
- `0x180012044`
- `0x18001524c`
- `0x1800158b0`
- `0x18001700c`
- `0x18001dc70`
- `0x1800274c6`
- `0x18002a010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180017370`
- `msvcrt!wcsrchr` at `0x180017370`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001747f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028f58`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001747f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180028f58`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001709c`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18001709c`

## string_xrefs

- `0x1800171a6`: `CStorage::Open`
- `0x180017287`: `CStorage::Open`
- `0x18001717b`: `CStorage::Open: CConsistentMappingFactory::CreateObject failed.`
- `0x18001725c`: `CStorage::Open: m_pMapping->Create(%s) failed.`

## pseudocode

```c
__int64 __fastcall CStorage::Open(CStorage *this, const char *Src, const unsigned __int16 *a3, int a4)
{
  __int64 result; // rax
  unsigned int v7; // r12d
  const unsigned __int16 *v8; // r14
  int v9; // r13d
  BOOL v10; // edi
  int v11; // ebx
  HANDLE MutexW; // rax
  __int64 v13; // rcx
  struct CConsistentMapping *Object; // rax
  int v15; // ebx
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  __int64 v19; // rax
  wchar_t *v20; // rax
  size_t v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  unsigned __int16 *v24; // rax
  __int64 v25; // rbx
  __int64 v26; // rax
  int v27; // [rsp+60h] [rbp-48h]
  int v28; // [rsp+68h] [rbp-40h]
  _BYTE v29[12]; // [rsp+6Ch] [rbp-3Ch] BYREF
  unsigned __int16 *v30; // [rsp+78h] [rbp-30h]
  LPCWSTR lpModuleName; // [rsp+A8h] [rbp+0h]
  int v32; // [rsp+B8h] [rbp+10h] BYREF

  result = 0;
  if ( !Src || *(_QWORD *)this || *((_DWORD *)this + 29) )
    return result;
  v7 = 0;
  v27 = 1;
  v8 = 0;
  v30 = 0;
  *(_DWORD *)&v29[8] = 0;
  v9 = a4 & 2;
  *(_QWORD *)v29 = (a4 & 1) == 0;
  v28 = a4 & 8;
  v10 = (a4 & 0x10000) == 0;
  v11 = a4 & 0x20000;
  MutexW = CreateMutexW(0, 1, a3);
  *(_QWORD *)this = MutexW;
  if ( MutexW )
  {
    if ( (**(unsigned int (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32) == 183 )
    {
      v27 = 0;
      (*(void (__fastcall **)(struct IKernel32Interface *, _QWORD, __int64))(*(_QWORD *)g_Kernel32 + 416LL))(
        g_Kernel32,
        *(_QWORD *)this,
        0xFFFFFFFFLL);
    }
    if ( !v28
      || !v9
      && (*(unsigned int (__fastcall **)(struct IKernel32Interface *, const char *))(*(_QWORD *)g_Kernel32 + 288LL))(
           g_Kernel32,
           Src) != -1 )
    {
      v13 = *((_QWORD *)this + 8);
      if ( v13 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 1);
      Object = CConsistentMappingFactory::CreateObject(v9);
      *((_QWORD *)this + 8) = Object;
      if ( !Object )
      {
        if ( g_bEnableDiagnosticMode )
        {
          v15 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
          v16 = (unsigned int)ConstructPartialMsgW(
                                0x6B000000u,
                                "CStorage::Open: CConsistentMappingFactory::CreateObject failed.");
          WdsSetupLogMessageW(
            v16,
            589824,
            (int)L"D",
            0,
            4413,
            L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
            (__int64)L"CStorage::Open",
            lpModuleName,
            v15,
            0,
            0);
        }
        goto LABEL_33;
      }
      v32 = 0;
      if ( !(*(unsigned int (__fastcall **)(struct CConsistentMapping *, const char *, char *, BOOL, int, _DWORD, __int64, int *, _DWORD))(*(_QWORD *)Object + 32LL))(
              Object,
              Src,
              (char *)this + 56,
              v10,
              v11,
              *(_DWORD *)v29,
              5,
              &v32,
              0) )
      {
        if ( g_bEnableDiagnosticMode )
        {
          v17 = (**(__int64 (__fastcall ***)(struct IKernel32Interface *))g_Kernel32)(g_Kernel32);
          v18 = (unsigned int)ConstructPartialMsgW(0x6B000000u, "CStorage::Open: m_pMapping->Create(%s) failed.", Src);
          WdsSetupLogMessageW(
            v18,
            589824,
            (int)L"D",
            0,
            4430,
            L"onecore\\base\\ntsetup\\panther\\engine\\bb.cpp",
            (__int64)L"CStorage::Open",
            lpModuleName,
            v17,
            0,
            0);
        }
        goto LABEL_33;
      }
      *((_DWORD *)this + 11) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
      *((_DWORD *)this + 12) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 96LL))(*((_QWORD *)this + 8));
      if ( v32 )
      {
        v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _BYTE *))(**((_QWORD **)this + 8) + 16LL))(
                *((_QWORD *)this + 8),
                0,
                256,
                &v29[4]);
        if ( !v19 )
          goto LABEL_33;
        *(_QWORD *)v19 = 1;
        *(_DWORD *)(v19 + 8) = 0;
        *(_DWORD *)(v19 + 12) = 256;
        *(_QWORD *)(v19 + 16) = 4;
        if ( !(unsigned int)CMemoryManager::InitializeMemMapsAsForNewFile(*((struct CConsistentMapping **)this + 8))
          || !(*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 8) + 24LL))(
                *((_QWORD *)this + 8),
                *(_QWORD *)&v29[4]) )
        {
          goto LABEL_33;
        }
        *(_QWORD *)&v29[4] = 0;
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 40LL))(*((_QWORD *)this + 8));
      }
      v20 = wcsrchr((const wchar_t *)Src, 0x5Cu);
      if ( !v20 )
      {
        v8 = 0;
        v30 = 0;
        goto LABEL_28;
      }
      v21 = (char *)v20 - Src + 4;
      v22 = *(_QWORD *)g_Kernel32;
      v23 = (*(__int64 (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 56LL))(g_Kernel32);
      v24 = (unsigned __int16 *)(*(__int64 (__fastcall **)(struct IKernel32Interface *, __int64, __int64, size_t))(v22 + 80))(
                                  g_Kernel32,
                                  v23,
                                  8,
                                  v21);
      v8 = v24;
      v30 = v24;
      if ( v24 )
      {
        memcpy_0(v24, Src, v21);
        v8[(v21 >> 1) - 1] = 0;
LABEL_28:
        if ( (unsigned int)CMemoryManager::Init(
                             (CStorage *)((char *)this + 72),
                             (CStorage *)((char *)this + 56),
                             v8,
                             *((struct CConsistentMapping **)this + 8),
                             v9)
          && (v32 || !v27 || (unsigned int)CStorage::CheckAndRestoreIntegrity(this)) )
        {
          v7 = 1;
        }
      }
    }
  }
LABEL_33:
  if ( *(_QWORD *)&v29[4] )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 24LL))(*((_QWORD *)this + 8));
  if ( v8 )
  {
    v25 = *(_QWORD *)g_Kernel32;
    v26 = (*(__int64 (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 56LL))(g_Kernel32);
    (*(void (__fastcall **)(struct IKernel32Interface *, __int64, _QWORD, const unsigned __int16 *))(v25 + 96))(
      g_Kernel32,
      v26,
      0,
      v8);
  }
  if ( *(_QWORD *)this )
    ReleaseMutex(*(HANDLE *)this);
  if ( !v7 )
    CStorage::DestroyObject(this);
  return v7;
}

```

## disassembly

```asm
0x18001700c  mov     r11, rsp
0x18001700f  mov     [r11+18h], rbx
0x180017013  mov     [r11+20h], rsi
0x180017017  mov     [r11+8], rcx
0x18001701b  push    rdi
0x18001701c  push    r12
0x18001701e  push    r13
0x180017020  push    r14
0x180017022  push    r15
0x180017024  sub     rsp, 80h
0x18001702b  mov     ebx, r9d
0x18001702e  mov     r15, rdx
0x180017031  mov     rsi, rcx
0x180017034  xor     eax, eax
0x180017036  test    rdx, rdx
0x180017039  jz      loc_18001749B
0x18001703f  cmp     [rcx], rax
0x180017042  jnz     loc_18001749B
0x180017048  cmp     [rcx+74h], eax
0x18001704b  jnz     loc_18001749B
0x180017051  mov     r12d, eax
0x180017054  mov     [rsp+0A8h+var_44], eax
0x180017058  mov     [rsp+0A8h+var_48], 1
0x180017060  mov     r14d, eax
0x180017063  mov     [r11-30h], rax
0x180017067  mov     [r11-38h], rax
0x18001706b  mov     r13d, ebx
0x18001706e  and     r13d, 2
0x180017072  mov     eax, ebx
0x180017074  not     eax
0x180017076  and     eax, 1
0x180017079  mov     [rsp+0A8h+var_3C], eax
0x18001707d  mov     eax, ebx
0x18001707f  and     eax, 8
0x180017082  mov     [rsp+0A8h+var_40], eax
0x180017086  mov     edi, ebx
0x180017088  shr     edi, 10h
0x18001708b  not     edi
0x18001708d  and     edi, 1
0x180017090  and     ebx, 20000h
0x180017096  lea     edx, [r14+1]; bInitialOwner
0x18001709a  xor     ecx, ecx; lpMutexAttributes
0x18001709c  call    cs:__imp_CreateMutexW
0x1800170a3  nop     dword ptr [rax+rax+00h]
0x1800170a8  mov     [rsi], rax
0x1800170ab  test    rax, rax
0x1800170ae  jz      loc_18001742C
0x1800170b4  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800170bb  mov     rax, [rcx]
0x1800170be  mov     rax, [rax]
0x1800170c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170c6  cmp     eax, 0B7h
0x1800170cb  jnz     short loc_1800170EF
0x1800170cd  mov     [rsp+0A8h+var_48], r14d
0x1800170d2  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800170d9  mov     rax, [rcx]
0x1800170dc  or      r8d, 0FFFFFFFFh
0x1800170e0  mov     rdx, [rsi]
0x1800170e3  mov     rax, [rax+1A0h]
0x1800170ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170ef  cmp     [rsp+0A8h+var_40], 0
0x1800170f4  jz      short loc_180017121
0x1800170f6  test    r13d, r13d
0x1800170f9  jnz     loc_18001742C
0x1800170ff  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017106  mov     rax, [rcx]
0x180017109  mov     rdx, r15
0x18001710c  mov     rax, [rax+120h]
0x180017113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017118  cmp     eax, 0FFFFFFFFh
0x18001711b  jz      loc_18001742C
0x180017121  mov     rcx, [rsi+40h]
0x180017125  test    rcx, rcx
0x180017128  jz      short loc_18001713B
0x18001712a  mov     rax, [rcx]
0x18001712d  mov     edx, 1
0x180017132  mov     rax, [rax+8]
0x180017136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001713b  mov     ecx, r13d; int
0x18001713e  call    ?CreateObject@CConsistentMappingFactory@@SAPEAVCConsistentMapping@@H@Z; CConsistentMappingFactory::CreateObject(int)
0x180017143  mov     rcx, rax
0x180017146  mov     [rsi+40h], rax
0x18001714a  test    rax, rax
0x18001714d  jnz     loc_1800171E2
0x180017153  cmp     cs:?g_bEnableDiagnosticMode@@3HA, eax; int g_bEnableDiagnosticMode
0x180017159  jz      loc_18001742C
0x18001715f  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017166  mov     rax, [rcx]
0x180017169  mov     rax, [rax]
0x18001716c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017171  mov     ebx, eax
0x180017173  mov     rdi, [rsp+0A8h]
0x18001717b  lea     rdx, aCstorageOpenCc; "CStorage::Open: CConsistentMappingFacto"...
0x180017182  mov     ecx, 6B000000h; unsigned int
0x180017187  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001718c  mov     [rsp+0A8h+var_58], 0; int
0x180017194  mov     [rsp+0A8h+var_60], 0; __int64
0x18001719d  mov     [rsp+0A8h+var_68], ebx; int
0x1800171a1  mov     [rsp+0A8h+lpModuleName], rdi; lpModuleName
0x1800171a6  lea     rcx, aCstorageOpen; "CStorage::Open"
0x1800171ad  mov     [rsp+0A8h+var_78], rcx; __int64
0x1800171b2  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x1800171b9  mov     [rsp+0A8h+var_80], rcx; unsigned __int16 *
0x1800171be  mov     [rsp+0A8h+var_88], 113Dh; int
0x1800171c6  xor     r9d, r9d; int
0x1800171c9  lea     r8, aD_1; "D"
0x1800171d0  mov     edx, 90000h; int
0x1800171d5  mov     rcx, rax; int
0x1800171d8  call    WdsSetupLogMessageW
0x1800171dd  jmp     loc_18001742C
0x1800171e2  mov     [rsp+0A8h+arg_8], 0
0x1800171ed  lea     r8, [rsi+38h]
0x1800171f1  mov     rax, [rax]
0x1800171f4  mov     [rsp+0A8h+var_68], 0
0x1800171fc  lea     rdx, [rsp+0A8h+arg_8]
0x180017204  mov     [rsp+0A8h+lpModuleName], rdx
0x180017209  mov     [rsp+0A8h+var_78], 5
0x180017212  mov     edx, [rsp+0A8h+var_3C]
0x180017216  mov     dword ptr [rsp+0A8h+var_80], edx
0x18001721a  mov     [rsp+0A8h+var_88], ebx
0x18001721e  mov     r9d, edi
0x180017221  mov     rdx, r15
0x180017224  mov     rax, [rax+20h]
0x180017228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001722d  test    eax, eax
0x18001722f  jnz     short loc_1800172AC
0x180017231  cmp     cs:?g_bEnableDiagnosticMode@@3HA, eax; int g_bEnableDiagnosticMode
0x180017237  jz      loc_18001742C
0x18001723d  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017244  mov     rax, [rcx]
0x180017247  mov     rax, [rax]
0x18001724a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001724f  mov     ebx, eax
0x180017251  mov     rdi, [rsp+0A8h]
0x180017259  mov     r8, r15
0x18001725c  lea     rdx, aCstorageOpenMP; "CStorage::Open: m_pMapping->Create(%s) "...
0x180017263  mov     ecx, 6B000000h; unsigned int
0x180017268  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001726d  mov     [rsp+0A8h+var_58], 0
0x180017275  mov     [rsp+0A8h+var_60], 0
0x18001727e  mov     [rsp+0A8h+var_68], ebx
0x180017282  mov     [rsp+0A8h+lpModuleName], rdi
0x180017287  lea     rcx, aCstorageOpen; "CStorage::Open"
0x18001728e  mov     [rsp+0A8h+var_78], rcx
0x180017293  lea     rcx, aOnecoreBaseNts_0; "onecore\\base\\ntsetup\\panther\\engine"...
0x18001729a  mov     [rsp+0A8h+var_80], rcx
0x18001729f  mov     [rsp+0A8h+var_88], 114Eh
0x1800172a7  jmp     loc_1800171C6
0x1800172ac  mov     rcx, [rsi+40h]
0x1800172b0  mov     rax, [rcx]
0x1800172b3  mov     rax, [rax+58h]
0x1800172b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172bc  mov     [rsi+2Ch], eax
0x1800172bf  mov     rcx, [rsi+40h]
0x1800172c3  mov     rax, [rcx]
0x1800172c6  mov     rax, [rax+60h]
0x1800172ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172cf  mov     [rsi+30h], eax
0x1800172d2  cmp     [rsp+0A8h+arg_8], 0
0x1800172da  jz      loc_180017368
0x1800172e0  mov     rcx, [rsi+40h]
0x1800172e4  mov     rax, [rcx]
0x1800172e7  lea     r9, [rsp+0A8h+var_38]
0x1800172ec  mov     ebx, 100h
0x1800172f1  mov     r8d, ebx
0x1800172f4  xor     edx, edx
0x1800172f6  mov     rax, [rax+10h]
0x1800172fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ff  test    rax, rax
0x180017302  jz      loc_18001742C
0x180017308  mov     qword ptr [rax], 1
0x18001730f  mov     dword ptr [rax+8], 0
0x180017316  mov     [rax+0Ch], ebx
0x180017319  mov     qword ptr [rax+10h], 4
0x180017321  mov     rcx, [rsi+40h]; struct CConsistentMapping *
0x180017325  call    ?InitializeMemMapsAsForNewFile@CMemoryManager@@SAHPEAVCConsistentMapping@@@Z; CMemoryManager::InitializeMemMapsAsForNewFile(CConsistentMapping *)
0x18001732a  test    eax, eax
0x18001732c  jz      loc_18001742C
0x180017332  mov     rcx, [rsi+40h]
0x180017336  mov     rax, [rcx]
0x180017339  mov     rdx, [rsp+0A8h+var_38]
0x18001733e  mov     rax, [rax+18h]
0x180017342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017347  test    eax, eax
0x180017349  jz      loc_18001742C
0x18001734f  mov     [rsp+0A8h+var_38], 0
0x180017358  mov     rcx, [rsi+40h]
0x18001735c  mov     rax, [rcx]
0x18001735f  mov     rax, [rax+28h]
0x180017363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017368  mov     edx, 5Ch ; '\'; Ch
0x18001736d  mov     rcx, r15; Str
0x180017370  call    cs:__imp_wcsrchr
0x180017377  nop     dword ptr [rax+rax+00h]
0x18001737c  test    rax, rax
0x18001737f  jz      short loc_1800173DF
0x180017381  sub     rax, r15
0x180017384  lea     rdi, [rax+4]
0x180017388  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18001738f  mov     rbx, [rcx]
0x180017392  mov     rax, [rbx+38h]
0x180017396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001739b  mov     r9, rdi
0x18001739e  mov     r8d, 8
0x1800173a4  mov     rdx, rax
0x1800173a7  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x1800173ae  mov     rax, [rbx+50h]
0x1800173b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173b7  mov     r14, rax
0x1800173ba  mov     [rsp+0A8h+var_30], rax
0x1800173bf  test    rax, rax
0x1800173c2  jz      short loc_18001742C
0x1800173c4  mov     r8, rdi; Size
0x1800173c7  mov     rdx, r15; Src
0x1800173ca  mov     rcx, rax; void *
0x1800173cd  call    memcpy_0
0x1800173d2  shr     rdi, 1
0x1800173d5  xor     eax, eax
0x1800173d7  mov     [r14+rdi*2-2], ax
0x1800173dd  jmp     short loc_1800173E7
0x1800173df  xor     r14d, r14d
0x1800173e2  mov     [rsp+0A8h+var_30], r14
0x1800173e7  lea     rcx, [rsi+48h]; this
0x1800173eb  mov     [rsp+0A8h+var_88], r13d; int
0x1800173f0  mov     r9, [rsi+40h]; struct CConsistentMapping *
0x1800173f4  mov     r8, r14; unsigned __int16 *
0x1800173f7  lea     rdx, [rsi+38h]; struct CObjectName *
0x1800173fb  call    ?Init@CMemoryManager@@QEAAHAEAVCObjectName@@PEBGPEAVCConsistentMapping@@H@Z; CMemoryManager::Init(CObjectName &,ushort const *,CConsistentMapping *,int)
0x180017400  test    eax, eax
0x180017402  jz      short loc_18001742C
0x180017404  cmp     [rsp+0A8h+arg_8], 0
0x18001740c  jnz     short loc_180017421
0x18001740e  cmp     [rsp+0A8h+var_48], 0
0x180017413  jz      short loc_180017421
0x180017415  mov     rcx, rsi; this
0x180017418  call    ?CheckAndRestoreIntegrity@CStorage@@IEAAHXZ; CStorage::CheckAndRestoreIntegrity(void)
0x18001741d  test    eax, eax
0x18001741f  jz      short loc_18001742C
0x180017421  mov     r12d, 1
0x180017427  mov     [rsp+0A8h+var_44], r12d
0x18001742c  mov     rdx, [rsp+0A8h+var_38]
0x180017431  test    rdx, rdx
0x180017434  jz      short loc_180017446
0x180017436  mov     rcx, [rsi+40h]
0x18001743a  mov     rax, [rcx]
0x18001743d  mov     rax, [rax+18h]
0x180017441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017446  test    r14, r14
0x180017449  jz      short loc_180017477
0x18001744b  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180017452  mov     rbx, [rcx]
0x180017455  mov     rax, [rbx+38h]
0x180017459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001745e  mov     r9, r14
0x180017461  xor     r8d, r8d
0x180017464  mov     rdx, rax
0x180017467  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x18001746e  mov     rax, [rbx+60h]
0x180017472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017477  mov     rcx, [rsi]; hMutex
0x18001747a  test    rcx, rcx
0x18001747d  jz      short loc_18001748B
0x18001747f  call    cs:__imp_ReleaseMutex
0x180017486  nop     dword ptr [rax+rax+00h]
0x18001748b  test    r12d, r12d
0x18001748e  jnz     short loc_180017498
0x180017490  mov     rcx, rsi; this
0x180017493  call    ?DestroyObject@CStorage@@IEAAXXZ; CStorage::DestroyObject(void)
0x180017498  mov     eax, r12d
0x18001749b  lea     r11, [rsp+0A8h+var_28]
0x1800174a3  mov     rbx, [r11+40h]
0x1800174a7  mov     rsi, [r11+48h]
0x1800174ab  mov     rsp, r11
0x1800174ae  pop     r15
0x1800174b0  pop     r14
0x1800174b2  pop     r13
0x1800174b4  pop     r12
0x1800174b6  pop     rdi
0x1800174b7  retn
0x180028ee0  push    rbx
0x180028ee2  push    rbp
0x180028ee3  push    rdi
0x180028ee4  sub     rsp, 60h
0x180028ee8  mov     rbp, rdx
0x180028eeb  mov     rdx, [rbp+70h]
0x180028eef  test    rdx, rdx
0x180028ef2  jz      short loc_180028F0F
0x180028ef4  mov     rcx, [rbp+0B0h]
0x180028efb  mov     rax, [rcx+40h]
0x180028eff  mov     r8, [rax]
0x180028f02  mov     rcx, rax
0x180028f05  mov     rax, [r8+18h]
0x180028f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f0e  nop
0x180028f0f  mov     rdi, [rbp+78h]
0x180028f13  test    rdi, rdi
0x180028f16  jz      short loc_180028F48
0x180028f18  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180028f1f  mov     rax, [rcx]
0x180028f22  mov     rbx, [rax+60h]
  ... truncated ...
```

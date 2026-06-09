# CWdsProvider::Initialize(ushort const *,ushort const *,ushort const *,int,int,ulong,CPool<ProviderRequest> *)

- ea: `0x180010b44`
- end: `0x180010e87`
- name: `?Initialize@CWdsProvider@@QEAAKPEBG00HHKPEAV?$CPool@UProviderRequest@@@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(CWdsProvider *this, const unsigned __int16 *, const WCHAR *, const unsigned __int16 *, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012790`

## callees

- `0x180010b44`
- `0x180011104`
- `0x180011318`
- `0x1800113f4`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010c04`
- `KERNEL32!GetLastError` at `0x180010c3b`
- `KERNEL32!GetLastError` at `0x180010c04`
- `KERNEL32!GetLastError` at `0x180010c3b`
- `KERNEL32!LeaveCriticalSection` at `0x180010db8`
- `KERNEL32!LeaveCriticalSection` at `0x180010db8`
- `KERNEL32!EnterCriticalSection` at `0x180010b7f`
- `KERNEL32!EnterCriticalSection` at `0x180010b7f`
- `KERNEL32!GetProcAddress` at `0x180010ce7`
- `KERNEL32!GetProcAddress` at `0x180010ce7`
- `KERNEL32!LoadLibraryW` at `0x180010bdd`
- `KERNEL32!LoadLibraryW` at `0x180010bdd`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180010da3`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180010da3`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010c2f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010cb4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010d53`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010e2e`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010c2f`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010cb4`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010d53`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010e2e`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010d8d`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010e08`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010e5e`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010d8d`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010e08`
- `WdsServerCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x180010e5e`
- `WdsServerCommonLib!?WcsDup@@YAPEAGPEBG@Z` at `0x180010b8e`
- `WdsServerCommonLib!?WcsDup@@YAPEAGPEBG@Z` at `0x180010b8e`
- `WdsServerCommonLib!WdsGetFileVersion` at `0x180010c5e`
- `WdsServerCommonLib!WdsGetFileVersion` at `0x180010c5e`
- `WdsServerCommonLib!?ToAnsi@@YAKPEBGPEAPEAD@Z` at `0x180010cc8`
- `WdsServerCommonLib!?ToAnsi@@YAKPEBGPEAPEAD@Z` at `0x180010cc8`

## string_xrefs

- `0x180010c17`: `[%s] Failed to load provider DLL [%s], error %u`
- `0x180010c98`: `[%s] Loaded DLL [%s], version %u.%u.%u.%u`

## pseudocode

```c
__int64 __fastcall CWdsProvider::Initialize(
        CWdsProvider *this,
        const unsigned __int16 *a2,
        const WCHAR *a3,
        const unsigned __int16 *a4,
        int a5,
        int a6,
        int a7,
        __int64 a8)
{
  struct _RTL_CRITICAL_SECTION *v8; // r14
  unsigned __int16 *v13; // rax
  DWORD v14; // ebx
  HMODULE LibraryW; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  FARPROC ProcAddress; // rbx
  __int64 v19; // rdx
  __int64 v20; // r8
  unsigned int v21; // eax
  bool v22; // cf
  __int64 v24; // [rsp+20h] [rbp-58h]
  __int64 v25; // [rsp+28h] [rbp-50h]
  DWORD LastError; // [rsp+28h] [rbp-50h]
  __int64 v27; // [rsp+38h] [rbp-40h]
  __int64 v28; // [rsp+40h] [rbp-38h]
  unsigned int v29; // [rsp+50h] [rbp-28h] BYREF
  LPCSTR lpProcName; // [rsp+58h] [rbp-20h] BYREF
  unsigned int v31; // [rsp+80h] [rbp+8h] BYREF

  lpProcName = 0;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 200);
  v29 = 0;
  v31 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  v13 = WcsDup(a2);
  *((_QWORD *)this + 2) = v13;
  if ( !v13 )
  {
    v14 = 8;
    goto LABEL_15;
  }
  *((_QWORD *)this + 31) = a8;
  *((_DWORD *)this + 65) = a6;
  *((_DWORD *)this + 66) = a7;
  LibraryW = LoadLibraryW(a3);
  *((_QWORD *)this + 3) = LibraryW;
  if ( (unsigned int)ElValidateGleTrue_0(LibraryW == 0, v16, v17, 120) )
  {
    LastError = GetLastError();
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x80000u,
      L"[%s] Failed to load provider DLL [%s], error %u",
      a2,
      a3,
      LastError);
LABEL_5:
    v14 = GetLastError();
    goto LABEL_15;
  }
  if ( (int)WdsGetFileVersion(a3, &v29, &v31) >= 0 )
    CTrace::Trace(
      (CTrace *)qword_180039310,
      0x20000u,
      L"[%s] Loaded DLL [%s], version %u.%u.%u.%u",
      a2,
      a3,
      HIWORD(v29),
      (unsigned __int16)v29,
      HIWORD(v31),
      (unsigned __int16)v31);
  v14 = ToAnsi(a4, (char **)&lpProcName);
  if ( !v14 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 3), lpProcName);
    if ( (unsigned int)ElValidateGleTrue_0(ProcAddress == 0, v19, v20, 159) )
      goto LABEL_5;
    _InterlockedExchange((volatile __int32 *)this + 8, 1);
    v21 = ((__int64 (__fastcall *)(CWdsProvider *))ProcAddress)(this);
    v14 = ElValidateWin32_1(v21);
    if ( !v14 )
    {
      if ( *((_QWORD *)this + 5) && *((_QWORD *)this + 7) )
      {
        CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[%s] Provider Initialized.", a2);
        _InterlockedExchange((volatile __int32 *)this + 8, v14 + 2);
      }
      else
      {
        v14 = -1056898554;
        LODWORD(v25) = 1;
        CEventLog::Log((CEventLog *)qword_180039300, 0xC1010206, 2, 1, a2, v25, a3);
      }
    }
  }
LABEL_15:
  if ( lpProcName )
  {
    WdsPrivateHpFree((void *)lpProcName);
    lpProcName = 0;
  }
  LeaveCriticalSection(v8);
  if ( v14 )
  {
    v22 = a5 != 0;
    a5 = -a5;
    LODWORD(v28) = v14;
    LODWORD(v27) = 5;
    LODWORD(v25) = 1;
    CEventLog::Log((CEventLog *)qword_180039300, v22 ? -1056898559 : -2130640384, 3, 1, a2, v25, a3, v27, v28);
    LODWORD(v24) = v14;
    CTrace::Trace((CTrace *)qword_180039310, 0x80000u, L"[%s] Initialization Failed (rc=%u)", a2, v24);
    CWdsProvider::Shutdown(this);
  }
  else
  {
    LODWORD(v25) = 1;
    CEventLog::Log((CEventLog *)qword_180039300, 0x41010205u, 2, 1, a2, v25, a3);
  }
  return v14;
}

```

## disassembly

```asm
0x180010b44  mov     rax, rsp
0x180010b47  mov     [rax+10h], rbx
0x180010b4b  mov     [rax+18h], rbp
0x180010b4f  mov     [rax+20h], rsi
0x180010b53  push    rdi
0x180010b54  push    r12
0x180010b56  push    r14
0x180010b58  sub     rsp, 60h
0x180010b5c  and     qword ptr [rax-20h], 0
0x180010b61  lea     r14, [rcx+0C8h]
0x180010b68  and     dword ptr [rax-28h], 0
0x180010b6c  mov     rdi, rcx
0x180010b6f  and     dword ptr [rax+8], 0
0x180010b73  mov     rcx, r14; lpCriticalSection
0x180010b76  mov     rbx, r9
0x180010b79  mov     rbp, r8
0x180010b7c  mov     rsi, rdx
0x180010b7f  call    cs:__imp_EnterCriticalSection
0x180010b86  nop     dword ptr [rax+rax+00h]
0x180010b8b  mov     rcx, rsi
0x180010b8e  call    cs:__imp_?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x180010b95  nop     dword ptr [rax+rax+00h]
0x180010b9a  mov     [rdi+10h], rax
0x180010b9e  mov     r12d, 1
0x180010ba4  test    rax, rax
0x180010ba7  jnz     short loc_180010BB1
0x180010ba9  lea     ebx, [rax+8]
0x180010bac  jmp     loc_180010D99
0x180010bb1  mov     rax, [rsp+78h+arg_38]
0x180010bb9  mov     rcx, rbp; lpLibFileName
0x180010bbc  mov     [rdi+0F8h], rax
0x180010bc3  mov     eax, [rsp+78h+arg_28]
0x180010bca  mov     [rdi+104h], eax
0x180010bd0  mov     eax, [rsp+78h+arg_30]
0x180010bd7  mov     [rdi+108h], eax
0x180010bdd  call    cs:__imp_LoadLibraryW
0x180010be4  nop     dword ptr [rax+rax+00h]
0x180010be9  xor     ecx, ecx
0x180010beb  mov     r9d, 78h ; 'x'
0x180010bf1  test    rax, rax
0x180010bf4  mov     [rdi+18h], rax
0x180010bf8  setz    cl
0x180010bfb  call    ElValidateGleTrue_0
0x180010c00  test    eax, eax
0x180010c02  jz      short loc_180010C4E
0x180010c04  call    cs:__imp_GetLastError
0x180010c0b  nop     dword ptr [rax+rax+00h]
0x180010c10  mov     dword ptr [rsp+78h+var_50], eax
0x180010c14  mov     r9, rsi
0x180010c17  lea     r8, aSFailedToLoadP; "[%s] Failed to load provider DLL [%s], "...
0x180010c1e  mov     [rsp+78h+var_58], rbp
0x180010c23  mov     edx, 80000h
0x180010c28  lea     rcx, qword_180039310
0x180010c2f  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010c36  nop     dword ptr [rax+rax+00h]
0x180010c3b  call    cs:__imp_GetLastError
0x180010c42  nop     dword ptr [rax+rax+00h]
0x180010c47  mov     ebx, eax
0x180010c49  jmp     loc_180010D99
0x180010c4e  lea     r8, [rsp+78h+arg_0]
0x180010c56  mov     rcx, rbp
0x180010c59  lea     rdx, [rsp+78h+var_28]
0x180010c5e  call    cs:__imp_WdsGetFileVersion
0x180010c65  nop     dword ptr [rax+rax+00h]
0x180010c6a  test    eax, eax
0x180010c6c  js      short loc_180010CC0
0x180010c6e  mov     r8d, [rsp+78h+arg_0]
0x180010c76  mov     r9, rsi
0x180010c79  mov     edx, [rsp+78h+var_28]
0x180010c7d  movzx   ecx, r8w
0x180010c81  mov     [rsp+78h+var_38], ecx
0x180010c85  lea     rcx, qword_180039310
0x180010c8c  movzx   eax, dx
0x180010c8f  shr     r8d, 10h
0x180010c93  mov     dword ptr [rsp+78h+var_40], r8d
0x180010c98  lea     r8, aSLoadedDllSVer; "[%s] Loaded DLL [%s], version %u.%u.%u."...
0x180010c9f  shr     edx, 10h
0x180010ca2  mov     dword ptr [rsp+78h+var_48], eax
0x180010ca6  mov     dword ptr [rsp+78h+var_50], edx
0x180010caa  mov     edx, 20000h
0x180010caf  mov     [rsp+78h+var_58], rbp
0x180010cb4  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010cbb  nop     dword ptr [rax+rax+00h]
0x180010cc0  lea     rdx, [rsp+78h+lpProcName]
0x180010cc5  mov     rcx, rbx
0x180010cc8  call    cs:__imp_?ToAnsi@@YAKPEBGPEAPEAD@Z; ToAnsi(ushort const *,char * *)
0x180010ccf  nop     dword ptr [rax+rax+00h]
0x180010cd4  mov     ebx, eax
0x180010cd6  test    eax, eax
0x180010cd8  jnz     loc_180010D99
0x180010cde  mov     rdx, [rsp+78h+lpProcName]; lpProcName
0x180010ce3  mov     rcx, [rdi+18h]; hModule
0x180010ce7  call    cs:__imp_GetProcAddress
0x180010cee  nop     dword ptr [rax+rax+00h]
0x180010cf3  xor     ecx, ecx
0x180010cf5  mov     r9d, 9Fh
0x180010cfb  test    rax, rax
0x180010cfe  mov     rbx, rax
0x180010d01  setz    cl
0x180010d04  call    ElValidateGleTrue_0
0x180010d09  test    eax, eax
0x180010d0b  jnz     loc_180010C3B
0x180010d11  mov     eax, r12d
0x180010d14  mov     rcx, rdi
0x180010d17  xchg    eax, [rdi+20h]
0x180010d1a  mov     rax, rbx
0x180010d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d22  mov     ecx, eax
0x180010d24  call    ElValidateWin32_1
0x180010d29  mov     ebx, eax
0x180010d2b  test    eax, eax
0x180010d2d  jnz     short loc_180010D99
0x180010d2f  cmp     qword ptr [rdi+28h], 0
0x180010d34  jz      short loc_180010D67
0x180010d36  cmp     qword ptr [rdi+38h], 0
0x180010d3b  jz      short loc_180010D67
0x180010d3d  mov     r9, rsi
0x180010d40  lea     r8, aSProviderIniti; "[%s] Provider Initialized."
0x180010d47  mov     edx, 20000h
0x180010d4c  lea     rcx, qword_180039310
0x180010d53  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010d5a  nop     dword ptr [rax+rax+00h]
0x180010d5f  lea     eax, [rbx+2]
0x180010d62  xchg    eax, [rdi+20h]
0x180010d65  jmp     short loc_180010D99
0x180010d67  mov     [rsp+78h+var_48], rbp
0x180010d6c  lea     rcx, qword_180039300
0x180010d73  mov     ebx, 0C1010206h
0x180010d78  mov     dword ptr [rsp+78h+var_50], r12d
0x180010d7d  mov     edx, ebx
0x180010d7f  mov     [rsp+78h+var_58], rsi
0x180010d84  mov     r9d, r12d
0x180010d87  mov     r8d, 2
0x180010d8d  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180010d94  nop     dword ptr [rax+rax+00h]
0x180010d99  mov     rcx, [rsp+78h+lpProcName]
0x180010d9e  test    rcx, rcx
0x180010da1  jz      short loc_180010DB5
0x180010da3  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180010daa  nop     dword ptr [rax+rax+00h]
0x180010daf  and     [rsp+78h+lpProcName], 0
0x180010db5  mov     rcx, r14; lpCriticalSection
0x180010db8  call    cs:__imp_LeaveCriticalSection
0x180010dbf  nop     dword ptr [rax+rax+00h]
0x180010dc4  lea     rcx, qword_180039300
0x180010dcb  mov     r9d, r12d
0x180010dce  test    ebx, ebx
0x180010dd0  jz      short loc_180010E44
0x180010dd2  neg     [rsp+78h+arg_20]
0x180010dd9  mov     r8d, 3
0x180010ddf  mov     [rsp+78h+var_38], ebx
0x180010de3  sbb     edx, edx
0x180010de5  mov     dword ptr [rsp+78h+var_40], 5
0x180010ded  and     edx, 40000001h
0x180010df3  mov     [rsp+78h+var_48], rbp
0x180010df8  add     edx, 81010200h
0x180010dfe  mov     dword ptr [rsp+78h+var_50], r12d
0x180010e03  mov     [rsp+78h+var_58], rsi
0x180010e08  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180010e0f  nop     dword ptr [rax+rax+00h]
0x180010e14  mov     r9, rsi
0x180010e17  mov     dword ptr [rsp+78h+var_58], ebx
0x180010e1b  lea     r8, aSInitializatio; "[%s] Initialization Failed (rc=%u)"
0x180010e22  mov     edx, 80000h
0x180010e27  lea     rcx, qword_180039310
0x180010e2e  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010e35  nop     dword ptr [rax+rax+00h]
0x180010e3a  mov     rcx, rdi; this
0x180010e3d  call    ?Shutdown@CWdsProvider@@QEAAKXZ; CWdsProvider::Shutdown(void)
0x180010e42  jmp     short loc_180010E6A
0x180010e44  mov     [rsp+78h+var_48], rbp
0x180010e49  mov     edx, 41010205h
0x180010e4e  mov     dword ptr [rsp+78h+var_50], r12d
0x180010e53  mov     r8d, 2
0x180010e59  mov     [rsp+78h+var_58], rsi
0x180010e5e  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x180010e65  nop     dword ptr [rax+rax+00h]
0x180010e6a  lea     r11, [rsp+78h+var_18]
0x180010e6f  mov     eax, ebx
0x180010e71  mov     rbx, [r11+28h]
0x180010e75  mov     rbp, [r11+30h]
0x180010e79  mov     rsi, [r11+38h]
0x180010e7d  mov     rsp, r11
0x180010e80  pop     r14
0x180010e82  pop     r12
0x180010e84  pop     rdi
0x180010e85  retn
```

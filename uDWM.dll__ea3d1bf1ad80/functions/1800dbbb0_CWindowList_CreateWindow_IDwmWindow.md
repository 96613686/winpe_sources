# CWindowList::CreateWindow(IDwmWindow *)

- ea: `0x1800dbbb0`
- end: `0x1800dbc9a`
- name: `?CreateWindow@CWindowList@@UEAAJPEAUIDwmWindow@@@Z`
- size: `234`
- prototype: `__int64 __fastcall(CWindowList *__hidden this, struct IDwmWindow *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18001f43c`
- `0x18004451c`
- `0x180044e30`
- `0x180083b4c`
- `0x1800dbbb0`
- `0x1800e05d4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dbbce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dbbce`

## string_xrefs

- `0x1800dbbf8`: `CWindowList::CreateWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWindowList::CreateWindow(CWindowList *this, struct IDwmWindow *a2)
{
  unsigned __int64 v3; // rcx
  CWindowData *v4; // rax
  CWindowData *v5; // rbx
  unsigned int v6; // edi
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+48h] [rbp+10h] BYREF
  CWindowData *v9; // [rsp+50h] [rbp+18h]

  v8 = &CDesktopManager::s_csDwmInstance;
  EnterCriticalSection(&CDesktopManager::s_csDwmInstance);
  if ( (*(__int64 (__fastcall **)(struct IDwmWindow *))(*(_QWORD *)a2 + 8LL))(a2) )
    AssertW(
      0,
      L"pwdData == nullptr",
      L"CWindowList::CreateWindow",
      L"clientcore\\windows\\dwm\\udwm\\windowlist.cpp",
      0x84Eu);
  v4 = (CWindowData *)CWindowData::operator new(v3);
  v9 = v4;
  if ( v4 )
    v5 = CWindowData::CWindowData(v4);
  else
    v5 = 0;
  if ( v5 )
  {
    v6 = 0;
    *((_QWORD *)v5 + 3) = a2;
    (**(void (__fastcall ***)(struct IDwmWindow *, CWindowData *))a2)(a2, v5);
    *((_QWORD *)v5 + 5) = (*(__int64 (__fastcall **)(struct IDwmWindow *))(*(_QWORD *)a2 + 24LL))(a2);
  }
  else
  {
    v6 = -2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024882, 0x851u, 0);
  }
  CGuard<CDwmCS>::~CGuard<CDwmCS>(&v8);
  return v6;
}

```

## disassembly

```asm
0x1800dbbb0  mov     [rsp+arg_0], rbx
0x1800dbbb5  mov     [rsp+arg_18], rsi
0x1800dbbba  push    rdi
0x1800dbbbb  sub     rsp, 30h
0x1800dbbbf  mov     rsi, rdx
0x1800dbbc2  lea     rcx, ?s_csDwmInstance@CDesktopManager@@2VCDwmCS@@A; lpCriticalSection
0x1800dbbc9  mov     [rsp+38h+arg_8], rcx
0x1800dbbce  call    cs:__imp_EnterCriticalSection
0x1800dbbd4  nop
0x1800dbbd5  mov     rax, [rsi]
0x1800dbbd8  mov     rcx, rsi
0x1800dbbdb  mov     rax, [rax+8]
0x1800dbbdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbbe4  test    rax, rax
0x1800dbbe7  jz      short loc_1800DBC0D
0x1800dbbe9  mov     [rsp+38h+var_18], 84Eh; unsigned int
0x1800dbbf1  lea     r9, aClientcoreWind_7; "clientcore\\windows\\dwm\\udwm\\windowl"...
0x1800dbbf8  lea     r8, aCwindowlistCre; "CWindowList::CreateWindow"
0x1800dbbff  lea     rdx, aPwddataNullptr; "pwdData == nullptr"
0x1800dbc06  xor     ecx, ecx; unsigned __int16 *
0x1800dbc08  call    ?AssertW@@YAXPEBG000K@Z; AssertW(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x1800dbc0d  call    ??2CWindowData@@SAPEAX_K@Z; CWindowData::operator new(unsigned __int64)
0x1800dbc12  mov     [rsp+38h+arg_10], rax
0x1800dbc17  test    rax, rax
0x1800dbc1a  jz      short loc_1800DBC29
0x1800dbc1c  mov     rcx, rax; this
0x1800dbc1f  call    ??0CWindowData@@QEAA@XZ; CWindowData::CWindowData(void)
0x1800dbc24  mov     rbx, rax
0x1800dbc27  jmp     short loc_1800DBC2B
0x1800dbc29  xor     ebx, ebx
0x1800dbc2b  test    rbx, rbx
0x1800dbc2e  jnz     short loc_1800DBC54
0x1800dbc30  mov     edi, 8007000Eh
0x1800dbc35  mov     [rsp+38h+var_10], rbx; void *
0x1800dbc3a  mov     [rsp+38h+var_18], 851h; unsigned int
0x1800dbc42  mov     r9d, edi; int
0x1800dbc45  xor     r8d, r8d; unsigned int
0x1800dbc48  xor     edx, edx; int *
0x1800dbc4a  lea     ecx, [rbx+14h]; unsigned int
0x1800dbc4d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800dbc52  jmp     short loc_1800DBC7E
0x1800dbc54  xor     edi, edi
0x1800dbc56  mov     [rbx+18h], rsi
0x1800dbc5a  mov     rax, [rsi]
0x1800dbc5d  mov     rdx, rbx
0x1800dbc60  mov     rcx, rsi
0x1800dbc63  mov     rax, [rax]
0x1800dbc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc6b  mov     rcx, [rsi]
0x1800dbc6e  mov     rax, [rcx+18h]
0x1800dbc72  mov     rcx, rsi
0x1800dbc75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dbc7a  mov     [rbx+28h], rax
0x1800dbc7e  lea     rcx, [rsp+38h+arg_8]
0x1800dbc83  call    ??1?$CGuard@VCDwmCS@@@@QEAA@XZ; CGuard<CDwmCS>::~CGuard<CDwmCS>(void)
0x1800dbc88  mov     eax, edi
0x1800dbc8a  mov     rbx, [rsp+38h+arg_0]
0x1800dbc8f  mov     rsi, [rsp+38h+arg_18]
0x1800dbc94  add     rsp, 30h
0x1800dbc98  pop     rdi
0x1800dbc99  retn
```

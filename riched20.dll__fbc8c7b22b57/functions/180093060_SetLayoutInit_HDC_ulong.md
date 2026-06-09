# SetLayoutInit(HDC__ *,ulong)

- ea: `0x180093060`
- end: `0x1800930f0`
- name: `?SetLayoutInit@@YAKPEAUHDC__@@K@Z`
- size: `144`
- prototype: `unsigned int __fastcall(HDC, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180093060`
- `0x180095010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x180093089`
- `KERNEL32!GetModuleHandleA` at `0x180093089`
- `KERNEL32!EnterCriticalSection` at `0x180093076`
- `KERNEL32!EnterCriticalSection` at `0x180093076`
- `KERNEL32!LeaveCriticalSection` at `0x1800930d6`
- `KERNEL32!LeaveCriticalSection` at `0x1800930d6`
- `KERNEL32!GetProcAddress` at `0x1800930a4`
- `KERNEL32!GetProcAddress` at `0x1800930a4`

## string_xrefs

- `0x180093082`: `GDI32.DLL`

## pseudocode

```c
__int64 __fastcall SetLayoutInit(HDC a1, unsigned int a2)
{
  HMODULE ModuleHandleA; // rax
  unsigned int (*ProcAddress)(HDC, unsigned int); // rax
  unsigned int v6; // ebx

  EnterCriticalSection(&g_CriticalSection);
  ModuleHandleA = GetModuleHandleA("GDI32.DLL");
  if ( !ModuleHandleA
    || (ProcAddress = (unsigned int (*)(HDC, unsigned int))GetProcAddress(ModuleHandleA, "SetLayout")) == 0 )
  {
    ProcAddress = (unsigned int (*)(HDC, unsigned int))CDisplay::GetYScroll;
  }
  CW32System::_pfnSetLayout = ProcAddress;
  v6 = ((__int64 (__fastcall *)(HDC, _QWORD))ProcAddress)(a1, a2);
  LeaveCriticalSection(&g_CriticalSection);
  return v6;
}

```

## disassembly

```asm
0x180093060  mov     [rsp+arg_0], rbx
0x180093065  push    rdi
0x180093066  sub     rsp, 20h
0x18009306a  mov     rdi, rcx
0x18009306d  mov     ebx, edx
0x18009306f  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180093076  call    cs:__imp_EnterCriticalSection
0x18009307d  nop     dword ptr [rax+rax+00h]
0x180093082  lea     rcx, aGdi32Dll_0; "GDI32.DLL"
0x180093089  call    cs:__imp_GetModuleHandleA
0x180093090  nop     dword ptr [rax+rax+00h]
0x180093095  test    rax, rax
0x180093098  jz      short loc_1800930B5
0x18009309a  lea     rdx, aSetlayout; "SetLayout"
0x1800930a1  mov     rcx, rax; hModule
0x1800930a4  call    cs:__imp_GetProcAddress
0x1800930ab  nop     dword ptr [rax+rax+00h]
0x1800930b0  test    rax, rax
0x1800930b3  jnz     short loc_1800930BC
0x1800930b5  lea     rax, ?GetYScroll@CDisplay@@UEBAJXZ; CDisplay::GetYScroll(void)
0x1800930bc  mov     edx, ebx
0x1800930be  mov     cs:?_pfnSetLayout@CW32System@@2P6AKPEAUHDC__@@K@ZEA, rax; ulong (*CW32System::_pfnSetLayout)(HDC__ *,ulong)
0x1800930c5  mov     rcx, rdi
0x1800930c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930cd  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800930d4  mov     ebx, eax
0x1800930d6  call    cs:__imp_LeaveCriticalSection
0x1800930dd  nop     dword ptr [rax+rax+00h]
0x1800930e2  mov     eax, ebx
0x1800930e4  mov     rbx, [rsp+28h+arg_0]
0x1800930e9  add     rsp, 20h
0x1800930ed  pop     rdi
0x1800930ee  retn
```

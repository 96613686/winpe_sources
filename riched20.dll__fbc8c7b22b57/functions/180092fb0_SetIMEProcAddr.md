# SetIMEProcAddr

- ea: `0x180092fb0`
- end: `0x180093051`
- name: `SetIMEProcAddr`
- size: `161`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800539fc`
- `0x180090db0`
- `0x180090e3c`
- `0x180090f7c`
- `0x180091008`
- `0x1800910b0`
- `0x180091158`
- `0x1800911e0`
- `0x180091270`
- `0x1800912f4`
- `0x180091384`
- `0x180091418`
- `0x180091498`
- `0x180091514`
- `0x180091590`
- `0x1800915fc`
- `0x180091678`
- `0x180091704`

## callees

- `0x1800921e8`
- `0x180092fb0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180092fce`
- `KERNEL32!EnterCriticalSection` at `0x180092fce`
- `KERNEL32!LeaveCriticalSection` at `0x180093045`
- `KERNEL32!GetProcAddress` at `0x180093020`
- `KERNEL32!GetProcAddress` at `0x180093020`

## string_xrefs

- `0x180093002`: `imm32.dll`

## pseudocode

```c
void __fastcall SetIMEProcAddr(FARPROC *a1, int a2, const CHAR *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // r8d
  HINSTANCE Library; // rax

  EnterCriticalSection(&g_CriticalSection);
  if ( !*a1 )
  {
    if ( a2 )
    {
      if ( a2 == 1 )
        hModule = (HMODULE)-1LL;
    }
    else
    {
      Library = qword_1800A7588;
      if ( qword_1800A7588
        || (Library = CW32System::LoadLibrary(L"imm32.dll", v6, v7), (qword_1800A7588 = Library) != 0) )
      {
        *a1 = GetProcAddress(Library, a3);
      }
    }
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x180092fb0  mov     [rsp+arg_0], rbx
0x180092fb5  mov     [rsp+arg_8], rsi
0x180092fba  push    rdi
0x180092fbb  sub     rsp, 20h
0x180092fbf  mov     rdi, rcx
0x180092fc2  mov     rsi, r8
0x180092fc5  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180092fcc  mov     ebx, edx
0x180092fce  call    cs:__imp_EnterCriticalSection
0x180092fd5  nop     dword ptr [rax+rax+00h]
0x180092fda  cmp     qword ptr [rdi], 0
0x180092fde  jnz     short loc_18009302F
0x180092fe0  test    ebx, ebx
0x180092fe2  jz      short loc_180092FF6
0x180092fe4  cmp     ebx, 1
0x180092fe7  jnz     short loc_18009302F
0x180092fe9  mov     cs:hModule, 0FFFFFFFFFFFFFFFFh
0x180092ff4  jmp     short loc_18009302F
0x180092ff6  mov     rax, cs:qword_1800A7588
0x180092ffd  test    rax, rax
0x180093000  jnz     short loc_18009301A
0x180093002  lea     rcx, aImm32Dll; "imm32.dll"
0x180093009  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x18009300e  mov     cs:qword_1800A7588, rax
0x180093015  test    rax, rax
0x180093018  jz      short loc_18009302F
0x18009301a  mov     rdx, rsi; lpProcName
0x18009301d  mov     rcx, rax; hModule
0x180093020  call    cs:__imp_GetProcAddress
0x180093027  nop     dword ptr [rax+rax+00h]
0x18009302c  mov     [rdi], rax
0x18009302f  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x180093036  mov     rbx, [rsp+28h+arg_0]
0x18009303b  mov     rsi, [rsp+28h+arg_8]
0x180093040  add     rsp, 20h
0x180093044  pop     rdi
0x180093045  jmp     cs:__imp_LeaveCriticalSection
```

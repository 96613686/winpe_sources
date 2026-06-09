# SetProcAddr

- ea: `0x1800931b0`
- end: `0x1800932b6`
- name: `SetProcAddr`
- size: `262`
- prototype: ``
- caller_count: `48`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800269b4`
- `0x180041c68`
- `0x18004b3ac`
- `0x18004c338`
- `0x180054750`
- `0x180054a88`
- `0x1800551d0`
- `0x180057498`
- `0x18005c608`
- `0x18005d8d0`
- `0x180063ac4`
- `0x180063c40`
- `0x18006dbf0`
- `0x1800717bc`
- `0x180076438`
- `0x18007e71c`
- `0x18007ef54`
- `0x18007fbac`
- `0x18007fe50`
- `0x18008e9e0`
- `0x18008f6a8`
- `0x18008f76c`
- `0x18008fd88`
- `0x18008fe00`
- `0x180092088`
- `0x180092268`
- `0x18009253c`
- `0x1800925d4`
- `0x180092670`
- `0x18009270c`
- `0x180092768`
- `0x1800927b8`
- `0x180092814`
- `0x180092870`
- `0x1800928dc`
- `0x180092940`
- `0x18009299c`
- `0x1800929e0`
- `0x180092e64`
- `0x180092ed0`
- `0x180092f2c`
- `0x18009366c`
- `0x1800936bc`
- `0x18009370c`
- `0x180093758`
- `0x180093984`
- `0x1800939d0`
- `0x180093a3c`

## callees

- `0x1800921e8`
- `0x1800931b0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x1800931ce`
- `KERNEL32!EnterCriticalSection` at `0x1800931ce`
- `KERNEL32!LeaveCriticalSection` at `0x1800932aa`
- `KERNEL32!GetProcAddress` at `0x180093285`
- `KERNEL32!GetProcAddress` at `0x180093285`

## string_xrefs

- `0x18009326c`: `oleaut32.dll`
- `0x18009324b`: `ole32.dll`
- `0x18009322a`: `oleacc.dll`
- `0x180093209`: `user32.dll`

## pseudocode

```c
void __fastcall SetProcAddr(FARPROC *a1, int a2, const CHAR *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // r8d
  HMODULE v8; // rcx
  int v9; // ebx
  int v10; // ebx
  HINSTANCE Library; // rax

  EnterCriticalSection(&g_CriticalSection);
  if ( !*a1 )
  {
    v8 = 0;
    if ( a2 )
    {
      v9 = a2 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 != 1 )
            goto LABEL_15;
          v8 = (HMODULE)qword_1800A75C8;
          if ( qword_1800A75C8 )
            goto LABEL_15;
          Library = CW32System::LoadLibrary(L"user32.dll", v6, v7);
          qword_1800A75C8 = (__int64)Library;
          goto LABEL_14;
        }
        v8 = (HMODULE)qword_1800A7568;
        if ( !qword_1800A7568 )
        {
          Library = CW32System::LoadLibrary(L"oleacc.dll", v6, v7);
          qword_1800A7568 = (__int64)Library;
LABEL_14:
          v8 = Library;
        }
      }
      else
      {
        v8 = qword_1800A7558;
        if ( !qword_1800A7558 )
        {
          Library = CW32System::LoadLibrary(L"ole32.dll", v6, v7);
          qword_1800A7558 = Library;
          goto LABEL_14;
        }
      }
    }
    else
    {
      v8 = hLibModule;
      if ( !hLibModule )
      {
        Library = CW32System::LoadLibrary(L"oleaut32.dll", v6, v7);
        hLibModule = Library;
        goto LABEL_14;
      }
    }
LABEL_15:
    *a1 = GetProcAddress(v8, a3);
  }
  LeaveCriticalSection(&g_CriticalSection);
}

```

## disassembly

```asm
0x1800931b0  mov     [rsp+arg_0], rbx
0x1800931b5  mov     [rsp+arg_8], rsi
0x1800931ba  push    rdi
0x1800931bb  sub     rsp, 20h
0x1800931bf  mov     rdi, rcx
0x1800931c2  mov     rsi, r8
0x1800931c5  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800931cc  mov     ebx, edx
0x1800931ce  call    cs:__imp_EnterCriticalSection
0x1800931d5  nop     dword ptr [rax+rax+00h]
0x1800931da  cmp     qword ptr [rdi], 0
0x1800931de  jnz     loc_180093294
0x1800931e4  xor     ecx, ecx
0x1800931e6  test    ebx, ebx
0x1800931e8  jz      short loc_180093260
0x1800931ea  sub     ebx, 1
0x1800931ed  jz      short loc_18009323F
0x1800931ef  sub     ebx, 1
0x1800931f2  jz      short loc_18009321E
0x1800931f4  cmp     ebx, 1
0x1800931f7  jnz     loc_180093282
0x1800931fd  mov     rcx, cs:qword_1800A75C8
0x180093204  test    rcx, rcx
0x180093207  jnz     short loc_180093282
0x180093209  lea     rcx, aUser32Dll_0; "user32.dll"
0x180093210  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x180093215  mov     cs:qword_1800A75C8, rax
0x18009321c  jmp     short loc_18009327F
0x18009321e  mov     rcx, cs:qword_1800A7568
0x180093225  test    rcx, rcx
0x180093228  jnz     short loc_180093282
0x18009322a  lea     rcx, aOleaccDll; "oleacc.dll"
0x180093231  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x180093236  mov     cs:qword_1800A7568, rax
0x18009323d  jmp     short loc_18009327F
0x18009323f  mov     rcx, cs:qword_1800A7558
0x180093246  test    rcx, rcx
0x180093249  jnz     short loc_180093282
0x18009324b  lea     rcx, aOle32Dll; "ole32.dll"
0x180093252  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x180093257  mov     cs:qword_1800A7558, rax
0x18009325e  jmp     short loc_18009327F
0x180093260  mov     rcx, cs:hLibModule
0x180093267  test    rcx, rcx
0x18009326a  jnz     short loc_180093282
0x18009326c  lea     rcx, aOleaut32Dll; "oleaut32.dll"
0x180093273  call    ?LoadLibrary@CW32System@@SAPEAUHINSTANCE__@@PEBG@Z; CW32System::LoadLibrary(ushort const *)
0x180093278  mov     cs:hLibModule, rax
0x18009327f  mov     rcx, rax; hModule
0x180093282  mov     rdx, rsi; lpProcName
0x180093285  call    cs:__imp_GetProcAddress
0x18009328c  nop     dword ptr [rax+rax+00h]
0x180093291  mov     [rdi], rax
0x180093294  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CriticalSection
0x18009329b  mov     rbx, [rsp+28h+arg_0]
0x1800932a0  mov     rsi, [rsp+28h+arg_8]
0x1800932a5  add     rsp, 20h
0x1800932a9  pop     rdi
0x1800932aa  jmp     cs:__imp_LeaveCriticalSection
```

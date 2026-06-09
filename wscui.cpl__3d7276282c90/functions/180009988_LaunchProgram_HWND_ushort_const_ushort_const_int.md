# LaunchProgram(HWND__ *,ushort const *,ushort const *,int)

- ea: `0x180009988`
- end: `0x1800099df`
- name: `?LaunchProgram@@YA_NPEAUHWND__@@PEBG1H@Z`
- size: `87`
- prototype: `bool(HWND, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180007938`
- `0x180007b08`
- `0x180009d08`

## callees

- `0x180009988`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800099bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800099bc`
- `api-ms-win-core-memory-l1-1-1!SetProcessWorkingSetSize` at `0x1800099cc`
- `api-ms-win-core-memory-l1-1-1!SetProcessWorkingSetSize` at `0x1800099cc`
- `SHELL32!ShellExecuteW` at `0x1800099b3`
- `SHELL32!ShellExecuteW` at `0x1800099b3`

## pseudocode

```c
bool __fastcall LaunchProgram(HWND a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  HINSTANCE v3; // rbx
  HANDLE CurrentProcess; // rax

  if ( !a3 || !*a3 )
    a3 = 0;
  v3 = ShellExecuteW(a1, 0, a2, a3, 0, 1);
  CurrentProcess = GetCurrentProcess();
  SetProcessWorkingSetSize(CurrentProcess, 0xFFFFFFFFFFFFFFFFuLL, 0xFFFFFFFFFFFFFFFFuLL);
  return (unsigned __int64)v3 > 0x20;
}

```

## disassembly

```asm
0x180009988  push    rbx
0x18000998a  sub     rsp, 30h
0x18000998e  xor     eax, eax
0x180009990  test    r8, r8
0x180009993  jz      short loc_18000999B
0x180009995  cmp     [r8], ax
0x180009999  jnz     short loc_18000999E
0x18000999b  mov     r8, rax
0x18000999e  mov     r9, r8; lpParameters
0x1800099a1  mov     [rsp+38h+nShowCmd], 1; nShowCmd
0x1800099a9  mov     r8, rdx; lpFile
0x1800099ac  mov     [rsp+38h+lpDirectory], rax; lpDirectory
0x1800099b1  xor     edx, edx; lpOperation
0x1800099b3  call    cs:__imp_ShellExecuteW
0x1800099b9  mov     rbx, rax
0x1800099bc  call    cs:__imp_GetCurrentProcess
0x1800099c2  or      rdx, 0FFFFFFFFFFFFFFFFh; dwMinimumWorkingSetSize
0x1800099c6  mov     rcx, rax; hProcess
0x1800099c9  mov     r8, rdx; dwMaximumWorkingSetSize
0x1800099cc  call    cs:__imp_SetProcessWorkingSetSize
0x1800099d2  cmp     rbx, 20h ; ' '
0x1800099d6  setnbe  al
0x1800099d9  add     rsp, 30h
0x1800099dd  pop     rbx
0x1800099de  retn
```

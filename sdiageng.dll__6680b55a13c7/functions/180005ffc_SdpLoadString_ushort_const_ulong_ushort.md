# SdpLoadString(ushort const *,ulong,ushort * *)

- ea: `0x180005ffc`
- end: `0x180006154`
- name: `?SdpLoadString@@YAJPEBGKPEAPEAG@Z`
- size: `344`
- prototype: `__int64 __fastcall(const unsigned __int16 *, UINT, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800034c4`
- `0x180004518`
- `0x180004d58`
- `0x18000615c`
- `0x18001483c`
- `0x1800151fc`
- `0x180018a9c`
- `0x18001cc2c`
- `0x18001d544`
- `0x180020fc0`
- `0x18002114c`

## callees

- `0x1800012a4`
- `0x1800012b0`
- `0x180005ffc`
- `0x180026fa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800060a1`
- `KERNEL32!GetLastError` at `0x1800060f3`
- `KERNEL32!GetLastError` at `0x1800060a1`
- `KERNEL32!GetLastError` at `0x1800060f3`
- `KERNEL32!LoadLibraryExW` at `0x180006049`
- `KERNEL32!LoadLibraryExW` at `0x180006049`
- `KERNEL32!GetModuleHandleExW` at `0x180006093`
- `KERNEL32!GetModuleHandleExW` at `0x180006093`
- `KERNEL32!FreeLibrary` at `0x180006143`
- `KERNEL32!FreeLibrary` at `0x180006143`
- `USER32!LoadStringW` at `0x1800060d5`
- `USER32!LoadStringW` at `0x1800060d5`

## pseudocode

```c
__int64 __fastcall SdpLoadString(const unsigned __int16 *a1, UINT a2, unsigned __int16 **a3)
{
  signed int v5; // ebx
  unsigned int v6; // r8d
  WCHAR *v7; // rax
  unsigned __int16 *v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // r8d
  signed int v11; // eax
  HMODULE phModule; // [rsp+60h] [rbp+18h] BYREF

  phModule = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 424;
LABEL_3:
    SdpDebugTrace(1u, L"SdpLoadString", v6, v5);
    goto LABEL_24;
  }
  if ( a1 )
  {
    v5 = 0;
    phModule = LoadLibraryExW(a1, 0, 2u);
  }
  else if ( GetModuleHandleExW(0, L"sdiageng", &phModule) )
  {
    v5 = 0;
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = 439;
      goto LABEL_3;
    }
  }
  if ( (unsigned __int64)phModule - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = 0;
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
    v10 = 442;
    if ( v5 >= 0 )
      v5 = -2147467259;
  }
  else
  {
    v7 = (WCHAR *)operator new[](0x800u);
    v8 = v7;
    if ( !v7 )
    {
      v5 = -2147024882;
      v6 = 445;
      goto LABEL_3;
    }
    if ( LoadStringW(phModule, a2, v7, 1024) )
    {
      *a3 = v8;
      goto LABEL_24;
    }
    v5 = -2143551222;
    v10 = 450;
  }
  SdpDebugTrace(1u, L"SdpLoadString", v10, v5);
  if ( v8 )
    operator delete(v8);
LABEL_24:
  if ( phModule )
    FreeLibrary(phModule);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005ffc  push    rbx
0x180005ffe  push    rbp
0x180005fff  push    rsi
0x180006000  push    rdi
0x180006001  sub     rsp, 28h
0x180006005  mov     [rsp+48h+phModule], 0
0x18000600e  mov     rsi, r8
0x180006011  mov     ebp, edx
0x180006013  test    r8, r8
0x180006016  jnz     short loc_18000603C
0x180006018  mov     ebx, 80070057h
0x18000601d  mov     r8d, 1A8h; int
0x180006023  mov     r9d, ebx; int
0x180006026  lea     rdx, aSdploadstring; "SdpLoadString"
0x18000602d  mov     ecx, 1; Level
0x180006032  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x180006037  jmp     loc_180006139
0x18000603c  test    rcx, rcx
0x18000603f  jz      short loc_180006085
0x180006041  xor     ebx, ebx
0x180006043  xor     edx, edx; hFile
0x180006045  lea     r8d, [rbx+2]; dwFlags
0x180006049  call    cs:__imp_LoadLibraryExW
0x18000604f  mov     [rsp+48h+phModule], rax
0x180006054  mov     rax, [rsp+48h+phModule]
0x180006059  dec     rax
0x18000605c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006060  ja      loc_1800060F1
0x180006066  mov     ecx, 800h; unsigned __int64
0x18000606b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180006070  mov     rdi, rax
0x180006073  test    rax, rax
0x180006076  jnz     short loc_1800060C5
0x180006078  mov     ebx, 8007000Eh
0x18000607d  mov     r8d, 1BDh
0x180006083  jmp     short loc_180006023
0x180006085  lea     r8, [rsp+48h+phModule]; phModule
0x18000608a  xor     ecx, ecx; dwFlags
0x18000608c  lea     rdx, ModuleName; "sdiageng"
0x180006093  call    cs:__imp_GetModuleHandleExW
0x180006099  test    eax, eax
0x18000609b  jz      short loc_1800060A1
0x18000609d  xor     ebx, ebx
0x18000609f  jmp     short loc_180006054
0x1800060a1  call    cs:__imp_GetLastError
0x1800060a7  mov     ebx, eax
0x1800060a9  test    eax, eax
0x1800060ab  jle     short loc_1800060B6
0x1800060ad  movzx   ebx, ax
0x1800060b0  or      ebx, 80070000h
0x1800060b6  test    ebx, ebx
0x1800060b8  jns     short loc_180006054
0x1800060ba  mov     r8d, 1B7h
0x1800060c0  jmp     loc_180006023
0x1800060c5  mov     rcx, [rsp+48h+phModule]; hInstance
0x1800060ca  mov     r9d, 400h; cchBufferMax
0x1800060d0  mov     r8, rdi; lpBuffer
0x1800060d3  mov     edx, ebp; uID
0x1800060d5  call    cs:__imp_LoadStringW
0x1800060db  test    eax, eax
0x1800060dd  jnz     short loc_1800060EC
0x1800060df  mov     ebx, 803C010Ah
0x1800060e4  mov     r8d, 1C2h
0x1800060ea  jmp     short loc_180006118
0x1800060ec  mov     [rsi], rdi
0x1800060ef  jmp     short loc_180006139
0x1800060f1  xor     edi, edi
0x1800060f3  call    cs:__imp_GetLastError
0x1800060f9  mov     ebx, eax
0x1800060fb  test    eax, eax
0x1800060fd  jle     short loc_180006108
0x1800060ff  movzx   ebx, ax
0x180006102  or      ebx, 80070000h
0x180006108  test    ebx, ebx
0x18000610a  mov     eax, 80004005h
0x18000610f  mov     r8d, 1BAh; int
0x180006115  cmovns  ebx, eax
0x180006118  mov     r9d, ebx; int
0x18000611b  lea     rdx, aSdploadstring; "SdpLoadString"
0x180006122  mov     ecx, 1; Level
0x180006127  call    ?SdpDebugTrace@@YAXKPEBGHJ@Z; SdpDebugTrace(ulong,ushort const *,int,long)
0x18000612c  test    rdi, rdi
0x18000612f  jz      short loc_180006139
0x180006131  mov     rcx, rdi; Block
0x180006134  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006139  mov     rcx, [rsp+48h+phModule]; hLibModule
0x18000613e  test    rcx, rcx
0x180006141  jz      short loc_180006149
0x180006143  call    cs:__imp_FreeLibrary
0x180006149  mov     eax, ebx
0x18000614b  add     rsp, 28h
0x18000614f  pop     rdi
0x180006150  pop     rsi
0x180006151  pop     rbp
0x180006152  pop     rbx
0x180006153  retn
```

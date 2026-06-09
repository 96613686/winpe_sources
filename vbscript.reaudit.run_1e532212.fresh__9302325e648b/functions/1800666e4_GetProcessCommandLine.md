# GetProcessCommandLine

- ea: `0x1800666e4`
- end: `0x1800668cc`
- name: `GetProcessCommandLine`
- size: `488`
- prototype: `__int64 __fastcall(HANDLE hProcess, char *Destination)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180066ec4`

## callees

- `0x180045484`
- `0x180045dd4`
- `0x1800666e4`
- `0x1800671c8`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x1800667ad`
- `KERNEL32!ReadProcessMemory` at `0x1800667e7`
- `KERNEL32!ReadProcessMemory` at `0x180066857`
- `KERNEL32!ReadProcessMemory` at `0x1800667ad`
- `KERNEL32!ReadProcessMemory` at `0x1800667e7`
- `KERNEL32!ReadProcessMemory` at `0x180066857`
- `KERNEL32!WideCharToMultiByte` at `0x18006688f`
- `KERNEL32!WideCharToMultiByte` at `0x18006688f`
- `KERNEL32!GetModuleHandleA` at `0x180066734`
- `KERNEL32!GetModuleHandleA` at `0x180066734`
- `KERNEL32!GetProcAddress` at `0x18006674d`
- `KERNEL32!GetProcAddress` at `0x18006674d`

## string_xrefs

- `0x18006671e`: `ntdll.dll`

## pseudocode

```c
void __fastcall GetProcessCommandLine(HANDLE hProcess, char *Destination)
{
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  WCHAR *v8; // rax
  WCHAR *v9; // rbx
  LPCVOID lpBaseAddress[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v11; // [rsp+50h] [rbp-B0h]
  __int128 v12; // [rsp+60h] [rbp-A0h]
  _BYTE v13[112]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v14; // [rsp+E0h] [rbp-20h]
  LPCVOID v15; // [rsp+E8h] [rbp-18h]
  _BYTE Buffer[32]; // [rsp+F0h] [rbp-10h] BYREF
  LPCVOID v17; // [rsp+110h] [rbp+10h]

  *Destination = 0;
  *(_OWORD *)lpBaseAddress = 0;
  v11 = 0;
  v12 = 0;
  ModuleHandleA = GetModuleHandleA("ntdll.dll");
  if ( ModuleHandleA )
  {
    ProcAddress = GetProcAddress(ModuleHandleA, "NtQueryInformationProcess");
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(HANDLE, _QWORD, LPCVOID *, __int64, _QWORD))ProcAddress)(
             hProcess,
             0,
             lpBaseAddress,
             48,
             0) >= 0 )
      {
        memset_0(Buffer, 0, 0x2C8u);
        if ( ReadProcessMemory(hProcess, lpBaseAddress[1], Buffer, 0x2C8u, 0) )
        {
          memset_0(v13, 0, 0x80u);
          if ( ReadProcessMemory(hProcess, v17, v13, 0x80u, 0) )
          {
            if ( (unsigned __int16)(v14 - 1) <= 0xFFEu )
            {
              v6 = ((unsigned __int64)v14 >> 1) + 1;
              v7 = 2 * v6;
              if ( !is_mul_ok(v6, 2u) )
                v7 = -1;
              v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
              v9 = v8;
              if ( v8 )
              {
                if ( ReadProcessMemory(hProcess, v15, v8, v14, 0) )
                {
                  v9[(unsigned __int64)v14 >> 1] = 0;
                  WideCharToMultiByte(0, 0, v9, -1, Destination, 512, 0, 0);
                  MaskPIIInCommandLine(Destination);
                }
                operator delete[](v9);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800666e4  mov     [rsp-8+arg_10], rbx
0x1800666e9  mov     [rsp-8+arg_18], rsi
0x1800666ee  push    rbp
0x1800666ef  push    rdi
0x1800666f0  push    r15
0x1800666f2  lea     rbp, [rsp-2D0h]
0x1800666fa  sub     rsp, 3D0h
0x180066701  mov     rax, cs:__security_cookie
0x180066708  xor     rax, rsp
0x18006670b  mov     [rbp+2E0h+var_20], rax
0x180066712  xorps   xmm0, xmm0
0x180066715  mov     byte ptr [rdx], 0
0x180066718  mov     rdi, rcx
0x18006671b  mov     rsi, rdx
0x18006671e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180066725  movups  xmmword ptr [rsp+3E0h+lpBaseAddress], xmm0
0x18006672a  movups  [rsp+3E0h+var_390], xmm0
0x18006672f  movups  [rsp+3E0h+var_380], xmm0
0x180066734  call    cs:__imp_GetModuleHandleA
0x18006673a  test    rax, rax
0x18006673d  jz      loc_1800668A5
0x180066743  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x18006674a  mov     rcx, rax; hModule
0x18006674d  call    cs:__imp_GetProcAddress
0x180066753  test    rax, rax
0x180066756  jz      loc_1800668A5
0x18006675c  mov     r9d, 30h ; '0'
0x180066762  mov     [rsp+3E0h+lpNumberOfBytesRead], 0
0x18006676b  lea     r8, [rsp+3E0h+lpBaseAddress]
0x180066770  xor     edx, edx
0x180066772  mov     rcx, rdi
0x180066775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006677a  test    eax, eax
0x18006677c  js      loc_1800668A5
0x180066782  mov     ebx, 2C8h
0x180066787  lea     rcx, [rbp+2E0h+Buffer]; void *
0x18006678b  mov     r8d, ebx; Size
0x18006678e  xor     edx, edx; Val
0x180066790  call    memset_0
0x180066795  mov     rdx, [rsp+3E0h+lpBaseAddress+8]; lpBaseAddress
0x18006679a  lea     r8, [rbp+2E0h+Buffer]; lpBuffer
0x18006679e  mov     r9d, ebx; nSize
0x1800667a1  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800667aa  mov     rcx, rdi; hProcess
0x1800667ad  call    cs:__imp_ReadProcessMemory
0x1800667b3  test    eax, eax
0x1800667b5  jz      loc_1800668A5
0x1800667bb  mov     ebx, 80h
0x1800667c0  lea     rcx, [rsp+3E0h+var_370]; void *
0x1800667c5  mov     r8d, ebx; Size
0x1800667c8  xor     edx, edx; Val
0x1800667ca  call    memset_0
0x1800667cf  mov     rdx, [rbp+2E0h+var_2D0]; lpBaseAddress
0x1800667d3  lea     r8, [rsp+3E0h+var_370]; lpBuffer
0x1800667d8  mov     r9d, ebx; nSize
0x1800667db  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800667e4  mov     rcx, rdi; hProcess
0x1800667e7  call    cs:__imp_ReadProcessMemory
0x1800667ed  test    eax, eax
0x1800667ef  jz      loc_1800668A5
0x1800667f5  movzx   eax, [rbp+2E0h+var_300]
0x1800667f9  lea     edx, [rbx-7Fh]
0x1800667fc  sub     ax, dx
0x1800667ff  mov     ecx, 0FFEh
0x180066804  cmp     ax, cx
0x180066807  ja      loc_1800668A5
0x18006680d  movzx   ecx, [rbp+2E0h+var_300]
0x180066811  lea     eax, [rbx-7Eh]
0x180066814  shr     rcx, 1
0x180066817  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18006681e  add     rcx, rdx
0x180066821  mul     rcx
0x180066824  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006682b  cmovb   rax, r15
0x18006682f  mov     rcx, rax; unsigned __int64
0x180066832  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180066837  mov     rbx, rax
0x18006683a  test    rax, rax
0x18006683d  jz      short loc_1800668A5
0x18006683f  movzx   r9d, [rbp+2E0h+var_300]; nSize
0x180066844  mov     r8, rax; lpBuffer
0x180066847  mov     rdx, [rbp+2E0h+var_2F8]; lpBaseAddress
0x18006684b  mov     rcx, rdi; hProcess
0x18006684e  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x180066857  call    cs:__imp_ReadProcessMemory
0x18006685d  test    eax, eax
0x18006685f  jz      short loc_18006689D
0x180066861  movzx   edx, [rbp+2E0h+var_300]
0x180066865  xor     eax, eax
0x180066867  mov     [rsp+3E0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18006686c  mov     r9d, r15d; cchWideChar
0x18006686f  shr     rdx, 1
0x180066872  mov     r8, rbx; lpWideCharStr
0x180066875  mov     [rsp+3E0h+lpDefaultChar], rax; lpDefaultChar
0x18006687a  xor     ecx, ecx; CodePage
0x18006687c  mov     [rsp+3E0h+cbMultiByte], 200h; cbMultiByte
0x180066884  mov     [rsp+3E0h+lpNumberOfBytesRead], rsi; lpMultiByteStr
0x180066889  mov     [rbx+rdx*2], ax
0x18006688d  xor     edx, edx; dwFlags
0x18006688f  call    cs:__imp_WideCharToMultiByte
0x180066895  mov     rcx, rsi; Destination
0x180066898  call    MaskPIIInCommandLine
0x18006689d  mov     rcx, rbx; Block
0x1800668a0  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800668a5  mov     rcx, [rbp+2E0h+var_20]
0x1800668ac  xor     rcx, rsp; StackCookie
0x1800668af  call    __security_check_cookie
0x1800668b4  lea     r11, [rsp+3E0h+var_10]
0x1800668bc  mov     rbx, [r11+30h]
0x1800668c0  mov     rsi, [r11+38h]
0x1800668c4  mov     rsp, r11
0x1800668c7  pop     r15
0x1800668c9  pop     rdi
0x1800668ca  pop     rbp
0x1800668cb  retn
```

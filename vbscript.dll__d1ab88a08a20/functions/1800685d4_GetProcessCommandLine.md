# GetProcessCommandLine

- ea: `0x1800685d4`
- end: `0x1800687e1`
- name: `GetProcessCommandLine`
- size: `525`
- prototype: `void __fastcall(HANDLE hProcess, char *Destination)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180068e7c`

## callees

- `0x180046878`
- `0x1800471c4`
- `0x1800685d4`
- `0x1800691dc`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `KERNEL32!ReadProcessMemory` at `0x1800686a9`
- `KERNEL32!ReadProcessMemory` at `0x1800686e9`
- `KERNEL32!ReadProcessMemory` at `0x18006875f`
- `KERNEL32!ReadProcessMemory` at `0x1800686a9`
- `KERNEL32!ReadProcessMemory` at `0x1800686e9`
- `KERNEL32!ReadProcessMemory` at `0x18006875f`
- `KERNEL32!WideCharToMultiByte` at `0x18006879d`
- `KERNEL32!WideCharToMultiByte` at `0x18006879d`
- `KERNEL32!GetModuleHandleA` at `0x180068624`
- `KERNEL32!GetModuleHandleA` at `0x180068624`
- `KERNEL32!GetProcAddress` at `0x180068643`
- `KERNEL32!GetProcAddress` at `0x180068643`

## string_xrefs

- `0x18006860e`: `ntdll.dll`

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
0x1800685d4  mov     [rsp-8+arg_10], rbx
0x1800685d9  mov     [rsp-8+arg_18], rsi
0x1800685de  push    rbp
0x1800685df  push    rdi
0x1800685e0  push    r15
0x1800685e2  lea     rbp, [rsp-2D0h]
0x1800685ea  sub     rsp, 3D0h
0x1800685f1  mov     rax, cs:__security_cookie
0x1800685f8  xor     rax, rsp
0x1800685fb  mov     [rbp+2E0h+var_20], rax
0x180068602  xorps   xmm0, xmm0
0x180068605  mov     byte ptr [rdx], 0
0x180068608  mov     rdi, rcx
0x18006860b  mov     rsi, rdx
0x18006860e  lea     rcx, aNtdllDll; "ntdll.dll"
0x180068615  movups  xmmword ptr [rsp+3E0h+lpBaseAddress], xmm0
0x18006861a  movups  [rsp+3E0h+var_390], xmm0
0x18006861f  movups  [rsp+3E0h+var_380], xmm0
0x180068624  call    cs:__imp_GetModuleHandleA
0x18006862b  nop     dword ptr [rax+rax+00h]
0x180068630  test    rax, rax
0x180068633  jz      loc_1800687B9
0x180068639  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x180068640  mov     rcx, rax; hModule
0x180068643  call    cs:__imp_GetProcAddress
0x18006864a  nop     dword ptr [rax+rax+00h]
0x18006864f  test    rax, rax
0x180068652  jz      loc_1800687B9
0x180068658  mov     r9d, 30h ; '0'
0x18006865e  mov     [rsp+3E0h+lpNumberOfBytesRead], 0
0x180068667  lea     r8, [rsp+3E0h+lpBaseAddress]
0x18006866c  xor     edx, edx
0x18006866e  mov     rcx, rdi
0x180068671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068676  test    eax, eax
0x180068678  js      loc_1800687B9
0x18006867e  mov     ebx, 2C8h
0x180068683  lea     rcx, [rbp+2E0h+Buffer]; void *
0x180068687  mov     r8d, ebx; Size
0x18006868a  xor     edx, edx; Val
0x18006868c  call    memset_0
0x180068691  mov     rdx, [rsp+3E0h+lpBaseAddress+8]; lpBaseAddress
0x180068696  lea     r8, [rbp+2E0h+Buffer]; lpBuffer
0x18006869a  mov     r9d, ebx; nSize
0x18006869d  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800686a6  mov     rcx, rdi; hProcess
0x1800686a9  call    cs:__imp_ReadProcessMemory
0x1800686b0  nop     dword ptr [rax+rax+00h]
0x1800686b5  test    eax, eax
0x1800686b7  jz      loc_1800687B9
0x1800686bd  mov     ebx, 80h
0x1800686c2  lea     rcx, [rsp+3E0h+var_370]; void *
0x1800686c7  mov     r8d, ebx; Size
0x1800686ca  xor     edx, edx; Val
0x1800686cc  call    memset_0
0x1800686d1  mov     rdx, [rbp+2E0h+var_2D0]; lpBaseAddress
0x1800686d5  lea     r8, [rsp+3E0h+var_370]; lpBuffer
0x1800686da  mov     r9d, ebx; nSize
0x1800686dd  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x1800686e6  mov     rcx, rdi; hProcess
0x1800686e9  call    cs:__imp_ReadProcessMemory
0x1800686f0  nop     dword ptr [rax+rax+00h]
0x1800686f5  test    eax, eax
0x1800686f7  jz      loc_1800687B9
0x1800686fd  movzx   eax, [rbp+2E0h+var_300]
0x180068701  lea     edx, [rbx-7Fh]
0x180068704  sub     ax, dx
0x180068707  mov     ecx, 0FFEh
0x18006870c  cmp     ax, cx
0x18006870f  ja      loc_1800687B9
0x180068715  movzx   ecx, [rbp+2E0h+var_300]
0x180068719  lea     eax, [rbx-7Eh]
0x18006871c  shr     rcx, 1
0x18006871f  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180068726  add     rcx, rdx
0x180068729  mul     rcx
0x18006872c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180068733  cmovb   rax, r15
0x180068737  mov     rcx, rax; unsigned __int64
0x18006873a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18006873f  mov     rbx, rax
0x180068742  test    rax, rax
0x180068745  jz      short loc_1800687B9
0x180068747  movzx   r9d, [rbp+2E0h+var_300]; nSize
0x18006874c  mov     r8, rax; lpBuffer
0x18006874f  mov     rdx, [rbp+2E0h+var_2F8]; lpBaseAddress
0x180068753  mov     rcx, rdi; hProcess
0x180068756  mov     [rsp+3E0h+lpNumberOfBytesRead], 0; lpNumberOfBytesRead
0x18006875f  call    cs:__imp_ReadProcessMemory
0x180068766  nop     dword ptr [rax+rax+00h]
0x18006876b  test    eax, eax
0x18006876d  jz      short loc_1800687B1
0x18006876f  movzx   edx, [rbp+2E0h+var_300]
0x180068773  xor     eax, eax
0x180068775  mov     [rsp+3E0h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18006877a  mov     r9d, r15d; cchWideChar
0x18006877d  shr     rdx, 1
0x180068780  mov     r8, rbx; lpWideCharStr
0x180068783  mov     [rsp+3E0h+lpDefaultChar], rax; lpDefaultChar
0x180068788  xor     ecx, ecx; CodePage
0x18006878a  mov     [rsp+3E0h+cbMultiByte], 200h; cbMultiByte
0x180068792  mov     [rsp+3E0h+lpNumberOfBytesRead], rsi; lpMultiByteStr
0x180068797  mov     [rbx+rdx*2], ax
0x18006879b  xor     edx, edx; dwFlags
0x18006879d  call    cs:__imp_WideCharToMultiByte
0x1800687a4  nop     dword ptr [rax+rax+00h]
0x1800687a9  mov     rcx, rsi; Destination
0x1800687ac  call    MaskPIIInCommandLine
0x1800687b1  mov     rcx, rbx; Block
0x1800687b4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800687b9  mov     rcx, [rbp+2E0h+var_20]
0x1800687c0  xor     rcx, rsp; StackCookie
0x1800687c3  call    __security_check_cookie
0x1800687c8  lea     r11, [rsp+3E0h+var_10]
0x1800687d0  mov     rbx, [r11+30h]
0x1800687d4  mov     rsi, [r11+38h]
0x1800687d8  mov     rsp, r11
0x1800687db  pop     r15
0x1800687dd  pop     rdi
0x1800687de  pop     rbp
0x1800687df  retn
```

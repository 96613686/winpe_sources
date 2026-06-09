# GetServiceInfoForSvchost

- ea: `0x1800687e8`
- end: `0x180068a0e`
- name: `GetServiceInfoForSvchost`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180068e7c`

## callees

- `0x180046878`
- `0x1800471c4`
- `0x1800687e8`
- `0x18007a010`

## import_xrefs

- `msvcrt!_mbsnbcpy_s` at `0x1800689c6`
- `msvcrt!_mbsnbcpy_s` at `0x1800689c6`
- `KERNEL32!LoadLibraryA` at `0x180068813`
- `KERNEL32!LoadLibraryA` at `0x180068813`
- `KERNEL32!FreeLibrary` at `0x1800689e8`
- `KERNEL32!FreeLibrary` at `0x1800689e8`
- `KERNEL32!GetProcAddress` at `0x180068835`
- `KERNEL32!GetProcAddress` at `0x18006884e`
- `KERNEL32!GetProcAddress` at `0x180068867`
- `KERNEL32!GetProcAddress` at `0x180068835`
- `KERNEL32!GetProcAddress` at `0x18006884e`
- `KERNEL32!GetProcAddress` at `0x180068867`

## string_xrefs

- `0x180068809`: `advapi32.dll`
- `0x180068841`: `EnumServicesStatusExA`
- `0x18006885a`: `CloseServiceHandle`
- `0x18006882b`: `OpenSCManagerA`

## pseudocode

```c
int __fastcall GetServiceInfoForSvchost(int a1, unsigned __int8 *a2, unsigned __int64 a3)
{
  HMODULE LibraryA; // rax
  HMODULE v6; // rdi
  FARPROC ProcAddress; // rbx
  FARPROC v8; // rbp
  FARPROC v9; // rax
  void (__fastcall *v10)(__int64); // r15
  __int64 v11; // rax
  __int64 v12; // rsi
  char *v13; // rbx
  unsigned int v14; // ecx
  __int64 v15; // r8
  unsigned int v17; // [rsp+98h] [rbp+10h] BYREF
  unsigned __int64 v18; // [rsp+A0h] [rbp+18h] BYREF

  v18 = a3;
  *a2 = 0;
  LibraryA = LoadLibraryA("advapi32.dll");
  v6 = LibraryA;
  if ( LibraryA )
  {
    ProcAddress = GetProcAddress(LibraryA, "OpenSCManagerA");
    v8 = GetProcAddress(v6, "EnumServicesStatusExA");
    v9 = GetProcAddress(v6, "CloseServiceHandle");
    v10 = (void (__fastcall *)(__int64))v9;
    if ( ProcAddress )
    {
      if ( v8 )
      {
        if ( v9 )
        {
          v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64))ProcAddress)(0, 0, 4);
          v12 = v11;
          if ( v11 )
          {
            LODWORD(v18) = 0;
            v17 = 0;
            ((void (__fastcall *)(__int64, _QWORD, __int64, __int64, _QWORD, _DWORD, unsigned __int64 *, unsigned int *, _QWORD, _QWORD))v8)(
              v11,
              0,
              48,
              3,
              0,
              0,
              &v18,
              &v17,
              0,
              0);
            if ( (_DWORD)v18 )
            {
              v13 = (char *)operator new[]((unsigned int)v18, (const struct std::nothrow_t *)&std::nothrow);
              if ( v13 )
              {
                if ( ((unsigned int (__fastcall *)(__int64, _QWORD, __int64, __int64, char *, _DWORD, unsigned __int64 *, unsigned int *, _QWORD, _QWORD))v8)(
                       v12,
                       0,
                       48,
                       3,
                       v13,
                       v18,
                       &v18,
                       &v17,
                       0,
                       0) )
                {
                  v14 = 0;
                  if ( v17 )
                  {
                    while ( 1 )
                    {
                      v15 = 56LL * v14;
                      if ( *(_DWORD *)&v13[v15 + 44] == a1 )
                        break;
                      if ( ++v14 >= v17 )
                        goto LABEL_14;
                    }
                    _mbsnbcpy_s(a2, 0x100u, *(const unsigned __int8 **)&v13[v15 + 8], 0xFFFFFFFFFFFFFFFFuLL);
                  }
                }
LABEL_14:
                operator delete[](v13);
              }
            }
            v10(v12);
          }
        }
      }
    }
    LODWORD(LibraryA) = FreeLibrary(v6);
  }
  return (int)LibraryA;
}

```

## disassembly

```asm
0x1800687e8  mov     [rsp+arg_0], rbx
0x1800687ed  mov     [rsp+arg_18], rbp
0x1800687f2  mov     [rsp+arg_10], r8
0x1800687f7  push    rsi
0x1800687f8  push    rdi
0x1800687f9  push    r12
0x1800687fb  push    r14
0x1800687fd  push    r15
0x1800687ff  sub     rsp, 60h
0x180068803  mov     r12d, ecx
0x180068806  mov     byte ptr [rdx], 0
0x180068809  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x180068810  mov     r14, rdx
0x180068813  call    cs:__imp_LoadLibraryA
0x18006881a  nop     dword ptr [rax+rax+00h]
0x18006881f  mov     rdi, rax
0x180068822  test    rax, rax
0x180068825  jz      loc_1800689F4
0x18006882b  lea     rdx, aOpenscmanagera; "OpenSCManagerA"
0x180068832  mov     rcx, rax; hModule
0x180068835  call    cs:__imp_GetProcAddress
0x18006883c  nop     dword ptr [rax+rax+00h]
0x180068841  lea     rdx, aEnumservicesst; "EnumServicesStatusExA"
0x180068848  mov     rcx, rdi; hModule
0x18006884b  mov     rbx, rax
0x18006884e  call    cs:__imp_GetProcAddress
0x180068855  nop     dword ptr [rax+rax+00h]
0x18006885a  lea     rdx, aCloseserviceha; "CloseServiceHandle"
0x180068861  mov     rcx, rdi; hModule
0x180068864  mov     rbp, rax
0x180068867  call    cs:__imp_GetProcAddress
0x18006886e  nop     dword ptr [rax+rax+00h]
0x180068873  mov     r15, rax
0x180068876  test    rbx, rbx
0x180068879  jz      loc_1800689E5
0x18006887f  test    rbp, rbp
0x180068882  jz      loc_1800689E5
0x180068888  test    rax, rax
0x18006888b  jz      loc_1800689E5
0x180068891  xor     edx, edx
0x180068893  xor     ecx, ecx
0x180068895  mov     rax, rbx
0x180068898  lea     r8d, [rdx+4]
0x18006889c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800688a1  mov     rsi, rax
0x1800688a4  test    rax, rax
0x1800688a7  jz      loc_1800689E5
0x1800688ad  mov     [rsp+88h+var_40], 0
0x1800688b6  lea     rax, [rsp+88h+arg_8]
0x1800688be  mov     [rsp+88h+var_48], 0
0x1800688c7  xor     edx, edx
0x1800688c9  mov     [rsp+88h+var_50], rax
0x1800688ce  mov     rcx, rsi
0x1800688d1  lea     rax, [rsp+88h+arg_10]
0x1800688d9  mov     dword ptr [rsp+88h+arg_10], 0
0x1800688e4  mov     [rsp+88h+var_58], rax
0x1800688e9  mov     rax, rbp
0x1800688ec  mov     [rsp+88h+var_60], 0
0x1800688f4  lea     r9d, [rdx+3]
0x1800688f8  lea     r8d, [rdx+30h]
0x1800688fc  mov     [rsp+88h+var_68], 0
0x180068905  mov     [rsp+88h+arg_8], 0
0x180068910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068915  mov     eax, dword ptr [rsp+88h+arg_10]
0x18006891c  test    eax, eax
0x18006891e  jz      loc_1800689DA
0x180068924  mov     ecx, eax; unsigned __int64
0x180068926  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006892d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180068932  mov     rbx, rax
0x180068935  test    rax, rax
0x180068938  jz      loc_1800689DA
0x18006893e  mov     ecx, dword ptr [rsp+88h+arg_10]
0x180068945  lea     rax, [rsp+88h+arg_8]
0x18006894d  mov     [rsp+88h+var_40], 0
0x180068956  xor     edx, edx
0x180068958  mov     [rsp+88h+var_48], 0
0x180068961  mov     [rsp+88h+var_50], rax
0x180068966  lea     rax, [rsp+88h+arg_10]
0x18006896e  mov     [rsp+88h+var_58], rax
0x180068973  mov     rax, rbp
0x180068976  mov     [rsp+88h+var_60], ecx
0x18006897a  lea     r9d, [rdx+3]
0x18006897e  mov     rcx, rsi
0x180068981  mov     [rsp+88h+var_68], rbx
0x180068986  lea     r8d, [rdx+30h]
0x18006898a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006898f  test    eax, eax
0x180068991  jz      short loc_1800689D2
0x180068993  mov     edx, [rsp+88h+arg_8]
0x18006899a  xor     ecx, ecx
0x18006899c  test    edx, edx
0x18006899e  jz      short loc_1800689D2
0x1800689a0  mov     eax, ecx
0x1800689a2  imul    r8, rax, 38h ; '8'
0x1800689a6  cmp     [r8+rbx+2Ch], r12d
0x1800689ab  jz      short loc_1800689B5
0x1800689ad  inc     ecx
0x1800689af  cmp     ecx, edx
0x1800689b1  jb      short loc_1800689A0
0x1800689b3  jmp     short loc_1800689D2
0x1800689b5  mov     r8, [r8+rbx+8]; Src
0x1800689ba  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800689be  mov     edx, 100h; SizeInBytes
0x1800689c3  mov     rcx, r14; Dst
0x1800689c6  call    cs:__imp__mbsnbcpy_s
0x1800689cd  nop     dword ptr [rax+rax+00h]
0x1800689d2  mov     rcx, rbx; Block
0x1800689d5  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800689da  mov     rcx, rsi
0x1800689dd  mov     rax, r15
0x1800689e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800689e5  mov     rcx, rdi; hLibModule
0x1800689e8  call    cs:__imp_FreeLibrary
0x1800689ef  nop     dword ptr [rax+rax+00h]
0x1800689f4  lea     r11, [rsp+88h+var_28]
0x1800689f9  mov     rbx, [r11+30h]
0x1800689fd  mov     rbp, [r11+48h]
0x180068a01  mov     rsp, r11
0x180068a04  pop     r15
0x180068a06  pop     r14
0x180068a08  pop     r12
0x180068a0a  pop     rdi
0x180068a0b  pop     rsi
0x180068a0c  retn
```

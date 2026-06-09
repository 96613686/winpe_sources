# CResourceCache::GetCachedHandle(ushort const *,HINSTANCE__ * *)

- ea: `0x180024474`
- end: `0x18002467d`
- name: `?GetCachedHandle@CResourceCache@@QEAAJPEBGPEAPEAUHINSTANCE__@@@Z`
- size: `521`
- prototype: `int(CResourceCache *__hidden this, const unsigned __int16 *, HINSTANCE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fc50`
- `0x180023070`

## callees

- `0x18000809c`
- `0x1800242f4`
- `0x180024474`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800244ce`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800244ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002450c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002450c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002464a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002464a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024542`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800245cb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180024542`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800245cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024634`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180024634`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002452a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024620`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002452a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800245b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024620`
- `KERNEL32!lstrlenW` at `0x180024587`
- `KERNEL32!lstrlenW` at `0x180024587`

## pseudocode

```c
__int64 __fastcall CResourceCache::GetCachedHandle(int **this, const unsigned __int16 *a2, HINSTANCE *a3)
{
  int *v4; // r8
  int v7; // edi
  int v8; // ecx
  unsigned int v9; // ebp
  _QWORD *v10; // rbx
  HMODULE Library; // rax
  HANDLE ProcessHeap; // rax
  char *v13; // rax
  char *v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // r15d
  unsigned int v18; // ebx
  HANDLE v19; // rax
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rbx
  int *v22; // rcx
  unsigned __int16 **v23; // rcx
  HANDLE v24; // rax
  __int64 result; // rax
  unsigned __int16 **v26; // [rsp+50h] [rbp+8h] BYREF

  *a3 = 0;
  v4 = *this;
  v7 = -2147467259;
  if ( *this )
  {
    v8 = *v4;
    if ( (*v4 & 0xFFFFFFF) != 0 )
    {
      v9 = 0;
      do
      {
        v10 = v4 + 2;
        if ( (v8 & 0x10000000) != 0 )
          v10 = (_QWORD *)*v10;
        if ( !(unsigned int)_o__wcsicmp(v10[2 * v9], a2) )
          *a3 = (HINSTANCE)v10[2 * v9 + 1];
        v4 = *this;
        ++v9;
        v8 = **this;
      }
      while ( v9 < (v8 & 0xFFFFFFFu) );
    }
  }
  if ( !*a3 )
  {
    Library = LoadLibraryExW(a2, 0, 2u);
    *a3 = Library;
    if ( Library )
    {
      if ( *this )
        goto LABEL_18;
      ProcessHeap = GetProcessHeap();
      v13 = (char *)HeapAlloc(ProcessHeap, 8u, 0x18u);
      v14 = v13;
      if ( v13 )
      {
        *(_DWORD *)v13 = *(_DWORD *)v13 & 0x80000000 | 0x20000000;
        v7 = 0;
        *(_OWORD *)(v13 + 8) = 0;
      }
      else
      {
        v7 = -2147024882;
      }
      if ( v7 < 0 )
        v14 = 0;
      *this = (int *)v14;
      if ( v7 >= 0 )
      {
LABEL_18:
        v15 = lstrlenW(a2);
        v16 = v15 + 1;
        if ( (unsigned int)v16 < v15 )
        {
          v7 = -2147024362;
        }
        else
        {
          v17 = v15 + 1;
          v7 = 0;
          if ( (unsigned __int64)(2 * v16) > 0xFFFFFFFF )
            goto LABEL_27;
          v18 = 2 * v16;
          v19 = GetProcessHeap();
          v20 = (unsigned __int16 *)HeapAlloc(v19, 0, v18);
          v21 = v20;
          if ( !v20 )
            goto LABEL_27;
          v7 = StringCchCopyW(v20, v17, a2);
          if ( v7 >= 0 )
          {
            v22 = *this;
            v26 = 0;
            v7 = DirectUI::DynamicArrayBase<_HINST_MAPPING,DirectUI::DoubleAllocationPolicy<_HINST_MAPPING>,1,0>::AddPtr(
                   v22,
                   &v26);
            if ( v7 >= 0 )
            {
              v23 = v26;
              v26[1] = (unsigned __int16 *)*a3;
              *v23 = v21;
              goto LABEL_27;
            }
          }
          v24 = GetProcessHeap();
          HeapFree(v24, 0, v21);
        }
      }
      FreeLibrary(*a3);
      *a3 = 0;
    }
  }
LABEL_27:
  result = 0;
  if ( !*a3 )
    return (unsigned int)v7;
  return result;
}

```

## disassembly

```asm
0x180024474  mov     [rsp+arg_8], rbx
0x180024479  mov     [rsp+arg_10], rbp
0x18002447e  push    rsi
0x18002447f  push    rdi
0x180024480  push    r12
0x180024482  push    r14
0x180024484  push    r15
0x180024486  sub     rsp, 20h
0x18002448a  mov     rsi, r8
0x18002448d  mov     qword ptr [r8], 0
0x180024494  mov     r8, [rcx]
0x180024497  mov     r12, rdx
0x18002449a  mov     r14, rcx
0x18002449d  mov     edi, 80004005h
0x1800244a2  test    r8, r8
0x1800244a5  jz      short loc_1800244F9
0x1800244a7  mov     ecx, [r8]
0x1800244aa  test    ecx, 0FFFFFFFh
0x1800244b0  jbe     short loc_1800244F9
0x1800244b2  xor     ebp, ebp
0x1800244b4  lea     rbx, [r8+8]
0x1800244b8  bt      ecx, 1Ch
0x1800244bc  jnb     short loc_1800244C1
0x1800244be  mov     rbx, [rbx]
0x1800244c1  mov     r15d, ebp
0x1800244c4  mov     rdx, r12
0x1800244c7  add     r15, r15
0x1800244ca  mov     rcx, [rbx+r15*8]
0x1800244ce  call    cs:__imp__o__wcsicmp
0x1800244d5  nop     dword ptr [rax+rax+00h]
0x1800244da  test    eax, eax
0x1800244dc  jnz     short loc_1800244E6
0x1800244de  mov     rax, [rbx+r15*8+8]
0x1800244e3  mov     [rsi], rax
0x1800244e6  mov     r8, [r14]
0x1800244e9  inc     ebp
0x1800244eb  mov     ecx, [r8]
0x1800244ee  mov     eax, ecx
0x1800244f0  and     eax, 0FFFFFFFh
0x1800244f5  cmp     ebp, eax
0x1800244f7  jb      short loc_1800244B4
0x1800244f9  cmp     qword ptr [rsi], 0
0x1800244fd  jnz     loc_18002465D
0x180024503  xor     edx, edx; hFile
0x180024505  mov     rcx, r12; lpLibFileName
0x180024508  lea     r8d, [rdx+2]; dwFlags
0x18002450c  call    cs:__imp_LoadLibraryExW
0x180024513  nop     dword ptr [rax+rax+00h]
0x180024518  mov     [rsi], rax
0x18002451b  test    rax, rax
0x18002451e  jz      loc_18002465D
0x180024524  cmp     qword ptr [r14], 0
0x180024528  jnz     short loc_180024584
0x18002452a  call    cs:__imp_GetProcessHeap
0x180024531  nop     dword ptr [rax+rax+00h]
0x180024536  mov     edx, 8; dwFlags
0x18002453b  mov     rcx, rax; hHeap
0x18002453e  lea     r8d, [rdx+10h]; dwBytes
0x180024542  call    cs:__imp_HeapAlloc
0x180024549  nop     dword ptr [rax+rax+00h]
0x18002454e  mov     rcx, rax
0x180024551  test    rax, rax
0x180024554  jnz     short loc_18002455D
0x180024556  mov     edi, 8007000Eh
0x18002455b  jmp     short loc_180024573
0x18002455d  mov     eax, [rax]
0x18002455f  xorps   xmm0, xmm0
0x180024562  and     eax, 0A0000000h
0x180024567  bts     eax, 1Dh
0x18002456b  mov     [rcx], eax
0x18002456d  xor     edi, edi
0x18002456f  movups  xmmword ptr [rcx+8], xmm0
0x180024573  xor     eax, eax
0x180024575  test    edi, edi
0x180024577  cmovs   rcx, rax
0x18002457b  mov     [r14], rcx
0x18002457e  js      loc_180024647
0x180024584  mov     rcx, r12; lpString
0x180024587  call    cs:__imp_lstrlenW
0x18002458e  nop     dword ptr [rax+rax+00h]
0x180024593  lea     ecx, [rax+1]
0x180024596  cmp     ecx, eax
0x180024598  jb      loc_180024642
0x18002459e  lea     rax, [rcx+rcx]
0x1800245a2  mov     r15d, ecx
0x1800245a5  mov     ecx, 0FFFFFFFFh
0x1800245aa  xor     edi, edi
0x1800245ac  cmp     rax, rcx
0x1800245af  ja      loc_18002465D
0x1800245b5  mov     ebx, eax
0x1800245b7  call    cs:__imp_GetProcessHeap
0x1800245be  nop     dword ptr [rax+rax+00h]
0x1800245c3  mov     r8d, ebx; dwBytes
0x1800245c6  xor     edx, edx; dwFlags
0x1800245c8  mov     rcx, rax; hHeap
0x1800245cb  call    cs:__imp_HeapAlloc
0x1800245d2  nop     dword ptr [rax+rax+00h]
0x1800245d7  mov     rbx, rax
0x1800245da  test    rax, rax
0x1800245dd  jz      short loc_18002465D
0x1800245df  mov     r8, r12; unsigned __int16 *
0x1800245e2  mov     edx, r15d; unsigned __int64
0x1800245e5  mov     rcx, rax; unsigned __int16 *
0x1800245e8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800245ed  mov     edi, eax
0x1800245ef  test    eax, eax
0x1800245f1  js      short loc_180024620
0x1800245f3  mov     rcx, [r14]
0x1800245f6  lea     rdx, [rsp+48h+arg_0]
0x1800245fb  mov     [rsp+48h+arg_0], 0
0x180024604  call    ?AddPtr@?$DynamicArrayBase@U_HINST_MAPPING@@V?$DoubleAllocationPolicy@U_HINST_MAPPING@@@DirectUI@@$00$0A@@DirectUI@@QEAAJPEAPEAU_HINST_MAPPING@@@Z; DirectUI::DynamicArrayBase<_HINST_MAPPING,DirectUI::DoubleAllocationPolicy<_HINST_MAPPING>,1,0>::AddPtr(_HINST_MAPPING * *)
0x180024609  mov     edi, eax
0x18002460b  test    eax, eax
0x18002460d  js      short loc_180024620
0x18002460f  mov     rcx, [rsp+48h+arg_0]
0x180024614  mov     rax, [rsi]
0x180024617  mov     [rcx+8], rax
0x18002461b  mov     [rcx], rbx
0x18002461e  jmp     short loc_18002465D
0x180024620  call    cs:__imp_GetProcessHeap
0x180024627  nop     dword ptr [rax+rax+00h]
0x18002462c  mov     r8, rbx; lpMem
0x18002462f  xor     edx, edx; dwFlags
0x180024631  mov     rcx, rax; hHeap
0x180024634  call    cs:__imp_HeapFree
0x18002463b  nop     dword ptr [rax+rax+00h]
0x180024640  jmp     short loc_180024647
0x180024642  mov     edi, 80070216h
0x180024647  mov     rcx, [rsi]; hLibModule
0x18002464a  call    cs:__imp_FreeLibrary
0x180024651  nop     dword ptr [rax+rax+00h]
0x180024656  mov     qword ptr [rsi], 0
0x18002465d  mov     rbx, [rsp+48h+arg_8]
0x180024662  xor     eax, eax
0x180024664  cmp     [rsi], rax
0x180024667  mov     rbp, [rsp+48h+arg_10]
0x18002466c  cmovz   eax, edi
0x18002466f  add     rsp, 20h
0x180024673  pop     r15
0x180024675  pop     r14
0x180024677  pop     r12
0x180024679  pop     rdi
0x18002467a  pop     rsi
0x18002467b  retn
```

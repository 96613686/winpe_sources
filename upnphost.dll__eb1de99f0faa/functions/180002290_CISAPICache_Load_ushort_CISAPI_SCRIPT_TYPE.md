# CISAPICache::Load(ushort *,CISAPI * *,SCRIPT_TYPE)

- ea: `0x180002290`
- end: `0x18000254a`
- name: `?Load@CISAPICache@@QEAAPEAUHINSTANCE__@@PEAGPEAPEAVCISAPI@@W4SCRIPT_TYPE@@@Z`
- size: `698`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180001f50`

## callees

- `0x180001da8`
- `0x180002290`
- `0x180006168`
- `0x1800062a8`
- `0x1800071fc`
- `0x180039388`
- `0x18003a560`
- `0x18003ae80`
- `0x180043124`
- `0x18004317c`
- `0x18004f3d8`
- `0x18005430c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800023ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800023ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002386`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002386`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002509`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800023a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800024eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800022e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800022e0`

## string_xrefs

- `0x18000233e`: `\udhisapi.dll`

## pseudocode

```c
__int64 __fastcall CISAPICache::Load(__int64 a1, __int64 a2, CISAPI **a3)
{
  size_t v6; // r9
  __int64 v7; // rbp
  __int64 v8; // rax
  size_t *v9; // r8
  CISAPI **v11; // rdi
  CISAPI *v12; // rax
  unsigned int v13; // edx
  CISAPI *v14; // rbx
  _WORD *v15; // rax
  _WORD *v16; // r14
  void *v17; // rcx
  size_t v18; // [rsp+20h] [rbp-278h]
  size_t pcchDestLength[2]; // [rsp+30h] [rbp-268h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-258h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( (int)GetSystemDirectoryW(Buffer, 0x104u) <= 0 )
    return 0;
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( Buffer[v8] );
  if ( (unsigned __int64)(v8 + 13) >= 0x104 )
    return 0;
  pcchDestLength[0] = 0;
  if ( StringValidateDestAndLengthW(Buffer, 0x104u, pcchDestLength, v6) < 0
    || StringCopyWorkerW(&Buffer[pcchDestLength[0]], 260 - pcchDestLength[0], v9, L"\\udhisapi.dll", v18) < 0 )
  {
    return 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v11 = *(CISAPI ***)a1;
  if ( !*(_QWORD *)a1 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids, a2);
    }
    v11 = (CISAPI **)svsutil_Alloc(16, g_pvAllocData);
    if ( v11 )
    {
      v12 = (CISAPI *)malloc(0x40u);
      v14 = v12;
      if ( v12 )
      {
        memset_0(v12, 0, 0x40u);
        *(_DWORD *)v14 = 1;
        *v11 = v14;
        do
          ++v7;
        while ( Buffer[v7] );
        v15 = (_WORD *)svsutil_Alloc((unsigned int)(2 * v7 + 2), g_pvAllocData);
        v16 = v15;
        if ( v15 )
        {
          memcpy_0(v15, Buffer, 2LL * (int)v7);
          v16[(int)v7] = 0;
          *((_QWORD *)*v11 + 5) = v16;
          if ( (unsigned int)CISAPI::Load(*v11, Buffer) )
          {
            v11[1] = *(CISAPI **)a1;
            *(_QWORD *)a1 = v11;
            goto LABEL_9;
          }
        }
        else
        {
          *((_QWORD *)*v11 + 5) = 0;
        }
      }
      else
      {
        *v11 = 0;
      }
      if ( *v11 )
      {
        v17 = (void *)*((_QWORD *)*v11 + 5);
        if ( v17 )
        {
          svsutil_Free(v17);
          *((_QWORD *)*v11 + 5) = 0;
        }
        if ( *v11 )
          CISAPI::`scalar deleting destructor'(*v11, v13);
      }
      svsutil_Free(v11);
    }
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      GetLastError();
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2));
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    return 0;
  }
LABEL_9:
  ++*((_DWORD *)*v11 + 12);
  *a3 = *v11;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return *((_QWORD *)*v11 + 1);
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_18], rbx
0x180002295  push    rbp
0x180002296  push    rsi
0x180002297  push    rdi
0x180002298  push    r12
0x18000229a  push    r13
0x18000229c  push    r14
0x18000229e  push    r15
0x1800022a0  sub     rsp, 260h
0x1800022a7  mov     rax, cs:__security_cookie
0x1800022ae  xor     rax, rsp
0x1800022b1  mov     [rsp+298h+var_48], rax
0x1800022b9  mov     r12, r8
0x1800022bc  mov     r14, rdx
0x1800022bf  mov     r15, rcx
0x1800022c2  xor     edx, edx; Val
0x1800022c4  mov     r8d, 208h; Size
0x1800022ca  lea     rcx, [rsp+298h+Buffer]; void *
0x1800022cf  call    memset_0
0x1800022d4  mov     ebx, 104h
0x1800022d9  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x1800022de  mov     edx, ebx; uSize
0x1800022e0  call    cs:__imp_GetSystemDirectoryW
0x1800022e6  test    eax, eax
0x1800022e8  jle     short loc_180002355
0x1800022ea  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800022f1  lea     rcx, [rsp+298h+Buffer]
0x1800022f6  mov     rax, rbp
0x1800022f9  nop     dword ptr [rax+00000000h]
0x180002300  inc     rax
0x180002303  cmp     word ptr [rcx+rax*2], 0
0x180002308  jnz     short loc_180002300
0x18000230a  add     rax, 0Dh
0x18000230e  cmp     rax, rbx
0x180002311  jnb     short loc_180002355
0x180002313  xor     r13d, r13d
0x180002316  lea     r8, [rsp+298h+pcchDestLength]; pcchDestLength
0x18000231b  mov     rdx, rbx; cchDest
0x18000231e  mov     [rsp+298h+pcchDestLength], r13
0x180002323  lea     rcx, [rsp+298h+Buffer]; pszDest
0x180002328  call    StringValidateDestAndLengthW
0x18000232d  test    eax, eax
0x18000232f  js      short loc_180002355
0x180002331  mov     rax, [rsp+298h+pcchDestLength]
0x180002336  lea     rcx, [rsp+298h+Buffer]
0x18000233b  sub     rbx, rax
0x18000233e  lea     r9, aUdhisapiDll; "\\udhisapi.dll"
0x180002345  mov     rdx, rbx; cchDest
0x180002348  lea     rcx, [rcx+rax*2]; pszDest
0x18000234c  call    StringCopyWorkerW
0x180002351  test    eax, eax
0x180002353  jns     short loc_180002382
0x180002355  xor     eax, eax
0x180002357  mov     rcx, [rsp+298h+var_48]
0x18000235f  xor     rcx, rsp; StackCookie
0x180002362  call    __security_check_cookie
0x180002367  mov     rbx, [rsp+298h+arg_18]
0x18000236f  add     rsp, 260h
0x180002376  pop     r15
0x180002378  pop     r14
0x18000237a  pop     r13
0x18000237c  pop     r12
0x18000237e  pop     rdi
0x18000237f  pop     rsi
0x180002380  pop     rbp
0x180002381  retn
0x180002382  lea     rcx, [r15+8]; lpCriticalSection
0x180002386  call    cs:__imp_EnterCriticalSection
0x18000238c  mov     rdi, [r15]
0x18000238f  test    rdi, rdi
0x180002392  jz      short loc_1800023B4
0x180002394  mov     rax, [rdi]
0x180002397  lea     rcx, [r15+8]; lpCriticalSection
0x18000239b  inc     dword ptr [rax+30h]
0x18000239e  mov     rax, [rdi]
0x1800023a1  mov     [r12], rax
0x1800023a5  call    cs:__imp_LeaveCriticalSection
0x1800023ab  mov     rax, [rdi]
0x1800023ae  mov     rax, [rax+8]
0x1800023b2  jmp     short loc_180002357
0x1800023b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023bb  lea     rax, WPP_GLOBAL_Control
0x1800023c2  cmp     rcx, rax
0x1800023c5  jnz     loc_180002520
0x1800023cb  mov     rdx, cs:g_pvAllocData
0x1800023d2  mov     ecx, 10h
0x1800023d7  call    svsutil_Alloc
0x1800023dc  mov     rdi, rax
0x1800023df  test    rax, rax
0x1800023e2  jz      loc_1800024CF
0x1800023e8  mov     ecx, 40h ; '@'; Size
0x1800023ed  call    cs:__imp_malloc
0x1800023f3  mov     rbx, rax
0x1800023f6  test    rax, rax
0x1800023f9  jz      loc_18000248C
0x1800023ff  xor     edx, edx; Val
0x180002401  mov     r8d, 40h ; '@'; Size
0x180002407  mov     rcx, rax; void *
0x18000240a  call    memset_0
0x18000240f  mov     dword ptr [rbx], 1
0x180002415  lea     rax, [rsp+298h+Buffer]
0x18000241a  mov     [rdi], rbx
0x18000241d  nop     dword ptr [rax]
0x180002420  inc     rbp
0x180002423  cmp     [rax+rbp*2], r13w
0x180002428  jnz     short loc_180002420
0x18000242a  mov     rdx, cs:g_pvAllocData
0x180002431  lea     ecx, ds:2[rbp*2]
0x180002438  call    svsutil_Alloc
0x18000243d  mov     r14, rax
0x180002440  test    rax, rax
0x180002443  jz      loc_180002514
0x180002449  movsxd  rcx, ebp
0x18000244c  lea     rdx, [rsp+298h+Buffer]; Src
0x180002451  lea     rbx, [rcx+rcx]
0x180002455  mov     rcx, rax; void *
0x180002458  mov     r8, rbx; Size
0x18000245b  call    memcpy_0
0x180002460  mov     [rbx+r14], r13w
0x180002465  lea     rdx, [rsp+298h+Buffer]; unsigned __int16 *
0x18000246a  mov     rcx, [rdi]
0x18000246d  mov     [rcx+28h], r14
0x180002471  mov     rcx, [rdi]; this
0x180002474  call    ?Load@CISAPI@@QEAAHPEAG@Z; CISAPI::Load(ushort *)
0x180002479  test    eax, eax
0x18000247b  jz      short loc_18000248F
0x18000247d  mov     rax, [r15]
0x180002480  mov     [rdi+8], rax
0x180002484  mov     [r15], rdi
0x180002487  jmp     loc_180002394
0x18000248c  mov     [rdi], r13
0x18000248f  mov     rax, [rdi]
0x180002492  test    rax, rax
0x180002495  jz      short loc_1800024C0
0x180002497  mov     rcx, [rax+28h]; Block
0x18000249b  test    rcx, rcx
0x18000249e  jz      short loc_1800024B3
0x1800024a0  mov     rdx, cs:g_pvFreeData
0x1800024a7  call    svsutil_Free
0x1800024ac  mov     rax, [rdi]
0x1800024af  mov     [rax+28h], r13
0x1800024b3  mov     rcx, [rdi]; this
0x1800024b6  test    rcx, rcx
0x1800024b9  jz      short loc_1800024C0
0x1800024bb  call    ??_GCISAPI@@QEAAPEAXI@Z; CISAPI::`scalar deleting destructor'(uint)
0x1800024c0  mov     rdx, cs:g_pvFreeData
0x1800024c7  mov     rcx, rdi; Block
0x1800024ca  call    svsutil_Free
0x1800024cf  mov     rax, cs:WPP_GLOBAL_Control
0x1800024d6  lea     rcx, WPP_GLOBAL_Control
0x1800024dd  cmp     rax, rcx
0x1800024e0  jz      short loc_180002505
0x1800024e2  test    dword ptr [rax+1Ch], 1000h
0x1800024e9  jz      short loc_180002505
0x1800024eb  call    cs:__imp_GetLastError
0x1800024f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800024f8  mov     dword ptr [rsp+298h+var_278], eax
0x1800024fc  mov     rcx, [rcx+10h]
0x180002500  call    WPP_SF_dD
0x180002505  lea     rcx, [r15+8]; lpCriticalSection
0x180002509  call    cs:__imp_LeaveCriticalSection
0x18000250f  jmp     loc_180002355
0x180002514  mov     rax, [rdi]
0x180002517  mov     [rax+28h], r14
0x18000251b  jmp     loc_18000248F
0x180002520  test    dword ptr [rcx+1Ch], 1000h
0x180002527  jz      loc_1800023CB
0x18000252d  mov     rcx, [rcx+10h]
0x180002531  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180002538  mov     edx, 10h
0x18000253d  mov     r9, r14
0x180002540  call    WPP_SF_S
0x180002545  jmp     loc_1800023CB
```

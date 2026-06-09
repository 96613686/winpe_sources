# CISAPICache::Load(ushort *,CISAPI * *,SCRIPT_TYPE)

- ea: `0x180016d20`
- end: `0x180016f99`
- name: `?Load@CISAPICache@@QEAAPEAUHINSTANCE__@@PEAGPEAPEAVCISAPI@@W4SCRIPT_TYPE@@@Z`
- size: `633`
- prototype: `__int64 __fastcall(__int64, __int64, CISAPI **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800169b0`

## callees

- `0x18001658c`
- `0x1800167e8`
- `0x180016d20`
- `0x180018a4c`
- `0x18001aea8`
- `0x18001b240`
- `0x18003b904`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180045b90`
- `0x180045be8`
- `0x180052988`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016e7f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180016e7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e0d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016e0d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016e31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016f5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016d6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180016d6b`

## string_xrefs

- `0x180016dcd`: `\udhisapi.dll`

## pseudocode

```c
__int64 __fastcall CISAPICache::Load(__int64 a1, __int64 a2, CISAPI **a3)
{
  size_t v6; // r9
  __int64 v7; // rax
  size_t *v8; // r8
  CISAPI **v10; // rbx
  CISAPI *v11; // rax
  unsigned int v12; // edx
  CISAPI *v13; // rsi
  int v14; // edx
  unsigned __int16 *v15; // rax
  void *v16; // rcx
  size_t v17; // [rsp+20h] [rbp-278h]
  size_t pcchDestLength[2]; // [rsp+30h] [rbp-268h] BYREF
  wchar_t Buffer[264]; // [rsp+40h] [rbp-258h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( (int)GetSystemDirectoryW(Buffer, 0x104u) <= 0 )
    return 0;
  v7 = -1;
  do
    ++v7;
  while ( Buffer[v7] );
  if ( (unsigned __int64)(v7 + 13) >= 0x104 )
    return 0;
  pcchDestLength[0] = 0;
  if ( StringValidateDestAndLengthW(Buffer, 0x104u, pcchDestLength, v6) < 0
    || StringCopyWorkerW(&Buffer[pcchDestLength[0]], 260 - pcchDestLength[0], v8, L"\\udhisapi.dll", v17) < 0 )
  {
    return 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v10 = *(CISAPI ***)a1;
  if ( !*(_QWORD *)a1 )
  {
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids, a2);
    }
    v10 = (CISAPI **)svsutil_Alloc(16, g_pvAllocData);
    if ( v10 )
    {
      v11 = (CISAPI *)malloc(0x40u);
      v13 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, 0x40u);
        *(_DWORD *)v13 = 1;
        *v10 = v13;
        v15 = MySzDupW(Buffer, v14);
        *((_QWORD *)*v10 + 5) = v15;
        if ( v15 && (unsigned int)CISAPI::Load(*v10, Buffer) )
        {
          v10[1] = *(CISAPI **)a1;
          *(_QWORD *)a1 = v10;
          goto LABEL_9;
        }
      }
      else
      {
        *v10 = 0;
      }
      if ( *v10 )
      {
        v16 = (void *)*((_QWORD *)*v10 + 5);
        if ( v16 )
        {
          svsutil_Free(v16);
          *((_QWORD *)*v10 + 5) = 0;
        }
        if ( *v10 )
          CISAPI::`scalar deleting destructor'(*v10, v12);
      }
      svsutil_Free(v10);
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
  ++*((_DWORD *)*v10 + 12);
  *a3 = *v10;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return *((_QWORD *)*v10 + 1);
}

```

## disassembly

```asm
0x180016d20  push    rbx
0x180016d22  push    rbp
0x180016d23  push    rsi
0x180016d24  push    rdi
0x180016d25  push    r12
0x180016d27  push    r14
0x180016d29  push    r15
0x180016d2b  sub     rsp, 260h
0x180016d32  mov     rax, cs:__security_cookie
0x180016d39  xor     rax, rsp
0x180016d3c  mov     [rsp+298h+var_48], rax
0x180016d44  mov     r15, r8
0x180016d47  mov     rsi, rdx
0x180016d4a  mov     r14, rcx
0x180016d4d  xor     edx, edx; Val
0x180016d4f  mov     r8d, 208h; Size
0x180016d55  lea     rcx, [rsp+298h+Buffer]; void *
0x180016d5a  call    memset_0
0x180016d5f  mov     ebx, 104h
0x180016d64  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x180016d69  mov     edx, ebx; uSize
0x180016d6b  call    cs:__imp_GetSystemDirectoryW
0x180016d72  nop     dword ptr [rax+rax+00h]
0x180016d77  test    eax, eax
0x180016d79  jle     short loc_180016DE4
0x180016d7b  lea     rcx, [rsp+298h+Buffer]
0x180016d80  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180016d87  nop     word ptr [rax+rax+00000000h]
0x180016d90  inc     rax
0x180016d93  cmp     word ptr [rcx+rax*2], 0
0x180016d98  jnz     short loc_180016D90
0x180016d9a  add     rax, 0Dh
0x180016d9e  cmp     rax, rbx
0x180016da1  jnb     short loc_180016DE4
0x180016da3  xor     ebp, ebp
0x180016da5  lea     r8, [rsp+298h+pcchDestLength]; pcchDestLength
0x180016daa  mov     rdx, rbx; cchDest
0x180016dad  mov     [rsp+298h+pcchDestLength], rbp
0x180016db2  lea     rcx, [rsp+298h+Buffer]; pszDest
0x180016db7  call    StringValidateDestAndLengthW
0x180016dbc  test    eax, eax
0x180016dbe  js      short loc_180016DE4
0x180016dc0  mov     rax, [rsp+298h+pcchDestLength]
0x180016dc5  lea     rcx, [rsp+298h+Buffer]
0x180016dca  sub     rbx, rax
0x180016dcd  lea     r9, aUdhisapiDll; "\\udhisapi.dll"
0x180016dd4  mov     rdx, rbx; cchDest
0x180016dd7  lea     rcx, [rcx+rax*2]; pszDest
0x180016ddb  call    StringCopyWorkerW
0x180016de0  test    eax, eax
0x180016de2  jns     short loc_180016E09
0x180016de4  xor     eax, eax
0x180016de6  mov     rcx, [rsp+298h+var_48]
0x180016dee  xor     rcx, rsp; StackCookie
0x180016df1  call    __security_check_cookie
0x180016df6  add     rsp, 260h
0x180016dfd  pop     r15
0x180016dff  pop     r14
0x180016e01  pop     r12
0x180016e03  pop     rdi
0x180016e04  pop     rsi
0x180016e05  pop     rbp
0x180016e06  pop     rbx
0x180016e07  retn
0x180016e09  lea     rcx, [r14+8]; lpCriticalSection
0x180016e0d  call    cs:__imp_EnterCriticalSection
0x180016e14  nop     dword ptr [rax+rax+00h]
0x180016e19  mov     rbx, [r14]
0x180016e1c  test    rbx, rbx
0x180016e1f  jz      short loc_180016E46
0x180016e21  mov     rax, [rbx]
0x180016e24  lea     rcx, [r14+8]; lpCriticalSection
0x180016e28  inc     dword ptr [rax+30h]
0x180016e2b  mov     rax, [rbx]
0x180016e2e  mov     [r15], rax
0x180016e31  call    cs:__imp_LeaveCriticalSection
0x180016e38  nop     dword ptr [rax+rax+00h]
0x180016e3d  mov     rax, [rbx]
0x180016e40  mov     rax, [rax+8]
0x180016e44  jmp     short loc_180016DE6
0x180016e46  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e4d  lea     r12, WPP_GLOBAL_Control
0x180016e54  cmp     rcx, r12
0x180016e57  jnz     loc_180016F6F
0x180016e5d  mov     rdx, cs:g_pvAllocData
0x180016e64  mov     ecx, 10h
0x180016e69  call    svsutil_Alloc
0x180016e6e  mov     rbx, rax
0x180016e71  test    rax, rax
0x180016e74  jz      loc_180016F25
0x180016e7a  mov     ecx, 40h ; '@'; Size
0x180016e7f  call    cs:__imp_malloc
0x180016e86  nop     dword ptr [rax+rax+00h]
0x180016e8b  mov     rsi, rax
0x180016e8e  test    rax, rax
0x180016e91  jz      short loc_180016EE2
0x180016e93  xor     edx, edx; Val
0x180016e95  mov     r8d, 40h ; '@'; Size
0x180016e9b  mov     rcx, rax; void *
0x180016e9e  call    memset_0
0x180016ea3  mov     dword ptr [rsi], 1
0x180016ea9  lea     rcx, [rsp+298h+Buffer]; Src
0x180016eae  mov     [rbx], rsi
0x180016eb1  call    ?MySzDupW@@YAPEAGPEBGH@Z; MySzDupW(ushort const *,int)
0x180016eb6  mov     rcx, [rbx]
0x180016eb9  mov     [rcx+28h], rax
0x180016ebd  test    rax, rax
0x180016ec0  jz      short loc_180016EE5
0x180016ec2  mov     rcx, [rbx]; this
0x180016ec5  lea     rdx, [rsp+298h+Buffer]; unsigned __int16 *
0x180016eca  call    ?Load@CISAPI@@QEAAHPEAG@Z; CISAPI::Load(ushort *)
0x180016ecf  test    eax, eax
0x180016ed1  jz      short loc_180016EE5
0x180016ed3  mov     rax, [r14]
0x180016ed6  mov     [rbx+8], rax
0x180016eda  mov     [r14], rbx
0x180016edd  jmp     loc_180016E21
0x180016ee2  mov     [rbx], rbp
0x180016ee5  mov     rax, [rbx]
0x180016ee8  test    rax, rax
0x180016eeb  jz      short loc_180016F16
0x180016eed  mov     rcx, [rax+28h]; Block
0x180016ef1  test    rcx, rcx
0x180016ef4  jz      short loc_180016F09
0x180016ef6  mov     rdx, cs:g_pvFreeData
0x180016efd  call    svsutil_Free
0x180016f02  mov     rax, [rbx]
0x180016f05  mov     [rax+28h], rbp
0x180016f09  mov     rcx, [rbx]; this
0x180016f0c  test    rcx, rcx
0x180016f0f  jz      short loc_180016F16
0x180016f11  call    ??_GCISAPI@@QEAAPEAXI@Z; CISAPI::`scalar deleting destructor'(uint)
0x180016f16  mov     rdx, cs:g_pvFreeData
0x180016f1d  mov     rcx, rbx; Block
0x180016f20  call    svsutil_Free
0x180016f25  mov     rax, cs:WPP_GLOBAL_Control
0x180016f2c  cmp     rax, r12
0x180016f2f  jz      short loc_180016F5A
0x180016f31  test    dword ptr [rax+1Ch], 1000h
0x180016f38  jz      short loc_180016F5A
0x180016f3a  call    cs:__imp_GetLastError
0x180016f41  nop     dword ptr [rax+rax+00h]
0x180016f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f4d  mov     dword ptr [rsp+298h+var_278], eax
0x180016f51  mov     rcx, [rcx+10h]
0x180016f55  call    WPP_SF_dD
0x180016f5a  lea     rcx, [r14+8]; lpCriticalSection
0x180016f5e  call    cs:__imp_LeaveCriticalSection
0x180016f65  nop     dword ptr [rax+rax+00h]
0x180016f6a  jmp     loc_180016DE4
0x180016f6f  test    dword ptr [rcx+1Ch], 1000h
0x180016f76  jz      loc_180016E5D
0x180016f7c  mov     rcx, [rcx+10h]
0x180016f80  lea     r8, WPP_a551daa9c3c83c532b1715f40d740de9_Traceguids
0x180016f87  mov     edx, 10h
0x180016f8c  mov     r9, rsi
0x180016f8f  call    WPP_SF_S
0x180016f94  jmp     loc_180016E5D
```

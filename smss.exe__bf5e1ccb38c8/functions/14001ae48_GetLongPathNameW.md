# GetLongPathNameW

- ea: `0x14001ae48`
- end: `0x14001b22f`
- name: `GetLongPathNameW`
- size: `999`
- prototype: `__int64 __fastcall(PCWSTR Name, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting`

## callers

- `0x140019a5c`

## callees

- `0x14001a090`
- `0x14001ada8`
- `0x14001ae48`
- `0x14001b298`
- `0x14001ba7c`
- `0x14001bb50`
- `0x14001c0a0`
- `0x14001cc1d`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14001af6b`
- `ntdll!RtlAllocateHeap` at `0x14001b023`
- `ntdll!RtlAllocateHeap` at `0x14001af6b`
- `ntdll!RtlAllocateHeap` at `0x14001b023`
- `ntdll!RtlFreeHeap` at `0x14001b1fd`
- `ntdll!RtlFreeHeap` at `0x14001b21a`
- `ntdll!RtlFreeHeap` at `0x14001cfda`
- `ntdll!RtlFreeHeap` at `0x14001cff9`
- `ntdll!RtlFreeHeap` at `0x14001b1fd`
- `ntdll!RtlFreeHeap` at `0x14001b21a`
- `ntdll!RtlFreeHeap` at `0x14001cfda`
- `ntdll!RtlFreeHeap` at `0x14001cff9`
- `ntdll!wcslen` at `0x14001af3e`
- `ntdll!wcslen` at `0x14001b0bf`
- `ntdll!wcslen` at `0x14001b159`
- `ntdll!wcslen` at `0x14001b1a9`
- `ntdll!wcslen` at `0x14001af3e`
- `ntdll!wcslen` at `0x14001b0bf`
- `ntdll!wcslen` at `0x14001b159`
- `ntdll!wcslen` at `0x14001b1a9`
- `ntdll!RtlSetLastWin32Error` at `0x14001aea5`
- `ntdll!RtlSetLastWin32Error` at `0x14001af83`
- `ntdll!RtlSetLastWin32Error` at `0x14001aea5`
- `ntdll!RtlSetLastWin32Error` at `0x14001af83`

## pseudocode

```c
__int64 __fastcall GetLongPathNameW(WCHAR *Name, WCHAR *a2, unsigned int a3)
{
  __int64 v3; // r14
  unsigned int v7; // edi
  void *v8; // r12
  WCHAR *v9; // r13
  unsigned int v10; // r15d
  const WCHAR *v11; // rax
  SIZE_T v12; // r15
  WCHAR *Heap; // rax
  __int64 v14; // rdx
  WCHAR *v15; // r15
  PVOID v16; // rax
  wchar_t *v17; // r14
  __int64 v18; // rax
  unsigned int v19; // edi
  size_t v20; // rbx
  wchar_t v21; // bx
  struct _RTL_CRITICAL_SECTION *FirstFile; // rax
  signed __int64 v23; // rax
  size_t v24; // rbx
  int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // [rsp+34h] [rbp-2E4h]
  wchar_t *v28; // [rsp+38h] [rbp-2E0h] BYREF
  void *Src; // [rsp+40h] [rbp-2D8h] BYREF
  unsigned int v30; // [rsp+48h] [rbp-2D0h]
  WCHAR *v31; // [rsp+50h] [rbp-2C8h]
  WCHAR *v32; // [rsp+58h] [rbp-2C0h]
  PVOID v33; // [rsp+60h] [rbp-2B8h]
  SIZE_T v34; // [rsp+68h] [rbp-2B0h]
  WCHAR *v35; // [rsp+70h] [rbp-2A8h]
  _BYTE v36[44]; // [rsp+80h] [rbp-298h] BYREF
  wchar_t Str[274]; // [rsp+ACh] [rbp-26Ch] BYREF

  v3 = a3;
  v30 = a3;
  Src = 0;
  v28 = 0;
  memset_0(v36, 0, 0x250u);
  if ( !Name )
  {
    RtlSetLastWin32Error(0x57u);
    return 0;
  }
  v7 = 0;
  v8 = 0;
  v33 = 0;
  v9 = 0;
  v32 = 0;
  v10 = SetErrorMode(32769);
  v27 = v10;
  if ( (unsigned int)InternalGetFileAttributesW(Name) != -1 )
  {
    v11 = SkipPathTypeIndicator_U(Name);
    if ( !v11 || !*v11 || !(unsigned int)FindLFNorSFN_U(v11, &Src, &v28) )
    {
      v26 = wcslen(Name);
      v7 = v26;
      if ( (unsigned int)v3 > v26 && a2 )
      {
        if ( a2 != Name )
          memmove_0(a2, Name, 2LL * (v26 + 1));
      }
      else
      {
        v7 = v26 + 1;
      }
      goto LABEL_44;
    }
    v12 = 2LL * ((unsigned int)wcslen(Name) + 1);
    v34 = v12;
    Heap = (WCHAR *)RtlAllocateHeap(
                      *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                      KernelBaseGlobalData + 0x200000,
                      v12);
    v9 = Heap;
    v32 = Heap;
    if ( !Heap )
      goto LABEL_8;
    memmove_0(Heap, Name, v12);
    Src = &v9[((_BYTE *)Src - (_BYTE *)Name) >> 1];
    v28 = &v9[v28 - Name];
    v15 = a2;
    v31 = a2;
    if ( !(_DWORD)v3 || !a2 )
      goto LABEL_17;
    if ( a2 >= Name )
    {
      if ( a2 < (WCHAR *)((char *)Name + v34) )
      {
LABEL_15:
        v16 = RtlAllocateHeap(
                *(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL),
                KernelBaseGlobalData + 0x200000,
                2 * v3);
        v8 = v16;
        v33 = v16;
        if ( !v16 )
        {
LABEL_8:
          RtlSetLastWin32Error(8u);
LABEL_43:
          v10 = v27;
          goto LABEL_44;
        }
        v15 = (WCHAR *)v16;
        v31 = (WCHAR *)v16;
LABEL_17:
        v17 = v9;
        v35 = v9;
        while ( 1 )
        {
          v18 = ((_BYTE *)Src - (_BYTE *)v17) >> 1;
          v19 = v18 + v7;
          if ( (_DWORD)v18 && v30 > v19 )
          {
            v20 = 2LL * (unsigned int)v18;
            memmove_0(v15, v17, v20);
            v15 = (WCHAR *)((char *)v15 + v20);
            v31 = v15;
          }
          v21 = *v28;
          *v28 = 0;
          FirstFile = (struct _RTL_CRITICAL_SECTION *)InternalFindFirstFileExW(v9, v14, (__int64)v36);
          *v28 = v21;
          if ( FirstFile == (struct _RTL_CRITICAL_SECTION *)-1LL )
            break;
          FindClose(FirstFile);
          LODWORD(v23) = wcslen(Str);
          if ( (_DWORD)v23 )
          {
            Src = Str;
            v17 = v28;
          }
          else
          {
            v17 = v28;
            v23 = ((char *)v28 - (_BYTE *)Src) >> 1;
          }
          v7 = v23 + v19;
          if ( v30 > v7 && a2 )
          {
            v24 = 2LL * (unsigned int)v23;
            memmove_0(v15, Src, v24);
            v15 = (WCHAR *)((char *)v15 + v24);
            v31 = v15;
          }
          v35 = v17;
          if ( !*v17 || !(unsigned int)FindLFNorSFN_U(v17, &Src, &v28) )
            goto LABEL_32;
        }
        v7 = 0;
LABEL_32:
        if ( v7 )
        {
          v25 = wcslen(v17);
          v7 += v25;
          if ( v30 > v7 && a2 )
          {
            memmove_0(v15, v17, 2LL * (unsigned int)(v25 + 1));
            if ( v8 )
              memmove_0(a2, v8, 2LL * (v7 + 1));
          }
          else
          {
            ++v7;
          }
        }
        goto LABEL_43;
      }
      if ( a2 >= Name )
        goto LABEL_17;
    }
    if ( &a2[v3] < Name )
      goto LABEL_17;
    goto LABEL_15;
  }
LABEL_44:
  if ( v9 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v9);
  if ( v8 )
    RtlFreeHeap(*(PVOID *)(*(_QWORD *)&KeGetPcr()->MajorVersion + 48LL), 0, v8);
  SetErrorMode(v10);
  return v7;
}

```

## disassembly

```asm
0x14001ae48  push    rbx
0x14001ae4a  push    rsi
0x14001ae4b  push    rdi
0x14001ae4c  push    r12
0x14001ae4e  push    r13
0x14001ae50  push    r14
0x14001ae52  push    r15
0x14001ae54  sub     rsp, 2E0h
0x14001ae5b  mov     rax, cs:__security_cookie
0x14001ae62  xor     rax, rsp
0x14001ae65  mov     [rsp+318h+var_48], rax
0x14001ae6d  mov     r14d, r8d
0x14001ae70  mov     [rsp+318h+var_2D0], r14d
0x14001ae75  mov     rsi, rdx
0x14001ae78  mov     rbx, rcx
0x14001ae7b  xor     r15d, r15d
0x14001ae7e  mov     [rsp+318h+Src], r15
0x14001ae83  mov     [rsp+318h+var_2E0], r15
0x14001ae88  xor     edx, edx; Val
0x14001ae8a  mov     r8d, 250h; Size
0x14001ae90  lea     rcx, [rsp+318h+var_298]; void *
0x14001ae98  call    memset_0
0x14001ae9d  test    rbx, rbx
0x14001aea0  jnz     short loc_14001AED0
0x14001aea2  lea     ecx, [rbx+57h]; LastError
0x14001aea5  call    cs:__imp_RtlSetLastWin32Error
0x14001aeab  xor     eax, eax
0x14001aead  mov     rcx, [rsp+318h+var_48]
0x14001aeb5  xor     rcx, rsp; StackCookie
0x14001aeb8  call    __security_check_cookie
0x14001aebd  add     rsp, 2E0h
0x14001aec4  pop     r15
0x14001aec6  pop     r14
0x14001aec8  pop     r13
0x14001aeca  pop     r12
0x14001aecc  pop     rdi
0x14001aecd  pop     rsi
0x14001aece  pop     rbx
0x14001aecf  retn
0x14001aed0  mov     edi, r15d
0x14001aed3  mov     r12, r15
0x14001aed6  mov     [rsp+318h+var_2B8], r15
0x14001aedb  mov     r13, r15
0x14001aede  mov     [rsp+318h+var_2C0], r15
0x14001aee3  mov     ecx, 8001h
0x14001aee8  call    SetErrorMode
0x14001aeed  mov     r15d, eax
0x14001aef0  mov     [rsp+318h+var_2E4], eax
0x14001aef4  mov     rcx, rbx; Name
0x14001aef7  call    InternalGetFileAttributesW
0x14001aefc  cmp     eax, 0FFFFFFFFh
0x14001aeff  jz      loc_14001B1E6
0x14001af05  mov     rcx, rbx
0x14001af08  call    SkipPathTypeIndicator_U
0x14001af0d  xor     ecx, ecx
0x14001af0f  test    rax, rax
0x14001af12  jz      loc_14001B1A6
0x14001af18  cmp     [rax], cx
0x14001af1b  jz      loc_14001B1A6
0x14001af21  lea     r8, [rsp+318h+var_2E0]
0x14001af26  lea     rdx, [rsp+318h+Src]
0x14001af2b  mov     rcx, rax
0x14001af2e  call    FindLFNorSFN_U
0x14001af33  test    eax, eax
0x14001af35  jz      loc_14001B1A6
0x14001af3b  mov     rcx, rbx; Str
0x14001af3e  call    cs:__imp_wcslen
0x14001af44  inc     eax
0x14001af46  mov     edx, cs:KernelBaseGlobalData
0x14001af4c  lea     r15, [rax+rax]
0x14001af50  mov     [rsp+318h+var_2B0], r15
0x14001af55  add     edx, 200000h; Flags
0x14001af5b  mov     rcx, gs:60h
0x14001af64  mov     r8, r15; Size
0x14001af67  mov     rcx, [rcx+30h]; HeapHandle
0x14001af6b  call    cs:__imp_RtlAllocateHeap
0x14001af71  mov     r13, rax
0x14001af74  mov     [rsp+318h+var_2C0], rax
0x14001af79  test    rax, rax
0x14001af7c  jnz     short loc_14001AF8E
0x14001af7e  mov     ecx, 8; LastError
0x14001af83  call    cs:__imp_RtlSetLastWin32Error
0x14001af89  jmp     loc_14001B1E1
0x14001af8e  mov     r8, r15; Size
0x14001af91  mov     rdx, rbx; Src
0x14001af94  mov     rcx, r13; void *
0x14001af97  call    memmove_0
0x14001af9c  mov     rax, [rsp+318h+Src]
0x14001afa1  sub     rax, rbx
0x14001afa4  sar     rax, 1
0x14001afa7  lea     rax, ds:0[rax*2]
0x14001afaf  add     rax, r13
0x14001afb2  mov     [rsp+318h+Src], rax
0x14001afb7  mov     rax, [rsp+318h+var_2E0]
0x14001afbc  sub     rax, rbx
0x14001afbf  sar     rax, 1
0x14001afc2  lea     rax, ds:0[rax*2]
0x14001afca  add     rax, r13
0x14001afcd  mov     [rsp+318h+var_2E0], rax
0x14001afd2  mov     r15, rsi
0x14001afd5  mov     [rsp+318h+var_2C8], rsi
0x14001afda  test    r14d, r14d
0x14001afdd  jz      short loc_14001B042
0x14001afdf  test    rsi, rsi
0x14001afe2  jz      short loc_14001B042
0x14001afe4  cmp     rsi, rbx
0x14001afe7  jb      short loc_14001AFFB
0x14001afe9  mov     rax, [rsp+318h+var_2B0]
0x14001afee  add     rax, rbx
0x14001aff1  cmp     rsi, rax
0x14001aff4  jb      short loc_14001B004
0x14001aff6  cmp     rsi, rbx
0x14001aff9  jnb     short loc_14001B042
0x14001affb  lea     rcx, [rsi+r14*2]
0x14001afff  cmp     rcx, rbx
0x14001b002  jb      short loc_14001B042
0x14001b004  mov     edx, cs:KernelBaseGlobalData
0x14001b00a  mov     r8, r14
0x14001b00d  add     r8, r8; Size
0x14001b010  add     edx, 200000h; Flags
0x14001b016  mov     rcx, gs:60h
0x14001b01f  mov     rcx, [rcx+30h]; HeapHandle
0x14001b023  call    cs:__imp_RtlAllocateHeap
0x14001b029  mov     r12, rax
0x14001b02c  mov     [rsp+318h+var_2B8], rax
0x14001b031  test    rax, rax
0x14001b034  jz      loc_14001AF7E
0x14001b03a  mov     r15, rax
0x14001b03d  mov     [rsp+318h+var_2C8], rax
0x14001b042  mov     r14, r13
0x14001b045  mov     [rsp+318h+var_2A8], r13
0x14001b04a  mov     rax, [rsp+318h+Src]
0x14001b04f  sub     rax, r14
0x14001b052  sar     rax, 1
0x14001b055  add     edi, eax
0x14001b057  mov     [rsp+318h+var_2E8], edi
0x14001b05b  test    eax, eax
0x14001b05d  jz      short loc_14001B080
0x14001b05f  cmp     [rsp+318h+var_2D0], edi
0x14001b063  jbe     short loc_14001B080
0x14001b065  mov     ebx, eax
0x14001b067  add     rbx, rbx
0x14001b06a  mov     r8, rbx; Size
0x14001b06d  mov     rdx, r14; Src
0x14001b070  mov     rcx, r15; void *
0x14001b073  call    memmove_0
0x14001b078  add     r15, rbx
0x14001b07b  mov     [rsp+318h+var_2C8], r15
0x14001b080  mov     rcx, [rsp+318h+var_2E0]
0x14001b085  movzx   ebx, word ptr [rcx]
0x14001b088  xor     eax, eax
0x14001b08a  mov     [rcx], ax
0x14001b08d  lea     r8, [rsp+318h+var_298]
0x14001b095  mov     rcx, r13; DosName
0x14001b098  call    InternalFindFirstFileExW
0x14001b09d  mov     rcx, [rsp+318h+var_2E0]
0x14001b0a2  mov     [rcx], bx
0x14001b0a5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001b0a9  jz      loc_14001B146
0x14001b0af  mov     rcx, rax; BaseAddress
0x14001b0b2  call    FindClose
0x14001b0b7  lea     rcx, [rsp+318h+Str]; Str
0x14001b0bf  call    cs:__imp_wcslen
0x14001b0c5  xor     ebx, ebx
0x14001b0c7  test    eax, eax
0x14001b0c9  jnz     short loc_14001B0DD
0x14001b0cb  mov     r14, [rsp+318h+var_2E0]
0x14001b0d0  mov     rax, r14
0x14001b0d3  sub     rax, [rsp+318h+Src]
0x14001b0d8  sar     rax, 1
0x14001b0db  jmp     short loc_14001B0EF
0x14001b0dd  lea     rcx, [rsp+318h+Str]
0x14001b0e5  mov     [rsp+318h+Src], rcx
0x14001b0ea  mov     r14, [rsp+318h+var_2E0]
0x14001b0ef  add     edi, eax
0x14001b0f1  mov     [rsp+318h+var_2E8], edi
0x14001b0f5  cmp     [rsp+318h+var_2D0], edi
0x14001b0f9  jbe     short loc_14001B11F
0x14001b0fb  test    rsi, rsi
0x14001b0fe  jz      short loc_14001B11F
0x14001b100  mov     ebx, eax
0x14001b102  add     rbx, rbx
0x14001b105  mov     r8, rbx; Size
0x14001b108  mov     rdx, [rsp+318h+Src]; Src
0x14001b10d  mov     rcx, r15; void *
0x14001b110  call    memmove_0
0x14001b115  add     r15, rbx
0x14001b118  mov     [rsp+318h+var_2C8], r15
0x14001b11d  xor     ebx, ebx
0x14001b11f  mov     [rsp+318h+var_2A8], r14
0x14001b124  cmp     [r14], bx
0x14001b128  jz      short loc_14001B14E
0x14001b12a  lea     r8, [rsp+318h+var_2E0]
0x14001b12f  lea     rdx, [rsp+318h+Src]
0x14001b134  mov     rcx, r14
0x14001b137  call    FindLFNorSFN_U
0x14001b13c  test    eax, eax
0x14001b13e  jnz     loc_14001B04A
0x14001b144  jmp     short loc_14001B14E
0x14001b146  xor     ebx, ebx
0x14001b148  mov     edi, ebx
0x14001b14a  mov     [rsp+318h+var_2E8], ebx
0x14001b14e  test    edi, edi
0x14001b150  jz      loc_14001B1E1
0x14001b156  mov     rcx, r14; Str
0x14001b159  call    cs:__imp_wcslen
0x14001b15f  add     edi, eax
0x14001b161  mov     [rsp+318h+var_2E8], edi
0x14001b165  cmp     [rsp+318h+var_2D0], edi
0x14001b169  jbe     short loc_14001B19E
0x14001b16b  test    rsi, rsi
0x14001b16e  jz      short loc_14001B19E
0x14001b170  inc     eax
0x14001b172  mov     r8d, eax
0x14001b175  add     r8, r8; Size
0x14001b178  mov     rdx, r14; Src
0x14001b17b  mov     rcx, r15; void *
0x14001b17e  call    memmove_0
0x14001b183  test    r12, r12
0x14001b186  jz      short loc_14001B1E1
0x14001b188  lea     eax, [rdi+1]
0x14001b18b  mov     r8d, eax
0x14001b18e  add     r8, r8; Size
0x14001b191  mov     rdx, r12; Src
0x14001b194  mov     rcx, rsi; void *
0x14001b197  call    memmove_0
0x14001b19c  jmp     short loc_14001B1E1
0x14001b19e  inc     edi
0x14001b1a0  mov     [rsp+318h+var_2E8], edi
0x14001b1a4  jmp     short loc_14001B1E1
0x14001b1a6  mov     rcx, rbx; Str
0x14001b1a9  call    cs:__imp_wcslen
0x14001b1af  mov     rdi, rax
0x14001b1b2  mov     [rsp+318h+var_2E8], edi
0x14001b1b6  cmp     r14d, eax
0x14001b1b9  jbe     short loc_14001B1D9
0x14001b1bb  test    rsi, rsi
0x14001b1be  jz      short loc_14001B1D9
0x14001b1c0  cmp     rsi, rbx
0x14001b1c3  jz      short loc_14001B1E6
0x14001b1c5  lea     r8d, [rax+1]
0x14001b1c9  add     r8, r8; Size
0x14001b1cc  mov     rdx, rbx; Src
0x14001b1cf  mov     rcx, rsi; void *
0x14001b1d2  call    memmove_0
0x14001b1d7  jmp     short loc_14001B1E6
0x14001b1d9  inc     edi
0x14001b1db  mov     [rsp+318h+var_2E8], edi
0x14001b1df  jmp     short loc_14001B1E6
0x14001b1e1  mov     r15d, [rsp+318h+var_2E4]
0x14001b1e6  test    r13, r13
0x14001b1e9  jz      short loc_14001B203
0x14001b1eb  mov     rcx, gs:60h
0x14001b1f4  mov     r8, r13; BaseAddress
0x14001b1f7  xor     edx, edx; Flags
0x14001b1f9  mov     rcx, [rcx+30h]; HeapHandle
0x14001b1fd  call    cs:__imp_RtlFreeHeap
0x14001b203  test    r12, r12
0x14001b206  jz      short loc_14001B220
0x14001b208  mov     rcx, gs:60h
0x14001b211  mov     r8, r12; BaseAddress
0x14001b214  xor     edx, edx; Flags
0x14001b216  mov     rcx, [rcx+30h]; HeapHandle
0x14001b21a  call    cs:__imp_RtlFreeHeap
0x14001b220  mov     ecx, r15d
0x14001b223  call    SetErrorMode
0x14001b228  mov     eax, edi
0x14001b22a  jmp     loc_14001AEAD
0x14001cfb9  push    rbp
0x14001cfbb  sub     rsp, 30h
0x14001cfbf  mov     rbp, rdx
0x14001cfc2  mov     r8, [rbp+58h]; BaseAddress
0x14001cfc6  test    r8, r8
0x14001cfc9  jz      short loc_14001CFE1
0x14001cfcb  mov     rcx, gs:60h
0x14001cfd4  xor     edx, edx; Flags
0x14001cfd6  mov     rcx, [rcx+30h]; HeapHandle
0x14001cfda  call    cs:__imp_RtlFreeHeap
0x14001cfe0  nop
0x14001cfe1  mov     r8, [rbp+60h]; BaseAddress
0x14001cfe5  test    r8, r8
0x14001cfe8  jz      short loc_14001D000
0x14001cfea  mov     rcx, gs:60h
0x14001cff3  xor     edx, edx; Flags
0x14001cff5  mov     rcx, [rcx+30h]; HeapHandle
0x14001cff9  call    cs:__imp_RtlFreeHeap
0x14001cfff  nop
0x14001d000  add     rsp, 30h
0x14001d004  pop     rbp
0x14001d005  retn
```

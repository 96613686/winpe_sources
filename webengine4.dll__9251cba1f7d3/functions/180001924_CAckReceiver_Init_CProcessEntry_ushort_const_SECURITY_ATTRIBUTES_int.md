# CAckReceiver::Init(CProcessEntry *,ushort const *,_SECURITY_ATTRIBUTES *,int)

- ea: `0x180001924`
- end: `0x180001c00`
- name: `?Init@CAckReceiver@@QEAAJPEAVCProcessEntry@@PEBGPEAU_SECURITY_ATTRIBUTES@@H@Z`
- size: `732`
- prototype: `__int64 __fastcall(CAckReceiver *this, struct CProcessEntry *, char *, struct _SECURITY_ATTRIBUTES *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001dc88`

## callees

- `0x180001924`
- `0x180049810`
- `0x18004d030`
- `0x18004d350`
- `0x18004d690`
- `0x18004d6c8`

## import_xrefs

- `KERNEL32!CreateNamedPipeW` at `0x180001b8b`
- `KERNEL32!CreateNamedPipeW` at `0x180001b8b`
- `KERNEL32!InitializeCriticalSection` at `0x1800019e5`
- `KERNEL32!InitializeCriticalSection` at `0x1800019e5`
- `KERNEL32!lstrlenW` at `0x18000198a`
- `KERNEL32!lstrlenW` at `0x180001b24`
- `KERNEL32!lstrlenW` at `0x18000198a`
- `KERNEL32!lstrlenW` at `0x180001b24`
- `ucrtbase_clr0400!_itow_s` at `0x180001b57`
- `ucrtbase_clr0400!_itow_s` at `0x180001b57`

## pseudocode

```c
__int64 __fastcall CAckReceiver::Init(
        CAckReceiver *this,
        struct CProcessEntry *a2,
        char *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        int a5)
{
  __int64 v5; // r15
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // r13
  __int64 v10; // rax
  bool v11; // cf
  unsigned __int64 v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // r14
  _QWORD *v15; // rsi
  unsigned int v16; // ebx
  void *v17; // rax
  void *v18; // rax
  void *v19; // rax
  __int64 v20; // rsi
  __int64 v21; // r14
  WCHAR *v22; // rcx
  __int64 v23; // rdx
  WCHAR v24; // ax
  WCHAR *v25; // rax
  int v26; // eax
  HANDLE NamedPipeW; // rax
  WCHAR String[264]; // [rsp+50h] [rbp-258h] BYREF

  LODWORD(v5) = 0;
  lpSecurityAttributes = a4;
  if ( a2 && a3 && a5 >= 1 && lstrlenW((LPCWSTR)a3) <= 248 )
  {
    *((_QWORD *)this + 4) = a2;
    v10 = 56LL * a5;
    if ( !is_mul_ok(a5, 0x38u) )
      v10 = -1;
    v11 = __CFADD__(v10, 8);
    v12 = v10 + 8;
    if ( v11 )
      v12 = -1;
    v13 = MemAlloc(v12);
    if ( v13 )
    {
      v14 = v13 + 1;
      *v13 = a5;
      v15 = v13 + 1;
      v5 = a5;
      do
      {
        *v15 = -1;
        *((_DWORD *)v15 + 12) = 1;
        InitializeCriticalSection((LPCRITICAL_SECTION)(v15 + 1));
        v15 += 7;
        --v5;
      }
      while ( v5 );
      lpSecurityAttributes = a4;
    }
    else
    {
      v14 = 0;
    }
    *((_QWORD *)this + 2) = v14;
    if ( v14 )
    {
      v17 = MemAllocClear(saturated_mul(a5, 0x38u));
      *((_QWORD *)this + 3) = v17;
      if ( v17 )
      {
        v18 = MemAllocClear(saturated_mul(a5, 4u));
        *((_QWORD *)this + 5) = v18;
        if ( v18 )
        {
          v19 = MemAllocClear(saturated_mul(a5, 8u));
          *((_QWORD *)this + 6) = v19;
          if ( v19 )
          {
            v20 = 0;
            v21 = 0;
            while ( 1 )
            {
              *(_DWORD *)(*((_QWORD *)this + 3) + v21 + 48) = v5;
              *(_QWORD *)(*((_QWORD *)this + 3) + v21 + 32) = this;
              *(_DWORD *)(*((_QWORD *)this + 5) + 4 * v20) = 1024;
              *(_QWORD *)(*((_QWORD *)this + 6) + 8 * v20) = MemAllocClear(*(unsigned int *)(*((_QWORD *)this + 5)
                                                                                           + 4 * v20));
              if ( !*(_QWORD *)(*((_QWORD *)this + 6) + 8 * v20) )
                break;
              v22 = String;
              v23 = 260;
              do
              {
                if ( v23 == -2147483386 )
                  break;
                v24 = *(WCHAR *)((char *)v22 + a3 - (char *)String);
                if ( !v24 )
                  break;
                *v22++ = v24;
                --v23;
              }
              while ( v23 );
              v25 = v22 - 1;
              if ( v23 )
                v25 = v22;
              *v25 = 0;
              v16 = v23 == 0 ? 0x8007007A : 0;
              if ( !v23 )
                return v16;
              v26 = lstrlenW(String);
              String[v26] = 95;
              _itow_s(v5, &String[v26 + 1], 260 - (v26 + 1), 10);
              NamedPipeW = CreateNamedPipeW(String, 0x40080003u, 6u, 1u, 0x400u, 0x400u, 0x3E8u, lpSecurityAttributes);
              if ( NamedPipeW == (HANDLE)-1LL )
                return (unsigned int)GetLastWin32Error();
              *(_QWORD *)(v21 + *((_QWORD *)this + 2)) = NamedPipeW;
              v16 = AttachHandleToThreadPool(NamedPipeW);
              if ( !v16 )
              {
                ++*((_DWORD *)this + 14);
                LODWORD(v5) = v5 + 1;
                ++v20;
                v21 += 56;
                if ( v20 < a5 )
                  continue;
              }
              return v16;
            }
          }
        }
      }
    }
    return (unsigned int)-2147024882;
  }
  else
  {
    return (unsigned int)-2147024809;
  }
}

```

## disassembly

```asm
0x180001924  mov     [rsp+arg_8], rbx
0x180001929  push    rbp
0x18000192a  push    rsi
0x18000192b  push    rdi
0x18000192c  push    r12
0x18000192e  push    r13
0x180001930  push    r14
0x180001932  push    r15
0x180001934  sub     rsp, 270h
0x18000193b  mov     rax, cs:__security_cookie
0x180001942  xor     rax, rsp
0x180001945  mov     [rsp+2A8h+var_48], rax
0x18000194d  movsxd  rsi, [rsp+2A8h+arg_20]
0x180001955  xor     r15d, r15d
0x180001958  mov     [rsp+2A8h+var_268], r9
0x18000195d  mov     r13, r9
0x180001960  mov     r12, r8
0x180001963  mov     rbp, rdx
0x180001966  mov     rdi, rcx
0x180001969  mov     ebx, r15d
0x18000196c  test    rdx, rdx
0x18000196f  jz      loc_180001BCE
0x180001975  test    r8, r8
0x180001978  jz      loc_180001BCE
0x18000197e  cmp     esi, 1
0x180001981  jl      loc_180001BCE
0x180001987  mov     rcx, r8; lpString
0x18000198a  call    cs:__imp_lstrlenW
0x180001990  cmp     eax, 0F8h
0x180001995  jg      loc_180001BCE
0x18000199b  mov     [rdi+20h], rbp
0x18000199f  lea     eax, [r15+38h]
0x1800019a3  mul     rsi
0x1800019a6  mov     rbp, rsi
0x1800019a9  lea     rsi, [r15-1]
0x1800019ad  cmovo   rax, rsi
0x1800019b1  add     rax, 8
0x1800019b5  cmovb   rax, rsi
0x1800019b9  mov     rcx, rax; unsigned __int64
0x1800019bc  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x1800019c1  test    rax, rax
0x1800019c4  jz      short loc_180001A00
0x1800019c6  lea     r14, [rax+8]
0x1800019ca  mov     [rax], rbp
0x1800019cd  mov     rsi, r14
0x1800019d0  mov     r15, rbp
0x1800019d3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800019d7  lea     rcx, [rsi+8]; lpCriticalSection
0x1800019db  mov     [rsi], r13
0x1800019de  mov     dword ptr [rsi+30h], 1
0x1800019e5  call    cs:__imp_InitializeCriticalSection
0x1800019eb  lea     rsi, [rsi+38h]
0x1800019ef  sub     r15, 1
0x1800019f3  jnz     short loc_1800019D7
0x1800019f5  mov     r13, [rsp+2A8h+var_268]
0x1800019fa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800019fe  jmp     short loc_180001A03
0x180001a00  mov     r14, r15
0x180001a03  mov     [rdi+10h], r14
0x180001a07  test    r14, r14
0x180001a0a  jnz     short loc_180001A16
0x180001a0c  mov     ebx, 8007000Eh
0x180001a11  jmp     loc_180001BD3
0x180001a16  mov     eax, 38h ; '8'
0x180001a1b  mul     rbp
0x180001a1e  cmovo   rax, rsi
0x180001a22  mov     rcx, rax; unsigned __int64
0x180001a25  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180001a2a  mov     [rdi+18h], rax
0x180001a2e  test    rax, rax
0x180001a31  jz      short loc_180001A0C
0x180001a33  mov     eax, 4
0x180001a38  mul     rbp
0x180001a3b  cmovo   rax, rsi
0x180001a3f  mov     rcx, rax; unsigned __int64
0x180001a42  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180001a47  mov     [rdi+28h], rax
0x180001a4b  test    rax, rax
0x180001a4e  jz      short loc_180001A0C
0x180001a50  mov     eax, 8
0x180001a55  mul     rbp
0x180001a58  cmovo   rax, rsi
0x180001a5c  mov     rcx, rax; unsigned __int64
0x180001a5f  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180001a64  mov     [rdi+30h], rax
0x180001a68  test    rax, rax
0x180001a6b  jz      short loc_180001A0C
0x180001a6d  xor     eax, eax
0x180001a6f  test    rbp, rbp
0x180001a72  jz      loc_180001BD3
0x180001a78  mov     esi, eax
0x180001a7a  mov     r14d, eax
0x180001a7d  mov     rax, [rdi+18h]
0x180001a81  mov     [rax+r14+30h], r15d
0x180001a86  mov     rax, [rdi+18h]
0x180001a8a  mov     [rax+r14+20h], rdi
0x180001a8f  mov     rax, [rdi+28h]
0x180001a93  mov     dword ptr [rax+rsi*4], 400h
0x180001a9a  mov     rax, [rdi+28h]
0x180001a9e  mov     ecx, [rax+rsi*4]; unsigned __int64
0x180001aa1  call    ?MemAllocClear@@YAPEAX_K@Z; MemAllocClear(unsigned __int64)
0x180001aa6  mov     rcx, [rdi+30h]
0x180001aaa  xor     r9d, r9d
0x180001aad  mov     [rcx+rsi*8], rax
0x180001ab1  mov     rax, [rdi+30h]
0x180001ab5  cmp     [rax+rsi*8], r9
0x180001ab9  jz      loc_180001A0C
0x180001abf  lea     rax, [rsp+2A8h+String]
0x180001ac4  mov     r8, r12
0x180001ac7  sub     r8, rax
0x180001aca  lea     rcx, [rsp+2A8h+String]
0x180001acf  mov     edx, 104h
0x180001ad4  lea     rax, [rdx+7FFFFEFAh]
0x180001adb  test    rax, rax
0x180001ade  jz      short loc_180001AF7
0x180001ae0  movzx   eax, word ptr [r8+rcx]
0x180001ae5  test    ax, ax
0x180001ae8  jz      short loc_180001AF7
0x180001aea  mov     [rcx], ax
0x180001aed  add     rcx, 2
0x180001af1  sub     rdx, 1
0x180001af5  jnz     short loc_180001AD4
0x180001af7  test    rdx, rdx
0x180001afa  lea     rax, [rcx-2]
0x180001afe  cmovnz  rax, rcx
0x180001b02  mov     [rax], r9w
0x180001b06  mov     rax, rdx
0x180001b09  neg     rax
0x180001b0c  sbb     ebx, ebx
0x180001b0e  not     ebx
0x180001b10  and     ebx, 8007007Ah
0x180001b16  test    rdx, rdx
0x180001b19  jz      loc_180001BD3
0x180001b1f  lea     rcx, [rsp+2A8h+String]; lpString
0x180001b24  call    cs:__imp_lstrlenW
0x180001b2a  movsxd  rcx, eax
0x180001b2d  mov     edx, 5Fh ; '_'
0x180001b32  inc     eax
0x180001b34  mov     r9d, 0Ah; Radix
0x180001b3a  mov     [rsp+rcx*2+2A8h+String], dx
0x180001b3f  mov     ecx, 104h
0x180001b44  sub     ecx, eax
0x180001b46  lea     rdx, [rsp+2A8h+String]
0x180001b4b  cdqe
0x180001b4d  movsxd  r8, ecx; BufferCount
0x180001b50  mov     ecx, r15d; Value
0x180001b53  lea     rdx, [rdx+rax*2]; Buffer
0x180001b57  call    cs:__imp__itow_s
0x180001b5d  mov     [rsp+2A8h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180001b62  lea     rcx, [rsp+2A8h+String]; lpName
0x180001b67  mov     eax, 400h
0x180001b6c  mov     [rsp+2A8h+nDefaultTimeOut], 3E8h; nDefaultTimeOut
0x180001b74  mov     r9d, 1; nMaxInstances
0x180001b7a  mov     [rsp+2A8h+nInBufferSize], eax; nInBufferSize
0x180001b7e  mov     edx, 40080003h; dwOpenMode
0x180001b83  mov     [rsp+2A8h+nOutBufferSize], eax; nOutBufferSize
0x180001b87  lea     r8d, [r9+5]; dwPipeMode
0x180001b8b  call    cs:__imp_CreateNamedPipeW
0x180001b91  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180001b95  jz      short loc_180001BC5
0x180001b97  mov     rcx, [rdi+10h]
0x180001b9b  mov     [r14+rcx], rax
0x180001b9f  mov     rcx, rax
0x180001ba2  call    AttachHandleToThreadPool
0x180001ba7  mov     ebx, eax
0x180001ba9  test    eax, eax
0x180001bab  jnz     short loc_180001BD3
0x180001bad  inc     dword ptr [rdi+38h]
0x180001bb0  inc     r15d
0x180001bb3  inc     rsi
0x180001bb6  add     r14, 38h ; '8'
0x180001bba  cmp     rsi, rbp
0x180001bbd  jl      loc_180001A7D
0x180001bc3  jmp     short loc_180001BD3
0x180001bc5  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180001bca  mov     ebx, eax
0x180001bcc  jmp     short loc_180001BD3
0x180001bce  mov     ebx, 80070057h
0x180001bd3  mov     eax, ebx
0x180001bd5  mov     rcx, [rsp+2A8h+var_48]
0x180001bdd  xor     rcx, rsp; StackCookie
0x180001be0  call    __security_check_cookie
0x180001be5  mov     rbx, [rsp+2A8h+arg_8]
0x180001bed  add     rsp, 270h
0x180001bf4  pop     r15
0x180001bf6  pop     r14
0x180001bf8  pop     r13
0x180001bfa  pop     r12
0x180001bfc  pop     rdi
0x180001bfd  pop     rsi
0x180001bfe  pop     rbp
0x180001bff  retn
```

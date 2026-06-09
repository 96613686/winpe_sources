# URL_HASH_ENTRY::Init(int,void *,int,char const *)

- ea: `0x180031a10`
- end: `0x180031b30`
- name: `?Init@URL_HASH_ENTRY@@QEAAJHPEAXHPEBD@Z`
- size: `288`
- prototype: `__int64 __fastcall(char **this, __int64, char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001a7e0`

## callees

- `0x180028000`
- `0x18003179c`
- `0x1800318f4`
- `0x180031a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031b05`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180031b05`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031a49`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180031a49`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180031a28`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180031a28`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031ae3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031ae3`

## pseudocode

```c
__int64 __fastcall URL_HASH_ENTRY::Init(char **this, __int64 a2, char *a3, int a4, char *a5)
{
  char *v8; // rax
  unsigned int v9; // edx
  PtrsQueue **v10; // rbx
  unsigned int v11; // edi
  LPCSTR v12; // rcx
  __int64 v13; // rdx

  InitializeCriticalSection((LPCRITICAL_SECTION)(this + 6));
  *((_DWORD *)this + 22) = 1;
  *((_DWORD *)this + 8) = 0;
  this[2] = a3;
  if ( a4 )
  {
    v8 = (char *)malloc(0xA8u);
    if ( v8 )
      *(_QWORD *)v8 = 0;
    else
      v8 = 0;
    v10 = (PtrsQueue **)(this + 3);
    this[3] = v8;
    if ( !v8 )
    {
      v11 = -2147024882;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_15;
      v13 = 12;
      goto LABEL_14;
    }
  }
  else
  {
    v10 = (PtrsQueue **)(this + 3);
    this[3] = 0;
  }
  DupStr(this, a5);
  if ( *this )
  {
    *((_DWORD *)this + 9) = 0;
    v11 = 0;
    *((_DWORD *)this + 10) = 0;
    *((_DWORD *)this + 11) = 0;
    this[12] = 0;
    return v11;
  }
  v11 = -2147024882;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    v13 = 13;
LABEL_14:
    WPP_SF_(*((_QWORD *)v12 + 2), v13, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids);
  }
LABEL_15:
  if ( *((_DWORD *)this + 22) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(this + 6));
    *((_DWORD *)this + 22) = 0;
  }
  if ( *v10 )
  {
    PtrsQueue::`scalar deleting destructor'(*v10, v9);
    *v10 = 0;
  }
  if ( *this )
  {
    free(*this);
    *this = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x180031a10  push    rbx
0x180031a12  push    rbp
0x180031a13  push    rsi
0x180031a14  push    rdi
0x180031a15  push    r14
0x180031a17  sub     rsp, 20h
0x180031a1b  mov     rsi, rcx
0x180031a1e  mov     edi, r9d
0x180031a21  add     rcx, 30h ; '0'; lpCriticalSection
0x180031a25  mov     rbx, r8
0x180031a28  call    cs:__imp_InitializeCriticalSection
0x180031a2e  xor     r14d, r14d
0x180031a31  mov     dword ptr [rsi+58h], 1
0x180031a38  mov     [rsi+20h], r14d
0x180031a3c  mov     [rsi+10h], rbx
0x180031a40  test    edi, edi
0x180031a42  jz      short loc_180031A8D
0x180031a44  mov     ecx, 0A8h; Size
0x180031a49  call    cs:__imp_malloc
0x180031a4f  test    rax, rax
0x180031a52  jz      short loc_180031A59
0x180031a54  mov     [rax], r14
0x180031a57  jmp     short loc_180031A5C
0x180031a59  mov     rax, r14
0x180031a5c  lea     rbx, [rsi+18h]
0x180031a60  mov     [rbx], rax
0x180031a63  test    rax, rax
0x180031a66  jnz     short loc_180031A94
0x180031a68  mov     edi, 8007000Eh
0x180031a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031a74  lea     rax, WPP_GLOBAL_Control
0x180031a7b  cmp     rcx, rax
0x180031a7e  jz      short loc_180031AD9
0x180031a80  test    byte ptr [rcx+1Ch], 1
0x180031a84  jz      short loc_180031AD9
0x180031a86  mov     edx, 0Ch
0x180031a8b  jmp     short loc_180031AC9
0x180031a8d  lea     rbx, [rsi+18h]
0x180031a91  mov     [rbx], r14
0x180031a94  mov     rdx, [rsp+48h+arg_20]; char *
0x180031a99  mov     rcx, rsi; char **
0x180031a9c  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x180031aa1  cmp     [rsi], r14
0x180031aa4  jnz     short loc_180031B10
0x180031aa6  mov     edi, 8007000Eh
0x180031aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ab2  lea     rax, WPP_GLOBAL_Control
0x180031ab9  cmp     rcx, rax
0x180031abc  jz      short loc_180031AD9
0x180031abe  test    byte ptr [rcx+1Ch], 1
0x180031ac2  jz      short loc_180031AD9
0x180031ac4  mov     edx, 0Dh
0x180031ac9  mov     rcx, [rcx+10h]
0x180031acd  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x180031ad4  call    WPP_SF_
0x180031ad9  cmp     [rsi+58h], r14d
0x180031add  jz      short loc_180031AED
0x180031adf  lea     rcx, [rsi+30h]; lpCriticalSection
0x180031ae3  call    cs:__imp_DeleteCriticalSection
0x180031ae9  mov     [rsi+58h], r14d
0x180031aed  mov     rcx, [rbx]; this
0x180031af0  test    rcx, rcx
0x180031af3  jz      short loc_180031AFD
0x180031af5  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x180031afa  mov     [rbx], r14
0x180031afd  mov     rcx, [rsi]; Block
0x180031b00  test    rcx, rcx
0x180031b03  jz      short loc_180031B23
0x180031b05  call    cs:__imp_free
0x180031b0b  mov     [rsi], r14
0x180031b0e  jmp     short loc_180031B23
0x180031b10  mov     [rsi+24h], r14d
0x180031b14  mov     edi, r14d
0x180031b17  mov     [rsi+28h], r14d
0x180031b1b  mov     [rsi+2Ch], r14d
0x180031b1f  mov     [rsi+60h], r14
0x180031b23  mov     eax, edi
0x180031b25  add     rsp, 20h
0x180031b29  pop     r14
0x180031b2b  pop     rdi
0x180031b2c  pop     rsi
0x180031b2d  pop     rbp
0x180031b2e  pop     rbx
0x180031b2f  retn
```

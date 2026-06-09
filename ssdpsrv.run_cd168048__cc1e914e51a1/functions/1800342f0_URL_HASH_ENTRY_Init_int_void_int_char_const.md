# URL_HASH_ENTRY::Init(int,void *,int,char const *)

- ea: `0x1800342f0`
- end: `0x180034429`
- name: `?Init@URL_HASH_ENTRY@@QEAAJHPEAXHPEBD@Z`
- size: `313`
- prototype: `__int64 __usercall@<rax>(char **this@<rcx>, int@<edx>, void *@<r8>, int@<r9d>, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001bb1c`

## callees

- `0x180029df0`
- `0x180034060`
- `0x1800341cc`
- `0x1800342f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800343f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800343f7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003432f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18003432f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034308`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180034308`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800343cf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800343cf`

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
0x1800342f0  push    rbx
0x1800342f2  push    rbp
0x1800342f3  push    rsi
0x1800342f4  push    rdi
0x1800342f5  push    r14
0x1800342f7  sub     rsp, 20h
0x1800342fb  mov     rsi, rcx
0x1800342fe  mov     edi, r9d
0x180034301  add     rcx, 30h ; '0'; lpCriticalSection
0x180034305  mov     rbx, r8
0x180034308  call    cs:__imp_InitializeCriticalSection
0x18003430f  nop     dword ptr [rax+rax+00h]
0x180034314  xor     r14d, r14d
0x180034317  mov     dword ptr [rsi+58h], 1
0x18003431e  mov     [rsi+20h], r14d
0x180034322  mov     [rsi+10h], rbx
0x180034326  test    edi, edi
0x180034328  jz      short loc_180034379
0x18003432a  mov     ecx, 0A8h; Size
0x18003432f  call    cs:__imp_malloc
0x180034336  nop     dword ptr [rax+rax+00h]
0x18003433b  test    rax, rax
0x18003433e  jz      short loc_180034345
0x180034340  mov     [rax], r14
0x180034343  jmp     short loc_180034348
0x180034345  mov     rax, r14
0x180034348  lea     rbx, [rsi+18h]
0x18003434c  mov     [rbx], rax
0x18003434f  test    rax, rax
0x180034352  jnz     short loc_180034380
0x180034354  mov     edi, 8007000Eh
0x180034359  mov     rcx, cs:WPP_GLOBAL_Control
0x180034360  lea     rax, WPP_GLOBAL_Control
0x180034367  cmp     rcx, rax
0x18003436a  jz      short loc_1800343C5
0x18003436c  test    byte ptr [rcx+1Ch], 1
0x180034370  jz      short loc_1800343C5
0x180034372  mov     edx, 0Ch
0x180034377  jmp     short loc_1800343B5
0x180034379  lea     rbx, [rsi+18h]
0x18003437d  mov     [rbx], r14
0x180034380  mov     rdx, [rsp+48h+arg_20]; char *
0x180034385  mov     rcx, rsi; char **
0x180034388  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18003438d  cmp     [rsi], r14
0x180034390  jnz     short loc_180034408
0x180034392  mov     edi, 8007000Eh
0x180034397  mov     rcx, cs:WPP_GLOBAL_Control
0x18003439e  lea     rax, WPP_GLOBAL_Control
0x1800343a5  cmp     rcx, rax
0x1800343a8  jz      short loc_1800343C5
0x1800343aa  test    byte ptr [rcx+1Ch], 1
0x1800343ae  jz      short loc_1800343C5
0x1800343b0  mov     edx, 0Dh
0x1800343b5  mov     rcx, [rcx+10h]
0x1800343b9  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x1800343c0  call    WPP_SF_
0x1800343c5  cmp     [rsi+58h], r14d
0x1800343c9  jz      short loc_1800343DF
0x1800343cb  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800343cf  call    cs:__imp_DeleteCriticalSection
0x1800343d6  nop     dword ptr [rax+rax+00h]
0x1800343db  mov     [rsi+58h], r14d
0x1800343df  mov     rcx, [rbx]; this
0x1800343e2  test    rcx, rcx
0x1800343e5  jz      short loc_1800343EF
0x1800343e7  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x1800343ec  mov     [rbx], r14
0x1800343ef  mov     rcx, [rsi]; Block
0x1800343f2  test    rcx, rcx
0x1800343f5  jz      short loc_18003441B
0x1800343f7  call    cs:__imp_free
0x1800343fe  nop     dword ptr [rax+rax+00h]
0x180034403  mov     [rsi], r14
0x180034406  jmp     short loc_18003441B
0x180034408  mov     [rsi+24h], r14d
0x18003440c  mov     edi, r14d
0x18003440f  mov     [rsi+28h], r14d
0x180034413  mov     [rsi+2Ch], r14d
0x180034417  mov     [rsi+60h], r14
0x18003441b  mov     eax, edi
0x18003441d  add     rsp, 20h
0x180034421  pop     r14
0x180034423  pop     rdi
0x180034424  pop     rsi
0x180034425  pop     rbp
0x180034426  pop     rbx
0x180034427  retn
```

# URL_HASH_ENTRY::Init(int,void *,int,char const *)

- ea: `0x180023124`
- end: `0x18002325a`
- name: `?Init@URL_HASH_ENTRY@@QEAAJHPEAXHPEBD@Z`
- size: `310`
- prototype: `__int64 __usercall@<rax>(char **this@<rcx>, int@<edx>, void *@<r8>, int@<r9d>, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800223c4`

## callees

- `0x180023124`
- `0x180024000`
- `0x18003c018`
- `0x180055380`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023228`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180023228`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180023160`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180023160`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180023139`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180023139`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023200`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023200`

## pseudocode

```c
__int64 __fastcall URL_HASH_ENTRY::Init(char **this, __int64 a2, void *a3, int a4, char *a5)
{
  char *v7; // rax
  unsigned int v8; // edx
  PtrsQueue **v9; // rbx
  unsigned int v10; // esi
  STRSAFE_PCNZWCH v11; // rcx
  __int64 v12; // rdx

  InitializeCriticalSection((LPCRITICAL_SECTION)(this + 6));
  *((_DWORD *)this + 22) = 1;
  *((_DWORD *)this + 8) = 0;
  this[2] = 0;
  if ( a4 )
  {
    v7 = (char *)malloc(0xA8u);
    if ( v7 )
      *(_QWORD *)v7 = 0;
    else
      v7 = 0;
    v9 = (PtrsQueue **)(this + 3);
    this[3] = v7;
    if ( !v7 )
    {
      v10 = -2147024882;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_15;
      v12 = 12;
      goto LABEL_14;
    }
  }
  else
  {
    v9 = (PtrsQueue **)(this + 3);
    this[3] = 0;
  }
  DupStr(this, a5);
  if ( *this )
  {
    *((_DWORD *)this + 9) = 0;
    v10 = 0;
    *((_DWORD *)this + 10) = 0;
    *((_DWORD *)this + 11) = 0;
    this[12] = 0;
    return v10;
  }
  v10 = -2147024882;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v12 = 13;
LABEL_14:
    WPP_SF_(*((_QWORD *)v11 + 2), v12, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids);
  }
LABEL_15:
  if ( *((_DWORD *)this + 22) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(this + 6));
    *((_DWORD *)this + 22) = 0;
  }
  if ( *v9 )
  {
    PtrsQueue::`scalar deleting destructor'(*v9, v8);
    *v9 = 0;
  }
  if ( *this )
  {
    free(*this);
    *this = 0;
  }
  return v10;
}

```

## disassembly

```asm
0x180023124  push    rbx
0x180023126  push    rbp
0x180023127  push    rsi
0x180023128  push    rdi
0x180023129  push    r14
0x18002312b  sub     rsp, 20h
0x18002312f  mov     rdi, rcx
0x180023132  mov     ebx, r9d
0x180023135  add     rcx, 30h ; '0'; lpCriticalSection
0x180023139  call    cs:__imp_InitializeCriticalSection
0x180023140  nop     dword ptr [rax+rax+00h]
0x180023145  xor     r14d, r14d
0x180023148  mov     dword ptr [rdi+58h], 1
0x18002314f  mov     [rdi+20h], r14d
0x180023153  mov     [rdi+10h], r14
0x180023157  test    ebx, ebx
0x180023159  jz      short loc_1800231AA
0x18002315b  mov     ecx, 0A8h; Size
0x180023160  call    cs:__imp_malloc
0x180023167  nop     dword ptr [rax+rax+00h]
0x18002316c  test    rax, rax
0x18002316f  jz      short loc_180023176
0x180023171  mov     [rax], r14
0x180023174  jmp     short loc_180023179
0x180023176  mov     rax, r14
0x180023179  lea     rbx, [rdi+18h]
0x18002317d  mov     [rbx], rax
0x180023180  test    rax, rax
0x180023183  jnz     short loc_1800231B1
0x180023185  mov     esi, 8007000Eh
0x18002318a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023191  lea     rax, WPP_GLOBAL_Control
0x180023198  cmp     rcx, rax
0x18002319b  jz      short loc_1800231F6
0x18002319d  test    byte ptr [rcx+1Ch], 1
0x1800231a1  jz      short loc_1800231F6
0x1800231a3  mov     edx, 0Ch
0x1800231a8  jmp     short loc_1800231E6
0x1800231aa  lea     rbx, [rdi+18h]
0x1800231ae  mov     [rbx], r14
0x1800231b1  mov     rdx, [rsp+48h+arg_20]; char *
0x1800231b6  mov     rcx, rdi; char **
0x1800231b9  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x1800231be  cmp     [rdi], r14
0x1800231c1  jnz     short loc_180023239
0x1800231c3  mov     esi, 8007000Eh
0x1800231c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800231cf  lea     rax, WPP_GLOBAL_Control
0x1800231d6  cmp     rcx, rax
0x1800231d9  jz      short loc_1800231F6
0x1800231db  test    byte ptr [rcx+1Ch], 1
0x1800231df  jz      short loc_1800231F6
0x1800231e1  mov     edx, 0Dh
0x1800231e6  mov     rcx, [rcx+10h]
0x1800231ea  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x1800231f1  call    WPP_SF_
0x1800231f6  cmp     [rdi+58h], r14d
0x1800231fa  jz      short loc_180023210
0x1800231fc  lea     rcx, [rdi+30h]; lpCriticalSection
0x180023200  call    cs:__imp_DeleteCriticalSection
0x180023207  nop     dword ptr [rax+rax+00h]
0x18002320c  mov     [rdi+58h], r14d
0x180023210  mov     rcx, [rbx]; this
0x180023213  test    rcx, rcx
0x180023216  jz      short loc_180023220
0x180023218  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x18002321d  mov     [rbx], r14
0x180023220  mov     rcx, [rdi]; Block
0x180023223  test    rcx, rcx
0x180023226  jz      short loc_18002324C
0x180023228  call    cs:__imp_free
0x18002322f  nop     dword ptr [rax+rax+00h]
0x180023234  mov     [rdi], r14
0x180023237  jmp     short loc_18002324C
0x180023239  mov     [rdi+24h], r14d
0x18002323d  mov     esi, r14d
0x180023240  mov     [rdi+28h], r14d
0x180023244  mov     [rdi+2Ch], r14d
0x180023248  mov     [rdi+60h], r14
0x18002324c  mov     eax, esi
0x18002324e  add     rsp, 20h
0x180023252  pop     r14
0x180023254  pop     rdi
0x180023255  pop     rsi
0x180023256  pop     rbp
0x180023257  pop     rbx
0x180023258  retn
```

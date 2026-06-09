# URL_HASH_ENTRY::Init(int,void *,int,char const *)

- ea: `0x1800224dc`
- end: `0x1800225f9`
- name: `?Init@URL_HASH_ENTRY@@QEAAJHPEAXHPEBD@Z`
- size: `285`
- prototype: `__int64 __usercall@<rax>(char **this@<rcx>, int@<edx>, void *@<r8>, int@<r9d>, const char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800217f4`

## callees

- `0x1800224dc`
- `0x180023310`
- `0x180039a84`
- `0x180051b8c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800225ce`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800225ce`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022512`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180022512`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800224f1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800224f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800225ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800225ac`

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
0x1800224dc  push    rbx
0x1800224de  push    rbp
0x1800224df  push    rsi
0x1800224e0  push    rdi
0x1800224e1  push    r14
0x1800224e3  sub     rsp, 20h
0x1800224e7  mov     rdi, rcx
0x1800224ea  mov     ebx, r9d
0x1800224ed  add     rcx, 30h ; '0'; lpCriticalSection
0x1800224f1  call    cs:__imp_InitializeCriticalSection
0x1800224f7  xor     r14d, r14d
0x1800224fa  mov     dword ptr [rdi+58h], 1
0x180022501  mov     [rdi+20h], r14d
0x180022505  mov     [rdi+10h], r14
0x180022509  test    ebx, ebx
0x18002250b  jz      short loc_180022556
0x18002250d  mov     ecx, 0A8h; Size
0x180022512  call    cs:__imp_malloc
0x180022518  test    rax, rax
0x18002251b  jz      short loc_180022522
0x18002251d  mov     [rax], r14
0x180022520  jmp     short loc_180022525
0x180022522  mov     rax, r14
0x180022525  lea     rbx, [rdi+18h]
0x180022529  mov     [rbx], rax
0x18002252c  test    rax, rax
0x18002252f  jnz     short loc_18002255D
0x180022531  mov     esi, 8007000Eh
0x180022536  mov     rcx, cs:WPP_GLOBAL_Control
0x18002253d  lea     rax, WPP_GLOBAL_Control
0x180022544  cmp     rcx, rax
0x180022547  jz      short loc_1800225A2
0x180022549  test    byte ptr [rcx+1Ch], 1
0x18002254d  jz      short loc_1800225A2
0x18002254f  mov     edx, 0Ch
0x180022554  jmp     short loc_180022592
0x180022556  lea     rbx, [rdi+18h]
0x18002255a  mov     [rbx], r14
0x18002255d  mov     rdx, [rsp+48h+arg_20]; char *
0x180022562  mov     rcx, rdi; char **
0x180022565  call    ?DupStr@@YAXPEAPEADPEBD@Z; DupStr(char * *,char const *)
0x18002256a  cmp     [rdi], r14
0x18002256d  jnz     short loc_1800225D9
0x18002256f  mov     esi, 8007000Eh
0x180022574  mov     rcx, cs:WPP_GLOBAL_Control
0x18002257b  lea     rax, WPP_GLOBAL_Control
0x180022582  cmp     rcx, rax
0x180022585  jz      short loc_1800225A2
0x180022587  test    byte ptr [rcx+1Ch], 1
0x18002258b  jz      short loc_1800225A2
0x18002258d  mov     edx, 0Dh
0x180022592  mov     rcx, [rcx+10h]
0x180022596  lea     r8, WPP_c7aedd0b68c2342b7dbcb5aec11862d5_Traceguids
0x18002259d  call    WPP_SF_
0x1800225a2  cmp     [rdi+58h], r14d
0x1800225a6  jz      short loc_1800225B6
0x1800225a8  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800225ac  call    cs:__imp_DeleteCriticalSection
0x1800225b2  mov     [rdi+58h], r14d
0x1800225b6  mov     rcx, [rbx]; this
0x1800225b9  test    rcx, rcx
0x1800225bc  jz      short loc_1800225C6
0x1800225be  call    ??_GPtrsQueue@@QEAAPEAXI@Z; PtrsQueue::`scalar deleting destructor'(uint)
0x1800225c3  mov     [rbx], r14
0x1800225c6  mov     rcx, [rdi]; Block
0x1800225c9  test    rcx, rcx
0x1800225cc  jz      short loc_1800225EC
0x1800225ce  call    cs:__imp_free
0x1800225d4  mov     [rdi], r14
0x1800225d7  jmp     short loc_1800225EC
0x1800225d9  mov     [rdi+24h], r14d
0x1800225dd  mov     esi, r14d
0x1800225e0  mov     [rdi+28h], r14d
0x1800225e4  mov     [rdi+2Ch], r14d
0x1800225e8  mov     [rdi+60h], r14
0x1800225ec  mov     eax, esi
0x1800225ee  add     rsp, 20h
0x1800225f2  pop     r14
0x1800225f4  pop     rdi
0x1800225f5  pop     rsi
0x1800225f6  pop     rbp
0x1800225f7  pop     rbx
0x1800225f8  retn
```

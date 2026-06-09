# CSatelliteSessionContext::Build(void)

- ea: `0x100479430`
- end: `0x10047972d`
- name: `?Build@CSatelliteSessionContext@@AEAA_NXZ`
- size: `765`
- prototype: `char __fastcall(CSatelliteSessionContext *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10047a7a0`

## callees

- `0x100479430`
- `0x100487cd6`

## import_xrefs

- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004795ea`
- `sqldk!??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004795ea`
- `sqldk!??_V@YAXPEAX@Z` at `0x10047949d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100479519`
- `sqldk!??_V@YAXPEAX@Z` at `0x100479597`
- `sqldk!??_V@YAXPEAX@Z` at `0x10047949d`
- `sqldk!??_V@YAXPEAX@Z` at `0x100479519`
- `sqldk!??_V@YAXPEAX@Z` at `0x100479597`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047961c`
- `sqldk!??3@YAXPEAX_K@Z` at `0x10047961c`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479488`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479504`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479582`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479682`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004796e5`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479488`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479504`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479582`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x100479682`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1004796e5`

## string_xrefs

- `0x100479476`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x1004794e8`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x10047956e`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x1004795cc`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x10047966e`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`
- `0x1004796c9`: `Sql\Ntdbms\extensibility\common\src\satellitesessioncontext.cpp`

## pseudocode

```c
char __fastcall CSatelliteSessionContext::Build(CSatelliteSessionContext *this)
{
  unsigned __int64 v2; // rax
  void *v3; // rax
  void *v4; // rcx
  void *v5; // rdi
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rax
  void *v8; // rax
  void *v9; // rcx
  void *v10; // rdi
  unsigned __int64 v11; // rax
  void *v12; // rax
  void *v13; // rcx
  void *v14; // rdi
  _DWORD *v15; // rdi
  _DWORD *v16; // rcx
  unsigned __int64 v17; // rax
  void *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  void *v21; // rax

  if ( !*((_QWORD *)this + 19) && *((_WORD *)this + 21) )
  {
    v2 = 30LL * *((unsigned __int16 *)this + 21);
    if ( !is_mul_ok(*((unsigned __int16 *)this + 21), 0x1Eu) )
      v2 = -1;
    v3 = operator new[](
           v2,
           *(struct IMemObj **)this,
           1,
           "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
           54,
           6u);
    v4 = (void *)*((_QWORD *)this + 19);
    v5 = v3;
    if ( v4 != v3 )
      operator delete[](v4);
    *((_QWORD *)this + 19) = v5;
    if ( !v5 )
      return 0;
    memset_0(v5, 0, 30LL * *((unsigned __int16 *)this + 21));
  }
  if ( !*((_QWORD *)this + 20) )
  {
    v6 = *((unsigned __int16 *)this + 22);
    if ( (_WORD)v6 )
    {
      v7 = 30 * v6;
      if ( !is_mul_ok(v6, 0x1Eu) )
        v7 = -1;
      v8 = operator new[](
             v7,
             *(struct IMemObj **)this,
             1,
             "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
             65,
             6u);
      v9 = (void *)*((_QWORD *)this + 20);
      v10 = v8;
      if ( v9 != v8 )
        operator delete[](v9);
      *((_QWORD *)this + 20) = v10;
      if ( !v10 )
        return 0;
      memset_0(v10, 0, 30LL * *((unsigned __int16 *)this + 22));
    }
  }
  if ( !*((_QWORD *)this + 21) && *((_WORD *)this + 23) )
  {
    v11 = 41LL * *((unsigned __int16 *)this + 23);
    if ( !is_mul_ok(*((unsigned __int16 *)this + 23), 0x29u) )
      v11 = -1;
    v12 = operator new[](
            v11,
            *(struct IMemObj **)this,
            1,
            "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
            76,
            6u);
    v13 = (void *)*((_QWORD *)this + 21);
    v14 = v12;
    if ( v13 != v12 )
      operator delete[](v13);
    *((_QWORD *)this + 21) = v14;
    if ( !v14 )
      return 0;
    memset_0(v14, 0, 41LL * *((unsigned __int16 *)this + 23));
  }
  if ( !*((_QWORD *)this + 22) )
  {
    v15 = operator new(
            0xFu,
            *(struct IMemObj **)this,
            1,
            "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
            87,
            6u);
    if ( v15 )
    {
      *(_QWORD *)v15 = 0;
      v15[2] = 0;
      *((_WORD *)v15 + 6) = 0;
      *((_BYTE *)v15 + 14) = 0;
    }
    else
    {
      v15 = 0;
    }
    v16 = (_DWORD *)*((_QWORD *)this + 22);
    if ( v16 != v15 )
      operator delete(v16, 0xFu);
    *((_QWORD *)this + 22) = v15;
    if ( !v15 )
      return 0;
    *(_QWORD *)v15 = 0;
    v15[2] = 0;
    *((_WORD *)v15 + 6) = 0;
    *((_BYTE *)v15 + 14) = 0;
  }
  if ( !*((_QWORD *)this + 25) && *((_WORD *)this + 26) )
  {
    v17 = 2LL * *((unsigned __int16 *)this + 26);
    if ( !is_mul_ok(*((unsigned __int16 *)this + 26), 2u) )
      v17 = -1;
    v18 = operator new[](
            v17,
            *(struct IMemObj **)this,
            1,
            "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
            99,
            6u);
    *((_QWORD *)this + 25) = v18;
    if ( !v18 )
      return 0;
    memset_0(v18, 0, 2LL * *((unsigned __int16 *)this + 26));
  }
  if ( !*(_QWORD *)((char *)this + 210) )
  {
    v19 = *((unsigned __int16 *)this + 27);
    if ( (_WORD)v19 )
    {
      v20 = 2 * v19;
      if ( !is_mul_ok(v19, 2u) )
        v20 = -1;
      v21 = operator new[](
              v20,
              *(struct IMemObj **)this,
              1,
              "Sql\\Ntdbms\\extensibility\\common\\src\\satellitesessioncontext.cpp",
              112,
              6u);
      *(_QWORD *)((char *)this + 210) = v21;
      if ( !v21 )
        return 0;
      memset_0(v21, 0, 2LL * *((unsigned __int16 *)this + 27));
    }
  }
  return 1;
}

```

## disassembly

```asm
0x100479430  mov     [rsp+arg_0], rbx
0x100479435  mov     [rsp+arg_8], rsi
0x10047943a  push    rdi
0x10047943b  sub     rsp, 30h
0x10047943f  cmp     qword ptr [rcx+98h], 0
0x100479447  mov     rbx, rcx
0x10047944a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x100479451  jnz     short loc_1004794C5
0x100479453  movzx   eax, word ptr [rcx+2Ah]
0x100479457  test    ax, ax
0x10047945a  jz      short loc_1004794C5
0x10047945c  mov     ecx, eax
0x10047945e  mov     [rsp+38h+var_10], 6
0x100479463  mov     eax, 1Eh
0x100479468  mov     [rsp+38h+var_18], 36h ; '6'
0x100479470  mul     rcx
0x100479473  mov     rdx, [rbx]
0x100479476  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x10047947d  lea     r8d, [rsi+2]
0x100479481  cmovo   rax, rsi
0x100479485  mov     rcx, rax
0x100479488  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047948e  mov     rcx, [rbx+98h]
0x100479495  mov     rdi, rax
0x100479498  cmp     rcx, rax
0x10047949b  jz      short loc_1004794A3
0x10047949d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1004794a3  mov     [rbx+98h], rdi
0x1004794aa  test    rdi, rdi
0x1004794ad  jz      loc_1004796F7
0x1004794b3  movzx   eax, word ptr [rbx+2Ah]
0x1004794b7  xor     edx, edx; Val
0x1004794b9  imul    r8, rax, 1Eh; Size
0x1004794bd  mov     rcx, rdi; void *
0x1004794c0  call    memset_0
0x1004794c5  cmp     qword ptr [rbx+0A0h], 0
0x1004794cd  jnz     short loc_100479541
0x1004794cf  movzx   ecx, word ptr [rbx+2Ch]
0x1004794d3  test    cx, cx
0x1004794d6  jz      short loc_100479541
0x1004794d8  mov     eax, 1Eh
0x1004794dd  mov     [rsp+38h+var_10], 6
0x1004794e2  mul     rcx
0x1004794e5  mov     rdx, [rbx]
0x1004794e8  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x1004794ef  mov     r8d, 1
0x1004794f5  mov     [rsp+38h+var_18], 41h ; 'A'
0x1004794fd  cmovo   rax, rsi
0x100479501  mov     rcx, rax
0x100479504  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x10047950a  mov     rcx, [rbx+0A0h]
0x100479511  mov     rdi, rax
0x100479514  cmp     rcx, rax
0x100479517  jz      short loc_10047951F
0x100479519  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10047951f  mov     [rbx+0A0h], rdi
0x100479526  test    rdi, rdi
0x100479529  jz      loc_1004796F7
0x10047952f  movzx   eax, word ptr [rbx+2Ch]
0x100479533  xor     edx, edx; Val
0x100479535  imul    r8, rax, 1Eh; Size
0x100479539  mov     rcx, rdi; void *
0x10047953c  call    memset_0
0x100479541  cmp     qword ptr [rbx+0A8h], 0
0x100479549  jnz     short loc_1004795BF
0x10047954b  movzx   eax, word ptr [rbx+2Eh]
0x10047954f  test    ax, ax
0x100479552  jz      short loc_1004795BF
0x100479554  mov     ecx, eax
0x100479556  mov     [rsp+38h+var_10], 6
0x10047955b  mov     eax, 29h ; ')'
0x100479560  mov     [rsp+38h+var_18], 4Ch ; 'L'
0x100479568  mul     rcx
0x10047956b  mov     rdx, [rbx]
0x10047956e  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100479575  mov     r8d, 1
0x10047957b  cmovo   rax, rsi
0x10047957f  mov     rcx, rax
0x100479582  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100479588  mov     rcx, [rbx+0A8h]
0x10047958f  mov     rdi, rax
0x100479592  cmp     rcx, rax
0x100479595  jz      short loc_10047959D
0x100479597  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x10047959d  mov     [rbx+0A8h], rdi
0x1004795a4  test    rdi, rdi
0x1004795a7  jz      loc_1004796F7
0x1004795ad  movzx   eax, word ptr [rbx+2Eh]
0x1004795b1  xor     edx, edx; Val
0x1004795b3  imul    r8, rax, 29h ; ')'; Size
0x1004795b7  mov     rcx, rdi; void *
0x1004795ba  call    memset_0
0x1004795bf  cmp     qword ptr [rbx+0B0h], 0
0x1004795c7  jnz     short loc_100479641
0x1004795c9  mov     rdx, [rbx]
0x1004795cc  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x1004795d3  mov     r8d, 1
0x1004795d9  mov     [rsp+38h+var_10], 6
0x1004795de  mov     [rsp+38h+var_18], 57h ; 'W'
0x1004795e6  lea     ecx, [r8+0Eh]
0x1004795ea  call    cs:__imp_??2@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new(unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004795f0  mov     rdi, rax
0x1004795f3  test    rax, rax
0x1004795f6  jz      short loc_100479609
0x1004795f8  xor     eax, eax
0x1004795fa  mov     [rdi], rax
0x1004795fd  mov     [rdi+8], eax
0x100479600  mov     [rdi+0Ch], ax
0x100479604  mov     [rdi+0Eh], al
0x100479607  jmp     short loc_10047960B
0x100479609  xor     edi, edi
0x10047960b  mov     rcx, [rbx+0B0h]
0x100479612  cmp     rcx, rdi
0x100479615  jz      short loc_100479622
0x100479617  mov     edx, 0Fh
0x10047961c  call    cs:__imp_??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x100479622  mov     [rbx+0B0h], rdi
0x100479629  test    rdi, rdi
0x10047962c  jz      loc_1004796F7
0x100479632  xor     eax, eax
0x100479634  mov     [rdi], rax
0x100479637  mov     [rdi+8], eax
0x10047963a  mov     [rdi+0Ch], ax
0x10047963e  mov     [rdi+0Eh], al
0x100479641  cmp     qword ptr [rbx+0C8h], 0
0x100479649  jnz     short loc_1004796A6
0x10047964b  movzx   eax, word ptr [rbx+34h]
0x10047964f  test    ax, ax
0x100479652  jz      short loc_1004796A6
0x100479654  mov     ecx, eax
0x100479656  mov     [rsp+38h+var_10], 6
0x10047965b  mov     eax, 2
0x100479660  mov     [rsp+38h+var_18], 63h ; 'c'
0x100479668  mul     rcx
0x10047966b  mov     rdx, [rbx]
0x10047966e  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x100479675  mov     r8d, 1
0x10047967b  cmovo   rax, rsi
0x10047967f  mov     rcx, rax
0x100479682  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x100479688  mov     [rbx+0C8h], rax
0x10047968f  test    rax, rax
0x100479692  jz      short loc_1004796F7
0x100479694  movzx   r8d, word ptr [rbx+34h]
0x100479699  xor     edx, edx; Val
0x10047969b  add     r8, r8; Size
0x10047969e  mov     rcx, rax; void *
0x1004796a1  call    memset_0
0x1004796a6  cmp     qword ptr [rbx+0D2h], 0
0x1004796ae  jnz     short loc_10047971B
0x1004796b0  movzx   ecx, word ptr [rbx+36h]
0x1004796b4  test    cx, cx
0x1004796b7  jz      short loc_10047971B
0x1004796b9  mov     eax, 2
0x1004796be  mov     [rsp+38h+var_10], 6
0x1004796c3  mul     rcx
0x1004796c6  mov     rdx, [rbx]
0x1004796c9  lea     r9, aSqlNtdbmsExten_3; "Sql\\Ntdbms\\extensibility\\common\\src"...
0x1004796d0  mov     r8d, 1
0x1004796d6  mov     [rsp+38h+var_18], 70h ; 'p'
0x1004796de  cmovo   rax, rsi
0x1004796e2  mov     rcx, rax
0x1004796e5  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z; operator new[](unsigned __int64,IMemObj *,int,char const *,int,uchar)
0x1004796eb  mov     [rbx+0D2h], rax
0x1004796f2  test    rax, rax
0x1004796f5  jnz     short loc_100479709
0x1004796f7  xor     al, al
0x1004796f9  mov     rbx, [rsp+38h+arg_0]
0x1004796fe  mov     rsi, [rsp+38h+arg_8]
0x100479703  add     rsp, 30h
0x100479707  pop     rdi
0x100479708  retn
0x100479709  movzx   r8d, word ptr [rbx+36h]
0x10047970e  xor     edx, edx; Val
0x100479710  add     r8, r8; Size
0x100479713  mov     rcx, rax; void *
0x100479716  call    memset_0
0x10047971b  mov     rbx, [rsp+38h+arg_0]
0x100479720  mov     al, 1
0x100479722  mov     rsi, [rsp+38h+arg_8]
0x100479727  add     rsp, 30h
0x10047972b  pop     rdi
0x10047972c  retn
```

# ConstructDependencyGraph(CDynArray<CProviderEntry *,CDeallocateRelease> &,int * * *,ulong *)

- ea: `0x1800124ac`
- end: `0x180012789`
- name: `?ConstructDependencyGraph@@YAKAEAV?$CDynArray@PEAUCProviderEntry@@VCDeallocateRelease@@@@PEAPEAPEAHPEAK@Z`
- size: `733`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012790`

## callees

- `0x180001984`
- `0x180003944`
- `0x1800124ac`
- `0x18001c12a`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180012611`
- `msvcrt!_wcsicmp` at `0x180012611`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001275c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001277b`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001275c`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001277b`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012675`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800126d0`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180012675`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x1800126d0`

## string_xrefs

- `0x1800126b8`: `[%s] dependency %s not installed.`

## pseudocode

```c
__int64 __fastcall ConstructDependencyGraph(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned __int64 v3; // rsi
  unsigned int v4; // ebx
  __int64 v5; // r13
  unsigned __int64 v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // r14
  unsigned int v9; // ebp
  unsigned __int64 v10; // rcx
  _QWORD *v11; // rbx
  unsigned __int64 v12; // rax
  void *v13; // rax
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int v17; // r12d
  __int64 v18; // r15
  __int64 v19; // rdi
  unsigned int v20; // eax
  unsigned int v21; // ebp
  const wchar_t *v22; // r13
  __int64 v23; // r15
  __int64 v24; // rdx
  void **v26; // rdi
  __int64 v27; // [rsp+30h] [rbp-68h]
  __int64 v28; // [rsp+38h] [rbp-60h]
  __int64 v29; // [rsp+40h] [rbp-58h]
  unsigned int v33; // [rsp+B8h] [rbp+20h]

  v3 = *(unsigned int *)(a1 + 12);
  v4 = 0;
  v5 = a1;
  v6 = 8 * v3;
  if ( !is_mul_ok(v3, 8u) )
    v6 = -1;
  v7 = operator new[](v6, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    if ( (_DWORD)v3 )
    {
      memset_0(v7, 0, 8 * v3);
      v9 = 0;
      v10 = v3;
      v11 = v8;
      do
      {
        v12 = 4 * v10;
        if ( !is_mul_ok(v10, 4u) )
          v12 = -1;
        v13 = operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
        *v11 = v13;
        if ( !v13 )
        {
          v4 = 8;
          goto LABEL_36;
        }
        v14 = 0;
        v15 = v3;
        do
        {
          *(_DWORD *)(v14 + *v11) = 0;
          v14 += 4;
          --v15;
        }
        while ( v15 );
        ++v9;
        ++v11;
        v10 = v3;
      }
      while ( v9 < (unsigned int)v3 );
      v16 = 0;
      v27 = 0;
      v28 = 0;
      v17 = 0;
      v18 = 0;
      while ( 1 )
      {
        v19 = 0;
        v4 = 0;
        if ( v17 < *(_DWORD *)(v5 + 12) )
          v19 = *(_QWORD *)(v16 + *(_QWORD *)v5);
        else
          v4 = 1413;
        if ( (unsigned int)ElValidateWin32(v4, v15, "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp", 142) )
          break;
        v20 = 0;
        v33 = 0;
        if ( *(_DWORD *)(v19 + 40) )
        {
          do
          {
            v21 = 0;
            v22 = *(const wchar_t **)(*(_QWORD *)(v19 + 32) + 8LL * v20);
            if ( v22 && *v22 )
            {
              v23 = 0;
              while ( 1 )
              {
                v29 = *(_QWORD *)(v23 + *(_QWORD *)a1);
                if ( !_wcsicmp(*(const wchar_t **)(v29 + 16), v22) )
                  break;
                ++v21;
                v23 += 8;
                if ( v21 >= (unsigned int)v3 )
                {
                  v18 = v27;
                  goto LABEL_28;
                }
              }
              v18 = v27;
              *(_DWORD *)(v27 + v8[v21]) = 1;
              if ( !*(_DWORD *)(v19 + 24) )
              {
                if ( *(_DWORD *)(v29 + 24) )
                {
                  CTrace::Trace(
                    (CTrace *)qword_180039310,
                    0x100000u,
                    L"[%s] A required provider %s is not enabled.",
                    *(_QWORD *)(v19 + 16),
                    v22);
                  v4 = 1610;
                  if ( (unsigned int)ElValidateWin32(
                                       1610,
                                       v24,
                                       "base\\eco\\wds\\wdssrv\\server\\src\\wdsprovhdl.cpp",
                                       185) )
                    goto LABEL_36;
                }
              }
LABEL_28:
              if ( v21 == *(_DWORD *)(a1 + 12) )
                CTrace::Trace(
                  (CTrace *)qword_180039310,
                  0x40000u,
                  L"[%s] dependency %s not installed.",
                  *(_QWORD *)(v19 + 16),
                  v22);
            }
            v20 = v33 + 1;
            v33 = v20;
          }
          while ( v20 < *(_DWORD *)(v19 + 40) );
          v5 = a1;
        }
        v18 += 4;
        v16 = v28 + 8;
        v27 = v18;
        ++v17;
        v28 += 8;
        if ( v17 >= (unsigned int)v3 )
          goto LABEL_33;
      }
LABEL_36:
      v26 = (void **)v8;
      do
      {
        if ( *v26 )
        {
          WdsPrivateHpFree(*v26);
          *v26 = 0;
        }
        ++v26;
        --v3;
      }
      while ( v3 );
      WdsPrivateHpFree(v8);
    }
    else
    {
LABEL_33:
      *a2 = v8;
      *a3 = v3;
    }
  }
  else
  {
    return 8;
  }
  return v4;
}

```

## disassembly

```asm
0x1800124ac  mov     [rsp+arg_10], r8
0x1800124b1  mov     [rsp+arg_8], rdx
0x1800124b6  mov     [rsp+arg_0], rcx
0x1800124bb  push    rbx
0x1800124bc  push    rbp
0x1800124bd  push    rsi
0x1800124be  push    rdi
0x1800124bf  push    r12
0x1800124c1  push    r13
0x1800124c3  push    r14
0x1800124c5  push    r15
0x1800124c7  sub     rsp, 58h
0x1800124cb  mov     esi, [rcx+0Ch]
0x1800124ce  xor     ebx, ebx
0x1800124d0  mov     r13, rcx
0x1800124d3  mov     edi, esi
0x1800124d5  lea     eax, [rbx+8]
0x1800124d8  mul     rsi
0x1800124db  lea     r15, [rbx-1]
0x1800124df  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800124e6  cmovo   rax, r15
0x1800124ea  mov     rcx, rax; unsigned __int64
0x1800124ed  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800124f2  mov     r14, rax
0x1800124f5  test    rax, rax
0x1800124f8  jnz     short loc_180012502
0x1800124fa  lea     ebx, [rax+8]
0x1800124fd  jmp     loc_180012738
0x180012502  test    esi, esi
0x180012504  jz      loc_180012723
0x18001250a  mov     r8, rdi
0x18001250d  xor     edx, edx; Val
0x18001250f  shl     r8, 3; Size
0x180012513  mov     rcx, r14; void *
0x180012516  call    memset_0
0x18001251b  xor     ebp, ebp
0x18001251d  mov     rcx, rdi
0x180012520  mov     rbx, r14
0x180012523  mov     eax, 4
0x180012528  mul     rcx
0x18001252b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012532  cmovo   rax, r15
0x180012536  mov     rcx, rax; unsigned __int64
0x180012539  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001253e  xor     r8d, r8d
0x180012541  mov     [rbx], rax
0x180012544  test    rax, rax
0x180012547  jz      loc_18001274C
0x18001254d  mov     ecx, r8d
0x180012550  mov     rdx, rdi
0x180012553  mov     rax, [rbx]
0x180012556  mov     [rcx+rax], r8d
0x18001255a  lea     rcx, [rcx+4]
0x18001255e  sub     rdx, 1
0x180012562  jnz     short loc_180012553
0x180012564  inc     ebp
0x180012566  add     rbx, 8
0x18001256a  mov     rcx, rdi
0x18001256d  cmp     ebp, esi
0x18001256f  jb      short loc_180012523
0x180012571  mov     rcx, r8
0x180012574  mov     [rsp+98h+var_68], r8
0x180012579  mov     [rsp+98h+var_60], rcx
0x18001257e  mov     r12d, r8d
0x180012581  mov     r15, r8
0x180012584  mov     rdi, r8
0x180012587  mov     ebx, r8d
0x18001258a  cmp     r12d, [r13+0Ch]
0x18001258e  jb      short loc_180012597
0x180012590  mov     ebx, 585h
0x180012595  jmp     short loc_18001259F
0x180012597  mov     rax, [r13+0]
0x18001259b  mov     rdi, [rcx+rax]
0x18001259f  mov     r9d, 8Eh
0x1800125a5  lea     r8, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x1800125ac  mov     ecx, ebx
0x1800125ae  call    ElValidateWin32
0x1800125b3  xor     r8d, r8d
0x1800125b6  test    eax, eax
0x1800125b8  jnz     loc_180012751
0x1800125be  mov     eax, r8d
0x1800125c1  mov     [rsp+98h+arg_18], eax
0x1800125c8  cmp     [rdi+28h], r8d
0x1800125cc  jbe     loc_180012700
0x1800125d2  mov     ecx, eax
0x1800125d4  mov     ebp, r8d
0x1800125d7  mov     rax, [rdi+20h]
0x1800125db  mov     r13, [rax+rcx*8]
0x1800125df  test    r13, r13
0x1800125e2  jz      loc_1800126DF
0x1800125e8  cmp     [r13+0], r8w
0x1800125ed  jz      loc_1800126DF
0x1800125f3  mov     r15, r8
0x1800125f6  mov     rax, [rsp+98h+arg_0]
0x1800125fe  mov     rdx, r13; String2
0x180012601  mov     rax, [rax]
0x180012604  mov     rax, [r15+rax]
0x180012608  mov     [rsp+98h+var_58], rax
0x18001260d  mov     rcx, [rax+10h]; String1
0x180012611  call    cs:__imp__wcsicmp
0x180012618  nop     dword ptr [rax+rax+00h]
0x18001261d  xor     r8d, r8d
0x180012620  test    eax, eax
0x180012622  jz      short loc_180012635
0x180012624  inc     ebp
0x180012626  add     r15, 8
0x18001262a  cmp     ebp, esi
0x18001262c  jb      short loc_1800125F6
0x18001262e  mov     r15, [rsp+98h+var_68]
0x180012633  jmp     short loc_1800126A7
0x180012635  mov     r15, [rsp+98h+var_68]
0x18001263a  mov     eax, ebp
0x18001263c  mov     rcx, [r14+rax*8]
0x180012640  mov     dword ptr [r15+rcx], 1
0x180012648  cmp     [rdi+18h], r8d
0x18001264c  jnz     short loc_1800126A7
0x18001264e  mov     rax, [rsp+98h+var_58]
0x180012653  cmp     [rax+18h], r8d
0x180012657  jz      short loc_1800126A7
0x180012659  mov     r9, [rdi+10h]
0x18001265d  lea     r8, aSARequiredProv; "[%s] A required provider %s is not enab"...
0x180012664  mov     edx, 100000h
0x180012669  mov     [rsp+98h+var_78], r13
0x18001266e  lea     rcx, qword_180039310
0x180012675  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18001267c  nop     dword ptr [rax+rax+00h]
0x180012681  mov     eax, 64Ah
0x180012686  lea     r8, aBaseEcoWdsWdss_16; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x18001268d  mov     ecx, eax
0x18001268f  mov     r9d, 0B9h
0x180012695  mov     ebx, eax
0x180012697  call    ElValidateWin32
0x18001269c  xor     r8d, r8d
0x18001269f  test    eax, eax
0x1800126a1  jnz     loc_180012751
0x1800126a7  mov     rax, [rsp+98h+arg_0]
0x1800126af  cmp     ebp, [rax+0Ch]
0x1800126b2  jnz     short loc_1800126DF
0x1800126b4  mov     r9, [rdi+10h]
0x1800126b8  lea     r8, aSDependencySNo; "[%s] dependency %s not installed."
0x1800126bf  mov     edx, 40000h
0x1800126c4  mov     [rsp+98h+var_78], r13
0x1800126c9  lea     rcx, qword_180039310
0x1800126d0  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x1800126d7  nop     dword ptr [rax+rax+00h]
0x1800126dc  xor     r8d, r8d
0x1800126df  mov     eax, [rsp+98h+arg_18]
0x1800126e6  inc     eax
0x1800126e8  mov     [rsp+98h+arg_18], eax
0x1800126ef  cmp     eax, [rdi+28h]
0x1800126f2  jb      loc_1800125D2
0x1800126f8  mov     r13, [rsp+98h+arg_0]
0x180012700  mov     rcx, [rsp+98h+var_60]
0x180012705  add     r15, 4
0x180012709  add     rcx, 8
0x18001270d  mov     [rsp+98h+var_68], r15
0x180012712  inc     r12d
0x180012715  mov     [rsp+98h+var_60], rcx
0x18001271a  cmp     r12d, esi
0x18001271d  jb      loc_180012584
0x180012723  mov     rax, [rsp+98h+arg_8]
0x18001272b  mov     [rax], r14
0x18001272e  mov     rax, [rsp+98h+arg_10]
0x180012736  mov     [rax], esi
0x180012738  mov     eax, ebx
0x18001273a  add     rsp, 58h
0x18001273e  pop     r15
0x180012740  pop     r14
0x180012742  pop     r13
0x180012744  pop     r12
0x180012746  pop     rdi
0x180012747  pop     rsi
0x180012748  pop     rbp
0x180012749  pop     rbx
0x18001274a  retn
0x18001274c  mov     ebx, 8
0x180012751  mov     rdi, r14
0x180012754  mov     rcx, [rdi]
0x180012757  test    rcx, rcx
0x18001275a  jz      short loc_18001276E
0x18001275c  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180012763  nop     dword ptr [rax+rax+00h]
0x180012768  xor     r8d, r8d
0x18001276b  mov     [rdi], r8
0x18001276e  add     rdi, 8
0x180012772  sub     rsi, 1
0x180012776  jnz     short loc_180012754
0x180012778  mov     rcx, r14
0x18001277b  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x180012782  nop     dword ptr [rax+rax+00h]
0x180012787  jmp     short loc_180012738
```

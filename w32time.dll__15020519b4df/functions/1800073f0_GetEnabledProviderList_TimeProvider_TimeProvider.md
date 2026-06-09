# GetEnabledProviderList(TimeProvider * *,TimeProvider * *)

- ea: `0x1800073f0`
- end: `0x1800077eb`
- name: `?GetEnabledProviderList@@YAJPEAPEAUTimeProvider@@0@Z`
- size: `1019`
- prototype: `__int64 __fastcall(struct TimeProvider **, struct TimeProvider **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008930`

## callees

- `0x180007038`
- `0x1800073f0`
- `0x180007800`
- `0x180008520`
- `0x18000885c`
- `0x180009238`
- `0x180018138`
- `0x18001d9a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000770c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000775a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000770c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000775a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000750a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000750a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000751a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007529`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000757f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800074af`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000757f`

## string_xrefs

- `0x180007799`: `ValidateProviderList : Enabled list of providers is invalid due to incompatibility among them. ValidateProviderList failed with error 0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetEnabledProviderList(struct TimeProvider **a1, struct TimeProvider **a2)
{
  struct TimeProvider *v2; // rbp
  struct TimeProvider *v3; // r12
  int PreferenceEnabledProviderListp; // eax
  _QWORD *v5; // r14
  unsigned int v6; // ebx
  HLOCAL *v7; // rsi
  int PolicyEnabledProviderListp; // eax
  _DWORD *v9; // r13
  _QWORD *v10; // r15
  _QWORD *i; // rbx
  HLOCAL *v12; // rbx
  char v13; // r12
  _DWORD *k; // rdi
  _OWORD *v15; // rax
  HLOCAL v16; // rcx
  HLOCAL *v17; // rdi
  char v19; // r12
  _QWORD *j; // rdi
  _OWORD *v21; // rax
  struct TimeProvider *v22; // rcx
  struct TimeProvider *m; // rax
  struct TimeProvider *n; // rbx
  HLOCAL hMem; // [rsp+20h] [rbp-68h] BYREF
  HLOCAL v26; // [rsp+28h] [rbp-60h] BYREF
  HLOCAL v27; // [rsp+30h] [rbp-58h] BYREF
  struct TimeProvider *v30; // [rsp+A0h] [rbp+18h]
  HLOCAL v31; // [rsp+A8h] [rbp+20h] BYREF

  v26 = 0;
  v2 = 0;
  v27 = 0;
  v3 = 0;
  v31 = 0;
  hMem = 0;
  v30 = 0;
  PreferenceEnabledProviderListp = GetPreferenceEnabledProviderListp(
                                     (struct TimeProvider **)&v31,
                                     (struct TimeProvider **)&hMem);
  v5 = v31;
  v6 = PreferenceEnabledProviderListp;
  v7 = (HLOCAL *)hMem;
  if ( PreferenceEnabledProviderListp >= 0 )
  {
    PolicyEnabledProviderListp = GetPolicyEnabledProviderListp(
                                   (struct TimeProvider **)&v26,
                                   (struct TimeProvider **)&v27);
    v9 = v26;
    v6 = PolicyEnabledProviderListp;
    v10 = v27;
    if ( PolicyEnabledProviderListp >= 0 )
    {
      for ( i = v5; i; i = (_QWORD *)i[3] )
      {
        v19 = 1;
        for ( j = v10; j; j = (_QWORD *)j[3] )
        {
          if ( !(unsigned int)_o__wcsicmp(i[1], j[1]) )
          {
            v19 = 0;
            *((_DWORD *)i + 23) = *((_DWORD *)j + 23);
            *((_DWORD *)i + 24) = v9[24];
            break;
          }
        }
        v21 = LocalAlloc(0x40u, 0x78u);
        if ( !v21 )
        {
LABEL_10:
          v6 = -2147024882;
          goto LABEL_11;
        }
        *v21 = *(_OWORD *)i;
        v21[1] = *((_OWORD *)i + 1);
        v21[2] = *((_OWORD *)i + 2);
        v21[3] = *((_OWORD *)i + 3);
        v21[4] = *((_OWORD *)i + 4);
        v21[5] = *((_OWORD *)i + 5);
        v21[6] = *((_OWORD *)i + 6);
        *((_QWORD *)v21 + 14) = i[14];
        i[1] = 0;
        *i = 0;
        if ( v19 )
        {
          v3 = v30;
          v22 = v2;
          v2 = (struct TimeProvider *)v21;
        }
        else
        {
          v22 = v30;
          v3 = (struct TimeProvider *)v21;
          v30 = (struct TimeProvider *)v21;
        }
        *((_QWORD *)v21 + 3) = v22;
      }
      v12 = v7;
      while ( v12 )
      {
        v13 = 0;
        for ( k = v9; k; k = (_DWORD *)*((_QWORD *)k + 3) )
        {
          if ( !(unsigned int)_o__wcsicmp(v12[1], *((_QWORD *)k + 1)) )
          {
            v13 = 1;
            *((_DWORD *)v12 + 23) = k[23];
            *((_DWORD *)v12 + 24) = v9[24];
            break;
          }
        }
        v15 = LocalAlloc(0x40u, 0x78u);
        if ( !v15 )
          goto LABEL_10;
        *v15 = *(_OWORD *)v12;
        v15[1] = *((_OWORD *)v12 + 1);
        v15[2] = *((_OWORD *)v12 + 2);
        v15[3] = *((_OWORD *)v12 + 3);
        v15[4] = *((_OWORD *)v12 + 4);
        v15[5] = *((_OWORD *)v12 + 5);
        v15[6] = *((_OWORD *)v12 + 6);
        *((_QWORD *)v15 + 14) = v12[14];
        v12[1] = 0;
        *v12 = 0;
        if ( v13 )
        {
          v3 = v30;
          *((_QWORD *)v15 + 3) = v2;
          v2 = (struct TimeProvider *)v15;
          v12 = (HLOCAL *)v12[3];
        }
        else
        {
          v3 = (struct TimeProvider *)v15;
          *((_QWORD *)v15 + 3) = v30;
          v12 = (HLOCAL *)v12[3];
          v30 = (struct TimeProvider *)v15;
        }
      }
      v6 = ValidateProviderList(v2);
      if ( v6 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(0) )
          FileLogAdd(
            L"ValidateProviderList : Enabled list of providers is invalid due to incompatibility among them. ValidateProvi"
             "derList failed with error 0x%08x\n",
            v6);
      }
      else
      {
        for ( m = v2; m; m = (struct TimeProvider *)*((_QWORD *)m + 3) )
        {
          if ( !*(_QWORD *)m )
          {
            v6 = -2147024894;
            goto LABEL_11;
          }
        }
        for ( n = v2; n; n = (struct TimeProvider *)*((_QWORD *)n + 3) )
          LogProviderInformation(*(const unsigned __int16 **)n, *((_BYTE *)n + 16), *((_BYTE *)n + 17));
        v6 = 0;
        v30 = 0;
        *a1 = v2;
        v2 = 0;
        *a2 = v3;
      }
    }
LABEL_11:
    if ( v9 )
      FreeTimeProviderList(v9);
    if ( v10 )
      FreeTimeProviderList(v10);
    v3 = v30;
  }
  if ( v5 )
    FreeTimeProviderList(v5);
  while ( v7 )
  {
    v16 = *v7;
    v17 = v7;
    v7 = (HLOCAL *)v7[3];
    LocalFree(v16);
    LocalFree(v17[1]);
    LocalFree(v17);
  }
  if ( v2 )
    FreeTimeProviderList(v2);
  if ( v3 )
    FreeTimeProviderList(v3);
  return v6;
}

```

## disassembly

```asm
0x1800073f0  mov     rax, rsp
0x1800073f3  mov     [rax+10h], rdx
0x1800073f7  mov     [rax+8], rcx
0x1800073fb  push    rbx
0x1800073fc  push    r12
0x1800073fe  sub     rsp, 78h
0x180007402  mov     [rax-18h], rbp
0x180007406  lea     rdx, [rax-68h]; struct TimeProvider **
0x18000740a  mov     [rax-20h], rsi
0x18000740e  lea     rcx, [rax+20h]; struct TimeProvider **
0x180007412  mov     [rax-28h], rdi
0x180007416  xor     edi, edi
0x180007418  mov     [rax-60h], rdi
0x18000741c  mov     ebp, edi
0x18000741e  mov     [rax-58h], rdi
0x180007422  mov     r12d, edi
0x180007425  mov     [rax+20h], rdi
0x180007429  mov     [rax-68h], rdi
0x18000742d  mov     [rsp+88h+arg_10], rdi
0x180007435  mov     [rax-38h], r14
0x180007439  call    ?GetPreferenceEnabledProviderListp@@YAJPEAPEAUTimeProvider@@0@Z; GetPreferenceEnabledProviderListp(TimeProvider * *,TimeProvider * *)
0x18000743e  mov     r14, [rsp+88h+arg_18]
0x180007446  mov     ebx, eax
0x180007448  mov     rsi, [rsp+88h+hMem]
0x18000744d  test    eax, eax
0x18000744f  js      loc_1800074ED
0x180007455  mov     [rsp+88h+var_30], r13
0x18000745a  lea     rdx, [rsp+88h+var_58]; struct TimeProvider **
0x18000745f  lea     rcx, [rsp+88h+var_60]; struct TimeProvider **
0x180007464  mov     [rsp+88h+var_40], r15
0x180007469  call    ?GetPolicyEnabledProviderListp@@YAJPEAPEAUTimeProvider@@0@Z; GetPolicyEnabledProviderListp(TimeProvider * *,TimeProvider * *)
0x18000746e  mov     r13, [rsp+88h+var_60]
0x180007473  mov     ebx, eax
0x180007475  mov     r15, [rsp+88h+var_58]
0x18000747a  test    eax, eax
0x18000747c  js      short loc_1800074C9
0x18000747e  mov     rbx, r14
0x180007481  test    rbx, rbx
0x180007484  jnz     loc_180007566
0x18000748a  mov     rbx, rsi
0x18000748d  test    rbx, rbx
0x180007490  jz      loc_18000766F
0x180007496  xor     r12b, r12b
0x180007499  mov     rdi, r13
0x18000749c  test    rdi, rdi
0x18000749f  jnz     loc_180007752
0x1800074a5  mov     edx, 78h ; 'x'; uBytes
0x1800074aa  mov     ecx, 40h ; '@'; uFlags
0x1800074af  call    cs:__imp_LocalAlloc
0x1800074b6  nop     dword ptr [rax+rax+00h]
0x1800074bb  test    rax, rax
0x1800074be  jnz     loc_180007601
0x1800074c4  mov     ebx, 8007000Eh
0x1800074c9  test    r13, r13
0x1800074cc  jnz     loc_1800077AA
0x1800074d2  mov     r13, [rsp+88h+var_30]
0x1800074d7  test    r15, r15
0x1800074da  jnz     loc_1800077B7
0x1800074e0  mov     r12, [rsp+88h+arg_10]
0x1800074e8  mov     r15, [rsp+88h+var_40]
0x1800074ed  test    r14, r14
0x1800074f0  jnz     loc_1800077C4
0x1800074f6  mov     r14, [rsp+88h+var_38]
0x1800074fb  test    rsi, rsi
0x1800074fe  jz      short loc_18000753A
0x180007500  mov     rcx, [rsi]; hMem
0x180007503  mov     rdi, rsi
0x180007506  mov     rsi, [rsi+18h]
0x18000750a  call    cs:__imp_LocalFree
0x180007511  nop     dword ptr [rax+rax+00h]
0x180007516  mov     rcx, [rdi+8]; hMem
0x18000751a  call    cs:__imp_LocalFree
0x180007521  nop     dword ptr [rax+rax+00h]
0x180007526  mov     rcx, rdi; hMem
0x180007529  call    cs:__imp_LocalFree
0x180007530  nop     dword ptr [rax+rax+00h]
0x180007535  test    rsi, rsi
0x180007538  jnz     short loc_180007500
0x18000753a  mov     rdi, [rsp+88h+var_28]
0x18000753f  mov     rsi, [rsp+88h+var_20]
0x180007544  test    rbp, rbp
0x180007547  jnz     loc_1800077D1
0x18000754d  mov     rbp, [rsp+88h+var_18]
0x180007552  test    r12, r12
0x180007555  jnz     loc_1800077DE
0x18000755b  mov     eax, ebx
0x18000755d  add     rsp, 78h
0x180007561  pop     r12
0x180007563  pop     rbx
0x180007564  retn
0x180007566  mov     r12b, 1
0x180007569  mov     rdi, r15
0x18000756c  test    rdi, rdi
0x18000756f  jnz     loc_180007704
0x180007575  mov     edx, 78h ; 'x'; uBytes
0x18000757a  mov     ecx, 40h ; '@'; uFlags
0x18000757f  call    cs:__imp_LocalAlloc
0x180007586  nop     dword ptr [rax+rax+00h]
0x18000758b  test    rax, rax
0x18000758e  jz      loc_1800074C4
0x180007594  movups  xmm0, xmmword ptr [rbx]
0x180007597  xor     edi, edi
0x180007599  movups  xmmword ptr [rax], xmm0
0x18000759c  movups  xmm1, xmmword ptr [rbx+10h]
0x1800075a0  movups  xmmword ptr [rax+10h], xmm1
0x1800075a4  movups  xmm0, xmmword ptr [rbx+20h]
0x1800075a8  movups  xmmword ptr [rax+20h], xmm0
0x1800075ac  movups  xmm1, xmmword ptr [rbx+30h]
0x1800075b0  movups  xmmword ptr [rax+30h], xmm1
0x1800075b4  movups  xmm0, xmmword ptr [rbx+40h]
0x1800075b8  movups  xmmword ptr [rax+40h], xmm0
0x1800075bc  movups  xmm1, xmmword ptr [rbx+50h]
0x1800075c0  movups  xmmword ptr [rax+50h], xmm1
0x1800075c4  movups  xmm0, xmmword ptr [rbx+60h]
0x1800075c8  movups  xmmword ptr [rax+60h], xmm0
0x1800075cc  movsd   xmm1, qword ptr [rbx+70h]
0x1800075d1  movsd   qword ptr [rax+70h], xmm1
0x1800075d6  mov     [rbx+8], rdi
0x1800075da  mov     [rbx], rdi
0x1800075dd  test    r12b, r12b
0x1800075e0  jz      loc_18000773A
0x1800075e6  mov     r12, [rsp+88h+arg_10]
0x1800075ee  mov     rcx, rbp
0x1800075f1  mov     rbp, rax
0x1800075f4  mov     [rax+18h], rcx
0x1800075f8  mov     rbx, [rbx+18h]
0x1800075fc  jmp     loc_180007481
0x180007601  movups  xmm0, xmmword ptr [rbx]
0x180007604  xor     edi, edi
0x180007606  movups  xmmword ptr [rax], xmm0
0x180007609  movups  xmm1, xmmword ptr [rbx+10h]
0x18000760d  movups  xmmword ptr [rax+10h], xmm1
0x180007611  movups  xmm0, xmmword ptr [rbx+20h]
0x180007615  movups  xmmword ptr [rax+20h], xmm0
0x180007619  movups  xmm1, xmmword ptr [rbx+30h]
0x18000761d  movups  xmmword ptr [rax+30h], xmm1
0x180007621  movups  xmm0, xmmword ptr [rbx+40h]
0x180007625  movups  xmmword ptr [rax+40h], xmm0
0x180007629  movups  xmm1, xmmword ptr [rbx+50h]
0x18000762d  movups  xmmword ptr [rax+50h], xmm1
0x180007631  movups  xmm0, xmmword ptr [rbx+60h]
0x180007635  movups  xmmword ptr [rax+60h], xmm0
0x180007639  movsd   xmm1, qword ptr [rbx+70h]
0x18000763e  movsd   qword ptr [rax+70h], xmm1
0x180007643  mov     [rbx+8], rdi
0x180007647  mov     [rbx], rdi
0x18000764a  test    r12b, r12b
0x18000764d  jnz     short loc_18000769F
0x18000764f  mov     rcx, [rsp+88h+arg_10]
0x180007657  mov     r12, rax
0x18000765a  mov     [rax+18h], rcx
0x18000765e  mov     rbx, [rbx+18h]
0x180007662  mov     [rsp+88h+arg_10], rax
0x18000766a  jmp     loc_18000748D
0x18000766f  mov     rcx, rbp; struct TimeProvider *
0x180007672  call    ?ValidateProviderList@@YAJPEAUTimeProvider@@@Z; ValidateProviderList(TimeProvider *)
0x180007677  mov     ebx, eax
0x180007679  test    eax, eax
0x18000767b  jnz     loc_180007788
0x180007681  mov     rax, rbp
0x180007684  test    rax, rax
0x180007687  jz      short loc_1800076BA
0x180007689  cmp     qword ptr [rax], 0
0x18000768d  jz      short loc_180007695
0x18000768f  mov     rax, [rax+18h]
0x180007693  jmp     short loc_180007684
0x180007695  mov     ebx, 80070002h
0x18000769a  jmp     loc_1800074C9
0x18000769f  mov     r12, [rsp+88h+arg_10]
0x1800076a7  mov     rcx, rbp
0x1800076aa  mov     [rax+18h], rcx
0x1800076ae  mov     rbp, rax
0x1800076b1  mov     rbx, [rbx+18h]
0x1800076b5  jmp     loc_18000748D
0x1800076ba  mov     rbx, rbp
0x1800076bd  test    rbp, rbp
0x1800076c0  jz      short loc_1800076DC
0x1800076c2  movzx   r8d, byte ptr [rbx+11h]; bool
0x1800076c7  movzx   edx, byte ptr [rbx+10h]; bool
0x1800076cb  mov     rcx, [rbx]; unsigned __int16 *
0x1800076ce  call    ?LogProviderInformation@@YAXPEBG_N1@Z; LogProviderInformation(ushort const *,bool,bool)
0x1800076d3  mov     rbx, [rbx+18h]
0x1800076d7  test    rbx, rbx
0x1800076da  jnz     short loc_1800076C2
0x1800076dc  mov     rax, [rsp+88h+arg_0]
0x1800076e4  mov     ebx, edi
0x1800076e6  mov     [rsp+88h+arg_10], rdi
0x1800076ee  mov     [rax], rbp
0x1800076f1  mov     rbp, rdi
0x1800076f4  mov     rax, [rsp+88h+arg_8]
0x1800076fc  mov     [rax], r12
0x1800076ff  jmp     loc_1800074C9
0x180007704  mov     rdx, [rdi+8]
0x180007708  mov     rcx, [rbx+8]
0x18000770c  call    cs:__imp__o__wcsicmp
0x180007713  nop     dword ptr [rax+rax+00h]
0x180007718  test    eax, eax
0x18000771a  jz      short loc_180007725
0x18000771c  mov     rdi, [rdi+18h]
0x180007720  jmp     loc_18000756C
0x180007725  mov     eax, [rdi+5Ch]
0x180007728  xor     r12b, r12b
0x18000772b  mov     [rbx+5Ch], eax
0x18000772e  mov     eax, [r13+60h]
0x180007732  mov     [rbx+60h], eax
0x180007735  jmp     loc_180007575
0x18000773a  mov     rcx, [rsp+88h+arg_10]
0x180007742  mov     r12, rax
0x180007745  mov     [rsp+88h+arg_10], rax
0x18000774d  jmp     loc_1800075F4
0x180007752  mov     rdx, [rdi+8]
0x180007756  mov     rcx, [rbx+8]
0x18000775a  call    cs:__imp__o__wcsicmp
0x180007761  nop     dword ptr [rax+rax+00h]
0x180007766  test    eax, eax
0x180007768  jz      short loc_180007773
0x18000776a  mov     rdi, [rdi+18h]
0x18000776e  jmp     loc_18000749C
0x180007773  mov     eax, [rdi+5Ch]
0x180007776  mov     r12b, 1
0x180007779  mov     [rbx+5Ch], eax
0x18000777c  mov     eax, [r13+60h]
0x180007780  mov     [rbx+60h], eax
0x180007783  jmp     loc_1800074A5
0x180007788  xor     ecx, ecx
0x18000778a  call    FileLogAllowEntry
0x18000778f  test    al, al
0x180007791  jz      loc_1800074C9
0x180007797  mov     edx, ebx
0x180007799  lea     rcx, aValidateprovid; "ValidateProviderList : Enabled list of "...
0x1800077a0  call    FileLogAdd
0x1800077a5  jmp     loc_1800074C9
0x1800077aa  mov     rcx, r13; hMem
0x1800077ad  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800077b2  jmp     loc_1800074D2
0x1800077b7  mov     rcx, r15; hMem
0x1800077ba  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800077bf  jmp     loc_1800074E0
0x1800077c4  mov     rcx, r14; hMem
0x1800077c7  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800077cc  jmp     loc_1800074F6
0x1800077d1  mov     rcx, rbp; hMem
0x1800077d4  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800077d9  jmp     loc_18000754D
0x1800077de  mov     rcx, r12; hMem
0x1800077e1  call    ?FreeTimeProviderList@@YAXPEAUTimeProvider@@@Z; FreeTimeProviderList(TimeProvider *)
0x1800077e6  jmp     loc_18000755B
```

# LogElfEvent

- ea: `0x1800771dc`
- end: `0x1800775af`
- name: `LogElfEvent`
- size: `979`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, void *Src, size_t)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x18005eda4`
- `0x180087a88`
- `0x18008cca0`
- `0x180093d78`
- `0x1800c2410`
- `0x1800c2528`

## callees

- `0x180006f50`
- `0x180006fb0`
- `0x180018374`
- `0x18002d3e4`
- `0x180030374`
- `0x1800472e4`
- `0x1800771dc`
- `0x180092ee4`
- `0x1800d3370`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077472`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180077472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180077538`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180077538`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077541`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077541`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180077211`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x180077211`

## pseudocode

```c
PVOID *__fastcall LogElfEvent(
        unsigned int a1,
        __int16 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        void *Src,
        size_t a7)
{
  unsigned int v7; // ebx
  __int64 v8; // r8
  unsigned __int16 v9; // di
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int16 v12; // ax
  _QWORD *v13; // rcx
  PVOID *result; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rsi
  unsigned int v18; // r15d
  unsigned int v19; // eax
  unsigned int v20; // r13d
  int v21; // ecx
  unsigned int v22; // r14d
  unsigned int v23; // r12d
  unsigned int *v24; // rbx
  unsigned int v25; // r12d
  char *v26; // rsi
  char *v27; // r15
  __int64 v28; // rax
  __int64 v29; // rdi
  char *v30; // rdi
  unsigned int *v31; // [rsp+20h] [rbp-58h] BYREF
  unsigned int v32; // [rsp+28h] [rbp-50h]
  unsigned int v33; // [rsp+2Ch] [rbp-4Ch]
  unsigned int Size; // [rsp+30h] [rbp-48h]
  int Size_4; // [rsp+34h] [rbp-44h]
  __int64 v36; // [rsp+38h] [rbp-40h] BYREF
  struct LOGMODULE *v37; // [rsp+40h] [rbp-38h] BYREF
  __int128 v38; // [rsp+48h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-20h]
  unsigned int v42; // [rsp+D0h] [rbp+58h]

  v7 = a4;
  v36 = 0;
  GetSystemTimePreciseAsFileTime(&v36);
  v8 = 0;
  v42 = v7;
  v9 = 0;
  while ( (unsigned int)v8 < v7 )
  {
    v10 = *(_QWORD *)(a5 + 8LL * (unsigned int)v8);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(v10 + 2 * v11) );
      v12 = v9 + v11 + 1;
      if ( v12 < v9 )
      {
        v13 = WPP_GLOBAL_Control;
        result = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 10;
          return (PVOID *)WPP_SF_(v13[2], v15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
        }
        return result;
      }
      v9 = v12;
    }
    v8 = (unsigned int)(v8 + 1);
  }
  v16 = (__int64)(*((_QWORD *)ElfModule + 1) - *(_QWORD *)ElfModule) >> 1;
  v17 = (unsigned int)(2 * v16 + 62);
  Size = 2 * v16 + 2;
  v18 = v17 + 2 * v9;
  v33 = v18;
  if ( v18 >= (unsigned int)v17 )
  {
    v19 = v18 + 4;
    if ( v18 + 4 >= v18 )
    {
      v20 = a7;
      v21 = v19 + a7;
      if ( v19 + (unsigned int)a7 >= (unsigned int)a7 )
      {
        v22 = 4 - (v21 & 3);
        v32 = v22;
        v23 = v22 + v21;
        Size_4 = v22 + v21;
        if ( v22 + v21 >= v22 )
        {
          tlx::make_unique_oversize_for_overwrite<_EVENTLOGRECORD,0>(&v31, v23, v8, 1);
          v24 = v31;
          if ( v31 )
          {
            *v31 = v23;
            v25 = 0;
            v24[3] = v36;
            v24[1] = 1699505740;
            v24[4] = HIDWORD(v36);
            v24[5] = a1;
            *((_WORD *)v24 + 12) = a2;
            *(_QWORD *)(v24 + 7) = 0;
            *((_WORD *)v24 + 13) = a4;
            v24[9] = v17;
            v24[12] = a7;
            v24[13] = v18;
            v24[10] = 0;
            v24[11] = v17;
            v26 = (char *)v24 + v17;
            if ( v42 )
            {
              v27 = v26;
              do
              {
                _o_wcscpy_s(v26, v9 - ((v26 - v27) >> 1), *(_QWORD *)(a5 + 8LL * v25));
                v28 = -1;
                do
                  ++v28;
                while ( *(_WORD *)(*(_QWORD *)(a5 + 8LL * v25) + 2 * v28) );
                ++v25;
                v26 += 2 * v28 + 2;
              }
              while ( v25 < v42 );
              v24 = v31;
              v22 = v32;
              v18 = v33;
              v20 = a7;
            }
            v29 = Size;
            memcpy_0(v24 + 14, *(const void **)ElfModule, Size);
            *(unsigned int *)((char *)v24 + v29 + 56) = 120;
            memcpy_0((char *)v24 + v18, Src, v20);
            v30 = (char *)v24 + v18 + v20;
            memcpy_0(v30, &dword_1800F4A6C, v22);
            *(_DWORD *)&v30[v22] = Size_4;
            v39 = 0;
            v37 = ElfModule;
            v38 = 0;
            utl::unique_ptr<_EVENTLOGRECORD,tlx::generic_delete<_EVENTLOGRECORD,tlx::operator_delete_deallocate>>::operator=(
              (char *)&v38 + 8,
              &v31);
            wmi::AutoRef<Publisher>::operator=(&v38, g_EventLogPublisher);
            LODWORD(v39) = GetCurrentProcessId();
            HIDWORD(v39) = GetCurrentThreadId();
            PerformWriteRequest((struct WRITE_PKT *)&v37);
            WRITE_PKT::~WRITE_PKT((WRITE_PKT *)&v37);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
          }
          return (PVOID *)utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v31);
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          result = &WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 14;
            return (PVOID *)WPP_SF_(v13[2], v15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
          }
        }
      }
      else
      {
        v13 = WPP_GLOBAL_Control;
        result = &WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 13;
          return (PVOID *)WPP_SF_(v13[2], v15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
        }
      }
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      result = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 12;
        return (PVOID *)WPP_SF_(v13[2], v15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
      }
    }
  }
  else
  {
    v13 = WPP_GLOBAL_Control;
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 11;
      return (PVOID *)WPP_SF_(v13[2], v15, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800771dc  mov     rax, rsp
0x1800771df  mov     [rax+20h], r9w
0x1800771e4  mov     [rax+18h], r8w
0x1800771e9  mov     [rax+10h], dx
0x1800771ed  mov     [rax+8], ecx
0x1800771f0  push    rbp
0x1800771f1  push    rbx
0x1800771f2  push    rsi
0x1800771f3  push    rdi
0x1800771f4  push    r12
0x1800771f6  push    r13
0x1800771f8  push    r14
0x1800771fa  push    r15
0x1800771fc  mov     rbp, rsp
0x1800771ff  sub     rsp, 78h
0x180077203  xor     esi, esi
0x180077205  movzx   ebx, r9w
0x180077209  lea     rcx, [rbp+var_40]
0x18007720d  mov     [rbp+var_40], rsi
0x180077211  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x180077217  mov     rdx, [rbp+arg_20]
0x18007721b  lea     r9d, [rsi+1]
0x18007721f  mov     r8d, esi
0x180077222  mov     [rbp+arg_10], ebx
0x180077225  mov     edi, esi
0x180077227  mov     eax, ebx
0x180077229  cmp     r8d, eax
0x18007722c  jnb     short loc_1800772A3
0x18007722e  mov     eax, r8d
0x180077231  mov     rcx, [rdx+rax*8]
0x180077235  test    rcx, rcx
0x180077238  jz      short loc_180077256
0x18007723a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007723e  inc     rax
0x180077241  cmp     [rcx+rax*2], si
0x180077245  jnz     short loc_18007723E
0x180077247  add     ax, di
0x18007724a  add     ax, r9w
0x18007724e  cmp     ax, di
0x180077251  jb      short loc_18007725B
0x180077253  movzx   edi, ax
0x180077256  add     r8d, r9d
0x180077259  jmp     short loc_180077227
0x18007725b  mov     rcx, cs:WPP_GLOBAL_Control
0x180077262  lea     rax, WPP_GLOBAL_Control
0x180077269  cmp     rcx, rax
0x18007726c  jz      loc_18007759E
0x180077272  test    dword ptr [rcx+1Ch], 1000h
0x180077279  jz      loc_18007759E
0x18007727f  cmp     byte ptr [rcx+19h], 2
0x180077283  jb      loc_18007759E
0x180077289  mov     edx, 0Ah
0x18007728e  mov     rcx, [rcx+10h]
0x180077292  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x180077299  call    WPP_SF_
0x18007729e  jmp     loc_18007759E
0x1800772a3  mov     rax, cs:?ElfModule@@3PEAULOGMODULE@@EA; LOGMODULE * ElfModule
0x1800772aa  mov     rcx, [rax+8]
0x1800772ae  sub     rcx, [rax]
0x1800772b1  sar     rcx, 1
0x1800772b4  lea     eax, ds:2[rcx*2]
0x1800772bb  lea     esi, [rax+3Ch]
0x1800772be  mov     dword ptr [rbp+Size], eax
0x1800772c1  movzx   eax, di
0x1800772c4  lea     r15d, [rsi+rax*2]
0x1800772c8  mov     [rbp+var_4C], r15d
0x1800772cc  cmp     r15d, esi
0x1800772cf  jnb     short loc_180077306
0x1800772d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800772d8  lea     rax, WPP_GLOBAL_Control
0x1800772df  cmp     rcx, rax
0x1800772e2  jz      loc_18007759E
0x1800772e8  test    dword ptr [rcx+1Ch], 1000h
0x1800772ef  jz      loc_18007759E
0x1800772f5  cmp     byte ptr [rcx+19h], 2
0x1800772f9  jb      loc_18007759E
0x1800772ff  mov     edx, 0Bh
0x180077304  jmp     short loc_18007728E
0x180077306  lea     eax, [r15+4]
0x18007730a  cmp     eax, r15d
0x18007730d  jnb     short loc_180077347
0x18007730f  mov     rcx, cs:WPP_GLOBAL_Control
0x180077316  lea     rax, WPP_GLOBAL_Control
0x18007731d  cmp     rcx, rax
0x180077320  jz      loc_18007759E
0x180077326  test    dword ptr [rcx+1Ch], 1000h
0x18007732d  jz      loc_18007759E
0x180077333  cmp     byte ptr [rcx+19h], 2
0x180077337  jb      loc_18007759E
0x18007733d  mov     edx, 0Ch
0x180077342  jmp     loc_18007728E
0x180077347  mov     r13d, dword ptr [rbp+arg_30]
0x18007734b  lea     ecx, [rax+r13]
0x18007734f  cmp     ecx, r13d
0x180077352  jnb     short loc_18007738C
0x180077354  mov     rcx, cs:WPP_GLOBAL_Control
0x18007735b  lea     rax, WPP_GLOBAL_Control
0x180077362  cmp     rcx, rax
0x180077365  jz      loc_18007759E
0x18007736b  test    dword ptr [rcx+1Ch], 1000h
0x180077372  jz      loc_18007759E
0x180077378  cmp     byte ptr [rcx+19h], 2
0x18007737c  jb      loc_18007759E
0x180077382  mov     edx, 0Dh
0x180077387  jmp     loc_18007728E
0x18007738c  mov     eax, ecx
0x18007738e  mov     r14d, 4
0x180077394  and     eax, 3
0x180077397  sub     r14d, eax
0x18007739a  mov     [rbp+var_50], r14d
0x18007739e  lea     r12d, [r14+rcx]
0x1800773a2  mov     dword ptr [rbp+Size+4], r12d
0x1800773a6  cmp     r12d, r14d
0x1800773a9  jnb     short loc_1800773E3
0x1800773ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800773b2  lea     rax, WPP_GLOBAL_Control
0x1800773b9  cmp     rcx, rax
0x1800773bc  jz      loc_18007759E
0x1800773c2  test    dword ptr [rcx+1Ch], 1000h
0x1800773c9  jz      loc_18007759E
0x1800773cf  cmp     byte ptr [rcx+19h], 2
0x1800773d3  jb      loc_18007759E
0x1800773d9  mov     edx, 0Eh
0x1800773de  jmp     loc_18007728E
0x1800773e3  mov     edx, r12d
0x1800773e6  lea     rcx, [rbp+var_58]
0x1800773ea  call    ??$make_unique_oversize_for_overwrite@U_EVENTLOGRECORD@@$0A@@tlx@@YA?AV?$unique_ptr@U_EVENTLOGRECORD@@U?$generic_delete@U_EVENTLOGRECORD@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@_K@Z; tlx::make_unique_oversize_for_overwrite<_EVENTLOGRECORD,0>(unsigned __int64)
0x1800773ef  mov     rbx, [rbp+var_58]
0x1800773f3  xor     ecx, ecx
0x1800773f5  test    rbx, rbx
0x1800773f8  jz      loc_18007755E
0x1800773fe  mov     [rbx], r12d
0x180077401  mov     r12d, ecx
0x180077404  mov     eax, dword ptr [rbp+var_40]
0x180077407  mov     [rbx+0Ch], eax
0x18007740a  mov     dword ptr [rbx+4], 654C664Ch
0x180077411  mov     eax, dword ptr [rbp+var_40+4]
0x180077414  mov     [rbx+10h], eax
0x180077417  mov     eax, [rbp+arg_0]
0x18007741a  mov     [rbx+14h], eax
0x18007741d  movzx   eax, [rbp+arg_8]
0x180077421  mov     [rbx+18h], ax
0x180077425  movzx   eax, [rbp+arg_18]
0x180077429  mov     [rbx+1Ch], rcx
0x18007742d  mov     [rbx+1Ah], ax
0x180077431  mov     [rbx+24h], esi
0x180077434  mov     [rbx+30h], r13d
0x180077438  mov     [rbx+34h], r15d
0x18007743c  mov     [rbx+28h], ecx
0x18007743f  mov     [rbx+2Ch], esi
0x180077442  add     rsi, rbx
0x180077445  cmp     [rbp+arg_10], ecx
0x180077448  jbe     short loc_1800774AB
0x18007744a  mov     r13d, [rbp+arg_10]
0x18007744e  mov     r15, rsi
0x180077451  mov     rbx, [rbp+arg_20]
0x180077455  movzx   r14d, di
0x180077459  mov     rax, rsi
0x18007745c  mov     edi, r12d
0x18007745f  sub     rax, r15
0x180077462  mov     rdx, r14
0x180077465  sar     rax, 1
0x180077468  mov     rcx, rsi
0x18007746b  sub     rdx, rax
0x18007746e  mov     r8, [rbx+rdi*8]
0x180077472  call    cs:__imp__o_wcscpy_s
0x180077478  mov     rcx, [rbx+rdi*8]
0x18007747c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077480  xor     edx, edx
0x180077482  inc     rax
0x180077485  cmp     [rcx+rax*2], dx
0x180077489  jnz     short loc_180077482
0x18007748b  lea     rsi, [rsi+rax*2]
0x18007748f  inc     r12d
0x180077492  add     rsi, 2
0x180077496  cmp     r12d, r13d
0x180077499  jb      short loc_180077459
0x18007749b  mov     rbx, [rbp+var_58]
0x18007749f  mov     r14d, [rbp+var_50]
0x1800774a3  mov     r15d, [rbp+var_4C]
0x1800774a7  mov     r13d, dword ptr [rbp+arg_30]
0x1800774ab  mov     rdx, cs:?ElfModule@@3PEAULOGMODULE@@EA; LOGMODULE * ElfModule
0x1800774b2  lea     rcx, [rbx+38h]; void *
0x1800774b6  mov     edi, dword ptr [rbp+Size]
0x1800774b9  mov     r8d, edi; Size
0x1800774bc  mov     rdx, [rdx]; Src
0x1800774bf  call    memcpy_0
0x1800774c4  mov     rdx, [rbp+Src]; Src
0x1800774c8  mov     dword ptr [rdi+rbx+38h], 78h ; 'x'
0x1800774d0  mov     edi, r15d
0x1800774d3  add     rdi, rbx
0x1800774d6  mov     r8d, r13d; Size
0x1800774d9  mov     rcx, rdi; void *
0x1800774dc  mov     ebx, r13d
0x1800774df  call    memcpy_0
0x1800774e4  add     rdi, rbx
0x1800774e7  mov     r8d, r14d; Size
0x1800774ea  mov     rcx, rdi; void *
0x1800774ed  mov     ebx, r14d
0x1800774f0  lea     rdx, dword_1800F4A6C; Src
0x1800774f7  call    memcpy_0
0x1800774fc  mov     eax, dword ptr [rbp+Size+4]
0x1800774ff  lea     rdx, [rbp+var_58]
0x180077503  mov     [rdi+rbx], eax
0x180077506  lea     rcx, [rbp+var_28]
0x18007750a  xor     eax, eax
0x18007750c  xorps   xmm0, xmm0
0x18007750f  mov     [rbp+var_20], rax
0x180077513  mov     rax, cs:?ElfModule@@3PEAULOGMODULE@@EA; LOGMODULE * ElfModule
0x18007751a  mov     [rbp+var_38], rax
0x18007751e  movdqu  xmmword ptr [rbp-30h], xmm0
0x180077523  call    ??4?$unique_ptr@U_EVENTLOGRECORD@@U?$generic_delete@U_EVENTLOGRECORD@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<_EVENTLOGRECORD,tlx::generic_delete<_EVENTLOGRECORD,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<_EVENTLOGRECORD,tlx::generic_delete<_EVENTLOGRECORD,tlx::operator_delete_deallocate>> &&)
0x180077528  mov     rdx, cs:?g_EventLogPublisher@@3V?$AutoRef@VPublisher@@@wmi@@A; wmi::AutoRef<Publisher> g_EventLogPublisher
0x18007752f  lea     rcx, [rbp+var_30]
0x180077533  call    ??4?$AutoRef@VPublisher@@@wmi@@QEAAAEAV01@PEAVPublisher@@@Z; wmi::AutoRef<Publisher>::operator=(Publisher *)
0x180077538  call    cs:__imp_GetCurrentProcessId
0x18007753e  mov     dword ptr [rbp+var_20], eax
0x180077541  call    cs:__imp_GetCurrentThreadId
0x180077547  lea     rcx, [rbp+var_38]; struct WRITE_PKT *
0x18007754b  mov     dword ptr [rbp+var_20+4], eax
0x18007754e  call    ?PerformWriteRequest@@YAJAEAUWRITE_PKT@@@Z; PerformWriteRequest(WRITE_PKT &)
0x180077553  lea     rcx, [rbp+var_38]; this
0x180077557  call    ??1WRITE_PKT@@QEAA@XZ; WRITE_PKT::~WRITE_PKT(void)
0x18007755c  jmp     short loc_180077595
0x18007755e  mov     rcx, cs:WPP_GLOBAL_Control
0x180077565  lea     rax, WPP_GLOBAL_Control
0x18007756c  cmp     rcx, rax
0x18007756f  jz      short loc_180077595
0x180077571  test    dword ptr [rcx+1Ch], 1000h
0x180077578  jz      short loc_180077595
0x18007757a  cmp     byte ptr [rcx+19h], 2
0x18007757e  jb      short loc_180077595
0x180077580  mov     rcx, [rcx+10h]
0x180077584  lea     r8, WPP_2c2d62d8dcc43732bdae633c77dd2d8d_Traceguids
0x18007758b  mov     edx, 0Fh
0x180077590  call    WPP_SF_
0x180077595  lea     rcx, [rbp+var_58]
0x180077599  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x18007759e  add     rsp, 78h
0x1800775a2  pop     r15
0x1800775a4  pop     r14
0x1800775a6  pop     r13
0x1800775a8  pop     r12
0x1800775aa  pop     rdi
0x1800775ab  pop     rsi
0x1800775ac  pop     rbx
0x1800775ad  pop     rbp
0x1800775ae  retn
```
